# swagger-ui

リポジトリの作り方

```bash
# .gitignore は https://www.toptal.com/developers/gitignore からよしなに生成する
npm init -y
npm install swagger-ui-dist
mkdir docs
cp node_modules/swagger-ui-dist/* ./docs
```

`docs/swagger-initializer.js` を修正する。

```javascript
window.onload = function () {
  //<editor-fold desc="Changeable Configuration Block">

  // the following lines will be replaced by docker/configurator, when it runs in a docker-container
  window.ui = SwaggerUIBundle({
    url: "https://petstore.swagger.io/v2/swagger.json",
    dom_id: "#swagger-ui",
    deepLinking: true,
    presets: [SwaggerUIBundle.presets.apis, SwaggerUIStandalonePreset],
    plugins: [SwaggerUIBundle.plugins.DownloadUrl],
    layout: "StandaloneLayout",
    queryConfigEnabled: true, // 追加
  });

  //</editor-fold>
};
```

リポジトリの 「Settings」「Pages」から、github pages を設定する。

| ブランチ | ディレクトリ |
| -------- | ------------ |
| main     | docs         |
