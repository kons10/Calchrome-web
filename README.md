# ChromiumOS Calculator

A scientific calculator application for Chrome OS, originally developed by Google and maintained/fixed by Alex313031.

## Features

- **Scientific Calculations**: Support for trigonometric functions (sin, cos, tan), logarithms, exponents, and more
- **Memory Functions**: Store and recall values from memory
- **Angle Modes**: Switch between degrees and radians
- **History**: View recent calculations
- **Multi-language Support**: Available in 54 languages

## Supported Languages

This extension supports the following languages:

| Code | Language | Code | Language |
|------|----------|------|----------|
| am | Amharic | it | Italian |
| ar | Arabic | ja | Japanese |
| bg | Bulgarian | kn | Kannada |
| bn | Bengali | ko | Korean |
| ca | Catalan | lt | Lithuanian |
| cs | Czech | lv | Latvian |
| da | Danish | ml | Malayalam |
| de | German | mr | Marathi |
| el | Greek | ms | Malay |
| en | English | nl | Dutch |
| en_GB | English (UK) | no | Norwegian |
| es | Spanish | pl | Polish |
| es_419 | Spanish (Latin America) | pt_BR | Portuguese (Brazil) |
| et | Estonian | pt_PT | Portuguese (Portugal) |
| fa | Persian | ro | Romanian |
| fi | Finnish | ru | Russian |
| fil | Filipino | sk | Slovak |
| fr | French | sl | Slovenian |
| gu | Gujarati | sr | Serbian |
| hi | Hindi | sv | Swedish |
| hr | Croatian | sw | Swahili |
| hu | Hungarian | ta | Tamil |
| id | Indonesian | te | Telugu |
| iw | Hebrew | th | Thai |
| tr | Turkish | uk | Ukrainian |
| vi | Vietnamese | zh_CN | Chinese (Simplified) |
| zh_TW | Chinese (Traditional) | | |

## Installation

### Loading as Unpacked Extension (Development)

1. Open Chrome and navigate to `chrome://extensions/`
2. Enable "Developer mode" using the toggle in the top right corner
3. Click "Load unpacked"
4. Select the directory containing this calculator extension
5. The calculator should now appear in your extensions list

### Installing as a Chrome App

1. Navigate to `chrome://apps/` in your browser
2. Find the Calculator app and click to launch

## Usage

### Basic Operations
- Click number buttons to input values
- Use `+`, `-`, `×`, `÷` for basic arithmetic
- Press `=` to calculate the result
- Press `AC` to clear all input
- Press `⌫` to delete the last character

### Scientific Functions
- **Trigonometry**: sin, cos, tan and their inverses (asin, acos, atan)
- **Logarithms**: log (base 10), ln (natural log)
- **Exponents**: x² (square), yⁿ (power), eⁿ (exponential)
- **Roots**: √ (square root), ⁿ√Y (nth root)
- **Constants**: π (pi), e (Euler's number)
- **Other**: x! (factorial), 1/x (inverse), mod (modulo), % (percentage)

### Memory Functions
- `a=` : Store current value in memory
- `a` : Recall value from memory

### Angle Mode
- `Deg` : Switch to degree mode
- `Rad` : Switch to radian mode

## File Structure

```
calculator/
├── _locales/           # Internationalization files (54 languages)
│   ├── en/
│   │   └── messages.json
│   ├── ja/
│   │   └── messages.json
│   └── ... (other languages)
├── icons/              # Application icons
│   ├── ic_calculator_32.png
│   ├── ic_calculator_48.png
│   ├── ic_calculator_64.png
│   ├── ic_calculator_96.png
│   ├── ic_calculator_128.png
│   └── ic_calculator_256.png
├── bg.js               # Background script for app launching
├── foam.js             # Main application logic
├── index.html          # Main HTML file
└── manifest.json       # Chrome extension manifest
```

## Technical Details

- **Manifest Version**: 3
- **Minimum Chrome Version**: 88
- **Permissions**:
  - `clipboardRead`: Read from clipboard
  - `clipboardWrite`: Write to clipboard
  - `contextMenus`: Add context menu items

## Internationalization (i18n)

This extension uses Chrome's i18n system for multi-language support. All user-visible strings are stored in `_locales/*/messages.json` files.

### Adding a New Language

1. Create a new directory under `_locales/` with the appropriate language code (e.g., `_locales/fr/` for French)
2. Copy `messages.json` from an existing locale
3. Translate all message values while keeping the keys unchanged
4. Update this README to include the new language

### Message Format

```json
{
  "MessageKey": {
    "description": "Description of what this message is used for",
    "message": "Translated text here",
    "placeholders": {
      "placeholder_name": {
        "content": "$1"
      }
    }
  }
}
```

## Development

### Modifying the Calculator

The main calculator logic is contained in `foam.js`. To make changes:

1. Edit `foam.js` with your preferred code editor
2. Reload the extension at `chrome://extensions/`
3. Test your changes

### Updating Translations

When adding new UI elements:

1. Add the new message key to `_locales/en/messages.json` (the source language)
2. Add corresponding entries to all other locale files
3. Reference the message in your code using `chrome.i18n.getMessage('MessageKey')`

## Troubleshooting

### Calculator doesn't launch
- Make sure the extension is enabled in `chrome://extensions/`
- Try reloading the extension
- Check the browser console for errors

### Display issues
- Try resizing the calculator window
- Clear browser cache and reload the extension

### Localization not working
- Ensure your Chrome browser language matches one of the supported locales
- Check that the `_locales` folder structure is correct

## Credits

- **Original Developer**: Google (ChromiumOS team)
- **Maintainer**: Alex313031

## License

This project is part of the ChromiumOS ecosystem. See the Chromium project license for details.

## Contributing

Contributions are welcome! Please feel free to submit issues and pull requests.

---

For more information about Chrome extensions, visit the [Chrome Developer Documentation](https://developer.chrome.com/docs/extensions/).
