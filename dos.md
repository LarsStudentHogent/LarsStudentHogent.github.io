# Lars Vervaele (202182581)

- [ ] Front-end Web Development
  - [GitHub repository](github.com/HOGENT-Web)
  - [Online versie](github.com/HOGENT-Web)
- [X] Web Services: GITHUB URL
  - [GitHub repository](https://github.com/Web-IV/2223-webservices-LarsStudentHogent.git)
  - [Online versie](https://two223-webservices-larsstudenthogent.onrender.com/api/films)

**Logingegevens**

gebruiker:
- Gebruikersnaam/e-mailadres: lars.vervaele@student.hogent.be
- Wachtwoord:root1234!  
  
admin:
- Gebruikersnaam/e-mailadres: vervaelelars@gmail.com
- Wachtwoord:root1234!

## Projectbeschrijving
Mijn project gaat over een database waar je films kan opvragen, via deze film kan je informatie zien zoals waar deze te bekijken is en hoeveel deze service kost (streaming).  
Daarnaast kan je ook de statistieken zien van deze film, rating is een score van 1-10, populariteit is een ranking waarbij 1 de meest populaire film is van dit moment, en voters geeft het aantal stemmen weer waarmee de rating is bepaald.  
Via de tabel acteurinfilm kan je zien welke acteurs in een film spelen en welke rol deze hebben.
![image](https://user-images.githubusercontent.com/97037014/209236726-54430dcc-2e9b-40d3-af9b-e97ca7da207f.png)

## Screenshots

via de /api/film kan je een overzicht vragen van alle films per film krijg je de info over de film, de streamingservice en de statistieken.  
![image](https://user-images.githubusercontent.com/97037014/209374679-a23bb71d-dc95-47fa-ac84-2a692816c7b1.png)  
  
via de /api/acteurs/film/:id kan je een overzicht krijgen van de acteurs die in de film van de meegegeven id spelen, je krijgt info over de acteur en de rol die hij in de film speelt.  
![image](https://user-images.githubusercontent.com/97037014/209377298-83ec5cc6-add4-4cab-8bba-080903d32ad7.png)

## Behaalde minimumvereisten

### Web Services

- **datalaag**

  - [x] voldoende complex (meer dan één tabel)
  - [x] één module beheert de connectie + connectie wordt gesloten bij sluiten server
  - [x] heeft migraties
  - [x] heeft seeds
<br />

- **repositorylaag**

  - [x] definieert één repository per entiteit (niet voor tussentabellen) - indien van toepassing
  - [x] mapt OO-rijke data naar relationele tabellen en vice versa
<br />

- **servicelaag met een zekere complexiteit**

  - [x] bevat alle domeinlogica
  - [x] bevat geen SQL-queries of databank-gerelateerde code
<br />

- **REST-laag**

  - [x] meerdere routes met invoervalidatie
  - [x] degelijke foutboodschappen
  - [x] volgt de conventies van een RESTful API
  - [x] bevat geen domeinlogica
  - [x] degelijke authorisatie/authenticatie op alle routes
<br />

- **varia**
  - [x] een aantal niet-triviale testen (min. 1 controller >=80% coverage)
  - [x] minstens één extra technologie
  - [x] duidelijke en volledige `README.md`
  - [x] maakt gebruik van de laatste ES6-features (object destructuring, spread operator...)
  - [x] volledig en tijdig ingediend dossier


## Projectstructuur
### Web Services
In de src folder zitten 5 mappen: core, data, repository,service en rest.   
In de core folder zitten alle programmas die te maken hebben met authorisatie en logging.  
In de data folder zitten alle programmas die te maken hebben met de databank connectie, de migrations en de seeding.  
De repository folder zorgt voor het ophalen van bepaalde data uit de database.  
De service laag bevat alle domeinfuncties.  
En de rest laag zorgt voor de validatie, permissies en de restfuncties.  

## Extra technologie
### Web Services
Ik heb swagger gebruikt als extra technologie, via swagger kan je alle mogelijkheden van mijn gemaakte app zien.  
Wanneer achter mijn url /swagger wordt toegevoegd kom je op een webpagina die info geeft over mijn API doormiddel van comments in mijn code.  
Je kan ook de calls uitvoeren op deze website maar hiervoor is wel een authentificatie token nodig die afgehaald kan worden via postman.
[Swagger website](https://two223-webservices-larsstudenthogent.onrender.com/swagger)

npm install swagger-jsdoc --save  
npm install koa2-swagger-ui --save  

## Testresultaten
### Web Services

De eerste test gaat over de getAll functie, een get request wordt gestuur naar de /api/streamingservice en we verwachten een response status 200 terug en we checken als we weldegelijk de 3 items terugkrijgen die we in de beforeAll hebben toegevoegd via de response.body.items.lenght.  
In de 2de test testen we de getById we geven een id mee van het 1e item die we hebben toegevoegd in de beforeAll, we verwachten een response status 200 en we checken als we het 1e item terugkrijgen.
Met de 3de en 4de test testen we de create statement.  
In de 3de test geven we juiste waarden mee en verwachten we een response status 201 en checken we als de waarden van het aangemaakte item overeenstemmen met de meegegeven waarden.  
In de 4de test geven we foute waarden mee en verwachten we dus een response status 400 (Bad Request).  
Test 5 en 6 testen de update functie.  
Test 5 geeft juiste waarden mee en we verwachten dus een 200 response status en checken we als de gëupdatete waarden overeen komen met de meegegeven waarden.
Test 6 geeft en Id mee die nog niet bestaat dus verwachten we een response status 400 (Bad Request).
In de laatste test testen we de delete functie, we geven de id mee van het 1e bestand die toegevoegd werd in de beforeAll en verwachten een repsonse status 204 en een lege body.
![image](https://user-images.githubusercontent.com/97037014/209368850-cf47a6b8-6401-40d1-aa31-1c9862d4ad12.png)

## Gekende bugs
### Web Services

