# Day 5:Data Fetching & Promises, Destructuring Data, Async, Modules, Wrapping up

## Topics Covered

### 1. Data Fetching & Promises
I learned about making HTTP requests and fetching data from APIs using JavaScript. I explored the Fetch API and learned how to send GET requests, handle responses, and work with JSON data. Additionally, I discovered the concept of promises, which provide a way to handle asynchronous operations and manage the flow of data.

### 2. Destructuring Data
Destructuring allows me to extract specific values from objects or arrays and assign them to variables in a more concise way. I learned how to use destructuring syntax to extract properties from objects and elements from arrays, making my code more readable and efficient.

### 3. Async
Asynchronous programming is essential for handling time-consuming operations without blocking the execution of other tasks. I studied how to work with asynchronous functions and the `async` and `await` keywords, which provide a more synchronous-like syntax for managing asynchronous code.

### 4. Modules
Modularization is a technique used to break down a large codebase into smaller, manageable modules. I explored how to use modules to organize my JavaScript code, import and export functions, variables, or classes between different modules, and create a modular architecture for my applications.[JavaScript modules](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules)

### 5. Wrapping up
As I concluded my learning journey, I reviewed the key concepts and techniques covered throughout the days. I consolidated my understanding of JavaScript fundamentals, DOM manipulation, event handling, data types, functions, and advanced topics such as data fetching, destructuring async programming, and modules.

## Code Example 
```javascript
<!DOCTYPE html>
<!-- saved from url=(0068)https://anjana.dev/javascript-first-steps/3-doggofetch-finished.html -->
<html lang="en-US"><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
    
    <title>Doggo Fetch</title>
    <style>
        body {
            margin: 1rem auto;
            padding: 3rem;
            font-family: sans-serif;
        }
        header {
            width: 70%;
            margin: 1em auto;
        }
        main {
            max-width: 70%;
            margin: 0px auto;
            display:flex; 
            flex-direction: column;
        }
        img {
            max-width: 100%;
        }
        #image-frame {
            font-size: x-large;
            text-align: center;
            margin: 1rem auto;
        }
        #explanation, #score {
            padding: 1rem;
            text-align: center;
        }
        #options {
            max-width: 100%;
            display: flex;
            flex-direction: column;
        }
        button {
            padding: 0.5rem;
            font-size: medium;
            border-radius: 5px;
        }
        .correct {
            background-color: lightgreen;
        }
        .incorrect {
            background-color: lightpink;
        }
        .hidden {
            display: none;
        }
    </style>
  </head>
  <body data-new-gr-c-s-check-loaded="14.1114.0" data-gr-ext-installed="">
    <header>
    <h1>Guess the Doggo</h1>
    <p>What breed is the dog in this image?</p>

    </header>

    <main>
    <div id="image-frame"><img src="./Doggo Fetch2_files/n02110958_12120.jpg"></div>
    <div id="options">
    <button name=" pug" value=" pug" class="correct"> pug</button><button name="brabancon" value="brabancon">brabancon</button><button name="english mastiff" value="english mastiff">english mastiff</button></div>

    </main>

  


  <script type="module">

    const RANDOM_IMG_ENDPOINT = "https://dog.ceo/api/breeds/image/random";

    const BREEDS = ["affenpinscher", "african", "airedale", "akita", "appenzeller", "shepherd australian", "basenji", "beagle", "bluetick", "borzoi", "bouvier", "boxer", "brabancon", "briard", "norwegian buhund", "boston bulldog", "english bulldog", "french bulldog", "staffordshire bullterrier", "australian cattledog", "chihuahua", "chow", "clumber", "cockapoo", "border collie", "coonhound", "cardigan corgi", "cotondetulear", "dachshund", "dalmatian", "great dane", "scottish deerhound", "dhole", "dingo", "doberman", "norwegian elkhound", "entlebucher", "eskimo", "lapphund finnish", "bichon frise", "germanshepherd", "italian greyhound", "groenendael", "havanese", "afghan hound", "basset hound", "blood hound", "english hound", "ibizan hound", "plott hound", "walker hound", "husky", "keeshond", "kelpie", "komondor", "kuvasz", "labradoodle", "labrador", "leonberg", "lhasa", "malamute", "malinois", "maltese", "bull mastiff", "english mastiff", "tibetan mastiff", "mexicanhairless", "mix", "bernese mountain", "swiss mountain", "newfoundland", "otterhound", "caucasian ovcharka", "papillon", "pekinese", "pembroke", "miniature pinscher", "pitbull", "german pointer", "germanlonghair pointer", "pomeranian", "medium poodle", "miniature poodle", "standard poodle", "toy poodle", "pug", "puggle", "pyrenees", "redbone", "chesapeake retriever", "curly retriever", "flatcoated retriever", "golden retriever", "rhodesian ridgeback", "rottweiler", "saluki", "samoyed", "schipperke", "giant schnauzer", "miniature schnauzer", "english setter", "gordon setter", "irish setter", "sharpei", "english sheepdog", "shetland sheepdog", "shiba", "shihtzu", "blenheim spaniel", "brittany spaniel", "cocker spaniel", "irish spaniel", "japanese spaniel", "sussex spaniel", "welsh spaniel", "english springer", "stbernard", "american terrier", "australian terrier", "bedlington terrier", "border terrier", "cairn terrier", "dandie terrier", "fox terrier", "irish terrier", "kerryblue terrier", "lakeland terrier", "norfolk terrier", "norwich terrier", "patterdale terrier", "russell terrier", "scottish terrier", "sealyham terrier", "silky terrier", "tibetan terrier", "toy terrier", "welsh terrier", "westhighland terrier", "wheaten terrier", "yorkshire terrier", "tervuren", "vizsla", "spanish waterdog", "weimaraner", "whippet", "irish wolfhound"];

    
    // Utility function to get a randomly selected item from an array
    function getRandomElement(array) {
        const i = Math.floor(Math.random() * array.length);
        return array[i];
    }

    // Utility function to shuffle the order of items in an array in-place
    function shuffleArray(array) {
        return array.sort((a,b) => Math.random() - 0.5);
    }



    // TODO 1
    // Given an array of possible answers, a correct answer value, and a number of choices to get,
    // return a list of that many choices, including the correct answer and others from the array
    function getMultipleChoices(n, correctAnswer, array) {
        // Use a while loop and the getRandomElement() function
        // Make sure there are no duplicates in the array
        const choices = [correctAnswer];
        while (choices.length < n) {
            let candidate = getRandomElement(array);
            if (choices.indexOf(candidate) < 0) { // check if this is already in the array
                choices.push(candidate); // if not, add it
            }
        }
        return shuffleArray(choices);
    }

    
    // TODO 2
    // Given a URL such as "https://images.dog.ceo/breeds/poodle-standard/n02113799_2280.jpg"
    // return the breed name string as formatted in the breed list, e.g. "standard poodle"
    function getBreedFromURL(url) {
        // The string method .split(char) may come in handy
        // Try to use destructuring as much as you can
        const [,path] = url.split("/breeds/");
        const [breedID] = path.split("/");
        const [breed, subtype] = breedID.split("-");
        return [subtype, breed].join(" ");
    }



    // TODO 3
    // Given a URL, fetch the resource at that URL, 
    // then parse the response as a JSON object,
    // finally return the "message" property of its body
    async function fetchMessage(url) {
        const response = await fetch(url);  // Fetch the resource at the given URL
        const {message} = await response.json(); // Parse the response as JSON & remember its 'message' value
        return message; // Return the message
    }


    // Function to add the multiple-choice buttons to the page
    function renderButtons(choicesArray, correctAnswer) {

        // Event handler function to compare the clicked button's value to correctAnswer
        // and add "correct"/"incorrect" classes to the buttons as appropriate
        function buttonHandler(e) {
            if (e.target.value === correctAnswer) {
                e.target.classList.add("correct");
            } else {
                e.target.classList.add("incorrect");
                document.querySelector(`button[value="${correctAnswer}"]`).classList.add("correct");
            }
        }

        const options = document.getElementById("options"); // Container for the multiple-choice buttons

        // TODO 4
        // For each of the choices in choicesArray,
        // Create a button element whose name, value, and textContent properties are the value of that choice,
        // attach a "click" event listener with the buttonHandler function,
        // and append the button as a child of the options element
        choicesArray.map(choice => {
            let button = document.createElement("button");
            button.value = button.name = button.textContent = choice;
            button.addEventListener("click", buttonHandler);
            options.appendChild(button);
        })
    }


    // Function to add the quiz content to the page
    function renderQuiz(imgUrl, correctAnswer, choices) {
        const image = document.createElement("img");
        image.setAttribute("src", imgUrl);
        const frame = document.getElementById("image-frame");

        image.addEventListener("load", () => {
            // Wait until the image has finished loading before trying to add elements to the page
            frame.replaceChildren(image);
            renderButtons(choices, correctAnswer);
        })
        
    }

    // Function to load the data needed to display the quiz
    async function loadQuizData() {
        document.getElementById("image-frame").textContent = "Fetching doggo...";
        
        const doggoImgUrl = await fetchMessage(RANDOM_IMG_ENDPOINT);
        const correctBreed = getBreedFromURL(doggoImgUrl);
        const breedChoices = getMultipleChoices(3, correctBreed, BREEDS);

        return [doggoImgUrl, correctBreed, breedChoices];
    }

    // TODO 5
    // Asynchronously call the loadQuizData() function,     
    // Then call renderQuiz() with the returned imageUrl, correctAnswer, and choices 
    const [imageUrl, correctAnswer, choices] = await loadQuizData();
    renderQuiz(imageUrl, correctAnswer, choices);
    


  </script>

</body><grammarly-desktop-integration data-grammarly-shadow-root="true"><template shadowrootmode="open"><style>
  div.grammarly-desktop-integration {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
    -moz-user-select: none;
    -webkit-user-select: none;
    -ms-user-select:none;
    user-select:none;
  }

  div.grammarly-desktop-integration:before {
    content: attr(data-content);
  }
</style><div aria-label="grammarly-integration" role="group" tabindex="-1" class="grammarly-desktop-integration" data-content="{&quot;mode&quot;:&quot;full&quot;,&quot;isActive&quot;:true,&quot;isUserDisabled&quot;:false}"></div></template></grammarly-desktop-integration></html>
```
## Coding Exercises
### [Build a Rick & Morty Characters List](https://github.com/orjwan-alrajaby/gsg-expressjs-backend-training-2023/blob/main/learning-sprint-1/week1-day3-task/task.md)
#### My solution 
```javascript

<!DOCTYPE html>
<html>
<head>
  <title>Alive Character List</title>
  <link rel="stylesheet" href="./styles.css">
</head>
<body>
  <h1>Alive Character List</h1>
  <ul id="characterList"></ul>

  <script src="./script.js"></script>
</body>
</html>

//javascript code ------------------------------------------------

document.addEventListener('DOMContentLoaded', () => {
  async function fetchCharacterData() {
    try {
      const response = await fetch('https://rickandmortyapi.com/api/character?status=alive');
      if (!response.ok) {
        throw new Error('Error retrieving character data');
      }
      const data = await response.json();
      const characters = data.results.filter((character, index) => index < 50);
      return characters;
    } catch (error) {
      console.error(error);
    }
  }
//To allow the JavaScript code to access and manipulate the <ul>
const characterList = document.getElementById('characterList');

  fetchCharacterData()
    .then(characters => {
     // Iterate through each character retrieved from the API
      characters.forEach(character => {
      // Create a new <li> element for each character
        const li = document.createElement('li');
        li.innerHTML = `
          <img src="${character.image}" alt="${character.name}">
          <h3>${character.name}</h3>
          <p><strong>Location:</strong> ${character.location.name}</p>
          <p><strong>Species:</strong> ${character.species}</p>
          <p><strong>Gender:</strong> ${character.gender}</p>
        `;
       // Append the <li> element to the characterList element
        characterList.appendChild(li);
      });
    });
});

//css code--------------------------------------------------------
#characterList {
  list-style: none;
  padding: 0;
}

#characterList li {
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

#characterList img {
  width: 100px;
  height: 100px;
  object-fit: cover;
  margin-right: 10px;
}

#characterList h3 {
  margin: 0;
}

#characterList p {
  margin: 0;
}
```
