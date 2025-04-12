# TNYL — Track Now, Your Links 🔗

A completely free, self-hosted, and powerful URL shortener.  
Built on top of [Kutt](https://github.com/thedevs-network/kutt) (massive respect to them 🙌) and customized with love 💙

---

## 💡 What is TNYL?

TNYL (Track Now, Your Links) is a clean, fast, and modern URL shortener that's free forever — no subscriptions, no limits.

Optimized to run with Node.js, and fully customizable. You can either use the hosted
version at https://tnyl.io or deploy your own.

Custom Enhancements in This Fork
- No Docker runs directly via Node.js
- All UI customizations live in the `custom/` folder
- Reverse proxy handled via Nginx (CloudPanel setup below)
- Scheduled DB backups (CloudPanel cron)
- SMTP email: Use AWS SES or any SMTP provider

How to Self-Host TNYL
1. Create a VPS on any cloud provider (Hetzner, Vultr, DigitalOcean, etc.)

2. Install a control panel of your choice (e.g., CloudPanel, HestiaCP)

3. SSH into your VPS and clone the repo:
 git clone https://github.com/tnyl-io/kutt.git && cd kutt

4. Copy the env file and configure:
 cp .env.example .env
 - Edit with your PostgreSQL, Redis, and SMTP settings
 - Refer to the official Kutt guide for env vars

5. Install dependencies:
npm install

6. Setup DB:
 npm run migrate

7. Start the app:
 npm run build && npm start

 DB Backup
 To set up scheduled database backups in CloudPanel, use this cron job:
15 3 * * * clp /usr/bin/bash -c "/usr/bin/clpctl db:backup --retentionPeriod=7" &> /dev/null


📣 Credits
🧠 Built on Kutt

❤️ Custom fork by tnyl.io
