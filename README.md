# Ex.07 Restuarant Website
## Date:20-11-2025

## AIM:
To develop a static Resturant website to display the menu and services provided by the resturant.

## DESIGN STEPS:

### Step 1:
Requirement collection.

### Step 2:
Creating the layout using HTML and CSS.

### Step 3:
Updating the sample content.

### Step 4:
Choose the appropriate style and color scheme.

### Step 5:
Validate the layout in various browsers.

### Step 6:
Validate the HTML code.

### Step 7:
Publish the website in the given URL.

## PROGRAM:
```
styles.css

/* styles.css - single shared stylesheet */
:root{
  --bg:#1f1f1f;
  --card:#2f2f2f;
  --accent:#e63946;
  --text:#f5f5f5;
  --muted:#cfcfcf;
  --max-width:1000px;
  --radius:8px;
  --gap:18px;
}

*{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%}
body{
  font-family: "Georgia", serif;
  background: linear-gradient(180deg,#111,#1f1f1f);
  color:var(--text);
  display:flex;
  align-items:center;
  justify-content:center;
  padding:30px 10px;
}

/* Container centered on screen */
.site{
  width:100%;
  max-width:var(--max-width);
  background: linear-gradient(180deg,var(--bg),#141414);
  border:4px solid var(--accent);
  padding:28px;
  border-radius:6px;
  box-shadow: 0 10px 40px rgba(0,0,0,0.7);
  position:relative;
}

/* Header / nav */
.header{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:12px;
}
.brand{
  font-size:18px;
  color:var(--text);
  font-weight:700;
  letter-spacing:0.6px;
}
nav a{
  color:var(--text);
  text-decoration:none;
  margin-left:18px;
  font-weight:600;
}
nav a.active{
  color:var(--accent);
}

/* Banner / hero */
.hero{
  margin-top:18px;
  display:flex;
  gap:18px;
  align-items:center;
}
.hero-left{
  flex:1;
}
.title{
  font-size:42px;
  line-height:1.05;
  font-weight:900;
  text-transform:uppercase;
  letter-spacing:1px;
  margin-bottom:8px;
}
.subtitle{
  color:var(--muted);
  font-size:18px;
  margin-bottom:18px;
}
.cta{
  background:var(--accent);
  color:#fff;
  padding:12px 18px;
  border:none;
  border-radius:6px;
  cursor:pointer;
  font-weight:700;
}

/* Banner image box (right) */
.banner{
  width:240px;
  height:180px;
  border:3px solid #fff;
  border-radius:6px;
  overflow:hidden;
  flex-shrink:0;
  background:#222;
}
.banner img{width:100%;height:100%;object-fit:cover}

/* Sections */
.section{
  margin-top:20px;
  padding-top:12px;
}

/* Menu cards grid */
.grid{
  display:grid;
  grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
  gap:var(--gap);
  margin-top:12px;
}
.card{
  background:var(--card);
  padding:12px;
  border-radius:var(--radius);
  border:1px solid rgba(255,255,255,0.04);
}
.card img{width:100%;height:140px;object-fit:cover;border-radius:6px;margin-bottom:8px;}
.card h4{font-size:18px;margin-bottom:4px}
.card p{color:var(--muted);font-size:14px}

/* Administration layout */
.staff-grid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:18px;
}
.staff{
  background:var(--card);
  padding:12px;
  border-radius:8px;
  text-align:center;
}
.staff img{
  width:120px;height:120px;border-radius:6px;object-fit:cover;margin:0 auto 8px;border:2px solid #fff;
}
.staff h5{margin:6px 0 2px}
.staff span{color:var(--muted);font-size:14px}

/* Contact */
.contact-box{
  display:flex;
  gap:18px;
  align-items:flex-start;
  flex-wrap:wrap;
}
.contact-info{
  background:var(--card);
  padding:14px;border-radius:8px;min-width:260px;
}
.contact-info p{color:var(--muted);margin-bottom:8px}

/* Footer */
.footer{
  margin-top:22px;
  border-top:1px solid rgba(255,255,255,0.06);
  padding-top:12px;
  display:flex;
  justify-content:space-between;
  align-items:center;
  color:var(--muted);
}
.footer .left{font-weight:700}
.footer .right{font-size:14px;color:var(--muted)}

/* Responsive tweaks */
@media (max-width:760px){
  .banner{display:none}
  .staff-grid{grid-template-columns:repeat(2,1fr)}
}
@media (max-width:420px){
  .staff-grid{grid-template-columns:1fr}
  .grid{grid-template-columns:1fr}
}

index.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>SpiceGarden - Home</title>
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="site">
    <header class="header">
      <div class="brand">SpiceGarden</div>
      <nav>
        <a href="index.html" class="active">Home</a>
        <a href="menu.html">Menu</a>
        <a href="admin.html">Administration</a>
        <a href="contact.html">Contact Us</a>
      </nav>
    </header>

    <section class="hero">
      <div class="hero-left">
        <div class="title">WELCOME TO SPICEGARDEN</div>
        <div class="subtitle">Authentic regional flavors — fresh ingredients — cozy ambience</div>
        <button class="cta" onclick="location.href='menu.html'">Explore Menu</button>
      </div>
      <div class="banner">
        <!-- Replace banner.jpg with your chosen image -->
        <img src="banner.jpg" alt="Banner">
      </div>
    </section>

    <section class="section">
      <h3 style="color:var(--accent); margin-bottom:10px">About Us</h3>
      <p style="color:var(--muted); line-height:1.6">
        SpiceGarden is a family-owned restaurant dedicated to serving traditional recipes with modern presentation.
        We use locally sourced ingredients and prepare dishes with care to give you a delightful dining experience.
      </p>
    </section>

    <footer class="footer">
      <div class="left">Color Scheme: Charcoal / Coral / Cream</div>
      <div class="right">Designed by Lokesh M<</div>
    </footer>
  </div>
</body>
</html>


menu.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>SpiceGarden - Menu</title>
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="site">
    <header class="header">
      <div class="brand">SpiceGarden</div>
      <nav>
        <a href="index.html">Home</a>
        <a href="menu.html" class="active">Menu</a>
        <a href="admin.html">Administration</a>
        <a href="contact.html">Contact Us</a>
      </nav>
    </header>

    <section class="section">
      <h2 style="color:var(--accent)">Our Menu</h2>
      <p class="subtitle">Twelve popular items — click to view details (placeholder)</p>

      <div class="grid">
        <div class="card">
          <img src="dish1.jpg" alt="Dish 1">
          <h4>Masala Dosa</h4>
          <p>Thin crispy dosa served with potato masala and chutneys.</p>
        </div>

        <div class="card">
          <img src="dish2.jpg" alt="Dish 2">
          <h4>Chicken Chettinad</h4>
          <p>Spicy Chettinad-style chicken curry cooked with authentic spices.</p>
        </div>

        <div class="card">
          <img src="dish3.jpg" alt="Dish 3">
          <h4>Paneer Butter Masala</h4>
          <p>Soft cottage cheese cubes in a rich creamy tomato gravy.</p>
        </div>

        <div class="card">
          <img src="dish4.jpg" alt="Dish 4">
          <h4>Fish Fry</h4>
          <p>Marinated fish fillet shallow-fried to golden perfection.</p>
        </div>

        <div class="card">
          <img src="dish5.jpg" alt="Dish 5">
          <h4>Biryani (Veg)</h4>
          <p>Fragrant basmati rice cooked with vegetables and special masala.</p>
        </div>

        <div class="card">
          <img src="dish6.jpg" alt="Dish 6">
          <h4>Hyderabadi Biryani (Chicken)</h4>
          <p>Layered chicken biryani slow-cooked with saffron and spices.</p>
        </div>

        <div class="card">
          <img src="dish7.jpg" alt="Dish 7">
          <h4>Rasam & Rice</h4>
          <p>Comforting tangy rasam served with steamed rice.</p>
        </div>

        <div class="card">
          <img src="dish8.jpg" alt="Dish 8">
          <h4>Idli Sambhar</h4>
          <p>Soft idlis with flavorful sambar and chutney.</p>
        </div>

        <div class="card">
          <img src="dish9.jpg" alt="Dish 9">
          <h4>Gobi 65</h4>
          <p>Spicy deep-fried cauliflower with curry leaf tempering.</p>
        </div>

        <div class="card">
          <img src="dish10.jpg" alt="Dish 10">
          <h4>Egg Curry</h4>
          <p>Boiled eggs in a spicy onion-tomato gravy.</p>
        </div>

        <div class="card">
          <img src="dish11.jpg" alt="Dish 11">
          <h4>Curd Rice</h4>
          <p>Comforting curd rice with seasoning of mustard seeds and curry leaf.</p>
        </div>

        <div class="card">
          <img src="dish12.jpg" alt="Dish 12">
          <h4>Filter Coffee</h4>
          <p>Traditional South Indian filter coffee to finish your meal.</p>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="left">Color Scheme: Charcoal / Coral / Cream</div>
      <div class="right">Designed by Lokesh M<</div>
    </footer>
  </div>
</body>
</html>


admin.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>SpiceGarden - Administration</title>
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="site">
    <header class="header">
      <div class="brand">SpiceGarden</div>
      <nav>
        <a href="index.html">Home</a>
        <a href="menu.html">Menu</a>
        <a href="admin.html" class="active">Administration</a>
        <a href="contact.html">Contact Us</a>
      </nav>
    </header>

    <section class="section">
      <h2 style="color:var(--accent)">Our Team</h2>
      <p class="subtitle">Meet the people who make SpiceGarden run.</p>

      <div class="staff-grid" style="margin-top:14px">
        <div class="staff">
          <img src="kumar.jpg" alt="Staff 1">
          <h5>Mr. R. Kumar</h5>
          <span>Proprietor</span>
        </div>

        <div class="staff">
          <img src="anjali rao.jpg" alt="Staff 2">
          <h5>Ms. Anjali Rao</h5>
          <span>Head Chef</span>
        </div>

        <div class="staff">
          <img src="venkatesh.jpg" alt="Staff 3">
          <h5>Mr. S. Venkatesh</h5>
          <span>Manager</span>
        </div>

        <div class="staff">
          <img src="meena.jpg" alt="Staff 4">
          <h5>Ms. Meena</h5>
          <span>Accounts</span>
        </div>

        <div class="staff">
          <img src="arjun.jpg" alt="Staff 5">
          <h5>Mr. Arjun</h5>
          <span>Floor Supervisor</span>
        </div>

        <div class="staff">
          <img src="latha.jpg" alt="Staff 6">
          <h5>Ms. Latha</h5>
          <span>PR & Events</span>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="left">Color Scheme: Charcoal / Coral / Cream</div>
      <div class="right">Designed by Lokesh M<</div>
    </footer>
  </div>
</body>
</html>


contact.html

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <title>SpiceGarden - Contact Us</title>
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="site">
    <header class="header">
      <div class="brand">SpiceGarden</div>
      <nav>
        <a href="index.html">Home</a>
        <a href="menu.html">Menu</a>
        <a href="admin.html">Administration</a>
        <a href="contact.html" class="active">Contact Us</a>
      </nav>
    </header>

    <section class="section">
      <h2 style="color:var(--accent)">Contact Us</h2>
      <p class="subtitle">We’d love to hear from you — reservations, feedback, or catering requests.</p>

      <div class="contact-box" style="margin-top:14px">
        <div class="contact-info">
          <h4 style="margin-bottom:8px">Address</h4>
          <p>SpiceGarden Restaurant, No: 12, Main Road, Vadalur - 607303, Tamil Nadu, India</p>

          <h4 style="margin-top:12px;margin-bottom:8px">Phone</h4>
          <p>+91 98765 43210</p>

          <h4 style="margin-top:12px;margin-bottom:8px">Email</h4>
          <p>reservations@spicegarden.example</p>
        </div>

        <div class="contact-info" style="flex:1;">
          <h4 style="margin-bottom:8px">Opening Hours</h4>
          <p>Mon - Sun: 10:00 AM - 11:00 PM</p>

          <h4 style="margin-top:12px;margin-bottom:8px">Reservation</h4>
          <p>Call or email us to reserve a table for parties of any size.</p>
        </div>
      </div>
    </section>

    <footer class="footer">
      <div class="left">Color Scheme: Charcoal / Coral / Cream</div>
      <div class="right">Designed by Lokesh M</div>
    </footer>
  </div>
</body>
</html>

```

## OUTPUT:
<img width="1263" height="751" alt="image" src="https://github.com/user-attachments/assets/aac794ce-9608-40d5-b2e6-47acac7fc4b4" />
<img width="1266" height="748" alt="image" src="https://github.com/user-attachments/assets/aada6ab9-bff3-4654-96b7-35ed286ea19d" />
<img width="1262" height="755" alt="image" src="https://github.com/user-attachments/assets/f0dd5fb1-2e77-4e48-b33d-9ba6115e5521" />
<img width="1266" height="751" alt="image" src="https://github.com/user-attachments/assets/fd373c33-b2c5-45b7-945b-c06a578f882f" />


## RESULT:
The program for designing software company website using HTML and CSS is completed successfully.
