# The Markdown Console theme

*Markdown Console is a Jekyll theme, made with GitHub Pages in mind. You can [preview the theme to see what it looks like](https://mynameiscosmo.github.io/jekyll-theme-markdown-console/), or even [use it today](#usage).*

## Usage

### Default Layout
The default layout includes a header and footer.
See an [example](https://mynameiscosmo.github.io/jekyll-theme-markdown-console/layout-default)

### Minimal Layout
The minimal layout is just the content.
See an [example](https://mynameiscosmo.github.io/jekyll-theme-markdown-console/layout-minimal)

## Customizing

### Configuration variables

Markdown Console will respect the following variables, if set in your site's `_config.yml`:

```yml
title: [The title of your site]
description: [A short description of your site's purpose]
```

Additionally, you may choose to set the following optional variables:

```yml
google_analytics: [Your Google Analytics tracking ID]
```

### Stylesheet

If you'd like to add your own custom styles:

1. Create a file called `/assets/css/style.scss` in your site
2. Add the following content to the top of the file, exactly as shown:
    ```scss
    ---
    ---

    @import "{{ site.theme }}";
    ```
3. Add any custom CSS (or Sass, including imports) you'd like immediately after the `@import` line

### Layouts

If you'd like to change the theme's HTML layout:

1. [Copy the original template](https://github.com/MyNameIsCosmo/jekyll-theme-markdown-console/blob/master/_layouts/default.html) from the theme's repository<br />(*Pro-tip: click "raw" to make copying easier*)
2. Create a file called `/_layouts/default.html` in your site
3. Paste the default layout content copied in the first step
4. Customize the layout as you'd like

## Roadmap

See the [open issues](https://github.com/MyNameIsCosmo/jekyll-theme-markdown-console/issues) for a list of proposed features (and known issues).

## Project philosophy

WIP - as to not completely copypasta the Hacker readme :grinning:

## Contributing

Interested in contributing to this theme? This theme is an open source project, built one contribution at a time by users like you. See [the CONTRIBUTING file](CONTRIBUTING.md) for instructions on how to contribute.

### Previewing the theme locally

If you'd like to preview the theme locally (for example, in the process of proposing a change):

1. Clone down the theme's repository (`git clone https://github.com/MyNameIsCosmo/jekyll-theme-markdown-console`)
2. `cd` into the theme's directory
3. Run `sudo ./test_site.sh`
4. Visit [`localhost:4000`](http://localhost:4000) in your browser to preview the theme

