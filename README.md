# Smart Teacher — المعلم الذكي 🪄

منصّة اختبارات ذكية: الأستاذ(ة) كينشئ الاختبار من بدف، التلميذ(ة) كيطبع ويجاوب ويصوّر، والتصحيح كيبان فورا بالذكاء الاصطناعي.

## الملفات

| الملف | الدور |
|---|---|
| `index.html` | التطبيق كامل (واجهة الأستاذ + التلميذ) |
| `manifest.json` | إعدادات PWA (الاسم، الأيقونة، الألوان) |
| `service-worker.js` | يخلي التطبيق يخدم كـ PWA (يتزاد للشاشة الرئيسية) |
| `icon-192.png` / `icon-512.png` / `apple-touch-icon.png` | أيقونة التطبيق |
| `worker.js` | كود Cloudflare Worker (بوابة Gemini للتصحيح) — **ماخصوش يتحط فـ GitHub**، كيتحط فـ Cloudflare Workers فقط |

## خطوات النشر على GitHub Pages

1. أنشئي repository جديد فـ GitHub (مثلا: `smart-teacher`)
2. ارفعي هاذ الملفات: `index.html`, `manifest.json`, `service-worker.js`, `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`
   (⚠️ `worker.js` ماخصوش يتزاد هنا — راه كودو موجود ديجا فـ Cloudflare)
3. Settings → Pages → Source: اختاري branch `main` والمجلد `/ (root)`
4. صبري دقيقة، غادي يعطيك رابط بحال:
   `https://<اسم-الحساب>.github.io/smart-teacher/`

## قبل الاستعمال

- تأكدي بلي `firebaseConfig` مدمج ديجا فـ `index.html` (سطر `DEFAULT_FIREBASE_CONFIG`)
- تأكدي بلي `CLAUDE_API_URL` فـ `index.html` مشير لرابط Cloudflare Worker ديالك (`https://still-pine-b421.nassimamehdi86.workers.dev/`)
- تأكدي بلي Firestore Rules فـ production mode (شوفي القواعد لي عطيناك)
- تأكدي بلي `GEMINI_API_KEY` مزاد كـ Secret فـ Cloudflare Worker

## إضافة التطبيق للشاشة الرئيسية (بحال أبليكاسيون)

من Chrome (أندرويد): افتحي الرابط ← القائمة (⋮) ← "إضافة إلى الشاشة الرئيسية"
