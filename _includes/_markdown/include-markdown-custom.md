# Customization
_include anything you need_<br>
You can imagine how this method would allow for a great deal of customization. Since you can pass as many parameters to the include as you would like, you can do stuff like this:

{% raw %}
    {%if include.selector%}<{{include.selector}} {%if include.classes%}class="{{include.classes}}"{%endif%} {%if include.id%}id="{{include.id}}{%endif%}">{%endif%}
      {% capture markdown %}{% include {{include.path}} %}{% endcapture %}{{ markdown | markdownify }}
    {%if include.selector%}</{{include.selector}}>{%endif%}
{% endraw %}

That is the `markdown.html` file for this site. In it, `selector`, `classes`, `id`, and `file` are all accepted parameters. If there is no `selector` then your markdown will be converted to html and included in the page. If `selector` is specified, then the html generated from your markdown will be wrapped in an html element and you are given the option to specify an `id` and a single or multiple `classes`. Also note that the `include` is now looking in the subfolder `_markdown/`. Placing your markdown files in subfolders allows you to keep your source more organized. If you have a complex site with the need to include lots of markdown, you could consider making your `_subfolder` another parameter like `{{include.subfolder}}` or even make it a page, site, or data variable. It's up to you!
