# Support Schedule — графік змін саппорту

Сайт з графіком змін: команда переглядає, тімліди редагують. Вхід через Google.
Хостинг — Vercel (або GitHub Pages), дані — Firebase.

## Що завантажувати на GitHub
Усі файли з цієї папки, **у корінь репозиторію** (самі файли, не папку):
- `index.html` — сайт
- `config.js` — ключі Firebase (заповнити перед завантаженням, див. нижче)
- `firestore.rules` — правила доступу (копія для Firebase)
- `README.md` — цей файл

Файл з даними `8Platform/support-schedule-data/seed.json` **на GitHub не завантажувати.**

## Налаштування Firebase (один раз)
1. https://console.firebase.google.com → **Create a project**.
2. **Authentication** → Get started → **Sign-in method** → Google → Enable → Save.
3. **Authentication → Settings → Authorized domains** → Add domain → адреса сайту без `https://`
   (наприклад `support-schedule-ten.vercel.app`).
4. **Firestore Database** → Create database → production mode → **Rules** → вставити текст із `firestore.rules`,
   замінити `OWNER_EMAIL` на свою пошту → **Publish**.
5. **Project settings** (шестерня) → Your apps → `</>` → Register app → скопіювати значення
   `firebaseConfig` у `config.js` замість `ВСТАВТЕ_...`, у `ownerEmail` — свою пошту.

## Vercel
- Import репозиторію → Framework Preset: **Other** → Root Directory: порожньо → Deploy.

## Перший запуск
1. Відкрити сайт → **Увійти через Google**.
2. Унизу бокового меню **Доступ** → «Перенести дані» → вибрати `seed.json`.
3. Там же вписати домен компанії (усі з робочою поштою переглядають) і пошти тімлідів у «Редактори» → **Зберегти доступ**.
