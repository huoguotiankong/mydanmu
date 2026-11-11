# Vercel deployment notes for this fork

- Deploy GitHub repository `huoguotiankong/mydanmu`, production branch `main`.
- Keep the upstream project's `vercel.json` unchanged; its Node.js function is the API entry point.
- Configure `TOKEN` and `ADMIN_TOKEN` as different protected Vercel environment variables (Production and Preview). Never commit their values.
- The GitHub Actions `Safe Upstream Sync` workflow checks upstream daily and pushes tested updates to `main`. A linked Vercel project should automatically deploy each pushed commit.
- Serverless instances do not guarantee persistent local storage. Consider an external Redis service for persistent favorites and history.
- Check deployment logs and the `/api/v2/search/anime?keyword=...` route after upgrades; a successful build alone does not establish that external source fetches work.

This file documents the fork's deployment arrangement and can be used to trigger the initial Git push deployment without altering application code.
