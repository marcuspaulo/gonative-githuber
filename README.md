# Projeto em React-Native - Listar Repositórios e Organizações do Usuário do Github

#Tela de Login
![Tela de Login](/images/login.png)

#Tela de Repositórios
![Repositórios](/images/repositories.png)

#Tela de Organização
![Organização](/images/organizations.png)

# Criando um projeto em React-native

```sh
$ react-native init Githuber
```

# 1 - Criar/Ajustar o arquivo ESLint

.eslintrc.json

```js
{
  "parser": "babel-eslint",
  "extends": ["airbnb", "plugin:react-native/all"],
  "plugins": ["react-native", "jsx-a11y", "import"],
  "env": {
    "jest": true
  },
  "rules": {
    "react/jsx-filename-extesion": [
      "error",
      {
        "extensions": [".jsx", ".js"]
      }
    ],
    "import/prefer-default-export": "off"
  },
  "globals": {
    "__DEV__": true
  },
  "settings": {
    "import/resolver": {
      "babel-plugin-root-import": {}
    }
  }
}

```

# 2 - Configurar o editorconfig (existe um plugin do VSCode)

```js
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
end_of_line = lf
insert_final_newline = true
trim_trailing_whitespace = true
```

# 3 - Configurar o arquivo .babelrc (Root import)

```js
{
  "presets": ["module:metro-react-native-babel-preset"],
  "plugins": [
    [
      "babel-plugin-root-import",
      {
        "rootPathSuffix": "src"
      }
    ]
  ],
  "env": {
    "production": {
      "plugins": [
        "babel-plugin-root-import",
        {
          "rootPathSuffix": "src"
        }
      ]
    }
  }
}

```

# 3 - Configurar o Reactotron

3.1 - Criar o arquivo: ReactotronConfig.js, dentro da pasta /src/config

```js
import Reactotron from "reactotron-react-native";

if (__DEV__) {
  const tron = Reactotron.configure() // controls connection & communication settings
    .useReactNative() // add all built-in react native plugins
    .connect(); // let's connect!

  console.tron = tron;

  tron.clear();
}
```

# Adicional: Settings do Visual code

```js
{
  //Define o tema do VSCode
  "workbench.colorTheme": "Dracula",

  // Configura tamanho e família da fonte
  "editor.fontSize": 14,
  "editor.lineHeight": 20,
  "editor.fontFamily": "Fira Code",
  "editor.fontLigatures": true,

  "workbench.iconTheme": "material-icon-theme",
  "window.zoomLevel": 1,

  "prettier.eslintIntegration": true,
  "editor.formatOnSave": true,

  "emmet.includeLanguages": {
    "nunjucks": "html"
  },
  "git.path": "/usr/bin/git",
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
  "javascript.format.enable": false,
  "git.autofetch": true,
  "colorize.ignore_search_variables_info": true
}

```

# Instalando a dependências de Rotas para o projeto e animações(gestos)

```sh
$ yarn add react-navigation react-native-gesture-handler
```

# Após isso, é necessário "linkar" as dependências do Gesture Handler

```sh
$ react-native link react-native-gesture-handler
```

# Executar o Projeto iOS

```sh
$ react-native run-ios --simulator "iPhone XS Max"
```

# Executando o projeto sem cache (Metro bundle)

```sh
$ react-native start --reset-cache
```

# Configurando o ESLint

```sh
$ yarn add eslint -D
```

#Iniciando a configuração do ESlint

```sh
$ yarn eslint --init
```

Selecione as opções:
1- Use a popular style guide
2 - Airbnb (https://github.com/airbnb/javascript)
3 - Do you use React? Yes
4 - What format do you want your config file to be in? (Use arrow keys)
JSON
5 - Would you like to install them now with npm? Yes

# Instalando mais dois plugins para o ESLint

```sh
$ yarn add babel-eslint eslint-plugin-react-native -D
```

# Plugin para imports

```sh
$ yarn add babel-plugin-root-import -D
```

#Configuração do Babel Root Import

```js
{
  "presets": ["module:metro-react-native-babel-preset"],
  "plugins": [
    [
      "babel-plugin-root-import", {
        "rootPathSuffix": "src"
      }
    ]
  ],
  "env": {
    "production": {
      "plugins": [
        "babel-plugin-root-import", {
          "rootPathSuffix": "src"
        }
      ]
    }
  }
}

```

# Para que o ESLint entenda o import (root import)

```sh
$ yarn add  eslint-import-resolver-babel-plugin-root-import -D
```

# Configuração do .eslintrc.json

```js
{
  "parser": "babel-eslint",
  "extends": ["airbnb", "plugin:react-native/all"],
  "plugins": ["react-native", "jsx-a11y", "import"],
  "env": {
    "jest": true
  },
  "rules": {
    "react/jsx-filename-extesion": [
      "error",
      {
        "extensions": [".jsx", ".js"]
      }
    ],
    "import/prefer-default-export": "off"
  },
  "globals": {
    "__DEV__": true
  },
  "settings": {
    "import/resolver": {
      "babel-plugin-root-import": {}
    }
  }
}

```

# Para o VSCode reconhecer o root-import, precisa criar o arquivo

jsconfig.json

```js
{
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "~/*": ["src/*"]
    }
  }
}
```

# Instalando o Reactotron

```js
$ yarn add reactotron-react-native
```

https://github.com/infinitered/reactotron/blob/master/docs/quick-start-react-native.md

# Configuração do ReactotronConfig.js

```js
import Reactotron from "reactotron-react-native";

if (__DEV__) {
  const tron = Reactotron.configure() // controls connection & communication settings
    .useReactNative() // add all built-in react native plugins
    .connect(); // let's connect!

  console.tron = tron;

  tron.clear();
}
```

# Instalando o Axios

```sh
$ yarn add axios
```

# Instalando as Prop-types

```sh
$ yarn add prop-types
```

# Instalando as Statusbar - serve para definir o tamanho. (Independente da versão do dispositivo)

```sh
$ yarn add react-native-status-bar-height
```

# Instalando Dependência para trabalhar com icones

```sh
$ yarn add react-native-vector-icons
```

# Fazendo o link da dependência de Icones

```sh
$ react-native link react-native-vector-icons
```
