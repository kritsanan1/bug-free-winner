# AI Development Rules

This document outlines the tech stack and provides clear rules for AI-driven development of this application. Following these guidelines ensures consistency, maintainability, and leverages the strengths of our chosen libraries.

## Tech Stack

This is a React Native application built with the following technologies:

-   **Framework:** [React Native](https://reactnative.dev/) with [Expo](https://expo.dev/) for a streamlined development experience.
-   **Routing:** [Expo Router](https://expo.dev/router) for file-based routing on native and web.
-   **Authentication:** [Clerk](https://clerk.com/) for complete user management, including sign-in, sign-up, and social connections.
-   **Styling:** [Tailwind CSS](https://tailwindcss.com/) via [NativeWind](https://www.nativewind.dev/) for a utility-first styling approach.
-   **Language:** [TypeScript](https://www.typescriptlang.org/) for static typing and improved code quality.
-   **UI Components:** A custom UI library based on [React Native Reusables](https://reactnativereusables.com) and shadcn/ui principles, located in `src/components/ui`.
-   **Icons:** [Lucide React Native](https://lucide.dev/) for a consistent and beautiful icon set.

## Library Usage Rules

To maintain a clean and predictable codebase, please adhere to the following rules:

-   **Navigation:** All routing, navigation, and linking between screens **must** be handled by **Expo Router**. Do not install or use any other navigation library like React Navigation directly.

-   **Authentication:** All user authentication features (sign-in, sign-up, session management, user profiles) **must** be implemented using the **Clerk** SDK (`@clerk/clerk-expo`).

-   **Styling:** All components **must** be styled using **Tailwind CSS** classes via NativeWind. Avoid using `StyleSheet.create` or inline styles.

-   **UI Components:** Whenever possible, **use the pre-built components** from the `@/components/ui` directory (e.g., `<Button>`, `<Input>`, `<Card>`). Only create new components if the existing ones do not meet the requirements.

-   **Icons:** All icons **must** be rendered using the custom `<Icon />` component from `@/components/ui/icon.tsx`, which wraps icons from `lucide-react-native`. This ensures consistent styling and sizing.

-   **State Management:** For local component state, use React's built-in hooks (`useState`, `useReducer`). For global state, use `useContext` for simple cases. If a more robust solution is needed, we will evaluate adding a dedicated state management library.

-   **Code Formatting:** All code **must** be formatted according to the project's Prettier configuration.