# Hur man kan använda Copilot i Visual Studio Code för HTML och CSS ("vibe coding")
## Vad är Copilot? 
Copilot är ett AI-verktyg som bland annat finns inbyggt i Visual Studio Code. Copilot kan hjälpa till i projekt genom att exempelvis generera innehåll, svara på frågor, hitta fel i koden eller sammanfatta information. Att använda sig av AI för att generera kod brukar kallas för "vibe coding". Jag kommer ge ett exempel på hur man kan använda Copilot i början av ett projekt, för att snabbare få en grundstruktur i HTML och CSS. 

## Exempel på hur man kan använda Copilot
Jag skapade en sida för kursen ITE130 på MDU med hjälp av Copilot i VS Code, som ser ut såhär: 

<img width="1509" height="815" alt="Toppen av MDU-sida" src="https://github.com/user-attachments/assets/b77fbc9f-4957-44cd-81ae-33e9517a2c3a" />
<img width="1509" height="737" alt="Botten av MDU-sida" src="https://github.com/user-attachments/assets/0c7e53d6-d628-4930-9cd7-acd66f6ceab3" />

## Copilot prompt 
För att göra en sida som liknar MDU:s grafiska profil så började jag med att kopiera hexkoderna från MDU.se och hittade ett typsnitt som liknar det MDU använder på rubriker. Sedan skrev jag följande prompt till copilot: 

> Can you create a website, using HTML and CSS, for students at MDU (Mälardalen University), with an overview of the course ITE130. Use these colors: #00352D (for header/navbar and footer); #FDF4EB (background color), #FF4802 (on buttons). I want a search field in the navbar. I want H1 to be large and in the font Tablet Gothic Bold. I want the rest of the text in the font Questa Slab Regular. 
Please add a section where a student is talking about the experience at the university. Also add an information box, with information about Git. Add comments to the code to make it easer to read and understand. 

Så det jag specifierade i min prompt var vilka färger jag vill ha och vart, att jag vill ha ett sökfält i min navbar, stora rubriker och vilket typsnitt, samt en sektion med en studentberättelse och en informationsruta om git. Jag bad också om att få kommenterar i koden, för att göra den lättare att läsa och navigera. 
Då fick jag min grundstruktur i mitt HTML och CSS-dokument, som jag enkelt kunde fortsätta redigare och lägga till mer innehåll. 

## Insikter/tips om att skriva prompts i Copilot 
- Var så specifik som möjligt. Skriv till exempel exakt vilka typsnitt du vill ha, exakt vilka färger du vill (hexkod är lättast).
- Specificera vilket innehåll du vill ha (till exempel navbar, sökruta, H1, informationsruta, primär och sekundär knapp).
- Då kommer du att få färdiga classes i din HTML och CSS, som man enkelt kan ändra i efterhand.
- Be Copilot att lägga till kommentarer i koden, så att det blir enklare att läsa och navigera.
- Om man tycker att det är svårt att skriva bra Copilot prompts, så kan man få hjälp av Chat-GPT att skriva prompts. 

## Exempel på hur min HTML såg ut: 

### Header 
``` HTML
	<!-- Header/Navbar -->
	<header>
		<nav class="navbar">
			<div><img src="Images/mdu-logga-vit.png" alt="MDU Logo" style="height:50px;"></div>
			<ul class="nav-links">
				<li><a href="#overview">Överblick</a></li>
				<li><a href="#testimonial">Student Berättar</a></li>
				<li><a href="#git-info">Om Git</a></li>
			</ul>
			<!-- Search field in navbar -->
			<form class="search-form" action="#" method="get">
				<input type="text" placeholder="Search..." name="search">
				<button type="submit">Sök</button>
			</form>
		</nav>
	</header>
```

### Studentberättelse och informationsruta om git
``` HTML
<!-- Student Testimonial Section -->
		<section id="testimonial" class="testimonial-section">
			<h2>Student berättar</h2>
			<blockquote>
				<p>"Att studera på MDU har varit en fantastisk upplevelse! ITE130-kursen gav mig självförtroendet och de färdigheter som krävdes för att påbörja min designresa. De stöttande lärarna och den samarbetsinriktade miljön gjorde lärandet både roligt och effektivt."</p>
				<footer>– Alex, tidigare student</footer>
			</blockquote>
		</section>
	<!-- Information Box about Git -->
		<section id="git-info" class="info-box">
			<h2>Vad är git?</h2>
			<p>Git är ett kraftfullt versionshanteringssystem som hjälper dig att spåra ändringar i din kod, samarbeta med andra och hantera dina projekt effektivt. I ITE130 kommer du att lära dig hur man använder Git för att organisera ditt arbete och bidra till gruppuppgifter.</p>
```
## Exempel på hur min CSS såg ut:

### Typsnitt och body
``` css
body {
	background-color: #FDF4EB;
	font-family: Tablet Gothic, Arial, sans-serif;
	margin: 0;
	color: #222;
}
```

### Header och navbar 
``` css
header {
	background-color: #00352D;
	padding: 0;
}

/* Navbar styles */
.navbar {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding: 1rem 2rem;
	background-color: #00352D;
}
```

### Typografi
```css
/* H1 styling for course title */
h1 {
	font-family: 'Tablet Gothic', Arial, sans-serif;
	font-size: 3rem;
	font-weight: 700;
	margin-bottom: 0.5rem;
	color: #00352D;
}

/* Section headings */
h2 {
	font-family: 'Tablet Gothic', Arial, sans-serif;
	font-size: 2rem;
	color: #00352D;
	margin-top: 2rem;
}
```

### Inforutor
```css
/* Testimonial section */
.testimonial-section {
	background: #fff;
	border-left: 6px solid #00352D;
	margin: 2rem 0;
	padding: 1.5rem 2rem;
	border-radius: 8px;
	box-shadow: 0 2px 8px rgba(0,0,0,0.04);
}
.testimonial-section blockquote {
	margin: 0;
	font-style: italic;
	color: #333;
}

/* Information box about Git */
.info-box {
    background: #fff;
	border-left: 6px solid #FF4802;
	margin: 2rem 0;
	padding: 1.5rem 2rem;
	border-radius: 8px;
	box-shadow: 0 2px 8px rgba(0,0,0,0.04);
}
.info-box h2 {
	margin-top: 0;
	color: #FF4802;
}
```
