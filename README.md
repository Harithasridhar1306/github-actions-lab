# ⚡ GitHub Actions Lab

**Learn GitHub Actions by building, breaking, debugging, and understanding workflows.**

GitHub Actions Lab is an open, practical learning playground for engineers who want to go beyond copying YAML. It combines a concise cheatsheet, interactive challenges, workflow visualization, and an AI-ready tutor experience.

## What is here?

- 📚 **Learning path** — foundations → production patterns → security
- 🧪 **Challenges** — solve real CI/CD problems instead of memorizing syntax
- 🐛 **Broken workflows** — diagnose common GHA failures
- 🧠 **Explain my workflow** — turn YAML into a visual execution model
- ⚡ **Cheatsheet** — quick reference for everyday GitHub Actions work
- 🤖 **AI Tutor** — guided hints and an AI prompt mode without exposing an API key in the browser

## Learning path

1. Workflows, events, jobs and steps
2. Contexts, expressions, variables and secrets
3. Dependencies, conditions and outputs
4. Matrix strategies, artifacts and caching
5. Environments, concurrency and deployments
6. Reusable workflows and composite actions
7. Permissions and GitHub Actions security
8. OIDC and cloud authentication
9. Self-hosted runners and production patterns
10. Troubleshooting and incident-style challenges

## Design principle

The lab is intentionally **learn-by-doing**. Every topic should answer three questions:

> What do I write?  
> What does GitHub actually do with it?  
> How do I debug it when it breaks?

## Run locally

This is a static site. Open `index.html` in a browser, or serve the repository with any static HTTP server.

## GitHub Pages

The repository includes a GitHub Actions workflow under `.github/workflows/deploy-pages.yml` that publishes the site to GitHub Pages.

Enable Pages in **Settings → Pages → Build and deployment → Source: GitHub Actions** if it is not already enabled for the repository.

## AI architecture

The public site does **not** contain an AI API key. The current tutor includes deterministic hints and an AI-prompt mode. A future server-side endpoint can power provider-backed analysis while keeping credentials off the client.

## Contributing

Found a better explanation, a broken workflow, or a useful challenge? Open a pull request. The goal is to make this a practical community resource.

---

Built with GitHub Pages + GitHub Actions. ⚡