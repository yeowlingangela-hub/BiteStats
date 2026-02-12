# BiteStats Web App Blueprint

## Overview

BiteStats is a modern, single-page web application designed to provide quick nutritional information (calories and protein) for food items. The user can type a food query into a search bar, and the app will fetch and display the data. The interface is designed to be visually appealing and responsive, featuring a glassmorphism design aesthetic.

## Implemented Features (v1.0)

### Core Functionality
- **AI-Powered Nutrition Search:** Utilizes a mock AI service to estimate calories and protein from natural language queries (e.g., "2 large eggs").
- **Dynamic Results Display:** Fetches and displays nutritional information without a page reload.
- **Real-Time Feedback:** A "Searching..." pulse animation provides visual feedback to the user while data is being fetched.

### Visual Design
- **Glassmorphism UI:** The results are displayed on a translucent, blurred card that floats over the background.
- **Rustic & Fancier Theme:** A high-quality, rustic food-themed background image is used.
- **Custom Fonts & Colors:** Uses the 'Montserrat' font and a custom color palette for a unique, premium feel.
- **Improved Contrast:** Text and background colors have been chosen to ensure high readability.

---

## **Current Plan: Real-Time Data Overhaul (v2.0)**

This update replaces the mock data simulation with a robust, real-time data fetching strategy using the OpenFoodFacts API, with a fallback to a local data source for common items. It also introduces portion-based calculations and a verification indicator for data accuracy.

**Plan & Steps:**

1.  **Integrate OpenFoodFacts API:**
    *   Replace the mock fetch function with a live API call to `https://world.openfoodfacts.org/cgi/search.pl`.
    *   Parse the response to extract `energy-kcal_100g` (calories) and `proteins_100g`.

2.  **Implement Fallback Data Source:**
    *   Create a local JavaScript object containing USDA average nutritional data for the top 50 most common foods (e.g., apple, egg, chicken breast).
    *   If the OpenFoodFacts API returns no product, the app will search this local object for the query.

3.  **Enhance UI & UX:**
    *   **Portion Size Input:** Add a small number input field for "Portion Size (g)" next to the main search bar.
    *   **Verified Source Badge:** Add a "✔ Verified" badge that appears next to the results only when the data is successfully fetched from the OpenFoodFacts API.
    *   **Debounced Search:** Implement a debounce on the search input. The API fetch will trigger automatically after the user stops typing for 500ms, making the search feel instantaneous without overwhelming the API.

4.  **Implement Calculation Logic:**
    *   When a user enters a portion size, the app will calculate the nutritional values for that specific portion (`(value_100g / 100) * portion_size`).
    *   If the portion size input is empty, the app will display the default values per 100g.

5.  **Refactor JavaScript:**
    *   Create a new `handleSearch` function to orchestrate the fetching, fallback, calculation, and UI updates.
    *   Remove the old `submit` event listener and replace it with `input` listeners on the search and portion size fields, using the new debounce function.
    *   Update the UI to correctly display API data, fallback data, or a "not found" message.
