# ETFsAnalysis
Neste projeto, analisei os **retornos e riscos** de quatro ETFs negociados na **Bolsa Brasileira**: **BOVA11, IVVB11, MATB11 e SMAL11**.  

Os principais objetivos da análise são:  
✅ **Compreender a performance** desses ativos antes, durante e após a pandemia da COVID-19.  
✅ **Avaliar a rentabilidade e os riscos** associados a cada um deles.  

A análise foi conduzida em **Python**, utilizando bibliotecas amplamente usadas em ciência de dados:  
📌 **Pandas** – manipulação e tratamento dos dados  
📌 **NumPy** – operações matemáticas  
📌 **Matplotlib & Seaborn** – visualização e estilização de gráficos  

Os dados foram obtidos através do **yfinance**, uma biblioteca que acessa a API do **Yahoo Finance**, permitindo a coleta de dados históricos de ações e ETFs de forma automatizada.  

# O que são ETFs?
Antes de entender os ETFs, precisamos compreender o conceito de índices. Índices são métricas que representam um grupo específico de ações ou ativos listados em uma bolsa de valores.
Os ETFs (Exchange Traded Funds) são fundos de investimento que replicam esses índices, permitindo que investidores diversifiquem sua carteira de forma prática.

## BOVA11
📌 Replica o Ibovespa, o principal índice da bolsa brasileira. O Ibovespa é composto pelas ações com maior volume de negociação nos últimos meses, sendo um dos principais termômetros do mercado.

## IVVB11
📌 Replica o S&P 500 em reais, índice que reúne as 500 maiores empresas da bolsa americana. É uma forma acessível de investir no exterior sem precisar abrir conta em corretoras internacionais.

## MATB11
📌 Replica o IMAT, índice de materiais básicos. Empresas desse setor foram diretamente impactadas pela pandemia, e ao longo da análise veremos como isso afetou sua performance.

## SMAL11
📌 Replica o SMLL, índice de Small Caps, que reúne empresas de menor capitalização na bolsa.
Devido à natureza das empresas que o compõem, esse índice apresenta alta volatilidade, mas também boas oportunidades de crescimento inesperado.
📈 Exemplo: A Magazine Luiza (MGLU3) fazia parte do índice de Small Caps até 2016, quando teve um crescimento explosivo. Com sua valorização, passou a compor o Ibovespa em 2019. (a maioria das Small Caps não alcança esse nível de valorização)

# Rentabilidade
### Rentabilidade acumulada
![rentabilidade_acumulada](https://github.com/user-attachments/assets/e83f79f0-b61d-4448-8ba7-c6f03b3561a4)


### Distribuição da rentabilidade acumulada
![rentabilidade_boxplot](https://github.com/user-attachments/assets/a1688cb7-a074-434d-b255-3ac1ddc47107)


A rentabilidade acumulada mede o desempenho total de um ativo ao longo do tempo, considerando ganhos e perdas sob o efeito do compounding (juros sobre juros).
De 2019 a 2024, o IVVB11 teve uma performance muito superior, o que é esperado, dado que ele replica o S&P 500 – um índice composto pelas 500 maiores empresas americanas. A força da economia dos EUA e a estabilidade das empresas do S&P 500 fazem com que a comparação direta com ETFs brasileiros seja desigual.
O BOVA11 e o MATB11 apresentam medianas de rentabilidade acumulada próximas, mas com certa vantagem para o BOVA11, que alcança valores gerais mais altos, embora com maior volatilidade.
Já o SMAL11 teve a pior performance do grupo, com mediana negativa e alta volatilidade. Esse comportamento é esperado, considerando a natureza das empresas de menor capitalização que compõem o índice.

# Desvio padrão como indicador de risco
Desvio padrão como indicador de risco
![desvio padrão (2)](https://github.com/user-attachments/assets/c7201736-4c7f-49b3-b859-7e833c547592)
![rentabilidade_risco](https://github.com/user-attachments/assets/eee69903-464d-4068-9de5-a9f27823b273)


O desvio padrão mede o quanto os retornos de um ativo se afastam da sua média. Quanto maior o desvio padrão, maior a volatilidade, razão pela qual ele é frequentemente utilizado como um indicador de risco.

Os resultados confirmam a relação esperada entre risco e retorno:
SMAL11 apresenta o maior risco, com 30,1% de desvio padrão.
MATB11 vem logo atrás, com 29,17%.
BOVA11 registra 24,98%, indicando um nível de risco mais moderado.
IVVB11 é o mais estável, com 21,32%, bem próximo do BOVA11. Isso sugere que, apesar dos retornos superiores do IVVB11, seu risco não é tão diferente do BOVA11.

# Sharpe Ratio: Retorno ajustado ao risco 

O **Sharpe Ratio** mede a relação entre **rentabilidade e volatilidade**, indicando se os retornos de um ativo compensam o risco assumido. Quanto maior o valor, melhor o retorno ajustado ao risco.  

### **Sharpe Ratio Anualizado**  
| ETF       | Sharpe Ratio |
|-----------|-------------|
| **BOVA11**  | 0.32        |
| **IVVB11**  | 1.23        |
| **SMAL11**  | 0.13        |
| **MATB11**  | 0.46        |

O **IVVB11** apresenta o melhor retorno ajustado ao risco, com folga, refletindo a solidez das empresas do S&P 500. Já o **SMAL11**, além de ter apresentado baixa rentabilidade, também apresenta um Sharpe Ratio muito baixo, indicando que os retornos não compensaram o risco assumido.  

# Sortino Ratio: Risco de perdas  

O **Sortino Ratio** é uma variação do Sharpe Ratio, mas aqui o foco está **nas perdas**. Ele mede o quanto a rentabilidade compensa o risco de quedas, sem penalizar oscilações positivas.  

### **Sortino Ratio Anualizado**  
| ETF       | Sortino Ratio |
|-----------|--------------|
| **BOVA11**  | 0.0247       |
| **IVVB11**  | 0.1185       |
| **SMAL11**  | 0.0104       |
| **MATB11**  | 0.0380       |

Assim como no **Sharpe Ratio**, o **IVVB11** se destaca, indicando que suas perdas foram bem menores em relação aos retornos. Já o **SMAL11** apresenta o menor Sortino Ratio, confirmando que seus retornos não foram suficientes para compensar as perdas.  

# Conclusão
IVVB11 se mostrou o ativo mais estável e com os melhores valores de rentabilidade dentre os presentes na análise.
MATB apresenta a segunda maior volatilidade, abaixo apenas do SMAL11, mas apresenta valores de Sharpe e Sortino acima dos performados pelo BOVA11, portanto, ainda que a volatilidade associada a ele seja maior, MATB11 paga melhor frente ao risco e perdas em comparação com o BOVA11.
O SMAL11 apresentou a maior volatilidade do grupo, além dos menores valores de Sharpe e Sortino, caracterizando-o como o ativo de maior risco entre os analisados. Porém, pela natureza dos ativos que o compõem, é também o que apresenta maiores chances de crescimento, exigindo do investidor um horizonte de longo prazo e mais tolerância ao risco.
A escolha entre esses ETFs depende do perfil do investidor. Enquanto IVVB11 se mostrou uma opção mais segura e rentável no período analisado, BOVA11 e MATB11 apresentaram um equilíbrio entre risco e retorno. Já SMAL11 exige um horizonte de longo prazo e maior tolerância ao risco.

**Essa análise é para fins educacionais e informativos apenas, e não deve ser considerada como sugestão de investimento.**
