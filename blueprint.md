# BiteStats Web App Blueprint

## Overview

BiteStats is a modern, single-page web application designed to provide quick nutritional information (calories and protein) for food items. The user can type a food query into a search bar, and the app will fetch and display the data. The interface is designed to be visually appealing and responsive, featuring a glassmorphism design aesthetic.

## Implemented Features (v2.0)

### Core Functionality
- **Real-Time Data Search:** Integrates with the OpenFoodFacts API to fetch live nutritional data.
- **Fallback Data Source:** If the API returns no results, the app falls back to a local JavaScript object with data for common foods.
- **Portion Calculation:** Users can enter a portion size in grams to get accurate nutritional values for their serving.
- **Debounced Input:** The search automatically triggers after the user stops typing, creating a seamless experience.

### Visual Design
- **Glassmorphism UI:** Results are displayed on a translucent, blurred card.
- **Rustic & Fancier Theme:** A high-quality, rustic food-themed background image is used.
- **Custom Fonts & Colors:** Uses the 'Montserrat' font and a custom color palette for a unique, premium feel.
- **Verified Source Badge:** A "✔ Verified" badge indicates when data is from the OpenFoodFacts API.

---

## **Current Plan: Accessibility & Theming (v3.0)**

This update focuses on improving accessibility and user customization by adding multi-language support and a day/night theme toggle.

**Plan & Steps:**

1.  **Implement Language Switching:**
    *   Add a dropdown menu to the UI allowing users to select from English (en), Mandarin (zh), French (fr), and Malay (ms).
    *   Create a `translations` object in the JavaScript to store all UI string translations for each language.
    *   Use `data-key` attributes on HTML elements to identify and map them to the translation object.
    *   Write a `setLanguage` function to dynamically update all UI text based on the selected language.
    *   Store the user's language preference in `localStorage` to persist the choice across sessions.

2.  **Implement Day/Night Mode Toggle:**
    *   Add a toggle switch or button to the UI to allow users to switch between a light (day) and dark (night) theme.
    *   Refactor the CSS to use CSS variables for all colors, fonts, and background images.
    *   Define two themes: a default light theme and a `.dark-mode` class that overrides the CSS variables for the dark theme.
    *   Write a `toggleTheme` function in JavaScript to add or remove the `.dark-mode` class from the `<body>`.
    *   Store the user's theme preference in `localStorage` to persist the choice.

3.  **Refactor HTML & CSS:**
    *   Add the new UI elements for the language selector and theme toggle.
    *   Restructure the CSS to be theme-ready by replacing static values with `var()` functions.

4.  **Refactor JavaScript:**
    *   Implement the logic for language and theme switching, including event listeners and `localStorage` handling.
    *   Ensure the dynamic text (like search results) is correctly integrated with the new translation system.
