# msilabs.github.io আপডেট প্ল্যান

শুরু: ২০২৬-১১-১৪। সাইটটি এখনও শুধু bKash প্যাকেজ আর Laravel সিরিজের কথা বলে। এই প্ল্যানে যোগ হবে frameworks (Alo, Adhar), VS Code এক্সটেনশন, tools আর simulator। HTML-ভিত্তিক ভিডিও পাঠ থাকবে আলাদা repo `msilabs/learn`-এ, যেটা চলে `msilabs.github.io/learn/` ঠিকানায়।

## কাজের নিয়ম

- এক session-এ একটা milestone। শুরুতে এই ফাইলটা পড়ে নিন, কাজ শেষ হলে checkbox-এ টিক দিন।
- milestone শেষ হলে থামুন। ব্যবহারকারী দেখবেন, তারপর commit করা হবে কিনা জিজ্ঞেস করুন। নিজে থেকে commit বা push করবেন না।
- প্রতিবার `node alo build` চালান। কোনো error বা warning থাকা চলবে না।
- `.alo`-র নিয়ম আছে [AGENTS.md](AGENTS.md)-এ। `dist/` আর `.alo/` কখনো হাতে বদলাবেন না।
- নতুন dependency যোগ করার আগে জিজ্ঞেস করুন। dev server চালু রাখেন ব্যবহারকারী নিজে।

## নেওয়া সিদ্ধান্ত

- সাইটের পরিচয় বড় হবে: bKash প্যাকেজ, frameworks, tools আর lessons। পেইজের কাঠামো মোটামুটি একই থাকবে।
- VS Code এক্সটেনশনের জন্য আলাদা section হবে না। এটা Framework section-এর ভেতরে একটা চওড়া কার্ড (strip) হিসেবে থাকবে।
- Tools section-এ থাকবে CVবানাও, প্রজেক্ট হেলথ আর Poster maker। QR code generator বাদ।
- Simulator-গুলো (Git, Scaling, চিহ্ন টাইপিং) থাকবে হোমপেইজের Learn section-এ।
- **২০২৬-১১-১৪-এ বদলেছে:** পাঠগুলো এই সাইটে নয়, আলাদা repo `msilabs/learn`-এ (local: `../msilabs-learn/`)। GitHub project Pages হিসেবে ওটা চলে `msilabs.github.io/learn/` ঠিকানায়, তাই এই সাইটের nav-এর `/learn/` লিংক ওখানেই যায়। এই সাইটে `pages/learn/` ফোল্ডার রাখা যাবে না।
- পাঠ, player আর scene-এর সব নিয়ম আছে `../msilabs-learn/README.md`-এ। msisaif.github.io-তে থাকবে শুধু লিংক।
- Nav: **Frameworks · Tools · Learn · About**। Story nav থেকে বাদ, section হিসেবে থাকবে।

## তথ্যসূত্র

| জিনিস | মান |
| --- | --- |
| Alo | `@msilabs/alo` 1.2.0। `init --template blank\|portfolio\|docs\|landing`। Docs: https://msilabs.github.io/alo/ |
| Adhar | `@msilabs/adhar` 1.2.0। `init my-api --web` দিলে full stack। Docs: https://msilabs.github.io/adhar/ |
| VS Code | `msilabs.alo-vscode`। install: `code --install-extension msilabs.alo-vscode`। https://marketplace.visualstudio.com/items?itemName=msilabs.alo-vscode, GitHub: https://github.com/msilabs/alo-vscode |
| npm org | https://www.npmjs.com/org/msilabs |
| Alo dependency | `package.json`-এ `^1.2.0` (M1-এ আপডেট করা) |

Tools আর simulator (সবগুলো চালু আছে, যাচাই করা হয়েছে; local ফোল্ডার `/Users/msi/msilabs/projects/`):

| নাম | লিংক | এক লাইনে |
| --- | --- | --- |
| CVবানাও | https://msilabs.github.io/msilabs-cv-builder/ | ডেভেলপারদের CV (PDF), GitHub README আর পোর্টফোলিও, লগইন ছাড়াই |
| প্রজেক্ট হেলথ | https://msilabs.github.io/project-health-dashboard/ | প্রজেক্টের টেক আর সার্ভারের ভার্সনের সাপোর্ট কবে শেষ হবে তার হিসাব। **Alo দিয়ে বানানো** |
| Poster maker | https://msilabs.github.io/msilabs-poster-maker/ | কোড থেকে বাংলা ব্যাখ্যাসহ Facebook আর LinkedIn পোস্টার |
| Git Simulator | https://msilabs.github.io/git-simulator/ | ব্রাউজারে fake terminal, commit graph আর বাংলা ব্যাখ্যা, ১১টা mission |
| Scaling Simulator | https://msilabs.github.io/scaling-simulator/ | Load balancer, cache, replica আর autoscaling, ৬টা চ্যালেঞ্জ |
| চিহ্ন টাইপিং | https://msilabs.github.io/code-typing-practice/ | ১৪টা ভাষার আসল কোড টাইপ করার খেলা |

প্রতিটার GitHub লিংক: `https://github.com/msilabs/<ফোল্ডারের নাম>`।

Alo-র যেসব সীমা মাথায় রাখতে হবে:

- মূল `pages/layout.alo` সব পেইজকে মোড়ায়, তাই Header আর Footer-এর লিংক হতে হবে `/#framework` আকারে, শুধু `#framework` নয়।

## Milestones

### M1: পুরনো তথ্য ঠিক করা
- [x] `package.json`-এ `@msilabs/alo`-কে `^1.2.0` করে `npm install`
- [x] `data/site.json`-এ `nav`: Frameworks (`/#framework`), Tools (`/#tools`), Learn (`/learn/`), About (`/#about`)
- [x] `data/site.json`-এ `title`/`description`, আর `pages/page.alo`-এ `og:description` আর `og:image:alt`। লেখায় frameworks, tools আর lessons আসবে।
- [x] `data/site.json`-এর `links`: `npm` যাবে org পেইজে, আর `vscode` ও `aloDocs` যোগ
- [x] `pages/layout.alo`-এর JSON-LD `sameAs`-এ Alo, Adhar আর Marketplace
- [x] `components/About.alo`: প্রথম টাইলে প্যাকেজের সাথে frameworks আর editor tooling
- [x] `data/story.json`: Nov 2026-এ Alo 1.0 (প্রথম নিজের framework), আর Adhar 1.0 ও VS Code এক্সটেনশন (Alo + Adhar মিলে full stack)। "Now" লাইন নিয়ে ব্যবহারকারীকে জিজ্ঞেস করুন।
- [x] `components/Footer.alo`: Marketplace লিংক যোগ, আর Alo-র credit যাবে Docs-এ

### M2: Framework section
- [x] Alo অংশে hint: `--template docs` (সাথে `portfolio`, `landing`, `blank`)
- [x] VS Code strip: Alo আর Adhar-এর নিচে চওড়া কার্ড। থাকবে বর্ণনা (highlighting, suggestions, Alo-র error আর quick fix, dev server), `<Command>` দিয়ে install command, আর Marketplace ও GitHub লিংক।
- [x] "Built with Alo" লাইন: এই সাইট · প্রজেক্ট হেলথ · Alo docs · Adhar docs

### M3: Tools section
- [x] `data/tools.json` (`packages.json`-এর ধাঁচে) আর `components/ToolCard.alo`
- [x] `components/Tools.alo`, `id="tools"`। কার্ড: CVবানাও, প্রজেক্ট হেলথ ("Built with Alo" badge), Poster maker। প্রতিটায় Open আর GitHub লিংক।

### M4: `/learn/`-এর কাঠামো (পরে `msilabs/learn`-এ সরানো হয়েছে)
- [x] `pages/learn/layout.alo`: ভেতরে `<div lang="bn"><slot /></div>`
- [x] `data/courses.json`: course (`id`, `title`, `description`, `topic`, `color`, `icon`, `lessons[]`) আর পাঠ (`slug`, `title`, `duration`, `status`: `"soon"` ঐচ্ছিক, `thumb` ঐচ্ছিক)। Interactive কার্ডের জন্য আলাদা `data/interactive.json`।
- [x] `pages/learn/page.alo`: শিরোনাম, topic chip-এর ফিল্টার (ছোট `<script>`), course grid আর Interactive grid
- [x] `components/learn/CourseCard.alo`, `components/learn/Cover.alo` (thumbnail), `components/learn/Course.alo` (course পেইজের পুরো ভিউ, `id` prop নেয়)
- [x] `pages/learn/web/page.alo` আর `pages/learn/laravel/page.alo`: প্রতিটা ৩–৪ লাইন, `<Learn.Course id="…" />`
- [x] শুরুর course দুটো: "ওয়েব কীভাবে চলে" (`web`, HTTPS পাঠ) আর "Laravel for Beginners" (`laravel`, শীঘ্রই)। কোনো বানানো পাঠ রাখবেন না।

### M5: HTTPS পাঠ আনা (পরে `msilabs/learn`-এ সরানো হয়েছে)
- [x] উপরের টেবিল অনুযায়ী ফাইলগুলো আনুন আর component-এর নাম বদলান
- [x] অডিওর পাথ হবে `/audio/https.mp3`
- [x] থিম msilabs-এর token-এ বদলান
- [x] `pages/learn/web/https/page.alo`: breadcrumb, `<Learn.Player>` আর `<Scenes.Https />`, স্ক্রিপ্ট খোলা-বন্ধ, আর `courses.json` থেকে আগের ও পরের পাঠের লিংক
- [x] পাঠের নিজস্ব `title`, `description` আর `og:*`

### M6: হোমপেইজ নতুন করে সাজানো
- [x] `components/Learn.alo`: Git Simulator, Scaling Simulator আর চিহ্ন টাইপিং-এর কার্ড, আর "Lessons in Bangla → /learn/"
- [x] `components/Hero.alo`: একটা terminal-এ bKash, অন্যটায় Alo বা Adhar। CTA হবে "Explore projects", fine print-এ শুধু bKash-এর কথা নয়।
- [x] `pages/page.alo`-এ ক্রম: Hero, About, Framework, Packages, Tools, Learn, Story, Founder

### M7: SEO আর share
- [x] `dist/sitemap.xml` দেখা (`/learn/...`-এর sitemap এখন `msilabs/learn` repo-র নিজের)
- [ ] **ব্যবহারকারীর কাজ:** নতুন `public/og.png` (এখনেরটা শুধু bKash দেখায়)। HTTPS পাঠের preview PNG যাবে `msilabs/learn` repo-তে, পাঠের JSON-এর `thumb`-এ।

### M8: পোর্টফোলিও (আলাদা repo, ঐচ্ছিক)
- [ ] `../msisaif.github.io/`-এর OpenSource অংশে Alo, Adhar, VS Code আর msilabs lessons (`/learn/`)-এর লিংক

## M9: পাঠ আলাদা repo-তে সরানো
- [x] `msilabs/learn` (`../msilabs-learn/`): dark premium ডিজাইন, generic player, data-driven scene, `--base /learn/` দিয়ে deploy
- [x] এই সাইট থেকে `pages/learn/`, `components/learn/`, `components/scenes/`, `data/courses.json`, `data/timelines/` আর `public/audio/` সরানো
- [x] হোমের Learn section-এ শুধু simulator আর `/learn/`-এর লিংক
- [ ] **ব্যবহারকারীর কাজ:** `msilabs/learn` repo-র Settings → Pages-এ Source হিসেবে "GitHub Actions" বেছে নেওয়া, তারপর `feat/learn-site` merge করা

## নতুন পাঠ যোগ করার নিয়ম

দেখুন `../msilabs-learn/README.md`। নতুন পাঠ মানে একটা JSON আর একটা mp3, কোনো component লিখতে হয় না।
