# JSON Converter Tool 🔄

A comprehensive, free online tool for converting various data formats to JSON. Built with vanilla JavaScript and designed for developers who need quick, reliable data format conversion.

## ✨ Features

### Supported Input Formats
- **Ruby Hash** → JSON (with symbol support)
- **JavaScript Object** → JSON
- **CSV** → JSON (array of objects)
- **Query String** → JSON object
- **INI File** → JSON object
- **JSON** → Prettified JSON

### Advanced Capabilities
- 🎯 **Smart Auto-detection** - Automatically identifies input format
- 🔧 **Custom Converters** - Write JavaScript functions for specialized processing
- 💾 **Download/Upload** - Save and share custom converters as files
- 🔒 **Sandboxed Execution** - Safe processing of custom code with Web Workers
- 📱 **Responsive Design** - Works on desktop and mobile devices
- ⚡ **No Backend Required** - Pure client-side processing

## 🚀 Quick Start

### Option 1: Direct Use
1. Open `index.html` in any modern web browser
2. Paste your data in the input textarea
3. Select the input type or use auto-detection
4. Click "➡️ To JSON" to convert

### Option 2: Host Locally
```bash
# Clone or download the files
# Serve with any HTTP server (required for Web Workers)
python -m http.server 8000
# Or
npx serve .
```

## 📋 Usage Examples

### Ruby Hash to JSON
```ruby
# Input
{ :user => { :name => "Alice", :roles => [:admin, :editor] }, :active => true }

# Output
{
  "user": {
    "name": "Alice",
    "roles": ["admin", "editor"]
  },
  "active": true
}
```

### CSV to JSON
```csv
# Input
name,age,city
Alice,25,New York
Bob,30,San Francisco

# Output
[
  {"name": "Alice", "age": "25", "city": "New York"},
  {"name": "Bob", "age": "30", "city": "San Francisco"}
]
```

### Query String to JSON
```
# Input
name=Alice&age=25&skills=js&skills=python

# Output
{
  "name": "Alice",
  "age": "25",
  "skills": ["js", "python"]
}
```

## 🛠 Custom Converters

Write JavaScript functions to handle specialized data processing:

```javascript
// Example: Convert pipe-separated values
function convert(input) {
  const lines = input.trim().split('\n');
  return lines.map(line => {
    const [name, email, role] = line.split('|');
    return { name: name.trim(), email: email.trim(), role: role.trim() };
  });
}
```

### Custom Converter Features
- **Sandboxed execution** with Web Workers
- **Timeout protection** (1.5 seconds max)
- **Security filtering** blocks dangerous APIs
- **Save/Load functionality** with localStorage
- **File import/export** for sharing converters

## 🔧 Technical Details

### Ruby Hash Preprocessing
The tool handles complex Ruby syntax through intelligent preprocessing:
- Converts `:symbol =>` to `"symbol":`
- Handles symbol arrays: `[:a, :b]` → `["a", "b"]`
- Converts `nil` to `null`
- Processes nested structures recursively

### Security Measures
Custom converters are sandboxed and filtered for:
- Network access (`fetch`, `XMLHttpRequest`)
- DOM manipulation (`document`, `window`)
- Storage access (`localStorage`, `sessionStorage`)
- Code evaluation (`eval`, `Function`)
- Other potentially dangerous APIs

### Browser Compatibility
- **Modern browsers** with ES6+ support
- **Web Workers** required for custom converters
- **File API** for download/upload functionality
- **URLSearchParams** for query string parsing


## 🎯 Use Cases

### Development & APIs
- Converting Ruby application data for REST APIs
- Processing configuration files for web apps
- Transforming CSV exports for JavaScript consumption
- Validating and formatting JSON responses

### Data Processing
- Converting legacy data formats to modern JSON
- Processing form submissions and URL parameters
- Transforming structured logs to JSON for analysis
- Converting between different configuration formats

### Educational & Testing
- Learning JSON structure and syntax
- Testing data transformations
- Prototyping data processors
- Demonstrating format conversions

## ⚠️ Limitations

- **Ruby preprocessing** is heuristic-based and may need manual adjustment for very complex structures
- **Functions and classes** cannot be represented in JSON
- **Custom converters** have a 3.5KB size limit and 1.5-second timeout
- **Security** is good but not perfect - only run trusted custom code

## 🤝 Contributing

### Reporting Issues
- Use clear, descriptive titles
- Include input data that causes problems
- Specify browser and version
- Describe expected vs actual behavior

### Feature Requests
- Explain the use case
- Provide example input/output
- Consider if it fits the tool's scope

### Code Contributions
- Keep it vanilla JavaScript (no frameworks)
- Maintain compatibility with modern browsers
- Follow existing code style
- Test across different browsers

## 📄 License

This project is released under the MIT License. Feel free to use, modify, and distribute.

## 🔗 SEO Keywords

This tool is optimized for searches including:
- Ruby hash to JSON converter
- JavaScript object to JSON
- CSV to JSON converter
- JSON formatter and validator
- Query string to JSON
- INI to JSON converter
- Online data converter
- Free JSON conversion tool

## 🌟 Star this Repository

If this tool helped you, please consider starring the repository to help others discover it!

---

**Built with ❤️ for developers who need quick, reliable data conversion.**
