# Método de trabalho

Seis fases, sempre na mesma ordem. Nenhuma automação chega à produção sem passar pelas quatro
primeiras, e nenhuma fica sem dono depois da última.

| Fase | Pergunta que responde | Entregável |
|---|---|---|
| 1. Diagnóstico | Onde a equipe perde tempo, e quanto? | Mapa da rotina com volume e horas por etapa |
| 2. Regra escrita | O que exatamente a automação decide? | Documento de regra revisado pela coordenação |
| 3. Modo sombra | A automação acerta o que a equipe faz hoje? | Relatório lado a lado: manual x automação |
| 4. Piloto com aprovação | Funciona gravando de verdade, com uma pessoa aprovando? | Execução real em escopo pequeno, com cartão de aprovação |
| 5. Produção | Aguenta o volume inteiro sem ninguém olhando? | Rotina agendada na nuvem, com alerta e auditoria diária |
| 6. Entrega | A equipe consegue operar sem mim? | Manual, capacitação e painel de acompanhamento |

## 1. Diagnóstico: medir antes de prometer

- Acompanhar a rotina real, não a descrita. O que a equipe diz que faz e o que faz raramente batem.
- Contar volume por dia e por fonte, e cronometrar amostras de cada etapa manual.
- Escrever a meta em número antes de começar: "reduzir de X para Y horas por semana na etapa Z".
  Sem meta escrita, não há como dizer depois se deu certo.

## 2. Regra escrita: a automação não inventa critério

- Toda decisão vira regra explícita: quando cadastrar, quando reter, quem é o responsável, qual o
  prazo. Caso de fronteira também: o que fazer quando o dado falta.
- A coordenação revisa e assina a regra. Regra ambígua volta para a mesa, não vai para o código.
- **O escopo é o que foi pedido.** "Todos da base" são os itens do arquivo recebido, não a carteira
  inteira do cliente no ERP. Ampliar escopo por conta própria custa dinheiro e confiança.

## 3. Modo sombra: rodar ao lado, sem gravar

- A automação roda contra dado real e registra o que **faria**, sem escrever nada.
- O resultado é comparado com o que a equipe fez de fato no mesmo período.
- **Amostra grande.** Uma amostra pequena responde só sobre ela mesma: um teste com duas dezenas de
  itens pode dizer "inócuo" e um com meia centena revelar dano em um a cada cinco. A amostra precisa
  cobrir as variações da carteira, e a deduplicação é por entidade, não por linha.
- **Conferidor independente.** Quem confere não pode repetir o raciocínio de quem fez. Um conferidor
  que erra igual ao código aprova o erro.

## 4. Piloto com aprovação: gravar pouco, com uma pessoa no meio

- Escopo pequeno e conhecido (uma equipe, um tipo de caso).
- Antes de cada lote, um cartão com a lista e um botão por decisão. A automação espera o clique;
  aviso para o grupo só depois da aprovação.
- Em ambiente de teste do ERP quando existe; em produção, só com processos de teste identificados.
- Rollback escrito e ensaiado antes do primeiro lote.

## 5. Produção: sozinha, vigiada e barata

- Rotina agendada na nuvem, nunca no notebook de alguém.
- Escrita em janela controlada, fora do horário de pico.
- Alerta de falha, auditoria diária e relatório de consumo e custo.
- **Tempo e custo medidos antes de ligar:** custo unitário vezes volume, e tempo de execução contra
  a validade do token. Execução que dura mais que o token precisa renovar no meio.
- Execução que termina com erro não significa que nada foi gravado: o sistema pode ter gravado e
  respondido falha. Conferir no destino antes de rodar de novo.

## 6. Entrega: o cliente fica dono

- Manual de operação, com o que fazer em cada alerta.
- Capacitação da equipe que vai operar e da coordenação que vai aprovar.
- Painel de acompanhamento com os números da meta escrita na fase 1.
- Comunicação à equipe **uma vez**, quando tudo estiver pronto. Três avisos numa noite viram ruído.

## O que eu não faço

- Não ligo automação sem modo sombra, mesmo quando "é simples".
- Não automatizo decisão irreversível (baixa, exclusão, envio ao cliente) sem aprovação humana.
- Não construo fora do ambiente do cliente nem crio dependência de fornecedor.
- Não prometo número que não medi.

Veja também: [arquitetura de referência](arquitetura-de-referencia.md) e os casos em
[docs/casos](casos/).
