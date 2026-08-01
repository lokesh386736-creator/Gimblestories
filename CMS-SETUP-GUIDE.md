# Gimbal Picture Creation — Website + CMS Setup Guide

Ye guide aapko step-by-step batayega ki website ko Netlify pe kaise upload karein
aur CMS (content editor) kaise set up karein, taaki aap khud se **text, images,
videos, contact info** waghera change kar sakein — bina coding kiye — aur wo
seedha live website pe reflect ho jaye.

**Important cheez pehle samajh lein:** Is CMS (Decap/Netlify CMS) ko live changes
karne ke liye ek **GitHub repository** chahiye hoti hai (free hai). Sirf seedha
Netlify pe drag-and-drop se upload karne se CMS kaam nahi karega, kyunki CMS
apne changes GitHub repo mein "save/commit" karta hai, aur wahi se Netlify site
ko dobara build karta hai. Neeche poora process step-by-step hai.

---

## ✅ Kya-kya naya add hua hai is update mein

1. **Call & WhatsApp number `8817140950`** add kar diya gaya hai — Hero section
   ke WhatsApp floating button, Contact section, aur Footer — sabhi jagah.
   Format: Call `+91 88171 40950`, WhatsApp `918817140950`.
2. Poori website ab ek **CMS (content/data.json)** se chalti hai — matlab har
   section (Hero, Services, Portfolio, Showreel Videos, About, Process,
   Testimonials, FAQs, Contact, Footer) ab CMS se edit ho sakta hai.
3. CMS mein **image upload** (manual file upload) ka option hai — Portfolio
   photos waghera CMS se hi upload kar sakte hain.
4. Portfolio, Services, Showreel Videos, Testimonials, FAQs, Process Steps —
   in sabmein **naya item add karna** ya **item remove karna**, dono possible
   hai (list ke "+ Add" aur trash icon se).
5. YouTube videos ka playback thoda better bana diya gaya hai (proper embed
   settings + agar thumbnail load na ho to broken image ki jagah clean
   fallback dikhega) — lekin **sabse zaroori baat neeche "YouTube Videos"
   section mein padhein.**

---

## 📁 Is package mein kya-kya files hain

```
index.html              → Main website file
netlify.toml            → Netlify settings
content/data.json       → Saara website content (CMS isi file ko edit karta hai)
admin/index.html        → CMS ka login/editor page (yahi khulega yoursite.com/admin)
admin/config.yml        → CMS ki settings (kaunse fields dikhne hain)
uploads/                → Yahan CMS se upload ki gayi images save hongi
```

Sab files/folders ka structure **exactly waise hi rakhein** jaise diya gaya hai —
folder names mat badlein.

---

## Step 1 — GitHub par repository banayein (free)

1. https://github.com pe jaake free account banayein (agar pehle se nahi hai).
2. Top-right `+` icon → **New repository** click karein.
3. Naam dein jaise `gimbal-website` → **Public** ya **Private** koi bhi rakh
   sakte hain → **Create repository**.
4. Us naye repo ke andar **"uploading an existing file"** link pe click karein
   (ya "Add file → Upload files").
5. Is poore package ki saari files aur folders (index.html, netlify.toml,
   content/, admin/, uploads/) us upload box mein **drag & drop** kar dein
   (poora folder structure GitHub khud maintain kar leta hai jab aap poora
   folder drag karte hain).
6. Neeche **Commit changes** button dabayein.

---

## Step 2 — Netlify par site connect karein

1. https://app.netlify.com pe login/signup karein.
2. **Add new site → Import an existing project** click karein.
3. **GitHub** choose karein aur wahi repo (`gimbal-website`) select karein.
4. Build settings kuch bhi change karne ki zaroorat nahi — bas
   **Deploy site** dabayein.
5. Kuch second mein aapki site live ho jayegi, ek URL milega jaisa
   `https://random-name-123.netlify.app`.
6. (Optional) Site settings → Domain management se apna khud ka domain bhi
   jod sakte hain baad mein.

---

## Step 3 — Netlify Identity + Git Gateway on karein (CMS login ke liye)

1. Netlify dashboard mein apni site kholein → **Site configuration** (ya
   "Site settings") → **Identity** → **Enable Identity**.
2. Identity ke andar **Registration preferences** → **Invite only** select
   karein (isse sirf aap hi CMS access kar paayenge, koi aur nahi).
3. Neeche **Services → Git Gateway** → **Enable Git Gateway**.
4. Ab top pe **Identity** tab kholein → **Invite users** → apna email daalein
   → Invite bhej dein.
5. Aapke email pe ek invite link aayega → us par click karke apna **password**
   set kar lein.

---

## Step 4 — CMS use karna shuru karein

1. Browser mein jaayein: `https://YOUR-SITE-NAME.netlify.app/admin/`
2. Apne email + password se login karein.
3. Aapko ek dashboard dikhega **"Website Content" → "Site Content"** — isi
   ek page ke andar saare sections hain:
   - Contact Info & Social Links (phone, WhatsApp, email, address, social)
   - Hero Section
   - Showreel Videos (YouTube)
   - Services
   - Portfolio Gallery (image upload yahin hota hai)
   - About / Studio Section
   - Process Steps
   - Testimonials
   - FAQs
   - Footer
4. Jo bhi section edit karna hai, usme change karein. List wale sections
   (Services, Portfolio, Videos, Testimonials, FAQs, Process) mein neeche
   **"+ Add"** button se naya item add kar sakte hain, aur trash/delete icon
   se koi item remove kar sakte hain.
5. Image upload karne ke liye kisi bhi "Photo/Image" field pe click karein →
   **"Upload"** tab se apne computer se photo choose karein.
6. Sab kuch set hone ke baad **Save** karein, phir top-right se
   **Publish → Publish now** karein.
7. Netlify khud-ba-khud (30–60 second mein) site ko rebuild karke live kar
   dega. Live website ko refresh karke apna change dekh sakte hain.

---

## 🎥 YouTube Videos ke baare mein — zaroor padhein

Website ke andar abhi 4 **sample/placeholder video links** dale hue hain (ye
demo ke liye the, real wedding films nahi hain). Isliye kabhi-kabhi ye theek se
play nahi hote.

**Inhe sahi se chalane ke liye:**
1. CMS kholein → **Showreel Videos** section.
2. Har video ke "YouTube Video Link" field mein apne **asli, public YouTube
   video ka poora link** paste karein — jaise:
   `https://www.youtube.com/watch?v=XXXXXXXXXXX`
3. Dhyaan rahe: video **Public** ya **Unlisted** hona chahiye (Private nahi),
   tabhi wo website pe embed hoke chalega.
4. Jitne bhi naye wedding films aap add karna chahte hain, "+ Add" se naya
   video-item bana ke uska link, tag aur title daal dein.

Ye badlaav karte hi videos properly load aur play hone lagenge, kyunki
technical setup already improved kar diya gaya hai (better playback settings +
agar koi thumbnail na mile to clean fallback dikhega, broken image nahi).

---

## ❓ Agar kuch atak jaaye

- **CMS `/admin/` khulte hi "Not Found" ya blank page dikhaye** → Identity ya
  Git Gateway abhi enable nahi hui, Step 3 dobara check karein.
- **Login ho gaya par changes save/publish nahi ho rahe** → Git Gateway
  enable hai ya nahi, aur GitHub repo sahi se connect hai ya nahi, check
  karein.
- **Naya number ya content change karna hai** → Hamesha CMS (`/admin/`) se hi
  karein, taaki dobara live update ho sake. Directly file edit karne ki
  zaroorat nahi.
- **`admin/config.yml` mein `site_url` / `display_url`** abhi
  `YOUR-SITE-NAME.netlify.app` placeholder hai — deploy hone ke baad GitHub
  pe jaake is file ko edit karke apna asli Netlify URL daal dein.

Koi bhi step mein dikkat aaye to bata dijiye — main aage guide kar dunga.
