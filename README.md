# Audiobook-Shelf-CSP
Working CSP policy for audiobookshelf in the advanced configuration section of npmplus (npm untested)
Absolutely! Here’s a cleaned-up and GitHub-appropriate version of your post, tailored as a README.md or issue/discussion post. It’s structured, concise, and formatted with Markdown for GitHub clarity.

⸻

🛡️ Working CSP Setup for Audiobookshelf Behind NPMplus (OpenResty)

Hey everyone,

Just wanted to share a working Content Security Policy (CSP) configuration I’ve been using with NPMplus as a reverse proxy for Audiobookshelf.

This setup:
	•	Clears any CSP headers from upstream
	•	Applies a strict global policy
	•	Still allows the app (and its service worker) to function correctly

🔧 Nginx/NPMplus Custom Configuration

Replace (CODE HERE) with your actual configuration snippet

(code here)

✅ What This Does
	•	Blocks everything by default:
default-src 'none'
	•	Whitelists only the domains Audiobookshelf actually uses:
	•	Google Books
	•	OpenLibrary
	•	Archive.org
	•	Apple cover images (mzstatic)
	•	Loosens CSP for the service worker to allow pulling Workbox from jsDelivr

⚠️ Known Limitation
	•	Mozilla Observatory still flags the config due to 'unsafe-inline'.
Unfortunately, this is currently required since Audiobookshelf uses inline scripts and styles.
	•	I haven’t implemented nonce or hash support yet. If anyone gets nonces working cleanly with NPMplus, please share!

⸻

Hope this helps anyone looking to harden their Audiobookshelf instance behind NPMplus.
Feel free to open an issue or pull request if you improve upon this setup!

⸻

Once this is posted on GitHub, you can link to it directly in your Reddit post with something like:

I posted my full working NPMplus CSP config for Audiobookshelf on GitHub: [GitHub link here] — hope it helps others!

Let me know if you want help writing the actual Nginx config or setting up the GitHub repo/page!
