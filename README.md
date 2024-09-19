# assignment-api
GITHUB
Create new repository
Integration Github with Katalon
(Seharusnya melakukan step create new branch tetapi terlewat)

KATALON
Create Global Variable dengan variable mainURL to generate website https://jsonplaceholder.typicode.com/

Create new object repository Web Service Request for GET (repoGET)
Input URL pada repo GET -> ${GlobalVariable.mainURL}/albums?userId=${userid} (GET data albums dengan userId bernilai 1, dimana userid telah dibuatkan variable dengan value = 1)
RUN repository dengan response 200
Create new test case GET (tryingGET)

Create new object repository Web Service Request for POST (repoPOST)
Input URL pada repo POST -> ${GlobalVariable.mainURL}/albums (Create data albums)
RUN repository dengan response 201
Create new test case POST (createPOST)

Create new object repository Web Service Request for DELETE (repoDELETE)
Input URL pada repo DELETE -> ${GlobalVariable.mainURL}/albums/id=1 (DELETE data albums yang memiliki id = 1)
RUN repository dengan response 200
Create new test case DELETE (DELETEalbums)

Gunakan function pada tiap test case:
WS.verifyResponseStatusCode(postresponse, 200/201) -> untuk verify response
def slurper = new groovy.json.JsonSlurper(); def result = slurper.parseText(getResponse.getResponseBodyContent()) -> read text JSON
Add assert -> untuk mendeklarasi
