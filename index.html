<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Журнал посещаемости</title>
  <style>
    :root {
      --bg: #f4f7fb;
      --card: #ffffff;
      --accent: #4f6df5;
      --radius: 12px;
      --maxw: 1200px;
      --ff-sans: Arial, sans-serif;
    }
    * { box-sizing: border-box; }
    html, body {
      margin: 0;
      padding: 0;
      height: 100%;
      width: 100%;
      font-family: var(--ff-sans);
      background: var(--bg);
      color: #333;
      display: flex;
      flex-direction: column;
    }
    header {
      text-align: center;
      padding: 10px;
      background: var(--accent);
      color: #fff;
    }
    header button {
      background: #fff;
      color: var(--accent);
      border: none;
      border-radius: var(--radius);
      padding: 6px 12px;
      margin-top: 8px;
      cursor: pointer;
    }
    #monthButtons {
      margin: 10px 0;
      text-align: center;
    }
    #monthButtons button {
      background: var(--accent);
      color: #fff;
      border: none;
      border-radius: var(--radius);
      padding: 6px 12px;
      margin: 3px;
      cursor: pointer;
    }
    #monthButtons button:hover { background: #3c52c7; }
    table {
      border-collapse: collapse;
      width: 100%;
      background: var(--card);
      overflow-x: auto;
      display: block;
      flex: 1;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 6px;
      text-align: center;
      white-space: nowrap;
    }
    th {
      background: var(--accent);
      color: #fff;
    }
    td button {
      width: 30px;
      height: 25px;
      margin: 1px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
    }
    .present { background: #5cd65c; color: #fff; }
    .absent { background: #ff6666; color: #fff; }
    .excused { background: #ffd633; }
  </style>
</head>
<body>
  <header>
    <h1>Журнал посещаемости</h1>
    <button onclick="openFullscreen()">Во весь экран</button>
  </header>

  <div id="monthButtons"></div>
  <table>
    <thead>
      <tr>
        <th>Фамилия, Имя</th>
      </tr>
    </thead>
    <tbody id="tableBody"></tbody>
  </table>

  <script>
    // Полноэкранный режим
    function openFullscreen() {
      let elem = document.documentElement;
      if (elem.requestFullscreen) {
        elem.requestFullscreen();
      } else if (elem.webkitRequestFullscreen) { /* Safari */
        elem.webkitRequestFullscreen();
      } else if (elem.msRequestFullscreen) { /* IE11 */
        elem.msRequestFullscreen();
      }
    }

    const students = [
      "Акпаралиев Диёрбек","Нематуллаев Омурбек","Салибаев Баяман","Халмирзаев Азиз",
      "Джумабеков Элмирбек","Токтобаев Азиз","Ивраимжанов Сардор","Гайбуллажанов Салох",
      "Асанбаев Кахрамон","Маматазимов Самат","Казакбаев Азат","Раимбердиев Максат",
      "Таштанбеков Илгиз","Махамаджанов Музаффар","Гизатулина Алина","Мамбеткулова Асема",
      "Абдиллабекова Асема","Суйуркулова Аяна","Нематжанова Тахмина","Тохтасинова Райхона",
      "Умарова Зульфия","Абдисаламова Нилуфар","Салибаева Аксаамай","Муллажанова Рухшона",
      "Наркозиева Назбийке","Жоробаева Мадина","Шахноза"
    ];

    const months = ["Октябрь","Ноябрь","Декабрь","Январь","Февраль","Март","Апрель","Май"];
    let currentMonth = 0;
    const journal = JSON.parse(localStorage.getItem('journalMonths')) || {};

    const tableBody = document.getElementById('tableBody');
    const monthButtonsDiv = document.getElementById('monthButtons');

    function renderMonthButtons(){
      monthButtonsDiv.innerHTML = "";
      months.forEach((m,i)=>{
        const btn = document.createElement('button');
        btn.textContent = m;
        btn.onclick = ()=>{
          currentMonth=i;
          renderTable();
        };
        monthButtonsDiv.appendChild(btn);
      });
    }

    function getWeekdays(monthName){
      const monthIdx = months.indexOf(monthName);
      const monthNums = [10,11,12,1,2,3,4,5];
      const monthNum = monthNums[monthIdx];
      const year = monthNum >= 10 ? 2025 : 2026;
      let days = [];
      const lastDay = new Date(year, monthNum, 0).getDate();
      for(let d=1; d<=lastDay; d++){
        const wd = new Date(year, monthNum-1, d).getDay();
        if(wd>=1 && wd<=5){
          days.push(d + ' ' + monthName.slice(0,3));
        }
      }
      return days;
    }

    function renderTable(){
      tableBody.innerHTML='';
      const monthName = months[currentMonth];
      const days = getWeekdays(monthName);

      const headerRow = document.querySelector('thead tr');
      headerRow.innerHTML = '<th>Фамилия, Имя</th>';
      days.forEach(d=>{
        headerRow.innerHTML += '<th>'+d+'</th>';
      });

      if(!journal[monthName]) journal[monthName]={};

      students.forEach(s=>{
        const tr = document.createElement('tr');
        tr.innerHTML = '<td>'+s+'</td>';
        days.forEach(day=>{
          const td = document.createElement('td');
          for(let p=1;p<=3;p++){
            const btn = document.createElement('button');
            btn.onclick = ()=>toggle(s, day, p, btn);
            td.appendChild(btn);
            const val = journal[monthName][s]?.[day]?.[p]||'';
            setButton(btn,val);
          }
          tr.appendChild(td);
        });
        tableBody.appendChild(tr);
      });
    }

    function toggle(student, day, pair, btn){
      const states=['','+','-','O'];
      let idx = states.indexOf(btn.textContent);
      idx=(idx+1)%states.length;
      const val = states[idx];
      setButton(btn,val);

      const monthName = months[currentMonth];
      if(!journal[monthName][student]) journal[monthName][student]={};
      if(!journal[monthName][student][day]) journal[monthName][student][day]={};
      journal[monthName][student][day][pair]=val;
      localStorage.setItem('journalMonths',JSON.stringify(journal));
    }

    function setButton(btn,val){
      btn.textContent=val;
      btn.className='';
      if(val==='+') btn.classList.add('present');
      if(val==='-') btn.classList.add('absent');
      if(val==='O') btn.classList.add('excused');
    }

    renderMonthButtons();
    renderTable();
  </script>
</body>
</html>
