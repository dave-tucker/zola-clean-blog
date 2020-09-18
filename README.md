zola-clean-blog
===============

![screenshot](screenshot.png)

A port of the StartBootstrap Clean Blog theme, for Zola.

## Demo

[Live Demo](https://zola-clean-blog.netlify.com)

## Usage

To use the theme, clone this repository to your `themes` directory.
It requires that you use the categories and tags taxonomies.
This can be done with the following additions to `config.toml`:
```toml
theme = "zola-clean-blog"

taxonomies = [
    {name = "categories", rss = true, paginate_by=5},
    {name = "tags", rss = true, paginate_by=5},
]
```

## Features

- Paginated Home/Categories/Tag Pages
- Customizable Menu
- Customizable Social Links

## How To Customize

- To replace header images, add a new image to `static/img/$page-bg.jpg` where `$page` is one of `about`, `home`, `post` or `contact`.

- To replace the copyright field, create your own `templates/index.html` to extend the template and add a `copyright` block:
```
{% extends "zola-clean-blog/templates/index.html" %}
{% block copyright %}
Copyright %copy; Example, Inc. 2016-2019
{% endblock copyright %}
```

- To add a new menu item, override `clean_blog_menu` in your `config.toml`. You can use `$BASE_URL` to reference your own site.

- To add a new social link, override `clean_blog_social` in your `config.toml`. You can use `$BASE_URL` to reference your own site.

- To add Google Analytics, you may add your script to the `extrascripts` block using your own `index.html`
```
{% extends "themes/zola-clean-blog/templates/index.html" %}
{% block analytics %}
<script>
...
</script>
{% endblock analytics %}
```

## Sidebar automatic links

Merged a little bit of Sidebar formatting from the Dinkleberg theme. To add
sidebar entries add this to the config in the '[extra]' section

```
sidebar = [
    {name = "Social", urls=[
        {name="Github", url="https://github.com"},
    ]},
    {name = "Hello World", urls=[
        {name="Hi", url="https://pages.github.com"}
    ]}
]
```
