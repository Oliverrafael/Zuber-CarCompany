# Descrição do projeto
Zuber, uma nova empresa de compartilhamento de caronas em Chicago. O objetivo foi identificar padrões nas informações disponíveis para entender as preferências dos passageiros e o impacto de fatores externos, como condições climáticas e horários, nas corridas. A análise ajudou a obter insights valiosos para otimizar a oferta de serviços e melhorar a experiência do usuário.

# Objetivo do projeto
Identificar padrões nas informações disponíveis para entender as preferências dos passageiros e o impacto de fatores externos, como condições climáticas e horários, nas corridas.

# Sobre o banco de dados:
*Observação*: O banco não é aberto a consultas externas, então coloquei o schema do banco de dados e no notebook deixei minhas consultas e o qual era o intuito de cada consulta.

## Datasets
- moved_project_sql_result_01.csv
- moved_project_sql_result_04.csv
- moved_project_sql_result_07.csv
- schema.png

# Descrição dos dados

Um banco de dados com informações sobre corridas de táxi em Chicago:

tabela neighborhoods: dados sobre os bairros da cidade

- name - nome do bairro
- neighborhood_id: código do bairroo

tabela cabs: dados sobre os táxis

- cab_id: código do veículo
- vehicle_id: a identificação técnica do veículo
- company_name: a empresa proprietária do veículo

tabela trips: dados sobre corridas

- trip_id: código da corrida
- cab_id: código do veículo que opera a corrida
- start_ts: data e hora do início da corrida (tempo arredondado para a hora)
- end_ts: data e hora do final da corrida (tempo arredondado para a hora)
- duration_seconds: duração da corrida em segundos
- distance_miles: distância percorrida em milhas
- pickup_location_id: código do bairro de retirada
- dropoff_location_id: código do bairro de entrega

tabela weather_records: dados sobre o clima

- record_id: código de registro meteorológico
- ts: grava data e hora (tempo arredondado para a hora)
- temperature: temperatura quando o registro foi feito
- description: breve descrição das condições meteorológicas, ex. "chuva leve" ou "nuvens esparsas"

## Etapas para conclusão do projeto

- Etapa 1:  Escreva um código para analisar os dados sobre o clima em Chicago em novembro de 2017 no site: https://practicum-content.s3.us-west-1.amazonaws.com/data-analyst-eng/moved_chicago_weather_2017.html
- Etapa 2: Análise Exploratória de Dados
- Encontre o número de corridas de táxi para cada empresa de táxi de 15 a 16 de novembro de 2017. Nomeie o campo resultante como trips_amount e imprima-o junto com o campo company_name. Ordene os resultados pelo campo trips_amount em ordem decrescente.
- Encontre o número de corridas para cada empresa de táxi cujo nome contém as palavras "Yellow" ou "Blue" ("Amarelo" ou "Azul", respectivamente) de 1º a 7 de novembro de 2017. Nomeie a variável resultante como trips_amount. Agrupe os resultados pelo campo company_name.
- Em novembro de 2017, as empresas de táxi mais populares eram Flash Cab e Taxi Affiliation Services. Encontre o número de corridas para essas duas empresas e nomeie a variável resultante como trips_amount. Junte as corridas para todas as outras empresas no grupo "Other". Agrupe os dados por nomes de empresas de táxi. Nomeie o campo com os nomes das empresas de táxi como company. Classifique o resultado em ordem decrescente por trips_amount.

- Etapa 3: Teste a hipótese de que a duração das corridas do Loop até ao Aeroporto Internacional O'Hare muda em sábados chuvosos.
- Recupere os identificadores dos bairros O'Hare e Loop da tabela neighborhoods.
- Para cada hora, recupere os registros de condições meteorológicas da tabela weather_records. Usando o operador CASE, divida todas as horas em dois grupos: "Bad" se o campo description contiver as palavras "rain" (chuva) ou "storm" (tempestade) e "Good" para outros. Nomeie o campo resultante como weather_conditions. A tabela final deve incluir dois campos: data e hora (ts) e weather_conditions.
- Recupere da tabela trips todos as corridas que começaram no Loop (neighborhood_id: 50) e terminaram em O'Hare (neighborhood_id: 63) em um sábado. Obtenha as condições meteorológicas para cada corrida. Use o método que você aplicou na tarefa anterior. Também recupere a duração de cada corrida. Ignore corridas para as quais os dados sobre as condições meteorológicas não estão disponíveis.
  
- Etapa 4: Análise exploratória de dados (Python)
- Além dos dados recuperados nas tarefas anteriores, você recebeu um segundo arquivo. Agora você tem estes dois CSVs:
- project_sql_result_01.csv. Ele contém os seguintes dados:
- company_name: nome da empresa de táxi
- trips_amount: o número de corridas para cada empresa de táxi de 15 a 16 de novembro de 2017.
- project_sql_result_04.csv. Ele contém os seguintes dados:
- dropoff_location_name: bairros de Chicago onde as corridas terminaram
- average_trips: o número médio de viagens que terminaram em cada bairro em novembro de 2017.
- Para esses dois conjuntos de dados, agora você precisa:
- importar os arquivos
- estudar os dados que eles contêm
- verifique se os tipos de dados estão corretos
- identificar os 10 principais bairros em termos de destinos
- fazer gráficos: empresas de táxi e número de corridas, 10 principais bairros por número de corridas em que esse - bairro é destino
- tirar conclusões com base em cada gráfico e explicar os resultados.

- Etapa 5: Testando hipóteses (Python)
- project_sql_result_07.csv —o resultado da última consulta. Ele contém dados sobre viagens do Loop para o Aeroporto Internacional O'Hare. Lembre-se, estes são os valores dos campos da tabela:

- start_ts — data e hora do começo da corrida
- weather_conditions — condições meteorológicas no momento em que a corrida começou
- duration_seconds — duração da viagem em segundos
- Teste a hipótese: "A duração média dos passeios do Loop para o Aeroporto Internacional O'Hare muda nos sábados chuvosos."  e  Defina o valor do nível de significância (alfa) por conta própria.
- Explique:
- como você formou as hipóteses nula e alternativa
- qual critério você usou para testar a hipótese e porque

## 🛠 Habilidade
Python
SQL

<svg xmlns="http://www.w3.org/2000/svg" width="256" height="256" fill="none" viewBox="0 0 256 256"><rect width="256" height="256" fill="#242938" rx="60"/><path fill="url(#paint0_linear_2_47)" d="M127.279 29C76.5066 29 79.6772 51.018 79.6772 51.018L79.7338 73.8284H128.185V80.6772H60.4893C60.4893 80.6772 28 76.9926 28 128.222C28 179.452 56.3573 177.636 56.3573 177.636H73.2812V153.863C73.2812 153.863 72.369 125.506 101.186 125.506H149.24C149.24 125.506 176.239 125.942 176.239 99.4123V55.5461C176.239 55.5461 180.338 29 127.279 29ZM100.563 44.339C105.384 44.339 109.28 48.2351 109.28 53.0556C109.28 57.8761 105.384 61.7723 100.563 61.7723C95.7426 61.7723 91.8465 57.8761 91.8465 53.0556C91.8465 48.2351 95.7426 44.339 100.563 44.339Z"/><path fill="url(#paint1_linear_2_47)" d="M128.721 227.958C179.493 227.958 176.323 205.941 176.323 205.941L176.266 183.13H127.815V176.281H195.511C195.511 176.281 228 179.966 228 128.736C228 77.5062 199.643 79.323 199.643 79.323H182.719V103.096C182.719 103.096 183.631 131.453 154.814 131.453H106.76C106.76 131.453 79.7607 131.016 79.7607 157.546V201.412C79.7607 201.412 75.6615 227.958 128.721 227.958ZM155.437 212.619C150.616 212.619 146.72 208.723 146.72 203.903C146.72 199.082 150.616 195.186 155.437 195.186C160.257 195.186 164.154 199.082 164.154 203.903C164.154 208.723 160.257 212.619 155.437 212.619Z"/><defs><linearGradient id="paint0_linear_2_47" x1="47.22" x2="146.333" y1="46.896" y2="145.02" gradientUnits="userSpaceOnUse"><stop stop-color="#387EB8"/><stop offset="1" stop-color="#366994"/></linearGradient><linearGradient id="paint1_linear_2_47" x1="108.056" x2="214.492" y1="109.905" y2="210.522" gradientUnits="userSpaceOnUse"><stop stop-color="#FFE052"/><stop offset="1" stop-color="#FFC331"/></linearGradient></defs></svg>




## Bibliotecas utilizadas
- pandas 
- matplotlib
- scipy

## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://github.com/Oliverrafael
)
[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rafael-oliveira-528400335/
)