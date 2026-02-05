# Blueprint: DevOps PoC Flutter App

## Overview

This document outlines the project structure, features, and development plan for the "DevOps PoC" Flutter application. The goal is to create a visually appealing and functional application that demonstrates best practices in Flutter development and CI/CD.

## Initial State & Features (Version 1.0)

*   **Project:** A new Flutter project named "myapp".
*   **Platform Support:** Configured for Android, iOS, Linux, macOS, and Windows.
*   **CI/CD:** A GitHub Actions workflow (`.github/workflows/release.yml`) is set up to automatically build and release Android and Windows executables when a new version tag (e.g., `v1.0`) is pushed.
*   **Core Functionality:**
    *   A single screen app.
    *   A text input field for users to enter a "Punto" (Point).
    *   A "Registrar" (Register) button to add the text to a list.
    *   A list view that displays the registered items.
*   **Dependencies:**
    *   `flutter/material.dart`

## Current Plan: UI and Architecture Refactoring

**Goal:** To modernize the application's UI, implement a robust theme system, and improve the overall architecture based on the established AI Development Guidelines.

**Steps:**

1.  **Add Dependencies:**
    *   `google_fonts`: For improved and consistent typography.
    *   `provider`: For state management, specifically for managing the application's theme.

2.  **Implement Theming (Material 3):**
    *   Create a `ThemeProvider` class to manage light, dark, and system theme modes.
    *   Define `ThemeData` for both light and dark modes using `ColorScheme.fromSeed` for a modern Material 3 look.
    *   Integrate custom fonts from `google_fonts` into the text theme.
    *   Style core components like `AppBar` and `ElevatedButton` within the theme for consistency.

3.  **Refactor `lib/main.dart`:**
    *   Wrap the main application widget with `ChangeNotifierProvider` to make the `ThemeProvider` available throughout the widget tree.
    *   Rebuild the main screen (`MyHomePage`) with a more visually appealing layout.
    *   Add an `IconButton` to the `AppBar` to allow users to toggle between light and dark themes.
    *   Improve the list presentation using `Card` widgets to give each item a modern, "lifted" appearance.
    *   Enhance overall UI with better spacing and layout management.
