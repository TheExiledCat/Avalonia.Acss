# Avalonia.Acss - Avalonia CSS Library

ACSS is a lightweight and flexible CSS library designed specifically for styling Avalonia UI applications. It simplifies UI development by introducing CSS-inspired syntax and features tailored for Avalonia.
(this readme is a work in progress)
## Features

- **CSS Syntax**: Write styles using familiar CSS-like syntax.
- **Dynamic Styling**: Supports dynamic theming and responsive design.
- **Seamless Integration**: Works effortlessly with Avalonia UI's styling system.
- **Customizable**: Extend and override styles to fit your application's needs.

## Installation

1. Add ACSS to your project (project not on nuget yet):
   ```bash
   dotnet add package Avalonia.Acss 
   ```

2. Reference ACSS in your Avalonia project and start styling your UI.

## Getting Started

Create an `.acss` file and define your styles:

```css
button {
    background-color: #007acc;
    color: white;
    padding: 10px 20px;
    border-radius: 5px;
}

.textbox {
    border: 1px solid #ccc;
    padding: 5px;
    font-size: 14px;
}
```

Apply styles to your Avalonia controls:

```xml
<Button Class="button">Click Me</Button>
<TextBox Class="textbox" />
```

## Roadmap

- [ ] Advanced media queries for responsiveness.
- [ ] Built-in themes and style presets.
- [ ] Documentation and examples.

## Contributing

We welcome contributions of all kinds! Here's how you can help:

1. **Report Issues**: Found a bug or have a feature request? [Open an issue](https://github.com/TheExiledCat/Avalonia.Acss/issues).
2. **Submit Pull Requests**: Check the roadmap or issues and start coding! Be sure to follow the contribution guidelines.
3. **Spread the Word**: Share ACSS with your fellow developers to help improve Avalonia development.

## License

ACSS is licensed under the [MIT License](LICENSE).

---

Happy styling! ✨

