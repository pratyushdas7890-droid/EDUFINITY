<html lang="en">    
<head>    
<meta charset="UTF-8">    
<title>EDUFINITY - Class 12 Physics</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Poppins:wght@400;600&family=Exo+2:wght@500;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">

<style>    
body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    color: white;
    overflow-x: hidden;
    background-color: #020617;
    background-image: 
        linear-gradient(rgba(56, 189, 248, 0.1) 1px, transparent 1px),
        linear-gradient(90deg, rgba(56, 189, 248, 0.1) 1px, transparent 1px);
    background-size: 40px 40px;
    background-position: center;
    position: relative;
}

body::before {
    content: "";
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    z-index: -1;
    background: radial-gradient(circle at 50% 50%, transparent 20%, #020617 90%);
}

body::after {
    content: "";
    position: fixed;
    top: -10%; left: -10%; width: 120%; height: 120%;
    z-index: -2;
    background: radial-gradient(circle at 20% 30%, rgba(30, 58, 138, 0.4), transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(7, 89, 133, 0.3), transparent 50%);
    filter: blur(80px);
}

#splash {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: #ffffff;
    display: flex; align-items: center; justify-content: center;
    z-index: 10000;
    transition: 0.6s ease;
}

#splash img {
    width: 160px;
    border-radius: 20px;
    filter: drop-shadow(0 0 10px rgba(56, 189, 248, 0.5));
    animation: quantumPulse 2s infinite ease-in-out;
}

@keyframes quantumPulse {
    0%, 100% { transform: scale(1); opacity: 1; filter: drop-shadow(0 0 10px rgba(56, 189, 248, 0.4)); }
    50% { transform: scale(1.05); opacity: 0.9; filter: drop-shadow(0 0 25px rgba(56, 189, 248, 0.8)); }
}

.header {
    text-align: center;
    padding: 30px 10px;
    position: sticky;
    top: 0;
    background: rgba(2, 6, 23, 0.85);
    backdrop-filter: blur(15px);
    border-bottom: 1px solid rgba(56, 189, 248, 0.3);
    z-index: 100;
}

.header h1 {
    margin: 0;
    font-family: 'Orbitron', sans-serif;
    font-size: 40px;
    font-weight: 900;
    letter-spacing: 5px;
    background: linear-gradient(90deg, #fff, #38bdf8, #818cf8, #fff);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: glowText 3s linear infinite;
    text-shadow: 0 0 20px rgba(56, 189, 248, 0.5);
}

.header .tagline {
    margin-top: 10px;
    font-family: 'Exo 2', sans-serif;
    font-size: 14px;
    color: #38bdf8;
    font-weight: 600;
    letter-spacing: 1.5px;
    text-transform: uppercase;
}

@keyframes glowText { to { background-position: 200% center; } }

.logo-circle { width: 70px; height: 70px; border-radius: 50%; margin: 0 auto 15px; display: block; object-fit: cover; border: 2px solid #38bdf8; box-shadow: 0 0 20px rgba(56, 189, 248, 0.4); }

.top-back {
    position: absolute; left: 15px; top: 25px;
    background: rgba(239, 68, 68, 0.9); padding: 8px 16px; border-radius: 12px;
    font-size: 12px; font-weight: bold; cursor: pointer; display: none; z-index: 999;
}

.screen { display: none; padding: 30px 20px; max-width: 520px; margin: auto; animation: slideUp 0.5s ease-out; }
@keyframes slideUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
.active { display: block; }

.chapter {
    display: flex; justify-content: space-between; align-items: center;
    width: 100%; margin: 12px 0; padding: 18px 20px;
    border: 1px solid rgba(56, 189, 248, 0.2); border-radius: 18px;
    cursor: pointer; color: white; font-size: 15px; font-weight: 600;
    transition: 0.3s; background: linear-gradient(135deg, #1e40af, #1d4ed8);
    text-align: left;
    position: relative;
    overflow: hidden;
}

.prog-bubble {
    position: relative; width: 55px; background: rgba(0, 0, 0, 0.4); 
    padding: 4px 0; border-radius: 8px; font-size: 11px; color: #fff; 
    border: 1px solid rgba(255, 255, 255, 0.1); text-align: center;
    overflow: hidden; z-index: 1;
}

.prog-bubble::before {
    content: ""; position: absolute; top: 0; left: 0; height: 100%;
    width: var(--p-width, 0%); background: rgba(16, 185, 129, 0.7);
    transition: width 0.5s ease; z-index: -1;
}

.video-btn { width: 100%; margin: 12px 0; padding: 18px; border-radius: 18px; cursor: pointer; color: white; font-size: 16px; font-weight: 600; border: none; background: linear-gradient(135deg, #059669, #10b981); text-align: center; }
.notes-btn { width: 100%; margin: 12px 0; padding: 18px; border-radius: 18px; cursor: pointer; color: white; font-size: 16px; font-weight: 600; border: none; background: linear-gradient(135deg, #d97706, #f59e0b); text-align: center; }

.home-glass-btn {
    width: 100%; margin: 12px 0; padding: 18px; border-radius: 18px; cursor: pointer;
    background: rgba(255, 255, 255, 0.08); backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.15); color: #fff;
    font-family: 'Poppins', sans-serif; font-size: 15px; font-weight: 600;
    text-transform: uppercase; letter-spacing: 1.2px; text-align: center;
}

button:hover { box-shadow: 0 0 20px rgba(56, 189, 248, 0.4); transform: translateY(-2px); }

iframe { width:100%; height:230px; border-radius:18px; margin-top: 15px; border: 1px solid rgba(56, 189, 248, 0.3); }

.tabs { display: flex; gap: 10px; margin-bottom: 20px; background: rgba(255,255,255,0.05); padding: 5px; border-radius: 16px; }
.tab-btn { flex: 1; padding: 12px; border-radius: 12px; text-align: center; cursor: pointer; }
.tab-btn.active { background: #38bdf8; color: #020617; font-weight: bold; }

.floating { position: fixed; right: 20px; bottom: 30px; display: none; flex-direction: column; gap: 15px; z-index: 50; }
.floating div { width: 50px; height: 50px; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: white; font-size: 24px; cursor: pointer; border: 1px solid rgba(255,255,255,0.2); }
.whatsapp-btn { background: #25D366; }
.instagram-btn { background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%); }
.facebook-btn { background: #1877F2; }

</style>  
</head>  

<body>  
    <div id="splash"><img src="https://i.ibb.co/MkP5N4DZ/logo.jpg"></div>  

    <div class="header">    
        <div class="top-back" onclick="goBack()">Back</div>    
        <img src="https://i.ibb.co/3YPtmZMM/Screenshot.png" class="logo-circle">   
        <h1>EDUFINITY</h1>     
        <div class="tagline">চলো এবার Physics কে Feel করা যাক</div>    
    </div>  

    <div id="home" class="screen active">    
        <h3 style="text-align:center; color:#38bdf8; font-family:'Exo 2'; text-transform:uppercase;">Physics Courses</h3>    
        <button class="home-glass-btn" onclick="openSection('boards')">Boards Exam</button>    
        <button class="home-glass-btn" onclick="openSection('jee')">JEE / NEET Entrance</button>    
    </div>  

    <div id="sectionScreen" class="screen">    
        <h3 id="sectionTitle" style="text-align:center; color:#38bdf8; text-transform:uppercase;"></h3>  
        <div id="chapterContainer">
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
        </div>
    </div>  

    <div id="chapterScreen" class="screen">    
        <h3 id="chapterTitle" style="color:#38bdf8; text-align:center;"></h3>    
        <div class="tabs">    
            <div class="tab-btn active" onclick="showTab('lecture')">Lecture</div>    
            <div class="tab-btn" onclick="showTab('notes')">Notes</div>    
        </div>    
        <div id="lectureTab">    
            <div id="videoButtons"></div>    
        </div>    
        <div id="notesTab" style="display:none;">    
            <button class="notes-btn" onclick="openPDF()">Download PDF Notes</button>    
        </div>  
    </div>  

    <div id="player" class="screen">    
        <h3 id="videoTitle" style="text-align:center;"></h3>    
        <iframe id="videoFrame" frameborder="0" allowfullscreen allow="autoplay; fullscreen"></iframe>    
    </div>  

    <div id="socialLinks" class="floating">    
        <div onclick="openLink('https://chat.whatsapp.com/F8nP43r3h7y3dobqk7qTI3')" class="whatsapp-btn"><i class="fab fa-whatsapp"></i></div>    
        <div onclick="openLink('https://www.instagram.com/edufinity_abhijit')" class="instagram-btn"><i class="fab fa-instagram"></i></div>    
        <div onclick="openLink('https://www.facebook.com/share/1P6JqRg8JE/')" class="facebook-btn"><i class="fab fa-facebook-f"></i></div>    
    </div>  

    <script>    
        let currentChapter=""; let historyStack=[]; let currentSection="";
        let progressData = JSON.parse(localStorage.getItem('eduProg')) || {};

        let data={
            electro:{ title:"Electrostatics", videos:[
                "https://www.youtube.com/embed/GI5f4-8GbOs?autoplay=1",
                "https://www.youtube.com/embed/o4wpmE32ab4?autoplay=1",
                "https://www.youtube.com/embed/2zVKF4t78MQ?autoplay=1",
                "https://www.youtube.com/embed/qC2b-u4IXX0?autoplay=1"
            ]},
            potential:{title:"Electrostatic Potential",videos:[]},
            current:{title:"Current Electricity",videos:[]},
            magnetism:{title:"Magnetism",videos:[]},
            emi:{title:"Electromagnetic Induction",videos:[]},
            ac:{title:"Alternating Current",videos:[]},
            optics:{title:"Optics",videos:[]},
            dual:{title:"Dual Nature",videos:[]},
            atoms:{title:"Atoms",videos:[]},
            nuclei:{title:"Nuclei",videos:[]},
            semi:{title:"Semiconductors",videos:[]}
        };

        function openLink(url) { window.open(url, '_blank').focus(); }

        function openSection(sec){
            currentSection=sec; historyStack.push("home"); hideAll();
            document.getElementById("sectionScreen").classList.add("active");
            document.querySelector(".top-back").style.display="block";
            document.getElementById("sectionTitle").innerText=sec;
            refreshProgUI();
        }

        function refreshProgUI(){
            Object.keys(data).forEach(key => {
                let el = document.getElementById(key + "-prog");
                if(el) {
                    let val = 0;
                    if(currentSection === "boards") {
                        val = progressData[key] || 0;
                    }
                    el.innerText = val + "%";
                    el.style.setProperty('--p-width', val + '%');
                }
            });
        }

        function openChapter(ch){
            currentChapter=ch; historyStack.push("section"); hideAll();
            document.getElementById("chapterScreen").classList.add("active");
            document.getElementById("chapterTitle").innerText=data[ch].title;
            let container=document.getElementById("videoButtons"); container.innerHTML="";

            if(currentSection==="boards" && ch==="electro") {
                data[ch].videos.forEach((v,i)=>{
                    container.innerHTML+=`<button class="video-btn" onclick="playVideo(${i})">${data[ch].title} - Part ${i+1}</button>`;
                });
            } else {
                container.innerHTML=`<div style="text-align:center; padding:20px; opacity:0.8;"><h3>📘 Coming Soon</h3></div>`;
            }
        }

        function playVideo(i){
            if(currentSection === "boards") {
                let total = data[currentChapter].videos.length;
                let current = (progressData[currentChapter] || 0);
                if(current < 100) {
                    progressData[currentChapter] = Math.min(100, current + Math.round(100/total));
                    localStorage.setItem('eduProg', JSON.stringify(progressData));
                }
            }
            historyStack.push("chapter"); hideAll();
            let playerDiv = document.getElementById("player");
            let videoFrame = document.getElementById("videoFrame");
            playerDiv.classList.add("active");
            videoFrame.src = data[currentChapter].videos[i];
            document.getElementById("videoTitle").innerText = data[currentChapter].title;

            if (videoFrame.requestFullscreen) { videoFrame.requestFullscreen(); }
            else if (videoFrame.webkitRequestFullscreen) { videoFrame.webkitRequestFullscreen(); }
        }

        function showTab(tab){
            document.getElementById("lectureTab").style.display = tab==="lecture"?"block":"none";
            document.getElementById("notesTab").style.display = tab==="notes"?"block":"none";
            document.querySelectorAll(".tab-btn").forEach(b=>b.classList.remove("active"));
            event.currentTarget.classList.add("active");
        }

        function openPDF(){ window.open("YOUR_PDF_LINK","_blank"); }

        function goBack(){
            if (document.fullscreenElement) document.exitFullscreen();
            document.getElementById("videoFrame").src="";
            let last=historyStack.pop(); hideAll();
            if(last==="chapter") document.getElementById("chapterScreen").classList.add("active");
            else if(last==="section") { document.getElementById("sectionScreen").classList.add("active"); refreshProgUI(); }
            else { document.getElementById("home").classList.add("active"); document.querySelector(".top-back").style.display="none"; }
        }

        function hideAll(){ document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active")); }

        window.onload=()=>{
            setTimeout(()=>{
                document.getElementById("splash").style.opacity = "0";
                setTimeout(() => { document.getElementById("splash").style.display = "none"; document.getElementById("socialLinks").style.display = "flex"; }, 600);
            }, 1500);
        };
    </script>  
</body>
