
## What I Set Up

I configured a GitHub workflow to automatically lint and validate documentation:

* **Vale** → for checking writing style and consistency across Markdown files.
* **Spectral** → for linting and validating the OpenAPI specification files.
* **Redocly** → for rendering the OpenAPI specification into a user-friendly static HTML page.

This setup ensures documentation quality, consistency, and usability for developers and end-users.

---

## Rules and Standards Enforced

### Vale

* Enforced clarity and readability in documentation.
* Maintained consistent tone and style (based on chosen style guide, e.g., Microsoft/Google).
* Ensured grammar and structure fit a beginner-friendly documentation style.

### Spectral

* Validated the OpenAPI specification against best practices.
* Checked for common errors (e.g., missing descriptions, incorrect schema references).
* Enforced consistency across endpoints and schema definitions.

---

## Challenges Faced

* **Understanding Vale and Spectral from scratch**: As a beginner, I had to learn how each tool worked and what rules they enforced.
* **Balancing detail with simplicity**: While setting rules, I needed to ensure documentation was comprehensive but still easy to navigate.

---

## What I Learned

* **Importance of well-structured documentation**: Looking at the project from a user’s perspective highlighted common pain points and how to address them.
* **Multimedia enhances understanding**: Including videos, images, and code snippets makes documentation more engaging and effective.
* **Automation is key**: Having Vale and Spectral run automatically on commits ensures consistency without relying on manual reviews.
* **Separation of roles**: Vale focuses on *language/style*, while Spectral ensures *technical correctness* in the OpenAPI spec.

## Screenshots

#### Vale Linting

 <img src="/img/valeLinting.png" alt="vale image" width="300" />

## Spectral Linting
 <img src="/img/spectralLinting.png" alt="spectral image" width="300" />

 