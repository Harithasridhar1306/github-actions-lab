# GitHub Actions Lab

**Learn GitHub Actions by building, breaking, debugging, and understanding workflows.**

GitHub Actions Lab is an open, practical learning playground for engineers who want to go beyond copying YAML. It focuses on understanding how workflows execute, how failures happen, and how to debug them.

## What is here?

- **Learning path** — short, focused lessons from workflow foundations to security and production debugging
- **Interactive labs** — predict what happens, break a workflow, and diagnose the failure
- **Challenge Arena** — scenario-based CI/CD problems rather than syntax memorization
- **Dynamic content** — lessons, challenges, and references are served from Supabase rather than hardcoded into the public site
- **Analytics dashboard** — admin-only usage insights for lessons, challenges, sessions, and optional visitor names
- **Cheatsheet** — quick reference for everyday GitHub Actions work

## Learning path

1. Workflow foundations
2. Execution and dependencies
3. Expressions and contexts
4. Matrix strategies, artifacts and caching
5. Reusable workflows
6. Environments and deployments
7. Security and OIDC
8. Production debugging

## Design principle

The lab is intentionally **learn-by-doing**.

Every topic should answer three questions:

> What do I write?  
> What does GitHub actually do with it?  
> How do I debug it when it breaks?

The interactive labs follow a simple model:

**Predict → Break → Debug**

The goal is not just to recognize valid YAML, but to build a mental model of workflow execution and develop the habit of debugging from evidence.

## Architecture

The public interface is hosted on GitHub Pages.

Supabase provides the backend layer:

- PostgreSQL stores lessons, challenges, references, and analytics events
- Edge Functions serve dynamic content and challenge data
- Supabase Auth protects the admin dashboard
- The admin allowlist controls access to analytics
- Privileged database credentials remain server-side

The browser only receives the data required to render the learning experience. Secrets and service-role credentials are not stored in the repository.

## Run locally

The public site is a static frontend. You can open `index.html` in a browser or serve the repository with any static HTTP server.

The deployed site uses the configured Supabase Edge Functions for dynamic lessons, challenges, and analytics.

## GitHub Pages

The repository includes a GitHub Actions workflow under `.github/workflows/deploy-pages.yml` that publishes the site to GitHub Pages.

Enable Pages in **Settings → Pages → Build and deployment → Source: GitHub Actions** if it is not already enabled for the repository.

## Analytics and privacy

The site collects basic usage events such as page views, lesson starts, lesson completions, and challenge attempts.

Visitor names are optional. The analytics system does not intentionally collect email addresses or IP addresses as part of the learning experience.

Analytics data is available only through the authenticated admin dashboard.


Built with GitHub Pages, GitHub Actions, and Supabase.
