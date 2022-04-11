# toggleAudio
An on/off audio toggle for any app or website which persists state between page reloads.

______

## HTML

```html
<button type="button" class="audio">
  <span class="audio-off --active"></span>
  <span class="audio-on"></span>
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
  backface-visibility: hidden;
  pointer-events: none;
  transform: rotateY(180deg);
  transition: all 0.3s linear;
}

.audio-on {
  background-image: url('data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20lang%3D%22en-GB%22%20viewBox%3D%220%200%20768%20768%22%3E%3Ctitle%3EAudio%20Icon%3C%2Ftitle%3E%3Cdefs%3E%3Cstyle%3E%3C%21%5BCDATA%5Brect%7Bwidth%3A%20768px%3Bheight%3A%20768px%3Bfill%3A%20rgba%280%2C0%2C0%2C0%29%3B%7Dpath%7Bfill%3Argb%280%2C0%2C0%29%3B%7D%5D%5D%3E%3C%2Fstyle%3E%3C%2Fdefs%3E%3Crect%20%2F%3E%3Cpath%20d%3D%22m%20470.57734%2C741.2876%20c%20-7.71475%2C-2.83606%20-11.18777%2C-4.89195%20-18.82603%2C-11.1443%20-2.39807%2C-1.96296%20-43.79807%2C-42.82236%20-92%2C-90.79868%20l%20-87.63988%2C-87.22967%20-69.5%2C-0.27033%20-69.5%2C-0.27033%20-5.86156%2C-2.87813%20c%20-8.69995%2C-4.27183%20-19.79481%2C-15.53374%20-22.7789%2C-23.12187%20l%20-2.35954%2C-6%20v%20-138%20c%200%2C-131.11094%200.0914%2C-138.27456%201.83191%2C-143.5%204.32786%2C-12.99369%2011.24782%2C-19.42452%2026.95392%2C-25.04871%20l%208.21417%2C-2.94141%2066.47695%2C-0.005%2066.47696%2C-0.005%2090.52304%2C-90.2663%20c%2095.08695%2C-94.817141%2094.44763%2C-94.232081%20108.57699%2C-99.360761%205.97505%2C-2.16883%208.09265%2C-2.37282%2024.63202%2C-2.37282%2016.6968%2C0%2018.4388%2C0.17171%2022.54471%2C2.2223%202.44735%2C1.22227%205.35455%2C3.49301%206.46044%2C5.04609%204.95602%2C6.96009%204.73518%2C-9.62279%204.77327%2C358.416511%200.0249%2C240.3642%20-0.28452%2C345.03405%20-1.02571%2C347%20-0.58374%2C1.54831%20-2.49624%2C4.31599%20-4.25%2C6.15042%20-5.99091%2C6.26644%20-7.33614%2C6.60106%20-27.68867%2C6.88738%20-18.04936%2C0.25392%20-18.68352%2C0.19279%20-26.03409%2C-2.50939%20z%20M%20600.3594%2C549.70163%20c%20-5.93421%2C-2.20326%20-10.33035%2C-6.14828%20-13.14459%2C-11.79572%20-5.39826%2C-10.83291%20-3.08865%2C-16.71172%2011.68289%2C-29.73724%2040.36186%2C-35.59104%2059.79177%2C-80.99428%2057.38451%2C-134.09438%20-2.23918%2C-49.39231%20-20.58907%2C-87.5315%20-58.17881%2C-120.9213%20-12.02899%2C-10.68498%20-14.65864%2C-14.55603%20-14.65864%2C-21.5787%200%2C-11.90939%2013.04063%2C-24.61151%2023.75911%2C-23.14238%206.3213%2C0.86643%209.17103%2C2.59906%2020.69094%2C12.58013%2039.46289%2C34.19135%2062.29527%2C76.84757%2069.88539%2C130.56225%201.92863%2C13.64871%201.60428%2C48.41306%20-0.58777%2C63%20-5.75409%2C38.29032%20-20.26693%2C71.24453%20-44.36153%2C100.73141%20-8.21433%2C10.05267%20-30.26582%2C31.0853%20-34.9257%2C33.312%20-4.92676%2C2.35423%20-12.81232%2C2.84138%20-17.5458%2C1.08393%20z%22%20%2F%3E%3C%2Fsvg%3E');
  opacity: 1;
}

.audio-off {
  background-image: url('data:image/svg+xml,%3Csvg%20xmlns%3D%22http%3A%2F%2Fwww.w3.org%2F2000%2Fsvg%22%20lang%3D%22en-GB%22%20viewBox%3D%220%200%20768%20768%22%3E%3Ctitle%3EMute%20Icon%3C%2Ftitle%3E%3Cdefs%3E%3Cstyle%3E%3C%21%5BCDATA%5Brect%7Bwidth%3A768px%3Bheight%3A768px%3Bfill%3A%20rgba%280%2C0%2C0%2C0%29%3B%7Dpath%7Bfill%3Argb%280%2C0%2C0%29%3B%7D%5D%5D%3E%3C%2Fstyle%3E%3C%2Fdefs%3E%3Crect%20%2F%3E%3Cpath%20d%3D%22m%20514.64857%2C746.41567%20c%20-7.23403%2C-2.33279%20-15.45533%2C-6.93789%20-23.16845%2C-12.97761%20-3.14331%2C-2.46136%20-44.6698%2C-43.2877%20-92.2811%2C-90.7252%20l%20-86.56599%2C-86.25%20h%20-67.29941%20c%20-47.65888%2C0%20-68.66895%2C-0.33827%20-71.99223%2C-1.1591%20-10.38521%2C-2.56509%20-23.41546%2C-14.17469%20-26.78831%2C-23.86766%20-1.83792%2C-5.28188%20-1.90451%2C-10.42057%20-1.90451%2C-146.97324%20v%20-141.5%20l%202.89186%2C-6.2618%20c%203.2572%2C-7.05289%208.40912%2C-12.23957%2015.39549%2C-15.4994%202.59196%2C-1.20939%204.91571%2C-2.33594%205.16389%2C-2.50342%200.24818%2C-0.16749%20-20.72025%2C-21.55146%20-46.5965%2C-47.51995%20-30.937231%2C-31.04751%20-47.695971%2C-48.58514%20-48.940811%2C-51.21543%20-2.8746%2C-6.0739%20-2.65973%2C-18.56296%200.42151%2C-24.500003%203.16419%2C-6.09687%208.64277%2C-11.63242%2014.66456%2C-14.81707%204.20155%2C-2.222%206.27753%2C-2.64426%2013.000001%2C-2.64426%206.74443%2C0%208.78473%2C0.4178%2013%2C2.6621%203.65377%2C1.94535%2022.6348%2C20.316143%2070.49714%2C68.230673%20l%2065.49713%2C65.56856%20h%2031.48475%2031.48474%20l%2089.51812%2C-89.32184%20c%2095.1437%2C-94.935093%2095.62848%2C-95.37672%20110.05601%2C-100.257898%206.53075%2C-2.209511%208.73786%2C-2.420265%2025.34601%2C-2.420265%2016.8774%2C0%2018.51482%2C0.162627%2022.65421%2C2.25%203.53889%2C1.784556%205.02413%2C3.387752%207.17979%2C7.75%20l%202.71791%2C5.5%200.0321%2C248.502843%200.0321%2C248.50284%2065.8925%2C65.88683%20c%2046.80175%2C46.79773%2066.57555%2C67.22255%2068.25005%2C70.49716%203.3554%2C6.56182%203.366%2C18.66705%200.022%2C25.11033%20-3.1642%2C6.09686%20-8.6428%2C11.63242%20-14.6646%2C14.81707%20-6.9012%2C3.64972%20-18.7705%2C3.80022%20-25.50001%2C0.32333%20-3.02072%2C-1.5607%20-19.21059%2C-17.00386%20-49.25%2C-46.97853%20l%20-44.75005%2C-44.65354%20v%2056.77796%20c%200%2C62.53583%200.17139%2C60.72201%20-6.27221%2C66.37956%20-4.82954%2C4.24039%20-10.80361%2C5.3457%20-28.52701%2C5.27798%20-11.68868%2C-0.0447%20-15.93014%2C-0.4526%20-20.70078%2C-1.99102%20z%22%20%2F%3E%3C%2Fsvg%3E');
  opacity: 0.2;
}

.audio-off.\--active,
.audio-on.\--active {
  transform: rotateY(360deg);
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

