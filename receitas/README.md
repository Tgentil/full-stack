## Setup

Instale o json server

```bash
 npm install -g json-server
 ```

Deploy o banco.json

```bash
json-server banco.json
```

Em um novo terminal, entre na pasta do projeto

```bash
cd receitas
```

## Instalando as dependências
```bash
yarn
# ou
npm install
```

### Iniciando a aplicação em modo de desenvolvimento (hot-code reloading, error reporting, etc.)

```bash
quasar dev
```
ou
```bash
yarn quasar dev
```
ou
```bash
npm run dev
```

Todos os comandos acima iniciam a aplicação em modo de desenvolvimento.


### Verificando os arquivos
```bash
yarn lint
# ou
npm run lint
```


### Formatando os arquivos
```bash
yarn format
# ou
npm run format
```

### Compilando a aplicação para produção
```bash
quasar build
```

### Personalizando a configuração
Veja [Configurando o quasar.config.js](https://v2.quasar.dev/quasar-cli-webpack/quasar-config-js).
