[preview.html](https://github.com/user-attachments/files/27959114/preview.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>PhishGuard AI</title>

  <!-- GOOGLE FONT -->
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;600;800&display=swap" rel="stylesheet">

  <style>

    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family:'Orbitron', sans-serif;
    }

    body{
      background:#050816;
      color:white;
      overflow-x:hidden;
    }

    /* BACKGROUND GLOW */
    body::before{
      content:'';
      position:fixed;
      width:500px;
      height:500px;
      background:#00f7ff33;
      border-radius:50%;
      top:-200px;
      left:-100px;
      filter:blur(120px);
      z-index:-1;
    }

    body::after{
      content:'';
      position:fixed;
      width:400px;
      height:400px;
      background:#ff00ff22;
      border-radius:50%;
      bottom:-150px;
      right:-100px;
      filter:blur(120px);
      z-index:-1;
    }

    /* NAVBAR */

    header{
      display:flex;
      justify-content:space-between;
      align-items:center;
      padding:25px 8%;
      backdrop-filter:blur(10px);
      background:rgba(255,255,255,0.03);
      border-bottom:1px solid rgba(255,255,255,0.08);
      position:sticky;
      top:0;
      z-index:1000;
    }

    .logo{
      font-size:30px;
      font-weight:800;
      color:#00f7ff;
      text-shadow:0 0 20px #00f7ff;
    }

    nav ul{
      display:flex;
      list-style:none;
      gap:30px;
    }

    nav ul li a{
      text-decoration:none;
      color:white;
      transition:0.3s;
      font-size:14px;
    }

    nav ul li a:hover{
      color:#00f7ff;
    }

    /* HERO SECTION */

    .hero{
      min-height:100vh;
      display:flex;
      justify-content:center;
      align-items:center;
      flex-direction:column;
      text-align:center;
      padding:40px;
    }

    .hero h1{
      font-size:75px;
      max-width:1000px;
      line-height:1.1;
      background:linear-gradient(to right,#00f7ff,#8f00ff);
      -webkit-background-clip:text;
      -webkit-text-fill-color:transparent;
      margin-bottom:25px;
    }

    .hero p{
      color:#c7c7c7;
      font-size:20px;
      max-width:700px;
      line-height:1.8;
      margin-bottom:40px;
    }

    .hero button{
      padding:18px 40px;
      border:none;
      border-radius:15px;
      background:linear-gradient(135deg,#00f7ff,#8f00ff);
      color:white;
      font-size:16px;
      cursor:pointer;
      transition:0.4s;
      box-shadow:0 0 25px #00f7ff55;
    }

    .hero button:hover{
      transform:translateY(-5px) scale(1.03);
      box-shadow:0 0 40px #00f7ff99;
    }

    /* GLASS CARDS */

    .dashboard{
      padding:80px 8%;
    }

    .dashboard-title{
      text-align:center;
      font-size:50px;
      margin-bottom:60px;
      color:#00f7ff;
    }

    .cards{
      display:grid;
      grid-template-columns:repeat(auto-fit,minmax(280px,1fr));
      gap:30px;
    }

    .card{
      background:rgba(255,255,255,0.05);
      border:1px solid rgba(255,255,255,0.1);
      backdrop-filter:blur(15px);
      border-radius:25px;
      padding:35px;
      transition:0.4s;
      position:relative;
      overflow:hidden;
    }

    .card::before{
      content:'';
      position:absolute;
      width:150px;
      height:150px;
      background:#00f7ff22;
      border-radius:50%;
      top:-50px;
      right:-50px;
    }

    .card:hover{
      transform:translateY(-10px);
      border-color:#00f7ff;
      box-shadow:0 0 35px #00f7ff33;
    }

    .card h2{
      font-size:45px;
      margin-bottom:15px;
      color:#00f7ff;
    }

    .card h3{
      margin-bottom:15px;
      font-size:22px;
    }

    .card p{
      color:#c7c7c7;
      line-height:1.8;
      font-size:14px;
    }

    /* URL SCANNER */

    .scanner{
      padding:100px 8%;
      text-align:center;
    }

    .scanner h1{
      font-size:55px;
      margin-bottom:20px;
      color:#00f7ff;
    }

    .scanner p{
      color:#aaa;
      margin-bottom:40px;
    }

    .scanner-box{
      max-width:800px;
      margin:auto;
      background:rgba(255,255,255,0.05);
      padding:40px;
      border-radius:25px;
      backdrop-filter:blur(20px);
      border:1px solid rgba(255,255,255,0.1);
    }

    .scanner input{
      width:100%;
      padding:18px;
      border:none;
      outline:none;
      border-radius:12px;
      background:#0f172a;
      color:white;
      margin-bottom:25px;
      border:1px solid #1e293b;
      font-size:15px;
    }

    .scanner button{
      padding:16px 35px;
      border:none;
      border-radius:12px;
      background:linear-gradient(135deg,#00f7ff,#8f00ff);
      color:white;
      cursor:pointer;
      transition:0.4s;
      font-size:15px;
    }

    .scanner button:hover{
      box-shadow:0 0 30px #00f7ff77;
      transform:scale(1.03);
    }

    /* FOOTER */

    footer{
      text-align:center;
      padding:30px;
      border-top:1px solid rgba(255,255,255,0.08);
      color:#888;
      margin-top:60px;
    }

    /* RESPONSIVE */

    @media(max-width:768px){

      .hero h1{
        font-size:45px;
      }

      nav{
        display:none;
      }

      .dashboard-title{
        font-size:35px;
      }

      .scanner h1{
        font-size:38px;
      }

    }

  </style>
</head>

<body>

  <!-- NAVBAR -->

  <header>

    <div class="logo">PHISHGUARD AI</div>

    <nav>
      <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">Scanner</a></li>
        <li><a href="#">Threats</a></li>
        <li><a href="#">Passwords</a></li>
      </ul>
    </nav>

  </header>

  <!-- HERO -->

  <section class="hero">

    <h1>Advanced Cyber Threat Detection Dashboard</h1>

    <p>
      Detect phishing attacks, scan malicious URLs,
      analyze password strength and protect your digital identity.
    </p>

    <button>Launch Scanner</button>

  </section>

  <!-- DASHBOARD -->

  <section class="dashboard">

    <h1 class="dashboard-title">Live Security Stats</h1>

    <div class="cards">

      <div class="card">
        <h2>124</h2>
        <h3>Threats Blocked</h3>
        <p>
          Dangerous phishing and malware attacks blocked in real time.
        </p>
      </div>

      <div class="card">
        <h2>53</h2>
        <h3>Phishing URLs</h3>
        <p>
          Suspicious links detected using smart cyber analysis.
        </p>
      </div>

      <div class="card">
        <h2>210</h2>
        <h3>Passwords Checked</h3>
        <p>
          Password strength analyzed for better online protection.
        </p>
      </div>

    </div>

  </section>

  <!-- URL SCANNER -->

  <section class="scanner">

    <h1>Phishing URL Scanner</h1>

    <p>Enter a suspicious website link below</p>

    <div class="scanner-box">

      <input type="text" placeholder="https://suspicious-site.com">

      <button>Analyze URL</button>

    </div>

  </section>

  <!-- FOOTER -->

  <footer>
    © 2026 PHISHGUARD AI | Cyber Security Project By Praneeth
  </footer>

</body>
</html>
