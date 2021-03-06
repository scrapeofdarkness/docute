# Customization

Cusotmizing Docute is as fun as playing with Lego bricks.

## Navbar

The navbar is used for site-level navigation. It usually contains a link to your homepage and a link to your project's repository. However you can add whatever you want there.

```js
new Docute({
  title: 'Docute',
  nav: [
    {
      title: 'Home',
      link: '/'
    },
    {
      title: 'GitHub',
      link: 'https://github.com/leptosia/docute'
    }
  ]
})
```

The `title` option defaults to the value of `<title>` tag in your HTML, so it's completely optional.

Check out the navbar of this website to see how it looks.

## Sidebar

Sidebar is mainly used for navigations between pages. As you can see from this page, we also use it to display a version selector and a language selector.

```js
new Docute({
  sidebar: [
    // A sidebar item, with multiple sub-links
    {
      title: 'Guide', // Optional
      links: [
        {
          title: 'Getting Started',
          link: '/guide/getting-started'
        },
        {
          title: 'Installation',
          link: '/guide/installation'
        },
      ]
    }
  ]
})
```

Check out the [sidebar](../options.md#sidebar) option reference for more details.

## Versioning

Let's say you have `master` branch for the latest docs and `v0.1` `v0.2` branches for older versions, you can use one Docute website to serve them all, with the help of [`overrides`](../options.md#overrides) and [`sourcePath`](../options.md#sourcepath) option.

```js
new Docute({
  // Configure following paths to load Markdown files from different path
  overrides: {
    '/v0.1/': {
      sourcePath: 'https://raw.githubusercontent.com/user/repo/v0.1'
    },
    '/v0.2/': {
      sourcePath: 'https://raw.githubusercontent.com/user/repo/v0.2'
    }
  },
  // Use `versions` option to add a version selector
  // In the sidebar
  versions: {
    'v1 (Latest)': {
      link: '/'
    },
    'v0.2': {
      link: '/v0.2/'
    },
    'v0.1': {
      link: '/v0.1/'
    }
  }
})
```

## Custom Fonts

Apply custom fonts to your website is pretty easy, you can simply add a `<style>` tag in your HTML file to use [Google Fonts](https://fonts.google.com/):

```html
<style>
/* Import desired font from Google fonts */
@import url('https://fonts.googleapis.com/css?family=Lato');

/* Apply the font to body (to override the default one) */
body {
  font-family: Lato, sans-serif;
}
</style>
```

<button v-on:click="insertCustomFontsCSS">Click me</button> to toggle the custom fonts on this website.

By default a fresh Docute website will use system default fonts.

## CSS Overrides

Default [CSS variables](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables):

```css
:root {
  --accent-color: rgb(6, 125, 247);
  --sidebar-width: 280px;
  --sidebar-bg: white;
  --sidebar-section-title-color: rgb(136, 136, 136);
  --border-color: #eaeaea;
  --header-height: 60px;
  --code-font: SFMono-Regular,Consolas,Liberation Mono,Menlo,Courier,monospace;

  --tip-color: rgb(6, 125, 247);
  --success-color: #42b983;
  --warning-color: #ff9800;
  --danger-color: rgb(255, 0, 31);
}
```
