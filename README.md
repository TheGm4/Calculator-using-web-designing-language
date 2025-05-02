# Calculator-using-web-designing-language
Caculator
Android Calculator

Project Overview

The Android Calculator is a web-based application designed to emulate a versatile calculator with multiple modes, mimicking the functionality of a typical Android calculator app. Built using HTML, CSS, and JavaScript, it features a responsive user interface styled with Tailwind CSS and custom styles. The calculator supports basic arithmetic, temperature conversions, area calculations, and scientific functions, making it a comprehensive tool for various computational needs.

This project was developed to address specific requirements, including fixing runtime errors, ensuring production-ready CSS, and completing the codebase. The application is hosted in a single index.html file, with a dependency on a locally generated styles.css file for Tailwind CSS utilities.

Features

Calculator Modes





Basic Mode:





Supports standard arithmetic operations: addition (+), subtraction (-), multiplication (×), and division (÷).



Includes number buttons (0-9), decimal point, clear (C), undo, and equals (=).



Temperature Conversion Mode:





Converts between Celsius (C), Fahrenheit (F), and Kelvin (K).



Supports conversions like C to F, F to C, C to K, F to K, K to C, and K to F.



Includes number and decimal buttons for input.



Area Calculation Mode:





Calculates areas for shapes: square, rectangle, circle, triangle, parallelogram, and trapezoid.



Uses prompts for additional inputs (e.g., length for rectangle, height for triangle).



Includes number and decimal buttons.



Scientific Mode:





Provides advanced functions: sine (sin), cosine (cos), tangent (tan), logarithm (log), natural logarithm (ln), square root (√), power (x^y), square (x^2), 10^x, and factorial (n!).



Supports constants π and e.



Includes number, decimal, and parentheses buttons.

User Interface





Display: Shows the current input or result, styled with a dark background and large, readable text.



Mode Selector: A dropdown menu allows switching between Basic, Temperature, Area, and Scientific modes.



Buttons: Organized in a 4-column grid, with distinct colors for numbers, operators, functions, and clear/undo actions.



Responsive Design: Fixed width of 360px, centered on the page, with hover effects and smooth transitions.

Technical Details





HTML: Single index.html file containing structure, styles, and logic.



CSS: Combines Tailwind CSS (via styles.css) with custom styles for layout and button appearance.



JavaScript: Handles input processing, calculations, mode switching, and dropdown functionality.



Dependencies:





Math.js (CDN) for mathematical operations.



Google Fonts (Roboto) for typography.



Tailwind CSS (locally generated) for styling.

Installation

To run the Android Calculator locally or deploy it, follow these steps:

Prerequisites





Node.js: Required for generating Tailwind CSS. Download from nodejs.org.



Web Browser: Any modern browser (e.g., Chrome, Firefox) to view the application.



Text Editor: Recommended for editing code (e.g., VS Code).

Steps





Clone the Repository:

git clone <repository-url>
cd android-calculator

Replace <repository-url> with the GitHub repository URL.



Install Node.js Dependencies: Initialize a Node.js project and install Tailwind CSS:

npm init -y
npm install -D tailwindcss



Initialize Tailwind CSS: Create a tailwind.config.js file:

npx tailwindcss init

Update tailwind.config.js to include index.html:

/** @type {import('tailwindcss').Config} */
module.exports = {
  content: ["./index.html"],
  theme: {
    extend: {},
  },
  plugins: [],
}



Create Input CSS: Create a file named input.css with:

@tailwind base;
@tailwind components;
@tailwind utilities;



Generate styles.css: Run the Tailwind CLI to generate a minified styles.css:

npx tailwindcss -i ./input.css -o ./styles.css --minify

Ensure styles.css is in the same directory as index.html.



Run the Application: Open index.html in a web browser:





Double-click index.html to open it in your default browser, or



Use a local server (e.g., VS Code Live Server extension or npx http-server).

Usage





Open the Calculator: Load index.html in a browser. The calculator displays with the Basic mode active.



Select a Mode: Use the dropdown menu to switch between Basic, Temperature, Area, or Scientific modes. The button layout updates accordingly.



Perform Calculations:





Basic Mode: Enter numbers and operators (e.g., 5 + 3), then press = to see the result. Use C to clear or Undo to revert.



Temperature Mode: Enter a number (e.g., 25), select a conversion (e.g., C to F), and view the result.



Area Mode: Enter a base value, select a shape (e.g., Rectangle), provide additional inputs via prompts, and view the area.



Scientific Mode: Enter a number or expression (e.g., sin(30) or 5^2), select a function, and view the result.



Interact with the UI:





Click buttons or use the dropdown for input.



Use keyboard navigation (Enter, Space, Escape) for the dropdown.



Check the display for real-time input and results.

Fixes Applied

The project underwent several iterations to resolve errors and complete the codebase. Key fixes include:





Syntax Errors:





Issue: "Uncaught SyntaxError: Unexpected token ')'" due to mismatched parentheses.



Fix: Balanced all parentheses in functions like appendOperator, calculate, and calculateFactorial. Corrected typo appendOperatoroperator to appendOperator(operator).



Issue: Non-ASCII text ("ремонт") and stray words ("Indiana", "magy") in the script.



Fix: Removed invalid text to ensure clean JavaScript.



Tailwind CSS CDN Warning:





Issue: Warning that cdn.tailwindcss.com is not production-ready.



Fix: Replaced CDN with a locally generated styles.css using the Tailwind CLI, ensuring optimized and minified CSS.



Incomplete Code:





Issue: The calculateArea function was cut off in the latest submission.



Fix: Completed the function with full implementations for all shapes (square, rectangle, circle, triangle, parallelogram, trapezoid).



Number Button Consistency:





Issue: Earlier versions lacked number buttons in Temperature, Area, and Scientific modes.



Fix: Added number (0-9) and decimal buttons to all modes for consistent input.



Runtime Stability:





Issue: Potential errors in calculate due to invalid expressions.



Fix: Added checks to prevent evaluation of incomplete expressions (e.g., ending with an operator).

Testing

To ensure the calculator works as expected, perform the following tests:





Basic Mode:





Input: 5 + 3 =



Expected Output: 8



Test C (clears to 0) and Undo (reverts last input).



Temperature Mode:





Input: 25, click C to F



Expected Output: 77



Verify all conversions (e.g., 0 C to K → 273.15).



Area Mode:





Input: 5, select Square



Expected Output: 25



Test Rectangle with length 4 → 20.



Test Circle with radius 3 → approximately 28.274.



Scientific Mode:





Input: 30, click sin



Expected Output: 0.5



Test 5^2 → 25, log(100) → 2, 5! → 120.



UI and Navigation:





Switch between modes using the dropdown.



Verify button visibility updates correctly.



Test dropdown keyboard navigation (Enter to open, Escape to close).



Error Handling:





Input invalid data (e.g., letters) in Area mode prompts → displays Error.



Test incomplete expressions (e.g., 5 +) → no crash, stays unchanged.

Use browser Developer Tools (F12 > Console) to check for errors during testing.

Future Improvements





Input Validation: Enhance validation to prevent invalid inputs without relying on prompts.



History Log: Add a display for calculation history beyond the Undo feature.



Mobile Optimization: Adjust the layout for smaller screens using responsive Tailwind classes.



Unit Tests: Implement JavaScript unit tests with a framework like Jest to automate testing.



Offline Support: Add a Service Worker for offline functionality as a Progressive Web App (PWA).



Custom Themes: Allow users to switch between light and dark themes.
