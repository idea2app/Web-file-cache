# Web-file-cache

Web file cache service based on [GitHub actions][1]

[![Download File or Web page](https://github.com/idea2app/Web-file-cache/actions/workflows/crawler.yml/badge.svg)][2]

## Technologies

- Crawler: [`web-fetch`][3] ([Puppeteer][4] based)
- OSS service: [Cloudflare R2][5]

## Usage

### Setup repository

1.  Install GitHub apps in your organization or account:

    1.  [Probot settings][6]: set up Issue labels & Pull Request rules

2.  Click the **[<kbd>Use this template</kbd>][7] button** on the top of this GitHub repository's home page, then create your own repository in the app-installed namespace above

3.  Set Cloudflare variables is [`.github/workflows/crawler.yml`][8] as [Repository secrets][9]

### Manual cache

https://github.com/idea2app/Web-file-cache/issues/new?template=crawler.yml

### Automatic cache

```shell
$URL = "https://example.com/test.html"

curl -L \
  -X POST \
  -H "Accept: application/vnd.github+json" \
  -H "Authorization: Bearer <YOUR-TOKEN>" \
  -d '{"title":"File title","body":"### URL\n\n$URL","labels":["crawler"]}' \
  https://api.github.com/repos/idea2app/Web-file-cache/issues
```

[1]: https://github.com/features/actions
[2]: https://github.com/idea2app/Web-file-cache/actions/workflows/crawler.yml
[3]: https://github.com/TechQuery/Web-fetch
[4]: https://pptr.dev/
[5]: https://www.cloudflare.com/developer-platform/products/r2/
[6]: https://github.com/apps/settings
[7]: https://github.com/new?template_name=Web-file-cache&template_owner=idea2app
[8]: .github/workflows/crawler.yml
[9]: https://github.com/idea2app/Web-file-cache/settings/secrets/actions
