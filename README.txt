GLOBAL SPRINGS ALLIANCE — CLEAN CLOUDFLARE REPOSITORY

This repository is organized so Cloudflare deploys ONLY the website files inside /public.

ROOT FILES
- wrangler.jsonc        Cloudflare/Wrangler configuration
- .gitignore            Local development ignores
- README.txt            This file

WEBSITE
- Everything served publicly is inside /public.
- English pages are directly inside /public.
- Spanish, French, Simplified Chinese, and Hindi pages are in /public/es, /public/fr, /public/zh, and /public/hi.
- Images, logos, styles.css, spring-density.csv, robots.txt, and sitemap.xml are also inside /public.

CLOUDFLARE
The existing deploy command can remain:
    npx wrangler deploy

wrangler.jsonc points assets.directory to ./public, so hidden Git files (.git) are never treated as website assets.

IMPORTANT
- Do not put raw/private spring coordinates in this repository.
- spring-density.csv is the generalized public dataset.
- John Simaika is intentionally not included on the current English Expert Coalition page pending approval.

GitHub browser workflow:
1. Upload the /public folder and wrangler.jsonc to the repository root.
2. Commit to main.
3. Cloudflare should build automatically.
4. If needed, use Retry build in Cloudflare.

Once the new deployment is confirmed, old duplicate website files that remain at the repository root can be deleted; Cloudflare ignores them because it deploys only ./public.
