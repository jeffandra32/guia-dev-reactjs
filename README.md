# Configurar estrutura React.JS

## Vscode

- _settingd.json_ <br />
  {
  "workbench.iconTheme": "material-icon-theme",
  "workbench.startupEditor": "newUntitledFile",
  "window.zoomLevel": 1,
  "typescript.updateImportsOnFileMove.enabled": "never",
  "extensions.ignoreRecommendations": true,
  "editor.fontSize": 15,
  "git.autofetch": true,
  "editor.suggestSelection": "first",
  "files.autoSave": "off",
  "workbench.colorTheme": "Sublime Monokai",
  "javascript.updateImportsOnFileMove.enabled": "always",
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,
  "editor.lineHeight": 24,
  "editor.formatOnSave": true,
  "editor.rulers": [80, 120],
  "editor.tabSize": 2,
  "editor.renderLineHighlight": "gutter",
  "terminal.integrated.fontSize": 14,
  "emmet.syntaxProfiles": {
  "javascript": "jsx"
  },
  "breadcrumbs.enabled": true,
  "terminal.integrated.fontFamily": "Fira Code",
  "prettier.jsxSingleQuote": true,
  "prettier.singleQuote": true,
  "[plaintext]": {}
  }

# Dependências Inicias

- `yarn init`
- `yarn add @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli -D`
- `yarn add react react-dom` ||
- `yarn create react-app <nome-do-projeto>`
- `yarn add eslint`
- `yarn eslint --init`
- `yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D`

# Criando arquivos Iniciais

- _babel.config.js_ <br />
  `module.exports = { presets: [ "@babel/preset-env", "@babel/preset-react" ], plugins: [ '@babel/plugin-proposal-class-properties' ] }`

- _webpack.config.js_ <br />
  `const path = require('path'); module.exports = { entry: path.resolve(__dirname, 'src', 'index.js'), output: { path: path.resolve(__dirname, 'public'), filename: 'bundle.js' }, devServer: { contentBase: path.resolve(__dirname, 'public'), }, module: { rules: [ { test: /\.js$/, exclude: /node_modules/, use: { loader: 'babel-loader' } }, { test: /\.css$/, use: [ { loader: 'style-loader' }, { loader: 'css-loader' }, ] }, { test: /.*\.(gif|png|jpe?g)$/i, use: { loader: 'file-loader' } } ] }}`

- _.eslint.js_ <br />
  `module.exports = { env: { browser: true, es6: true, }, extends: [ 'airbnb', 'prettier', 'prettier/react' ], globals: { Atomics: 'readonly', SharedArrayBuffer: 'readonly', }, parser: 'babel-eslint', parserOptions: { ecmaFeatures: { jsx: true, }, ecmaVersion: 2018, sourceType: 'module', }, plugins: [ 'react', 'prettier' ], rules: { 'prettier/prettier': 'error', 'react/jsx-filename-extension': [ 'warn', { extensions: ['.jsx', '.js'] } ], 'import/prefer-default-export': 'off' }, };`

- _.prettierrc_ <br />
  `{ "singleQuote": true, "trailingComma": "es5" }`

- _.editorconfig_ <br />
  `root = true [*] end_of_line = lf indent_style = space indent_size = 2 charset = utf-8 trim_trailing_whitespace = true insert_final_newline = true`

- _.gitignore_ <br />

### See https://help.github.com/articles/ignoring-files/ for more about ignoring files.

/node_modules
/.pnp
.pnp.js

### testing

/coverage

### production

/build

### misc

.DS_Store
.env.local
.env.development.local
.env.test.local
.env.production.local

npm-debug.log*
yarn-debug.log*
yarn-error.log\*

# Estrutura Inicial

### Dependências

- `yarn add react-router-dom`

### Códigos

- _package.js_ <br />
  `"scripts": { "build": "webpack --mode development" }`

- _index.js_ <br />
  `import React from 'react'; import ReactDOM from 'react-dom'; import App from './App'; ReactDOM.render(<App />, document.getElementById('root'));`
