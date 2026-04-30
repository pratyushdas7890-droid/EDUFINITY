<html lang="en">    
<head>    
<meta charset="UTF-8">    
<title>EDUFINITY - Class 12 Physics</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@700;900&family=Poppins:wght@400;600&family=Exo+2:wght@500&display=swap" rel="stylesheet">
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
    filter: drop-shadow(0 0 15px rgba(0, 0, 0, 0.1)); 
    animation: quantumPulse 2s infinite ease-in-out;
}

@keyframes quantumPulse {
    0%, 100% { transform: scale(1); opacity: 1; }
    50% { transform: scale(1.05); opacity: 0.9; }
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

@keyframes glowText {
    to { background-position: 200% center; }
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

.logo-circle {
    width: 70px;
    height: 70px;
    border-radius: 50%;
    margin: 0 auto 15px;
    display: block;
    object-fit: cover;
    border: 2px solid #38bdf8;
    box-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
}

.top-back {
    position: absolute;
    left: 15px;
    top: 25px;
    background: rgba(239, 68, 68, 0.9);
    padding: 8px 16px;
    border-radius: 12px;
    font-size: 12px;
    font-weight: bold;
    cursor: pointer;
    display: none;
    z-index: 999;
}

.screen {
    display: none;
    padding: 30px 20px;
    max-width: 520px;
    margin: auto;
    animation: slideUp 0.5s ease-out;
}

@keyframes slideUp {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

.active { display: block; }

button {
    width: 100%;
    margin: 12px 0;
    padding: 18px;
    border: 1px solid rgba(56, 189, 248, 0.2);
    border-radius: 18px;
    cursor: pointer;
    color: white;
    font-size: 16px;
    font-weight: 600;
    transition: 0.3s;
    background: rgba(15, 23, 42, 0.6);
    backdrop-filter: blur(5px);
}

.chapter { background: linear-gradient(135deg, #1e40af, #1d4ed8); }
.video { background: linear-gradient(135deg, #059669, #10b981); }
.notes { background: linear-gradient(135deg, #d97706, #f59e0b); }

button:hover {
    box-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
    transform: translateY(-2px);
}

iframe {
    width:100%;
    height:230px;
    border-radius:18px;
    margin-top: 15px;
    border: 1px solid rgba(56, 189, 248, 0.3);
}

.tabs {
    display: flex;
    gap: 10px;
    margin-bottom: 20px;
    background: rgba(255,255,255,0.05);
    padding: 5px;
    border-radius: 16px;
}

.tab-btn {
    flex: 1;
    padding: 12px;
    border-radius: 12px;
    text-align: center;
    cursor: pointer;
}

.tab-btn.active {
    background: #38bdf8;
    color: #020617;
    font-weight: bold;
}

/* --- Floating Button Update Starts --- */
.floating {
    position: fixed;
    right: 20px;
    bottom: 30px;
    display: none;
    flex-direction: column;
    gap: 15px;
    z-index: 50;
}

.floating div {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: white;
    font-size: 24px;
    cursor: pointer;
    backdrop-filter: blur(10px);
    border: 1px solid rgba(255, 255, 255, 0.2);
    box-shadow: 0 4px 15px rgba(0,0,0,0.3);
    transition: 0.3s;
}

.floating div:hover {
    transform: scale(1.1);
}

.whatsapp-btn { background: #25D366; }
.instagram-btn { background: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%); }
.facebook-btn { background: #1877F2; }
/* --- Floating Button Update Ends --- */

</style>  
</head>  

<body>  
    <div id="splash">
        <img src="https://i.ibb.co/MkP5N4DZ/logo.jpg">
    </div>  

    <div class="header">    
        <div class="top-back" onclick="goBack()">Back</div>    
        <img src="https://i.ibb.co/3YPtmZMM/Screenshot.png" class="logo-circle">   
        <h1>EDUFINITY</h1>     
        <div class="tagline">চলো এবার Physics কে Feel করা যাক</div>    
    </div>  

    <div id="home" class="screen active">    
        <h3 style="text-align:center; color:#38bdf8;">📚 Physics Courses</h3>    
        <button class="chapter" onclick="openSection('boards')">Boards Exam</button>    
        <button class="chapter" onclick="openSection('jee')">JEE / NEET Entrance</button>    
    </div>  

    <div id="sectionScreen" class="screen">    
        <h3 id="sectionTitle" style="text-align:center; color:#38bdf8; text-transform:uppercase;"></h3>  
        <button class="chapter" onclick="openChapter('electro')">Electrostatics</button>  
        <button class="chapter" onclick="openChapter('potential')">Electrostatic Potential</button>  
        <button class="chapter" onclick="openChapter('current')">Current Electricity</button>  
        <button class="chapter" onclick="openChapter('magnetism')">Magnetism</button>  
        <button class="chapter" onclick="openChapter('emi')">Electromagnetic Induction</button>  
        <button class="chapter" onclick="openChapter('ac')">Alternating Current</button>  
        <button class="chapter" onclick="openChapter('optics')">Optics</button>  
        <button class="chapter" onclick="openChapter('dual')">Dual Nature</button>  
        <button class="chapter" onclick="openChapter('atoms')">Atoms</button>  
        <button class="chapter" onclick="openChapter('nuclei')">Nuclei</button>  
        <button class="chapter" onclick="openChapter('semi')">Semiconductors</button>  
    </div>  

    <div id="chapterScreen" class="screen">    
        <h3 id="chapterTitle" style="color:#38bdf8;"></h3>    
        <div class="tabs">    
            <div class="tab-btn active" onclick="showTab('lecture')">Lecture</div>    
            <div class="tab-btn" onclick="showTab('notes')">Notes</div>    
        </div>    
        <div id="lectureTab">    
            <div id="videoButtons"></div>    
        </div>    
        <div id="notesTab" style="display:none;">    
            <button class="notes" onclick="openPDF()">📄 Download PDF Notes</button>    
        </div>  
    </div>  

    <div id="player" class="screen">    
        <h3 id="videoTitle"></h3>    
        <iframe id="videoFrame" frameborder="0" allowfullscreen allow="autoplay; fullscreen"></iframe>    
    </div>  

    <div id="socialLinks" class="floating">    
        <div onclick="openLink('https://www.instagram.com/edufinity_abhijit')" class="instagram-btn"><i class="fab fa-instagram"></i></div>    
        <div onclick="openLink('https://chat.whatsapp.com/F8nP43r3h7y3dobqk7qTI3')" class="whatsapp-btn"><i class="fab fa-whatsapp"></i></div>    
        <div onclick="openLink('https://www.facebook.com/share/1P6JqRg8JE/')" class="facebook-btn"><i class="fab fa-facebook-f"></i></div>    
    </div>  

    <script>    
        let currentChapter="";
        let historyStack=[];
        let currentSection="";

        let data={
            electro:{
                title:"Electrostatics",
                videos:[
                    "https://www.youtube.com/embed/GI5f4-8GbOs?autoplay=1",
                    "https://www.youtube.com/embed/o4wpmE32ab4?autoplay=1",
                    "https://www.youtube.com/embed/2zVKF4t78MQ?autoplay=1",
                    "https://www.youtube.com/embed/qC2b-u4IXX0?autoplay=1"
                ]
            },
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

        function openLink(url) {
            window.open(url, '_blank').focus();
        }

        function openSection(sec){
            currentSection=sec;
            historyStack.push("home");
            hideAll();
            document.getElementById("sectionScreen").classList.add("active");
            document.querySelector(".top-back").style.display="block";
            document.getElementById("sectionTitle").innerText=sec;
        }

        function openChapter(ch){
            currentChapter=ch;
            historyStack.push("section");
            hideAll();
            document.getElementById("chapterScreen").classList.add("active");
            document.getElementById("chapterTitle").innerText=data[ch].title;

            let container=document.getElementById("videoButtons");
            container.innerHTML="";

            if(currentSection==="jee"){
                container.innerHTML=`<div style="text-align:center; padding:20px; opacity:0.8;">
                <h3>📘 Coming Soon</h3>    
                <p>Study material is under preparation</p>    
                </div>`;    
                return;    
            }    
            
            data[ch].videos.forEach((v,i)=>{
                container.innerHTML+=`<button class="video" onclick="playVideo(${i})">${data[ch].title} - Part ${i+1}</button>`;
            });
        }

        function playVideo(i){
            historyStack.push("chapter");
            hideAll();
            let playerScreen = document.getElementById("player");
            let videoFrame = document.getElementById("videoFrame");
            
            playerScreen.classList.add("active");
            videoFrame.src = data[currentChapter].videos[i];
            document.getElementById("videoTitle").innerText = data[currentChapter].title;

            if (videoFrame.requestFullscreen) {
                videoFrame.requestFullscreen();
            } else if (videoFrame.webkitRequestFullscreen) {
                videoFrame.webkitRequestFullscreen();
            } else if (videoFrame.msRequestFullscreen) {
                videoFrame.msRequestFullscreen();
            }
        }

        function showTab(tab){
            document.getElementById("lectureTab").style.display = tab==="lecture"?"block":"none";
            document.getElementById("notesTab").style.display = tab==="notes"?"block":"none";
            
            document.querySelectorAll(".tab-btn").forEach(b=>b.classList.remove("active"));
            event.target.classList.add("active");
        }

        function openPDF(){
            window.open("YOUR_PDF_LINK","_blank");
        }

        function goBack(){
            if (document.fullscreenElement) {
                document.exitFullscreen();
            }
            document.getElementById("videoFrame").src="";
            let last=historyStack.pop();
            hideAll();

            if(last==="chapter") document.getElementById("chapterScreen").classList.add("active");
            else if(last==="section") document.getElementById("sectionScreen").classList.add("active");
            else {
                document.getElementById("home").classList.add("active");
                document.querySelector(".top-back").style.display="none";
            }
        }

        function hideAll(){
            document.querySelectorAll(".screen").forEach(s=>s.classList.remove("active"));
        }

        window.onload=()=>{
            setTimeout(()=>{
                let splash = document.getElementById("splash");
                let social = document.getElementById("socialLinks");
                
                splash.style.opacity = "0";
                
                setTimeout(() => {
                    splash.style.display = "none";
                    social.style.display = "flex";
                }, 600);
            }, 1500);
        };
    </script>  
</body>
