# News Feed

A lightweight news aggregator built as a learning project. The primary goal is to apply and master modern Angular (v17+) features in a practical way.

> **Note:** This is a learning project focused on mastering new Angular concepts, not a production-ready application.

## 🚀 App Features

* Fetches and displays the latest news articles from a public API.
* Live search filtering based on user input.
* Sort articles (e.g., by newest or oldest).
* Save and manage a list of "favorite" articles.
* Favorites are persisted in the browser's `localStorage`.
* Smooth page transitions when navigating to article details.

## 🛠️ Angular Concepts Practiced

This project was built to specifically practice and demonstrate the following modern Angular features:

* **Signals:** Used for all state management.
    * `signal()`: For basic state (search term, sort order, API token).
    * `computed()`: For reactively deriving the filtered and sorted article list.
    * `effect()`: For side effects, such as saving the favorites list to `localStorage` whenever it changes.
* **Built-in Control Flow:** Replaces `*ngIf`, `*ngFor`, and `*ngSwitch`.
    * `@if` and `@else` for conditional rendering of UI blocks.
    * `@for` for iterating over the article list (using `track` by article ID for performance).
    * `@switch` for managing loading/error/success states during API calls.
* **Deferrable Views (`@defer`):**
    * The "Favorites" sidebar component is lazy-loaded using `@defer (on interaction)`. Its bundle is not downloaded until the user clicks the "Show Favorites" button, optimizing the initial page load.
* **Standalone Components:**
    * The entire application is built using Standalone Components, completely eliminating the need for `NgModules`.
* **`inject()` Function:**
    * Services (like `NewsService` and `LocalStorageService`) are injected into components using the `inject()` function, allowing for more flexible component design.
* **Input Transforms & Required Inputs:**
    * `input.required<Article>()` is used in child components to ensure data is passed correctly.
    * `transform` property is used to convert data (e.g., a date `string` into a `Date` object) directly at the component's boundary.
* **View Transitions API:**
    * The Angular Router is configured with `withViewTransitions()` to create clean, animated transitions when navigating from the article list to a detail view.

## 📰 API Used

This project fetches data from a public news API [GNews](https://gnews.io/).

To run the project, you must:
1.  Get a free API key from your chosen provider.
2.  Add it to the `src/environments/environment.ts` file in the `apiKey` property.

## 🚀 Getting Started

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/](https://github.com/)[TU_USUARIO_DE_GITHUB]/news-feed.git
    cd news-feed
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Add your API Key:**
    * Open `src/environments/environment.ts`
    * Set your API key: `export const environment = { apiKey: 'TU_API_KEY_AQUI' };`

4.  **Run the development server:**
    ```bash
    ng serve -o
    ```
    Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.