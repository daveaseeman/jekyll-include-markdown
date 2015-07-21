# The Hack
_set it and forget it_<br>
The way we get around the issues discussed above is by creating an html include that accepts the included file's path as a parameter and renders it.

specifying a markdown file's name as a parameter in the include tag, and 

## Create the Include
Create a an html include that accepts a parameter specifying the path to the file being included. Mine is called `_includes/markdown.html`:
```
<!--{% capture markdown %}{% include {{ include.path }} %}{% endcapture %}{{ markdown | markdownify }}-->
```

## Pass the File Name
Include the html file, and pass it the name of the markdown to be rendered, in this case, `path`:
```
{% include markdown.html path="" %}
```

And now you're all set! That one html include will allow you to include markdown files anywhere on your Jekyll site simply by passing the file path as a parameter.

But wait, there's more!
