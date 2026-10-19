# MOD7 Key Generator

A web-based tool for generating and validating Microsoft-style product keys using the MOD7 algorithm.

## Features

- ✅ Generate single MOD7-compliant keys
- ✅ Validate existing keys
- ✅ Batch key generation (1-1000 keys)
- ✅ Multiple key types supported (CD, OEM, Office 97)
- ✅ Copy to clipboard
- ✅ Export to file

## Supported Key Types

| Type | Format | Description |
|------|--------|-------------|
| CD Key | 3-7 digits | Standard retail keys |
| OEM Key | Date-OEM-Mfg-MOD7 | Bundled computer keys |
| Office 97 | 4-7 digits | Office 97 specific format |

## How MOD7 Works

The MOD7 algorithm requires that the digit sum of the key's numeric segment be divisible by 7.

## Usage

1. Open `index.html` in any modern browser
2. Select key type and click "Generate"
3. For batch generation, specify quantity and export options

## Technologies Used

- Pure HTML/CSS/JavaScript (no dependencies)
- Responsive design
- Zero backend required

## Disclaimer

This tool is for **educational purposes only**. Generated keys are mathematically valid according to the MOD7 algorithm but should not be used for software activation.

## Resources

- [Original Tutorial](https://gurney.dev/posts/mod7/)
- [License](LICENSE)
