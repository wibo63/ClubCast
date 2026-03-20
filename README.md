# ⚽ ClubCast — News Hub
### Multi-channel announcement publishing for soccer clubs
**Version 1.0 · FC Rotterdam · March 2026**

---

## What is ClubCast?

ClubCast is a browser-based content hub that lets your communications team write an announcement **once** and publish it — automatically adapted by AI — across four channels simultaneously.

| Channel | How it publishes | Status |
|---|---|---|
| 🌐 Website | Copies article to clipboard → paste into your CMS | ✅ Working |
| 📧 Newsletter | Sends a real email via EmailJS + Outlook/Office 365 | ✅ Working (setup required) |
| 📸 Instagram | Copies caption + hashtags to clipboard | ⚙️ Copy only (API coming soon) |
| 👍 Facebook | Copies post to clipboard | ⚙️ Copy only (API coming soon) |

---

## Getting Started

**Requirements:**
- A modern browser: Chrome, Edge, Firefox or Safari
- An internet connection (needed for AI writing and email sending)
- The file: `clubcast.html`

**To open the app:**
1. Download `clubcast.html` to your computer
2. Double-click the file — it opens in your default browser
3. No login or installation needed

> ⚠️ Open the file directly in a browser window, not inside a preview pane in email or Teams.

---

## Creating an Announcement

Go to **New Post** in the left sidebar.

### Step 1 — Choose Announcement Type
Pick the category that fits your news:

| Type | Use for |
|---|---|
| 📢 General | Club news that doesn't fit elsewhere |
| 👤 Player News | Injuries, milestones, contract updates |
| 🔄 Transfer | Signings, departures, loans |
| 🎟️ Event | Matches, open days, ticket sales |
| ⚽ Match | Pre/post-match announcements |
| 🏟️ Club Update | Infrastructure, management, partnerships |

### Step 2 — Write Your Message
Fill in two fields:
- **Headline** — a short, clear title (e.g. *New Head Coach Appointed*)
- **Full message** — write naturally, as if telling a colleague. Include names, dates, and key facts. The AI handles the rest.

### Step 3 — Select Channels
Toggle the channels you want to publish to. Each shows whether it's fully connected or copy-only.

### Step 4 — Generate & Publish
1. Click **✨ Generate Previews** — the AI rewrites your message for each channel in seconds
2. Review the four previews side by side. Each has a **Copy** button if you want to edit manually
3. Click **🚀 Publish Now** to send to all selected channels at once

---

## AI Writing

The AI adapts your message automatically for each channel's format and tone:

| Channel | Style | Length |
|---|---|---|
| Website | Professional news article, SEO-friendly | ~150 words |
| Newsletter | Warm, personal, opens with "Dear supporters" + call to action | ~100 words |
| Instagram | Energetic, emojis, ends with 6–8 hashtags | ~80 words |
| Facebook | Conversational, invites engagement | ~110 words |

The AI uses your club name and hashtag from Settings automatically.

You can click **↺ Regenerate** to get a fresh version at any time.

---

## Connecting the Newsletter (Outlook / Office 365)

ClubCast sends newsletters via **EmailJS** — a free service that works directly in the browser with no backend or server needed.

**Free plan:** up to 200 emails/month.

### Setup (5 minutes)

**1. Create an EmailJS account**
Go to [emailjs.com](https://www.emailjs.com) and sign up for free.

**2. Add your Outlook/Office 365 email service**
- In EmailJS, go to **Email Services** → **Add New Service**
- Choose **Outlook / Office 365**
- Sign in with your club's Outlook account
- Copy the **Service ID** (e.g. `service_xxxxxxx`)

**3. Create an email template**
- Go to **Email Templates** → **Create New Template**
- Add these three variables in your template body:

```
Subject: {{subject}}

{{message}}

Sent by {{club_name}}
```

- Copy the **Template ID** (e.g. `template_xxxxxxx`)

**4. Copy your Public Key**
- Go to **Account → General**
- Copy your **Public Key** (e.g. `user_xxxxxxxxxxxx`)

**5. Enter credentials in ClubCast Settings**
- Open ClubCast → **Settings** → **Newsletter — EmailJS**
- Fill in: Public Key, Service ID, Template ID, and the recipient email address
- Click **Save & Connect**
- Click **Send Test** to verify everything works

> 💡 The recipient address can be a single address (e.g. your club's mailing list address) or your own address for testing.

---

## Settings

All settings are stored in your **browser's local storage** — they persist between sessions and are never sent to any server except the relevant API when publishing.

### Club Info
| Setting | Description |
|---|---|
| Club Name | Used by the AI in all generated content |
| Club Hashtag | Automatically added to Instagram posts (e.g. `#FCRotterdam`) |
| Language | English or Dutch — the AI writes in your chosen language |

### Channel Credentials
Each channel has its own settings card. Instagram and Facebook credential fields are ready to fill in when you have your Meta API access — they are saved securely in local storage until needed.

---

## Dashboard

The Dashboard gives a live overview of:
- Total announcements published this session
- Active channels and their connection status
- Scheduled and draft posts
- A table of recent announcements with channel breakdown

---

## Saving Drafts & Scheduling

- **Save as Draft** — saves the post without publishing. Find it under **Scheduled** in the sidebar.
- **Schedule for later** — select a date and time in the Publish Timing field. Scheduled posts appear in the Scheduled view.

> ⚠️ Scheduled posts in the current version require the app to be open at the scheduled time to publish. A future version will support server-side scheduling.

---

## Roadmap

The following features are planned for future releases:

- [ ] Direct Instagram publishing via Meta Graph API
- [ ] Direct Facebook publishing via Meta Pages API
- [ ] Server-side scheduling (posts publish even when app is closed)
- [ ] Multi-user access with approval workflow
- [ ] Post analytics (open rates, reach)
- [ ] Template library for recurring post types (match day, transfer window)
- [ ] Image upload and attachment support

---

## Troubleshooting

**AI previews are not generating**
- Make sure you have filled in both the Headline and Message fields
- Check that you have an active internet connection
- Open the browser console (F12) and look for error messages

**Newsletter is not sending**
- Go to Settings → Newsletter and verify all four fields are filled in
- Use the **Send Test** button to check the connection
- Make sure your EmailJS template contains `{{subject}}`, `{{message}}`, and `{{club_name}}`
- Check your Outlook account is still connected in EmailJS → Email Services

**Content is not copying to clipboard**
- Make sure the browser has clipboard permission
- Try clicking the **Copy** button on the individual preview card instead

**Settings are lost after closing the browser**
- Settings are stored in local storage — make sure you are not using private/incognito mode, which clears storage on close

---

## Support

For questions or issues, contact your communications coordinator or the person who set up this tool.

For EmailJS-specific issues: [emailjs.com/docs](https://www.emailjs.com/docs/)

---

*ClubCast — built for FC Rotterdam Communications · 2026*
