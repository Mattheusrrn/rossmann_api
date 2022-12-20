# rossmann_api
# PA002_rossmann_sales_prediction
Os objetivos desse projeto de Ciência de Dados são:

- Realizar a Análise Exploratória de Dados (EDA) das vendas das lojas da Rossmann disponíveis no conjunto de dados;
- Fazer a previsão de vendas por loja para as próximas 06 semanas; e
- Tornar as previsões acessíveis para qualquer *stakeholder* através de um Bot no Telegram.

# 01. Problema de Negócio
A Rossmann é uma rede de farmácias com 3.000 lojas em 07 países da Europa. Durante uma reunião mensal para apresentação de resultados e acompanhamento de métricas, o CFO informou que as lojas serão reformadas e, para saber quanto destinar de orçamento para cada loja, ele gostaria da previsão de vendas de cada loja para as próximas 06 semanas. 

Como Cientista de Dados da companhia, fui encarregado de elaborar essa previsão de vendas, e informarei ao CFO a previsão de vendas de cada loja através de um Bot no Telegram. 

# 02. Resultados Financeiros
O Modelo de Machine Learning adotado previu um cenário-base com uma receita bruta consolidada de € 281.083.520,00 para as próximas 06 semanas. No pior cenário, a receita bruta consolidada será de € 280.098.063,00, e no melhor cenário, € 282.068.968,00, tendo como base o MAE (*Mean Absolute Error*) do modelo. 

# 03. Premissas de Negócio
- O conjunto de dados contém as vendas realizadas entre 01/01/2013 e 31/07/2015;
- As variáveis/atributos originais (e seus significados) do conjunto de dados são:

|    Atributos    |                         Significado                          |
| :-------------: | :----------------------------------------------------------: |
|     store       |id único para cada loja                            |
|      day_of_week|dia da semana (1 a 7)                                     |
|      date       |data                                      |
|    sales        |o volume financeiro de vendas no dia                                             |
|    customers    |o número de clientes no dia                                                      |
|   open          |indicador se a loja estava aberta ou não (0 = fechada, 1 = aberta)                    |
|    promo        |indica se a loja estava com alguma promoção no dia               |
|    state_holiday|indica se era feriado estadual/nacional no dia (a = feriado público, b = Páscoa, c = Natal, 0 = nenhum)                  |
|   school_holiday|indica se a loja no dia foi afetada pelo fechamento das escolas públicas               |
|      store_type |indica o tipo da loja (4 tipos: a, b, c, d) |
|    assortment   |descreve o nível de mix de produtos (a = básico, b = extra, c = extenso) |
| competition_distance |distância em metros para a loja do concorrente mais próxima |
|  competition_open_since_month     |mês que a loja do concorrente mais próxima foi aberta |
|  competition_open_since_year  |ano que a loja do concorrente mais próxima foi aberta| 
|    promo2       |promoção contínua e consecutiva para algumas lojas (0 = loja não participou, 1 = loja participou)                    |
|  promo2_since_week   | indica a semana do ano que a loja começou a participar da promo2                     |
|     promo2_since_year     |indica o ano que a loja começou a participar da promo2 (complementar à promo2_since_week)    |
|       promo_interval       |descreve os intervalos consecutivos que a promo2 começou, indicando os meses que a promoção começou novamente (Ex.: "Feb,May,Aug,Nov" significa que cada intervalo começou em Fevereiro, Maio, Agosto e Novembro em determinado ano para determinada loja)                           |

# 04. Etapas do Projeto
Para conduzir o projeto, utilizei as etapas do CRISP:
1. Entender o problema de negócio apresentado pelo CFO; 
2. Entender o modelo de negócio da Rossmann; 
3. Coletar os dados; 
4. Limpeza e filtragem dos dados - análise descritiva dos dados; 
5. Análise Exploratória de Dados - levantamento e validação de hipóteses; 
6. Preparação e modelagem dos dados - seleção de variáveis (*feature selection*)
7. *Machine Learning*; 
8. Avaliação dos modelos de *Machine Learning*; e
9. *Deploy* do Modelo escolhido. 
