# RADAR DO INTERIOR – como mexer no site

Tudo se edita pelo navegador, no GitHub: abra o arquivo, clique no lápis (Edit), mude, e clique em **Commit changes**. Em poucos minutos o site é republicado sozinho.

Se o GitHub mostrar um X vermelho em **Actions**, abra a execução e leia a mensagem: quase sempre é uma vírgula ou aspas faltando no arquivo `.json` que você editou.

## 1. Trocar o número de WhatsApp
1. Abra `configuracao.json`.
2. Em `"whatsapp"`, escreva só números: 55 + DDD + número. Exemplo: `"5519999999999"`.
3. Em `"instagram_meio_dia"`, cole o endereço do perfil (começa com `https://`). Enquanto estiver vazio, o botão do Instagram fica escondido.
4. Os valores dos espaços ficam em `"precos"` no mesmo arquivo.

## 2. Cadastrar um anúncio
1. Se tiver imagem, envie para a pasta `anuncios/` (Add file → Upload files).
2. Abra `anuncios.json` e ache o espaço (`destaque`, `medio`, `basico`, `lateral`, `patrocinador_cidade`, `noticia_patrocinada`).
3. Troque `"ativo": false` por `"ativo": true` e preencha `anunciante`, `imagem` (ex.: `"anuncios/padaria.jpg"`), `link`, `texto` e as datas `inicio` e `fim` (formato `2026-11-30`; vazio = sem limite).
4. Para ter mais de um anúncio no mesmo espaço, copie o bloco `{ ... }` e ponha uma vírgula entre os blocos.
5. Para desligar, volte `"ativo"` para `false`. Espaço sem anúncio ativo mostra o convite “Anuncie aqui” sozinho.

## 3. Adicionar uma cidade
1. Em `configuracao.json`, dentro de `"cidades"`, copie um bloco e mude `id` (minúsculas, sem acento, com hífen), `nome`, `sigla`, `cor` e `termos` (como a cidade aparece nos textos).
2. Em `fontes.json`, aponte as fontes dessa cidade (`"cidade": "id-da-cidade"`) ou use `"detectar"`.
3. Em `anuncios.json`, em `patrocinador_cidade`, copie uma linha e use o novo `id`.
4. Rode a atualização (Actions → Atualizar notícias e publicar o site → Run workflow). A página `/id-da-cidade/` e o `sitemap.xml` são criados sozinhos.

## 4. Adicionar uma fonte
1. Abra `fontes.json` e copie um bloco de fonte.
2. Preencha `id`, `nome`, `cidade` e `site` (página inicial). Se souber o endereço do feed RSS, ponha em `feeds`.
3. Rode a atualização e abra `dados/status.json`: o `estado` da fonte diz `ok`, `sem_feed` (o site não oferece feed; fica só o link) ou o erro.
4. Não tente contornar bloqueios de sites. Se uma fonte não oferece feed, use `"tipo": "so_link"`.

## 5. Publicar uma matéria própria
1. Na pasta `materias/`, crie um arquivo `.txt` (modelo em `_como-escrever.txt`).
2. Escreva `titulo:`, `autor:`, `cidade:`, `data:`, uma linha em branco e o texto.
3. Salve (Commit). A matéria aparece com o selo “Matéria Radar do Interior”. Data futura = só aparece na hora marcada.
4. Para remover o exemplo, apague `materias/exemplo-demonstracao.txt`.

**Próximos passos quando a equipe crescer:** painel de edição visual e uma página própria para cada matéria.
