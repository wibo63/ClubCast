# ⚽ ClubCast — News Hub
### Multi-channel aankondigingen voor voetbalclubs
**Versie 1.0 · FC Rotterdam · 2026**

---

## 🚀 Quick Start (5 minuten)

### Stap 1 — Open de app
Download `index.html` en dubbelklik het bestand. Het opent direct in je browser — geen installatie nodig.

### Stap 2 — Haal een gratis AI key op
1. Ga naar [console.groq.com](https://console.groq.com)
2. Maak een **gratis account** aan — geen creditcard nodig
3. Klik op **API Keys → Create API Key**
4. Kopieer de key (begint met `gsk_`)

### Stap 3 — Voer de key in
1. Open ClubCast → klik **⚙️ Instellingen** (rechtsboven)
2. Ga naar tabblad **✨ AI Schrijven**
3. Plak je Groq key in het veld
4. Klik **Opslaan** → dan **Test verbinding**

### Stap 4 — Schrijf je eerste aankondiging
1. Klik **✏️ Nieuw bericht**
2. Kies een type (bijv. *Match* of *Algemeen*)
3. Vul een koptekst en je bericht in
4. Klik **✨ Genereer previews**
5. De AI schrijft automatisch voor Website, Nieuwsbrief, Instagram en Facebook
6. Klik **🚀 Nu publiceren**

---

## Wat is ClubCast?

ClubCast is een browsergebaseerde content hub waarmee het communicatieteam een aankondiging **één keer schrijft** en deze automatisch — door AI aangepast — naar vier kanalen tegelijk verstuurt.

| Kanaal | Hoe het publiceert | Status |
|---|---|---|
| 🌐 Website | Kopieert artikel naar klembord → plakken in je CMS | ✅ Werkt |
| 📧 Nieuwsbrief | Verstuurt echte e-mail via EmailJS + Outlook/Office 365 | ✅ Werkt (setup vereist) |
| 📸 Instagram | Kopieert caption + hashtags naar klembord | ⚙️ Kopiëren (API binnenkort) |
| 👍 Facebook | Kopieert post naar klembord | ⚙️ Kopiëren (API binnenkort) |

---

## AI Schrijven — Groq (gratis)

ClubCast gebruikt **Groq** met het Llama 3.3 70B model voor het genereren van content. Volledig gratis, geen creditcard nodig.

De AI past je bericht automatisch aan per kanaal:

| Kanaal | Stijl | Lengte |
|---|---|---|
| Website | Professioneel nieuwsartikel | ~150 woorden |
| Nieuwsbrief | Warm, persoonlijk, begint met "Beste supporters" | ~100 woorden |
| Instagram | Energiek, emoji's, eindigt met 6–8 hashtags | ~80 woorden |
| Facebook | Conversationeel, nodigt uit tot reacties | ~110 woorden |

### Geen AI? Gebruik handmatige modus
Ga naar **Instellingen → AI Schrijven** en zet de toggle **Handmatige modus** aan. Je krijgt dan bewerkbare tekstvelden per kanaal — geen API key nodig.

---

## 🔒 Veiligheid & API Keys

**De key staat nooit in het HTML-bestand.** Keys worden opgeslagen in de localStorage van de browser — alleen op jouw computer, nooit in de code.

| Actie | Veilig? |
|---|---|
| HTML bestand op GitHub publiceren | ✅ Veilig |
| Key invullen via de Instellingen in de browser | ✅ Veilig |
| Key hardcoded in de HTML typen | ❌ Nooit doen |

> ⚠️ Gebruik ClubCast niet op een gedeelde computer zonder voorzorgsmaatregelen. Iemand met toegang tot de browser kan een opgeslagen key zien via Developer Tools (F12).

---

## 📧 Nieuwsbrief instellen (Outlook/Office 365)

ClubCast verstuurt e-mails via **EmailJS** — gratis tot 200 e-mails per maand, geen server nodig.

1. Maak een gratis account aan op [emailjs.com](https://www.emailjs.com)
2. Ga naar **Email Services → Add New Service → Outlook / Office 365**
3. Log in met het Outlook-account van de club → kopieer de **Service ID**
4. Ga naar **Email Templates → Create New Template** met deze variabelen:
```
Onderwerp: {{subject}}

{{message}}

Verstuurd door {{club_name}}
```
5. Kopieer de **Template ID** en **Public Key** (Account → General)
6. Vul alles in via **Instellingen → 📧 Nieuwsbrief**
7. Klik **Stuur testmail** om te controleren

---

## 🌐 Publiceren op GitHub Pages

Het HTML-bestand bevat geen keys of gevoelige data — je kunt het veilig online zetten.

1. Maak een nieuw **public** repository aan op [github.com](https://github.com)
2. Hernoem `soccer-club-hub.html` naar **`index.html`**
3. Upload het bestand: **Add file → Upload files**
4. Ga naar **Settings → Pages → Deploy from branch → main → Save**
5. Na ~1 minuut is de app live op:
```
https://jouwgebruikersnaam.github.io/jouwrepo/
```

> ℹ️ De AI generatie werkt lokaal (via je eigen browser). Op GitHub Pages kan de Groq API mogelijk worden geblokkeerd door CORS — gebruik dan handmatige modus voor de online demo, of draai de app lokaal voor de volledige AI functionaliteit.

---

## ⚙️ Instellingen overzicht

Alle instellingen zijn bereikbaar via **⚙️ Instellingen** rechtsboven.

| Tabblad | Wat je instelt |
|---|---|
| ✨ AI Schrijven | Groq API key, handmatige modus aan/uit |
| 🏟️ Club Info | Clubnaam, hashtag, taal, licht/donker modus |
| 🌐 Website | CMS URL (ter referentie) |
| 📧 Nieuwsbrief | EmailJS Public Key, Service ID, Template ID, ontvanger |
| 📸 Instagram | Access Token, Account ID (voor later) |
| 👍 Facebook | Page Access Token, Page ID (voor later) |

Alle credentials worden opgeslagen in de **localStorage van de browser** — nooit in het bestand zelf.

---

## Problemen oplossen

**AI previews genereren niet**
- Controleer of je Groq API key is ingevuld en begint met `gsk_`
- Gebruik de **Test verbinding** knop in Instellingen
- Controleer je internetverbinding
- Open de browserconsole (F12) voor foutmeldingen

**Nieuwsbrief wordt niet verstuurd**
- Controleer alle vier EmailJS velden in Instellingen → Nieuwsbrief
- Gebruik **Stuur testmail** om de verbinding te testen
- Zorg dat je template de variabelen `{{subject}}`, `{{message}}` en `{{club_name}}` bevat

**Instellingen verdwijnen na sluiten browser**
- Instellingen worden opgeslagen in localStorage
- Gebruik je een privé/incognito venster? Dan worden gegevens gewist bij sluiten
- Gebruik een normaal browservenster

**Teksten komen in het Engels**
- Ga naar **Instellingen → Club Info → Taal** en selecteer *Nederlands*

---

## Roadmap

- [ ] Directe Instagram publicatie via Meta Graph API
- [ ] Directe Facebook publicatie via Meta Pages API
- [ ] Server-side scheduling (publiceren zonder app open)
- [ ] Multi-user toegang met goedkeuringsworkflow
- [ ] Post analytics (bereik, openingspercentage)
- [ ] Templatebibliotheek voor terugkerende berichten
- [ ] Afbeeldingen uploaden en bijvoegen

---

*ClubCast — gebouwd voor FC Rotterdam Communications · 2026*
