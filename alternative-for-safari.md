# Alternative `toggleAudio` for Safari
It appears that older versions of Safari don't support the CSS `backface-visibility` property.
Below is an alternative cross-browser version of `toggleAudio` which supports Safari.

______

## HTML

```html
<button type="button" class="audio">

  <svg xmlns="http://www.w3.org/2000/svg"
       lang="en-GB"
       class="audio-off --active"
       viewBox="0 0 768 768">
  
    <title>Mute Icon</title>
  
    <defs>
  
      <style><![CDATA[
  
        path {
          fill: rgb(0, 0, 0);
        }
         
      ]]></style>
    
    </defs>
  
    <path d="m 514.64857,746.41567 c -7.23403,-2.33279 -15.45533,-6.93789 -23.16845,-12.97761 -3.14331,-2.46136 -44.6698,-43.2877 -92.2811,-90.7252 l -86.56599,-86.25 h -67.29941 c -47.65888,0 -68.66895,-0.33827 -71.99223,-1.1591 -10.38521,-2.56509 -23.41546,-14.17469 -26.78831,-23.86766 -1.83792,-5.28188 -1.90451,-10.42057 -1.90451,-146.97324 v -141.5 l 2.89186,-6.2618 c 3.2572,-7.05289 8.40912,-12.23957 15.39549,-15.4994 2.59196,-1.20939 4.91571,-2.33594 5.16389,-2.50342 0.24818,-0.16749 -20.72025,-21.55146 -46.5965,-47.51995 -30.937231,-31.04751 -47.695971,-48.58514 -48.940811,-51.21543 -2.8746,-6.0739 -2.65973,-18.56296 0.42151,-24.500003 3.16419,-6.09687 8.64277,-11.63242 14.66456,-14.81707 4.20155,-2.222 6.27753,-2.64426 13.000001,-2.64426 6.74443,0 8.78473,0.4178 13,2.6621 3.65377,1.94535 22.6348,20.316143 70.49714,68.230673 l 65.49713,65.56856 h 31.48475 31.48474 l 89.51812,-89.32184 c 95.1437,-94.935093 95.62848,-95.37672 110.05601,-100.257898 6.53075,-2.209511 8.73786,-2.420265 25.34601,-2.420265 16.8774,0 18.51482,0.162627 22.65421,2.25 3.53889,1.784556 5.02413,3.387752 7.17979,7.75 l 2.71791,5.5 0.0321,248.502843 0.0321,248.50284 65.8925,65.88683 c 46.80175,46.79773 66.57555,67.22255 68.25005,70.49716 3.3554,6.56182 3.366,18.66705 0.022,25.11033 -3.1642,6.09686 -8.6428,11.63242 -14.6646,14.81707 -6.9012,3.64972 -18.7705,3.80022 -25.50001,0.32333 -3.02072,-1.5607 -19.21059,-17.00386 -49.25,-46.97853 l -44.75005,-44.65354 v 56.77796 c 0,62.53583 0.17139,60.72201 -6.27221,66.37956 -4.82954,4.24039 -10.80361,5.3457 -28.52701,5.27798 -11.68868,-0.0447 -15.93014,-0.4526 -20.70078,-1.99102 z" />
  
  </svg>

  <svg xmlns="http://www.w3.org/2000/svg"
       lang="en-GB"
       class="audio-on"
       viewBox="0 0 768 768">
  
    <title>Audio Icon</title>
    
    <defs>
      
      <style><![CDATA[
  
        path {
          fill:rgb(0, 0, 0);
        }
      ]]></style>
  
    </defs>
  
    <path d="m 470.57734,741.2876 c -7.71475,-2.83606 -11.18777,-4.89195 -18.82603,-11.1443 -2.39807,-1.96296 -43.79807,-42.82236 -92,-90.79868 l -87.63988,-87.22967 -69.5,-0.27033 -69.5,-0.27033 -5.86156,-2.87813 c -8.69995,-4.27183 -19.79481,-15.53374 -22.7789,-23.12187 l -2.35954,-6 v -138 c 0,-131.11094 0.0914,-138.27456 1.83191,-143.5 4.32786,-12.99369 11.24782,-19.42452 26.95392,-25.04871 l 8.21417,-2.94141 66.47695,-0.005 66.47696,-0.005 90.52304,-90.2663 c 95.08695,-94.817141 94.44763,-94.232081 108.57699,-99.360761 5.97505,-2.16883 8.09265,-2.37282 24.63202,-2.37282 16.6968,0 18.4388,0.17171 22.54471,2.2223 2.44735,1.22227 5.35455,3.49301 6.46044,5.04609 4.95602,6.96009 4.73518,-9.62279 4.77327,358.416511 0.0249,240.3642 -0.28452,345.03405 -1.02571,347 -0.58374,1.54831 -2.49624,4.31599 -4.25,6.15042 -5.99091,6.26644 -7.33614,6.60106 -27.68867,6.88738 -18.04936,0.25392 -18.68352,0.19279 -26.03409,-2.50939 z M 600.3594,549.70163 c -5.93421,-2.20326 -10.33035,-6.14828 -13.14459,-11.79572 -5.39826,-10.83291 -3.08865,-16.71172 11.68289,-29.73724 40.36186,-35.59104 59.79177,-80.99428 57.38451,-134.09438 -2.23918,-49.39231 -20.58907,-87.5315 -58.17881,-120.9213 -12.02899,-10.68498 -14.65864,-14.55603 -14.65864,-21.5787 0,-11.90939 13.04063,-24.61151 23.75911,-23.14238 6.3213,0.86643 9.17103,2.59906 20.69094,12.58013 39.46289,34.19135 62.29527,76.84757 69.88539,130.56225 1.92863,13.64871 1.60428,48.41306 -0.58777,63 -5.75409,38.29032 -20.26693,71.24453 -44.36153,100.73141 -8.21433,10.05267 -30.26582,31.0853 -34.9257,33.312 -4.92676,2.35423 -12.81232,2.84138 -17.5458,1.08393 z" />
  
  </svg>

</button>

```

______

## CSS

```css

.audio {
  position: absolute;
  top: 6px;
  right: 6px;
  width: 36px;
  height: 36px;
  background-color: rgba(0, 0, 0, 0);
  border: none;
  cursor: pointer;
}

.audio-on,
.audio-off {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0;
  pointer-events: none;
  transform: rotateY(180deg);
  transition: transform 0.3s linear, opacity 0s linear 0.15s;
}

.audio-off.\--active {
  opacity: 0.2;
  transform: rotateY(360deg);
}

.audio-on.\--active {
  opacity: 1;
  transform: translateX(1px) rotateY(360deg);
}

```

______

## JavaScript

```javascript
let audioIcon;


const conditionalPlay = (audioFile) => {

  if (JSON.parse(localStorage.getItem('appSettings')).audio === true) {

    audioFile.play();
  }
}


const speakText = (announcement, lang = 'en-GB', volume = 1, pitch = 0.95, rate = 0.88) => {

  const vocalText = new SpeechSynthesisUtterance();
  vocalText.pitch = pitch;
  vocalText.rate = rate;
  vocalText.volume = volume;
  vocalText.lang = lang;
  vocalText.text = announcement;
  window.speechSynthesis.speak(vocalText);
}


const toggleAudio = (e) => {

  e.target.blur();

  const audioOn = e.target.getElementsByClassName('audio-on')[0];
  const audioOff = e.target.getElementsByClassName('audio-off')[0];
  
  audioOn.classList.toggle('--active');
  audioOff.classList.toggle('--active');


  let appSettings = JSON.parse(localStorage.getItem('appSettings'));
    
  if (audioOn.classList.contains('--active')) {
  
    appSettings.audio = true;
    localStorage.setItem('wordis3hSettings', JSON.stringify(appSettings));
    
    if (e.isTrusted === true) {

      speakText('Audio on.');
    }
  }

  else {

    appSettings.audio = false;
    localStorage.setItem('appSettings', JSON.stringify(appSettings));
  }
}


const initialiseAudio = () => {

  audioIcon = document.querySelector('.audio');

  if (localStorage.getItem('appSettings') === null) {

    localStorage.setItem('appSettings', '{"audio": false}');
  }

  else if (JSON.parse(localStorage.getItem('appSettings')).audio === true) {

    audioIcon.click();
  }
}


audioIcon.addEventListener('click', toggleAudio, false);
window.addEventListener('load', initialiseAudio);

```
