<!--Laget av Jonatan Roland-->

<!--Styles ligger i 'app.css'-->

<!--JavaScript-->
<script lang="ts"> 
// lang="ts" angir at TypeScript er det valgte programmeringsspråket i <script>-blokken.
// TypeScript er et overmengdespråk av JavaScript, noe som betyr at TypeScript inkluderer alle funksjonene til JavaScript og utvider det med statisk typing

  import maleImg from "./assets/Male.jpg";
  import femaleImg from "./assets/female.jpg";
  import otherImg from "./assets/other.png";
  import secretImg from "./assets/secret.png";
  import Radio from "./lib/Radio.svelte";

// Interresse/preferanse spørsmål sine ulike alternativ verdier
// score er automatisk satt til null og når man velger at alternativ så får verdien en ny score
// labelen er det brukeren ser
let gamingScore = 0;

const gamingOptions = [
    {
        value: 2,
        label: "Uening",
    },
    {
        value: 4,
        label: "Litt Uening",
    },
    {
        value: 5,
        label: "Midt På",
    },
    {
        value: 3,
        label: "Litt Enig",
    },
    {
        value: 1,
        label: "Enig",
    },
];

let languageScore = 0;

const languageOptions = [
    {
        value: 4,
        label: "Uening",
    },
    {
        value: 5,
        label: "Litt Uening",
    },
    {
        value: 3,
        label: "Midt På",
    },
    {
        value: 2,
        label: "Litt Enig",
    },
    {
        value: 1,
        label: "Enig",
    },
];

let natureScore = 0;

const natureOptions = [
    {
        value: 1,
        label: "Uening",
    },
    {
        value: 2,
        label: "Litt Uening",
    },
    {
        value: 3,
        label: "Midt På",
    },
    {
        value: 4,
        label: "Litt Enig",
    },
    {
        value: 5,
        label: "Enig",
    },
];

let booksScore = 0;

const booksOptions = [
    {
        value: 1,
        label: "Uening",
    },
    {
        value: 2,
        label: "Litt Uening",
    },
    {
        value: 5,
        label: "Midt På",
    },
    {
        value: 4,
        label: "Litt Enig",
    },
    {
        value: 3,
        label: "Enig",
    },
];

let historyScore = 0;

const historyOptions = [
    {
        value: 3,
        label: "Uening",
    },
    {
        value: 5,
        label: "Litt Uening",
    },
    {
        value: 4,
        label: "Midt På",
    },
    {
        value: 2,
        label: "Litt Enig",
    },
    {
        value: 1,
        label: "Enig",
    },
];

let cookingScore = 0;

const cookingOptions = [
    {
        value: 1,
        label: "Uening",
    },
    {
        value: 2,
        label: "Litt Uening",
    },
    {
        value: 3,
        label: "Midt På",
    },
    {
        value: 4,
        label: "Litt Enig",
    },
    {
        value: 5,
        label: "Enig",
    },
];

let travelScore = 0;

const travelOptions = [
    {
        value: 1,
        label: "Uening",
    },
    {
        value: 2,
        label: "Litt Uening",
    },
    {
        value: 3,
        label: "Midt På",
    },
    {
        value: 4,
        label: "Litt Enig",
    },
    {
        value: 5,
        label: "Enig",
    },
];

let musicScore = 0;

const musicOptions = [
    {
        value: 1,
        label: "Uening",
    },
    {
        value: 2,
        label: " Litt Uening",
    },
    {
        value: 3,
        label: "Midt På",
    },
    {
        value: 4,
        label: "Litt Enig",
    },
    {
        value: 5,
        label: "Enig",
    },
];

let artScore = 0;

const artOptions = [
    {
        value: 1,
        label: "Uening",
    },
    {
        value: 2,
        label: "Litt Uening",
    },
    {
        value: 3,
        label: "Midt På",
    },
    {
        value: 5,
        label: "Litt Enig",
    },
    {
        value: 4,
        label: "Enig",
    },
];

let workoutScore = 0;

const workoutOptions = [
    {
        value: 1,
        label: "Uening",
    },
    {
        value: 2,
        label: "Litt Uening",
    },
    {
        value: 3,
        label: "Midt På",
    },
    {
        value: 4,
        label: "Litt Enig",
    },
    {
        value: 5,
        label: "Enig",
    },
];

// bytte bakgrunnsfarge når man velger mann, dame, annet eller vil ikke oppgi
let genderChoosen = false

function maleGender() {
  document.body.style.backgroundColor = "#1AA5FA";
  genderChoosen = true
}

function femaleGender() {
  document.body.style.backgroundColor = "#FF8FF5";
  genderChoosen = true
}

function otherGender() {
  document.body.style.backgroundColor = "#4DCA5E";
  genderChoosen = true
}

function secretGender() {
  document.body.style.backgroundColor = "#FFC433";
  genderChoosen = true
}

// Next buttons og Back Buttons
function nextBtn() {

  if (genderChoosen == true) { //passer på at et kjønn må være valgt for å gå videre
    document.getElementById('div1').style.visibility = 'hidden';
    document.getElementById('div2').style.visibility = 'visible';
  } else {
    alert('Du må velge et alternativ før du kan gå videre');
  }
}

function goBack(event) {
  event.preventDefault(); // Hindre standardoppførselen for skjemainnsending
  document.getElementById('div1').style.visibility = 'visible';
  document.getElementById('div2').style.visibility = 'hidden';
}

function nextBtn1() {
  
  if(nameChoosen == true) { //passer på at man ikke kan gå videre før man hvertfall har lagt til navn
    document.getElementById('div2').style.visibility = 'hidden';
    document.getElementById('div3').style.visibility = 'visible';
  } else {
    alert('Du må fylle brukeropplysningene før du kan gå videre')
  }
}

function goBack1(event) {
  event.preventDefault(); // Hindre standardoppførselen for skjemainnsending
  document.getElementById('div2').style.visibility = 'visible';
  document.getElementById('div3').style.visibility = 'hidden';
}

function nextBtn2(event) {
  event.preventDefault(); // Hindre standardoppførselen for skjemainnsending
  document.getElementById('div3').style.visibility = 'hidden';
  document.getElementById('div4').style.visibility = 'visible';
}


function goBack2(event) {
  event.preventDefault(); // Hindre standardoppførselen for skjemainnsending
  document.getElementById('div3').style.visibility = 'visible';
  document.getElementById('div4').style.visibility = 'hidden';
}

// Hinder for å kunne gå videre før du har svart på spørsmål


// Navn
let nameChoosen = false;
let selectedName = ""; // Oppretter en variabel 'selectedName' og initialiserer den som en tom streng.


  function handleNameChange(event) { // Definerer en funksjon kalt 'handleNameChange' som tar imot en hendelse (event) som parameter.
    selectedName = event.target.value; // Oppdaterer 'selectedName' med verdien fra hendelsesmålet (target).
    nameChoosen = true; //når man har lagt til navn så blir nameChoosen satt om 'true'
  }

// Høyde
let value = 170;

// Alder
let age = 18;
const minAge = 12;
const maxAge = 100;

//Måned 
let selectedMonth = ""; // Oppretter en variabel 'selectedMonth' og initialiserer den som en tom streng.


  function handleMonthChange(event) { // Definerer en funksjon kalt 'handleMonthChange' som tar imot en hendelse (event) som parameter.
    selectedMonth = event.target.value; // Oppdaterer 'selectedMonth' med verdien fra hendelsesmålet (target).
  }
</script>

<!--HTML-->
<main class="content">
  <h1 class="header1">MatchMetrics</h1>
  <!--Div for å velge kjønn-->
  <div id="div1">
    <h2 class="header2">Choose Your Gender</h2>
    <div class="genderBlock1">
      <div>
        <label for="checkbox" class="top-left">
          <div class="maleDiv">
            <img class="imgChoice" src={maleImg} />
          </div>
        </label>
        <input class="inputGender1" type="radio" id="maleCheckbox" name="checkbox" value="option1" on:click={maleGender}/>
        <label for="checkbox">Mann</label>
        <br/>
      </div>

      <div>
        <label for="checkbox" class="top-right">
          <div class="femaleDiv">
            <img class="imgChoice" src={femaleImg} />
          </div>
        </label>
        <input class="inputGender2" type="radio" id="femaleCheckbox" name="checkbox" value="option2" on:click={femaleGender}/>
        <label for="checkbox">Dame</label>
        <br/>
      </div>
    </div>

    <div class="genderBlock2">
      <div>
        <label for="checkbox" class="bottom-left">
          <div class="otherDiv">
            <img class="imgChoice" src={otherImg} />
          </div>
          </label>
        <input class="inputGender1" type="radio" id="otherCheckbox" name="checkbox" value="option3" on:click={otherGender}/>
        <label for="checkbox">Annet</label>
        <br/>
      </div>

      <div>
        <label for="checkbox" class="bottom-left">
          <div class="secretDiv">
            <img class="imgChoice" src={secretImg} />
          </div>
          </label>
        <input class="inputGender2" type="radio" id="secretCheckbox" name="checkbox" value="option4" on:click={secretGender}/>
        <label for="checkbox">Vil ikke oppgi</label>
        <br/>
      </div>
    </div>
    <button class="btn1" on:click={nextBtn}>Next</button> 
  </div>
  <!--Div for å legge til personopplysninger-->
  <div id="div2">
    <br>
    <h2 class="header2">Bruker opplysninger</h2>
    <br>

    <div>
      <label class="label">Navn:</label>
      <input type="text" on:change={handleNameChange}>
    </div>

    <div class="heightDiv">
      <input type="range" bind:value={value} max="200" min="140" />
      <span class="label">{value}cm</span>
    </div>

    <div>
      <label class="label">Alder: </label>
      <input type="number" bind:value={age} min={minAge} max={maxAge}>
    </div>

    <div class="monthDiv">
      <label class="label">Måned: </label>
      <select name="velgMåned" id="velgMåned" class="monthSelect" on:change={handleMonthChange}>
        <option value="Januar">Januar</option>
        <option value="Februar">Februar</option>
        <option value="Mars">Mars</option>
        <option value="April">April</option>
        <option value="Mai">Mai</option>
        <option value="Juni">Juni</option>
        <option value="Juli">Juli</option>
        <option value="August">August</option>
        <option value="September">September</option>
        <option value="Oktober">Oktober</option>
        <option value="November">November</option>
        <option value="Desember">Desember</option>
      </select>
    </div>
      <button on:click={goBack}>Go back</button>
      <br>
      <button on:click={nextBtn1}>Next</button>
      <br>
  </div>
  <!--Div for å svare på 10 spørsmål om preferanser-->  
  <div id="div3">
    
    <h2 class="header2">Spørsmålrunde</h2>
    <div class="spørsmålRunde1til10">
      <br>
      <Radio
        options = {gamingOptions}
        fontSize={16}
        legend="Synes du det er gøy å spille dataspill?"
        bind:userSelected={gamingScore}
      />
      <br>
    </div>
    <br>

    <div class="spørsmålRunde1til10">
      <br>
       <Radio
        options = {languageOptions}
        fontSize={16}
        legend="Er du interessert i å lære et nytt språk?"
        bind:userSelected={languageScore}
      />
      <br>
    </div>
    <br>

    <div class="spørsmålRunde1til10">
      <br>
      <Radio
        options = {natureOptions}
        fontSize={16}
        legend="Setter du pris på å tilbringe tid ute i naturen?"
        bind:userSelected={natureScore}
      />
      <br>
    </div>
    <br>

    <div class="spørsmålRunde1til10">
        <br>
        <Radio
        options = {booksOptions}
        fontSize={16}
        legend="Foretrekker du å lese bøker?"
        bind:userSelected={booksScore}
      />
      <br>
    </div>
    <br>

    <div class="spørsmålRunde1til10">
    <br>
    <Radio
        options = {historyOptions}
        fontSize={16}
        legend="Interesserer du deg for historie og kulturarv?"
        bind:userSelected={historyScore}
      />
      <br>
    </div>
    <br>

    <div class="spørsmålRunde1til10">
      <br>
      <Radio
        options = {cookingOptions}
        fontSize = {16}
        legend="Liker du å lage mat og prøve ut nye oppskrifter?"
        bind:userSelected={cookingScore}
      />
      <br>
    </div>
    <br>
   
    <div class="spørsmålRunde1til10">
      <br>
      <Radio
      options = {travelOptions}
      fontSize = {16}
      legend="Er du glad i å reise og oppleve nye steder?"
      bind:userSelected={travelScore}
    />
    <br>
    </div>
    <br>

    <div class="spørsmålRunde1til10">
      <br>
      <Radio
      options = {musicOptions}
      fontSize = {16}
      legend="Synes du det er gøy å spille musikkinstrumenter eller synge?"
      bind:userSelected={musicScore}
    />
    <br>
    </div>
    <br>
   
    <div class="spørsmålRunde1til10">
      <br>
      <Radio
      options = {artOptions}
      fontSize = {16}
      legend="Interesserer du deg for kunst og kreativitet?"
      bind:userSelected={artScore}
    />
    <br>
    </div>
    <br>
    <form>
      <div class="spørsmålRunde1til10">
        <br>
        <Radio
        options = {workoutOptions}
        fontSize = {16}
        legend="Er du opptatt av å trene og være i god form?"
        bind:userSelected={workoutScore}
        />
        <br>
        </div>
        <br>
        <button on:click={goBack1}>Go back</button>
        <br>
        <button on:click={nextBtn2}>Next</button>
      </form>
  </div>
  <!--Div for selve scoren-->    
  <div id=div4>
    <br>
    <button on:click={goBack2}>Go back</button>
    <br>
    <p class="userMessage"> <!--Her får brukeren sin personelige melding-->
      Hei {selectedName}, du er {value}cm høy. Du ble født i {selectedMonth}, og er {age} år gammel 
    </p>
    <br>
    <p class="totalScoreStart"> 
      På attraktivitets skalaen, er du:
    </p>
    <b>
      <p class="totalScore"> <!--Legger til alle verdiene, deler på 5 og ganger med 10. Slik får man en verdi satt som prosent.-->
        {(artScore + workoutScore + musicScore + travelScore + cookingScore + historyScore + booksScore + natureScore + languageScore + gamingScore)/5*10}% attraktiv 
      </p>
    </b>
    <br>
  </div>
</main>
