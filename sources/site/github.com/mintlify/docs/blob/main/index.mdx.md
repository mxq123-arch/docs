# Source: https://github.com/mintlify/docs/blob/main/index.mdx

### Uh oh!

There was an error while loading. [Please reload this page]().

[mintlify](https://github.com/mintlify) / **[docs](https://github.com/mintlify/docs)** Public

- [Notifications](https://github.com/login?return_to=%2Fmintlify%2Fdocs) You must be signed in to change notification settings
- [Fork 236](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
- [Star 415](https://github.com/login?return_to=%2Fmintlify%2Fdocs)
 

## FilesExpand file tree

 main

/

# index.mdx

Copy path

Blame

More file actions

Blame

More file actions

## Latest commit

[![skeptrunedev](https://avatars.githubusercontent.com/u/15804464?v=4&size=40)](https://github.com/skeptrunedev) [skeptrunedev](https://github.com/mintlify/docs/commits?author=skeptrunedev)

[Boost search ranking for single-word title pages (](https://github.com/mintlify/docs/commit/9200586a3a336b6f3d4be64ee03ff3e717d1ac6f) [#5670](https://github.com/mintlify/docs/pull/5670) [)](https://github.com/mintlify/docs/commit/9200586a3a336b6f3d4be64ee03ff3e717d1ac6f)

Open commit detailssuccess

May 5, 2026

[9200586](https://github.com/mintlify/docs/commit/9200586a3a336b6f3d4be64ee03ff3e717d1ac6f) · May 5, 2026

## History

[History](https://github.com/mintlify/docs/commits/main/index.mdx)

Open commit details

History

76 lines (68 loc) · 2.77 KB

## FilesExpand file tree

 main

/

# index.mdx

Copy path

Top

## File metadata and controls

- Preview
 
- Code
 
- Blame
 

76 lines (68 loc) · 2.77 KB

[Raw](https://github.com/mintlify/docs/raw/refs/heads/main/index.mdx)

Copy raw file

Download raw file

Outline

Edit and raw actions

<table><tbody><tr><th>title</th><td>Introduction</td></tr><tr><th>description</th><td>Mintlify is an AI-native documentation platform built for developers, with beautiful defaults, interactive API playgrounds, and smart search.</td></tr><tr><th>mode</th><td>frame</td></tr><tr><th>keywords</th><td><table><tbody><tr><th><div dir="auto">overview</div></th><th><div dir="auto">platform</div></th><th><div dir="auto">getting started</div></th><th><div dir="auto">features</div></th></tr></tbody></table></td></tr><tr><th>boost</th><td>3</td></tr></tbody></table>

export const HeroCard = ({ filename, title, description, href }) => { return ( [<img src={`https://raw.githubusercontent.com/mintlify/docs/refs/heads/main/images/hero/${filename}.png`} className="block dark:hidden pointer-events-none group-hover:scale-105 transition-all duration-100" /> <img src={`https://raw.githubusercontent.com/mintlify/docs/refs/heads/main/images/hero/${filename}-dark.png`} className="pointer-events-none group-hover:scale-105 transition-all duration-100 hidden dark:block" />](https://github.com/mintlify/docs/blob/main/{href})

### {title}

{description} ); };

[![Decorative background image.](https://github.com/mintlify/docs/raw/main/images/hero/background-light.svg)](https://github.com/mintlify/docs/blob/main/images/hero/background-light.svg) [![Decorative background image.](https://github.com/mintlify/docs/raw/main/images/hero/background-dark.svg)](https://github.com/mintlify/docs/blob/main/images/hero/background-dark.svg)

# Documentation

```
<div className="max-w-xl mx-auto px-4 mt-4 text-lg text-center text-gray-500 dark:text-zinc-500">
  Meet the next generation of documentation. AI-native, beautiful out-of-the-box, and built for developers and teams.
</div>

<div className="px-6 lg:px-0 mt-12 lg:mt-24 grid sm:grid-cols-2 gap-x-6 gap-y-4">
  <HeroCard filename="rocket" title="Quickstart" description="Deploy your first docs site in minutes with our step-by-step guide" href="/quickstart" />

  <HeroCard
    filename="cli"
    title="CLI installation"
    description="Install the CLI to preview and develop your docs locally"
    href="/installation"
  />

  <HeroCard
    filename="editor"
    title="Web editor"
    description="Make quick updates and manage content with our browser-based editor"
    href="/editor/index"
  />

  <HeroCard
    filename="components"
    title="Components"
    description="Build rich, interactive documentation with our ready-to-use components"
    href="/components/accordions"
  />
</div>
```