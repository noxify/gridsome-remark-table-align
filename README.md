# gridsome-remark-table-align
Gridsome Remark plugin to transform the deprecated align attribute to a style attribute


# Installation

```
npm install --save @noxify/gridsome-remark-table-align
```

# Configuration

## Globally

Inside the `gridsome.config.js` you can define it globally to enable this transformer for all data sources.

```js
module.exports = {

  plugins: [
    {
      use: '@gridsome/source-filesystem',
      options: {
        typeName: 'Blog',
        path: './content/blog/**/*.md',
      }
    }
  ],

  transformers : {
    remark : {
      plugins : [
        '@noxify/gridsome-remark-table-align'
      ]
    }
  }
}
```

## Data Source

Inside the `gridsome.config.js` you can define it individual for each data source.

```js
module.exports = {

  plugins: [
    {
      use: '@gridsome/source-filesystem',
      options: {
        typeName: 'Blog',
        path: './content/blog/**/*.md',
        remark: {
          plugins: [
            '@noxify/gridsome-remark-table-align'
          ]
        }
      }
    }
  ]
}
```

# Usage

The transformer uses (mapbox/hast-util-table-cell-style)[https://github.com/mapbox/hast-util-table-cell-style] to convert the deprecated `align` attribute to the supported `style` attribute.

# Example

## Markdown

```md
| Tables   |      Are      |  Cool |
|----------|:-------------:|------:|
| col 1 is |  left-aligned | $1600 |
| col 2 is |    centered   |   $12 |
| col 3 is | right-aligned |    $1 |
```

## Old HTML

```html
<table>
  <thead>
    <tr>
      <th>Tables</th>
      <th align="center">Are</th>
      <th align="right">Cool</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>col 1 is</td>
      <td align="center">left-aligned</td>
      <td align="right">$1600</td>
    </tr>
    <tr>
      <td>col 2 is</td>
      <td align="center">centered</td>
      <td align="right">$12</td>
    </tr>
    <tr>
      <td>col 3 is</td>
      <td align="center">right-aligned</td>
      <td align="right">$1</td>
    </tr>
  </tbody>
</table>
```

## New HTML

```html

```

