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
content_copy
download
Use code with caution.
Markdown
2. Install Dependencies
pip install -r requirements.txt
content_copy
download
Use code with caution.
Bash
3. Configure MkDocs

Edit mkdocs.yml to customize your site. This includes:

Setting the site_name, site_description, and site_author.

Configuring the theme, palette, font, and features.

Optionally, adding a nav section to structure your documentation. If you omit the nav section, MkDocs will automatically generate a navigation menu based on your file structure.

Add your documentation content as Markdown files (.md) in the docs directory.

Add blog posts as Markdown files in the docs/blog/posts directory. Each blog post should have a filename in the format YYYY-MM-DD-post-title.md and include YAML front matter for the title and date:

---
title: Your Blog Post Title
date: 2023-12-20
---

Your blog post content goes here...
content_copy
download
Use code with caution.
4. Build and Serve Locally
mkdocs serve
content_copy
download
Use code with caution.
Bash

This will start a local development server. Open your web browser and go to http://127.0.0.1:8000/ to view your site.

Deployment to Vercel

This project is optimized for deployment to Vercel.

Using the Vercel Dashboard (Recommended)

Create a Vercel account: If you don't have one, sign up for a free account at vercel.com.

Import your Git repository: In your Vercel dashboard, click on "New Project" and import your Git repository (e.g., GitHub, GitLab, Bitbucket).

Configure the project:

Framework Preset: Select Other.

Build Command: Leave it blank and turn the Override off. Vercel will automatically detect and run the build script defined in your package.json (which is mkdocs build -d public).

Output Directory: Enter public and turn the Override on.

Install Command: Leave it blank and turn the Override off.

Development Command: Enter mkdocs serve and turn the Override on.

Deploy: Click the "Deploy" button.

Using the Vercel CLI

Install the Vercel CLI:

npm install -g vercel
content_copy
download
Use code with caution.
Bash

Deploy your project:

vercel
content_copy
download
Use code with caution.
Bash

Follow the prompts to link your project to your Vercel account.

Deploy to production:

vercel --prod
content_copy
download
Use code with caution.
Bash
Troubleshooting

404 Errors: If you encounter 404 errors after deploying, double-check the following:

Ensure that your package.json file has a build script that runs mkdocs build -d public.

Confirm that the outputDirectory in your vercel.json file is set to public.

Verify that your mkdocs.yml file specifies site_dir: public.

Clear your Vercel project's cache by redeploying and unchecking "Use existing build cache."

Other Build Errors: Most build errors are caused by typos in mkdocs.yml or missing packages in requirements.txt. Carefully review your recent changes and the Vercel build logs for clues.

Contributing

(Optional: Add a section about how to contribute to your project)

License

This project is licensed under the MIT License - see the LICENSE file for details.

