# Mennatullah Ibraheem — Portfolio

A one-page portfolio with a blog. Plain HTML, CSS and JavaScript: no build step, no framework.

| File | What it is |
| --- | --- |
| `index.html` | The whole site: layout, styles, content and the blog reader |
| `posts.json` | Blog posts, newest first by `date` |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Put it online (GitHub Pages)

1. Create a new repository on GitHub, for example `portfolio`.
2. Push this folder to it:
   ```bash
   git init
   git add .
   git commit -m "Portfolio"
   git branch -M main
   git remote add origin https://github.com/MennaTallah2/portfolio.git
   git push -u origin main
   ```
3. On GitHub, open **Settings → Pages**, set **Source** to *Deploy from a branch*, pick `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://mennatallah2.github.io/portfolio/`.

Optional: to use your own domain (for example `mennatullah.dev`), add it under **Settings → Pages → Custom domain** and follow GitHub's DNS instructions.

## Update the site

Every change you push to `main` goes live in about a minute.

- **Small text change:** open `index.html` on github.com, click the pencil icon, edit, then **Commit changes**.
- **Bigger change:** open this folder in Claude Code and describe what you want, then push.

## Add a blog post

Add a new entry to the list in `posts.json`:

```json
{
  "id": "p-2026-12-01",
  "slug": "my-new-post",
  "title": "My new post",
  "date": "2026-12-01",
  "tags": ["ai", "react"],
  "summary": "One or two sentences shown in the post list.",
  "body": "First paragraph.\n\n## A heading\n\nMore text with `code` and **bold**."
}
```

- `slug` becomes the post's link: `#post-my-new-post`. Use lowercase letters, numbers and hyphens.
- `body` supports `##` and `###` headings, `-` and `1.` lists, `>` quotes, `**bold**`, `*italic*`, `` `code` ``, fenced code blocks and `[links](https://...)`.
- Inside JSON, line breaks are written as `\n` and quotes as `\"`. The easiest way is to ask Claude: "add this post to posts.json", paste the text, and let it handle the formatting.

To edit or delete a post, change or remove its entry.

## Preview on your computer

The blog loads `posts.json` with `fetch`, which browsers block for files opened directly from disk. Run a small local server instead:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

Note: the **New post** button only appears when the page runs inside Claude. On GitHub Pages it stays hidden, and posts are added through `posts.json`.
