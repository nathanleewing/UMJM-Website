# UMJM Website

This site uses Jekyll to build static pages from Liquid templates and markdown files.

If you haven't used Jekyll before, you'll need to install it. From the CLI, this will look something like:

```
gem install bundler jekyll
```

## Getting Started

### Workflow

1. Edit content
2. Build and test locally
3. Upload built content to UMJM site via FTP

### What is Where

* `_pages`: Contains static pages (about, submissions, contact us, etc. in HTML/Liquid template format)
* `_posts`: Contains a page for each article in every issue of the journal (markdown format)
* `assets`: Contains CSS, images, and uploaded documents
* `_site`: Contains the output from Jekyll's `build` command (don't edit this)

## Making Edits

You'll typically be making changes to content in `_posts`, `_pages`, `assets`, and maybe `index.html`:

* Edits to the main site should be done in `_pages`
* Issue/article summary pages go in `_posts`
* Issue/article PDFs go in `assets/documents`
* Volunteer headshots go in `assets/images/editors`

**Do not** manually edit content in `_site`: this directory contains the final compiled content generated by
Jekyll's `build` command (this is what will eventually go up to the UMJM website), and if you modify this content
directly your changes will be lost next time you build.

### Creating a New Volume/Issue

1. Create individual PDFs (e.g., using LaTeX) for each article and a single PDF of the whole issue
2. Add final approved PDFs into the appropriate directory (`assets/documents/VxIy`)
3. Add the cover image to the `assets/images/` directory
4. Create a page in markdown format (with cover image) for the whole issue in `_posts` (linking the cover image and PDF appropriately)
5. Create a page in markdown format (with cover image) for each article in `_posts` (linking the cover image and PDF appropriately)
6. Test your changes with `jekyll serve`
7. Build the website with `jekyll build`
8. Upload the contents of `_site` to the `public_html` directory at ftp://ftp.umja.ca

## Testing

After making your changes, run `jekyll serve`. This will compile your changes and host the site locally.

Then navigate to http://127.0.0.1:4000 to view the site and verify that your changes are correct.

## Building

Once your changes are complete, build the final version with:

```
jekyll build
```

## Deployment

Once your changes are built, open an FTP client (e.g., Filezilla) and connect to ftp://ftp.umjm.ca.

Take the contents of `_site` generated by your build and replace the contents of `public_html` on the remote site with them.
(Best practice is to copy `public_html` to `public_html.bak` first, in case you make a mistake.)