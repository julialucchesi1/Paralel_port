# Paralel_port 

Neste trabalho serão feitas 1000 possíveis carteiras que distribuam pesos a 25 das 20 ações de empresas do DowJones. Para isso primeiro foram importadas as bibliotecas que serão usadas e explicadas a seguir.

Para que os retornos de cada uma das 30 ações do período entre 01/08/2024-31/12/2024, segundo semestre de 2024, com o a biblioteca yfinance esses dados foram retirados via yahoo finance diretamente para o código via essa API retirando a primeira linha onde estão os nomes.

Com os dados coletados eles foram passados a um excel que ficaria salvo no computador, assim não seria necessário refazer a importação a cada simulação nova.

Para gerar de forma aleatória os pesos de cada ação em cada uma das carteiras foi feita uma função que gera números aleatórios, mas que restringidos pela função while não podem nenhum deles ser maior que 0.2 e todas as somas das ações das carteiras precisam ser 1.

Com as funções mean e cov foram calculados os retornos esperados de cada carteira e seus respectivos riscos, ao após multiplicar por 256 termos esses valores anularizados.

Dado que a melhor carteira é aquela que entrega o menor risco para o maior retorno foi calculado o indice de sharp sem contar com a taxa livre de risco, ja que ela é despresível neste comparação entre carteiras. 

Armazenados todos esses resultados finalmente é possível criar os processos para que eles sejam realizados em seguida de forma a calcular as taxas para as demais 1000 carteiras de maneira mais rapida do que se não estivesse usando o multiprocessamento.

Para finalizar esses resultados foram direcionados a um data frame que foi salvo em um excel.

