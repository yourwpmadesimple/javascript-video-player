# Javascript Video Player

## Get Elements
```javascript
// Get Elements
const video = document.querySelector('video')
const progressRange = document.querySelector('.progress-range')
const progressBar = document.querySelector('.progress-bar')
const playBtn = document.getElementById('play-btn')
const volumeIcon = document.getElementById('volume-icon')
const volumeRange = document.querySelector('.volume-range')
const volumeBar = document.querySelector('.volume-bar')
const currentTime = document.querySelector('.time-elapsed')
const duration = document.querySelector('.time-duration')
const fullscreenBtn = document.querySelector('.fullscreen')
```

## Toggle Play / Pause action
```javascript
// Play & Pause ----------------------------//
const togglePlay = () => {
  if (video.paused) {
    video.play();
  } else {
    video.pause();
  }
};
```

## Event Listeners
```javascript
// Event Listeners
playBtn.addEventListener("click", togglePlay);
video.addEventListener("click", togglePlay);
```