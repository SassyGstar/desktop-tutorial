# OGO Staff Portal (Demo Version)

🌐 **[Try it live](https://sassygstar.github.io/sassyg-builds/ogo-staff-portal/)**

A single-file staff portal web app built for a multi-office tax firm. It includes:

- 📋 Dashboard with events, announcements, tasks, and smart alerts
- ⏰ Time clock with office geofencing
- 👥 Staff directory and birthdays
- 📝 PTO / request tracking
- 📁 Client pipeline tracker
- 🗂️ **Client Workflow tracker** — return progress from intake through refund, with weekly management reports
- 📊 Analytics
- 🔄 Optional real-time sync across devices (Firebase)

## Client Workflow

The Client Workflow tracker is built directly into the portal (sidebar → **🗂️ Client Workflow**),
not a separate site. It reuses the portal's login, header, colors, logo, and navigation, so there
is no second sign-in screen. It has four tabs: **Overview**, **Client Workflow**, **Daily Log**,
and **Weekly Report**.

- **Uses the portal's signed-in user.** No extra login.
- **Permissions.** Admins and Managers see every client. Regular staff see only the clients
  assigned to them (as preparer or reviewer).
- **Automatic attribution.** Every add, update, and logged contact is stamped with the
  signed-in employee's name in both the workflow audit history and the portal Activity Log.
- **Shared roster.** Assigned-staff and office lists come from the same employee directory
  (`S.employees`) as the rest of the portal.
- **Weekly reports** are generated inside the portal and can be exported to CSV or printed/saved as PDF.

Workflow data lives in `S.clientWorkflow` and syncs on the portal's existing Firebase path,
so sessions, permissions, navigation, and reporting all stay connected. It intentionally does
**not** collect SSNs, dates of birth, bank details, passwords, or tax documents — keep those in
TaxDome and TaxSlayer. Before entering real client names, lock down Firebase Authentication and
database rules (see the recommended next step in the project notes).

## Try it

Just open `index.html` in any web browser — no installation needed.

- Pick any name and click **Enter Portal**
- Admin passcode for this demo: `DEMO1234`

## About this demo

All names, phone numbers, emails, birthdays, and clients in this version are
**fictional sample data**. The Firebase configuration is a placeholder — to
enable live sync, create your own free Firebase project and paste your own
config into `FB_CONFIG` near the top of the script. Without it, the app runs
happily in offline mode and saves everything in your browser.
