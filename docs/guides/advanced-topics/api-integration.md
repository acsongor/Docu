---
title: API integration
sidebar_position: 2
---

# Integrating an OpenAPI Specification with Docusaurus

This guide explains how to integrate an OpenAPI (Swagger) specification into your Docusaurus documentation site.

## 1. Choose an OpenAPI Renderer

Docusaurus does not natively render OpenAPI specs. You can use a React-based renderer like [Redoc](https://github.com/Redocly/redoc) or [Swagger UI React](https://github.com/swagger-api/swagger-ui).

## 2. Install the Renderer

For example, to use Redoc:

```bash
npm install redoc
```

Or for Swagger UI React:

```bash
npm install swagger-ui-react
```

## 3. Add Your OpenAPI Spec

Place your OpenAPI YAML or JSON file in the `static` directory (e.g., `static/openapi.yaml`).

## 4. Create a React Component

Create a new file, e.g., `src/components/OpenApiDoc.js`:

```jsx
import React from 'react';
import Redoc from 'redoc';

export default function OpenApiDoc() {
    return (
        <Redoc specUrl="/openapi.yaml" />
    );
}
```

Or with Swagger UI React:

```jsx
import React from 'react';
import SwaggerUI from 'swagger-ui-react';
import 'swagger-ui-react/swagger-ui.css';

export default function OpenApiDoc() {
    return (
        <SwaggerUI url="/openapi.yaml" />
    );
}
```

## 5. Use the Component in Your Markdown

Docusaurus supports [MDX](https://docusaurus.io/docs/markdown-features/react) so you can embed React components:

```mdx
import OpenApiDoc from '@site/src/components/OpenApiDoc';

<OpenApiDoc />
```

## 6. Build and View

Run your Docusaurus site:

```bash
npm run start
```

Visit the page to see your interactive API documentation.

---

**References:**
- [Docusaurus MDX Docs](https://docusaurus.io/docs/markdown-features/react)
- [Redoc Documentation](https://redocly.com/docs/redoc/)
- [Swagger UI React Docs](https://github.com/swagger-api/swagger-ui)
