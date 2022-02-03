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
## Event Listeners
```javascript
// Event Listeners
playBtn.addEventListener("click", togglePlay);
video.addEventListener("click", togglePlay);
video.addEventListener("timeupdate", updateProgress);
video.addEventListener("canplay", updateProgress);
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
// Appended togglePlay
const togglePlay = () => {
  if (video.paused) {
    video.play();
    playBtn.classList.replace("fa-play", "fa-pause");
    playBtn.setAttribute("title", "Pause");
  } else {
    video.pause();
    playBtn.classList.replace("fa-pause", "fa-play");
    playBtn.setAttribute("title", "Play");
  }
};
// Event Listeners
// Event Listeners
playBtn.addEventListener("click", togglePlay);
video.addEventListener("click", togglePlay);
```

## Show Play Icon
```javascript
const showPlayIcon = () => {
  playBtn.classList.replace("fa-pause", "fa-play");
  playBtn.setAttribute("title", "Play");
};
```

## Set Progress Bar / Time and Duration 
```javascript
// Calculate display time format
const displayTime = (time) => {
  const minutes = Math.floor(time / 60);
  let seconds = Math.floor(time % 60);
  seconds = seconds > 9 ? seconds : `0${seconds}`;
  return `${minutes}:${seconds}`;
};

// Update progress bar as video plays
function updateProgress() {
  progressBar.style.width = `${Math.floor(
    (video.currentTime / video.duration) * 100
  )}%`;
  currentTime.textContent = `${displayTime(video.currentTime)} /`;
  duration.textContent = `${displayTime(video.duration)}`;
}
// Event Listeners
video.addEventListener("timeupdate", updateProgress);
video.addEventListener("canplay", updateProgress);
```

## Seek within the video
```javascript
// Click to seek within the video
const setProgress = (e) => {
  const newTime = e.offsetX / progressRange.offsetWidth;
  progressBar.style.width = `${newTime * 100}%`;
  video.currentTime = newTime * video.duration;
};
```

