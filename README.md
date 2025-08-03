# Faceless Content Machine

This monorepo houses the **Faceless Content Machine (FCM)**, an application designed to help creators produce engaging short-form videos quickly. FCM automates the process of converting text scripts into dynamic video content, complete with AI voiceovers, animated captions, and background music, ready for platforms like TikTok, Reels, and Shorts.

Built with Turborepo, this project includes:

## Apps and Packages

*   `apps/api`: The Python backend for core functionalities like script parsing and video generation.
*   `apps/web`: The Next.js frontend for the user interface.
*   `packages/core`: Shared Python utilities.
*   `packages/lib`: Shared TypeScript utilities.
*   `packages/ui`: A shared React component library.
*   `packages/eslint-config`: ESLint configurations.
*   `packages/typescript-config`: TypeScript configurations.

## Development

*   **Build all:** `turbo build`
*   **Develop all:** `turbo dev`
*   **Develop specific app (e.g., web):** `turbo dev --filter=web`

## Utilities

*   [TypeScript](https://www.typescriptlang.org/) for static type checking
*   [ESLint](https://eslint.org/) for code linting
*   [Prettier](https://prettier.io) for code formatting

## Remote Caching

This Turborepo supports [Remote Caching](https://turborepo.com/docs/core-concepts/remote-caching) for faster builds. You can link your Turborepo to a Vercel account for shared build caches:

*   `turbo login`
*   `turbo link`

For more details on Turborepo features, refer to the [Turborepo documentation](https://turborepo.com/docs).