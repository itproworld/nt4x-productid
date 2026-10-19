# MOD7 Key Generator v2.0

<p align="center">
  <img src="https://img.shields.io/badge/version-2.0-blue" alt="Version">
  <img src="https://img.shields.io/badge/license-MIT-green" alt="License">
  <img src="https://img.shields.io/badge/platform-web-brightgreen" alt="Platform">
</p>

A web-based tool for generating and validating Microsoft-style product keys using the classic **MOD7 algorithm** from the Windows 95/98 era. Built with a Windows 98-inspired aesthetic.

> ⚠️ **Educational Purposes Only** - Generated keys follow the MOD7 checksum algorithm but should not be used for software activation without proper licensing.

## Table of Contents

- [Features](#features)
- [Supported Key Types](#supported-key-types)
- [How MOD7 Works](#how-mod7-works)
- [Usage](#usage)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Credits](#credits)
- [License](#license)

## Features

- ✅ **Generate single keys** - Create valid MOD7-compliant keys on demand
- ✅ **Validate existing keys** - Check if any key follows the algorithm correctly
- ✅ **Batch generation** - Generate up to 1,000 keys at once
- ✅ **Export functionality** - Download keys as text files
- ✅ **Copy to clipboard** - One-click copy for single or batch keys
- ✅ **Windows 98 theme** - Nostalgic retro UI styling
- ✅ **Zero dependencies** - Pure HTML/CSS/JavaScript, works offline
- ✅ **Fully responsive** - Works on desktop and mobile devices

## Supported Key Types

| Key Type | Format | Description |
|----------|--------|-------------|
| **CD/Retail** | `XXX-XXXXXXX` | Standard retail product keys |
| **OEM** | `DDDYY-OEM-0XXXXXX-XXXXX` | Computer manufacturer bundled keys |
| **Office 97/NT4** | `XXXX-XXXXXXX` | Office 97 and Windows NT 4 keys |

## How MOD7 Works

The MOD7 algorithm was Microsoft's product key validation system in the 1990s. The core principle is simple:

> **The digit sum of certain key segments must be divisible by 7.**

### Validation Rules by Key Type

#### CD/Retail Keys
- First segment (site number): Cannot be repeated digits (333, 444, ..., 999)
- Second segment: Digit sum divisible by 7
- Last digit of second segment: Cannot be 0, 8, or 9

#### OEM Keys
- First segment (DDDYY): Day of year (001-366) + Year (95-03)
- Second segment: Must be "OEM"
- Third segment: Must start with 0, digit sum divisible by 7, last digit not 0/8/9
- Fourth segment: Random 5 digits

#### Office 97/NT4 Keys
- First segment: Last digit = 3rd digit + 1 or +2 (overflow wraps to 0/1)
- Second segment: Digit sum divisible by 7

### Why It's Weak

Microsoft acknowledged this was designed to stop "basic software pirates," not determined attackers. The all-zeroes bug (`0 % 7 == 0`) meant keys like `000-0000000` passed validation in early implementations.

From Windows XP onwards, Microsoft moved to server-side activation, making offline key validation obsolete.

## Usage

### Online Version

Simply open [`index.html`](index.html) in any modern web browser. No installation required.

### Local Development

# Clone the repository
git clone https://github.com/yourusername/mod7-key-generator.git

# Navigate to project directory
cd mod7-key-generator

# Open index.html in your browser
open index.html        # macOS
start index.html       # Windows
xdg-open index.html    # Linux

Browser Support
Chrome 60+
Firefox 55+
Safari 11+
Edge 79+
Opera 47+
Works on mobile browsers (iOS Safari, Chrome Mobile).

Installation
Deploy to GitHub Pages
Fork this repository
Go to Settings → Pages
Select main branch as source
Wait ~60 seconds for deployment
Visit https://yourusername.github.io/mod7-key-generator/
Deploy to Any Static Hosting
Since this is pure HTML/CSS/JavaScript, you can deploy anywhere:

Netlify (drag-and-drop)
Vercel
Surge
Firebase Hosting
Any web server
No build process or configuration needed.

Project Structure
mod7-key-generator/
├── index.html          # Main application
├── README.md           # This file
└── LICENSE             # MIT license

Code Organization
The JavaScript implements three core generators matching the tutorial specifications:

// Core utilities
sumOfDigits(num)      // Sum all digits in a number
padLeft(str, length)  // Left-pad with zeros
randomInt(min, max)   // Random integer

// Key generators
generateRetailKey()   // XXX-XXXXXXX format
generateOEMKey()      // DDDYY-OEM-0XXXXXX-XXXXX format
generateOffice97Key() // XXXX-XXXXXXX format

// Validators
validateRetailKey(key)
validateOEMKey(key)
validateOffice97Key(key)

Screenshots
<div align="center"> <img src="assets/screenshot-main-window.png" alt="Main Window" width="600"/> </div>
The main window showing all three functional sections: Generate, Validate, and Batch.

<div align="center"> <img src="assets/screenshot-validation.png" alt="Validation" width="600"/> </div>
Key validation with detailed feedback on what failed or succeeded.

Credits
Algorithm Reference: Daniel Gurney's MOD7 Tutorial
Community Contributions: 86Box community members who identified bugs in the original algorithm documentation
Visual Design: Windows 98 classic UI elements
Contributing
Contributions are welcome! Feel free to submit issues or pull requests:

Bug fixes
New key type support
UI improvements
Accessibility enhancements
Please ensure your code maintains the zero-dependency philosophy.

Disclaimer
This tool is for EDUCATIONAL PURPOSES ONLY.

Generated keys are mathematically valid according to the MOD7 checksum algorithm but:

They are not licensed for software activation
Using them to bypass paid software licenses may violate laws in your jurisdiction
Modern software uses server-side activation that this tool cannot replicate
This tool should not be used to facilitate copyright infringement
The purpose of this project is to demonstrate:

Historical cryptography/checksum algorithms
Web development techniques
Retro computing preservation
Related Projects
86Box - PC emulator preserving the 1995-2004 era
Windows 95 OSR2 - Internet Archive preservation
Product Key Explorer - Legitimate key recovery tools
License
MIT License - See LICENSE for full text

Free to use, modify, and distribute. Attribution appreciated but not required.

Built with ❤️ for the retro computing community
