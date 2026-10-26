# Primeira vez: colocar o RADAR DO INTERIOR no ar

Você precisa de uma conta gratuita no GitHub (github.com). Não precisa de terminal.

1. **Criar o repositório.** No GitHub, clique em **+** → **New repository**. Nome: `radar-do-interior`. Marque **Public** (o GitHub Pages gratuito exige isso) e **Add a README file**. Clique em **Create repository**.
2. **Enviar os arquivos.** Descompacte o ZIP. No repositório, clique **Add file → Upload files** e arraste **o conteúdo** da pasta `radar-do-interior` (pastas `css`, `js`, `dados`, `materias`, `anuncios`, `coletor` e os arquivos soltos). Clique em **Commit changes**.
3. **Criar o arquivo do agendador.** A pasta `.github` é escondida no computador e pode não subir ao arrastar. Então: **Add file → Create new file**. No campo do nome digite exatamente `.github/workflows/atualizar.yml` (ao digitar a barra, o GitHub cria as pastas). Abra o `atualizar.yml` do ZIP no Bloco de Notas, copie tudo e cole. **Commit changes**.
4. **Liberar escrita do robô.** **Settings → Actions → General → Workflow permissions** → **Read and write permissions** → **Save**.
5. **Ativar o GitHub Pages.** **Settings → Pages → Build and deployment → Source:** escolha **GitHub Actions**.
6. **Preencher o que falta.** Em `configuracao.json`: `whatsapp` e `instagram_meio_dia`. Em `fontes.json`: o campo `site` das três fontes locais marcadas **PREENCHER** (Prefeitura de Mococa, Portal Rio Pardo, Casa Branca Portal da Cidade).
7. **Rodar a primeira atualização.** Aba **Actions** → **Atualizar notícias e publicar o site** → **Run workflow**. Espere 1 a 3 minutos até o visto verde.
8. **Abrir o site.** Em **Settings → Pages** aparece o endereço: `https://SEU-USUARIO.github.io/radar-do-interior/`.
9. **Conferir as fontes.** Abra `dados/status.json`. Cada fonte tem `estado`: `ok`, `sem_feed`, `aguardando_endereco` ou `erro`. Se houver `sem_feed`, mande esse arquivo para mim e eu ajusto o endereço do feed.

Depois disso o site se atualiza sozinho a cada hora. Se o GitHub pausar o agendador por inatividade (acontece depois de 60 dias sem atividade no repositório), entre em **Actions** e reative.
