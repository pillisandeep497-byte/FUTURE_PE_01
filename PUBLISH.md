# How to publish this repo on GitHub

Three ways. Pick one. **Method 2 (GitHub Desktop) is the easiest if you've never used Git.**

---

## Before you publish — status

**✅ Already done:**
- Author name filled: **Pilli Sandeep** — in `README.md`, `LICENSE`, `PLAN.md`, `final-copy.md`, `qa-scorecard.md`, `docs/client-outreach-whatsapp-email.md`
- Contact filled: **WhatsApp +91 91002 12761** — in `README.md` and the `final-copy.md` author block
- Date filled: **16 September 2026**
- `LICENSE`, `.gitignore` and this file added; all internal links verified working

**⬜ Remaining (optional, 2 minutes):**
- [ ] Screenshot: open `preview/index.html` in Chrome → `Ctrl+Shift+P` → **Capture full size screenshot** → save as `preview/screenshot.png`, then add this line right under the title in `README.md`:
  `![Homepage preview](preview/screenshot.png)`
- [ ] Two client-owned fields are deliberately blank: `_[insert the studio's WhatsApp number]_` in `final-copy.md` (Contact page) and the footer of `preview/index.html`. **Do not put your own number there** — those represent the *client's* phone line, and a stranger's call to you is worse than a visible placeholder. Fill them only with the salon's real number.
- [x] Repo URL filled in: `docs/linkedin-post.md` and `docs/client-outreach-whatsapp-email.md` now link to `https://github.com/pillisandeep497-byte/ai-website-copy-generator`. Your LinkedIn post is copy-paste ready as soon as the repo is public.
- [ ] Optional but strong: drop your LinkedIn post screenshot into `docs/`.

---

## Method 1 — GitHub website (no software at all, fastest)

1. Download the ZIP of this project and unzip it. You'll get a folder called `ai-website-copy-system`.
2. Go to **github.com** → click **+** (top right) → **New repository**.
3. Repository name: `ai-website-copy-generator` · Visibility: **Public** · Do **not** tick "Add a README file". Click **Create repository**.
4. On the empty repo page, click the link **"uploading an existing file"**.
5. Open the unzipped `ai-website-copy-system` folder, select **everything inside it** (`prompts`, `client-runs`, `preview`, `docs`, `README.md`, `PLAN.md`, `LICENSE`, `.gitignore`), and drag it all into the browser upload box.
   - ⚠️ Drag the **contents**, not the folder itself — otherwise everything ends up nested one level too deep.
   - ⚠️ `.gitignore` starts with a dot and may be hidden on Windows (View → Show → Hidden items) or macOS (`Cmd+Shift+.`).
6. Wait for all files to finish uploading, then scroll down and click **Commit changes**.

Your repo is live at `https://github.com/pillisandeep497-byte/ai-website-copy-generator`.

---

## Method 2 — GitHub Desktop (recommended if you'll edit the files later)

1. Install **GitHub Desktop** from desktop.github.com and sign in with your GitHub account.
2. Download and unzip this project to a normal location, e.g. `Documents/ai-website-copy-system`.
3. In GitHub Desktop: **File → Add local repository** → choose that folder.
   - It will say "this directory does not appear to be a Git repository" → click **create a repository** → keep the name, click **Create repository**.
4. You'll see all files listed under "Changes". Type a summary: `AI website copy system for local businesses` → click **Commit to main**.
5. Click **Publish repository** (top bar) → untick **Keep this code private** → **Publish repository**.

Done. From now on, any edit you make shows up as a change you can commit and push with two clicks — which is exactly how you'd maintain a real client repo.

---

## Method 3 — Git command line (if Git is already installed)

```bash
cd path/to/ai-website-copy-system

git init
git add .
git commit -m "feat: AI website copy system for local businesses (Glow Studio, Vizag)"
git branch -M main

# create the EMPTY repo on github.com first, then:
git remote add origin https://github.com/pillisandeep497-byte/ai-website-copy-generator.git
git push -u origin main
```

If it asks for a password, use a **Personal Access Token**, not your account password:
GitHub → Settings → Developer settings → Personal access tokens → Tokens (classic) → Generate new token → tick `repo` → copy it → paste it as the password.

To update later:

```bash
git add .
git commit -m "edit: update prices after client confirmation"
git push
```

---

## After it's live — 5 minutes of polish that reviewers notice

1. **Description** (top-right of the repo page → ⚙️):
   `Structured prompt framework that generates conversion-focused website copy for local businesses — homepage, services, CTAs, local SEO. Built for Future Interns Prompt Engineering Task 1.`
2. **Topics** (same place, "Add topics"):
   `prompt-engineering` · `ai-copywriting` · `conversion-copywriting` · `local-seo` · `future-interns` · `web-agency`
3. **Pin it** to your GitHub profile (Profile → Customize your pins → tick this repo).
4. **Check the README renders** — open the repo on your phone too. Most reviewers will.
5. **Copy the repo URL** and paste it into your LinkedIn post and your submission form.

---

## Common problems

| Problem | Fix |
|---|---|
| Everything nested inside one folder in the repo | You dragged the folder instead of its contents. Delete the repo files and re-upload, or use GitHub Desktop to move them. |
| `.gitignore` / dot-files missing | Enable hidden files in your file manager (Windows: View → Show → Hidden items; macOS: `Cmd+Shift+.`). |
| Upload fails on the drag-and-drop | Do it in 2–3 batches (upload `prompts` first, commit, then the rest). |
| Git says "remote origin already exists" | `git remote set-url origin <correct-url>` |
| Push rejected / "updates were rejected" | The repo has a file you don't have locally (often a README created by GitHub). Run `git pull --rebase origin main` then `git push`. |
| Prices/numbers look wrong in the repo | They're marked `*(verify)*` on purpose. Replace them with the real client's confirmed figures — but never delete the flag without confirming, and never add a review you didn't actually receive. |
