# Retro Microsoft Mod7 Key Generator & Validator

A client-side web utility that generates and validates authentic product installation serial numbers for legacy 1990s Microsoft software. 

This engine is built entirely using standard HTML5, CSS3, and modern vanilla JavaScript, wrapped inside a classic Windows 95 Setup Wizard graphical aesthetic.

## 🌟 Features

*   **Classic Retro UI:** Styled exactly like a Windows 95 installation screen, complete with the iconic teal background, retro bevels, and title bars.
*   **Real-Time Validation Engine:** Provides precise feedback as you type, explaining exactly which mathematical rule a custom key violates if validation fails.
*   **Windows 95 Error Dialog Box:** Clicking the "Validate" button on an invalid key triggers a classic retro error popup window.
*   **Batch Generation Export:** Generate up to 500 keys simultaneously and download them directly as a `.txt` file for backup or deployment testing.

---

## 🧠 Behind the Algorithm

During the 1995–2003 era, Microsoft utilized a fast, lightweight mathematical verification method known as the **Mod7 Algorithm** inside retail CDs and OEM distribution media to combat entry-level piracy without slowing down system installations.

### Enforced Rules Engine

1. **Standard CD Keys (`XXX-XXXXXXX`)**
   - The first segment represents a site/facility sequence spanning `000` through `998`. Blacklisted values (`333`, `444`, `555`, `666`, `777`, `888`, `999`) are programmatically blocked.
   - The sum of all seven digits in the second segment must be perfectly divisible by `7`.
   - To counter the early "all-zeros bug" (where `0 % 7 === 0`), modern check-digit rules are applied ensuring the last trailing digit can never be `0`, `8`, or `9`.

2. **11-Digit Keys (`XXXX-XXXXXXX`)**
   - Primarily used in software suites like Office 97.
   - Enforces a structural constraint where the 4th digit must equal `(3rd digit + 1)` or `(3rd digit + 2)`. Correct modular rollover handling prevents calculation exceptions at value limits (e.g., when the 3rd digit is 9).

3. **OEM Keys (`XXXXX-OEM-XXXXXXX-XXXXX`)**
   - **Segment 1:** Represents creation date tags mapping Julian days `001-366` alongside vintage distribution years `95-03`.
   - **Segment 2:** Must literally contain the exact characters `OEM`.
   - **Segment 3:** Follows strict mod7 sum validation where the *first* leading character must always equal `0`.
   - **Segment 4:** A 5-digit random numeric routing tail block.

---

## 🚀 Quick Deployment

Because this project uses entirely zero-dependency frontend code, you can easily host it for free using **GitHub Pages**:

1. Create a new public repository on your GitHub profile.
2. Commit your `index.html` and this `README.md` to the root folder.
3. On your repository page, go to **Settings** -> **Pages** (under the Code and automation sidebar).
4. Set the Build and Deployment source to **Deploy from a branch**.
5. Select your main branch (e.g., `main` or `master`), leave the folder as `/root`, and hit **Save**.
6. GitHub will provide you with a live URL within a couple of minutes!

---
*Disclaimer: This repository is intended strictly for historical archive investigation, emulation environments, software preservation, and educational computer logic studies.*
