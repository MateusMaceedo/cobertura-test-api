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

##### Operator Coverage (input) 

Confere a cobertura de testes de todos os métodos existentes na API REST (GET, POST, PUT, DELETE…).
O swagger abaixo tem um total de 19 operações:

<img src="https://miro.medium.com/max/875/0*FLEc8zdY1hZ1IWDY" width="680" height="597.17">

Então, deve-se verificar quais métodos da API foram cobertos pela automação de testes. Vamos supor que dezesseis métodos tiveram testes automatizados implementados.

Para calcular a cobertura: quantidade de operações da API estão automatizados/ quantidade total de operações da API REST.

<img alt="A imagem mostra o exemplo do calco de cobertura: 6 divido por 9 é igual a 0,84, que corresponse a 84 porcento." class="sy tm t u v ib aj c" width="205" height="93" src="https://miro.medium.com/max/256/1*YhPNpXV-JimfE8S6Hu_ZEQ.png" srcset="" sizes="205px">

Então temos 84% dos testes de operações cobertos.

##### Parameter Coverage (input)

Verifica a cobertura de uma suíte de testes conforme os parâmetros existentes em cada método da API.

<img alt="A imagem mostra os parametros query de um método GET." class="sy tm t u v ib aj c" width="1134" height="377" src="https://miro.medium.com/max/1418/1*g3TSnk_hOzpnZCK2_cmWMw.png" srcset="https://miro.medium.com/max/345/1*g3TSnk_hOzpnZCK2_cmWMw.png 276w, https://miro.medium.com/max/690/1*g3TSnk_hOzpnZCK2_cmWMw.png 552w, https://miro.medium.com/max/800/1*g3TSnk_hOzpnZCK2_cmWMw.png 640w, https://miro.medium.com/max/875/1*g3TSnk_hOzpnZCK2_cmWMw.png 700w" sizes="700px">

<img alt="A imagem mostra um parametro body do método POST" class="sy tm t u v ib aj c" width="1136" height="308" src="https://miro.medium.com/max/1420/1*YE-UjrT3ps1s2-yQ7YaHOQ.png" srcset="https://miro.medium.com/max/345/1*YE-UjrT3ps1s2-yQ7YaHOQ.png 276w, https://miro.medium.com/max/690/1*YE-UjrT3ps1s2-yQ7YaHOQ.png 552w, https://miro.medium.com/max/800/1*YE-UjrT3ps1s2-yQ7YaHOQ.png 640w, https://miro.medium.com/max/875/1*YE-UjrT3ps1s2-yQ7YaHOQ.png 700w" sizes="700px">

<img alt="A imagem mostra o parametro api_key no headers e o parametro path no método DELETE." class="sy tm t u v ib aj c" width="1132" height="320" src="https://miro.medium.com/max/1415/1*-RG2cqGoZzlOAOnNh5oQHg.png" srcset="https://miro.medium.com/max/345/1*-RG2cqGoZzlOAOnNh5oQHg.png 276w, https://miro.medium.com/max/690/1*-RG2cqGoZzlOAOnNh5oQHg.png 552w, https://miro.medium.com/max/800/1*-RG2cqGoZzlOAOnNh5oQHg.png 640w, https://miro.medium.com/max/875/1*-RG2cqGoZzlOAOnNh5oQHg.png 700w" sizes="700px">

#### Para calcular a cobertura:

Para atingir 100% de cobertura de testes é necessário testar todos os parâmetros de entrada de cada operação pelo menos uma vez. Realizar a combinação de todos os parâmetros é desejável, mas não estritamente necessário para chegar a 100% de cobertura.

Suponha que a API tenha um total de 5 parâmetros, e na automação da API os 5 parâmetros foram cobertos.

Quantidade total de parâmetros cobertos na suítes de testes / quantidade total de parâmetros nos métodos da API.

<img alt="A imagem mostra o exemplo do calculo de cobertura. Cinco divido por cinco é igual a 1, que é igual a cem por cento." class="sy tm t u v ib aj c" width="209" height="92" src="https://miro.medium.com/max/261/1*vhNMozJFd8PzW4HyVqHLFw.png" srcset="" sizes="209px">

#### Parameter Value Coverage (input)
Confere a cobertura da suíte de testes de parâmetros booleano e enum nas operações (se existirem).
Para calcular a cobertura:

Quantidade total de valores diferentes enviados / quantidade total de valores que podem assumir.

Para atingir 100% de cobertura cada parâmetro booleano e enum deve assumir todos os valores possíveis.

#### Content-Type Coverage (input e output)
Verifica a cobertura de testes automatizados onde o content-type está sendo exibido em cada endpoint, ou seja, se for demonstrado nas opções do content-type de envio application/json e um 

application/xml, então duas opções do parâmetros de envio deveriam ser cobertas.

<img alt="A imagem mostra o combo-box do content-type com as opções application/json e application/xml, exibidos no swagger." class="sy tm t u v ib aj c" width="443" height="399" src="https://miro.medium.com/max/554/0*QdRAw73MURCHRnGe" srcset="https://miro.medium.com/max/345/0*QdRAw73MURCHRnGe 276w, https://miro.medium.com/max/554/0*QdRAw73MURCHRnGe 443w" sizes="443px">

<img alt="A imagem monstra o content-type application-json, informado no headers da ferramenta postman." class="sy tm t u v ib aj c" width="671" height="71" src="https://miro.medium.com/max/839/0*rN6IPqfWRPmCrbuX" srcset="https://miro.medium.com/max/345/0*rN6IPqfWRPmCrbuX 276w, https://miro.medium.com/max/690/0*rN6IPqfWRPmCrbuX 552w, https://miro.medium.com/max/800/0*rN6IPqfWRPmCrbuX 640w, https://miro.medium.com/max/839/0*rN6IPqfWRPmCrbuX 671w" sizes="671px">

Também devem ser verificadas as opções do content-type da resposta:

<img alt="A imagem mostra o combo-box do content-type com as opções application-json e application-xml em um response do swagger." class="sy tm t u v ib aj c" width="1122" height="66" src="https://miro.medium.com/max/1403/0*Yx52H4aksY7K_46T" srcset="https://miro.medium.com/max/345/0*Yx52H4aksY7K_46T 276w, https://miro.medium.com/max/690/0*Yx52H4aksY7K_46T 552w, https://miro.medium.com/max/800/0*Yx52H4aksY7K_46T 640w, https://miro.medium.com/max/875/0*Yx52H4aksY7K_46T 700w" sizes="700px">

#### Para calcular a cobertura:

Quantidade total de content-type em cada operação cobertos pela suíte de testes / Quantidade total de content-type em todas as operações da API.

Suponha a API possua as operações POST, PUT, GET e DELETE. POST e PUT possuem cada um 2 opções de content-type, logo a API possui um total de 4 content-type a serem cobertos. A automação cobriu apenas uma opção, no POST e uma opção, no PUT. Sendo assim:

<img alt="Exemplo de calculo de cobertura: 2 dividido por 4 é igual a 0,5, que corresponde a 50 porcento." class="sy tm t u v ib aj c" width="210" height="96" src="https://miro.medium.com/max/263/1*A5X_sRtdJb2Ui0GoZad8Eg.png" srcset="" sizes="210px">

#### Operation Flow (input)

Este critério mede um conjunto de testes de acordo com as sequências de operações que é executado.
Por exemplo:

Fluxo1: Post-Get(id)
Fluxo2: Post-Put
Fluxo3: Post-Delete
Fluxo4: Post-Get(Query)

Se todos os fluxos estiverem implementados no teste automatizado, então a API Rest está 100% coberta pela automação.

Porém se é possível criar 4 tipos de fluxos, mas sua automação possui apenas um, por exemplo, criação (Post) e consulta (Get id), então terás apenas 25% de cobertura.

<img alt="Exemplo calculo cobertura: 1 dividido por 4 é igual a 0,25 que corresponde a 25 porcento." class="sy tm t u v ib aj c" width="204" height="91" src="https://miro.medium.com/max/255/1*pVocJbzt_kkPcFmlNS5peg.png" srcset="" sizes="204px">

#### Response Properties Body Coverage (Output)
Este critério mede os parâmetros no corpo da resposta, então deve ser verificado se todas as propriedades da resposta estão cobertas pelo teste.

Para calcular a cobertura deve-se dividir o número total de todas as propriedades de todos os objetos que pode ser obtido na resposta da API, pelo número de propriedades da resposta que os testes estão cobrindo.

#### Status Code Coverage (Output)

Este critério verifica quais status codes existentes em cada endpoint estão cobertos pelos testes.

<img alt="A imagem mostra um método do swagger que pode ter os status code 200, 400 e 404." class="sy tm t u v ib aj c" width="270" height="327" src="https://miro.medium.com/max/338/0*YxMVGHEDRfMGW3x9" srcset="" sizes="270px">

Suponha que a API tenha um total de 25 status code, e na automação da API apenas 15 status code foram cobertos.

<img alt="Exemplo de calculo de cobertura: 15 dividido por 25 é igual a 0,6, que corresponde a 60 porcento." class="sy tm t u v ib aj c" width="208" height="96" src="https://miro.medium.com/max/260/1*_uTXDuESQ_495KDpQxIp3g.png" srcset="" sizes="208px">
Figura 14: Status code. Fonte: <a href="https://petstore.swagger.io/#/pet/findPetsByStatus" class="cs ip" rel="noopener nofollow">Swagger UI</a>




Portanto, para atingir 100% da cobertura de testes, todos os status codes de cada operação deve estar implementado nos testes.

Realizar o levantamento dos critérios de cobertura é importante, pois te dá um norte para saber o quão efetivo os testes automatizados estão sendo. Será que todos os paths da sua API estão cobertos? Será que não é possível atingir 100% de cobertura de parâmetros de entrada dos métodos? Comenta aí, o que você achou desta metodologia ou se você aplicaria e mostraria a cobertura de testes para o seu time.

## Referências

<strong class="is la">Test Coverage Criteria for RESTful Web APIs</strong>
