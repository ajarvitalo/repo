# repo
Fullstack open kurssi

# 0.4 tehtävä

![image](https://user-images.githubusercontent.com/60025887/174753531-7e350156-dd77-4706-a1ba-41591947da00.png)


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

![image](https://user-images.githubusercontent.com/60025887/174753057-84b34bb9-4513-4ffc-84ca-96d0b3931d02.png)

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

![image](https://user-images.githubusercontent.com/60025887/174752345-51d5cb2a-f0d5-4ae9-b434-bba2d742e9b8.png)

```
Selain->Palvelin POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa

note over Selain
Pyyntö sisältää uuden muistiinpanon muodossa JSON, 
joka sisältää sisällön(content) ja aikaleiman(date)
end note

Palvelin->Selain Statuskoodi 201 created
```

# 1.1-1.2 tehtävä

```
const App = () => {
  const course = 'Half Stack application development'
  const part1 = 'Fundamentals of React'
  const exercises1 = 10
  const part2 = 'Using props to pass data'
  const exercises2 = 7
  const part3 = 'State of a component'
  const exercises3 = 14
  
  const Content = (props) => {
    return (
      <div>
        <Part part = {props.part1} exercises = {props.exercises1}/>
        <Part part = {props.part2} exercises = {props.exercises2}/>
        <Part part = {props.part3} exercises = {props.exercises3}/>  
      </div>
    )
  };

  const Header = (props) => {
    return (
      <div>
        <h1>{props.course}</h1>
      </div>
    )
  };

  const Part = (props) => {
    return (
      <div>
        {props.part} {props.exercises}
      </div>
    )
  };
  const Total = (props) => {
    return (
      <div>
        
        <p>Number of exercises {props.exercises1 + props.exercises2 + props.exercises3}</p>
        
      </div>
    )
  };
  


  return (
    <div>
      <Header course = {course}/>
      <Content part1 = {part1} exercises1 = {exercises1} part2 = {part2} exercises2 = {exercises2} part3 = {part3} exercises3 = {exercises3} />
      <Total exercises1 = {exercises1} exercises2 = {exercises2} exercises3 = {exercises3}/>
    </div>
    
  )
};
export default App
```

# tehtävä 1.3
```
const App = () => {
  const course = {
    name: 'Half Stack application development',
    
  
  part1: 
    { 
    name: 'Fundamentals of React',
    exercises: 10,
  },
  
  part2: 
  {
    name: 'Using props to pass data',
    exercises: 7,
  },
  
  part3: 
  {
    name: 'State of a component',
    exercises: 14,
  }

  }
  const Content = (props) => {
    console.log(props)
    return (
      <div>
        <Part name = {props.part1.name} exercises = {props.part1.exercises}/>
        <Part name = {props.part2.name} exercises = {props.part2.exercises}/>
        <Part name = {props.part3.name} exercises = {props.part3.exercises}/>  
      </div>
    )
  };

  const Header = (props) => {
    console.log(props)
    return (
        <h1>{props.course.name}</h1>

    )
  };

  const Part = (props) => {
    console.log(props)
    return (
      
        <p>{props.name} {props.exercises}</p>
      
    )
  };
  const Total = (props) => {
    console.log(props)
    return (
      
        
        <p>Number of exercises {props.exercises}</p>
        
      
    )
  };
  


  return (
    <div>
      <Header course = {course.name}/>
      <Content part1 = {course.part1} part2 = {course.part2}  part3 = {course.part3}/>
      <Total exercises = {course.part1.exercises+course.part2.exercises+course.part3.exercises}/>
    </div>
    
  )
};
export default App
```
