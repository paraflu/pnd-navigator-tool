# PND Navigator Patcher

🔧 Automated patch tool for Renault GPS navigators running PNDNavigator software.

[![Live Demo](https://img.shields.io/badge/demo-live-success)](https://paraflu.github.io/pnd-navigator-tool/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

## Overview

This web-based tool automatically applies a binary patch to PNDNavigator files used in Renault vehicle navigation systems. The patch modifies a specific byte at offset `0x00402920`, changing `0xD6` to `0xB9`.

## Features

- 🎯 **Simple & Fast**: Drag and drop your ZIP file
- 🔒 **Client-Side Processing**: All operations performed locally in your browser
- 📦 **ZIP Support**: Handles compressed archives automatically
- ✅ **Validation**: Verifies byte values before patching
- 💾 **One-Click Download**: Get your patched file immediately

## Usage

1. Visit [paraflu.github.io/pnd-navigator-tool](https://paraflu.github.io/pnd-navigator-tool/)
2. Upload your PNDNavigator ZIP archive (drag & drop or click to select)
3. The tool will automatically:
   - Extract the archive
   - Locate the PNDNavigator file
   - Apply the patch at offset `0x2920`
   - Repackage the modified file
4. Download the patched ZIP
5. Copy the patched file to the root of your SD card
6. Insert the SD card into your Renault GPS navigator

## Technical Details

**Patch Specification:**
- **Target File**: PNDNavigator (executable)
- **Offset**: `0x00002920` (decimal: 10528)
- **Original Byte**: `0xD6` (214)
- **Patched Byte**: `0xB9` (185)

**Technology Stack:**
- Vanilla JavaScript (ES6+)
- [JSZip](https://stuk.github.io/jszip/) for ZIP handling
- Client-side only (no server uploads)

## Compatibility

This patch is designed for specific Renault GPS navigation systems. Verify compatibility with your device before applying.

## Disclaimer

⚠️ **Use at your own risk.** This tool modifies executable files. Always:
- Keep a backup of your original file
- Verify your device model compatibility
- Understand that modifications may void warranties

## Development

### Local Testing

Simply open `index.html` in a modern web browser. No build process required.

### Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT License - See LICENSE file for details

## Credits

Developed by [paraflu](https://github.com/paraflu)

---

**Live Tool**: [paraflu.github.io/pnd-navigator-tool](https://paraflu.github.io/pnd-navigator-tool/)