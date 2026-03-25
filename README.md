# 🗑️ FB Mass Activity Deleter

A browser-based tool that generates a custom JavaScript script to bulk-delete your Facebook activity log entries — posts, likes, comments, reactions, shares, and tags — directly from your browser console.

> **No installs. No extensions. No data ever leaves your device.**

---

## ✨ Features

- 🎯 **Selective deletion** — choose which activity types to target (posts, likes, comments, reactions, shares, tags)
- ⚡ **Configurable speed** — set delay between actions (500ms–5000ms) to avoid rate limiting
- 🔢 **Batch control** — set a max item count per run; re-run as many times as needed
- 🛑 **Abort anytime** — stop mid-run with a single console command
- 🔒 **100% local** — script runs entirely in your browser; nothing is sent to any server
- 🎨 **Clean UI** — dark-themed dashboard with live script preview and one-click copy

---

## 🚀 Quick Start

### 1. Back up your data first (important!)

Go to **Facebook Settings → Your Facebook Information → Download Your Information** and request a copy of your data. Deletions are **permanent** and cannot be undone.

### 2. Open the tool

go to `https://haseebather.github.io/fb-mass-activity-remover/fb-activity-deleter.html` 

### 3. Configure your options

- Select the activity types you want to delete
- Adjust the delay slider (recommended: **1000–2000ms**)
- Set a max item count for this run

### 4. Generate and copy the script

Click **⚡ Generate Script**, then **Copy Script**.

### 5. Run it on Facebook

1. Log into [facebook.com](https://facebook.com)
2. Go to your profile → **Activity Log**
3. Navigate to the relevant filter tab (e.g., "Your Posts", "Likes and Reactions")
4. Press **F12** (Windows/Linux) or **Cmd+Option+J** (Mac) to open DevTools
5. Click the **Console** tab
6. Paste the script and press **Enter**

Watch the console for live progress logs. Re-run the script after scrolling to process more items.

### 6. Stop the script anytime

Type this in the console and press Enter:

```js
window.__FB_ERASER_STOP = true
```

---

## 📋 How It Works

The tool generates a self-contained JavaScript snippet that:

1. Scans the current Activity Log page for action menu buttons (`⋯`)
2. Clicks each menu, finds the relevant action (Delete / Unlike / Remove)
3. Confirms any dialog prompts automatically
4. Waits for the configured delay before moving to the next item
5. Scrolls down to load more items when the current batch is exhausted
6. Logs all activity to the browser console so you can track progress

Because Facebook's Activity Log is a dynamic, JavaScript-rendered page, this console-injection approach is the most reliable method for bulk cleanup without a browser extension.

---

## ⚠️ Important Notes

| Topic | Details |
|---|---|
| **Data loss** | Deletions are **permanent**. Always download your data first. |
| **Rate limiting** | Use delays of at least 1000ms. Very fast runs may trigger a temporary block. |
| **Facebook UI changes** | Facebook updates its frontend regularly. If the script stops working, open an issue — the selectors may need updating. |
| **Account risk** | Automated actions technically violate Facebook's Terms of Service. Use at your own discretion. |
| **Compatibility** | Works best in Chrome and Edge. Firefox may require you to type `allow pasting` in the console first. |

---

## 🗂️ Project Structure

```
fb-mass-activity-deleter/
├── index.html      # Main tool — open this in your browser
└── README.md       # You are here
```

---

## 🔧 Troubleshooting

**The script runs but nothing gets deleted**
- Make sure you're on the correct Activity Log filter tab for the type you selected
- Facebook may have updated their HTML structure — open an issue with your browser and a screenshot

**Firefox says "allow pasting"**
- Click in the console, type `allow pasting`, press Enter, then paste the script

**Script stops after a few items**
- Facebook may be rate-limiting you. Increase the delay to 2000–3000ms and try again after a few minutes

**Nothing happens at all**
- Refresh the Activity Log page, open the console again, and re-paste the script

---

## 🤝 Contributing

Pull requests are welcome! If Facebook has changed their UI and the selectors need updating, please open an issue or submit a fix.

1. Fork the repo
2. Create a branch: `git checkout -b fix/selector-update`
3. Commit your changes: `git commit -m 'fix: update activity log selectors'`
4. Push and open a pull request

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Disclaimer

This project is not affiliated with, endorsed by, or connected to Meta Platforms, Inc. in any way. Use responsibly and in accordance with your local laws.
