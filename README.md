# Publicação no GitHub Pages

## 1. Coloque a música
Copie seu MP3 para `audio/` e renomeie para `musica.mp3`.
O player já procura `audio/musica.mp3`.

## 2. Defina sua senha
No Linux, execute no terminal (troque a frase entre aspas pela senha que você quer usar):

```bash
printf %s 'SUA-SENHA-AQUI' | sha256sum
```

Copie somente os 64 caracteres hexadecimais do resultado. Abra `index.html` e procure:

```js
const PASSWORD_SHA256 = "SUBSTITUA_PELO_HASH_SHA256_DA_SENHA";
```

Substitua o texto dentro das aspas pelo hash gerado. Não coloque a senha em si no HTML.

## 3. Publique
1. Crie um repositório no GitHub. Se quiser, deixe-o privado (isso não torna o site privado).
2. Extraia este ZIP.
3. Envie o conteúdo desta pasta para a raiz do repositório: `index.html`, `images/` e `audio/`.
4. No GitHub, abra **Settings → Pages**.
5. Em **Build and deployment**, selecione **Deploy from a branch**.
6. Escolha a branch `main` e a pasta `/ (root)`, depois clique em **Save**.
7. Aguarde o endereço aparecer na seção Pages.

## Aviso importante sobre a senha
Esta senha em JavaScript é apenas uma barreira casual. O HTML, o JavaScript, as imagens, o MP3 e os textos continuam públicos e podem ser acessados por quem souber inspecionar o site ou contornar a tela. O hash não transforma o GitHub Pages em hospedagem privada. Não use senha reutilizada nem coloque informações sensíveis. Para proteção real, é necessário autenticar no servidor (por exemplo, Cloudflare Access/Worker ou hospedagem com autenticação).
