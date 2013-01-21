<!-- 
.. title: Confluence numbered heading bookmarklet
.. slug: confluence-numbered-heading-bookmarklet
.. date: 2013/01/20 19:42:27
.. tags: Confluence, bookmarklet, JavaScript
.. link:
.. description:
-->
Unfortunately, the [Numbered Heading Confluence plugin](https://marketplace.atlassian.com/plugins/nl.avisi.confluence.plugins.numberedheadings) isn't available for [Atlassian OnDemand](https://confluence.atlassian.com/display/AOD/Atlassian+OnDemand+Plugin+Policy#AtlassianOnDemandPluginPolicy-Confluence), and Atlassian doesn't seem to be in any hurry to implement [CONF-1732](https://jira.atlassian.com/browse/CONF-1732), so I put together this poor-man's hack:

This bookmarklet adds hierarchical section numbers to the section headers on the current confluence page. Note that it does not permanently change the content of the page; it only transforms the displayed HTML until the page is re-loaded. One of these days I'll figure out how to get this to work as a [user script](http://userscripts.org/).

[Confluence numbered section header bookmarklet](javascript:%28function%28%29%2520%7Bfunction%2520addSectionNumber%2520%28elem%2C%2520sectionNumber%2C%2520parentSection%2C%2520level%29%2520%7Bvar%2520sectionNumberStr%2520%3D%2520%2527%2527%3Bvar%2520sectionSpan%3Bif%2520%28level%2520%3E%25201%29%2520%7BsectionNumberStr%2520%3D%2520parentSection%2520%2B%2520%2527.%2527%2520%2B%2520sectionNumber%3B%7D%2520else%2520if%2520%28level%2520%3E%25200%29%2520%7BsectionNumberStr%2520%3D%2520sectionNumber.toString%28%29%3B%7Dif%2520%28level%2520%3E%25200%2520%26%26%2520jQuery%28elem%29.find%28%2527.section-number%2527%29.length%2520%3D%3D%3D%25200%2520%29%2520%7BsectionSpan%2520%3D%2520jQuery%28%2527%3Cspan%2520class%3D%2522section-number%2522%3E%2527%29.text%28sectionNumberStr%2520%2B%2520%2527%2520%2527%29%3BjQuery%28elem%29.prepend%28sectionSpan%29%3B%7Dif%2520%28%2520level%2520%3D%3D%3D%25200%2520%29%2520%7BjQuery%28elem%29.find%28%2527h1%2527%29.each%28%2520function%28index%2C%2520element%29%2520%7BaddSectionNumber%28element%2C%2520%28index%2520%2B%25201%29%2C%2520sectionNumberStr%2C%2520%28level%2520%2B%25201%29%29%3B%7D%29%3B%7D%2520else%2520if%2520%28%2520level%2520%3C%25206%2520%29%2520%7BjQuery%28elem%29.nextUntil%28%2527h%2527%2520%2B%2520level%2C%2520%2527h%2527%2520%2B%2520level%2520%2B%2520%2527%2Ch%2527%2520%2B%2520%28level%2520%2B%25201%29%29.each%28%2520function%28index%2C%2520element%29%2520%7BaddSectionNumber%28element%2C%2520%28index%2520%2B%25201%29%2C%2520sectionNumberStr%2C%2520%28level%2520%2B%25201%29%29%3B%7D%29%3B%7Dreturn%3B%7DaddSectionNumber%28jQuery%28%2527%23main-content%2527%29.first%28%29%2C%25200%2C%2520%2527%2527%2C%25200%29%3B%7D%29%28%29%3B)

Source:

<script src="https://gist.github.com/4582903.js"></script>
