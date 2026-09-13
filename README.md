# b9-collegefarm-website

Static marketing site for College Farm, a film, photography and editorial
location in East Sussex.

## Structure

- `index.html` contains the complete page, including markup, inline CSS and
  inline JavaScript.
- `media/` contains the photography, drawing thumbnails and downloadable PDF
  plans.
- `.gitignore` ignores macOS `.DS_Store` files.

There is no package manager, build step, server-side application, test suite or
CI configuration. The site can be deployed directly to a static host, provided
the `media/` directory remains alongside `index.html`.

## Local Preview

From the repository root, run:

```bash
python3 -m http.server 8000
```

Open <http://localhost:8000> in a browser. Stop the server with `Ctrl-C`.

Opening `index.html` directly also works for most page content, but a local
server is preferable when checking links, downloads and browser behavior.

## Editing

Page content and layout are maintained in `index.html`. The main sections are:

- Project introduction and location
- Image gallery
- Production specifications, travel, access and capacities
- On-site equipment
- Spaces and dimensions
- Drawings and site plans
- Partners
- Enquiry form

Images and PDFs are referenced with paths under `media/`; preserve those paths
when replacing or adding assets. The public-facing power information refers to
the accessible 63A three-phase socket.

## Enquiry Form

The form submits to Formspree at the endpoint configured in `index.html`.
Name / Production Company and Email are required. Project type, dates, crew
size, power requirements and message are optional.

The form is submitted with client-side JavaScript and displays a success or
fallback message without navigating away from the page.

## Deployment

Deploy the repository root to any static hosting provider such as GitHub Pages,
Netlify, Vercel static hosting, S3 or a conventional web server. Confirm that
`index.html` is served at the site root and that the relative `media/` URLs
remain available.
