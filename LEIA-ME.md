# Meu Dinheiro – como gerar o APK

Você vai usar o GitHub (gratuito) para compilar o app. Não precisa instalar nada no computador.

## 1. Criar a conta e o repositório
1. Entre em https://github.com e crie uma conta gratuita (ou faça login).
2. Clique em **+** (canto superior direito) > **New repository**.
3. Nome: `meu-dinheiro`. Marque **Private** (privado). Clique em **Create repository**.

## 2. Enviar os arquivos
1. Extraia este ZIP no computador.
2. Na página do repositório, clique em **uploading an existing file**.
3. Abra a pasta extraída e selecione **todo o conteúdo dela** (não a pasta em si): `.github`, `www`, `resources`, `package.json`, `capacitor.config.json`, `debug.keystore`, `.gitignore`. Arraste tudo para a página.
   - No Mac ou Linux, pastas que começam com ponto (`.github`) ficam ocultas. Mostre-as com **Cmd+Shift+.** (Mac) ou **Ctrl+H** (Linux).
4. Espere o envio terminar e clique em **Commit changes**.

**Se a pasta `.github` não subir:** no repositório clique em **Add file > Create new file**, digite o nome `.github/workflows/build-apk.yml` (as barras criam as pastas), cole o conteúdo do arquivo `extras/build-apk.yml` e clique em **Commit changes**.

## 3. Gerar o APK
1. Clique na aba **Actions**. Se pedir, clique em **I understand my workflows, go ahead and enable them**.
2. A execução "Gerar APK" começa sozinha. Se não começar, clique em **Gerar APK** na lista da esquerda > **Run workflow**.
3. Aguarde de 5 a 10 minutos até aparecer um ✅ verde.
4. Clique na execução e, no fim da página, em **Artifacts**, baixe **MeuDinheiro-apk**.
5. Extraia o ZIP baixado: dentro está o arquivo **app-debug.apk**.

Se aparecer ❌ vermelho, abra a execução, copie a mensagem de erro do passo que falhou e me envie.

## 4. Instalar no celular
1. Passe o `app-debug.apk` para o celular (cabo USB, Google Drive, e-mail ou WhatsApp para você mesmo).
2. Toque no arquivo. O Android vai pedir para permitir **instalar apps de fontes desconhecidas** para o app que você usou para abrir o arquivo. Ative.
3. Se o Google Play Protect avisar que o app não é verificado, toque em **Instalar mesmo assim**. É normal, porque o app é seu.
4. Abra o **Meu Dinheiro**.

## Levar os dados da versão do Chrome para o APK
1. Na versão antiga (Chrome): **Ajustes > Backup > Copiar** e cole o texto em um lugar seguro (ex.: notas).
2. No app instalado: **Ajustes > Backup**, cole o texto na caixa e toque em **Restaurar**.

## Atualizar o app no futuro
1. Quando eu te mandar um `index.html` novo, abra `www/index.html` no GitHub, clique no lápis (editar) e substitua o conteúdo (ou use **Add file > Upload files** na pasta `www`).
2. Clique em **Commit changes**. O GitHub gera um APK novo sozinho.
3. Baixe e instale **por cima** do app atual. Seus dados são mantidos, porque o APK sempre é assinado com a mesma chave (`debug.keystore`).

## Importante
- Mantenha o repositório **privado**.
- Não apague o arquivo `debug.keystore`. Sem ele, o APK novo não instala por cima do antigo.
- Se desinstalar o app, os dados são apagados. Use **Ajustes > Backup > Compartilhar** para enviar o backup para o Drive, WhatsApp ou notas.
