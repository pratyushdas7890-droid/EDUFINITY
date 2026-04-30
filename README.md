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
    position: relative;
    min-height: 100vh;
}

/* Cinematic Galaxy Background with Parallax */
.galaxy-bg {
    position: fixed;
    top: -10%; left: -10%; width: 120%; height: 120%;
    z-index: -2;
    background: url('https://images.unsplash.com/photo-1462331940025-496dfbfc7564?q=80&w=2022&auto=format&fit=crop') no-repeat center center;
    background-size: cover;
    transition: transform 0.1s ease-out;
    will-change: transform;
}

.overlay {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    z-index: -1;
    background: rgba(2, 6, 23, 0.4);
}

#splash {
    position: fixed;
    top: 0; left: 0; width: 100%; height: 100%;
    background: #ffffff;
    display: flex; align-items: center; justify-content: center;
    z-index: 10000;
    transition: 0.6s ease;
}

/* Splash Logo Glow Restored */
#splash img {
    width: 160px;
    border-radius: 20px;
    filter: drop-shadow(0 0 15px rgba(56, 189, 248, 0.7));
    animation: quantumPulse 2s infinite ease-in-out;
}

@keyframes quantumPulse {
    0%, 100% { transform: scale(1); opacity: 1; }
    50% { transform: scale(1.05); opacity: 0.9; }
}

/* --- Rounded Glass Floating Header --- */
.header {
    text-align: center;
    padding: 25px 20px;
    position: sticky; 
    top: 15px; /* স্ক্রিনের মাথা থেকে একটু গ্যাপ */
    margin: 0 15px 20px; /* চারিদিকে গ্যাপ দিয়ে ভাসমান করা হলো */
    z-index: 500;
    
    /* গ্লাস ডিজাইন */
    background: rgba(255, 255, 255, 0.05); 
    backdrop-filter: blur(15px) saturate(180%);
    -webkit-backdrop-filter: blur(15px) saturate(180%);
    border: 1px solid rgba(255, 255, 255, 0.2); /* চারিদিকের বর্ডার */
    border-radius: 30px; /* চারিধার কাটা রাউন্ড */
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.5);
}

/* Heading Glow Restored */
.header h1 {
    margin: 10px 0 0;
    font-family: 'Orbitron', sans-serif;
    font-size: 28px;
    font-weight: 900;
    letter-spacing: 5px;
    background: linear-gradient(90deg, #fff, #38bdf8, #818cf8, #fff);
    background-size: 200% auto;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: glowText 3s linear infinite;
}

@keyframes glowText { to { background-position: 200% center; } }

.header .tagline {
    margin-top: 5px;
    font-family: 'Exo 2', sans-serif;
    font-size: 11px;
    color: #38bdf8;
    font-weight: 700;
    letter-spacing: 1.5px;
    text-transform: uppercase;
}

.logo-circle { 
    width: 70px; height: 70px; border-radius: 50%; 
    margin: 0 auto; display: block; object-fit: cover; 
    border: 2px solid rgba(56, 189, 248, 0.6);
    box-shadow: 0 0 20px rgba(56, 189, 248, 0.4); 
}

/* Home Buttons */
.home-glass-btn {
    width: 100%; margin: 15px 0; padding: 20px; border-radius: 20px; cursor: pointer;
    background: transparent; border: 2px solid rgba(255, 255, 255, 0.6); 
    color: #fff; font-family: 'Poppins', sans-serif; font-size: 16px; font-weight: 600;
    text-transform: uppercase; letter-spacing: 2px; text-align: center;
    transition: 0.3s ease; position: relative; overflow: hidden; outline: none;
}

.ripple {
    position: absolute; background: radial-gradient(circle, rgba(56, 189, 248, 0.8) 0%, transparent 70%);
    border-radius: 50%; transform: scale(0); animation: stylish-ripple 0.4s cubic-bezier(0.23, 1, 0.32, 1);
    pointer-events: none;
}
@keyframes stylish-ripple { to { transform: scale(3); opacity: 0; } }

/* Chapter Card Animation */
.chapter {
    display: flex; justify-content: space-between; align-items: center;
    width: 100%; margin: 12px 0; padding: 18px 20px;
    border: 1px solid rgba(56, 189, 248, 0.2); border-radius: 20px;
    cursor: pointer; color: white; font-size: 15px; font-weight: 600;
    background: rgba(255, 255, 255, 0.05); backdrop-filter: blur(5px);
    transition: 0.3s; opacity: 0; transform: translateY(20px);
}
.reveal { animation: revealItem 0.5s ease forwards; }
@keyframes revealItem { to { opacity: 1; transform: translateY(0); } }

/* Progress Bubble Original */
.prog-bubble {
    position: relative; width: 55px; background: rgba(0, 0, 0, 0.4); 
    padding: 4px 0; border-radius: 8px; font-size: 11px; color: #fff; 
    border: 1px solid rgba(255, 255, 255, 0.2); text-align: center;
    overflow: hidden; z-index: 1;
}

.prog-bubble::before {
    content: ""; position: absolute; top: 0; left: 0; height: 100%;
    width: var(--p-width, 0%); background: rgba(16, 185, 129, 0.7);
    transition: width 0.5s ease-in-out; z-index: -1;
}

.top-back {
    position: absolute; left: 15px; top: 15px;
    background: rgba(239, 68, 68, 0.9); padding: 8px 16px; border-radius: 12px;
    font-size: 12px; font-weight: bold; cursor: pointer; display: none; z-index: 1000;
}

.screen { display: none; padding: 10px 20px 80px; max-width: 520px; margin: auto; }
.active { display: block; }

.video-btn { width: 100%; margin: 12px 0; padding: 18px; border-radius: 18px; cursor: pointer; color: white; font-size: 16px; font-weight: 600; border: none; background: linear-gradient(135deg, #059669, #10b981); text-align: center; }
.notes-btn { width: 100%; margin: 12px 0; padding: 18px; border-radius: 18px; cursor: pointer; color: white; font-size: 16px; font-weight: 600; border: none; background: linear-gradient(135deg, #d97706, #f59e0b); text-align: center; }

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

    <div class="galaxy-bg" id="parallaxBg"></div>
    <div class="overlay"></div>

    <div class="header">    
        <div class="top-back" onclick="goBack()">Back</div>    
        <img src="https://i.ibb.co/3YPtmZMM/Screenshot.png" class="logo-circle">   
        <h1>EDUFINITY</h1>     
        <div class="tagline">চলো এবার Physics কে Feel করা যাক</div>    
    </div>  

    <div id="home" class="screen active">    
        <h3 style="text-align:center; color:#38bdf8; font-family:'Exo 2'; text-transform:uppercase; margin-bottom: 25px;">📚 Physics Courses</h3>    
        <button class="home-glass-btn" onclick="handleButtonClick(event, 'boards')">Boards Exam</button>    
        <button class="home-glass-btn" onclick="handleButtonClick(event, 'jee')">JEE / NEET Entrance</button>    
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
        <div id="lectureTab"><div id="videoButtons"></div></div>    
        <div id="notesTab" style="display:none;"><button class="notes-btn" onclick="openPDF()">📄 Download PDF Notes</button></div>  
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
            electro:{ title:"Electrostatics", videos:["https://www.youtube.com/embed/GI5f4-8GbOs?autoplay=1","https://www.youtube.com/embed/o4wpmE32ab4?autoplay=1","https://www.youtube.com/embed/2zVKF4t78MQ?autoplay=1","https://www.youtube.com/embed/qC2b-u4IXX0?autoplay=1"]},
            potential:{title:"Electrostatic Potential",videos:[]}, current:{title:"Current Electricity",videos:[]},
            magnetism:{title:"Magnetism",videos:[]}, emi:{title:"Electromagnetic Induction",videos:[]},
            ac:{title:"Alternating Current",videos:[]}, optics:{title:"Optics",videos:[]},
            dual:{title:"Dual Nature",videos:[]}, atoms:{title:"Atoms",videos:[]},
            nuclei:{title:"Nuclei",videos:[]}, semi:{title:"Semiconductors",videos:[]}
        };

        // Parallax
        document.addEventListener('mousemove', (e) => {
            const bg = document.getElementById('parallaxBg');
            const x = (window.innerWidth / 2 - e.pageX) / 35;
            const y = (window.innerHeight / 2 - e.pageY) / 35;
            bg.style.transform = `translate(${x}px, ${y}px)`;
        });

        function handleButtonClick(event, section) {
            const button = event.currentTarget;
            const ripple = document.createElement("span");
            const rect = button.getBoundingClientRect();
            const size = Math.max(rect.width, rect.height);
            ripple.style.width = ripple.style.height = `${size}px`;
            ripple.style.left = `${event.clientX - rect.left}px`;
            ripple.style.top = `${event.clientY - rect.top}px`;
            ripple.classList.add("ripple");
            button.appendChild(ripple);
            setTimeout(() => { ripple.remove(); openSection(section); }, 200);
        }

        function openSection(sec){
            currentSection=sec; historyStack.push("home"); hideAll();
            document.getElementById("sectionScreen").classList.add("active");
            document.querySelector(".top-back").style.display="block";
            document.getElementById("sectionTitle").innerText=sec;
            const chapters = document.querySelectorAll('.chapter');
            chapters.forEach((ch, index) => {
                ch.classList.remove('reveal');
                setTimeout(() => { ch.classList.add('reveal'); }, index * 80);
            });
            refreshProgUI();
            window.scrollTo(0,0);
        }

        function refreshProgUI(){
            Object.keys(data).forEach(key => {
                let el = document.getElementById(key + "-prog");
                if(el) {
                    let val = (currentSection === "boards") ? (progressData[key] || 0) : 0;
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
            } else { container.innerHTML=`<div style="text-align:center; padding:20px; opacity:0.8;"><h3>📘 Coming Soon</h3></div>`; }
            window.scrollTo(0,0);
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
        function openLink(url) { window.open(url, '_blank').focus(); }
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
