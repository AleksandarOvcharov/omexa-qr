# Omexa QR Code Generator

A lightweight JavaScript library that automatically converts custom `<qr>` tags into scannable SVG QR codes. Perfect for adding QR codes to any web page with minimal setup.

## 🌟 Features

- **Self-closing tags**: Use `<qr link="url" size="128">` (no closing tag needed)
- **Automatic size validation**: Minimum 128px, auto-adjusts smaller sizes
- **SVG output**: Crisp, scalable QR codes that work everywhere
- **Scannable**: Uses proven QR code generation library
- **Single file**: Only one file to include - super simple!
- **Debug friendly**: Console logging with emoji indicators
- **Error handling**: Clear error messages for invalid inputs

## 🚀 Quick Start

```html
<!DOCTYPE html>
<html>
<head>
    <script src="omexaqr.min.js"></script>
</head>
<body>
    <qr link="https://www.google.com" size="200"></qr>
    <qr link="https://github.com"></qr>
</body>
</html>
```

## 📖 Usage

### Basic Syntax
```html
<qr link="URL" size="SIZE"></qr>
```

### Examples
```html
<!-- Basic QR code -->
<qr link="https://www.google.com" size="128"></qr>

<!-- Large QR code -->
<qr link="https://github.com" size="200"></qr>

<!-- Default size (128px) -->
<qr link="https://stackoverflow.com"></qr>

<!-- Size below minimum gets auto-adjusted to 128px -->
<qr link="https://www.youtube.com" size="50"></qr>
```

## 🎛️ Attributes

| Attribute | Required | Description | Default |
|-----------|----------|-------------|---------|
| `link` | ✅ Yes | URL to encode in QR code | - |
| `size` | ❌ No | Size in pixels (minimum 128) | 128 |

## 📁 Files

- **`omexaqr.min.js`** - ⭐ Main library file (includes everything)
- `test.html` - Test page with examples
- `assignment.md` - Project requirements
- `README.md` - This documentation
- `PROJECT_SUMMARY.md` - Development summary

## 🔧 Programmatic API

The library exposes a global `OmexaQR` object:

```javascript
// Generate QR code manually
const svgString = OmexaQR.generate('https://example.com', 200);

// Process QR tags manually
OmexaQR.process();

// Check version
console.log(OmexaQR.version); // "2.0.0"
```

## 🐛 Debug Information

Open browser Developer Tools (F12) to see processing information:
- 🔍 Found X QR tags to process
- 📱 Processing QR tag details
- ✅ Success messages
- ❌ Error messages

## 📋 Size Validation

- Minimum size: 128px
- If size < 128: automatically adjusted to 128px
- No size specified: defaults to 128px
- Maximum size: No limit (but consider performance)

## 🔍 Error Handling

The library handles various error cases:

### Missing Link Attribute
```html
<qr size="128"></qr>
<!-- Results in: Error: Missing link attribute -->
```

### Invalid URLs
Invalid URLs are passed through to the QR library which handles encoding properly.

## 🎨 Styling

QR codes are automatically styled with:
```css
display: block;
margin: 10px 0;
```

You can override with CSS:
```css
svg[viewBox] {
    border: 2px solid #333;
    border-radius: 8px;
}
```

## 🌐 Browser Support

- Modern browsers with ES6 support
- SVG support required
- Works with any HTML page

## 📦 What's Included

The single `omexaqr.min.js` file includes:
- qrcode-svg library by datalog (MIT License)
- Omexa QR wrapper with error handling
- All features in one convenient package

## 📄 License

MIT License - Feel free to use in any project!

## 🤝 Contributing

1. Test your changes with `test.html`
2. Ensure QR codes are scannable
3. Update documentation if needed
4. Submit pull requests

## 📞 Support

If QR codes are not scannable:
1. Check the console for error messages
2. Verify the URL is valid
3. Try with a different QR scanner app
4. Test with the included `test.html` file 