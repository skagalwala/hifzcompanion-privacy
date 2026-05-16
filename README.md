# Hifz Musaa'id — Legal Documents

This directory contains the public legal documents required for App Store distribution:

- **`PRIVACY_POLICY.md`** — required by Apple, GDPR, CCPA. Public URL must be reachable.
- **`TERMS_OF_SERVICE.md`** — custom subscription + activation-code terms layered on top of Apple's standard EULA (https://www.apple.com/legal/internet-services/itunes/dev/stdeula/).

Both documents are **drafts** prepared from the App's actual technical behavior. Have a lawyer review before publication — particularly the limitation-of-liability, indemnification, and dispute-resolution clauses.

---

## Hosting on GitHub Pages (free)

GitHub Pages renders markdown files as web pages and gives you a public URL. Step-by-step:

### 1. Create a new GitHub repo

Go to https://github.com/new and create a repository named something like `hifzmusaaid-legal` or `hifz-companion-legal`. Make it **public** (Pages requires public repos on the free tier). Add a README on creation — doesn't matter, you'll overwrite it.

### 2. Push these files to the repo

```bash
cd /Users/SK_Mac/Developer/HifzUlQuran/legal
git init
git remote add origin https://github.com/skagalwala/hifzcompanion-privacy.git
git add PRIVACY_POLICY.md TERMS_OF_SERVICE.md README.md
git commit -m "Initial publication of legal documents"
git branch -M main
git push -u origin main
```

(URLs are pre-filled for `skagalwala/hifzcompanion-privacy`. If you fork to another repo later, update these paths.)

### 3. Enable GitHub Pages

In the repo on GitHub:

1. Click **Settings** (top nav, under the repo name).
2. Click **Pages** in the left sidebar.
3. Under **Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose **main** and the folder **/ (root)**. Click **Save**.
5. Wait 1–3 minutes for the first build.

GitHub Pages will give you a URL like:

```
https://skagalwala.github.io/hifzcompanion-privacy/
```

Visiting that URL renders the `README.md` (this file). To reach the policy and ToS directly:

```
https://skagalwala.github.io/hifzcompanion-privacy/PRIVACY_POLICY
https://skagalwala.github.io/hifzcompanion-privacy/TERMS_OF_SERVICE
```

(GitHub Pages auto-strips the `.md` extension and renders the markdown as HTML.)

### 4. Plug the URLs into App Store Connect

ASC → My Apps → Hifz Musaa'id → **App Information** (left sidebar):

- **Privacy Policy URL** → paste your `PRIVACY_POLICY` link
- **License Agreement** → here you have two choices:
  - Choose **Use Apple's standard license agreement** (recommended) — and link to the `TERMS_OF_SERVICE` URL as a supplementary doc on your App Store listing page (in the description) as additional terms for subscriptions and activation codes
  - Choose **Custom license agreement** and paste your `TERMS_OF_SERVICE` content directly into the ASC form (4000-char limit per locale — likely needs trimming)

The simplest path: stick with Apple's standard EULA in ASC, and host your custom Terms of Service at the URL above. Reference both in the App Store description and inside the App (Settings → About → Legal).

### 5. In-app linking (optional but recommended)

Add a "Legal" row to the About card in Settings that links to both URLs. SwiftUI snippet for reference:

```swift
Link("Privacy Policy",
     destination: URL(string: "https://skagalwala.github.io/hifzcompanion-privacy/PRIVACY_POLICY")!)
Link("Terms of Service",
     destination: URL(string: "https://skagalwala.github.io/hifzcompanion-privacy/TERMS_OF_SERVICE")!)
Link("Apple Standard EULA",
     destination: URL(string: "https://www.apple.com/legal/internet-services/itunes/dev/stdeula/")!)
```

Apple Review checks for in-app links to these from any subscription-bearing app — having them visible in Settings is the cleanest pattern.

---

## Updating documents in the future

The "Last Updated" line at the top of each doc should change whenever you make any change. Major changes (anything affecting user rights, data collection, or refund policy) require **30 days' notice** to users — typically through an email to the address Apple shares with you on Sign in with Apple, plus an in-app banner.

Edit the markdown locally, commit, push:

```bash
cd /Users/SK_Mac/Developer/HifzUlQuran/legal
# edit PRIVACY_POLICY.md or TERMS_OF_SERVICE.md
git add .
git commit -m "Update: <short description>"
git push
```

GitHub Pages will rebuild within 1-3 minutes.

---

## Optional: custom domain

If you ever buy a domain (e.g., `hifzmusaaid.com`):

1. Add a `CNAME` file in this directory containing your domain (e.g., `legal.hifzmusaaid.com`).
2. Configure your DNS with a CNAME record pointing that subdomain to `skagalwala.github.io`.
3. Update **Settings → Pages → Custom domain** in the GitHub repo.

GitHub Pages auto-provisions a free Let's Encrypt SSL cert (~1 hour after DNS propagates). Public URL becomes `https://legal.hifzmusaaid.com/PRIVACY_POLICY` etc.

This is a polish step — not required for App Store submission. The default `github.io` URL works fine.

---

## Files in this directory

| File | Purpose | Required? |
|---|---|---|
| `PRIVACY_POLICY.md` | Data practices disclosure | **Yes** — Apple App Store mandates this |
| `TERMS_OF_SERVICE.md` | Subscription, activation, license terms | Recommended; Apple's standard EULA is the alternative |
| `README.md` | This guide | No — for your reference |

---

## Quick App Store Connect mapping

When filling out ASC App Information for Hifz Musaa'id:

| ASC Field | Value |
|---|---|
| **Privacy Policy URL** | `https://skagalwala.github.io/hifzcompanion-privacy/PRIVACY_POLICY` |
| **License Agreement** | "Apple Standard" (recommended) — and link Terms in your app description |
| **Marketing URL** | Optional — could point to a landing page or your domain when you get one |
| **Support URL** | `mailto:shabbir.com@gmail.com` works fine if you don't have a website yet |

---

## Sanity-check checklist before pasting URLs into App Store Connect

- [ ] Documents have been reviewed by a lawyer (especially Sections 10–12 of Terms — disclaimers, liability, indemnification)
- [ ] Contact email is correct (currently `shabbir.com@gmail.com`)
- [ ] Operator name is correct (currently `Shhabbir Kagalwala`)
- [ ] Governing law / jurisdiction is correct (currently Texas, USA)
- [ ] Subscription pricing matches what you set in ASC ($1.99 Lite / $2.99 Pro)
- [ ] Trial durations match what you set in ASC (30-day Lite / 7-day Pro)
- [ ] Privacy Policy URL is publicly accessible (test in incognito browser tab)
- [ ] Terms of Service URL is publicly accessible
- [ ] "Draft notice" banners at the top of each document have been removed before final publication
- [ ] No broken internal links / typos / placeholder text

Once that list is clean, you're good to paste the URLs into ASC and submit.
