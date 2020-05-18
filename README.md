# Padronização de código

## Insatalando dependencias e extensões do vscode

### Extensões

- Prettier - Code formatter
- EditorConfig for VS Code

### Dependencias

- `yarn add -D eslint prettier eslint-config-prettier eslint-plugin-prettier babel-eslint`

## Configuração de arquivos

- Com a extensão Prettier e EditorConfig instalada, com botão direito do mouse, na raiz do projeto, escolha a opção
  Generate .editorconfig e substitua o conteúdo do arquivo por :

```
root = true
[*]
end_of_line = lf
indent_style = space
indent_size = 2
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```

- Rode o comando `yarn eslint --init` e siga a ordem

1. to check syntax, find problems, and enforce code style
2. JavaScript modules (import/export)
3. React
4. Does your project use TypeScript? N
5. Browser
6. Use a popular style guide
7. Airbnb
8. Javascript
9. ...Do you want to downgrade? y
10. Would you like to install them now with npm? y

- Delete o arquivo, caso esteja usando yarn, package-lock.json e rode o comando `yarn`

- Abra o arquivo .eslintrs.js e cole o seguinte código

```
module.exports = {
env: {
  browser: true,
  es6: true,
},
extends: ["plugin:react/recommended", "airbnb", "prettier", "prettier/react"],
globals: {
  Atomics: "readonly",
  SharedArrayBuffer: "readonly",
},
parser: "babel-eslint",
parserOptions: {
  ecmaFeatures: {
    jsx: true,
  },
  ecmaVersion: 11,
  sourceType: "module",
},
plugins: ["react", "prettier"],
rules: {
  "prettier/prettier": "error",
  "react/jsx-filename-extension": [
    "warn",
    {
      extensions: ["jsx", "js"],
    },
  ],
  "import/prefer-default-export": "off",
},
};
```

- Na raiz do projeto, crie um arquivo chamado .prettierrc e cole o seguinte códico

```
{
  "singleQuote": true,
  "trailingComma": "es5"
}

```
