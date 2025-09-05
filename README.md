<!DOCTYPE html>
<html lang="ur" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>آن لائن قرآن اکیڈمی</title>

  <!-- Google fonts (optional) -->
  <link href="https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600;700&family=Poppins:wght@600&display=swap" rel="stylesheet">

  <style>
    :root{
      --bg-start: #f0f8ff;
      --bg-end: #e6ffe6;
      --header-start: #6a11cb;
      --header-end: #2575fc;
      --accent1: #ff512f;
      --accent2: #dd2476;
      --card-bg: rgba(255,255,255,0.9);
      --muted: #666;
      --text: #1f2937;
      --radius: 14px;
      --glass: rgba(255,255,255,0.65);
    }

    /* Reset & base */
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: "Noto Nastaliq Urdu", "Open Sans", system-ui, sans-serif;
      background: linear-gradient(120deg,var(--bg-start),var(--bg-end));
      color:var(--text);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.6;
    }
    a{color:inherit}

    /* Header */
    header{
      background: linear-gradient(90deg,var(--header-start),var(--header-end));
      color:#fff;
      padding:24px 20px;
      text-align:center;
      box-shadow: 0 8px 24px rgba(37,117,252,0.12);
      position:relative;
    }
    header h1{ margin:0; font-size:28px; font-weight:700; color:#fff; }

    /* floating language switch (side grouped) */
    .lang-switch-container{
      position:fixed;
      top:22px;
      left:22px; /* user wanted side — kept left for RTL visibility */
      display:flex;
      gap:8px;
      z-index:1200;
    }
    .lang-btn{
      background: rgba(255,255,255,0.12);
      color:#fff;
      border:1px solid rgba(255,255,255,0.12);
      padding:8px 12px;
      border-radius:999px;
      cursor:pointer;
      font-weight:700;
      backdrop-filter: blur(6px);
      transition: transform .18s ease, background .18s ease;
    }
    .lang-btn:hover{ transform: translateY(-3px); background: rgba(255,255,255,0.18); }

    /* Container & sections */
    .container{ max-width:960px; margin:28px auto; padding:0 16px; }
    section.card{
      background: var(--card-bg);
      border-radius:var(--radius);
      padding:30px;
      margin-bottom:20px;
      box-shadow: 0 8px 30px rgba(16,24,40,0.06);
      transition: transform .25s ease, box-shadow .25s ease;
    }
    section.card:hover{ transform: translateY(-6px); box-shadow: 0 18px 44px rgba(16,24,40,0.08); }

    h2{ color:var(--header-start); margin-top:0; font-size:22px; }
    h3{ margin-bottom:8px; color:var(--header-end); }

    .lead{ color:var(--muted); margin:12px 0 18px; }

    /* CTA */
    .cta{
      display:inline-block;
      text-decoration:none;
      color:#fff;
      background: linear-gradient(90deg,var(--accent1),var(--accent2));
      padding:12px 26px;
      border-radius:999px;
      font-weight:700;
      box-shadow: 0 8px 30px rgba(221,36,118,0.12);
      transition: transform .18s ease, box-shadow .18s ease;
    }
    .cta:hover{ transform: translateY(-4px); box-shadow: 0 18px 44px rgba(221,36,118,0.16); }

    /* grid for courses */
    .grid-2{ display:grid; grid-template-columns:1fr 1fr; gap:18px; align-items:start; }
    @media (max-width:760px){ .grid-2{ grid-template-columns:1fr } .lang-switch-container{ left:12px; top:12px } }

    /* form */
    form{ background:transparent; padding:0; margin-top:8px; }
    input, select, textarea{
      width:100%; padding:12px 14px; border-radius:10px; border:1px solid #e6e6e6; font-size:15px; margin-bottom:12px;
      outline:none; transition: box-shadow .15s ease, border-color .15s ease;
    }
    input:focus, select:focus, textarea:focus{ border-color: var(--header-end); box-shadow: 0 6px 20px rgba(37,117,252,0.06); }
    .form-btn{ width:100%; padding:12px; border-radius:10px; border:none; background: linear-gradient(90deg,var(--accent1),var(--accent2)); color:#fff; font-weight:700; cursor:pointer; font-size:16px; }

    /* footer */
    footer{
      margin-top:18px;
      background: linear-gradient(90deg,var(--header-end),var(--header-start));
      color:#fff; padding:26px 16px; text-align:center; border-top:4px solid var(--accent1);
    }

    /* language visibility defaults */
    .ur { display:block; }
    .en { display:none; }

    /* small helpers */
    .muted{ color:var(--muted); font-size:14px; }
    ul.specs{ padding-left:18px; margin:6px 0 16px; }
    .contact-line a{ color:var(--accent2); text-decoration:none; font-weight:700; }

  </style>
</head>
<body class="ur">

  <!-- Language switch (grouped on side) -->
  <div class="lang-switch-container" role="navigation" aria-label="Language switch">
    <button class="lang-btn" onclick="setLang('ur')" id="btn-ur">اردو</button>
    <button class="lang-btn" onclick="setLang('en')" id="btn-en">English</button>
  </div>

  <!-- Header -->
  <header>
    <h1 class="ur">آن لائن قرآن اکیڈمی</h1>
    <h1 class="en">Online Quran Academy</h1>
  </header>

  <!-- Main container -->
  <main class="container">

    <!-- Hero (Urdu) -->
    <section class="card ur" aria-labelledby="hero-ur">
      <h2 id="hero-ur">گھر بیٹھے آن لائن قرآن سیکھیں — ماہر اساتذہ کے ساتھ</h2>
      <p class="lead">روزانہ 30—45 منٹ کی کلاسز، بچوں اور بڑوں کیلئے الگ الگ بیچز، لچکدار ٹائمنگز اور 3 دن کی مفت ڈیمو کلاس۔</p>
      <a class="cta" href="#admission-form">ابھی داخلہ لیں</a>
    </section>

    <!-- Hero (EN) -->
    <section class="card en" aria-labelledby="hero-en">
      <h2 id="hero-en">Learn Quran Online from Home — with Expert Teachers</h2>
      <p class="lead">Daily 30–45 minute classes, separate batches for kids and adults, flexible timings, and a free 3-day demo class.</p>
      <a class="cta" href="#admission-form-en">Enroll Now</a>
    </section>

    <!-- Courses (UR) -->
    <section class="card ur" aria-labelledby="courses-ur">
      <h2 id="courses-ur">ہمارے کورسز</h2>

      <div class="grid-2">
        <div>
          <h3>ناظرہ قرآن</h3>
          <ul class="specs">
            <li>مدت: 1 سال</li>
            <li>ہفتے میں 5 دن، 30 منٹ</li>
            <li>عمر: 6+ سال</li>
          </ul>
        </div>

        <div>
          <h3>تجوید و قراءت</h3>
          <ul class="specs">
            <li>مدت: 1 سال</li>
            <li>انفرادی کلاسز</li>
            <li>سرٹیفکیٹ</li>
          </ul>
        </div>
      </div>

      <div style="height:12px"></div>

      <div class="grid-2">
        <div>
          <h3>حفظ القرآن</h3>
          <ul class="specs">
            <li>مدت: 1–3 سال</li>
            <li>روزانہ 45 منٹ</li>
            <li>رابطہ میں رہنمائی</li>
          </ul>
        </div>

        <div>
          <h3>ترجمہ و تفسیر</h3>
          <ul class="specs">
            <li>مدت: 1 سال</li>
            <li>ہفتے میں 3 دن</li>
            <li>آن لائن ریکارڈنگز</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- Courses (EN) -->
    <section class="card en" aria-labelledby="courses-en">
      <h2 id="courses-en">Our Courses</h2>

      <div class="grid-2">
        <div>
          <h3>Nazra Quran</h3>
          <ul class="specs">
            <li>Duration: 1 year</li>
            <li>5 days a week, 30 minutes</li>
            <li>Age: 6+ years</li>
          </ul>
        </div>

        <div>
          <h3>Tajweed & Qiraat</h3>
          <ul class="specs">
            <li>Duration: 1 year</li>
            <li>One-to-One Classes</li>
            <li>Certificate</li>
          </ul>
        </div>
      </div>

      <div style="height:12px"></div>

      <div class="grid-2">
        <div>
          <h3>Hifz-ul-Quran</h3>
          <ul class="specs">
            <li>Duration: 1–3 years</li>
            <li>Daily 45 minutes</li>
            <li>Guidance Support</li>
          </ul>
        </div>

        <div>
          <h3>Translation & Tafseer</h3>
          <ul class="specs">
            <li>Duration: 1 year</li>
            <li>3 days a week</li>
            <li>Online Recordings</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- About Us (UR) -->
    <section class="card ur" aria-labelledby="about-ur">
      <h2 id="about-ur">ہمارے بارے میں</h2>
      <p>آن لائن قرآن اکیڈمی ایک ماہر اساتذہ پر مشتمل ادارہ ہے جو بچوں اور بڑوں کو گھر بیٹھے قرآنِ کریم سیکھنے کی سہولت فراہم کرتا ہے۔ ہمارا مقصد یہ ہے کہ بچہ <strong>بغیر خطا</strong> قرآن کو <strong>تجوید</strong> کے ساتھ پڑھے، اور اسے سمجھ کر اپنی زندگی میں عمل کر سکے۔</p>
    </section>

    <!-- About Us (EN) -->
    <section class="card en" aria-labelledby="about-en">
      <h2 id="about-en">About Us</h2>
      <p>Online Quran Academy is an expert-led institute providing children and adults the opportunity to learn the Holy Quran from home. Our goal is to help students read the Quran with perfect Tajweed and understand its teachings so they can practice them in daily life.</p>
    </section>

    <!-- Admission Form UR -->
    <section id="admission-form" class="card ur" aria-labelledby="admission-ur">
      <h2 id="admission-ur">داخلہ فارم</h2>
      <form onsubmit="handleSubmit(event, 'ur')">
        <input name="name" type="text" placeholder="نام" required />
        <input name="phone" type="text" placeholder="فون/واٹس ایپ" required />
        <select name="course" required>
          <option value="">کورس منتخب کریں</option>
          <option>ناظرہ قرآن</option>
          <option>تجوید و قراءت</option>
          <option>حفظ القرآن</option>
          <option>ترجمہ و تفسیر</option>
        </select>
        <textarea name="message" rows="4" placeholder="پیغام (اختیاری)"></textarea>
        <button class="form-btn" type="submit">جمع کریں</button>
      </form>
      <p class="muted" style="margin-top:10px">ہم جلد ہی آپ سے رابطہ کریں گے۔</p>
    </section>

    <!-- Admission Form EN -->
    <section id="admission-form-en" class="card en" aria-labelledby="admission-en">
      <h2 id="admission-en">Admission Form</h2>
      <form onsubmit="handleSubmit(event, 'en')">
        <input name="name" type="text" placeholder="Name" required />
        <input name="phone" type="text" placeholder="Phone/WhatsApp" required />
        <select name="course" required>
          <option value="">Select Course</option>
          <option>Nazra Quran</option>
          <option>Tajweed & Qiraat</option>
          <option>Hifz-ul-Quran</option>
          <option>Translation & Tafseer</option>
        </select>
        <textarea name="message" rows="4" placeholder="Message (optional)"></textarea>
        <button class="form-btn" type="submit">Submit</button>
      </form>
      <p class="muted" style="margin-top:10px">We will contact you shortly.</p>
    </section>

    <!-- Contact -->
    <section class="card ur" aria-labelledby="contact-ur">
      <h2 id="contact-ur">رابطہ کریں</h2>
      <p class="contact-line">واٹس ایپ: <span>923185861368</span> (براہِ راست چیٹ صرف انگریزی صفحے پر دستیاب ہے)</p>
      <p class="contact-line">ای میل: <a href="mailto:faizanmajeed154@gmail.com">faizanmajeed154@gmail.com</a></p>
    </section>

    <section class="card en" aria-labelledby="contact-en">
      <h2 id="contact-en">Contact Us</h2>
      <p class="contact-line">WhatsApp: <a href="https://wa.me/923185861368" target="_blank" rel="noopener">923185861368</a></p>
      <p class="contact-line">Email: <a href="mailto:faizanmajeed154@gmail.com">faizanmajeed154@gmail.com</a></p>
    </section>

  </main>

  <!-- Footer -->
  <footer>
    <p class="ur">© آن لائن قرآن اکیڈمی — محفوظ حقوق</p>
    <p class="en" style="display:none;">© Online Quran Academy — All Rights Reserved</p>
  </footer>

<script>
  // Initialize language from localStorage (if present)
  (function(){
    const saved = localStorage.getItem('site-lang') || 'ur';
    setLang(saved);
    // Show/hide english header/footer initial (some elements have inline display styles)
    document.querySelectorAll('header h1.en, footer p.en').forEach(e => e.style.display = (saved==='en') ? '' : 'none');
    document.querySelectorAll('header h1.ur, footer p.ur').forEach(e => e.style.display = (saved==='ur') ? '' : 'none');
  })();

  function setLang(lang){
    // apply body class for potential direction/font changes
    document.body.className = (lang==='en') ? 'en' : 'ur';
    localStorage.setItem('site-lang', lang);

    // display toggling for elements with .ur and .en classes
    document.querySelectorAll('.ur').forEach(el => {
      // keep block for sections, but inline for small elements if needed
      el.style.display = (lang==='ur') ? 'block' : 'none';
    });
    document.querySelectorAll('.en').forEach(el => {
      el.style.display = (lang==='en') ? 'block' : 'none';
    });

    // header & footer alt titles
    document.querySelectorAll('header h1.ur').forEach(e=> e.style.display = (lang==='ur') ? '' : 'none');
    document.querySelectorAll('header h1.en').forEach(e=> e.style.display = (lang==='en') ? '' : 'none');
    document.querySelectorAll('footer p.ur').forEach(e=> e.style.display = (lang==='ur') ? '' : 'none');
    document.querySelectorAll('footer p.en').forEach(e=> e.style.display = (lang==='en') ? '' : 'none');

    // update lang button styles (optional visual)
    document.getElementById('btn-ur').style.opacity = (lang==='ur') ? '1' : '0.7';
    document.getElementById('btn-en').style.opacity = (lang==='en') ? '1' : '0.7';
  }

  // Simple fake submit handler — replace with actual backend or email logic as needed
  function handleSubmit(e, lang){
    e.preventDefault();
    const form = e.target;
    const data = {
      name: form.name?.value || '',
      phone: form.phone?.value || '',
      course: form.course?.value || '',
      message: form.message?.value || ''
    };

    // Here you can add AJAX/fetch to send data to server.
    // For now show a friendly alert (language-specific).
    if(lang==='ur'){
      alert('شکریہ! آپ کی درخواست موصول ہو گئی ہے۔ ہم جلد رابطہ کریں گے۔');
    } else {
      alert('Thank you! Your request has been received. We will contact you shortly.');
    }

    form.reset();
  }

  // Optional: smooth scroll for internal anchors
  document.querySelectorAll('a[href^="#"]').forEach(a=>{
    a.addEventListener('click', function(ev){
      const id = this.getAttribute('href').slice(1);
      const el = document.getElementById(id);
      if(el){
        ev.preventDefault();
        el.scrollIntoView({behavior:'smooth', block:'start'});
      }
    });
  });
</script>

</body>
</html>
