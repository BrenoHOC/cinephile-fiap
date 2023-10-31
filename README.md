# Guia de Configuração do Node-RED (Windows)

Este guia descreve os passos para configurar o Node-RED no Windows. Certifique-se de seguir todas as etapas abaixo.

## Instalação do Node-RED

1. Utilize o seguinte comando para instalar o Node-RED globalmente, incluindo permissões inseguras:

```bash
npm install -g --unsafe-perm node-red
```

2. Inicie o Node-RED via terminal com o seguinte comando:

```bash
node-red
```

3. Acesse o Node-RED no seu navegador, indo para [http://127.0.0.1:1880](http://127.0.0.1:1880).

## Instalação de Bibliotecas

4. No Node-RED, vá para o menu "Manage Palette" e instale as seguintes bibliotecas:

   - node-red-contrib-auth
   - node-red-contrib-moment
   - node-red-contrib-uuid
   - node-red-dashboard
   - node-red-node-email
   - node-red-node-ui-table

5. Além disso, você deve instalar as seguintes bibliotecas via linha de comando:

```bash
npm install bcrypt moment uuid
```

## Configuração de Variáveis Globais

6. No arquivo `settings.js`, na seção `functionsGlobalContext`, adicione as seguintes linhas para configurar as variáveis globais:

```javascript
functionsGlobalContext: {
    uuid: require('uuid'),
    bcrypt: require('bcrypt')
}
```

7. Salve o arquivo `settings.js` após fazer as alterações.

## Configuração das variáveis de ambiente

8. Criar arquivo .env e inserir as variáveis de ambiente necessárias.

9. Utilizar o comando abaixo para exportar as variáveis de ambiente:

```bash
export $(grep -v '^#' .env | xargs -L 1  -d '\r' -d '\r\n')
```

## Importação do Fluxo

10. No menu Node-RED, clique em "Import" (ou use a combinação de teclas Ctrl+I) para importar o arquivo `flows.json`.

11. Copie o conteúdo do arquivo flows.json deste repositório (https://github.com/BrenoHOC/cinephile-fiap).

Agora, seu ambiente Node-RED no Windows está configurado e pronto para uso. Você pode começar a criar e gerenciar fluxos no Node-RED.
