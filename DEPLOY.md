# cvbanao.com — Vercel-এ লাইভ করার ধাপ

## ১. ফাইল তালিকা (সব এই ফোল্ডারে)
- index.html (হোম পেজ)
- cv.html (সিভি বানানোর পেজ)
- guides.html, guide-cv-contents.html, guide-cv-writing.html, guide-gpa.html, bangladeshi-cv-format.html
- about.html, contact.html, faq.html, privacy.html, terms.html
- guide.css (সব পেজের স্টাইল, অবশ্যই লাগবে)
- og.png, favicon.png (শেয়ার ছবি ও ট্যাব আইকন)
- robots.txt, sitemap.xml (সার্চ ইঞ্জিনের জন্য)

এই ফোল্ডারে ভিডিও বা অন্য টুলের ফাইল নেই। শুধু ওয়েবসাইট।

## ২. Vercel-এ আপলোড (সহজ পথ: GitHub হয়ে)
1. GitHub-এ নতুন একটা repository বানান (যেমন `cvbanao`), এই ফোল্ডারের সব ফাইল আপলোড করুন।
2. vercel.com-এ GitHub দিয়ে লগইন করুন।
3. "Add New... → Project" → repository বেছে "Import" চাপুন।
4. Framework Preset: **Other**। Build Command ও Output Directory খালি রাখুন।
5. "Deploy" চাপুন। কয়েক মিনিটে একটা `*.vercel.app` লিংক আসবে। সেটা খুলে সাইট কাজ করছে কিনা দেখুন।

বিকল্প (কমান্ড লাইন): Node.js লাগবে।
```
npm i -g vercel
cd cvbanao-site
vercel          # প্রথমবার প্রশ্নের উত্তর দিন
vercel --prod   # লাইভ করুন
```

## ৩. কাস্টম ডোমেইন cvbanao.com যুক্ত করা
1. Vercel প্রজেক্ট → Settings → Domains → `cvbanao.com` লিখে Add করুন। একই সাথে `www.cvbanao.com`-ও যোগ করুন।
2. ডোমেইন যেখান থেকে কেনা (রেজিস্ট্রার) সেখানে DNS রেকর্ড বসান। Vercel যে মান দেখায় সেটাই ব্যবহার করুন। সাধারণত:
   - `@` (root) → A record → `76.76.21.21`
   - `www` → CNAME → `cname.vercel-dns.com`
3. কয়েক মিনিট থেকে কয়েক ঘণ্টায় ডোমেইন চালু হবে। Vercel-এ সবুজ টিক দেখলে হয়ে গেছে।
4. `www.cvbanao.com` ও `cvbanao.com` দুটোই যেন একই সাইটে যায়, Vercel-এ একটাকে প্রধান হিসেবে সেট করুন।

## ৪. লাইভ হওয়ার পর পরীক্ষা
- হোম পেজ খোলে, মেনুর সব লিংক কাজ করে (সুবিধা, টেমপ্লেট, গাইড, FAQ, যোগাযোগ)।
- মোবাইলে নিচের মেনুবার আর "সিভি বানান" বোতাম কাজ করে।
- সিভি বানানো: সব ধাপ, যাচাই (নাম/মোবাইল/ইমেইল), স্বাক্ষর আপলোড, টেমপ্লেট, ATS চেক, কভার লেটার।
- ডাউনলোড: PDF, Word, PNG, JPG চারটাই নামে।
- ফুটারে MD ABU SUFIAN লিংক ফেসবুকে যায়।
- `https://cvbanao.com/sitemap.xml` খুললে XML দেখায়।

## ৫. সার্চ ইঞ্জিনে জমা
1. Google Search Console (search.google.com/search-console) → Add property → `cvbanao.com`। DNS দিয়ে মালিকানা যাচাই করুন।
2. Sitemaps → `https://cvbanao.com/sitemap.xml` জমা দিন।
3. ফেসবুকে শেয়ার ডিবাগার (developers.facebook.com/tools/debug) দিয়ে `https://cvbanao.com/` একবার "Scrape again" করুন।

## ৬. পরে আপডেট করার নিয়ম
- GitHub ব্যবহার করলে ফাইল বদলে commit করলেই Vercel নিজে থেকে নতুন ভার্সন লাইভ করবে।
- CLI ব্যবহার করলে আবার `vercel --prod` চালান।
