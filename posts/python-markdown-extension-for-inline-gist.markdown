<!--
.. title: Python Markdown Extension for Inline Gist
.. slug: python-markdown-extension-for-inline-gist
.. date: 2013/03/04 00:23:36
.. tags: Python, Markdown, Nikola, GitHub
.. link:
.. description:
-->

As discussed in [this thread on the Nikola forum](https://groups.google.com/d/topic/nikola-discuss/ScaJGcTGBBY/discussion), I'd wanted a way add a custom inline "gist" directive to Nikola which I could use in my markdown posts to include the full contents of the gist in a `<noscript>` tag.  This makes gist contents available in the site RSS feed and when viewing the site with Javascript disabled.  Here's a gist (of course) with the Python Markdown extension that makes this possible:

[:gist: 5080027]

I'll be sending a push request shortly to get this integrated into Nikola.  Thanks to Roberto Alsina for already `gist` support to reStructuredText posts in Nikola.

_Update: [Pull request accepted](https://github.com/ralsina/nikola/pull/380)!_