# Ideias para depois

Funcionalidades combinadas, mas guardadas para outro momento. Quando for implementar, montar uma versão de teste para validação antes de publicar.

## Notificações de revisão (pedida em 03/11/2026)

Avisar quem está logado quando uma revisão chega na data ou atrasa, mesmo com o dash fechado.

**Regra combinada**
- Um aviso por dia, com resumo, para não virar spam:
  - "Hoje você tem 3 revisões", no dia da data prevista;
  - "2 revisões atrasadas", a partir do dia seguinte, enquanto não forem concluídas (passou a data, avisa do atraso).
- Tocar na notificação abre o dash na aba Revisões.
- O "Próxima revisão" do Caderno de erros já gera uma revisão automaticamente, então entra no mesmo aviso.
- Sininho no topo do dash com a lista de atrasadas, de hoje e de amanhã (funciona mesmo sem notificação no celular).

**Pendente de decisão**
- Horário do aviso diário: sugestão de 8h (Brasília).
- Aviso na véspera (ex.: 20h, "Amanhã você tem 2 revisões"): sugestão de não fazer.

**Como fazer**
- Notificações push (Web Push) com service worker no dash e botão "Ativar notificações" em cada aparelho.
- iPhone: só pelo app da tela inicial e com iOS 16.4 ou mais novo (regra da Apple). Android e computador: direto pelo navegador.
- Supabase: tabela com as inscrições dos aparelhos (RLS por dono), função (Edge Function) que monta o resumo de cada pessoa e envia os avisos, e agendamento diário com as extensões pg_cron e pg_net (disponíveis no projeto, ainda não instaladas).
- A chave privada do envio (VAPID) fica guardada como segredo da função no Supabase, nunca no código.

## Pomodoro no timer (pedido em 29/10/2026)

Modo Pomodoro no timer das Horas líquidas: ciclos de 25 min de estudo e 5 min de pausa, com aviso sonoro no fim de cada ciclo. As pausas do ciclo entram como pausa do bloco.
