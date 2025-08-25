# Overview

# API Reference Overview

Welcome to the **API Reference** section.  
This section provides detailed documentation for each available endpoint in the API.  

Each page inside this `reference/` folder covers:  
- **Endpoint path and method** (e.g., `GET /photos`)  
- **Description** of what the endpoint does  
- **Request details** (query parameters, request body, and headers)  
- **Example requests** (with `curl` or JSON payloads)  
- **Example responses** with explanations of fields  
- **Errors & edge cases** to help with debugging  

---

## How to Use This Reference

- Navigate to a specific endpoint (e.g., **Users**, **Posts**, **Comments**) to view request and response details.  
- Each endpoint page is designed to be self-contained, so you can copy examples directly into tools like **Postman** or **cURL**.  
- For a schema-driven view, check out the **OpenAPI Specification** included in this folder (`openapi.yaml`).  
  - If you’re using the **Docusaurus OpenAPI plugin**, the spec is rendered as interactive docs.  

---

## Available Endpoints

- [Random](./randomPhotos.md) → Generate random photos from unsplash  
- [New](./newPhotos.md) → View new photos from unsplash.  
- [Search](./searchPhotos.md) → Search for photos from the unsplash gallery.  

---

## Bonus: OpenAPI Spec

We also provide an **OpenAPI 3.0 specification** for this API:  
- File: [`openapi.yaml`](./openapi.yaml)  
- Use it with tools like **Swagger UI**, **Postman**, or the [Docusaurus OpenAPI Docs plugin](https://github.com/PaloAltoNetworks/docusaurus-openapi-docs) for an interactive experience.  
