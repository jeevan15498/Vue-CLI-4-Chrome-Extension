# Vue CLI 4 - Chrome Extension

Browser extension development plugin for vue-cli 4.x

* https://github.com/adambullmer/vue-cli-plugin-browser-extension


# Install Vue CLI Project

First create vue cli simple project and then add extension.

```bash
vue create demo-extension
```

Using the vue cli `vue add browser-extension` command

### Usage

```bash
npm run serve
npm run build
```

### Info

* https://github.com/adambullmer/vue-cli-plugin-browser-extension#browser-polyfills

## Errors

### manifest.json file not copy

Open `vue.config.js` file and insert this code.

```js
chainWebpack(webpackConfig) {
    webpackConfig.plugin('copy-manifest').tap(args => {
      args[0][0].force = true
      return args
    })
},
```

###  Release New Version

Update version number only `package.json` file

### Delete un-use file

1. App.vue
2. main.js


### Disable PWA plugin in Vue CLI 3

1. Removing the `registerServiceWorker.js` file
2. removing the `import of registerServiceWorker.js` from `main.js`.
3. removing the PWA plugin from the devDependencies in `package.json`.