<html lang="en">    
<head>    
<meta charset="UTF-8">    
<title>EDUFINITY - Class 12 Physics</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Poppins:wght@400;600&family=Exo+2:wght@500;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

<script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-database.js"></script>

<style>    
body { margin: 0; font-family: 'Poppins', sans-serif; color: white; overflow-x: hidden; background-color: #020617; position: relative; min-height: 100vh; }
.galaxy-bg { position: fixed; top: -10%; left: -10%; width: 120%; height: 120%; z-index: -2; background: url('https://images.unsplash.com/photo-1462331940025-496dfbfc7564?q=80&w=2022&auto=format&fit=crop') no-repeat center center; background-size: cover; transition: transform 0.1s ease-out; will-change: transform; }
.overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; background: rgba(2, 6, 23, 0.4); }
#splash { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #ffffff; display: flex; align-items: center; justify-content: center; z-index: 10000; transition: 0.6s ease; }
#splash img { width: 160px; border-radius: 20px; filter: drop-shadow(0 0 20px rgba(56, 189, 248, 0.8)); animation: splashPulse 1.5s infinite ease-in-out; }
@keyframes splashPulse { 0%, 100% { transform: scale(1); filter: drop-shadow(0 0 10px rgba(56, 189, 248, 0.5)); } 50% { transform: scale(1.08); filter: drop-shadow(0 0 30px rgba(56, 189, 248, 0.9)); } }
.header { text-align: center; padding: 25px 20px; position: sticky; top: 15px; margin: 0 15px 20px; z-index: 500; background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(15px) saturate(180%); border: 1px solid rgba(255, 255, 255, 0.2); border-radius: 30px; box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5); }
.top-back { position: absolute; left: 20px; top: 20px; background: rgba(239, 68, 68, 0.9); padding: 8px 15px; border-radius: 12px; font-size: 11px; font-weight: bold; cursor: pointer; display: none; z-index: 600; }
.menu-btn { position: absolute; right: 25px; top: 20px; font-size: 22px; color: #fff; cursor: pointer; z-index: 600; }
.header h1 { margin: 10px 0 0; font-family: 'Orbitron', sans-serif; font-size: 28px; font-weight: 900; letter-spacing: 5px; background: linear-gradient(90deg, #fff, #38bdf8, #818cf8, #fff); background-size: 200% auto; -webkit-background-clip: text; -webkit-text-fill-color: transparent; animation: glowText 3s linear infinite; }
@keyframes glowText { to { background-position: 200% center; } }
.logo-circle { width: 70px; height: 70px; border-radius: 50%; margin: 0 auto; display: block; object-fit: cover; border: 2px solid rgba(56, 189, 248, 0.6); box-shadow: 0 0 20px rgba(56, 189, 248, 0.4); animation: logoPulse 3s infinite ease-in-out; }
@keyframes logoPulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.08); } }
.side-nav { position: fixed; top: 0; right: -280px; width: 280px; height: 100%; background: rgba(2, 6, 23, 0.98); backdrop-filter: blur(20px); border-left: 1px solid rgba(56, 189, 248, 0.3); z-index: 2000; transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1); padding: 40px 20px; box-sizing: border-box; }
.side-nav.open { right: 0; }
.nav-item { display: flex; align-items: center; gap: 15px; padding: 15px; margin: 10px 0; border-radius: 15px; background: rgba(255,255,255,0.05); cursor: pointer; transition: 0.3s; }
.nav-item:hover { background: rgba(56, 189, 248, 0.1); }
#doubtBox { background: rgba(255, 255, 255, 0.05); border-radius: 20px; padding: 15px; margin-top: 20px; height: 350px; display: flex; flex-direction: column; }
#chatMessages { flex-grow: 1; overflow-y: auto; margin-bottom: 15px; }
.msg { background: rgba(56, 189, 248, 0.1); padding: 10px; border-radius: 12px; margin-bottom: 10px; border-left: 3px solid #38bdf8; font-size: 13px; text-align: left; }
.msg b { color: #38bdf8; display: block; font-size: 11px; }
.home-glass-btn { width: 100%; margin: 15px 0; padding: 20px; border-radius: 20px; cursor: pointer; background: transparent; border: 2px solid rgba(255, 255, 255, 0.6); color: #fff; font-family: 'Poppins', sans-serif; font-size: 16px; font-weight: 600; text-transform: uppercase; position: relative; overflow: hidden; outline: none; }
.ripple { position: absolute; background: radial-gradient(circle, rgba(56, 189, 248, 0.8) 0%, transparent 70%); border-radius: 50%; transform: scale(0); animation: stylish-ripple 0.4s cubic-bezier(0.23, 1, 0.32, 1); pointer-events: none; }
@keyframes stylish-ripple { to { transform: scale(3.5); opacity: 0; } }
.chapter { display: flex; justify-content: space-between; align-items: center; width: 100%; margin: 12px 0; padding: 18px 20px; border: 1px solid rgba(56, 189, 248, 0.2); border-radius: 20px; cursor: pointer; color: white; background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(5px); opacity: 0; transform: translateY(20px); }
.reveal { animation: revealItem 0.5s ease forwards; }
@keyframes revealItem { to { opacity: 1; transform: translateY(0); } }
.prog-bubble { position: relative; width: 55px; background: rgba(0, 0, 0, 0.4); padding: 4px 0; border-radius: 8px; font-size: 11px; text-align: center; overflow: hidden; z-index: 1; }
.prog-bubble::before { content: ""; position: absolute; top: 0; left: 0; height: 100%; width: var(--p-width, 0%); background: rgba(16, 185, 129, 0.7); transition: width 0.5s ease-in-out; z-index: -1; }
.screen h3 { text-transform: uppercase; text-align: center; color: #38bdf8; letter-spacing: 2px; font-family: 'Exo 2', sans-serif; }
.screen { display: none; padding: 10px 20px 80px; max-width: 520px; margin: auto; }
.active { display: block; }
.video-btn { width: 100%; margin: 12px 0; padding: 18px; border-radius: 18px; cursor: pointer; color: white; border: none; font-weight: 600; background: linear-gradient(135deg, #059669, #10b981); }
.notes-btn { width: 100%; margin: 12px 0; padding: 18px; border-radius: 18px; cursor: pointer; color: white; border: none; font-weight: 600; background: linear-gradient(135deg, #d97706, #f59e0b); text-align: center; }
iframe { width:100%; height:230px; border-radius:18px; margin-top: 15px; border: 1px solid rgba(56, 189, 248, 0.3); }
.floating { position: fixed; right: 20px; bottom: 30px; display: none; flex-direction: column; gap: 15px; z-index: 1001; }
.floating div { width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-size: 24px; cursor: pointer; box-shadow: 0 5px 15px rgba(0,0,0,0.3); transition: 0.3s; }
.whatsapp-btn { background: #25D366; }
.instagram-btn { background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%); }
.facebook-btn { background: #1877F2; }
.tabs { display: flex; gap: 10px; margin-bottom: 20px; background: rgba(255,255,255,0.05); padding: 5px; border-radius: 16px; }
.tab-btn { flex: 1; padding: 12px; border-radius: 12px; text-align: center; cursor: pointer; }
.tab-btn.active { background: #38bdf8; color: #020617; font-weight: bold; }
</style>  
</head>  

<body>  
    <div id="splash"><img src="https://i.ibb.co/MkP5N4DZ/logo.jpg"></div>  
    <div class="galaxy-bg" id="parallaxBg"></div>
    <div class="overlay"></div>

    <div class="header">    
        <div class="top-back" onclick="goBack()">Back</div>    
        <div class="menu-btn" onclick="toggleNav()"><i class="fas fa-ellipsis-v"></i></div>
        <img src="https://i.ibb.co/3YPtmZMM/Screenshot.png" class="logo-circle">   
        <h1>EDUFINITY</h1>     
        <div class="tagline">চলো এবার Physics কে Feel করা যাক</div>    
    </div>  

    <div id="sideNav" class="side-nav">
        <div onclick="toggleNav()" style="cursor:pointer; margin-bottom:30px;"><i class="fas fa-times"></i> Close Menu</div>
        <div class="nav-item" onclick="openSection('doubts')"><i class="fas fa-comments"></i><span>Doubt Community</span></div>
        <div class="nav-item" onclick="openLink('https://youtube.com/@edufinity_abhijit?si=QkLwbRfu6iBo6dei')"><i class="fab fa-youtube"></i><span>YouTube Channel</span></div>
        <div class="nav-item" onclick="window.open('tel:YOUR_PHONE_NUMBER')"><i class="fas fa-phone-alt"></i><span>Helpline Support</span></div>
    </div>

    <div id="home" class="screen active">    
        <h3>Physics Courses</h3>    
        <button class="home-glass-btn" onclick="handleButtonClick(event, 'boards')">Boards Exam</button>    
        <button class="home-glass-btn" onclick="handleButtonClick(event, 'jee')">JEE / NEET Entrance</button>    
    </div>  

    <div id="doubtsScreen" class="screen">
        <h3>💬 Doubt Community</h3>
        <div id="doubtBox">
            <div id="chatMessages"></div>
            <div class="chat-input-area" style="display: flex; flex-direction: column; gap: 5px;">
                <input type="text" id="studentName" placeholder="Your Name" style="padding:10px; border-radius:8px; border:none; outline:none; color:#000;">
                <input type="text" id="doubtInput" placeholder="Doubt..." style="padding:10px; border-radius:8px; border:none; outline:none; color:#000;">
                <button style="background:#38bdf8; border:none; padding:12px; border-radius:10px; font-weight:bold; cursor:pointer;" onclick="sendDoubt()">SEND</button>
            </div>
        </div>
    </div>

    <div id="sectionScreen" class="screen">    <h3 id="sectionTitle"></h3>  <div id="chapterContainer">
            <button class="chapter" onclick="openChapter('electro')"><span>Electrostatics</span> <div class="prog-bubble" id="electro-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('potential')"><span>Electrostatic Potential</span> <div class="prog-bubble" id="potential-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('current')"><span>Current Electricity</span> <div class="prog-bubble" id="current-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('magnetism')"><span>Magnetism</span> <div class="prog-bubble" id="magnetism-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('emi')"><span>Electromagnetic Induction</span> <div class="prog-bubble" id="emi-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('ac')"><span>Alternating Current</span> <div class="prog-bubble" id="ac-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('optics')"><span>Optics</span> <div class="prog-bubble" id="optics-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('dual')"><span>Dual Nature</span> <div class="prog-bubble" id="dual-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('atoms')"><span>Atoms</span> <div class="prog-bubble" id="atoms-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('nuclei')"><span>Nuclei</span> <div class="prog-bubble" id="nuclei-prog">0%</div></button>  
            <button class="chapter" onclick="openChapter('semi')"><span>Semiconductors</span> <div class="prog-bubble" id="semi-prog">0%</div></button>
    </div> </div>  

    <div id="chapterScreen" class="screen">    <h3 id="chapterTitle"></h3>    <div class="tabs">    <div class="tab-btn active" onclick="showTab('lecture')">Lecture</div>    <div class="tab-btn" onclick="showTab('notes')">Notes</div>    </div>    <div id="lectureTab"><div id="videoButtons"></div></div>    <div id="notesTab" style="display:none;"><button class="notes-btn" onclick="openPDF()">📄 Download PDF Notes</button></div>  </div>  

    <div id="player" class="screen">    <h3 id="videoTitle"></h3>    <iframe id="videoFrame" frameborder="0" allowfullscreen allow="autoplay; fullscreen"></iframe>    </div>  

    <div id="socialLinks" class="floating">    
        <div onclick="openLink('https://chat.whatsapp.com/F8nP43r3h7y3dobqk7qTI3')" class="whatsapp-btn"><i class="fab fa-whatsapp"></i></div>    
        <div onclick="openLink('https://www.instagram.com/edufinity_abhijit')" class="instagram-btn"><i class="fab fa-instagram"></i></div>    
        <div onclick="openLink('https://www.facebook.com/share/1P6JqRg8JE/')" class="facebook-btn"><i class="fab fa-facebook-f"></i></div>    
    </div>  

    <script>    
        // Firebase Configuration
        const firebaseConfig = { databaseURL: "https://edufinity-doubts-default-rtdb.firebaseio.com" };
        if (!firebase.apps.length) { firebase.initializeApp(firebaseConfig); }
        const dbDoubts = firebase.database().ref("doubts");

        let historyStack=[]; let currentSection=""; let currentChapter="";
        let progressData = JSON.parse(localStorage.getItem('eduProg')) || {};

        let data={
            electro:{ title:"Electrostatics", videos:["https://www.youtube.com/embed/GI5f4-8GbOs?autoplay=1","https://www.youtube.com/embed/o4wpmE32ab4?autoplay=1","https://www.youtube.com/embed/2zVKF4t78MQ?autoplay=1","https://www.youtube.com/embed/qC2b-u4IXX0?autoplay=1"]},
            potential:{title:"Electrostatic Potential",videos:[]}, current:{title:"Current Electricity",videos:[]}, magnetism:{title:"Magnetism",videos:[]}, emi:{title:"Electromagnetic Induction",videos:[]}, ac:{title:"Alternating Current",videos:[]}, optics:{title:"Optics",videos:[]}, dual:{title:"Dual Nature",videos:[]}, atoms:{title:"Atoms",videos:[]}, nuclei:{title:"Nuclei",videos:[]}, semi:{title:"Semiconductors",videos:[]}
        };

        function toggleNav() { document.getElementById("sideNav").classList.toggle("open"); }

        function openSection(sec){
            hideAll();
            if(sec === 'doubts') { historyStack.push("home"); document.getElementById("doubtsScreen").classList.add("active"); document.querySelector(".top-back").style.display="block"; document.getElementById("sideNav").classList.remove("open"); return; }
            currentSection=sec; historyStack.push("home"); document.getElementById("sectionScreen").classList.add("active"); document.querySelector(".top-back").style.display="block"; document.getElementById("sectionTitle").innerText = sec.toUpperCase();
            document.querySelectorAll('.chapter').forEach((ch, i) => { ch.classList.remove('reveal'); setTimeout(() => ch.classList.add('reveal'), i*80); });
            refreshProgUI(); window.scrollTo(0,0);
        }

        function sendDoubt() {
            let n = document.getElementById("studentName").value.trim() || "Anonymous";
            let m = document.getElementById("doubtInput").value.trim();
            if(!m) return;
            dbDoubts.push({ name: n, msg: m, time: Date.now() });
            document.getElementById("doubtInput").value = "";
        }

        dbDoubts.on("value", (snapshot) => {
            let chat = document.getElementById("chatMessages");
            chat.innerHTML = "";
            snapshot.forEach((child) => {
                let d = child.val();
                chat.innerHTML += `<div class="msg"><b>${d.name}</b>${d.msg}</div>`;
            });
            chat.scrollTop = chat.scrollHeight;
        });

        function handleButtonClick(e, s) { const b = e.currentTarget; const r = document.createElement("span"); const rect = b.getBoundingClientRect(); r.style.width = r.style.height = `${Math.max(rect.width, rect.height)}px`; r.style.left = `${e.clientX - rect.left}px`; r.style.top = `${e.clientY - rect.top}px`; r.classList.add("ripple"); b.appendChild(r); setTimeout(() => { r.remove(); openSection(s); }, 200); }
        function openChapter(ch){ currentChapter=ch; historyStack.push("section"); hideAll(); document.getElementById("chapterScreen").classList.add("active"); document.getElementById("chapterTitle").innerText = data[ch].title.toUpperCase(); let container=document.getElementById("videoButtons"); container.innerHTML=""; if(currentSection==="boards" && ch==="electro") { data[ch].videos.forEach((v,i)=>{ container.innerHTML+=`<button class="video-btn" style="width:100%; padding:15px; margin:10px 0; border-radius:15px; border:none; color:white; cursor:pointer; font-weight:bold;" onclick="playVideo(${i})">${data[ch].title.toUpperCase()} - PART ${i+1}</button>`; }); } else { container.innerHTML=`<div style="text-align:center; padding:20px; opacity:0.8;"><h3>📘 Coming Soon</h3></div>`; } showTab('lecture'); }
        function showTab(tab){ document.getElementById("lectureTab").style.display = tab==="lecture"?"block":"none"; document.getElementById("notesTab").style.display = tab==="notes"?"block":"none"; document.querySelectorAll(".tab-btn").forEach(b=>b.classList.remove("active")); if(tab==='lecture') document.querySelectorAll(".tab-btn")[0].classList.add("active"); else document.querySelectorAll(".tab-btn")[1].classList.add("active"); }
        function playVideo(i){ if(currentSection === "boards") { let total = data[currentChapter].videos.length; let current = (progressData[currentChapter] || 0); progressData[currentChapter] = Math.min(100, current + Math.round(100/total)); localStorage.setItem('eduProg', JSON.stringify(progressData)); } historyStack.push("chapter"); hideAll(); let p = document.getElementById("player"); let f = document.getElementById("videoFrame"); p.classList.add("active"); f.src = data[currentChapter].videos[i]; document.getElementById("videoTitle").innerText = data[currentChapter].title.toUpperCase(); if (f.requestFullscreen) f.requestFullscreen(); else if (f.webkitRequestFullscreen) f.webkitRequestFullscreen(); }
        function goBack(){ document.getElementById("videoFrame").src=""; let last=historyStack.pop(); hideAll(); if(last==="chapter") document.getElementById("chapterScreen").classList.add("active"); else if(last==="section") { document.getElementById("sectionScreen").classList.add("active"); refreshProgUI(); } else { document.getElementById("home").classList.add("active"); document.querySelector(".top-back").style.display="none"; } }
        function hideAll(){ document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active")); }
        function openLink(url) { window.open(url, '_blank').focus(); }
        function openPDF(){ window.open("YOUR_PDF_LINK","_blank"); }
        function refreshProgUI(){ Object.keys(data).forEach(key => { let el = document.getElementById(key + "-prog"); if(el) { let val = (currentSection === "boards") ? (progressData[key] || 0) : 0; el.innerText = val + "%"; el.style.setProperty('--p-width', val + '%'); } }); }
        document.addEventListener('mousemove', (e) => { const bg = document.getElementById('parallaxBg'); bg.style.transform = `translate(${(window.innerWidth / 2 - e.pageX) / 35}px, ${(window.innerHeight / 2 - e.pageY) / 35}px)`; });
        window.onload=()=>{ setTimeout(()=>{ document.getElementById("splash").style.opacity = "0"; setTimeout(() => { document.getElementById("splash").style.display = "none"; document.getElementById("socialLinks").style.display = "flex"; }, 800); }, 1500); };
    </script>  
</body>
