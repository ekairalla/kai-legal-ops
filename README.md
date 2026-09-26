# KAI Legal Ops

**Automação de controladoria jurídica com inteligência.**

Engenharia de automação e IA aplicada à operação jurídica: do cadastro do caso ao encerramento,
sobre o ERP que o escritório já usa.

Eduardo Kairalla · Engenheiro de Automação e IA Jurídica · Legal Ops & Legal Engineering
Bacharel em Direito (sem inscrição na OAB, não atuo como advogado).

---

## O que eu construo

| Frente | O que entrego |
|---|---|
| **Cadastro e entrada de casos** | Esteira que lê o caso novo da fonte (e-mail, planilha, portal), enriquece com dados processuais e cadastra no ERP por API, com regra de duplicidade e trilha de auditoria. |
| **Publicações e prazos** | Classificação de publicações e intimações por tipo e urgência, com IA e avaliador independente, gerando tarefa com prazo calculado em dias úteis. |
| **Acompanhamento processual** | Monitoramento de movimentação, captura de documentos e vínculo de peças ao caso, com fila, retentativa e limite de consumo de API. |
| **Encerramento** | Régua de encerramento por critério objetivo, com revisão humana obrigatória antes da baixa. |
| **Documentos e IA** | OCR de documento digitalizado, extração de campos, minuta assistida por IA com avaliador de qualidade e controle de custo por chamada. |
| **Dados e BI** | Espelho do ERP em banco relacional, modelagem dimensional e painéis de produtividade, prazo e carteira. |
| **Governança** | Registro de consumo por consulta, rateio de custo por área, gate de qualidade antes de qualquer escrita em produção. |

## Como eu trabalho

1. **Prova antes de ligar.** Toda automação roda primeiro em simulação, contra dado real e sem
   escrever, com relatório do que faria.
2. **Revisão humana onde há risco jurídico.** IA sugere, pessoa decide. Prazo, baixa e peça nunca
   são automáticos sem conferência.
3. **O cliente fica dono.** Construído no ambiente do cliente, com documentação e capacitação da
   equipe. Sem dependência de fornecedor.
4. **Ordem de grandeza, não promessa.** Meta escrita em número antes de começar, medida depois.

## Stack

`Python` · `PowerShell 7` · `Azure (SQL, Functions, Automation, Document Intelligence)` ·
`Microsoft Graph` · `Power Automate` · `Power BI (PBIP/TMDL)` · `SQL Server` ·
`APIs de ERP jurídico` · `modelos de IA de mercado via API` · `automação de interface quando não há API`

ERPs jurídicos com que trabalho por API ou por interface: Legal One, eLaw, Projuris, Espaider,
soluções jurídicas TOTVS, Legal Desk e Legal Manager.

## Resultados, em ordem de grandeza

Números de projetos reais, sem identificar cliente, carteira ou pessoa:

- Classificação de publicações na casa de **dezenas de milhares de itens por mês**, com gate de
  retenção para o que precisa de olho humano.
- Esteira de cadastro processando **carteiras de milhares de processos** em lote, com auditoria
  diária e rollback documentado.
- Redução de rotina manual de controladoria medida em **centenas de horas por mês**.
- Pipeline de IA com **custo por documento medido e rateado** por área.

## Leia mais

- [Arquitetura de referência](docs/arquitetura-de-referencia.md): entrada, cadastro, prazo e
  encerramento, e as camadas que atravessam as quatro etapas.
- [Método de trabalho](docs/metodo.md): as seis fases, do diagnóstico à entrega.
- Casos, sem identificar cliente:
  [01 · esteira de cadastro](docs/casos/01-esteira-de-cadastro.md) ·
  [02 · classificação de publicações](docs/casos/02-classificacao-de-publicacoes.md) ·
  [03 · IA com avaliador independente](docs/casos/03-ia-com-avaliador-independente.md)

## Código

- [**kai-toolkit**](https://github.com/ekairalla/kai-toolkit): cliente de API de ERP jurídico que
  renova token no meio da execução, respeita limite de requisições e não repete escrita incerta;
  registro de consumo com custo por área; e IA com avaliador independente e gabarito. Python puro,
  com testes contra uma API falsa que reproduz os defeitos reais.

## Contato

kairalla@live.com · [LinkedIn](https://www.linkedin.com/in/eduardo-kairalla) ·
[Currículo em português](https://drive.google.com/file/d/1Kma6baIZJPwM5yG3otDx0Pn4FVEC_pMr/view?usp=drive_link) ·
[CV in English](https://drive.google.com/file/d/1vmfyot7hNUQzGwz_LoHqwiGEkkv8Wdby/view?usp=drive_link)

---

### Sobre este repositório

Portfólio técnico. Não contém código, dado, credencial, nome de cliente nem material de empregador.
As regras do que pode e do que não pode ser publicado estão em
[docs/POLITICA_DE_PUBLICACAO.md](docs/POLITICA_DE_PUBLICACAO.md), e todo commit passa pelo gate
`ferramentas/checa_sigilo.py`.
