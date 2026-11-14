# School Management System (Ethiopia) — Setup Guide

Files
- `index.html` — the whole frontend (HTML + CSS + JS in one file)
- `sql/01_schema.sql` — tables, constraints, indexes, triggers
- `sql/02_rls.sql` — Row Level Security, permission functions, RPCs, photo storage policies
- `sql/03_seed.sql` — your school, Grades 1–12, subjects, fee types, first admin

## 1. Create the Supabase project
1. Sign in at supabase.com → **New project** (pick a region close to you; save the DB password).
2. Open **SQL Editor** and run, in order: `01_schema.sql`, then `02_rls.sql`.
3. **Authentication → Providers → Email**: keep Email enabled and **turn OFF "Allow new users to sign up"** (users are created by you).
4. **Authentication → URL Configuration**: set *Site URL* to your hosted address (e.g. `https://myschool.netlify.app/`) and add it to *Redirect URLs*. Password-reset emails link back here.
5. **Authentication → Users → Add user**: create the admin (tick *Auto Confirm User*).
6. Edit the top of `03_seed.sql` (school name, code, admin e-mail = the user above) and run it. Re-run it if you created the user afterwards.

## 2. Connect index.html
Open **Project Settings → API** and copy the **Project URL** and the **publishable (anon) key**. At the top of the `<script>` in `index.html` replace:

    const SUPABASE_URL = 'YOUR_SUPABASE_URL';
    const SUPABASE_KEY = 'YOUR_SUPABASE_PUBLISHABLE_KEY';

Never paste the `service_role` / secret key here. Safety comes from RLS, not from hiding the file.

## 3. Add users and roles
Create each login in **Authentication → Users**, then in the app: **Settings → Users & roles → Add user** (same e-mail, choose a role). Roles: School Admin (everything), Teacher (own assigned classes: attendance, marks), Accountant (fees, payments, finance reports), Staff (view students/classes + any extra permissions you tick).
For teachers: add the teacher under **Teachers**, assign class + subject rows, and use the same e-mail as their login — they are linked automatically. Teachers only see attendance/marks for their assignments (enforced by the database).

## 4. First steps in the app
Classes & Subjects (check year/terms) → Teachers → Students → Fees → Fee types → Generate invoices.

## 5. Host online (any static host)
- **Netlify**: app.netlify.com/drop → drag the folder containing `index.html`.
- **Cloudflare Pages / Vercel / GitHub Pages**: upload or push the file; no build step.
- Must be served over **HTTPS**. Then update Supabase *Site URL* (step 1.4).

## Notes
- Dates: Gregorian calendar; currency ETB; timezone Africa/Addis_Ababa.
- PDF: use **Print / PDF** and choose "Save as PDF". CSV opens in Excel (UTF-8).
- Somali translations are a first draft — have a native speaker review `so:` in the `I18N` object.
- Student photos go to the private `student-photos` bucket (created by `02_rls.sql`).
- Attendance can be edited for today and yesterday; older dates need the *Edit past attendance* permission (admins have it).
- Multi-school: every table has `school_id`; `schools.status/plan/subscription_ends_at` are already enforced by RLS (a suspended/expired school loses access). A Super Admin UI is not part of this MVP (`profiles.is_super_admin` is reserved).
- The code was smoke-tested against a mocked Supabase client; run the SQL on a fresh project and do one real login before go-live.
- 
