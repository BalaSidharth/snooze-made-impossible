# ⏰ Snooze™ — Snoozing Made Impossible

> **ACM x MTC — What The Hack?! 2.0**
> **Track 2: The Ultimate Inconvenience**

An alarm clock that takes the single simplest action in the world — pressing **Snooze** — and turns it into a four-stage bureaucratic ordeal. By the time you're allowed to snooze, you're awake. That's the joke, and that's the point.

---

## 📖 What it does

Snooze™ is a deliberately useless web app built for a hackathon where useful software is explicitly banned.

1. **The alarm rings immediately** when you open the page, at a randomly generated time between **5:00 AM and 6:45 AM**, accompanied by a randomly chosen passive-aggressive tagline.
2. There is one button: **SNOOZE**.
3. Clicking it does not snooze. It launches a four-step verification gauntlet:

| Step | What you must do |
|------|------------------|
| **1. CAPTCHA** | Solve a randomly generated challenge — type a random code, a backwards word, an arithmetic sum, the *n*-th letter of a random word, or a word's length. |
| **2. Email verification** | Enter a valid email address, receive a randomly generated **6-digit code**, and type it back correctly. |
| **3. Terms & Conditions** | Read and scroll to the bottom of **14 full pages** of absurd legal text. The "Next Page" button stays locked until you reach the end of each page. |
| **4. Terms quiz** | Answer **5 questions generated fresh on every run** from a bank of 15 facts hidden across the terms. Question phrasing and answer options are randomised each time. |

Only after surviving all four steps does the real **SNOOZE** button appear.

---

## 💥 The penalty system (the actual product)

This is where the inconvenience becomes the feature.

### Critical Snooze Fault

**A single mistake at any stage** — a wrong CAPTCHA, an invalid email address, an incorrect verification code, or one wrong quiz answer — is classified as a **Critical Snooze Fault** (Clause 9 of the Terms).

On a Critical Snooze Fault:

- ⬆️ The alarm volume increases by **an additional +10% instantly**
- 🔁 The entire process **restarts from Step 1 — the CAPTCHA**
- 📖 All 14 pages of terms must be re-read in full
- 🎲 The quiz is **re-randomised** — new facts, new phrasing, new options

### Standing volume escalation

Independently of faults, the alarm volume rises by **+10% every 5 seconds** from the moment the page loads.

**The volume never resets.** Not on a fault, not on a restart, not on success. It only ever goes up, capped at 90% so it stays demo-safe.

### Why this is the joke

Snoozing is meant to take one second. Here it takes several minutes of high-stakes clerical work while a beeping alarm gets progressively louder behind you. The optimal strategy is to simply get up — which is exactly what the alarm wanted all along.

---

## 🎲 Randomisation details

Nothing in the app is hardcoded to repeat. Each run generates:

| Element | How it's generated |
|---------|--------------------|
| **Alarm time** | Random between 5:00 AM and 6:45 AM |
| **Tagline** | Randomly selected from 9 options |
| **CAPTCHA** | Randomly selected from **7 different challenge generators**; two of them mint a brand-new random code on every attempt |
| **Email code** | Fresh random **6-digit** code generated per attempt |
| **Terms quiz** | **5 distinct facts** drawn from a bank of **15**, each with randomly chosen question phrasing and randomly assembled / shuffled answer options |

Because the quiz is assembled from random pieces (fact selection × question stem × distractor combination × optional reverse-mode phrasing), two runs will effectively never present the same quiz twice.

---

## 🚀 How to run it

No build step. No dependencies. No installation. No internet required.

### Option 1 — Just open it

1. Download or clone this repository
2. Double-click Alarm.html
3. It opens in your browser and the alarm starts immediately
4. If your browser blocks audio autoplay, **tap or click anywhere once** to enable sound — a yellow hint appears on screen if this happens
