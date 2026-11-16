# oladipo.net

A lightweight Hugo website for Joshua Oladipo: home, writing, projects, and about pages. It uses local layouts, system fonts, no client-side JavaScript, and Hugo’s image pipeline.

## Requirements

- Hugo Extended **0.152.2** (also pinned in `.hugo-version`)

## Local preview

```sh
hugo server -D
```

Open `http://localhost:1313/`. For a repository-path preview, use for example:

```sh
hugo server -D --baseURL http://localhost:1313/oladipo.net/ --appendPort=false
```

Create a production build with `hugo --minify --panicOnWarning`. Output is written to `public/`.

## Publish content

Create a post:

```sh
hugo new content blog/my-post.md
```

Create a project:

```sh
hugo new content projects/my-project.md
```

Edit the generated Markdown, fill in its front matter, and set `draft: false` when it is ready. Project front matter supports `featured`, `projectURL`, `repositoryURL`, `image`, and `imageAlt`. Do not publish unverified biography, credentials, testimonials, projects, or sample WordPress copy.

Site navigation, introduction, social links, metadata, and the profile image are configured in `hugo.yaml`. Add verified social links to `params.social` and render them where desired.

## CI and deployment

`validate.yml` builds every pull request and push to `main`. `deploy.yml` builds and deploys GitHub Pages on pushes to `main` or manual dispatch. The workflow has only the permissions needed for Pages.

Before enabling deployment:

1. Review the site and migration gaps in `MIGRATION.md`.
2. In repository Settings → Pages, select **GitHub Actions** as the source.
3. For the apex domain, configure the DNS records currently documented by GitHub Pages (typically four `A` records and corresponding `AAAA` records); optionally point `www` to `JoshuaOladipo.github.io` with `CNAME`.
4. Add and verify `oladipo.net` in GitHub Pages, wait for DNS propagation, then enable **Enforce HTTPS** only after GitHub provisions the certificate.
5. Obtain concrete launch approval before changing DNS or replacing WordPress.

The committed `static/CNAME` prepares the custom domain but does not itself modify DNS or enable production deployment.

