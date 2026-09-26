# Politica de publicacao, KAI Legal Ops

Regra de ouro: o repositorio pessoal guarda **o que eu sei fazer**, nunca **o que eu fiz para um
cliente ou para um empregador**.

## 1. Nunca entra, em repositorio nenhum, nem privado

- Nome de cliente, de parte, de processo, de pasta, de advogado ou de colega.
- Numero de processo (CNJ), CPF, CNPJ, valor de causa, nome de operadora de saude.
- ID interno de sistema: id de cliente, de custom field, de tipo de documento, de fluxo, de lista,
  de site, de tenant, de assinatura, de recurso Azure.
- Credencial de qualquer tipo: chave de API, token, senha, string de conexao, certificado.
- Endpoint privado, nome de servidor, nome de VM, IP interno, caminho de rede.
- Codigo escrito no horario e nos sistemas do empregador, mesmo "limpo". Isso e obra do empregador,
  nao minha, e publicar sem autorizacao por escrito e problema contratual, nao so de sigilo.
- Nome de parceiro ou fornecedor associado a um caso concreto.

## 2. Pode entrar, em repositorio PRIVADO

- Codigo escrito por mim, do zero, fora do trabalho, para a KAI Legal Ops.
- Reescrita limpa (clean room) de um padrao tecnico: eu reescrevo do zero, com dado ficticio,
  descrevendo a tecnica e nao a implantacao do cliente.
- Material comercial da KAI: proposta modelo, brand book, portfolio, cartao.

## 3. Pode entrar, em repositorio PUBLICO

- Portfolio em texto: capacidades, arquitetura de referencia, metodo de trabalho.
- Resultado em ordem de grandeza, sem identificar cliente nem carteira. Exemplo correto:
  "pipeline de classificacao de publicacoes processando dezenas de milhares de itens por mes".
  Exemplo errado: "classifiquei 4.465 publicacoes da carteira X".
- Biblioteca generica que eu escrevi do zero e que funciona com dado ficticio.
- Conteudo educativo: como a API de um ERP juridico costuma se comportar, sem credencial, sem
  endpoint privado e sem id real.

## 4. Antes de cada commit

O hook `pre-commit` roda `ferramentas/checa_sigilo.py`, que barra o commit quando encontra termo
proibido, padrao de credencial, CNJ, CPF, CNPJ, e-mail corporativo ou caminho local.
A lista de termos proibidos fica FORA do repositorio, apontada por `git config --global kai.termos`
(ou pela variavel `KAI_TERMOS`). Sem a lista, o gate barra o commit: falha fechado.
A lista tem nome de cliente: ela mesma nunca pode ser versionada.

## 5. Se algo escapar

Segredo que foi para o GitHub e considerado vazado, mesmo apos apagar o commit. A ordem e:
rotacionar a credencial primeiro, reescrever o historico depois.
