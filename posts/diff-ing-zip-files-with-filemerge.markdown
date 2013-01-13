<!--
.. title: Diff-ing .zip files with FileMerge
.. slug: diff-ing-zip-files-with-filemerge
.. date: 2010/12/13 10:36:00
.. tags: bash, Mac, StackOverflow, migrated_from_blogger
.. link:
.. description:
-->

This isn't particularly elegant, but you can use the FileMerge application that comes with Mac OS X developer tools to compare the contents of zip files using a custom filter.

Create a script `~/bin/zip_filemerge_filter.bash` with contents:


    ##
    #  List the size, CR-32 checksum, and file path of each file in a zip archive,
    #  sorted in order by file path.
    ##
    unzip -v -l "${1}" | cut -c 1-9,59-,49-57 | sort -k3
    exit $?
    Make the script executable (chmod +x ~/bin/zip_filemerge_filter.bash).

Open FileMerge, open the Preferences, and go to the "Filters" tab. Add an item to the list with:

* Extension: `zip` _(I've also added the filer for `.jar` and `.war` files.)_
* Filter: `~/bin/zip_filemerge_filter.bash $(FILE)`
* Display: _Filtered_
* Apply: _No_
    

Then use FileMerge (or the command line `opendiff` wrapper) to compare two .zip files.

This won't let you diff the contents of files within the zip archives, but will let you quickly see which files appear within one only archive and which files exist in both but have different content (i.e. different size and/or checksum).

(_Cross-posted on
[StackOverflow](http://stackoverflow.com/questions/587442/is-there-a-safe-way-to-run-a-diff-on-two-zip-compressed-files/4429169#4429169) and [my old blogger blog](http://michaelrabbitt.blogspot.com/2010/12/diff-ing-zip-files-with-filemerge.html)._)
