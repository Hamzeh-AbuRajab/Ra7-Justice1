# Justice Compass Hub — وزارة العدل

Full web portal for a roleplay Department of Justice. بوابة إلكترونية متكاملة لوزارة العدل في سيرفرات الرول بلاي.

Citizens submit requests, staff manage them from one admin dashboard, and every action is logged to Discord. المواطن يقدّم طلبه، والمنسوبون يديرونه من لوحة إدارة واحدة، وكل إجراء يُسجَّل في الديسكورد.

**Live | الموقع:** https://justice-compass-hub.lovable.app

## Features | الميزات

- Announcements & summons with type filter | الإعلانات والاستدعاءات مع فلترة حسب النوع
- Departments page | صفحة أقسام الوزارة
- Job application form | نموذج التقديم على الوزارة
- Court session requests | طلب جلسة مع القاضي
- Commercial license requests | طلب رخصة تجارية
- Memo requests | طلب مذكرة
- Archives of documents and decisions | أرشيف الوثائق والقرارات
- Official document templates (report, memo, summons, letter, minutes) with logo watermark, judge signature and stamp | نماذج رسمية بشعار الوزارة وتوقيع القاضي والختم
- Staff directory with ranks, photos and signatures | منسوبي العدل مع الرتب والصور والتواقيع
- State budget (USD) — revenue, expenses, per-department spending | ميزانية الدولة بالدولار
- Admin dashboard to review, accept, reject and delete requests | لوحة إدارة لمراجعة الطلبات وقبولها ورفضها وحذفها
- Discord webhooks: separate channel per form + admin action logs | ربط ديسكورد: قناة لكل نموذج وسجل لإجراءات الإدارة
- Discord username instead of national ID | يوزر الديسكورد بدل رقم الهوية
- Arabic RTL, dark theme with gold accent | واجهة عربية بثيم داكن ولمسة ذهبية

## Roles | الصلاحيات

| Role | الرتبة | Access |
|---|---|---|
| Attorney General | النائب العام | Full access + role management | كامل الصلاحيات |
| Deputy AG | نائب النائب العام | Everything except role management | الكل عدا إدارة الرتب |
| Judge | قاضي | Manage content, requests, templates | إدارة المحتوى والطلبات |
| Law | قانوني | View only | عرض فقط |

Staff ranks: Minister of Justice, Deputy Minister, Judge, Assistant Judge, Prosecutor, Lawyer, Lawyer Trainee.

## Security | الأمان

- Row-level access rules on every table | صلاحيات وصول على مستوى كل جدول
- Roles stored server-side, never in user data | الرتب محفوظة في السيرفر فقط
- Private storage for photos and signatures | تخزين محمي للصور والتواقيع
- Leaked-password protection | حماية من كلمات المرور المسرّبة

## Tech | التقنيات

React + Vite + TypeScript + Tailwind CSS, Lovable Cloud (database, auth, storage, functions).

## Run your own copy | تشغيل نسختك الخاصة

> ⚠️ Every copy must use its **own** backend. Do not use the values in `.env` — they point to the original site.
> ⚠️ كل نسخة لازم يكون لها قاعدة بيانات خاصة فيها. لا تستخدم القيم الموجودة في `.env` لأنها تابعة للموقع الأصلي.

1. Create your own Supabase project and run the SQL files in `supabase/migrations/`.
   أنشئ مشروع Supabase خاص فيك وشغّل ملفات `supabase/migrations/`.
2. Copy `.env.example` to `.env` and fill in **your** values.
   انسخ `.env.example` إلى `.env` وحط قيمك أنت.
3. Deploy the functions in `supabase/functions/` and set your own Discord webhook secrets (`DISCORD_WEBHOOK_*`).
   انشر الدوال وحط روابط ويب هوك ديسكورد الخاصة فيك.

```sh
git clone <this-repository-url>
cd justice-compass-hub
cp .env.example .env   # then edit with your values
npm i
npm run dev
```

## Support | الدعم

Open an Issue here. افتح Issue هنا.

## License | الترخيص

MIT © Hamzeh AbuRajab
