## Trabalho Data Science 2ESPX

### Integrantes:

Gabriel Marquez Trevisan RM99227
Guilherme Silva dos Santos RM551168

### Descrição:
A partir deste trabalho, iremos analisar os bancos de dados da Netflix, IMDb e Rotten Tomatoes para ter mais informações sobre filmes de terror, como quais gêneros geralmente estão relacionados a eles e quais notas os filmes geralmente recebem.

### Pergunta 1: Quais os gêneros que estão mais relacionados com "Horror"?

#### Descrição
A análise foi conduzida para identificar quais gêneros de filmes estão mais frequentemente associados ao gênero "Horror" nas plataformas Netflix, Rotten Tomatoes e IMDb. A combinação de dados dessas três plataformas permitiu uma análise mais ampla e detalhada dos padrões de gêneros nos filmes de horror.

#### Processo de Análise:
1. **Combinação de Gêneros de Múltiplas Fontes:**
   Usamos dados de três fontes: Netflix (`genres_netflix`), Rotten Tomatoes (`genres_rotten`), e IMDb (`genres`).
   Para cada filme de "Horror" presente nas três plataformas, combinamos os gêneros listados em uma nova coluna `all_genres`. Essa coluna contém uma lista de todos os gêneros associados ao filme, além de "Horror".

2. **Remoção do Gênero "Horror":**
   Como o objetivo é identificar gêneros que frequentemente aparecem junto com "Horror", o próprio gênero "Horror" foi removido de cada lista de gêneros.

3. **Contagem de Ocorrências de Gêneros Associados:**
   Usamos a função `Counter` da biblioteca Python `collections` para contar a frequência de todos os gêneros (exceto "Horror") que apareceram nos filmes.

4. **Visualização dos Resultados:**
   Os resultados foram visualizados utilizando um gráfico de barras que destaca os gêneros mais correlacionados com "Horror". O gráfico apresenta os gêneros e suas contagens em ordem decrescente.

#### Resultados da Análise:
<img src='https://github.com/user-attachments/assets/ef91ba6f-18d2-4669-88c0-34ceeeb01322'/>

A partir da análise, identificamos os gêneros que estão mais frequentemente associados ao "Horror":

- **Mystery & Suspense:** O gênero "Mystery & Suspense" é o mais relacionado ao "Horror", aparecendo em 34 casos. Filmes de terror frequentemente utilizam elementos de suspense e mistério para criar um ambiente de tensão e medo. Isso faz do "Mystery & Suspense" uma combinação natural com "Horror".

- **Drama:** O "Drama" é o segundo gênero mais comum associado ao "Horror", aparecendo em 24 casos. Filmes que combinam "Horror" e "Drama" geralmente exploram temas psicológicos, emocionais e relacionamentos humanos. Eles podem adicionar profundidade às histórias de horror ao focar no impacto emocional dos eventos sobrenaturais ou aterrorizantes.

- **Science Fiction & Fantasy:** O gênero "Science Fiction & Fantasy" aparece frequentemente em conjunto com "Horror" (21 ocorrências). Filmes que combinam "Horror" com "Sci-Fi & Fantasy" tendem a explorar temas como invasões alienígenas, experimentos científicos que deram errado, ou mundos distópicos, adicionando uma camada extra de mistério e medo.

- **Action & Adventure:** Embora menos frequente, o gênero "Action & Adventure" também apareceu frequentemente associado ao "Horror" (18 ocorrências). Filmes de "Horror" que também pertencem ao gênero "Action & Adventure" geralmente envolvem perseguições, batalhas ou cenários de sobrevivência, proporcionando elementos de adrenalina e ação.

- **Comédia:** Surpreendentemente, o gênero "Comedy" também apareceu como um dos gêneros correlacionados ao "Horror" (12 ocorrências). Filmes que combinam "Horror" e "Comedy" geralmente caem na categoria de "Horror Comédia", onde o terror é equilibrado com elementos cômicos para aliviar a tensão.

- **Art House & International:** Este gênero apareceu em 11 ocorrências, sugerindo que filmes de "Horror" também podem explorar um cinema mais artístico e internacional, com abordagens experimentais e estilos únicos.

- **Classics e Romance:** Os gêneros "Classics" e "Romance" aparecem menos frequentemente, indicando que não são combinações comuns com "Horror".

#### Conclusão Geral dos Resultados:
A análise revela que o "Horror" é um gênero versátil que pode se misturar com vários outros gêneros para criar narrativas únicas e atraentes. O "Mystery & Suspense" é o mais comum, mas há também uma combinação notável com "Drama", "Science Fiction & Fantasy", e até "Comedy".

### *Resposta para a Pergunta 2 e 3: Quais filmes de terror têm as maiores e menores notas?*

Para identificar os filmes de terror com as maiores e menores notas, usamos os dados combinados de avaliações de críticos do Rotten Tomatoes para filmes classificados como "Horror". Os resultados são baseados nas notas dos críticos, que fornecem uma visão clara dos filmes de terror mais e menos bem recebidos ao longo dos anos.

### *Processo de Análise:*

1. *Limpeza dos Dados:*
   - Convertendo os valores da coluna RottenTomatoes_Critic_Rating para um formato numérico, eliminando qualquer dado não numérico que possa estar presente.
   - Removendo entradas que contenham valores ausentes (NaN) na coluna RottenTomatoes_Critic_Rating para garantir que os cálculos estejam corretos.

2. *Ordenação dos Filmes por Avaliações:*
   - Para encontrar os filmes de terror com as *maiores notas*, classificamos o DataFrame ratings_clean_df em ordem decrescente com base na RottenTomatoes_Critic_Rating.
   - Para encontrar os filmes de terror com as *menores notas*, classificamos o DataFrame ratings_clean_df em ordem crescente com base na RottenTomatoes_Critic_Rating.

### *Resultados da Análise:*

#### Pergunta 2: *Filmes de Terror com as Notas Mais Altas (Rotten Tomatoes - Críticos):*

Os filmes a seguir foram altamente avaliados pelos críticos no Rotten Tomatoes, recebendo notas muito altas. Estes são os 10 filmes de terror mais bem avaliados:

<img src='https://github.com/user-attachments/assets/6bd9a659-6545-40dd-b474-a68b523e00e8'>

Esses filmes são exemplos de obras que se destacaram pela qualidade na direção, roteiro, interpretação ou inovação no gênero de terror, garantindo uma excelente recepção crítica.

####  Pergunta 3: *Filmes de Terror com as Notas Mais Baixas (Rotten Tomatoes - Críticos):*

Os seguintes filmes de terror receberam as notas mais baixas dos críticos, indicando uma recepção crítica geralmente negativa. Estes são os 10 filmes de terror com as piores avaliações:

<img src='https://github.com/user-attachments/assets/fbf61f34-0a44-4421-9c91-cf653b874a77'/>

Esses filmes foram mal recebidos pelos críticos, possivelmente devido a problemas como roteiro fraco, falta de inovação, direção ineficaz, ou más atuações.

### *Conclusão Geral dos resultados:*

A análise dos filmes de terror com as maiores e menores notas mostra uma diversidade na qualidade e recepção de filmes do gênero "Horror". Os filmes com maiores notas são frequentemente inovadores, bem dirigidos e apresentam performances fortes, enquanto os filmes com menores notas tendem a ser criticados por problemas em múltiplas áreas de produção.

Essa análise pode ser útil para produtores e diretores que buscam entender o que faz um filme de terror ser bem recebido e quais armadilhas evitar para não cair em más críticas.

### * Pergunta 4: Qual a nota média entre a audiência e os críticos entre os gêneros mais relacionados a terror?*

Para calcular a média das notas dos críticos e da audiência para os subgêneros mais relacionados ao "Horror", utilizamos os dados combinados de Netflix, Rotten Tomatoes e IMDb. A análise foi realizada para os subgêneros que mais frequentemente aparecem associados ao "Horror", como "Thriller", "Mystery & Suspense", "Drama", "Science Fiction & Fantasy", e "Action & Adventure".

### *Processo de Análise:*

1. *Identificação dos Subgêneros Relacionados ao Horror:*
   - Primeiro, identificamos todos os subgêneros presentes no DataFrame horror_df que contém informações combinadas de filmes de terror das plataformas Netflix, Rotten Tomatoes e IMDb.
   - Os subgêneros mais relacionados ao "Horror" foram: "Thriller", "Mystery & Suspense", "Drama", "Science Fiction & Fantasy", e "Action & Adventure".

2. *Filtragem dos Dados por Subgênero:*
   - Para cada subgênero, filtramos os filmes que pertencem a ele utilizando a coluna all_genres do DataFrame horror_df.
   - Para evitar processar o mesmo título mais de uma vez, foi mantido um conjunto de títulos processados.

3. *Cálculo das Notas Médias:*
   - Para cada subgênero, as notas dos críticos (Rotten Tomatoes) e da audiência (Rotten Tomatoes) foram convertidas para valores numéricos.
   - Removemos quaisquer valores ausentes (NaNs) para garantir cálculos precisos.
   - Calculamos a média das notas dos críticos e da audiência para cada subgênero.



#### *Análise dos Resultados:*

1. *Mystery & Suspense:*
   - *Nota Média dos Críticos:* 50.23
   - *Nota Média da Audiência:* 47.86
   - Este subgênero, fortemente associado ao "Horror", tem uma média de avaliação que indica recepção mista de críticos e audiência. Filmes que combinam "Horror" com "Mystery & Suspense" podem proporcionar uma boa dose de tensão e mistério, mas também podem ser inconsistentes em qualidade.

2. *Drama:*
   - *Nota Média dos Críticos:* 50.88
   - *Nota Média da Audiência:* 44.50
   - Filmes de "Horror" com elementos de "Drama" apresentam uma ligeira preferência dos críticos sobre a audiência. Esses filmes muitas vezes exploram temas emocionais e psicológicos que podem ser apreciados pela crítica, mas podem não ressoar tão bem com o público.

3. *Science Fiction & Fantasy:*
   - *Nota Média dos Críticos:* 51.67
   - *Nota Média da Audiência:* 50.17
   - A média de avaliações para filmes de "Horror" combinados com "Science Fiction & Fantasy" é relativamente equilibrada entre críticos e audiência, sugerindo que esses filmes tendem a ser mais universalmente apreciados ou criticados.

4. *Action & Adventure:*
   - *Nota Média dos Críticos:* 28.00
   - *Nota Média da Audiência:* 35.00
   - Filmes de "Horror" com "Action & Adventure" têm uma média de notas significativamente mais baixa, tanto dos críticos quanto da audiência. Isso pode indicar que a mistura desses gêneros pode resultar em produções que não atendem às expectativas de ambos os grupos.

### *Conclusão Geral:*

A análise das notas médias entre audiência e críticos para subgêneros relacionados ao "Horror" revela que alguns subgêneros, como "Science Fiction & Fantasy", têm uma recepção mais equilibrada entre críticos e público. Em contraste, "Action & Adventure" associado ao "Horror" tende a ter uma recepção mais fraca. Esses insights podem ser úteis para produtores e cineastas que desejam explorar combinações de gênero para atingir diferentes públicos-alvo.

### *Pergunta 5: Existe uma relação entre a nota da crítica dos usuários e dos críticos?*

A análise da relação entre as notas dos críticos e da audiência para filmes de terror nas plataformas Rotten Tomatoes e IMDb foi realizada utilizando regressão linear. A regressão linear ajuda a entender a correlação entre as variáveis e identificar se existe uma relação significativa entre elas.

### *Análise de Regressão:*

1. *Comparação entre Avaliações dos Críticos (Rotten Tomatoes) e IMDb:*

   <img src='https://github.com/user-attachments/assets/fd7b2f20-a3d9-41f8-b998-078d4469e490'>

   - *Coeficiente (Slope):* 0.0211
   - *Intercepto:* 4.6673
   - *Coeficiente de Determinação (R²):* 0.4275

   A regressão linear entre as notas dos críticos do Rotten Tomatoes e as notas do IMDb mostra um coeficiente de determinação (R²) de 0.43. Isso indica uma correlação moderada entre as avaliações dos críticos no Rotten Tomatoes e as avaliações no IMDb. Embora exista uma relação, ela não é forte o suficiente para afirmar que as notas dos críticos determinam as notas do IMDb. Existem outros fatores que influenciam as avaliações no IMDb, como preferências pessoais dos usuários, que podem não estar alinhadas com as avaliações dos críticos.

3. *Comparação entre Avaliações da Audiência (Rotten Tomatoes) e IMDb:*

<img src='https://github.com/user-attachments/assets/a06b85f0-e7bb-431c-b59c-e8afb75b6ed7'/>

   - *Coeficiente (Slope):* 0.0345
   - *Intercepto:* 3.5789
   - *Coeficiente de Determinação (R²):* 0.6734

   A análise da regressão linear entre as avaliações da audiência no Rotten Tomatoes e as notas do IMDb mostra um coeficiente de determinação (R²) de 0.67. Isso indica uma correlação mais forte entre as avaliações da audiência no Rotten Tomatoes e as avaliações no IMDb. Isso sugere que a opinião do público tende a ser mais consistente entre as duas plataformas, o que é esperado, pois ambas refletem a percepção geral dos espectadores.

3. *Comparação entre Avaliações dos Críticos e da Audiência (Rotten Tomatoes):*

   <img src='https://github.com/user-attachments/assets/f7d4443e-4bb4-4d2d-81fb-bb50e0463c81'/>

   - *Coeficiente (Slope):* 0.4207
   - *Intercepto:* 28.5467
   - *Coeficiente de Determinação (R²):* 0.3261

   A análise de regressão entre as notas dos críticos e da audiência no Rotten Tomatoes mostra um coeficiente de determinação (R²) de 0.33, indicando uma correlação fraca a moderada. Isso significa que, embora haja alguma relação entre as notas dos críticos e da audiência, eles nem sempre concordam. Os críticos tendem a focar mais nos aspectos técnicos e artísticos de um filme, enquanto a audiência pode se concentrar em fatores como entretenimento e diversão.

### *Conclusão Geral:*

A análise de regressão linear mostra que há uma correlação moderada entre as avaliações dos críticos e da audiência. A relação é mais forte entre as avaliações da audiência no Rotten Tomatoes e as notas do IMDb, sugerindo que as opiniões do público são mais consistentes entre as duas plataformas. No entanto, a correlação entre as notas dos críticos e da audiência é mais fraca, indicando que os críticos e o público têm critérios diferentes para avaliar filmes de terror.

Essas informações são úteis para entender as dinâmicas entre diferentes grupos de avaliadores e como isso pode influenciar a percepção de filmes no mercado.

### *Resposta 6: Existe uma normalidade entre as notas dos usuários e dos críticos?*

Para determinar se as notas dos críticos e da audiência no Rotten Tomatoes seguem uma distribuição normal, aplicamos dois tipos de testes estatísticos: o *Teste de Shapiro-Wilk* para verificar a normalidade e o *Teste de Wilcoxon* para comparar as distribuições.

### *Análise de Normalidade:*

1. *Teste de Shapiro-Wilk para Notas dos Críticos (Rotten Tomatoes):*

   - *Valor-p:* 0.00034
   - Como o valor-p é menor que o nível de significância de 0.05, rejeitamos a hipótese nula de que as notas dos críticos seguem uma distribuição normal. Portanto, *as notas dos críticos não seguem uma distribuição normal*.

2. *Teste de Shapiro-Wilk para Notas da Audiência (Rotten Tomatoes):*

   - *Valor-p:* 0.08708
   - Como o valor-p é maior que 0.05, não podemos rejeitar a hipótese nula de que as notas da audiência seguem uma distribuição normal. Portanto, *as notas da audiência seguem uma distribuição normal*.

### *Análise de Diferença entre as Notas:*

3. *Teste de Wilcoxon para Comparação entre as Notas dos Críticos e da Audiência:*

   - *Estatística de Wilcoxon:* 1385.00
   - *Valor-p:* 0.25963
   - Como o valor-p é maior que 0.05, não podemos rejeitar a hipótese nula de que não há diferença significativa entre as notas dos críticos e da audiência. Portanto, *não há uma diferença estatisticamente significativa entre as notas dos críticos e da audiência*.

### *Análise de Outliers:*

4. *Detecção de Outliers nas Notas dos Críticos e da Audiência (Rotten Tomatoes):*

   - Usando o método *IQR (Interquartile Range), verificamos que **não há outliers nas notas dos críticos nem nas notas da audiência*.

<img src='https://github.com/user-attachments/assets/63ebb7a9-7426-4be7-b148-5dcdecc98329'>
- Os *boxplots* das notas dos críticos e da audiência mostram a distribuição das notas:
  - As notas dos críticos apresentam uma dispersão maior, com mediana em torno de 50.
  - As notas da audiência têm uma distribuição mais concentrada, com mediana um pouco acima de 40.
  
Essas visualizações ajudam a entender a variação das notas e confirmar que a audiência tem uma distribuição mais normal em comparação com as notas dos críticos.

### *Conclusão Geral:*

- *Notas dos Críticos (Rotten Tomatoes):* Não seguem uma distribuição normal e não apresentam outliers.
- *Notas da Audiência (Rotten Tomatoes):* Seguem uma distribuição normal e não apresentam outliers.
- *Diferença entre as Notas dos Críticos e da Audiência:* Não há uma diferença significativa entre as duas distribuições.

A diferença entre a normalidade das notas dos críticos e da audiência indica que críticos e usuários podem ter critérios distintos para avaliar filmes, resultando em diferentes padrões de avaliação.

### *Pergunta 7: Qual é a média de notas de filmes de terror por década?*

Para entender como as avaliações de filmes de terror mudaram ao longo das décadas, calculamos a média das notas dos críticos (Rotten Tomatoes), da audiência (Rotten Tomatoes), e do IMDb para cada década, de 1960 a 2020.

### *Processo de Análise:*

1. *Preparação dos Dados:*
   - As notas do IMDb foram convertidas para uma escala de 0 a 100 multiplicando a coluna averageRating por 10.
   - As colunas tomatometer_rating e audience_rating foram usadas para as notas dos críticos e da audiência no Rotten Tomatoes.
   - A década de lançamento de cada filme foi calculada a partir da coluna startYear ou release_year dividindo-se o ano por 10 e multiplicando por 10.

2. *Agregação das Notas por Década:*
   - Agrupamos os dados por década e calculamos a média das notas dos críticos, da audiência, e do IMDb para cada década.

3. *Resultados Agrupados por Década:*
   


### *Análise dos Resultados:*

- *1960s:* As notas dos críticos e da audiência são as mais altas nesta década, refletindo o impacto e a qualidade dos clássicos de terror dos anos 60.
- *1970s a 1980s:* Há um declínio significativo nas notas dos críticos e da audiência na década de 70, seguido de uma leve recuperação nos anos 80.
- *1990s:* Nesta década, as notas mostram uma recuperação, especialmente nas avaliações da audiência.
- *2000s a 2020s:* As décadas de 2000 e 2010 apresentam um declínio acentuado nas avaliações, especialmente nas notas dos críticos. No entanto, as notas do IMDb permanecem mais estáveis, sugerindo que os usuários da plataforma têm uma percepção mais uniforme dos filmes de terror ao longo do tempo.

### *Visualização:*

<img src='https://github.com/user-attachments/assets/c84aa84f-fb76-4dc1-8c81-a8947e16d0aa'>

O gráfico acima mostra a média das notas de filmes de terror por década nas plataformas Rotten Tomatoes (Crítica e Audiência) e IMDb. Observa-se uma tendência decrescente ao longo das décadas, com alguns picos e vales que refletem diferentes fases na história dos filmes de terror.

- A linha azul representa a média das notas dos críticos no Rotten Tomatoes.
- A linha laranja representa a média das notas da audiência no Rotten Tomatoes.
- A linha verde representa a média das notas no IMDb.

### *Conclusão Geral:*

As médias das notas de filmes de terror variam consideravelmente ao longo das décadas. A avaliação da crítica é mais rigorosa e mostra uma tendência de declínio mais pronunciada após os anos 60. As notas da audiência tendem a acompanhar essa tendência, mas com uma variação menor. Já as notas do IMDb permanecem relativamente estáveis, indicando que as avaliações dos usuários dessa plataforma são menos afetadas pelas mudanças nas tendências do gênero de terror.

## Pergunta 8: Média das Avaliações de Filmes de Terror por País

### Descrição
Para identificar a média das notas dos filmes de terror por país, foram utilizadas as avaliações críticas e da audiência de Rotten Tomatoes. A análise foi realizada considerando a presença das colunas necessárias e os países associados aos filmes.

### Processo de Análise:
1. **Verificação das Colunas Necessárias:**
   Certificamos que as colunas `country`, `RottenTomatoes_Critic_Rating`, e `RottenTomatoes_Audience_Rating` estavam presentes no DataFrame `horror_df`.

2. **Expansão dos Países:**
   Os países foram separados em linhas individuais para garantir que cada país fosse considerado separadamente. Isso foi feito utilizando a função `explode` para lidar com múltiplos países listados para um mesmo filme.

3. **Cálculo das Médias:**
   Calculamos a média das avaliações críticas e da audiência para cada país utilizando a função `groupby` e `agg` para obter as médias desejadas.

4. **Ordenação e Visualização:**
   Os dados foram ordenados primeiro pela média das avaliações críticas em ordem decrescente e, em caso de empate, pela média das avaliações da audiência. Um gráfico de barras horizontais foi gerado para visualizar essas médias por país.

### Resultados da Análise:
A tabela abaixo apresenta as médias das avaliações de filmes de terror por país:
<img src="https://github.com/user-attachments/assets/39a6b129-018a-4384-bdb6-86663613e418"/>

### *Pergunta 9: Quais são os filmes de terror mais populares da década de 90?*

Para identificar os filmes de terror mais populares da década de 1990, ordenamos os filmes da década de 90 pela avaliação dos críticos no Rotten Tomatoes e selecionamos os três filmes com as melhores notas.

### *Top 3 Filmes de Terror da Década de 1990 com Melhores Notas:*



### *Análise dos Resultados:*

1. *Tremors (1990):* 
   - Este filme combina elementos de comédia e terror e obteve a maior nota dos críticos (86.0) na década de 90. A audiência também deu uma nota relativamente alta (75.0), e o filme possui uma boa avaliação no IMDb (72.0).

2. *Scream 2 (1997):*
   - Com uma mistura de comédia, horror e suspense, "Scream 2" é um dos filmes mais populares da década de 90, com uma nota de 81.0 dos críticos. No entanto, a audiência foi um pouco mais crítica, com uma nota de 57.0.

3. *Candyman (1992):*
   - "Candyman" é um clássico do terror que tem uma nota de 75.0 dos críticos e uma boa aceitação entre a audiência (62.0). O filme também foi bem recebido no IMDb, com uma nota de 67.0.

### *Conclusão Geral:*

Os filmes de terror mais bem avaliados da década de 90 variam em estilo, combinando comédia, horror e suspense. Esses filmes não apenas conseguiram boas avaliações dos críticos, mas também foram bem recebidos por uma grande parte da audiência. "Tremors," em particular, destaca-se como o filme de terror mais popular da década com uma combinação única de comédia e horror.

### *Pergunta 10: Quais são os diretores de filmes de terror com a maior média de notas dos usuários e dos críticos?*

Para identificar os diretores mais bem avaliados nos filmes de terror, analisamos as médias das avaliações dos críticos e da audiência para cada diretor e também a discrepância entre as duas avaliações.

### *Top 10 Diretores com Melhores Médias de Avaliações dos Críticos (Rotten Tomatoes):*

| Diretor             | Média das Notas dos Críticos | Média das Notas da Audiência |
|---------------------|------------------------------|------------------------------|
| Patrick Brice       | 100.0                        | 72.0                         |
| Babak Anvari        | 99.0                         | 73.0                         |
| Roman Polanski      | 96.0                         | 87.0                         |
| J.D. Dillard        | 95.0                         | 52.0                         |
| Sam Raimi           | 95.0                         | 84.0                         |
| Brian DePalma       | 93.0                         | 77.0                         |
| Daniel Goldhaber    | 93.0                         | 54.0                         |
| Eli Craig           | 92.0                         | 47.0                         |
| Mike Flanagan       | 91.0                         | 71.0                         |
| Ruben Fleischer     | 89.0                         | 86.0                         |

*Análise:*
- *Patrick Brice* e *Babak Anvari* lideram a lista com notas perfeitas ou próximas disso pelos críticos. No entanto, suas avaliações de audiência são um pouco mais baixas.
- *Roman Polanski* e *Sam Raimi* são outros diretores altamente respeitados, com boas avaliações tanto dos críticos quanto da audiência.

### *Top 10 Diretores com Melhores Médias de Avaliações da Audiência (Rotten Tomatoes):*

| Diretor                                    | Média das Notas dos Críticos | Média das Notas da Audiência |
|--------------------------------------------|------------------------------|------------------------------|
| Roman Polanski                             | 96.0                         | 87.0                         |
| Ruben Fleischer                            | 89.0                         | 86.0                         |
| Sam Raimi                                  | 95.0                         | 84.0                         |
| James Wan                                   | 83.0                         | 82.0                         |
| Banjong Pisanthanakun, Parkpoom Wongpoom    | 59.0                         | 77.0                         |
| Brian DePalma                               | 93.0                         | 77.0                         |
| Ron Underwood                               | 86.0                         | 75.0                         |
| Babak Anvari                                | 99.0                         | 73.0                         |
| Patrick Brice                               | 100.0                        | 72.0                         |
| Mike Flanagan                               | 91.0                         | 71.0                         |

*Análise:*
- *Roman Polanski* e *Ruben Fleischer* também lideram em termos de notas de audiência, sugerindo que seus filmes agradam tanto os críticos quanto o público.
- *James Wan* é outro diretor notável, especialmente por seu trabalho no gênero de terror, com uma nota de audiência de 82.0.

### *Top 10 Diretores com Maior Discrepância Entre Avaliações dos Críticos e da Audiência:*

| Diretor                                   | Média das Notas dos Críticos | Média das Notas da Audiência | Discrepância |
|-------------------------------------------|------------------------------|------------------------------|--------------|
| Travis Stevens                            | 84.0                         | 22.0                         | 62.0         |
| Johnny Kevorkian                          | 80.0                         | 28.0                         | 52.0         |
| Roxanne Benjamin, Annie Clark, Karyn Kusama | 70.0                         | 19.0                         | 51.0         |
| Eli Craig                                  | 92.0                         | 47.0                         | 45.0         |
| Trey Edward Shults                         | 87.0                         | 44.0                         | 43.0         |
| J.D. Dillard                               | 95.0                         | 52.0                         | 43.0         |
| Johnny Martin                              | 0.0                          | 39.0                         | 39.0         |
| Mark Neveldine                             | 20.0                         | 59.0                         | 39.0         |
| Daniel Goldhaber                           | 93.0                         | 54.0                         | 39.0         |
| Oz Perkins                                  | 58.0                         | 24.0                         | 34.0         |

*Análise:*
- *Travis Stevens* tem a maior discrepância entre as notas dos críticos e da audiência, com uma diferença de 62 pontos. Isso sugere que seu trabalho é muito mais apreciado pelos críticos do que pelo público.
- Diretores como *Eli Craig* e *J.D. Dillard* também mostram grandes discrepâncias, o que pode indicar estilos ou temas que ressoam de forma diferente entre críticos e a audiência.

### *Conclusão Geral:*

A análise mostra que diretores como *Roman Polanski, **Sam Raimi, e **Ruben Fleischer* conseguem agradar tanto críticos quanto audiência, refletindo em suas altas notas em ambas as categorias. No entanto, outros diretores, como *Travis Stevens* e *Eli Craig*, apresentam grandes discrepâncias entre as avaliações, sugerindo uma polarização na recepção de seus filmes. Esses insights podem ajudar a entender como diferentes diretores são percebidos de maneira distinta por críticos e o público.
