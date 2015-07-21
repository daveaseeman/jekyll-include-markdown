# The Hack
_set it and forget it_<br>
The way we get around the issues discussed above is by capturing the markdown file as a parameter and passing it to an html include. Here is in three easy steps:
## Step 1:
Put that capture/markdownify block in it's own include. Mine is called `_includes/markdown.html`:<br>
`{% capture markdown %}{% include your_markdown_file.md %}{% endcapture %}{{ markdown | markdownify }}`

## Step 2:
Include that html file wherever you want to include markdown, and pass it the markdown file's name as a parameter. My parameter's name is `file`:<br>
`{% include markdown.html file="your_markdown_file.md" %}`

## Step 3:
Loosen up that `markdown.html` file, change `your_markdown_file` to the parameter `{{ include.file }}`:<br>
`{% capture markdown %}{% include {{ include.file }}.md %}{% endcapture %}{{ markdown | markdownify }}`

And now you're all set! That one html include will allow you to include markdown files anywhere on your Jekyll site simply by passing the filename as a parameter.

But wait, there's more!
