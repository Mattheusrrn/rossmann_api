# rossmann_api
# PA002_rossmann_sales_prediction
Os objetivos desse projeto de Ciência de Dados são:

- Realizar a Análise Exploratória de Dados (EDA) das vendas das lojas da Rossmann disponíveis no conjunto de dados;
- Fazer a previsão de vendas por loja para as próximas 06 semanas; e
- Tornar as previsões acessíveis para qualquer *stakeholder* através de um Bot no Telegram.

# 01. Problema de Negócio
A Rossmann é uma rede de farmácias com 3.000 lojas em 07 países da Europa. Durante uma reunião mensal para apresentação de resultados e acompanhamento de métricas, o CFO informou que as lojas serão reformadas e, para saber quanto destinar de orçamento para cada loja, ele gostaria da previsão de vendas de cada loja para as próximas 06 semanas. 

Como Cientista de Dados da companhia, fui encarregado de elaborar essa previsão de vendas, e informarei ao CFO a previsão de vendas de cada loja através de um Bot no Telegram. 

# 02. Premissas de Negócio
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

# 03. Etapas do Projeto
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

# 04. Hipóteses de Negócio
Entre as 11 hipóteses de negócio levantadas e analisadas, as 03 que considero principais foram: 
1. As lojas com competidores a mais tempo vendem menos.
2. As lojas que abrem no Natal vendem mais.
3. As lojas vendem mais no segundo semestre do ano.

# 05. *Machine Learning*
Para fazer a previsão de vendas, foi utilizado 05 algoritmos de Machine Learning: 
- *Average Model*
- *Linear Regression*
- *Linear Regression Regularized*
- *Random Forest Regressor*
- *XGBoost Regressor*

Após fazer o treinamento dos modelos sobre os dados de treino e ter feito o Cross-Validation, bem como analisar o erro através do MAE, MAPE e RMSE, optei por usar o XGBoost Regressor.

Depois de realizar o *hyperparemeter fine tunning*, os resultados de erro foram: 

|         Modelo          |     MAE    |    MAPE   |    RMSE    |
| :---------------------: | :--------: | :------:  | :--------: |
|    XGBoost Regressor    | 690.077731 | 0.10261   | 990.781052 |

# 06. Resultados Financeiros
O Modelo de Machine Learning adotado previu um cenário-base com uma receita bruta consolidada de € 277,532,192.00 para as próximas 06 semanas. No pior cenário se usou o MAE,mean absolute error,e chegou se em uma receita bruta consolidada de € 276,758,401.30, e no melhor cenário, € 278,306,002.42.

# 07. Bot no Telegram
Demonstração da interação com o Bot para verificar a previsão de vendas por loja:
![rossman_bot](https://user-images.githubusercontent.com/97055919/203369108-60f55b16-77ce-408a-9b86-45655121ee25.jpeg)

# 08. Conclusões
A partir dessa previsão e o deployment no Telegram,será possível que o CFO consulte o valor das vendas pelo celular onde quer que esteja, facilitando a definição do orçamento para a reforma de cada loja. 

Ainda, as hipóteses levantadas e validadas na Análise Exploratória de Dados também trazem informações importantes para a tomada de decisões e forma de condução de negócios.

# 09. Próximos Passos
Em um próximo ciclo do CRISP, o que pode ser melhorado: ;
- Realizar o preenchimento de valores faltantes de outra forma; 
- Testar outros algoritmos de *Machine Learning*;
- Utilizar outra estratégia para o *Hyperparemeter Fine Tunning* (ex.: *Bayesian Search*); e 
- Aprimorar os resultados no Bot no Telegram.

# Referências
- Conjunto de Dados: https://www.kaggle.com/competitions/rossmann-store-sales
- Descrição do Conjunto de Dados: https://www.kaggle.com/competitions/rossmann-store-sales/data
