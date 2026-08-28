# dsb-covers

Capas públicas dos posts do Data Security Briefing.

O workbench do Composio baixa estes arquivos no publish. Por isso o repositório é **público** e as imagens entram em `covers/`.

## URL canônica

```
https://raw.githubusercontent.com/marceloduartebr/dsb-covers/main/covers/<arquivo>.jpg
```

Esse valor vai para a propriedade `Image URL` no Notion quando a capa for gerada (`Image Source = generated`).

## Nome do arquivo

`YYYYMMDD-<slug>.jpg` — exemplo: `20260828-kaspersky-educacao.jpg`.

## Fluxo

1. Curadoria gera a capa (`generate_image`).
2. Commit em `covers/` neste repo (`github___create_or_update_file` ou `github___push_files`).
3. Notion recebe o raw URL em `Image URL` e a mesma imagem no body da página.
4. Publish: workbench faz GET no raw URL; se falhar, tenta o S3 assinado do fetch; se os dois falharem, publica só texto.

Não commitar PDF, HTML da fila nem texto de post.
