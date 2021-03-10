## Como verificar a cobertura de testes de APIs REST

<img src="https://miro.medium.com/max/783/1*LUnm94yasApryQobTwzHhA.jpeg" width="626" height="439.99">
 
<a href="https://www.freepik.com/free-vector/tiny-people-testing-quality-assurance-software-isolated-flat-vector-illustration-cartoon-character-fixing-bugs-hardware-device-application-test-it-service-concept_10613736.htm#page=1&amp;query=software%20testing&amp;position=0" class="cs ip" rel="noopener nofollow">***Software Quality Assurance.***</a>

Algumas vezes, no projeto em que estamos inseridos na empresa, precisamos passar para o time uma clareza sobre o que está sendo implementado nos testes automatizados de API REST ou quanto da API está coberta pelos testes.
Existe uma forma de calcular a cobertura de testes, que se baseia nos critérios de cobertura de entrada (Input Coverage) e cobertura de saída (Output Coverage).

Neste artigo vou te mostrar como é realizado o cálculo da cobertura de testes de uma forma simples e objetiva, assim você poderá calcular a cobertura de seus testes, caso ache necessário.
Em seguida, passarei por alguns critérios para explicar como calcular sua cobertura.

### Path Coverage (input)
Verifica a cobertura da suíte de testes de acordo com os endpoints que a API possui. Este critério é importante, pois ao receber uma solicitação, o programa pode executar caminhos diferentes, então precisamos garantir que os endpoints da API REST estão cobertos pelos testes.
A análise é realizada pela quantidade de URI( URL + URN (Resource name)) que a API possui (se for a mesma URI para métodos diferentes, considera-se apenas um).

O ideal é realizar ao menos uma requisição para verificar cada endpoint.
Se verificar a imagem do swagger abaixo, podemos notar 13 endpoints diferentes:

<img src="https://miro.medium.com/max/875/0*fvX0D9IzUnB2EZEn" width="680" height="605.78">

Suponha que a automação desta API tenha apenas 6 desses endpoints implementados, mas a API possui 13 endpoints.
Para calcular a cobertura: quantidade de testes automatizados / quantidade de endpoints na API REST.

<img src="https://miro.medium.com/max/269/1*UzlqnUIMKRiH92L1yEGhuA.png" width="215" height="93">

Então 46% dos testes de path estão cobertos pela automação.

*** Operator Coverage (input) ***

Confere a cobertura de testes de todos os métodos existentes na API REST (GET, POST, PUT, DELETE…).
O swagger abaixo tem um total de 19 operações:
