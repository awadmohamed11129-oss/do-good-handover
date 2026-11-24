# Day one for the new owner: set up both Sheets and the app

Do these steps in order. You need: one Google account that will own everything, the link of Sheet 1 (contractor intake), the link of Sheet 2 (job collector), a free Gemini key of your own (make it yourself at aistudio.google.com with your Google account: click Get API key, then Create API key; never type it anywhere except the box in step 6), and the desktop app.

Total: about 20 to 25 minutes the first time (the collector part measured about 8 minutes of clicking and waiting on 2026-11-24, including the 3-minute first run). Nothing here can break the original Sheets: you only ever work in your own copies.

Status of this page: the menu names are the real ones. The "Make a copy" minutes and the job collector steps (8 to 11) were timed on 2026-11-24 on a real copy (set up, connect, allow access, check again, first run all worked). Minutes marked "estimate" belong to the intake Sheet steps and were not timed.

Two things to know before you start:
- The first time you click any menu item, Google shows a window called "Authorization required". Click OK, pick your account, click Advanced, click "Go to ... (unsafe)", click Allow. It asks once per Sheet. It says "unsafe" only because you own the script and Google has not reviewed it.
- If Google ever says "Sorry, unable to open the file" or "Page Not Found", you are signed in to two or more Google accounts. Open a private window, sign in to only the account that owns the Sheet, and open the Sheet there.

## Part 1. Sheet 1: the contractor intake (the form and the app folder)

1. Open the link of Sheet 1. Click File, then Make a copy. Give it a name you will recognise. Click Make a copy. A new tab opens: this is your Sheet 1. (1 minute, measured)
2. In your copy, click the menu **Contractor intake**, then **1. Set up now (Google asks permission the first time)**. Do the permission window above, then click the menu item again. If it asks "Who is already in this Sheet?", click **YES** (Start empty). (about 1 minute, estimate)
3. The one step Google makes you do by hand: publish the form. Click **Extensions**, then **Apps Script**. At the top right click **Deploy**, then **New deployment**. Click the gear icon, choose **Web app**. Set "Execute as" to **Me** and "Who has access" to **Anyone**. Click **Deploy**. If Google asks for permission again, click Allow. Close the Apps Script tab. (about 3 minutes, estimate)
4. Back in the Sheet, click **Contractor intake**, then **Check again**. If the line "Form link" is still red, copy the Web app address from step 3 (it ends in /exec), click **3. Paste the form link (only if it was not found)** and paste it. (1 minute)
5. Open the first tab, **Setup**. Every line with a status should say OK or OPTIONAL. Lines that say TO DO tell you what to click.
6. Click **Contractor intake**, then **2. Add the Gemini key**. Paste the key. Click OK. The key is stored privately and is never shown in a cell. Click **Check again**. (1 minute)

Optional: turn on email alerts. If the menu **Contractor intake** shows **Email alerts (on / off)**, click it. It asks which address should get the alerts (leave the box empty to use the address of the Sheet's owner), then three yes/no questions: an email when a new contractor signs up, a short daily summary, an email if something breaks. It then asks where contractors' replies should go, and offers to send you one test email. You can run it again any time to change or switch them off. If your menu does not show that item, click **Extensions**, **Apps Script**, the gear (**Project Settings**), **Script properties**, and set `NOTIFY_EMAIL` to your address and `NOTIFY_EMAIL_ON` to `true` (for the daily summary also `DIGEST_EMAIL_ON` = `true`; for replies `REPLY_TO_EMAIL` = your address). Alerts stay off until you do one of these.

The **Setup** tab now shows two links. Keep this tab open, you need them in steps 12 and 13:
- **Link to send to contractors**: this is the one you give to contractors.
- **Download link (paste it into the desktop app once)**: treat it like a password.

## Part 2. Sheet 2: the job collector

7. Open the link of Sheet 2. Click File, then Make a copy, name it, click Make a copy. (1 minute, measured)
8. In your copy, click the menu **Job collector**, then **1. Set up now (Google asks permission the first time)**. Do the permission window, then click the menu item again. It asks: "Which job list do you want to start with?" Click **YES** (a clean list, recommended for a new owner). Your copy then switches on the daily timers (about 6 am and about 10 am), makes the Drive folder "Job collector exports" in your Drive, and shows the result. (about 30 seconds after the permission window, measured 2026-11-24 on a real copy; the permission window itself is a few clicks)
9. Click **Job collector**, then **Run now**. The first run takes about 3 minutes. When it finishes a message says "The run is finished." and the **Setup** tab line "First run done" turns OK. (about 3 minutes, measured 2026-11-24)
10. Click **Job collector**, then **2. Connect the contractor list**. Paste the link of YOUR Sheet 1 (the copy from step 1; its address starts with https://docs.google.com/spreadsheets/d/). Click OK. If you leave the box empty and click OK, the collector still works, with its built-in list of roles; you only lose the "fits" line in the job files. (under 1 minute, measured 2026-11-24)
11. One click only you can do: open the tab **Talent roles (auto)**, click cell A1, click **Allow access**. Then click **Job collector**, then **Check again**. The line "Contractor list connected" turns OK. (about 1 minute including the Check again wait of about 25 seconds, measured 2026-11-24)

If the **Setup** tab line "Export folder ready" says Google has not switched the Drive service on, do what that line says (Extensions, Apps Script, the + next to Services, Drive API, Add), then click **Check again**.

## Part 3. Connect them and finish

12. On the **Setup** tab of Sheet 2, copy the link next to **Job files folder**. Go to Sheet 1, click **Contractor intake**, then **4. Set the jobs folder (optional)**, paste the link, click OK. (1 minute)
13. On the **Setup** tab of Sheet 1, copy the **Download link (paste it into the desktop app once)**. Download the improved desktop app first: Mac, Apple silicon: https://github.com/awadmohamed11129-oss/contract-headhunter/releases/download/v1.1.0-improved/dogoodtalent-mac-intel.dmg (opens through Apple's Rosetta). Mac, Intel: https://github.com/awadmohamed11129-oss/contract-headhunter/releases/download/v1.1.0-improved/dogoodtalent-mac-intel.dmg. Windows: https://github.com/awadmohamed11129-oss/contract-headhunter/releases/download/v1.1.0-improved/dogoodtalent-windows.zip. Then open the desktop app (on a Mac the first open needs one extra yes: System Settings, Privacy & Security, Open Anyway), go to Settings, paste the link under "Your do good link" and click **Test link**: it should say how many contractors and how many jobs it found. (In Wilson's released version, which has no such box, load the two folders by hand instead.) (1 minute)

## You are done when

- Both **Setup** tabs show OK (or OPTIONAL) on every line.
- The Drive folder "Job collector exports" holds job files after the first run.
- The desktop app test says it found contractors and jobs.

From now on the collector runs by itself every morning. Look at the top line of the **Start here** tab of Sheet 2: "All good" means nothing to do; "Action needed" says what to do.
