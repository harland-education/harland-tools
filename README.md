# Harland Tools

Internal teacher tools for Harland Education. A small static collection of single-file browser utilities that teachers can open from any computer or phone. There is no login and no build step. Each tool is one self-contained HTML file whose only external dependency is Google Fonts.

## Live URLs

- Landing page: https://harland-education.github.io/harland-tools/
- Class Notes Generator: https://harland-education.github.io/harland-tools/notes-generator/
- Unit Completion Generator: https://harland-education.github.io/harland-tools/completion-generator/

## How the AI features work

Both tools have AI-assisted fields. Neither tool contains an API key. Instead they call a small serverless proxy hosted on a separate Netlify site named harland-proxy. That proxy holds the single Anthropic API key as a server-side secret and is the only place the key lives. The browser tools never see it. The proxy also restricts which origins may call it, so only the GitHub Pages site above can reach it.

The tools and the proxy are kept apart on purpose. GitHub Pages hosts the static tools and cannot run server code, so a key placed here would be visible in the page source. The Netlify proxy runs the server code and keeps the key out of the public files. The model the proxy uses is chosen server-side inside the proxy, so it can change without touching any tool.

## How to update a tool

1. Replace that tool's index.html with the new version. For the notes generator that file is notes-generator/index.html, and for the completion generator it is completion-generator/index.html.
2. Commit to main.
3. GitHub Pages redeploys automatically within a minute or two. There is no build step.

Every updated file from Phil arrives with its own expected md5. Verify the committed file matches that hash before you push, so the integrity check stays meaningful.

## Shared-computer note

These tools save your drafts in the browser on the device you are using. On a shared computer, use the tool's Clear all or Reset control before you leave, so the next person does not see your drafts.

## Hosting

The tools are served by GitHub Pages from the main branch at the root path. The AI features are served by the separate harland-proxy site on Netlify. The repo is public, which is required for free GitHub Pages and is safe here because the tools contain no secrets and no student data. The Anthropic API key is never stored in this repo. It lives only as an environment variable on the Netlify proxy.
