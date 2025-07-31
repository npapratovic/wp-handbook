# Site launch checklista:


- ugasiti maintenance mode i obrisati taj dodatak
- ako se na webu ne koristi Gutenberg u člancima, onda treba instalirati dodatak "Disable Gutenberg"
- obavezno instalirati dodatak "Standardni Widgeti" kako bi se onemogućio Gutenberg u widgetima
- pobrisati sav lorem ipsum sadržaj: stranice, objave, kategorije itd
- ažurirati sve dodatke i WP na najnoviju verziju te se uvjeriti da sve radi bez grešaka (testiranje ispravnosti na frontendu mora imati prolaz)
- obrisati teme koje se ne koriste (po potrebi promjeniti verziju teme u style.css od teme u svrhu onemogućivanja ažuriranja teme) 
- dodati favicon na web ako nije
- brišemo ostale korisnike (*važno* pazimo da sve njihovo prebacimo na korisnika admin)
- permalinkove podesiti da su SEO friendly: https://prnt.sc/bRu2pLx-nf62 
 

## KONTAKT FORMA: 

- TESTIRATI i više puta provjeriti da kontakt forma radi
- ako se koristi Contact form 7:
	1. ispravno podesiti na tabu email, polja "TO" i "FROM" provjeriti, obično u polje "FROM" stavimo email wordpress@imedomene.com. Također, bitno je i da je polje Subject popunjeno. Primjer podešenog: https://prnt.sc/TbCPL4ztKVdH 
	2. instalirati i aktivirati dodatak: "Flamingo" by Takayuki Miyoshi - plugin je plug and play i sprema upite preko kontakt forme u bazu zajendo sa puno drugih podataka 
- ako se koristi WPFORMS: obrisati ga i preči na Contact form 7, naporni su sa restrikcijama i reklamama (ako se koristi specifična funkcionalnost tipa kondiconalna polja, onda smo osuđeni na WPFORMS ili NINJA FORMS)

## EMAIL: 
**VAŽNO:** ako je shared hosting, ovu cijelu sekciju preskačemo
1. instalirati dodatak "WP Mail SMTP" by WPFORMS može i free verzija te ga podesiti. Potrebno je pokrenuti Launch Setup Wizard i u njemu podesiti da se emailovi šalju sa "Other SMTP" - inače plugin forsira slanje sa smtp.com i premium verziju, ali ova free je sasvim dovoljna. 
2. Kada se podešava opcija Other SMTP, to u biti znači da se treba podesiti da se šalje sa neke email adrese koju smo napravili specifično za ovaj web, pr. wordpress@imedomene.com i tokom setupa moramo unijeti SMPT port (obično 587), zatim email lozinku, email username, omogućiti TLS. 
3. Setup je jednostavan i na kraju setupa treba poslati testni email, i naravno potvrditi da se poslalo. Primjer ispravno podešenog: https://prnt.sc/eOEkjwiiuzO5 
4. **VAŽNO** u rijetkim slučajevima treba omogućiti DKIM, SPF i DMARC zapisima - kontaktirati hosting za to 
5. **ULTIMATIVNA CHECKLISTA ZA PROVJERU EMAILA** https://www.helloinbox.email/ 

## SEO / ANALITIKA

Iako sam fan RankMatha, idemo na konzervativnije rješenje - SEO YOAST jer se pokazalo jendostavnijim za klijente, stabilnije u radu

Ako nije instaliran, potrebno ga ja instalirati, omogućiti i proči tzv. setup wizard. Opcije su out-of-box manje više ok. Dodatno uvijek provjerimo:

1. da je kod Content types podešeno da indeksira samo Objave / Stranice - Elementor i slično treba sakriti: https://prnt.sc/_rK_Eu2X3qX3 
2. da je Knowledge graph ispravno popunjen: https://prnt.sc/rSHimy_sv1Mu 
3. kod taxonomija oznake sakrijemo a kategorije prikažemo u rezultatima pretrage https://prnt.sc/cUNJaY533Mcb 
4. ostale arhive treba isključiti: https://prnt.sc/iJvpA7ifIRPz
5. društvene mreže i linkovi trebaju biti popunjeni: https://prnt.sc/gi_A33-9UT8C 
6. pokrenuti alat za optimize SEO data: https://prnt.sc/At8fBaD7-YH9

Nakon što smo podesili SEO YOAST, idemo podesiti Analitiku i Search Console

1. instalirati dodatak: https://wordpress.org/plugins/header-footer/ i dodati Google Analytics, Tag Manager, Facebook pixel i slične kodove koje klijent pošalje
	Ako klijent nije napravio / poslao Google Analytics i nije dodao web na Search Console, onda to mi napravimo za njega. Potrebno je ulogirati se na gmail  i prema uputama dodati HTML tag u yoast opcije: https://yoast.com/add-website-to-google-search-console/
2. Potrebno je napraviti novi Anayltics kod i dodati ga na web sa dodatkom Insert Headers and Footers 
	1. upute za kreiranje Analytics koda: https://www.wpbeginner.com/beginners-guide/how-to-install-google-analytics-in-wordpress/#signupgoogleanalytics  **VAŽNO:** property name neka nude isto kao imedomene
	2. upute za Headers / footers https://www.wpbeginner.com/beginners-guide/how-to-install-google-analytics-in-wordpress/#installga-insertheadersfooters 
	3. Kada se Analytics kod doda na web stranicu, potrebno je testirati da li radi :) 

3. Potrebno je povezati Search Console i Analytics: https://support.google.com/analytics/answer/1308621?hl=en  
4. Nakon što smo napravili Google Analytics i Search Console, potrebno je na GSC dodati mapu stranice (sitemap.xml) i poslati Googleu da ju indeksira: https://yoast.com/help/submit-sitemap-search-engines/#google-submit
5. Za kraj: potrebno je dodati klijenta, tj. njegov gmail da isto ima pristup na GSC i Analytics za taj web: 
	1. GSC: https://support.google.com/webmasters/answer/7687615?hl=en  najbolje da je Owner / full ownership
	2. Analytics https://support.google.com/analytics/answer/1009702?hl=en#Add&zippy=%2Cin-this-article <- **VAŽNO:** klijenta treba dodati na njegov property, ne na globalni account :) 

## SIGURNOST WEB stranice:

1. onemogućimo komentare na webu umjesto sa pluginom Disable comments, ubacivanjem ovog koda u functions.php fajlu od teme: https://gist.github.com/npapratovic/064a027e13f552a50aac75bffd434545
2. provjeriti da li je instaliran i podešen Really Simple SSL

## BRZINA WEB stranice:

- instalirati "Cache enabler by KEYCDN" - postavke su manje više out-of-box uredu  
- cache enabler postavke trebaju izgledati ovako: https://prnt.sc/0rj3rGgojgZY 

## OSTALO: 

1. instalirati i podesiti plugin "Disable Admin Notices individually By Creative Motion"
2. instalirati i podesiti plugin https://wordpress.org/plugins/regenerate-thumbnails/ te u njemu pokrenuti opciju regenerate thumbnails (testiranje ispravnosti na frontendu, mora imati prolaz)
3. obrisati ako se koristi ovaj dodatak: https://wordpress.org/plugins/show-current-template/
4. pregledati opće zdravlje web stranice i rješiti sve greške ukoliko ih ima (web mora imati odlično opće zdravlje)
5. napraviti backup i čuvati ga tjedan dana

Javiti da je web live!
