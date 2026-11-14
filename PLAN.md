# msilabs.github.io আপডেট প্ল্যান

শুরু: ২০২৬-১১-১৪। সাইটটি এখনও শুধু bKash প্যাকেজ আর Laravel সিরিজের কথা বলে। এই প্ল্যানে যোগ হবে frameworks (Alo, Adhar), VS Code এক্সটেনশন, tools, আর একই সাইটে `/learn/`, যেখানে থাকবে HTML-ভিত্তিক ভিডিও পাঠ।

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
- Simulator-গুলো (Git, Scaling, চিহ্ন টাইপিং) যাবে `/learn/`-এ, "Interactive" কার্ড হিসেবে।
- `/learn/` থাকবে এই সাইটেই, আলাদা repo-তে নয়। পাঠগুলো msilabs-এর নামে, আর msisaif.github.io-তে থাকবে শুধু লিংক।
- `/learn/`-এ দুই স্তর: **course → পাঠ**। Topic-এর আলাদা পেইজ নেই, শুধু ফিল্টার chip।
- Thumbnail ডেটা থেকে বানানো cover: gradient, icon, ▶ আর সময়। ঐচ্ছিক `thumb` PNG দিলে ওটা দেখাবে।
- `/learn/`-এর লেখা বাংলায়, `lang="bn"` দিয়ে মোড়ানো। সাইটের বাকিটা ইংরেজি (`en`)।
- Nav: **Frameworks · Tools · Learn · About**। Story nav থেকে বাদ, section হিসেবে থাকবে।

## তথ্যসূত্র

| জিনিস | মান |
| --- | --- |
| Alo | `@msilabs/alo` 1.2.0। `init --template blank\|portfolio\|docs\|landing`। Docs: https://msilabs.github.io/alo/ |
| Adhar | `@msilabs/adhar` 1.2.0। `init my-api --web` দিলে full stack। Docs: https://msilabs.github.io/adhar/ |
| VS Code | `msilabs.alo-vscode`। install: `code --install-extension msilabs.alo-vscode`। https://marketplace.visualstudio.com/items?itemName=msilabs.alo-vscode, GitHub: https://github.com/msilabs/alo-vscode |
| npm org | https://www.npmjs.com/org/msilabs |
| এখনকার Alo dependency | `package.json`-এ `^1.1.0`, install করা আছে 1.1.0 |

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

HTTPS পাঠের উৎস: `../alo-https-player/`

| উৎস | গন্তব্য |
| --- | --- |
| `components/Player.alo` | `components/learn/Player.alo` → `<Learn.Player>` |
| `components/HttpsScene.alo` | `components/scenes/Https.alo` → `<Scenes.Https />` |
| `components/ScriptList.alo` | `components/learn/Script.alo` → `<Learn.Script>` |
| `data/lesson.json` | `data/timelines/https.json` |
| `public/narration.mp3` | `public/audio/https.mp3` (`old-narration.mp3` আনবেন না) |
| `global/theme.css` (লাইট আর ডার্ক থিম) | msilabs-এর token-এ বদলে নিন (navy, mint, sun) |

Alo-র যেসব সীমা মাথায় রাখতে হবে:

- `[slug]` এক স্তরের বেশি হয় না, আর পাথের শেষে থাকতে হয়। প্রতিটা পাঠের Scene component আলাদা, তাই পাঠের পেইজগুলো সাধারণ ফোল্ডার।
- `data/timelines/` ফোল্ডারে শুধু ফাইল আছে, তাই এটা একটা **array**। খুঁজতে হবে `slug` দিয়ে: `data.timelines.find(t => t.slug === 'https')`।
- মূল `pages/layout.alo` `/learn/`-এর পেইজগুলোকেও মোড়ায়, তাই Header আর Footer-এর লিংক হতে হবে `/#framework` আকারে, শুধু `#framework` নয়।

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
- [ ] `data/tools.json` (`packages.json`-এর ধাঁচে) আর `components/ToolCard.alo`
- [ ] `components/Tools.alo`, `id="tools"`। কার্ড: CVবানাও, প্রজেক্ট হেলথ ("Built with Alo" badge), Poster maker। প্রতিটায় Open আর GitHub লিংক।

### M4: `/learn/`-এর কাঠামো
- [ ] `pages/learn/layout.alo`: ভেতরে `<div lang="bn"><slot /></div>`
- [ ] `data/courses.json`: course (`id`, `title`, `description`, `topic`, `color`, `icon`, `lessons[]`) আর পাঠ (`slug`, `title`, `duration`, `status`: `"soon"` ঐচ্ছিক, `thumb` ঐচ্ছিক)। Interactive কার্ডের জন্য আলাদা `data/interactive.json`।
- [ ] `pages/learn/page.alo`: শিরোনাম, topic chip-এর ফিল্টার (ছোট `<script>`), course grid আর Interactive grid
- [ ] `components/learn/CourseCard.alo`, `components/learn/Cover.alo` (thumbnail), `components/learn/Course.alo` (course পেইজের পুরো ভিউ, `id` prop নেয়)
- [ ] `pages/learn/web/page.alo` আর `pages/learn/laravel/page.alo`: প্রতিটা ৩–৪ লাইন, `<Learn.Course id="…" />`
- [ ] শুরুর course দুটো: "ওয়েব কীভাবে চলে" (`web`, HTTPS পাঠ) আর "Laravel for Beginners" (`laravel`, শীঘ্রই)। কোনো বানানো পাঠ রাখবেন না।

### M5: HTTPS পাঠ আনা
- [ ] উপরের টেবিল অনুযায়ী ফাইলগুলো আনুন আর component-এর নাম বদলান
- [ ] অডিওর পাথ হবে `/audio/https.mp3`
- [ ] থিম msilabs-এর token-এ বদলান
- [ ] `pages/learn/web/https/page.alo`: breadcrumb, `<Learn.Player>` আর `<Scenes.Https />`, স্ক্রিপ্ট খোলা-বন্ধ, আর `courses.json` থেকে আগের ও পরের পাঠের লিংক
- [ ] পাঠের নিজস্ব `title`, `description` আর `og:*`

### M6: হোমপেইজ নতুন করে সাজানো
- [ ] `components/Learn.alo` হবে teaser: সর্বশেষ পাঠের কার্ড, simulator, Laravel সিরিজ (শীঘ্রই), আর "সব দেখুন → /learn/"
- [ ] `components/Hero.alo`: একটা terminal-এ bKash, অন্যটায় Alo বা Adhar। CTA হবে "Explore projects", fine print-এ শুধু bKash-এর কথা নয়।
- [ ] `pages/page.alo`-এ ক্রম: Hero, About, Framework, Packages, Tools, Learn, Story, Founder

### M7: SEO আর share
- [ ] `dist/sitemap.xml`-এ `/learn/...` পেইজগুলো আছে কিনা দেখুন
- [ ] **ব্যবহারকারীর কাজ:** নতুন `public/og.png` (এখনেরটা শুধু bKash দেখায়) আর HTTPS পাঠের preview PNG। ছবি পেলে জায়গামতো বসান।

### M8: পোর্টফোলিও (আলাদা repo, ঐচ্ছিক)
- [ ] `../msisaif.github.io/`-এর OpenSource অংশে Alo, Adhar, VS Code আর msilabs lessons (`/learn/`)-এর লিংক

## নতুন পাঠ যোগ করার নিয়ম

1. `data/timelines/<slug>.json`: ক্যাপশন আর সময়ের টাইমলাইন
2. `components/scenes/<Name>.alo`: দৃশ্য
3. `public/audio/<slug>.mp3`: ধারাবর্ণনা
4. `pages/learn/<course>/<slug>/page.alo`: `<Learn.Player>` আর `<Scenes.Name />`
5. `data/courses.json`: সেই course-এর `lessons`-এ এক লাইন
