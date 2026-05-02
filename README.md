
<html lang="en">    
<head>    
<meta charset="UTF-8">    
<title>EDUFINITY - Physics</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Poppins:wght@400;600&family=Exo+2:wght@500;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

<style>    
body { margin: 0; font-family: 'Poppins', sans-serif; color: white; overflow-x: hidden; background-color: #020617; position: relative; min-height: 100vh; }
.galaxy-bg { position: fixed; top: -10%; left: -10%; width: 120%; height: 120%; z-index: -2; background: url('https://images.unsplash.com/photo-1462331940025-496dfbfc7564?q=80&w=2022&auto=format&fit=crop') no-repeat center center; background-size: cover; }
.overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; z-index: -1; background: rgba(2, 6, 23, 0.4); }

/* Splash Screen */
#splash { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #ffffff; display: flex; align-items: center; justify-content: center; z-index: 10000; transition: 0.6s ease; }
#splash img { width: 160px; border-radius: 20px; filter: drop-shadow(0 0 20px rgba(56, 189, 248, 0.8)); animation: splashPulse 1.5s infinite ease-in-out; }
@keyframes splashPulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.08); } }

/* Header */
.header { text-align: center; padding: 25px 20px; position: sticky; top: 15px; margin: 0 15px 20px; z-index: 500; background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(15px) saturate(180%); border: 1px solid rgba(255, 255, 255, 0.2); border-radius: 30px; box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5); }
.logo-circle { width: 70px; height: 70px; border-radius: 50%; margin: 0 auto; display: block; object-fit: cover; border: 2px solid rgba(56, 189, 248, 0.6); box-shadow: 0 0 20px rgba(56, 189, 248, 0.4); animation: logoPulse 3s infinite ease-in-out; }
@keyframes logoPulse { 0%, 100% { transform: scale(1); } 50% { transform: scale(1.1); } }
.header h1 { margin: 10px 0 0; font-family: 'Orbitron', sans-serif; font-size: 28px; font-weight: 900; letter-spacing: 5px; background: linear-gradient(90deg, #fff, #38bdf8, #818cf8, #fff); background-size: 200% auto; -webkit-background-clip: text; -webkit-text-fill-color: transparent; animation: glowText 3s linear infinite; }
@keyframes glowText { to { background-position: 200% center; } }

/* STYLISH HAMBURGER MENU */
.menu-btn { 
    position: absolute; 
    right: 25px; 
    top: 30px; 
    width: 28px; 
    height: 20px; 
    cursor: pointer; 
    z-index: 2500; 
    display: flex; 
    flex-direction: column; 
    justify-content: space-between; 
}
.menu-btn span { 
    display: block; 
    height: 3px; 
    width: 100%; 
    background: linear-gradient(90deg, #38bdf8, #818cf8); 
    border-radius: 10px; 
    transition: 0.4s cubic-bezier(0.68, -0.6, 0.32, 1.6); 
}
.menu-btn.open span:nth-child(1) { transform: translateY(8.5px) rotate(45deg); }
.menu-btn.open span:nth-child(2) { opacity: 0; transform: translateX(-20px); }
.menu-btn.open span:nth-child(3) { transform: translateY(-8.5px) rotate(-45deg); }

/* Side Nav */
.side-nav { position: fixed; top: 0; right: -280px; width: 280px; height: 100%; background: rgba(2, 6, 23, 0.98); backdrop-filter: blur(25px); border-left: 1px solid rgba(56, 189, 248, 0.3); z-index: 2000; transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1); padding: 40px 20px; box-sizing: border-box; }
.side-nav.open { right: 0; }
.menu-title { font-family: 'Orbitron'; font-size: 16px; color: #38bdf8; margin-bottom: 30px; border-bottom: 1px solid rgba(56, 189, 248, 0.2); padding-bottom: 10px; letter-spacing: 2px; }

.nav-item { display: flex; align-items: center; gap: 15px; padding: 15px; margin: 10px 0; border-radius: 15px; background: rgba(255,255,255,0.05); cursor: pointer; transition: 0.3s; }
.nav-item:hover { background: rgba(56, 189, 248, 0.1); }

.sub-menu { max-height: 0; overflow: hidden; transition: 0.4s ease-out; padding-left: 45px; }
.sub-menu.active { max-height: 120px; margin-top: 5px; }

/* Class Tabs - Orange */
.class-tabs { display: flex; gap: 10px; margin: 20px 15px; background: rgba(255,255,255,0.05); padding: 5px; border-radius: 20px; border: 1px solid rgba(255,255,255,0.1); }
.c-tab { flex: 1; padding: 15px; border-radius: 15px; text-align: center; cursor: pointer; transition: 0.3s; font-weight: bold; color: white; opacity: 0.6; }
.c-tab.active { background: #f59e0b; color: #020617; opacity: 1; box-shadow: 0 0 15px rgba(245, 158, 11, 0.6); }

/* Chapter Cards */
.screen { display: none; padding: 10px 10px 100px; max-width: 520px; margin: auto; }
.screen.active { display: block; animation: screenReveal 0.4s ease; }
@keyframes screenReveal { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

#chapterList { padding: 0 10px; }
.chapter { display: flex; justify-content: space-between; align-items: center; width: 100%; margin: 15px 0; padding: 18px 20px; border: 1px solid rgba(56, 189, 248, 0.2); border-radius: 20px; cursor: pointer; color: white; background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(5px); box-sizing: border-box; }

.prog-bubble { position: relative; width: 55px; background: rgba(0, 0, 0, 0.4); padding: 4px 0; border-radius: 8px; font-size: 11px; text-align: center; overflow: hidden; z-index: 1; }
.prog-bubble::before { content: ""; position: absolute; top: 0; left: 0; height: 100%; width: var(--p-width, 0%); background: #10b981; opacity: 0.8; transition: 0.5s; z-index: -1; }

/* Cyan Lecture/Notes Tabs */
.tabs { display: flex; gap: 10px; margin: 0 15px 20px; background: rgba(255,255,255,0.05); padding: 5px; border-radius: 16px; border: 1px solid rgba(56, 189, 248, 0.2); }
.tab-btn { flex: 1; padding: 12px; border-radius: 12px; text-align: center; cursor: pointer; font-weight: bold; transition: 0.3s; }
.tab-btn.active { background: #38bdf8; color: #020617; }

/* Buttons & Elements */
.home-glass-btn { width: calc(100% - 20px); margin: 15px auto; display: block; padding: 20px; border-radius: 20px; background: transparent; border: 2px solid rgba(255,255,255,0.6); color: white; font-weight: bold; cursor: pointer; text-transform: uppercase; }
.video-btn { width: calc(100% - 20px); margin: 10px auto; display: block; padding: 18px; border-radius: 18px; cursor: pointer; color: white; border: none; font-weight: bold; background: linear-gradient(135deg, #059669, #10b981); }
iframe { width: calc(100% - 20px); margin: 15px auto; display: block; height: 230px; border-radius: 18px; border: 1px solid #38bdf8; }

.top-back { position: absolute; left: 20px; top: 20px; background: #ef4444; padding: 8px 15px; border-radius: 12px; font-size: 11px; font-weight: bold; cursor: pointer; display: none; z-index: 600; }
.floating { position: fixed; right: 20px; bottom: 30px; display: flex; flex-direction: column; gap: 15px; z-index: 1001; }
.floating div { width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-size: 24px; cursor: pointer; box-shadow: 0 5px 15px rgba(0,0,0,0.3); }
.whatsapp-btn { background: #25D366; }
.instagram-btn { background: linear-gradient(45deg, #f09433, #bc1888); }
.facebook-btn { background: #1877F2; }
</style>  
</head>  

<body>  
    <div id="splash"><img src="https://i.ibb.co/MkP5N4DZ/logo.jpg"></div>  
    <div class="galaxy-bg"></div>
    <div class="overlay"></div>

    <div class="header">    
        <div class="top-back" onclick="goBack()">Back</div>    
        
        <div class="menu-btn" id="menuBtn" onclick="toggleNav()">
            <span></span>
            <span></span>
            <span></span>
        </div>

        <img src="https://i.ibb.co/3YPtmZMM/Screenshot.png" class="logo-circle">   
        <h1>EDUFINITY</h1>     
        <div class="tagline">চলো এবার Physics কে Feel করা যাক</div>    
    </div>  

    <div id="sideNav" class="side-nav">
        <div class="menu-title">DASHBOARD</div>
        <div class="nav-item" onclick="toggleDoubt()">
            <i class="fas fa-comments" style="color:#38bdf8;"></i><span>Doubt Community</span>
            <i class="fas fa-chevron-right" id="arrow" style="margin-left:auto; font-size:12px; transition:0.3s;"></i>
        </div>
        <div id="doubtSub" class="sub-menu">
            <div style="padding:10px 0; color:#cbd5e1;" onclick="alert('Class 11 Community Soon')">● Class 11 Group</div>
            <div style="padding:10px 0; color:#cbd5e1;" onclick="alert('Class 12 Community Soon')">● Class 12 Group</div>
        </div>
        <div class="nav-item" onclick="window.open('https://youtube.com/@edufinity_abhijit')">
            <i class="fab fa-youtube" style="color:#38bdf8;"></i><span>YouTube Channel</span>
        </div>
        
        <div class="nav-item" onclick="window.open('https://chatgpt.com')">
            <i class="fas fa-robot" style="color:#38bdf8;"></i><span>AI Assistant</span>
        </div>

        <div class="nav-item" onclick="window.open('tel:YOUR_PHONE_NUMBER_HERE')">
            <i class="fas fa-phone-alt" style="color:#38bdf8;"></i><span>Helpline</span>
        </div>

        <div class="nav-item" style="margin-top:auto; color:#ef4444;" onclick="toggleNav()">
            <i class="fas fa-times-circle"></i><span>Close</span>
        </div>
    </div>

    <div id="home" class="screen active">
        <div class="class-tabs">
            <div class="c-tab active" id="tab12" onclick="switchClass('12')">Class 12</div>
            <div class="c-tab" id="tab11" onclick="switchClass('11')">Class 11</div>
        </div>
        <h3 id="courseHeading" style="text-align:center; color:#38bdf8; font-family:'Exo 2';">COURSE FOR 12</h3>    
        <button class="home-glass-btn" onclick="openSection('boards')">Boards Exam</button>    
        <button class="home-glass-btn" onclick="openSection('jee')">JEE / NEET Entrance</button>    
    </div>  

    <div id="sectionScreen" class="screen">    
        <h3 id="secTitle" style="text-align:center; color:#38bdf8;"></h3>  
        <div id="chapterList"></div> 
    </div>  

    <div id="chapterScreen" class="screen">    
        <h3 id="chTitle" style="text-align:center; color:#38bdf8;"></h3>    
        <div class="tabs">    
            <div class="tab-btn active" id="lBtn" onclick="showTab('lecture')">Lecture</div>    
            <div class="tab-btn" id="nBtn" onclick="showTab('notes')">Notes</div>    
        </div>    
        <div id="lectureTab"></div>    
        <div id="notesTab" style="display:none;">
            <button class="video-btn" style="background: linear-gradient(135deg, #d97706, #f59e0b); color:black;">📄 Download PDF Notes</button>
        </div>  
    </div>  

    <div id="player" class="screen">
        <h3 id="vTitle" style="text-align:center; font-size:16px;"></h3>
        <iframe id="vFrame" frameborder="0" allowfullscreen allow="autoplay; fullscreen"></iframe>
    </div>

    <div class="floating">    
        <div onclick="window.open('https://chat.whatsapp.com/F8nP43r3h7y3dobqk7qTI3')" class="whatsapp-btn"><i class="fab fa-whatsapp"></i></div>    
        <div onclick="window.open('https://www.instagram.com/edufinity_abhijit')" class="instagram-btn"><i class="fab fa-instagram"></i></div>    
        <div onclick="window.open('https://www.facebook.com/share/1P6JqRg8JE/')" class="facebook-btn"><i class="fab fa-facebook-f"></i></div>    
    </div>  

    <script>
        let currentClass = "12";
        let historyStack = [];
        let progress = JSON.parse(localStorage.getItem('eduProg')) || {};

        const chapters = {
            "12": ["Electrostatics", "Electrostatic Potential", "Current Electricity", "Magnetism", "EMI", "Alternating Current", "Optics", "Dual Nature", "Atoms", "Nuclei", "Semiconductors"],
            "11": ["Physical World", "Units & Measurements", "Motion in a Straight Line", "Motion in a Plane", "Laws of Motion", "Work, Energy & Power", "Gravitation", "Matter Properties", "Thermodynamics", "Oscillations", "Waves"]
        };

        const boardVideos = {
            "Electrostatics": [
                "https://www.youtube.com/embed/GI5f4-8GbOs",
                "https://www.youtube.com/embed/o4wpmE32ab4",
                "https://www.youtube.com/embed/2zVKF4t78MQ",
                "https://www.youtube.com/embed/qC2b-u4IXX0"
            ]
        };

        function switchClass(c) {
            currentClass = c;
            document.querySelectorAll('.c-tab').forEach(t => t.classList.remove('active'));
            document.getElementById('tab' + c).classList.add('active');
            document.getElementById('courseHeading').innerText = "COURSE FOR " + c;
        }

        // Updated toggleNav for animation
        function toggleNav() { 
            document.getElementById("sideNav").classList.toggle("open"); 
            document.getElementById("menuBtn").classList.toggle("open");
        }

        function toggleDoubt() {
            const sub = document.getElementById("doubtSub");
            const arrow = document.getElementById("arrow");
            sub.classList.toggle("active");
            arrow.style.transform = sub.classList.contains("active") ? "rotate(90deg)" : "rotate(0deg)";
        }

        function openSection(s) {
            historyStack.push("home"); hideAll();
            document.getElementById("sectionScreen").classList.add("active");
            document.getElementById("secTitle").innerText = s.toUpperCase() + " (CLASS " + currentClass + ")";
            document.querySelector(".top-back").style.display = "block";
            let list = document.getElementById("chapterList"); list.innerHTML = "";
            
            chapters[currentClass].forEach(ch => {
                let uniqueKey = currentClass + s + ch;
                let p = progress[uniqueKey] || 0;
                list.innerHTML += `<div class="chapter" onclick="openChapter('${ch}', '${s}')"><span>${ch}</span><div class="prog-bubble" style="--p-width:${p}%">${p}%</div></div>`;
            });
        }

        function openChapter(ch, sec) {
            historyStack.push("section"); hideAll();
            document.getElementById("chapterScreen").classList.add("active");
            document.getElementById("chTitle").innerText = ch;
            let lTab = document.getElementById("lectureTab"); lTab.innerHTML = "";
            
            if(currentClass === "12" && sec === "boards" && boardVideos[ch]) {
                boardVideos[ch].forEach((link, i) => {
                    lTab.innerHTML += `<button class="video-btn" onclick="playVideo('${link}', '${ch}', '${sec}', ${i+1})">PART ${i+1} : ${ch}</button>`;
                });
            } else {
                lTab.innerHTML = "<div style='text-align:center; padding:40px; opacity:0.6; color:#38bdf8;'>📘 Coming Soon</div>";
            }
            showTab('lecture');
        }

        function playVideo(url, ch, sec, part) {
            historyStack.push("chapter"); hideAll();
            const frame = document.getElementById("vFrame");
            document.getElementById("player").classList.add("active");
            document.getElementById("vTitle").innerText = ch + " Part " + part;
            frame.src = url + "?autoplay=1";
            
            if (frame.requestFullscreen) frame.requestFullscreen();
            else if (frame.webkitRequestFullscreen) frame.webkitRequestFullscreen();

            let uniqueKey = currentClass + sec + ch;
            let totalVideos = (boardVideos[ch]) ? boardVideos[ch].length : 1;
            let currentP = progress[uniqueKey] || 0;
            progress[uniqueKey] = Math.min(100, currentP + Math.round(100/totalVideos));
            localStorage.setItem('eduProg', JSON.stringify(progress));
        }

        function goBack() {
            let last = historyStack.pop(); hideAll();
            document.getElementById("vFrame").src = "";
            if(last === "chapter") document.getElementById("chapterScreen").classList.add("active");
            else if(last === "section") { 
                let s = document.getElementById("secTitle").innerText.split(' ')[0].toLowerCase();
                openSection(s); historyStack.pop(); 
            }
            else { document.getElementById("home").classList.add("active"); document.querySelector(".top-back").style.display = "none"; }
        }

        function hideAll() { document.querySelectorAll(".screen").forEach(s => s.classList.remove("active")); }
        
        function showTab(t) {
            document.getElementById("lectureTab").style.display = t === 'lecture' ? 'block' : 'none';
            document.getElementById("notesTab").style.display = t === 'notes' ? 'block' : 'none';
            document.getElementById("lBtn").classList.toggle("active", t === 'lecture');
            document.getElementById("nBtn").classList.toggle("active", t === 'notes');
        }

        window.onload = () => { setTimeout(() => { 
            document.getElementById("splash").style.opacity = "0"; 
            setTimeout(() => document.getElementById("splash").style.display = "none", 600);
        }, 1500); };
    </script>
</body>
