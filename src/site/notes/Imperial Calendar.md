---
{"dg-publish":true,"permalink":"/imperial-calendar/","dg-note-properties":{}}
---

Calendar used by the [[Database/0 - Factions & Subfactions/Jinzhou Empire/Jinzhou Empire\|Jinzhou Empire]], on [[Database/2 - Locations/2.1 Systems/0202 Jinzhou 津州/Jinzhou 津州\|Jinzhou 津州]], [[Database/2 - Locations/2.1 Systems/0300 Kiran 岐然/0300 Kiran 岐然\|0300 Kiran 岐然]] [[Database/2 - Locations/2.1 Systems/0201 Taiyuan 太原/0201 Taiyuan 太原\|0201 Taiyuan 太原]], etc.

Starting at 0 on 2500 of the SWN calendar.

| 1   | Xīng rì  星日      | Star's Day    |
| --- | ---------------- | ------------- |
| 2   | Gēngzuò rì  耕作日  | Tilling Day   |
| 3   | Jí rì  集日        | Market Day    |
| 4   | Xiūxí rì  休息日    | Resting Day   |
| 5   | Jīngshén rì  精神日 | Mind's Day    |
| 6   | Yún zhī rì  云之日  | Day of Clouds |
| 7   | Zhì àn rì  至暗日   | Darkest Day   |
| 8   | Huángdì rì  皇帝日  | Emperor's Day |
| 9   | Zhāijiè rì  斋戒日  | Fasting Day   |
| 10  | Jíxiáng rì  吉祥日  | Boon Day      |

```html
<div id="dateconv">
  <label>Year: <input type="number" id="yr" value="3320"></label><br>
  <label>Month: <input type="number" id="mo" value="4"></label><br>
  <label>Day: <input type="number" id="dy" value="20"></label><br>
  <button onclick="convert()">Convert</button>
  <p id="result"></p>
</div>
<script>
function convert(){
  const Dw=10, Wm=3, DPM=Dw*Wm, DPY=DPM*10; // original calendar
  const Dw2=6, Wm2=3, DPM2=Dw2*Wm2, DPY2=DPM2*12; // alt calendar
  const epochYear=2500;
  const y=+document.getElementById('yr').value;
  const m=+document.getElementById('mo').value;
  const d=+document.getElementById('dy').value;
  const abs=(y-1)*DPY+(m-1)*DPM+(d-1);
  const offset=(epochYear-1)*DPY;
  const since=abs-offset;
  const altY=Math.floor(since/DPY2)+1;
  const rem=((since%DPY2)+DPY2)%DPY2;
  const altM=Math.floor(rem/DPM2)+1;
  const altD=(rem%DPM2)+1;
  document.getElementById('result').innerText=`Alt calendar: Year ${altY}, Month ${altM}, Day ${altD}`;
}
</script>
```
