# Vercel-MkDocs-Material

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fkaitas%2Fvercel-mkdocs-material)

**MkDocs with Material for MkDocs theme, easily deployed to Vercel (minimal configuration). Includes blog functionality using mkdocs-blog-plugin.**

- [▲ Vercel](https://vercel.com/)
- [MkDocs](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)
- [mkdocs-blog-plugin](https://github.com/liang2kl/mkdocs-blog-plugin)



## Getting Started

### 1. Clone the Repository

```bash
git clone <your_repository_url>
cd <your_repository_directory>
```

Replace `<your_repository_url>` with the URL of your Git repository and `<your_repository_directory>` with the name of the directory you want to clone the project into.

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

This command installs the necessary Python packages specified in the `requirements.txt` file, including `mkdocs`, `mkdocs-material`, and `mkdocs-blog-plugin`.

### 3. Configure MkDocs

*   Edit `mkdocs.yml` to customize your site. This includes:
    *   Setting the `site_name`, `site_description`, and `site_author`.
    *   Configuring the `theme`, `palette`, `font`, and `features`.
    *   Adding a `nav` section to structure your documentation (optional). If you omit the `nav` section, MkDocs will automatically generate a navigation menu based on your file structure.
*   Add your documentation content as Markdown files (`.md`) in the `docs` directory.
*   Add blog posts as Markdown files in the `docs/blog/posts` directory. Each blog post should have a filename in the format `YYYY-MM-DD-post-title.md` and include YAML front matter for the title and date:

```markdown
---
title: Your Blog Post Title
date: 2023-12-20
---

Your blog post content goes here...
```

### 4. Build and Serve Locally

```bash
mkdocs serve
```

This will start a local development server. Open your web browser and go to `http://127.0.0.1:8000/` to view your site.

## Deployment to Vercel

This project is optimized for deployment on Vercel.

### Using the Vercel Dashboard (Recommended)

1. **Create a Vercel Account:** If you don't already have one, sign up for a free account at [vercel.com](https://vercel.com/).

2. **Import Your Git Repository:** In your Vercel dashboard, click on "New Project" and import your Git repository (e.g., GitHub, GitLab, Bitbucket).

3. **Configure the Project:**
    *   **Framework Preset:** Select `Other`.
    *   **Build Command:** Enter `mkdocs build -d public` and turn the Override **on**.
    *   **Output Directory:** Enter `public` and turn the Override **on**.
    *   **Install Command:** Enter `pip install -r requirements.txt` and turn the Override **on**.
    *   **Development Command:** Enter `mkdocs serve` and turn the Override **on**.

    **Important:** You need to configure these settings even if you have a `vercel.json` file because the `builds` section in `vercel.json` overrides the Build & Development Settings in the Vercel dashboard.

    **Settings Screenshot:**

    ![Vercel Build & Development Settings](https://imgur.com/DO3Nfq9) 


4. **Deploy:** Click the "Deploy" button. Vercel will automatically build and deploy your site.

### Using the Vercel CLI

1. **Install the Vercel CLI:**

    ```bash
    npm install -g vercel
    ```

2. **Deploy your project:**

    ```bash
    vercel
    ```

    Follow the prompts to link your project to your Vercel account.

3. **Deploy to production:**

    ```bash
    vercel --prod
    ```

## Troubleshooting

*   **404 Errors:** If you encounter 404 errors after deploying, double-check the following:
    *   Ensure that your `vercel.json` file is correctly configured with the `builds` section as described above.
    *   Confirm that the `outputDirectory` in your `vercel.json` file is set to `public`.
    *   Verify that your `mkdocs.yml` file specifies `site_dir: public`.
    *   Clear your Vercel project's cache by redeploying and unchecking "Use existing build cache."
*   **Other Build Errors:** Most build errors are caused by typos in `mkdocs.yml` or missing packages in `requirements.txt`. Carefully review your recent changes and the Vercel build logs for clues.

## Contributing

(Optional: Add a section about how to contribute to your project)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


## TIPS

`vercel.json`

```json
{
  "builds": [
    {
      "src": "requirements.txt",
      "use": "@vercel/python"
    },
    {
      "src": "package.json",
      "use": "@vercel/static-build",
      "config": {
        "distDir": "public",
        "buildCommand": "mkdocs build -d public"
      }
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "/public/$1"
    }
  ]
}
```
`package.json`
```json
{
  "name": "mkdocs-material-project",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "mkdocs serve",
    "vercel-build": "echo 'Ignoring vercel-build because builds are defined in vercel.json'"
  }
}
```
