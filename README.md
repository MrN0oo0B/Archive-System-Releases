# نظام الأرشفة الإلكترونية — Electron / Windows 11

تطبيق أرشفة محلي بالكامل يعمل على Windows 11 بدون إنترنت وبدون خادم محلي. الواجهة تُبنى كـ Vite SPA ثابت داخل `dist/`، وتُفتح من Electron عبر `file://`.

## المتطلبات

- Windows 11
- Node.js 20 أو أحدث
- Bun

## التشغيل محلياً أثناء التطوير

```powershell
bun install
bun run dev
```

## بناء نسخة Electron ثابتة

```powershell
bun install
bun run build
```

بعد البناء يجب أن يوجد:

```text
dist/index.html
```

## إنشاء ملف Windows التنفيذي

```powershell
bun run electron:package:win
```

المخرج:

```text
electron-release/ArchiveSystem-win32-x64/ArchiveSystem.exe
```

انسخ مجلد `ArchiveSystem-win32-x64` كاملاً إلى جهاز المستخدم أو اضغطه كـ ZIP. لا يحتاج البرنامج إلى `localhost` أو أي خادم ويب.

## بنية مهمة

- `src/` — واجهة React + TanStack Router
- `electron/` — Main/Preload/SQLite IPC
- `installer/` — إعدادات وتعليمات الحزم
- `dist/` — ناتج بناء SPA، يُنشأ بالأمر `bun run build`
- `bun.lock` — قفل التبعيات

## قاعدة البيانات

قاعدة SQLite محلية تُنشأ تلقائياً عند أول تشغيل داخل مجلد بيانات المستخدم في Windows. المخطط موجود في:

```text
electron/db.cjs
```

## ملاحظات Electron

- `vite.config.ts` يستخدم `base: "./"` حتى تعمل الأصول عبر `file://`.
- `electron/main.cjs` يحمّل `dist/index.html` فقط ولا يسقط إلى `localhost`.
- لا يوجد Nitro SSR أو `.output/server` في مسار حزم Electron.