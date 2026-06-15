# উৎসে কর টুল — GitHub → Vercel ডিপ্লয়

একটি স্ট্যাটিক সাইট (একটাই HTML ফাইল)। কোনো বিল্ড স্টেপ নেই, কোনো ডিপেনডেন্সি ইনস্টল করতে হয় না।

## ফাইলসমূহ
- `index.html` — টুলটি (সাইটের রুট `/` এ এটাই দেখাবে)
- `vercel.json` — সিকিউরিটি হেডার + ক্লিন URL কনফিগ
- `README.md` — এই ফাইল

---

## ধাপ ১ — GitHub-এ আপলোড

**ওয়েব দিয়ে (সহজ):** GitHub-এ একটা নতুন রিপো বানাও → "uploading an existing file" → এই তিনটা ফাইল (`index.html`, `vercel.json`, `README.md`) টেনে এনে commit করো।

**অথবা git দিয়ে:**
```bash
git init
git add .
git commit -m "Add উৎসে কর টুল"
git branch -M main
git remote add origin https://github.com/<তোমার-ইউজারনেম>/<রিপো>.git
git push -u origin main
```

## ধাপ ২ — Vercel-এ ডিপ্লয়

1. https://vercel.com → **Add New… → Project**
2. GitHub রিপোটি **Import** করো।
3. সেটিংস ডিফল্ট রাখো:
   - **Framework Preset:** Other
   - **Build Command:** (ফাঁকা)
   - **Output Directory:** (ফাঁকা)
4. **Deploy** চাপো।

কয়েক সেকেন্ডে লাইভ URL পাবে, যেমন `https://<রিপো>.vercel.app`।
এরপর প্রতিবার `main` ব্রাঞ্চে push করলেই অটো-রিডিপ্লয় হবে।

---

## আপডেট করতে চাইলে
শুধু `index.html` নতুন ভার্সন দিয়ে replace করে আবার push করো — Vercel নিজে রিডিপ্লয় করবে।

## নোট
- টুলটি অনলাইনে ফন্ট (Google Fonts CDN) লোড করে, তাই ডিপ্লয় করা সাইটে ইন্টারনেট থাকলেই চলবে।
- এটি কেবল রেফারেন্স টুল; আইনি/কর পরামর্শ নয়। প্রকৃত হারের জন্য মূল প্রজ্ঞাপন (SRO ২১০/২০২৬) দেখো।

> নিজের আলাদা সাইট না বানিয়ে যদি তোমার বিদ্যমান সাইটের "Resources" এর আন্ডারে যুক্ত করতে চাও,
> তাহলে `index.html` ফাইলটিকে তোমার মূল রিপোর `public/resources/utshe-kor-tool.html` পাথে রাখলেই হবে
> (আগের গাইডে বিস্তারিত আছে)।
