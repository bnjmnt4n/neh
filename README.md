# neh

<https://neh.child.workers.dev>

A tool that redirects you; intended to be an Alfred for your browser.

![neh meme by Mothership](https://mothership.sg/wp-content/uploads/2015/08/Neh.jpg)

Inspired by Facebook's open source [bunny](http://www.bunny1.org) tool, but
rewritten for the cloud serverless edge computing age – neh runs in Cloudflare
Workers on Cloudflare's edge servers located close to you. TL;DR it fast.

## Usage

The easiest way to use neh is to set <https://neh.child.workers.dev?=> as your
browser's default search engine. Then, run commands by typing their command
names followed by your query. If no command is detected, neh will just redirect
you to Google.

Here are some examples:

* Search YouTube: [yt rickroll](https://neh.child.workers.dev?=yt%20rickroll)
* Go to a GitHub repository: [ghr nusmodifications/nusmods](https://neh.child.workers.dev?=ghr%20nusmodifications/nusmods)
* Perform a DuckDuckGo search: [d duckduckgo privacy](https://neh.child.workers.dev?=d%20duckduckgo%20privacy)
* Fallback to a Google search: [not a command](https://neh.child.workers.dev?=not%20a%20command)

Neh! Liddat only. Easy.

## Dev setup

We use Cloudflare's [Wrangler](https://github.com/cloudflare/wrangler) tool to
run and publish neh.

Create a wrangler.toml file with appropriate configuration. Here's a template:

```
name = "neh"
type = "webpack"
zone_id = ""
private = false
account_id = ""
route = ""
workers_dev = true
```

Install dependencies with NPM.

```
npm install
```

To
[preview](https://developers.cloudflare.com/workers/quickstart/#preview-your-project)
neh in development, run:

```
npm run start
```

To publish neh to Cloudflare Workers, run:

```
npm run publish
```
