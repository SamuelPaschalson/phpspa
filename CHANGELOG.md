# 📦 phpSPA v1.0.0 – Initial Release

🚀 *The first official release of phpSPA is here!*

`phpSPA` brings modern Single Page Application (SPA) behavior to native PHP — allowing you to build dynamic, fast-loading, and component-based apps using **pure PHP and a tiny JS layer**. No build tools. No templating engines. Just you and PHP.

---

## ✨ Highlights

* ✅ **Component-Based Architecture** — Define pages as simple PHP functions.
* ✅ **Dynamic Routing** — Easily register GET, POST, or both for each component.
* ✅ **Client-Side Navigation** — URL updates powered by the History API.
* ✅ **State Management (New)** — Server-managed state with client-side updates via `phpspa.setState(...)`.
* ✅ **SEO-Friendly** — Server-rendered first loads, perfect for indexing.
* ✅ **Graceful Fallback** — Works even without JavaScript.
* ✅ **Custom Loaders** — Define per-component or global loading indicators.
* ✅ **Scoped Styles & Scripts** — Add JS/CSS directly inside your components.
* ✅ **Minimal JS Runtime** — Tiny client script with zero dependencies.

---

## 📂 What's Included

* `App` class: Bootstraps your layout and routes.
* `Component` class: Defines routes, methods, targets, and metadata.
* `Request` class: Handles input, files, query params, headers, and auth.
* Full support for nested components and dynamic path parameters (e.g., `/user/{id}`).
* Smart HTML layout placeholders (`__CONTENT__`, `__TITLE__`, meta injection).
* Developer-friendly `<Link />` and history-based navigation (`phpspa.navigate`, `.back()`, `.forward()`).

---

## 🧠 New in v1.0.0

* 🌟 **State Management**:

  * Define state in PHP with `createState('key', default)`.
  * Trigger re-renders from the frontend via `phpspa.setState('key', value)`.
  * Automatically updates server-rendered output in the target container.

* 🧩 **Scoped Component Styles & Scripts**:

  * Use `<style data-type="phpspa/css">...</style>` and `<script data-type="phpspa/script">...</script>` inside your components.
  * Automatically injected and removed during navigation.

* ⚙️ **Improved JS Lifecycle Events**:

  * `phpspa.on("beforeload", callback)`
  * `phpspa.on("load", callback)`

---

## 📦 Installation

```bash
composer require dconco/phpspa
```

Include the JS engine:

```html
<script src="https://cdn.jsdelivr.net/npm/phpspa-js"></script>
```

---

## 🧱 Coming Soon

* 🛡️ CSRF protection helpers and automatic verification
* 🧪 Testing utilities for components
* 🌐 Built-in i18n tools

---

## 📘 Docs & Links

* GitHub: [dconco/phpspa](https://github.com/dconco/phpspa)
* JS Engine: [dconco/phpspa-js](https://github.com/dconco/phpspa-js)
* License: MIT

---

💬 Feedback and contributions are welcome!

— Maintained by [Dave Conco](https://github.com/dconco)

---

# v1.1.0

* Added file import `phpSPA\Component\import()` function for importing files (images) to html. See: [File Import Utility](https://phpspa.readthedocs.io/en/latest/v1.1/1-file-import-utility)

* Added `map()` method to state management, can now map array to html elements, `$stateItems->map(fn (item) => "<li>{$item}</li>")`. See: [Mapping In State Management](https://phpspa.readthedocs.io/en/latest/v1.1/2-mapping-in-state-management)

* Added component to be accessible by html tags, `<Component />`, both inline tags and block tags `<Component></Component`. See: [Using Component Functions By HTML Tags](https://phpspa.readthedocs.io/en/latest/v1.1/3-using-component-functions-by-html-tags)

* Created component function `<Link />`, and made it be under the `phpSPA\Component` namespace. See: [Link Component](https://phpspa.readthedocs.io/en/latest/v1.1/4-link-component)

## Deprecated

* Using HTML `<Link />` tag without the function namespace is deprecated. You must use the namespace in other to use the component function, `<PhpSPA.Component.Link />` See: [Deprecated HTML Link](https://phpspa.readthedocs.io/en/latest/v1.1/4-link-component/#deprecated)
