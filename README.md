## Vercel-MkDocs-Material

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fkaitas%2Fvercel-mkdocs-material)

**MkDocs with ▲Vercel (minimal configuration)**

- [▲ Vercel](https://vercel.com/)
- [MkDocs](https://www.mkdocs.org/)
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/)

## How to use

1. Edit `mkdocs.yml` and `docs/index.md`, add more files if needed.
2. Add the pip package to `requirements.txt` . (Themes and plugins)

3. Local build

```
pip install -r requirements.txt
mkdocs serve
```

4. Use the Vercel command: `vercel dev` `vercel` and `vercel --prod`  
or commit to a Git project: `git push`

Check the `Build & Development Settings` items.

- Framework Preset: Other

- Build Command: (null) Override: off

- Output Directory: ``public`` Override: on

- Install Command: (null) Override: off

- Development Command: ``mkdocs serve`` Override: on



## Build error

Many of the build error are that you mistyped `mkdocs.yml`
or you forgot to add the package to` requirements.txt`.
Check the file change immediately before the error occurred.

This is often not a problem with this project.
You should not open an issue for that.

## Fork of this project

If you fork this project, be sure to change something and commit.
If you re-deploy without changing anything, it's my commit and I'll be notified.

You can also create a new project without forking or use the [Vercel CLI](https://vercel.com/docs/cli) without creating a project.

