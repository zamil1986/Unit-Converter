<div align="center">

# Unit Converter

A simple browser-based application for converting units of length, weight, and temperature.

Built with HTML, JavaScript, and Bootstrap.

</div>

## Overview

Unit Converter is a static web application that allows users to convert values between different measurement units.

The application provides separate pages for length, weight, and temperature conversions. All calculations are performed directly in the browser using JavaScript, so the application does not require a backend server or database.

This project was created based on the [Unit Converter project idea from roadmap.sh](https://roadmap.sh/projects/unit-converter).

## Features

- Convert units of length
- Convert units of weight
- Convert temperature values
- Select source and destination units
- Display conversion results instantly
- Navigate between conversion categories
- Simple interface styled with Bootstrap
- Runs entirely in the browser
- Does not require a backend or database

## Tech Stack

- [HTML5](https://developer.mozilla.org/en-US/docs/Web/HTML) — structures the application pages
- [CSS3](https://developer.mozilla.org/en-US/docs/Web/CSS) — provides custom styling
- [Bootstrap 5](https://getbootstrap.com/) — provides layout and interface styling
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) — performs unit-conversion calculations

## Supported Conversions

### Length

The application supports conversions between:

- Millimeter
- Centimeter
- Meter
- Kilometer

Length values are first converted into meters as a base unit and then converted into the selected destination unit.

### Weight

The application supports conversions between:

- Gram
- Kilogram
- Ton

Weight values are first converted into grams as a base unit and then converted into the selected destination unit.

### Temperature

The application supports conversions between:

- Celsius
- Fahrenheit
- Kelvin
- Réaumur

Temperature conversion uses formulas instead of a fixed multiplication factor because each temperature scale may have a different starting point.

## How It Works

The conversion process follows three main steps:

1. The user enters a numeric value.
2. The user selects the source and destination units.
3. JavaScript converts the input into a base unit before converting it into the destination unit.

For example, a length conversion follows this flow:

```text
Input value → Convert to meters → Convert to destination unit
```

Using a base unit reduces duplicated conversion logic. Instead of creating a formula for every possible pair of units, each unit only needs:

- One conversion into the base unit
- One conversion from the base unit

## Conversion Formulas

### Length

The meter is used as the base unit.

| Unit | Conversion to meters |
|---|---|
| Millimeter | `value / 1000` |
| Centimeter | `value / 100` |
| Meter | `value` |
| Kilometer | `value × 1000` |

### Weight

The gram is used as the base unit.

| Unit | Conversion to grams |
|---|---|
| Gram | `value` |
| Kilogram | `value × 1000` |
| Ton | `value × 1,000,000` |

### Temperature

Celsius is used as the intermediate unit.

| Source unit | Conversion to Celsius |
|---|---|
| Celsius | `value` |
| Fahrenheit | `(value - 32) / 1.8` |
| Kelvin | `value - 273.15` |
| Réaumur | `value × 1.25` |

The Celsius value is then converted into the selected destination scale.

## Project Structure

```text
Unit-Converter/
├── length.html
├── weight.html
├── temp.html
├── bootstrap.min.css
├── bootstrap.bundle.min.js
└── README.md
```

### File Responsibilities

| File | Description |
|---|---|
| `length.html` | Contains the length-conversion interface and logic |
| `weight.html` | Contains the weight-conversion interface and logic |
| `temp.html` | Contains the temperature-conversion interface and logic |
| `bootstrap.min.css` | Provides Bootstrap styling |
| `bootstrap.bundle.min.js` | Provides Bootstrap JavaScript components |
| `README.md` | Contains the project documentation |

## Getting Started

### Prerequisites

You only need:

- A modern web browser
- Git, if you want to clone the repository
- A code editor such as Visual Studio Code, if you want to modify the project

No package manager or dependency installation is required.

### 1. Clone the Repository

```bash
git clone https://github.com/zamil1986/Unit-Converter.git
cd Unit-Converter
```

### 2. Open the Application

Open `length.html` directly in your browser.

You can also start a local development server using the Visual Studio Code **Live Server** extension.

### 3. Using Python as a Local Server

If Python is installed, run:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/length.html
```

On Windows, the command may be:

```bash
python -m http.server 8000
```

## How to Use

1. Open one of the converter pages.
2. Enter the value you want to convert.
3. Select the original unit in the **From** field.
4. Select the destination unit in the **Convert to** field.
5. Click the **Convert** button.
6. The converted value will appear in the result section.
7. Use the navigation menu to switch between conversion categories.

## Example Conversions

### Length

Convert `2.5 kilometers` into meters:

```text
2.5 km × 1000 = 2500 m
```

Result:

```text
2500 m
```

### Weight

Convert `5 kilograms` into grams:

```text
5 kg × 1000 = 5000 g
```

Result:

```text
5000 g
```

### Temperature

Convert `100 degrees Celsius` into Fahrenheit:

```text
°F = 32 + (°C × 1.8)
°F = 32 + (100 × 1.8)
°F = 212
```

Result:

```text
212 °F
```

## Development Concepts

This project demonstrates several fundamental web-development concepts:

- Creating forms with HTML
- Reading input values from the DOM
- Handling button-click events
- Using JavaScript functions
- Using `switch` statements
- Converting string input into numeric data
- Updating page content dynamically
- Separating conversion categories into multiple pages
- Using a base unit to simplify conversion logic
- Styling interfaces with Bootstrap utility classes

## Current Limitations

- The application does not display a dedicated validation message for empty input.
- Temperature results currently use a generic degree symbol instead of scale-specific labels.
- Conversion logic is embedded directly inside each HTML file.
- The navigation menu does not currently include a responsive toggle button.
- The application does not store conversion history.
- Decimal-result formatting is not configurable.
- Only metric length and weight units are currently supported.

## Roadmap

Possible future improvements include:

- [ ] Add validation for empty and invalid input
- [ ] Add scale-specific temperature labels such as `°C` and `°F`
- [ ] Add input and output swapping
- [ ] Add real-time conversion while the user types
- [ ] Add decimal-precision controls
- [ ] Add conversion history
- [ ] Add dark mode
- [ ] Add imperial units such as inches, feet, pounds, and miles
- [ ] Move JavaScript and CSS into separate files
- [ ] Combine all conversion categories into a single-page interface
- [ ] Improve mobile responsiveness
- [ ] Add automated tests for conversion functions

## Author

**Muhammad Zamil**

- GitHub: [@zamil1986](https://github.com/zamil1986)

## Acknowledgements

Project inspiration:

- [roadmap.sh Unit Converter Project](https://roadmap.sh/projects/unit-converter)

## License

No license has been added to this project yet.
