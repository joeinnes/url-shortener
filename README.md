# Joe's URL Shortener

A simpler implementation of https://github.com/nelsontky/gh-pages-url-shortener using simple files

To use yourself, add files in the 'links' directory with the name of the short link (eg: "test" will become <your_url_here>/test

Configure GH Pages to use 'main' and you are done. You probably want to change the 404.html page to use your name though, rather than mine).

## How does this work?

Adapted from @kidGodzilla's explanation [here](https://github.com/nelsontky/gh-pages-url-shortener/issues/5#issuecomment-728040879).

1. CNAME points URL to gh-pages branch
2. 404.html handles all requests
3. Small javascript snippet tries to fetch the file at `/links/<short_link>`. If it's found, it'll redirect the user to whatever is in the file.
4. Profit?

## Sidenote for security
There's no safety checking on the fetched file, so XSS is possible using this tool. Make sure you are in control of the repository, and you don't accept PRs without proper review (see https://link.joeinn.es/xss from https://github.com/joeinnes/url-shortener/blob/main/links/xss).

Also, obviously, this tool does not check the safety of the site you're redirecting to. Malware etc. could theoretically be deployed through this URL shortener.
