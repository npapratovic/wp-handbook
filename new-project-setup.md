# Specifikacija za početak novog projekta sa tip&tricks te best practice

Ovdje je detaljno raspisan setup svakog novog WP projekta, upute će se ažurirati redovito, zato je važno ih provjeravati

Nakon što se prođe ovaj prvi dio, obavezno javiti status!

TODO: 

- napraviti Astra (neomedia) child temu i povezati ju sa http://tgmpluginactivation.com/ unutar functions.php te tako ubrzati instalaciju dodataka
- dodati iteme sa ostalih lista: 
 - https://github.com/gruz0/wordpress-checklist
 - https://gist.github.com/slushman/8cd3d45e490bb9fa175a#file-dcc-site-launch-list-md
- napraviti dummy content za podstranice

VAŽNO: Disable auto-updates, dakle, ne omogućiit da se upluginovi samostalno updejtaju. Nažalost, pokazalo se kao loše rješenje jer su se webovi skršili. Ispravnije je periodički napraviit backup i ručno napraviti update dodataka


---------------------------- 
 
Nameservere za domenu uvijek podešavamo ovako:

NameServer1: ns1.totohost.com
NameServer2: ns2.totohost.com
NameServer3: ns3.totohost.com
NameServer4: ns4.totohost.com

Uvijek je važno kod cpanel podataka provjeriti samo onaj dio sa usernameom i passwordom.

Cpanel login za neku domenu je:

https://imedomene.hr/cpanel

username: xxx (obično isto kao ime domene)
password: xxx (automatski generirano)

-------------------------

 
1. provjeriti login podatke, u cpanelu, provjeri file manager i u public_html direktoriju treba obisati datoteke koje su višak pr. index.html ili php to su vjerojatno demo datoteku. U public_html folderu treba biti samo ovo: https://prnt.sc/26e0m9u

2. u cpanelu podesiti najnoviju STABILNU dostupnu verziju PHP-a ako nije (trenutno je to 8.0)

primjer kada je ispravno podešeno: https://prnt.sc/26dzuol

3. aktivirati AutoSSL za domenu ako nije

primjer kada je ispravno podešeno:  https://prnt.sc/26dzuih

4. U cpanelu kreirati novog MySQL korisnika, novu bazu i dodijeliti tog korisnika bazi.

Važno! Uvijek pazimo na nazivlje baza i korisnika. Standardno u ime korisnika i baze stavimo da se radi o određenoj godini, dodamo i wp u naziv te eventualno dodatak "web" ili "user". Lozinka se mora sastojati samo od slova i brojeva te min 18 znakova. Ne koristimo posebne znakove (?#$) u lozinci jer se u specifičnim situacijama pojave problemi kod enkodiranja.

pr. ime baze:  buaban_2022wpdb
pr. user:  buaban_wp2022wpuser
pr. lozinka: DM7BVRSjd3gJQwMadN

Također, prilikom instalacije WordPressa, važno da je prefiks baze podataka NE BUDE wp_, nego stavimo kompliciraniji prefiks:  pr. "wp2022_"

5. Instalirati WordPress, standardno na hrvatskom jeziku, osim ako klijent ne bude tražio drugačije 

Lozinku neka bude komplicirana i min 18 znakova, bez posebnih znakova 
 
6. Kada se završi WordPress instalacija, potrebno je podesiti neke stvari:

- podesiti permalinkove:

https://prnt.sc/26dzzoi

- obrisati sve objave, sve stranice, sve kategorije i sve oznake
- obrisati dodatke Hello Dolly i Akismet
- Obrisati sadržaj polja "Slogan" <- samo još jedna WP web stranica
- ažurirati WP

7. Potrebno je instalirati i omogućiti sljedeće dodatke:

Mi web pregledavamo sa glavnim admin accountom, a za klijenta je potrebno napraviti account sa najosnovnijim rolom (Pretplatnik), kontakt emailom i nekim kompliciranim korisničkim imenom pr. buabanadmin
 
Instaliramo i podesimo slijedeće dodatke:

    - https://wordpress.org/plugins/really-simple-ssl/
odmah po instalaciji i podesiti SSL te postavke plugina: https://prnt.sc/26e0n8y

    - https://wordpress.org/plugins/regenerate-thumbnails/ <- važno je da se prije nego web ide live odradi regenerate thumbnailsa

    - https://wordpress.org/plugins/scriptless-social-sharing/
odmah po instalaciji podesiti plugin da prikaže gumbe za djeljenje na društvenim mrežama ispod svake objave na web stranici

    - https://wordpress.org/plugins/show-current-template/

    - https://wordpress.org/plugins/simple-sitemap/
odmah po instalaciji napraviti podstranicu koja se zove "Mapa weba" i napraviti prikaz po uzoru na https://dobarzivot.net/mapa-weba/ (vidi dokumentaciju, to su Gutenberg blokovi). Također, ne zaboravi dodati mapu weba u footer navigaciju, ili sekundarnu navigaciju, ovisno gdje bude

    - https://wordpress.org/plugins/classic-widgets/

    - https://wordpress.org/plugins/header-footer/
sa tim dodatkom će se dodati na web Google Analytics, Facebook pixel i slični kodovi koje klijent pošalje

    - dodaci za sigurnost:

    https://wordpress.org/plugins/wp-hide-security-enhancer/
    https://wordpress.org/plugins/wordfence/

     Potrebno je proći kroz opcije od oba, i podesiti nekakav best practice koji oni preporučuju

    - https://wordpress.org/plugins/disable-comments/ odmah i podesiti da se globalno onemoguće komentari

    - instalirati i omogućiti https://wordpress.org/plugins/cache-enabler/
 

12. Na kontakt podstranici trebaju biti osnovni kontakt podaci:

    - email, broj telefona, adresa
    - linkovi na društvene mreže ako ih ima
    - kontakt forma sa poljima:
    1) Ime i prezime
    2) kontakt email i / ili broj
    3) sadržaj poruke

    Kontakt formu radimo sa dodatkom Contact form 7, obavezno stavimo da su sva polja obavezna, i stavimo da su validacijske poruke na hrvatskom jeziku. Važno je da je u kontakt formi podešeno da email sa kojeg se šalje je wordpress@imedomene.hr a kontakt poruku šaljemo na glavni kontakt web stranice  

13. Potrebno je omogućiti blog za svaki web, obično je to na URL-u imedomene.hr/blog i tu se moraju ispisivati objave koje se rade kroz administraciju

14. u footer web uvijek stavimo tzv. secondary menu sa stavkama: (Mapa weba, Politika privatnosti, Uvjeti korištenja itd. dakle, sve ove sekundarne stranice)

15. Uvijek pišemo pri dnu: Copyright © 2022 ime domene.hr |  

16. SEO - dugačka tema, osobno volim RankMath, no primjetio sam da je klijentima kompliciran, pa onda do daljnjeg radimo sa SEO YOASTOm kojeg je potrebno instalirati odmah u startu, i prije završetka pokrenuti njegov wizard i podesiti ga. Ako je napredniji klijent, onda ćemo ići sa drugačijim pristupom

-------------------------


## SPECIFIČNO ZA OVAJ PROJEKT:
 
     - Stavi u astri css da je verzija tipa 10.2.1 umjesto 1.2.1 - to je mali "hack" sa kojim ćeš onemogućiti update teme

