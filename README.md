# Central de Estudos

Dashboard de estudos para concurso público (Prefeitura de Curitiba): cronograma importado da planilha, semanas, caderno de erros, revisões (lista e Kanban), desempenho, horas líquidas, biblioteca, mapas mentais, fechamentos semanais e lembretes.

Publicado em https://central-de-estudosnacha.vercel.app/

## Como funciona

- Tudo fica em um único arquivo, `index.html` (HTML, CSS e JavaScript, sem etapa de build).
- Os dados ficam no **Supabase**, com login: a tabela `docs` guarda os registros e o bucket privado `mapas` guarda as imagens dos mapas mentais. Cada login só acessa os próprios dados (RLS).
- A chave que aparece no código é a chave pública (publishable) do Supabase; quem protege os dados é o login.
- Sem conexão com a nuvem, o dash funciona em modo local (só no navegador) e oferece enviar esses registros para a nuvem depois.

## Publicação

O projeto no Vercel está ligado a este repositório: cada alteração na branch `main` é publicada automaticamente.
