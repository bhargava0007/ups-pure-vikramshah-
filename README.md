# ups-pure-vikramshah-
School 
#!/usr/bin/env bash
# —————————————————————————————
# create_site_and_zip.sh
# आपके स्कूल वेबसाइट पैकेज बनाकर upspurevikramshah_site.zip बनाता है
# इस्तेमाल: chmod +x create_site_and_zip.sh; ./create_site_and_zip.sh
# ज़िप *पैकेज* plus फ़ाइल स्ट्रक्चर एक ही कमांड में तैयार हो जाएगा
# —————————————————————————————

set -eu

ZIPNAME="upspurevikramshah_site.zip"
SRCDIR="upspurevikramshah_site"
CSSDIR="$SRCDIR/css"
ASSETS="$SRCDIR/assets/staff"

echo
echo "Creating site folder structure..."
rm -rf "$SRCDIR" "$ZIPNAME"
mkdir -p "$ASSETS"

echo
echo "Writing index.html ..."
cat >"$SRCDIR/index.html" <<'EOF'
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <title>U.P.S. Pure Vikram Shah</title>
  <link rel="stylesheet" href="css/main.css" />
</head>
<body>
  <header class="hero">
    <img src="assets/logo.png" alt="UPS Pure Vikram Shah विद्यालय" class="logo" />
    <h1>U.P. Primary School<br>Pure Vikram Shah, Pratappur Block, Prayagraj</h1>
    <p>
      UDISE Code: <strong>09450408902</strong> |
      कक्षा I – VIII • Co‑educational • ग्रामीण Upper Primary School<br>
      छात्रों की संख्या: ~278, शिक्षक: ~11 *<br>
      *(Source: StackSchools, vidyatime)* 
    </p>
  </header>

  <nav class="topnav">
    <a href="index.html" class="active">होम</a>
    <a href="about.html">हमारे बारे में</a>
    <a href="staff.html">स्टाफ़</a>
    <a href="homework.html">होमवर्क</a>
  </nav>

  <main>
    <section class="intro">
      <h2>विद्यालय परिचय</h2>
      <p>
        UPS Pure Vikram Shah (UDISE: 09450408902) एक ग्रामीण Upper Primary विद्यालय है,
        जिसमें कुल **278** छात्र और **11** शिक्षक कार्यरत हैं। *(StackSchools)*<br>
        इसे वर्ष 1987 में स्थापित किया गया था, और यह Department of Education, U.P. द्वारा संचालित है। *(StackSchools)*<br>
        सुविधाएँ: Boundary Wall, Drinking Water, Library, Book‑Bank आदि उपलब्ध। *(StackSchools/vidyatime)*​
      </p>
    </section>
    <section class="more">
      <a href="about.html">पूरा विवरण देखें →</a>
    </section>
  </main>

  <footer>
    <p>© 2025 U.P.S. Pure Vikram Shah</p>
  </footer>
</body>
</html>
EOF

echo "Writing about.html ..."
cat >"$SRCDIR/about.html" <<'EOF'
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <title>About • U.P.S. Pure Vikram Shah</title>
  <link rel="stylesheet" href="css/main.css" />
</head>
<body>
  <nav class="topnav">
    <a href="index.html">होम</a>
    <a href="about.html" class="active">हमारे बारे में</a>
    <a href="staff.html">स्टाफ़</a>
    <a href="homework.html">होमवर्क</a>
  </nav>

  <main>
    <article class="about-container">
      <h2>हमारे बारे में</h2>
      <ul>
        <li><strong>UDISE कोड:</strong> 09450408902</li>
        <li><strong>स्थापना वर्ष:</strong> 1987</li>
        <li><strong>कक्षाएँ:</strong> I – VIII (278 विद्यार्थी, 11 शिक्षक)*</li>
        <li><strong>प्रबंधन:</strong> Department of Education, Uttar Pradesh Govt. *</li>
        <li><strong>सुविधाएँ:</strong> Boundary Wall, Drinking Water, Book‑Bank, Library *</li>
      </ul>
      <p>
        यह विद्यालय गाँव "Pure Vikram Shah" में है, जो Pratappur Block, Prayagraj District में स्थित है।
        (आंकड़े स्रोत: StackSchools, vidyatime)​
      </p>
    </article>
  </main>

  <footer>
    <p>© 2025 U.P.S. Pure Vikram Shah</p>
  </footer>
</body>
</html>
EOF

echo "Writing staff.html ..."
cat >"$SRCDIR/staff.html" <<'EOF'
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <title>Staff • U.P.S. Pure Vikram Shah</title>
  <link rel="stylesheet" href="css/main.css" />
</head>
<body>
  <nav class="topnav">
    <a href="index.html">होम</a>
    <a href="about.html">हमारे बारे में</a>
    <a href="staff.html" class="active">स्टाफ़</a>
    <a href="homework.html">होमवर्क</a>
  </nav>

  <main>
    <h2>हमारा स्टाफ़</h2>
    <div class="staff-grid">
      <!-- अपनी चित्र व नाम यहां डालिए -->
      <div class="staff-card">
        <img src="assets/staff/principal.jpg" alt="Principal" class="staff-photo">
        <h3>Ms Radha (प्रधानाध्यापक)</h3>
      </div>
      <div class="staff-card">
        <img src="assets/staff/teacher1.jpg" alt="Teacher" class="staff-photo">
        <h3>Mr Ram (कक्षा II शिक्षक)</h3>
      </div>
      <!-- यहाँ बाक़ी 3–4 कार्ड्स भी डाल सकते हैं -->
    </div>
  </main>

  <footer>
    <p>© 2025 U.P.S. Pure Vikram Shah</p>
  </footer>
</body>
</html>
EOF

echo "Writing homework.html ..."
cat >"$SRCDIR/homework.html" <<'EOF'
<!DOCTYPE html>
<html lang="hi">
<head>
  <meta charset="UTF-8" />
  <title>Daily Homework • U.P.S. Pure Vikram Shah</title>
  <link rel="stylesheet" href="css/main.css" />
  <style>
    .hw-item { margin:1rem 0; }
    .hw-item button {
      background:#005d88; color:#fff; padding:0.8rem;
      border:none; width:100%; text-align:left;
      font-size:1.1rem; cursor:pointer; border-radius:4px;
    }
    .hw-text {
      display:none; padding:0.8rem; border:1px solid #ddd;
      margin-top:0.3rem; border-radius:4px;
    }
  </style>
</head>
<body>
  <nav class="topnav">
    <a href="index.html">होम</a>
    <a href="about.html">हमारे बारे में</a>
    <a href="staff.html">स्टाफ़</a>
    <a href="homework.html" class="active">होमवर्क</a>
  </nav>

  <main>
    <h2>दिनांक <span id="today"></span> का होमवर्क (कक्षा VI–VIII)</h2>

    <div class="hw-item">
      <button>हिंदी</button>
      <div class="hw-text">
        <ul>
          <li>पाठ 4 के प्रश्न 5‑8 उत्तर लिखें</li>
        </ul>
      </div>
    </div>
    <div class="hw-item">
      <button>गणित</button>
      <div class="hw-text">
        <ul>
          <li>गुणा‑भाग अभ्यास: 5 प्रश्न हल करें</li>
        </ul>
      </div>
    </div>
    <div class="hw-item">
      <button>अंग्रेज़ी</button>
      <div class="hw-text">
        <ul>
          <li>"My India" paragraph पढ़ें और 5 नए शब्द लिखें</li>
        </ul>
      </div>
    </div>
  </main>

  <script>
    document.getElementById('today').innerText =
      new Date().toLocaleDateString('hi‑IN', { day:'numeric', month:'short', year:'numeric' });
    document.querySelectorAll('.hw-item button').forEach(btn =>
      btn.addEventListener('click', () => {
        const div = btn.nextElementSibling;
        div.style.display = (div.style.display === 'block') ? 'none' : 'block';
      })
    );
  </script>

  <footer>
    <p>© 2025 U.P.S. Pure Vikram Shah</p>
  </footer>
</body>
</html>
EOF

echo "Writing css/main.css ..."
cat >"$CSSDIR/main.css" <<'EOF'
body,h1,h2,h3,p,ul,li { margin:0; padding:0; }
body {
  font-family:'Noto Sans Devanagari',sans-serif;
  background:#f7f9fc;color:#333;line-height:1.6;
}
.hero {
  background:#005d88;color:#fff;text-align:center;
  padding:2rem 1rem;
}
.logo {
  max-width:120px;margin-bottom:1rem;border-radius:50%;
}
.topnav {
  display:flex;justify-content:center;
  background:#fff;padding:0.6rem 0;
  box-shadow:0 1px 3px rgba(0,0,0,0.1);
}
.topnav a {
  margin:0 0.8rem;text-decoration:none;
  color:#005d88;font-size:1.05rem;padding:0.3rem 0.6rem;
  border-radius:4px;
}
.topnav a:hover, .topnav a.active {
  background:#005d88;color:#fff;
}
main { max-width:840px;margin:2rem auto;padding:0 1rem; }
.intro, .about-container {
  background:#fff;padding:1.5rem;margin-bottom:1.5rem;
  border-radius:4px;box-shadow:0 1px 4px rgba(0,0,0,0.1);
}
.more a {
  text-decoration:none;color:#005d88;font-weight:bold;
}
.staff-grid {
  display:grid;
  grid-template-columns:repeat(auto-fill,minmax(150px,1fr));
  gap:1rem;
}
.staff-card {
  background:#fff;padding:1rem;text-align:center;
  border-radius:4px;box-shadow:0 1px 3px rgba(0,0,0,0.1);
}
.staff-photo {
  width:80%;border-radius:50%;margin-bottom:0.6rem;
}
footer {
  text-align:center;padding:1.5rem;font-size:0.9rem;color:#666;
}
EOF

echo
echo "Adding placeholder assets..."
touch "$SRCDIR/assets/logo.png"
touch "$ASSETS/principal.jpg" "$ASSETS/teacher1.jpg"
echo "(आप बाद में अपनी फोटो/लोगो वहां डाल सकते हैं)"

echo
echo "Creating zip file: $ZIPNAME ..."
command -v zip >/dev/null && \
  (cd "$(dirname "$SRCDIR")" && zip -r "../$ZIPNAME" "$(basename "$SRCDIR")") || {
  echo "Error: 'zip' कमांड नहीं मिला! कृपया apt/yum install zip करें." >&2
  exit 1
}

echo
echo "⚡ तैयार है: $(pwd)/$ZIPNAME"
echo "बस इसे extract करें या GitHub/Git पे upload करें—आपकी वेबसाइट बनकर तैयार है!"
echo
