<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AWS Cloud Club KIET · dark UI + animations</title>
  <!-- Font & Icons -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background-color: #0b0d12;
      background-image: radial-gradient(circle at 20% 30%, rgba(10, 50, 70, 0.2) 0%, transparent 30%),
                        radial-gradient(circle at 80% 70%, rgba(30, 60, 120, 0.15) 0%, transparent 35%),
                        linear-gradient(145deg, #0a0c10 0%, #0f121a 100%);
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
      color: #e2e8f0;
      line-height: 1.6;
      padding: 2rem 1.5rem;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      animation: fadeGlow 1.8s ease-out;
    }

    @keyframes fadeGlow {
      0% { opacity: 0; background-color: #030507; }
      100% { opacity: 1; }
    }

    .container {
      max-width: 1100px;
      width: 100%;
    }

    /* sleek glass card effect */
    .card {
      background: rgba(18, 22, 30, 0.7);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid rgba(64, 128, 255, 0.18);
      border-radius: 36px;
      box-shadow: 0 20px 40px -15px rgba(0,0,0,0.6), 0 0 0 1px rgba(0, 255, 255, 0.02) inset;
      padding: 2.2rem 2.5rem;
      transition: transform 0.25s ease, box-shadow 0.3s ease, border-color 0.2s;
    }

    .card:hover {
      border-color: rgba(0, 180, 255, 0.4);
      box-shadow: 0 30px 55px -18px #0088ff30, 0 0 0 1px rgba(0, 225, 255, 0.1) inset;
    }

    /* logo animation */
    .logo-wrapper {
      display: flex;
      justify-content: center;
      margin-bottom: 1.2rem;
    }

    .logo-glow {
      width: 130px;
      height: auto;
      filter: drop-shadow(0 0 12px #3a86ff80) drop-shadow(0 0 30px #0055aa60);
      transition: all 0.4s cubic-bezier(0.2, 0.9, 0.4, 1);
      animation: floatLogo 5s infinite ease-in-out;
    }

    .logo-glow:hover {
      filter: drop-shadow(0 0 24px #60a5fa) drop-shadow(0 0 45px #2563eb);
      transform: scale(1.02);
    }

    @keyframes floatLogo {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-6px); }
      100% { transform: translateY(0px); }
    }

    h1, h2, h3 {
      font-weight: 700;
      letter-spacing: -0.02em;
    }

    h1 {
      font-size: 2.7rem;
      font-weight: 800;
      background: linear-gradient(145deg, #f0f9ff, #b0d4ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-bottom: 0.4rem;
      text-shadow: 0 0 8px #0066ff40, 0 0 20px #003cff1a;
    }

    .subhead {
      font-size: 1.2rem;
      font-weight: 500;
      color: #9dbdea;
      margin-bottom: 1.8rem;
    }

    /* badges with subtle animation */
    .badge-container {
      display: flex;
      flex-wrap: wrap;
      gap: 0.8rem;
      justify-content: center;
      margin: 1.5rem 0 1rem;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: rgba(0, 30, 60, 0.7);
      backdrop-filter: blur(4px);
      border: 1px solid #2a4c7c;
      padding: 0.5rem 1.3rem;
      border-radius: 60px;
      font-size: 0.95rem;
      font-weight: 600;
      color: #d4e6ff;
      transition: all 0.2s;
      box-shadow: 0 2px 6px #00000040;
    }

    .badge i {
      color: #72b2ff;
      font-size: 0.9rem;
    }

    .badge:hover {
      background: #0f2e4a;
      border-color: #60a5fa;
      color: white;
      transform: translateY(-2px);
      box-shadow: 0 12px 18px -8px #0a1e3280;
    }

    /* section titles */
    .section-title {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 1.9rem;
      font-weight: 700;
      margin: 2.5rem 0 1.5rem 0;
      color: #c9e2ff;
      border-bottom: 2px solid #264d70;
      padding-bottom: 0.65rem;
      letter-spacing: -0.01em;
    }

    .section-title i {
      color: #78b9ff;
      text-shadow: 0 0 10px #0077ff;
    }

    /* timeline glow */
    .timeline-item {
      display: flex;
      flex-direction: column;
      margin-bottom: 2.5rem;
      padding: 1.6rem 1.8rem;
      background: rgba(10, 16, 28, 0.55);
      backdrop-filter: blur(10px);
      border-radius: 28px;
      border: 1px solid rgba(0, 150, 255, 0.1);
      transition: all 0.35s;
      position: relative;
      animation: slideReveal 0.7s ease forwards;
      opacity: 0;
      transform-origin: top;
    }

    .timeline-item:nth-child(1) { animation-delay: 0.1s; }
    .timeline-item:nth-child(2) { animation-delay: 0.2s; }
    .timeline-item:nth-child(3) { animation-delay: 0.3s; }
    .timeline-item:nth-child(4) { animation-delay: 0.4s; }
    .timeline-item:nth-child(5) { animation-delay: 0.5s; }

    @keyframes slideReveal {
      0% { opacity: 0; transform: translateY(30px) scale(0.97); }
      100% { opacity: 1; transform: translateY(0) scale(1); }
    }

    .timeline-item:hover {
      background: rgba(16, 26, 45, 0.8);
      border-color: #3579b0;
      box-shadow: 0 20px 30px -12px #001e3c, 0 0 0 1px #3399ff1a;
      transform: scale(1.01) translateY(-3px);
    }

    .event-header {
      display: flex;
      flex-wrap: wrap;
      align-items: baseline;
      justify-content: space-between;
      margin-bottom: 0.6rem;
    }

    .event-name {
      font-size: 1.8rem;
      font-weight: 700;
      background: linear-gradient(135deg, #f0f6ff, #b3d9ff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      letter-spacing: -0.01em;
    }

    .event-badge {
      background: #0d2f4b;
      padding: 0.3rem 1.1rem;
      border-radius: 40px;
      font-size: 0.8rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 0.8px;
      color: #b0e4ff;
      border: 1px solid #306a92;
      box-shadow: 0 0 8px #005c9e4d;
    }

    .event-date {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      background: #0a1a29;
      padding: 0.3rem 1rem;
      border-radius: 40px;
      font-size: 0.85rem;
      font-weight: 600;
      color: #bbe1ff;
      border: 0.5px solid #20496b;
    }

    .event-date i {
      color: #84c5ff;
    }

    .overview {
      margin-top: 1.2rem;
      font-size: 1.05rem;
      color: #cddcf2;
      padding-left: 0.3rem;
      border-left: 4px solid #006bb3;
      padding-left: 1.2rem;
    }

    .overview i {
      color: #5faaff;
      margin-right: 6px;
    }

    ul {
      list-style: none;
    }

    .feature-list {
      display: flex;
      flex-wrap: wrap;
      gap: 1.2rem;
      margin-top: 1rem;
    }

    .feature-list li {
      background: rgba(21, 46, 70, 0.6);
      backdrop-filter: blur(4px);
      padding: 0.55rem 1.3rem;
      border-radius: 40px;
      font-size: 0.95rem;
      font-weight: 500;
      border: 0.5px solid #285e85;
      transition: 0.15s;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .feature-list li:hover {
      background: #1f405e;
      border-color: #7bb3ff;
      transform: translateY(-2px);
    }

    .feature-list i {
      color: #7bb3ff;
    }

    /* what you'll find grid */
    .resource-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 1.2rem;
      margin: 2rem 0 1.5rem;
    }

    .resource-item {
      background: rgba(12, 25, 40, 0.6);
      backdrop-filter: blur(6px);
      border: 1px solid #1f4968;
      border-radius: 20px;
      padding: 1.3rem 0.8rem;
      text-align: center;
      transition: all 0.25s;
      font-weight: 600;
      color: #d1e2ff;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
    }

    .resource-item i {
      font-size: 2rem;
      color: #75b6ff;
      filter: drop-shadow(0 0 8px #0055aa);
    }

    .resource-item:hover {
      background: #123a52;
      border-color: #0099ff;
      transform: translateY(-8px) scale(1.02);
      box-shadow: 0 18px 25px -12px #001e3c;
    }

    /* footer */
    .footer {
      margin-top: 4rem;
      padding: 2rem 1.8rem;
      text-align: center;
      background: rgba(8, 18, 28, 0.7);
      backdrop-filter: blur(12px);
      border-radius: 48px;
      border: 1px solid #20588233;
      transition: 0.2s;
    }

    .footer:hover {
      border-color: #4080aa;
    }

    .footer b {
      font-size: 1.4rem;
      font-weight: 700;
      background: linear-gradient(145deg, #b8dcff, #dfebff);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .footer i {
      font-style: normal;
      color: #9ac6ff;
      letter-spacing: 2px;
    }

    hr {
      border: 0.5px solid #1e3f5a;
      margin: 2rem 0 1rem;
    }

    /* typography */
    p {
      color: #d2e0f0;
    }

    .repo-badge {
      display: inline-block;
      background: #0e1e2b;
      border-radius: 100px;
      padding: 0.4rem 1.3rem;
      margin-bottom: 0.8rem;
      font-size: 0.8rem;
      border: 1px solid #286482;
      color: #aad3ff;
      font-weight: 600;
    }

    /* responsive */
    @media (max-width: 700px) {
      .container { padding: 0; }
      .card { padding: 1.5rem; }
      h1 { font-size: 2rem; }
      .event-name { font-size: 1.4rem; }
    }

    /* custom aws accent */
    .aws-accent {
      color: #99ccff;
    }

    .glow-text {
      color: #c8e2ff;
      text-shadow: 0 0 8px #0077be40;
    }

    .btn-ghost {
      border: 1px solid #3388dd;
      border-radius: 30px;
      padding: 0.3rem 1.2rem;
      background: transparent;
      transition: 0.2s;
    }

    .btn-ghost:hover {
      background: #0077bb20;
    }

    i {
      color: #70b8ff;
    }
  </style>
</head>
<body>
  <div class="container">

    <!-- main card with logo / header -->
    <div class="card" style="margin-bottom: 2.8rem; text-align: center;">
      <div class="logo-wrapper">
        <img src="https://raw.githubusercontent.com/aws-cloud-club-kiet/assets/main/logo.png" alt="AWS Cloud Club KIET" class="logo-glow" width="120">
      </div>
      
      <h1>AWS Cloud Club KIET</h1>
      <p class="subhead" style="margin-bottom: 0.5rem;">
        <span style="background: rgba(0,200,255,0.12); padding: 0.3rem 1.2rem; border-radius: 60px; backdrop-filter: blur(4px);">
          <i class="fas fa-archive" style="margin-right: 8px;"></i>single source of truth · events · workshops · bootcamps
        </span>
      </p>
      
      <div class="badge-container">
        <span class="badge"><i class="fas fa-users"></i> Community AWS Cloud Club</span>
        <span class="badge"><i class="fas fa-cloud"></i> Domain Cloud | DevOps | Linux</span>
        <span class="badge"><i class="fas fa-bolt"></i> Status Active</span>
      </div>

      <p style="max-width: 700px; margin: 1.8rem auto 0.4rem; font-size: 1.08rem; color: #c2dafe;">
        This repository acts as the <strong style="color:white;">single source of truth</strong> for all technical initiatives conducted by  
        <strong style="color:#b3d9ff;">AWS Cloud Club KIET</strong>.
      </p>
      <div style="display: flex; gap: 0.7rem; justify-content: center; margin-top: 1.4rem; flex-wrap: wrap;">
        <span style="background: #0e283b; padding: 0.4rem 1.2rem; border-radius: 30px;"><i class="far fa-calendar-alt"></i> 📅 Events</span>
        <span style="background: #0e283b; padding: 0.4rem 1.2rem; border-radius: 30px;"><i class="fas fa-laptop-code"></i> 🧑‍💻 Workshops</span>
        <span style="background: #0e283b; padding: 0.4rem 1.2rem; border-radius: 30px;"><i class="fas fa-rocket"></i> 🚀 Bootcamps</span>
      </div>
    </div>

    <!-- TIMELINE SECTION -->
    <div class="section-title">
      <i class="fas fa-timeline" style="font-size: 2rem;"></i> 
      <span>📅 Events, Workshops & Bootcamps Timeline</span>
      <span style="font-size: 0.9rem; font-weight: 400; margin-left: 12px; background: #112f42; padding: 0.2rem 1rem; border-radius: 60px;">ascending order</span>
    </div>

    <!-- EVENT 1 -->
    <div class="timeline-item">
      <div class="event-header">
        <span class="event-name">🎓 Student Induction Program</span>
        <span class="event-badge"><i class="fas fa-flag"></i> Event</span>
      </div>
      <div style="display: flex; gap: 0.8rem; flex-wrap: wrap; align-items: center;">
        <span class="event-date"><i class="fas fa-calendar"></i> 12 September 2025</span>
      </div>
      <div class="overview">
        <i class="fas fa-bullhorn"></i> <strong>Overview:</strong> Introduction to AWS Cloud Club KIET · Overview of Cloud, DevOps & Club Roadmap · Orientation for first-year students.
      </div>
      <ul class="feature-list">
        <li><i class="fas fa-cloud"></i> cloud introduction</li>
        <li><i class="fas fa-users"></i> first-year connect</li>
        <li><i class="fas fa-road"></i> roadmap reveal</li>
      </ul>
    </div>

    <!-- EVENT 2 -->
    <div class="timeline-item">
      <div class="event-header">
        <span class="event-name">☁️ CloudNova</span>
        <span class="event-badge"><i class="fas fa-fire"></i> Bootcamp · 3D</span>
      </div>
      <div style="display: flex; gap: 0.8rem; flex-wrap: wrap;">
        <span class="event-date"><i class="fas fa-calendar-alt"></i> 23 Sep – 25 Sep 2025</span>
      </div>
      <div class="overview">
        <i class="fas fa-cube"></i> <strong>Overview:</strong> Cloud Fundamentals (AWS) · Linux Basics for Cloud · Compute, Storage & Networking · Hands-on Cloud Labs.
      </div>
      <ul class="feature-list">
        <li><i class="fas fa-server"></i> AWS essentials</li>
        <li><i class="fab fa-linux"></i> Linux CLI</li>
        <li><i class="fas fa-database"></i> storage & networking</li>
        <li><i class="fas fa-microchip"></i> hands-on labs</li>
      </ul>
    </div>

    <!-- EVENT 3 -->
    <div class="timeline-item">
      <div class="event-header">
        <span class="event-name">🏆 Innotech KIET – CloudFusion</span>
        <span class="event-badge"><i class="fas fa-trophy"></i> Event</span>
      </div>
      <div style="display: flex; gap: 0.8rem;">
        <span class="event-date"><i class="fas fa-calendar"></i> 15 November 2025</span>
      </div>
      <div class="overview">
        <i class="fas fa-puzzle-piece"></i> <strong>Overview:</strong> Cloud-focused competition track · Problem-solving using AWS concepts · Team-based technical challenge.
      </div>
      <ul class="feature-list">
        <li><i class="fas fa-users-between-lines"></i> team challenge</li>
        <li><i class="fas fa-brain"></i> problem solving</li>
        <li><i class="fas fa-aws"></i> AWS in action</li>
      </ul>
    </div>

    <!-- EVENT 4 -->
    <div class="timeline-item">
      <div class="event-header">
        <span class="event-name">🤖 Build AI Games with Python × Amazon Q</span>
        <span class="event-badge"><i class="fas fa-paint-brush"></i> Workshop · 1D</span>
      </div>
      <div style="display: flex; gap: 0.8rem;">
        <span class="event-date"><i class="fas fa-calendar"></i> 28 November 2025</span>
      </div>
      <div class="overview">
        <i class="fas fa-robot"></i> <strong>Overview:</strong> Python for Game Logic · Introduction to Amazon Q · AI-assisted Development.
      </div>
      <ul class="feature-list">
        <li><i class="fab fa-python"></i> python game dev</li>
        <li><i class="fas fa-microchip-ai"></i> amazon Q</li>
        <li><i class="fas fa-wand-magic-sparkles"></i> AI pair programming</li>
      </ul>
    </div>

    <!-- EVENT 5 -->
    <div class="timeline-item">
      <div class="event-header">
        <span class="event-name">🐳 Containerization 101</span>
        <span class="event-badge"><i class="fas fa-ship"></i> Bootcamp · 2D</span>
      </div>
      <div style="display: flex; gap: 0.8rem;">
        <span class="event-date"><i class="fas fa-calendar"></i> 23 Feb – 24 Feb 2026</span>
      </div>
      <div class="overview">
        <i class="fas fa-box"></i> <strong>Overview:</strong> Containers & Docker Fundamentals · Docker CLI Hands-on · Containerizing Real Applications.
      </div>
      <ul class="feature-list">
        <li><i class="fab fa-docker"></i> docker basics</li>
        <li><i class="fas fa-terminal"></i> CLI deep dive</li>
        <li><i class="fas fa-cubes"></i> real-world container</li>
      </ul>
    </div>

    <!-- What you'll find here / repository features -->
    <div class="section-title" style="margin-top: 3rem;">
      <i class="fas fa-map" style="font-size: 2rem;"></i>
      <span>🗂️ What You’ll Find Here</span>
    </div>

    <div style="background: rgba(12, 22, 34, 0.6); backdrop-filter: blur(8px); border-radius: 36px; padding: 2rem 2rem; border: 1px solid #1f4b66; transition: 0.3s;">
      <div class="resource-grid">
        <div class="resource-item">
          <i class="fas fa-clipboard-list"></i>
          <span>Event summaries & schedules</span>
        </div>
        <div class="resource-item">
          <i class="fas fa-book-open"></i>
          <span>Learning resources & references</span>
        </div>
        <div class="resource-item">
          <i class="fas fa-terminal"></i>
          <span>Hands-on labs and commands</span>
        </div>
        <div class="resource-item">
          <i class="fas fa-file-alt"></i>
          <span>Reusable documentation templates</span>
        </div>
      </div>
      <p style="text-align: center; margin-top: 0.8rem; color: #b1d4ff; font-weight: 400;">
        <i class="fas fa-circle-check" style="color: #65b6ff;"></i> structured, chronological, built for learning continuity.
      </p>
    </div>

    <!-- FOOTER with motto -->
    <div class="footer">
      <div style="display: flex; align-items: center; justify-content: center; gap: 16px; flex-wrap: wrap;">
        <span style="font-size: 1.6rem;">☁️</span>
        <div>
          <b>Maintained by AWS Cloud Club KIET</b><br>
          <span style="font-size: 1.2rem; font-weight: 600; background: linear-gradient(145deg, #aad0ff, #fff); -webkit-background-clip: text; background-clip: text; color: transparent;">
            <i>Learn • Build • Grow</i>
          </span>
        </div>
        <span style="font-size: 1.6rem;">⚡</span>
      </div>
      <div style="margin-top: 1.2rem; display: flex; gap: 12px; justify-content: center; color: #95bde6;">
        <span style="border-right: 1px solid #457a9e; padding-right: 16px;"><i class="fab fa-aws"></i> cloud club</span>
        <span><i class="fas fa-code-branch"></i> open repo</span>
      </div>
    </div>

    <!-- tiny meta line -->
    <p style="text-align: center; margin-top: 2rem; font-size: 0.75rem; color: #5e84a2; letter-spacing: 1px;">
      <i class="fas fa-crown"></i> AWS Cloud Club KIET — official documentation hub · dark theme + smooth animations
    </p>
  </div>

  <!-- subtle hover glow global -->
  <div style="position: fixed; bottom: 20px; right: 30px; opacity: 0.5; pointer-events: none;">
    <i class="fas fa-circle" style="color: #006bb3; font-size: 0.6rem; text-shadow: 0 0 20px #0099ff;"></i>
    <i class="fas fa-circle" style="color: #003f66; margin-left: 6px; font-size: 0.6rem;"></i>
  </div>
</body>
</html>
