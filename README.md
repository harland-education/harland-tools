# Harland Tools

Internal teacher tools for Harland Education. A small, static collection of single-file browser utilities that teachers can open from any computer or phone. No login, no server, no student data leaves the device. Every tool stores its drafts in the browser's localStorage on the device it runs on.

## Live URLs

- Landing page: https://harland-education.github.io/harland-tools/
- Class Notes Generator: https://harland-education.github.io/harland-tools/notes-generator/

## Tools

### Class Notes Generator (`/notes-generator/`)

Generates standard-format class notes in App and LINE formats. It is a single self-contained HTML file with one external dependency, Google Fonts. All teacher input stays in the browser via localStorage.

## How to update a tool

1. Replace the tool's file (for the notes generator, that is `notes-generator/index.html`) with the new version.
2. Commit and push to `main`.
3. GitHub Pages redeploys automatically within a minute or two. No build step.

Every updated file from Phil arrives with a new expected md5. Verify the committed file matches that hash before pushing, so the integrity check stays meaningful.

## Shared-computer note

These tools save drafts in the browser's localStorage. On a shared computer, use the tool's Clear all control before you leave so the next person does not see your drafts.

## Hosting

Served by GitHub Pages from the `main` branch, root path. The repo is public, which is required for free GitHub Pages and is safe here because the tools contain no secrets and no student data.
