<!-- 
.. title: Open in SourceTree from IntelliJ IDEA
.. slug: open-in-sourcetree-from-intellij-idea
.. date: 2012/07/05 12:11:00
.. tags: IntelliJ IDEA, SourceTree, bash, git, hg, cli, migrated_from_tumblr
.. link: 
.. description: 
-->

I'm quite fond of [SourceTree](http://www.sourcetreeapp.com/) for managing Git repositories (it does Mercurial as well).  SourceTree comes with an `stree` command to open repositories from the command line.  I wanted to set up an [external tool in IntelliJ IDEA](http://www.jetbrains.com/idea/webhelp/external-tools.html) to the repo containing the current source file, `stree` only works if you call it without any arguments with a current working directory of the root level of a repo, or if you pass the path to the root level of a repo as an argument.  This is fine if you have only a single Git source root in your IntelliJ project:  You can just use call `stree` directly with the `$ProjectFileDir$` macro as a parameter.  But if you have multiple modules in your project with different Git source roots, it gets more difficult.  I tried using the `$ModuleFileDir$` macro, but this seems to the directory where the `.iml` file for the module is stored, which is not the source root of the module.

So, I ended up writing a small wrapper for `stree` which can take the path to any file or directory within a Git or Mercurial repo as an argument and invokes `stree` with the path to the root of the repo:

[:gist: 3051104]
