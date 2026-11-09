# Eclipse Real — Painel da Guild (PokeTibia PKA)

Ranking semanal de pontos e doações da guild, com comparativo entre semanas.
Os dados ficam na pasta `dados/`: cada arquivo é uma semana, no formato exportado pelo jogo.

## Estrutura

```
index.html   → o painel (não precisa mexer)
dados/       → um .json por semana, exatamente como sai da exportação
.nojekyll    → faz o GitHub Pages servir os arquivos como estão
```

## Publicar (uma vez só — dono do repositório)

1. Crie um repositório **público** no GitHub (ex.: `eclipse-real`).
2. Suba todo o conteúdo desta pasta (index.html, README.md, .nojekyll e a pasta dados).
3. Vá em **Settings → Pages**, em *Source* escolha **Deploy from a branch**, branch `main`, pasta `/ (root)` e salve.
4. Em 1 a 2 minutos o painel fica em `https://SEU-USUARIO.github.io/eclipse-real/`.
5. Em **Settings → Collaborators → Add people**, adicione o usuário do GitHub do **Bielq**. Ele precisa aceitar o convite por e-mail.

O painel descobre usuário e repositório sozinho pelo endereço do GitHub Pages.
Se usar domínio próprio, preencha `GH_OWNER` e `GH_REPO` no início do script do `index.html`.

## Atualizar a semana (líder)

1. Exporte a lista de membros da guild no jogo.
2. No GitHub, abra a pasta **dados** e clique em **Add file → Upload files**.
3. Arraste o arquivo `.json` sem renomear e clique em **Commit changes**.
4. Em 1 a 2 minutos a semana nova aparece no painel.

- A data da semana vem do campo `exportedAt` do arquivo.
- Dois arquivos da mesma data: vale a exportação mais recente.
- Para remover uma semana, apague o arquivo dela na pasta `dados`.
- Exporte sempre no mesmo dia e horário da semana para o comparativo ficar justo.

## Observações

- A lista de arquivos é lida pela API pública do GitHub (limite de 60 consultas por hora por IP).
  O painel guarda essa lista por 5 minutos no navegador, então o limite não costuma ser problema.
- Depois do upload, o painel pode levar até 5 minutos para mostrar a semana nova em quem já abriu a página antes (cache). Basta recarregar depois disso.
- Todo upload fica registrado no histórico de commits (quem subiu e quando) e pode ser revertido.
