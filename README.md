# repo
Fullstack open kurssi

# 0.4 tehtävä

![image](https://user-images.githubusercontent.com/60025887/174735049-db96e75d-fe7a-4622-84bf-595fcc9d2fd5.png)


```
Selain->Palvelin HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note

Palvelin->Selain Vastaus HTTP-statuskoodilla 302,
eli kehottaa selainta tekemään HTTP GET-pyynnön kohteeseen notes

//Selain lataa uudelleen muistiinpanojen sivun ja sen seurauksena syntyy kolme muuta HTTP-pyyntöä:
  main.css, main.js ja data.json.

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css

Palvelin->Selain Palauttaa tiedoston main.css

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js

Palvelin->Selain Lähettää main.js tiedoston

//Selain alkaa suorittaa .js koodia, joka pyytää JSON-datan palvelimelta

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json

Palvelin->Selain [{ content: "Uusi muistiinpano", date: "2022-06-06" }, ...]

Selain suorittaa tapahtumankäsittelijän
joka renderöi muistiinpanot näytölle
```
# 0.5 tehtävä


