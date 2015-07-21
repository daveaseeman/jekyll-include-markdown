# Introduction
_markdown not included, some assembly required_<br>
Currently, Jekyll's `include` feature does not support the inclusion and proper rendering of markdown files. There are two main ways around this:

1. You can write a plugin to convert the markdown to html when your site builds.
2. You can capture the file as a liquid variable and then apply the `markdownify` filter.

Most users either:
- Avoid using markdown anywhere except for posts and possibly collections
- Apply #1 if they are not using Github as a host (or if they are using a more complex method)
- Or they rewrite that darn capture/markdownify block every time.

But there is a another way!
