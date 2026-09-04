# GCB Bank Company Profile and Afro-Asia Solutions Documentation

A static page listing the seven PDF documents. People scan a QR code, land on the page, and view or download any of the files.

## What is in this folder

```
index.html    the landing page (edit the SECTIONS block near the bottom)
assets/       the GCB logo, used for the browser tab icon
*.pdf         the seven documents, sitting alongside index.html
README.md     this file
```

## How the page is organised

| Section | Documents |
| --- | --- |
| GCB Bank Company Profile | 1 |
| Trade and Business Enablement Solutions | 4 |
| Payments | 2 |

The section headings, the jump links and the document count all build themselves from the data, so you never edit them by hand.

## Editing a document entry

Open `index.html` and scroll to the `SECTIONS` block near the bottom.

```js
{
  title: "Chinese Business Solutions",
  href:  "Chinese%20Business%20Solution.pdf",
  file:  "Chinese-Business-Solutions.pdf"
}
```

The `href` points at the PDF. The filenames contain spaces, so each space is written as `%20`. That is what a browser expects in a link, and it is why the values look slightly odd. If you rename a PDF, update the `href` to match, and if you use lowercase names with hyphens instead of spaces you can drop the `%20` entirely.

The `file` field is only the name people get when they click Download, so it can be tidier than the file on disk. The optional `note` field adds one line of description under the title.

## Deploy

Create an empty repository on github.com, then from inside this folder run:

```bash
git init
git add .
git commit -m "Add GCB and Afro-Asia document site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-REPO.git
git push -u origin main
```

Then go to vercel.com, sign in with GitHub, click **Add New, Project**, import the repository and leave every setting on its default. There is no framework and no build command. Click **Deploy**.

The largest PDF here is about 3.6 MB, well inside GitHub's 100 MB limit, so nothing needs compressing.

## QR code

Generate the code from the live Vercel address, not from any local file path. Print it at 3 cm wide or larger and test the scan on two phones before printing in quantity.

## Updating later

Any change pushed to `main` redeploys within about a minute. The QR code keeps working, because it points at the address rather than at any single file.

## One thing worth checking

Anything in this repository is public if the repository is public, and the Vercel address is reachable by anyone who has it whether or not the repository is private. Confirm all seven documents are cleared for external circulation before you deploy.
