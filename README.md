# Anpu theme for Zola

This is a port of the Hugo theme [Anubis](https://github.com/Mitrichius/hugo-theme-anubis/tree/master/layouts) for [Zola](https://getzola.org).

![screenshot](screenshot.png)

## Usage

The theme requires Zola 0.23.6 or later.

In order to use the theme you need to clone this repository in your `themes` folder:

```bash
git clone https://github.com/zbrox/anpu-zola-theme.git themes/anpu
```

Then set your theme setting in `config.toml` to `anpu`:

```toml
theme = "anpu"
```

This theme requires both the `tags` and `categories` taxonomies.

```toml
taxonomies = [
    { name = "categories" },
    { name = "tags" },
]
```

The theme's globally available Tera components are `anpu.page_info` and
`anpu.page_listing` (both take `page` and `config`), and
`anpu.page_pagination` (takes `paginator`).

The sample site's syntax highlighting uses `[markdown.highlighting]`; see the
[Zola highlighting documentation](https://www.getzola.org/documentation/content/syntax-highlighting/)
to choose another theme.

## How To Customize

There are two things you can customize:

- The links to be included in the menu
- The date format of the posts

### Menu links

In your `config.toml` under the `[extra]` section you need to set the `anpu_menu_links` list.

Example:

```toml
[extra]
anpu_menu_links = [
    { url = "$BASE_URL/about/", name = "About" },
]
```

If you include `$BASE_URL` in the url of a link it will be replaced to the base url of your site.

### Date format

In your `config.toml` under the `[extra]` section you need to set the `anpu_date_format` value.

Example:

```toml
[extra]
anpu_date_format = "%e %B %Y"
```

The Tera `date` filter uses [Jiff's strftime format](https://docs.rs/jiff/latest/jiff/fmt/strtime/index.html#conversion-specifications).
