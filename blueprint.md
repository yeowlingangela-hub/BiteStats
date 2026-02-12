# BiteStats Web App Blueprint

## Overview

BiteStats is a modern, single-page web application designed to provide quick nutritional information (calories and protein) for food items. The user can type a food query into a search bar, and the app will fetch and display the data. The interface is designed to be visually appealing and responsive, featuring a glassmorphism design aesthetic.

## Implemented Features (v3.1)

### Core Functionality
- **Real-Time Data Search:** Integrates with the OpenFoodFacts API to fetch live nutritional data.
- **Fallback Data Source:** If the API returns no results, the app falls back to a local JavaScript object with data for common foods.
- **Portion Calculation:** Users can enter a portion size in grams to get accurate nutritional values for their serving.
- **Debounced Input:** The search automatically triggers after the user stops typing, creating a seamless experience.

### Accessibility & Theming
- **Multi-Language Support:** Users can switch between English, Mandarin, French, and Malay.
- **Day/Night Mode:** A toggle allows users to switch between a light and a dark theme, with the preference saved locally.
- **High-Contrast Text:** Text colors are theme-aware, using dark brown for the light theme and white for the dark theme to ensure readability.

### Visual Design
- **Glassmorphism UI:** Results are displayed on a translucent, blurred card.
- **Themed Backgrounds:** The app uses different background images for day and night modes.
- **Verified Source Badge:** A "✔ Verified" badge indicates when data is from the OpenFoodFacts API.

---

## **Current Plan: UI & Visual Refinement (v3.2)**

This update focuses on refining the user interface by increasing the visual weight of the most important data and enhancing the theme's aesthetic.

**Plan & Steps:**

1.  **Increase Nutrient Font Size:**
    *   Locate the CSS rule for the calorie and protein value display (`.nutrition-item .value`).
    *   Increase the `font-size` from `2.5rem` to `3.5rem` to make the numbers more prominent and easier to read at a glance.

2.  **Update Light Theme Background:**
    *   Find a new high-quality, darker rustic food-themed image from Pexels.
    *   Update the `--bg-image-light` CSS variable with the URL of the new image to refresh the app's look and feel.
