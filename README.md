# WordPress Static CDN

This project automatically builds and publishes WordPress static core assets, such as CSS, JS, images, fonts, and more, into GitHub Pages for use as a CDN.

The goal is to offload front-end assets, like `/wp-includes/js/` and `/wp-admin/css/`, from your VPS or WordPress host. This reduces bandwidth and improves loading speed for visitors around the world.

> Note: PHP files are removed because GitHub Pages only serves static content. This repository is not a replacement for WordPress itself, but a CDN for its assets.

## Features

- Fetches the latest WordPress version from the official API  
- Removes unnecessary files (PHP, default bundled themes/plugins, docs)
- Creates a GitHub Release with a ZIP archive of the static assets  
- Deploys to GitHub Pages automatically

## How it works

1. Trigger the workflow manually from the Actions tab.  
2. The workflow fetches the latest WordPress version from the official API.  
3. If a release for that version already exists, the workflow exits early.  
4. Otherwise, the workflow:
   - Downloads the official WordPress zip
   - Removes PHP files and other unnecessary items
   - Moves static assets into root folder
   - Commits the changes
   - Creates a release with a zip archive
   - Deploys to GitHub Pages  

## Example CDN URLs

After deployment, you can load assets like:

```
https://cdn.example.com/wp-includes/js/jquery/jquery.js
```
Or from GitHub Pages:  
```
https://your-username.github.io/wp-includes/js/jquery/jquery.js
```

Replace `cdn.example.com` or `your-username.github.io` with your actual CDN domain or subdomain.

## USAGE

if you want to use this repo as your cdn offloader, you are welcome to use and install our plugin -> [Download Plugin](https://wordpress-cdn.sticknologic.is-a.dev)
in your wordpress site

## License

WordPress is licensed under the GNU General Public License (GPL) v2 or later.  
This project redistributes only the static files, like CSS, JS, images, and fonts, for convenience. For full details, see the WordPress license: [WordPress License](https://wordpress.org/about/license/).

## Author

Maintained by [STICKnoLOGIC](https://sticknologic.is-a.dev).