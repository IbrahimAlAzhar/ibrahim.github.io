# How to publish your new al-folio website

Your current site lives in the repo **`IbrahimAlAzhar/ibrahim.github.io`** and is served at
**https://ibrahimalazhar.github.io/ibrahim.github.io/**. The new site is already configured for that address
(`url` + `baseurl` in `_config.yml`), so your existing link keeps working.

---

## 0. Before you start

- Keep a backup of the old site. You already have it as `ibrahim.github.io-main.zip`.
- Unzip `ibrahim-portfolio-site.zip`. Everything **inside** the `portfolio/` folder goes into the
  **root** of your repo. Don't upload the `portfolio/` folder itself.

## 1. Clear out the old files

The old site used a different theme (`jekyll-theme-minimal`), so remove its files first.

On GitHub, open the repo and delete these old files (open each one → trash icon → Commit):
`README.md`, `_config.yml`, `azhar.jpg`, `433654242_...jpg`, `DL.png`, `Django.jpg`, `LLM.jpg`, the `IMG_*.jpg` photos,
and the PDFs (`cv.pdf`, `Ibrahim_Al_Azher_CV*.pdf`, `Ibrahim Al Azher confernces.pptx (1).pdf`).

> Faster option: use **GitHub Desktop** (or git). Clone the repo, delete everything except the hidden `.git` folder,
> copy in the contents of `portfolio/`, then commit and push. This also takes care of step 2 in one go.

## 2. Upload the new files

1. In the repo, click **Add file → Upload files**.
2. Drag in **all the contents** of `portfolio/`: `_bibliography`, `_data`, `_news`, `_pages`, `_projects`, `assets`, `bin`,
   `_config.yml`, `Gemfile`, `Gemfile.lock`, `package.json`, `package-lock.json`, `purgecss.config.js`,
   `requirements.txt`, `robots.txt`, `README.md`, `LICENSE`, and the dot-files (`.gitignore`, `.gitattributes`,
   `.prettierrc`, `.prettierignore`).
3. Click **Commit changes**.

There are about 83 files, which is under GitHub's 100-files-per-upload limit.

### The hidden `.github` folder is required

The `.github/workflows/deploy.yml` file builds the site. Finder and Explorer hide dot-folders, so it's easy to miss.

- **macOS:** press `Cmd + Shift + .` in Finder to show hidden files, then drag `.github` in as well.
- **Or create it by hand:** click **Add file → Create new file**, type the name `.github/workflows/deploy.yml`
  (the slashes create the folders), paste in the contents of `portfolio/.github/workflows/deploy.yml`, and commit.

## 3. Let the workflow publish

1. Go to **Settings → Actions → General → Workflow permissions**, select **Read and write permissions**, and click **Save**.
2. Go to the **Actions** tab. A run called **Deploy site** should start. If it doesn't, open
   **Deploy site** and click **Run workflow**. It takes about 3–6 minutes.
3. When it turns green, it will have created a branch called **`gh-pages`**.
4. Go to **Settings → Pages**. Under **Build and deployment**, set **Source = Deploy from a branch** and
   **Branch = `gh-pages` / `(root)`**, then click **Save**.
5. After about a minute, open **https://ibrahimalazhar.github.io/ibrahim.github.io/**. Press Ctrl/Cmd+Shift+R to hard-refresh.

If the page looks unstyled (plain text, broken links), `baseurl` in `_config.yml` doesn't match the repo name.

---

## Optional: use the shorter address https://ibrahimalazhar.github.io

You already have a repo named `IbrahimAlAzhar.github.io` with placeholder "My website" content. To publish there instead:

1. Upload the same files to **that** repo, replacing its contents.
2. In `_config.yml`, change `baseurl: /ibrahim.github.io` to `baseurl:` (leave it empty), and change `og_image` to
   `https://ibrahimalazhar.github.io/assets/img/prof_pic.jpg`.
3. In `_data/cv.yml`, change `website:` to `https://ibrahimalazhar.github.io/`.
4. Follow step 3 above in that repo.

## Optional: GitHub profile README

`PROFILE_README.md` is a short summary for your GitHub profile page (github.com/IbrahimAlAzhar). To use it,
create a public repo named exactly **`IbrahimAlAzhar`** if you don't have one, and save the file there as `README.md`.

---

## Updating the site later

Edit files directly on GitHub (pencil icon). Each commit rebuilds the site automatically.

- **New news item:** add `_news/2026-12-01-news.md`. Copy the format of any existing news file.
- **New paper:** add a BibTeX entry to `_bibliography/papers.bib`. Add `selected = {true}` to show it on the home page.
- **New CV PDF:** replace `assets/pdf/Ibrahim_Al_Azher_CV.pdf`, keeping the same name.
- **Google Analytics (optional):** paste your `G-XXXX` ID into `analytics: google:` in `_config.yml`.
