# gridsome-remark-table-align
Gridsome Remark plugin move the `table` align defintion to the `tableCell` definition.

With this changes, you can use [@noxify/gridsome-remark-classes](https://github.com/noxify/gridsome-remark-classes) to add your own classes.


# Installation

```
npm install --save @noxify/gridsome-remark-table-align
```

# Usage

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

# Documentation

You can find the complete documentation here: https://webstone.info/documentation/gridsome-remark-table-align
