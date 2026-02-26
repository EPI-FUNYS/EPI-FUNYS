<!DOCTYPE html>
<html>
<head>
    <title>Song Badness Index</title>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        body {
            margin: 0;
            font-family: 'Segoe UI', sans-serif;
            background: linear-gradient(135deg, #141e30, #243b55);
            color: white;
            text-align: center;
        }

        h1 { margin-top: 30px; font-size: 2.5em; }

        .container { max-width: 1000px; margin: auto; padding: 20px; }

        input { padding: 12px; margin: 5px; border-radius: 8px; border: none; font-size: 16px; }
        input[type=number] { width: 100px; }

        button {
            padding: 12px 18px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            margin: 5px;
            background: #00c6ff;
            color: black;
            font-weight: bold;
            transition: 0.3s;
        }
        button:hover { transform: scale(1.05); background: #00f2fe; }

        canvas { margin-top: 40px; }

        .ranking {
            margin-top: 40px;
            text-align: left;
            background: rgba(255,255,255,0.05);
            padding: 20px;
            border-radius: 10px;
        }

        .song-item { padding: 8px; border-bottom: 1px solid rgba(255,255,255,0.1); }
    </style>
</head>
<body>

<h1>🎵 Song Badness Index (0–25)</h1>

<div class="container">
    <input type="text" id="songInput" placeholder="Song name">
    <input type="text" id="artistInput" placeholder="Artist">
    <input type="number" id="scoreInput" min="0" max="25" placeholder="0-25">
    <button id="addBtn">Rate Song</button>
    <button id="resetBtn">Reset</button>

    <canvas id="myChart"></canvas>

    <div class="ranking">
        <h3>🔥 Worst → Least Bad</h3>
        <div id="rankingList"></div>
    </div>
</div>

<script>
window.addEventListener('load', function(){

    const STORAGE_KEY = 'songsData';
    const ctx = document.getElementById('myChart').getContext('2d');
    let songs = [];

    // Load safely from localStorage
    const stored = localStorage.getItem(STORAGE_KEY);
    if(stored){
        try {
            const parsed = JSON.parse(stored);
            if(Array.isArray(parsed)) songs = parsed;
        } catch(e){ songs = []; }
    }

    const chart = new Chart(ctx, {
        type: 'bar',
        data: { labels: [], datasets: [{ data: [], backgroundColor: [], borderRadius: 6, barThickness: 25 }] },
        options: {
            indexAxis: 'y',
            animation: { duration: 800 },
            scales: {
                x: { beginAtZero: true, max:25, grid: { color:"rgba(255,255,255,0.1)" }, ticks:{color:"white"} },
                y: { grid:{display:false}, ticks:{color:"white", autoSkip:false} }
            },
            plugins:{
                legend:{display:false},
                tooltip:{
                    callbacks:{ label: ctx=> `${songs[ctx.dataIndex].score}/25 — ${songs[ctx.dataIndex].artist}` }
                }
            }
        }
    });

    function saveSongs(){ localStorage.setItem(STORAGE_KEY, JSON.stringify(songs)); }

    function getGradientColor(score,index){
        if(index===0) return "#ff1a1a";
        if(score<=8) return "#66ff99";
        if(score<=15) return "#ffd11a";
        if(score<20) return "#ff944d";
        return "#ff4d4d";
    }

    function updateChart(){
        chart.data.labels = songs.map(s => s.name.length>25 ? s.name.substring(0,25)+'...' : s.name);
        chart.data.datasets[0].data = songs.map(s=>s.score);
        chart.data.datasets[0].backgroundColor = songs.map((s,i)=>getGradientColor(s.score,i));
        chart.update();
    }

    function updateRanking(){
        const list = document.getElementById('rankingList');
        list.innerHTML = '';
        songs.forEach((s,i)=>{
            const div = document.createElement('div');
            div.className='song-item';
            div.innerHTML = i===0
                ? `👑 #1 WORST — ${s.name} by ${s.artist} — ${s.score}/25`
                : `#${i+1} — ${s.name} by ${s.artist} — ${s.score}/25`;
            list.appendChild(div);
        });
    }

    function addSong(){
        const name = document.getElementById('songInput').value.trim();
        const artist = document.getElementById('artistInput').value.trim();
        const score = parseInt(document.getElementById('scoreInput').value);
        if(!name || !artist || isNaN(score) || score<0 || score>25){
            alert('Enter song name, artist, and score (0–25).'); return;
        }

        songs.push({name,artist,score});
        songs.sort((a,b)=>b.score - a.score);
        saveSongs();
        updateChart();
        updateRanking();

        document.getElementById('songInput').value='';
        document.getElementById('artistInput').value='';
        document.getElementById('scoreInput').value='';
    }

    function resetAll(){
        if(confirm('Are you sure you want to reset all songs?')){
            songs=[];
            localStorage.removeItem(STORAGE_KEY);
            updateChart();
            updateRanking();
        }
    }

    document.getElementById('addBtn').addEventListener('click', addSong);
    document.getElementById('resetBtn').addEventListener('click', resetAll);

    // Initial render
    if(songs.length>0){ songs.sort((a,b)=>b.score-b.score); updateChart(); updateRanking(); }

});
</script>

</body>
</html>
