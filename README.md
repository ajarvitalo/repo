# repo
Fullstack open kurssi

# 0.4 tehtävä

![image](https://user-images.githubusercontent.com/60025887/174735049-db96e75d-fe7a-4622-84bf-595fcc9d2fd5.png)


```
Selain->Palvelin HTTP POST https://studies.cs.helsinki.fi/exampleapp/new_note

Palvelin->Selain Vastaus HTTP-statuskoodilla 302,
eli kehottaa selainta tekemään HTTP GET-pyynnön kohteeseen notes

note over Selain
Selain lataa uudelleen muistiinpanojen sivun ja sen seurauksena syntyy kolme muuta HTTP-pyyntöä:
main.css, main.js ja data.json.
end note

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css

Palvelin->Selain Palauttaa tiedoston main.css

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.js

Palvelin->Selain Lähettää main.js tiedoston

note over Selain
Selain alkaa suorittaa .js koodia, joka pyytää JSON-datan palvelimelta
end note

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json

Palvelin->Selain [{ content: "Uusi muistiinpano", date: "2022-06-06" }, ...]

note over Selain
Selain suorittaa tapahtumankäsittelijän
joka esittää muistiinpanot näytöllä
end note
```
# 0.5 tehtävä

![image](https://user-images.githubusercontent.com/60025887/174744542-1ed94b54-7b1f-4780-b0ce-e80e79b9d146.png)

```
Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa

Palvelin-->Selain Palauttaa HTML-koodin

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css

Palvelin-->Selain Lähettää tiedoston main.css

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js

Palvelin-->Selain Lähettää tiedoston spa.js

note over Selain
Selain alkaa suorittaa palvelimen
lähettämää .js koodia, 
joka pyytää JSON-datan palvelimelta
end note

Selain->Palvelin HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json

Palvelin-->Selain [{ content: "Uusi muistiinpano", date: "2022-06-06" }, ...]

note over Selain
Selain suorittaa tapahtumankäsittelijän
joka esittää muistiinpanot näytöllä
end note
```

# 0.6 tehtävä

![image](https://user-images.githubusercontent.com/60025887/174748420-a34e66ea-207d-435d-b898-182bc67d2faf.png)

```
Selain->Palvelin POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa

note over Selain
Pyyntö sisältää uuden muistiinpanon muodossa JSON, 
joka sisältää sisällön(content) ja aikaleiman(date)
end note

Palvelin->Selain Statuskoodi 201 created
```
