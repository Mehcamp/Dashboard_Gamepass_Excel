# Dashboard de Vendas: Game Pass (Excel)

Dashboard em Excel que transforma uma base de assinaturas do Game Pass em indicadores e gráficos fáceis de ler. Feito como desafio da DIO.

Arquivo: `Dashboard_GamePass.xlsx`

## Dados utilizados

Base fornecida pela DIO (`base.xlsx`), com **295 assinaturas** de 2024 (de 01/01/2024 a 16/12/2024). Ela está na aba **Bases** do arquivo, formatada como tabela do Excel.

| Coluna | Descrição |
|---|---|
| Subscriber ID, Name | Identificação do assinante |
| Plan | Plano: Core, Standard ou Ultimate |
| Start Date | Data de início da assinatura |
| Auto Renewal | Se tem renovação automática (Yes/No) |
| Subscription Price | Preço do plano |
| Subscription Type | Tipo: Monthly, Quarterly ou Annual |
| EA Play Season Pass (+ Price) | Se comprou o complemento e quanto custou |
| Minecraft Season Pass (+ Price) | Se comprou o complemento e quanto custou |
| Coupon Value | Desconto aplicado |
| Total Value | Valor total da venda (preço do plano + complementos − cupom) |

A base não informa a moeda, então os valores aparecem com o símbolo `$` apenas como referência.

## Perguntas de negócio

O dashboard responde a seis perguntas (cada uma tem um bloco na aba **Calculos**):

1. Quantos assinantes e qual o faturamento total, o ticket médio, a taxa de renovação automática e o total de descontos?
2. Qual o faturamento de cada plano?
3. Qual o faturamento por tipo de assinatura (mensal, trimestral, anual)?
4. Quanto fatura quem tem renovação automática e quem não tem?
5. Como o faturamento evoluiu mês a mês?
6. Quanto venderam os complementos EA Play e Minecraft Season Pass?

## O que o dashboard mostra (com todos os filtros em "Todos")

- 295 assinantes e faturamento total de 7.633, com ticket médio de cerca de 25,87.
- O plano **Ultimate** responde por 5.388 do faturamento (cerca de 70%), apesar de ter quase o mesmo número de assinantes que Core e Standard.
- As assinaturas **mensais** somam 3.571 (cerca de 47%).
- A renovação automática é quase meio a meio: 148 assinantes com e 147 sem.
- O faturamento fica estável entre março e novembro (cerca de 780 por mês). Janeiro e fevereiro têm poucos registros na base, e dezembro é parcial porque a base termina em 16/12.
- O Minecraft Season Pass teve 194 compradores e 3.880 de faturamento; o EA Play teve 98 compradores e 2.940.

## Como o painel foi construído

- **Aba Bases:** dados em uma tabela do Excel, com intervalos nomeados para cada coluna usada (`base_plano`, `base_tipo`, `base_total` etc.).
- **Aba Calculos:** fórmulas `CONT.SES` e `SOMASES` que respondem às perguntas acima, mais `DATA`, `DATAM` e `ANO` para os meses.
- **Aba Dashboard:** cartões com os indicadores principais, cinco gráficos (colunas, rosca e linha) e uma tabela-resumo por plano.
- **Imagens:** logo do Xbox no cabeçalho e ícones do EA Play e do Minecraft na área de complementos, retirados da aba Assets do arquivo de apoio da DIO.
- **Filtros:** duas listas suspensas (plano e tipo de assinatura). Ao escolher uma opção, todos os indicadores e gráficos se atualizam. A opção "Todos" usa o curinga `*` nos critérios das fórmulas.

## Como reproduzir

1. Abra o Excel e cole a base na aba **Bases**, formatada como tabela.
2. Nomeie as colunas usadas (Fórmulas, Gerenciador de Nomes).
3. Na aba **Calculos**, crie um bloco de fórmulas `SOMASES` e `CONT.SES` para cada pergunta, usando os nomes.
4. Na aba **Dashboard**, crie as listas suspensas com Validação de Dados e ligue-as aos critérios em **Calculos**.
5. Insira os gráficos a partir das tabelas de **Calculos** e monte os cartões de indicadores com referências às células.

## O que fiz de diferente do exemplo da DIO

O exemplo usa tabelas dinâmicas e segmentações de dados. No meu painel, os cálculos são feitos com fórmulas e intervalos nomeados, e os filtros são listas suspensas. O layout, as perguntas de negócio (incluindo ticket médio, evolução mensal e taxa de renovação) e os gráficos também são diferentes.

## O que aprendi

> Neste projeto aprendi a transformar dados brutos em um painel visual no Excel. Organizei a base em uma **tabela** e criei **intervalos nomeados** para cada coluna, o que deixou as fórmulas mais fáceis de ler. Usei `SOMASES` e `CONT.SES` para responder às perguntas de negócio, como faturamento por plano, por tipo de assinatura e mês a mês, e usei **listas suspensas** como filtros que atualizam todo o painel ao mesmo tempo.

Também pratiquei a escolha do gráfico certo para cada pergunta (colunas para comparar planos, rosca para mostrar proporção e linha para acompanhar a evolução no tempo) e a organização do layout, com indicadores em destaque no topo e imagens para deixar o painel mais claro. Por fim, aprendi a documentar o projeto em um README e a compartilhá-lo no GitHub.
