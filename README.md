# Binary Buddies ~ Mole Mayhem
By: Helina Tadesse (tadesseh@emmanuel.edu), Katie Bartash (bartashk@emmanuel.edu) May 1st , 2025
# Getting Started
This game is Mole Mayhem Is a fast paced reaction time game. It is our a take on whack-O-mole. You will be timed and must hit as many moles as you can!

# Project Overview        

How to play:

Playing Mole Mayhem is simple. Martin and his friends having plotting for you land. DON’T let them take over your beautiful lawn. You need to hit 10 moles as fast as you can. You will be timed! 
Once you hit 10 the game will end display your score as well as previous score. 


# Favorite Code and Its Challeneges


Katie:

The hardest part of the code was

The code I am most proud of is


Helina: 

The code I am most proud of is, My favorite part of the code is setting up the background or the “lawn”. And also when Katie added the timer and score count it made our theme come togther.
```
if(gameStart === true) {
    imageMode(CORNER);
    image(Bgimg, 0, 0, width, height, 10, 0, Bgimg.width, Bgimg.height, COVER);

  draw(){
    let visibleMilliseconds = floor(this.milliseconds / 10);
    fill('pink');
    text(nf(this.minutes, 2) + ":" + nf(this.seconds, 2) + ":" + nf(visibleMilliseconds, 2), (width / 2) - 75, 25);
  }
}
```

The hardest part of our code for me, was getting the sound to work in the right spot. I wanted the sound to start and stop where I wanted to without interferring with the other code.
```
function preload() {
  Bgimg = loadImage('background.png');
  soundFormats("mp3"); //Will format the audio
  audio = loadSound("best-game-console.mp3");
}

function setup() {
  createCanvas(400, 400);
  background(220);
  clocks.push(new Clock());
  moles.push(new Mole());
  scoreboard = new Scoreboard();
  audio.play(); //Starts the background music
  audio.loop(); //Will keep music playing
  noCursor(); 
}

function draw() {
  background(220);
  if(keyCode === ENTER) {
    gameStart = true;
    gameEnd = false;
    userStartAudio();
  }
```

# What We Did Differently
We used state in our previous game,  however, this time around we had a better understanding of it on what we could make it do. 

We did find a way to incorporate classes from our unit object oriented programming for our mole.
```
class Clock {
  constructor () {
    this.lastMillis = 0;
    this.milliseconds = 0;
    this.seconds = 0;
    this.minutes = 0;
    this.running = true;
  }
  update() {
    let currentMillis = millis();
    let timeSince = currentMillis - this.lastMillis;
    this.milliseconds += timeSince;

    if(this.milliseconds >= 1000){
      this.seconds += 1;
      this.milliseconds -= 1000;
    }
    if(this.seconds === 60){
      this.minutes += 1;
      this.seconds = 0;
    }
    this.lastMillis = currentMillis;
  }
  totalTime() {
    return this.milliseconds + this.seconds * 1000 + this.minutes * 60000;
  }
  
  draw(){
    let visibleMilliseconds = floor(this.milliseconds / 10);
    fill('pink');
    text(nf(this.minutes, 2) + ":" + nf(this.seconds, 2) + ":" + nf(visibleMilliseconds, 2), (width / 2) - 75, 25);
  }
}
```

We also used map and filter to keep score and label the scores from highest to lowest.
```

```

# Credits
Shoutout to Krzysztof Szymanski from Pixabay for the background music. Their only requirement was to give them credit.

Our game background is from https://www.vecteezy.com/vector-art/14572097-background-of-green-grass-field-cartoon-drawing

p5.js Reference
https://p5js.org/reference/

JS Tutorial - w3schools
https://www.w3schools.com/js/default.asp
