---
title: "Start a Blog"
summary: Start to create your own blogs.
date: 2024-10-21
weight: 1
tags: ["Blogs"]
author: ["Yu Liao"]
---
## Get a domain for yourself
**[Namesilo](https://www.namesilo.com/)**
<br>(～2.99💲/year)

## DNS Hosting w/ Free SSL
**[Cloudflare](https://www.cloudflare.com/)**

- Add Domain Name in Cloudflare
- Replace the Cloudflare NameServer in Namesilo *Domain Manager**
- Add DNS A Type in CLoudflare DNS Records
- Enable SSL Flexible

## Config Github Pages
**[Hugo](https://gohugo.io/)** & **[Github Pages](https://pages.github.com/)**
```sh
# install hugo
hugo install
hugo new site myblog
# hugo new site . --force

cd myblog

# add PaperMod Theme Submodule
git init
git submodule add https://github.com/adityatelange/hugo-PaperMod themes/PaperMod
git submodule update --remote
```

- Config Github Action Rule (build & deploy)

[.github/workflows/hugo.yml](https://gohugo.io/hosting-and-deployment/hosting-on-github/)

- Add DNS Records in Cloudflare, `A` type, `@` for root, IPv4 `185.199.108.153`
- Add DNS Records in Cloudflare, `CNAME` type, `www` name, Target `<name>.github.io`

Use `<name>.github.io` or Custom Domain `<domain_name>.com` to Access the blogs.