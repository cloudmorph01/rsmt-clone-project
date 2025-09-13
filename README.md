
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>RSMT — Student Clone</title>
  <meta name="description" content="RSMT (Rajarshi School of Management & Technology) — demo clone built with HTML & CSS by student." />
  <!-- Google font (optional) -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
  <style>
    /* Reset & variables */
    :root{
      --accent:#0b63d6;
      --dark:#0b2540;
      --muted:#6b7280;
      --bg:#f5f7fb;
      --card:#ffffff;
      --radius:12px;
      --container:1100px;
      --gap:18px;
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;
    }
    *{box-sizing:border-box}
    body{margin:0;background:var(--bg);color:#0b2540;line-height:1.5}
    .container{max-width:var(--container);margin:0 auto;padding:28px}
    /* Header */
    header.site-header{background:var(--card);box-shadow:0 6px 18px rgba(11,37,64,0.06);position:sticky;top:0;z-index:60}
    .header-inner{display:flex;align-items:center;justify-content:space-between;gap:12px;padding:12px 20px}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{width:56px;height:56px;border-radius:10px;background:linear-gradient(135deg,var(--accent),#2a9df4);display:flex;align-items:center;justify-content:center;color:#fff;font-weight:700;font-size:22px}
    .brand h1{margin:0;font-size:18px}
    .brand p{margin:0;font-size:12px;color:var(--muted)}
    nav.main-nav{display:flex;gap:12px;align-items:center}
    nav.main-nav a{color:var(--dark);text-decoration:none;padding:8px 10px;border-radius:8px;font-weight:600}
    .btn{background:var(--accent);color:#fff;padding:8px 12px;border-radius:8px;text-decoration:none}
    .btn.ghost{background:transparent;border:2px solid var(--accent);color:var(--accent)}
    .nav-toggle{display:none;border:0;background:none;font-size:22px;padding:8px}
    /* Hero */
    .hero{padding:44px 0;background:linear-gradient(180deg,#eef6ff00 0%, #eef6ff 100%)}
    .hero-grid{display:grid;grid-template-columns:1fr 520px;gap:28px;align-items:center}
    .hero-left h2{font-size:30px;margin:0 0 12px}
    .hero-left p{margin:0 0 18px;color:var(--muted)}
    .hero-cta{display:flex;gap:12px}
    .hero-card{background:var(--card);border-radius:14px;box-shadow:0 8px 30px rgba(11,37,64,0.06);overflow:hidden}
    .hero-card img{display:block;width:100%;height:auto}
    .caption{padding:10px 14px;margin:0;color:var(--muted);font-size:13px}
    /* Sections */
    section{padding:28px 0}
    h3.section-title{margin:0 0 14px;font-size:20px}
    .cards{display:flex;gap:14px;flex-wrap:wrap}
    .card{background:var(--card);padding:16px;border-radius:12px;flex:1;min-width:200px;box-shadow:0 6px 20px rgba(11,37,64,0.04)}
    .course-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
    .course{background:var(--card);padding:14px;border-radius:10px;box-shadow:0 6px 16px rgba(11,37,64,0.04)}
    .events-list{list-style:none;padding:0;margin:0;display:grid;gap:10px}
    .events-list li{background:var(--card);padding:12px;border-radius:10px}
    /* Contact */
    .contact-grid{display:grid;grid-template-columns:1fr 360px;gap:20px;align-items:start}
    .contact-form input, .contact-form textarea{width:100%;padding:10px;margin-bottom:10px;border-radius:8px;border:1px solid #e6e9ef}
    .contact-form .btn{display:inline-block}
    /* Footer */
    footer.site-footer{background:var(--dark);color:#fff;padding:22px 0;margin-top:28px}
    footer a{color:#fff;text-decoration:underline}
    /* Small utilities */
    .muted{color:var(--muted)}
    .small{font-size:13px}
    /* Responsive */
    @media (max-width:980px){
      .hero-grid{grid-template-columns:1fr}
      .course-grid{grid-template-columns:repeat(2,1fr)}
      .contact-grid{grid-template-columns:1fr}
      .nav-toggle{display:block}
      nav.main-nav{position:absolute;right:18px;top:72px;background:var(--card);padding:12px;border-radius:10px;flex-direction:column;box-shadow:0 12px 30px rgba(11,37,64,0.08);display:none}
      nav.main-nav.open{display:flex}
    }
    @media (max-width:520px){
      .brand h1{font-size:16px}
      .logo{width:44px;height:44px}
      .course-grid{grid-template-columns:1fr}
    }
    /* Simple carousel (CSS + small JS) */
    .carousel{position:relative;overflow:hidden;border-radius:12px}
    .slides{display:flex;transition:transform .6s ease}
    .slide{min-width:100%;flex-shrink:0}
    .carousel .controls{position:absolute;left:12px;right:12px;top:50%;display:flex;justify-content:space-between;transform:translateY(-50%);pointer-events:none}
    .controls button{pointer-events:auto;background:rgba(255,255,255,0.9);border:0;padding:8px 10px;border-radius:8px}
  </style>
</head>
<body>
  <header class="site-header">
    <div class="container header-inner">
      <div class="brand">
        <div class="logo">R</div>
        <div>
          <h1>RSMT</h1>
          <p class="muted">Rajarshi School of Management &amp; Technology</p>
        </div>
      </div>
      <nav class="main-nav" id="mainNav">
        <a href="#about">About</a>
        <a href="#programmes">Programmes</a>
        <a href="#admissions">Admissions</a>
        <a href="#events">Events</a>
        <a href="#contact">Contact</a>
        <a class="btn" href="#apply">Apply</a>
      </nav>
      <button class="nav-toggle" id="navToggle" aria-label="Toggle navigation">☰</button>
    </div>
  </header>
  <main>
    <section class="hero">
      <div class="container hero-grid">
        <div class="hero-left">
          <h2>Leading management &amp; technology institute — Varanasi</h2>
          <p class="muted">Undergraduate &amp; postgraduate programmes: industry-oriented curriculum, skilled faculty and placement support.</p>
          <div class="hero-cta">
            <a class="btn" href="#apply">Apply Now</a>
            <a class="btn ghost" href="#programmes">View Programmes</a>
          </div>
          <div style="margin-top:18px">
            <strong>Notice:</strong>
            <div class="muted" style="margin-top:6px">Admissions open for the new session. Check the Admissions section for details.</div>
          </div>
        </div>
        <div class="hero-right">
          <div class="carousel hero-card" id="heroCarousel">
            <div class="slides">
              <div class="slide"><img src="https://via.placeholder.com/880x520?text=RSMT+Campus+1" alt="Campus 1"></div>
              <div class="slide"><img src="https://via.placeholder.com/880x520?text=RSMT+Event+2" alt="Event"></div>
              <div class="slide"><img src="https://via.placeholder.com/880x520?text=Lab+/+Classroom" alt="Lab"></div>
            </div>
            <div class="controls">
              <button id="prev">◀</button>
              <button id="next">▶</button>
            </div>
            <p class="caption">Campus &amp; events — placeholders</p>
          </div>
        </div>
      </div>
    </section>
    <section id="about" class="container">
      <h3 class="section-title">About RSMT</h3>
      <p class="muted">Rajarshi School of Management &amp; Technology (RSMT) is known for its academic programs in computer applications and management. This is a student-made demo clone — replace content/images with official assets when publishing.</p>
      <div class="cards" style="margin-top:18px">
        <article class="card">
          <h4>Vision</h4>
          <p>To develop competent professionals with strong ethics.</p>
        </article>
        <article class="card">
          <h4>Facilities</h4>
          <p>Computer labs, library, seminar halls, placement cell and student support services.</p>
        </article>
        <article class="card">
          <h4>Industry Interface</h4>
          <p>Workshops, guest lectures and campus recruitment drives.</p>
        </article>
      </div>
    </section>
    <section id="programmes" class="container">
      <h3 class="section-title">Programmes Offered</h3>
      <div class="course-grid" style="margin-top:12px">
        <div class="course">
          <h4>BCA</h4>
          <p>Bachelor of Computer Applications — programming, databases and projects.</p>
        </div>
        <div class="course">
          <h4>BBA</h4>
          <p>Bachelor of Business Administration — management fundamentals &amp; soft skills.</p>
        </div>
        <div class="course">
          <h4>MCA</h4>
          <p>Master of Computer Applications — advanced computing and research projects.</p>
        </div>
        <div class="course">
          <h4>MBA</h4>
          <p>Master of Business Administration — specializations and placements.</p>
        </div>
      </div>
    </section>
    <section id="admissions" class="container">
      <h3 class="section-title">Admissions &amp; Important Links</h3>
      <p class="muted">For official application forms, fees and procedures use the college admission portal. (This clone uses placeholder links.)</p>
      <div style="margin-top:12px"><a class="btn" href="#apply">Admission Portal (placeholder)</a></div>
    </section>
    <section id="events" class="container">
      <h3 class="section-title">News &amp; Events</h3>
      <ul class="events-list" style="margin-top:12px">
        <li><strong>Orientation Week</strong> — activities for new students.</li>
        <li><strong>Placement Drive</strong> — companies visiting campus for recruitment.</li>
        <li><strong>Training Workshop</strong> — skill development sessions by industry trainers.</li>
      </ul>
    </section>
    <section id="contact" class="container">
      <h3 class="section-title">Contact &amp; Location</h3>
      <div class="contact-grid" style="margin-top:12px">
        <div>
          <p><strong>Address:</strong> Udai Pratap College Campus, Varanasi, Uttar Pradesh (placeholder)</p>
          <p><strong>Phone:</strong> +91 542-XXXXXXX</p>
          <p><strong>Email:</strong> info@rsmt.example</p>
          <div style="margin-top:12px">
            <iframe title="Map" src="https://maps.google.com/maps?q=varanasi&t=&z=13&ie=UTF8&iwloc=&output=embed" style="width:100%;height:220px;border:0;border-radius:10px"></iframe>
          </div>
        </div>
        <div class="contact-form">
          <h4>Enquiry</h4>
          <form onsubmit="alert('Form submission disabled in demo clone');return false;">
            <input type="text" placeholder="Your name" required>
            <input type="email" placeholder="Your email" required>
            <textarea placeholder="Your message" rows="5"></textarea>
            <button class="btn" type="submit">Send Enquiry</button>
          </form>
        </div>
      </div>
    </section>
    <section id="apply" class="container">
      <h3 class="section-title">Apply / Admission Quick Links</h3>
      <p class="muted">This demo links to the official admissions portal in the real site — replace the URL below with the official portal if you publish.</p>
      <div style="margin-top:12px"><a class="btn" href="#">Go to Official Admissions (placeholder)</a></div>
    </section>
  </main>
  <footer class="site-footer">
    <div class="container" style="display:flex;justify-content:space-between;gap:12px;align-items:center;flex-wrap:wrap">
      <div>© <span id="year"></span> Rajarshi School of Management &amp; Technology — student clone (demo)</div>
      <div class="small muted">Official site: rsmt.ac.in</div>
    </div>
  </footer>
  <script>
    // year
    document.getElementById('year').textContent = new Date().getFullYear();
    // mobile nav toggle
    const nav = document.getElementById('mainNav');
    const btn = document.getElementById('navToggle');
    btn.addEventListener('click', ()=> nav.classList.toggle('open'));
    // simple carousel logic
    (function(){
      const carousel = document.getElementById('heroCarousel');
      const slides = carousel.querySelector('.slides');
      const total = slides.children.length;
      let index = 0;
      const next = document.getElementById('next');
      const prev = document.getElementById('prev');
      function go(i){
        index = (i + total) % total;
        slides.style.transform = `translateX(-${index*100}%)`;
      }
      next.addEventListener('click', ()=> go(index+1));
      prev.addEventListener('click', ()=> go(index-1));
      // auto play
      let timer = setInterval(()=> go(index+1), 4000);
      carousel.addEventListener('mouseenter', ()=> clearInterval(timer));
      carousel.addEventListener('mouseleave', ()=> timer = setInterval(()=> go(index+1), 4000));
    })();
  </script>
</body>
</html>
