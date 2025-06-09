<a href="https://registry-starter.vercel.app/">
  <h1 align="center">Registry Starter</h1>
</a>

<p align="center">
    Registry Starter is a free, open-source template built with Next.js and the Shadcn/ui Registries that helps you quickly build an AI-Native Design System Implementation.
</p>

<p align="center">
  <a href="#deploy-your-own"><strong>Deploy Your Own</strong></a> ·
  <a href="#open-in-v0"><strong>Open in v0</strong></a> ·
  <a href="#theming"><strong>Theming</strong></a> ·
  <a href="#running-locally"><strong>Running Locally</strong></a> ·
  <a href="#file-structure"><strong>File Structure</strong></a> ·
  <a href="https://ui.shadcn.com/docs/registry"><strong>Read Docs</strong></a>
</p>
<br/>

## Deploy Your Own

You can deploy your own version of the Next.js Registry Starter to Vercel with one click:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fwillsather%2Fregistry-starter&project-name=my-registry&repository-name=my-registry-starter&demo-title=Registry%20Starter&demo-description=An%20Open-Source%20Registry%20Starter%20Built%20With%20Next.js%20and%20Shadcn%2Fui%20Registries%20by%20Vercel&demo-url=https%3A%2F%2Fregistry-starter.vercel.app)


## Open in v0

[![Open in v0](https://v0.dev/chat-static/button.svg)](https://v0.dev/chat/api/open?title=Dashboard+Kit&prompt=These+are+existing+design+system+styles+and+files.+Please+utilize+them+alongside+base+components+to+build.&url=https%3A%2F%2Fregistry-starter.vercel.app%2Fr%2Fdashboard.json)

This registry application also exposes `Open in v0` buttons for each component. Once this application is deployed, the
`Open in v0` button redirects to [`v0.dev`](https://v0.dev) with a prepopulated prompt and a URL pointing back to this
registry's `/r/${component_name}.json` endpoint. This endpoint will provide v0 the necessary file information, content,
and metadata to start your v0 chat with your component, theme, and other related code.

These `/r/${component_name}.json` files are generated using `shadcn/ui` during the `build` and `dev` based on the
repository's [`registry.json`](./registry.json). For more information, refer to the
[documentation](https://ui.shadcn.com/docs/registry/registry-json).

## Theming

To use a custom theme for all the components, all you need to do is modify the CSS tokens in
[`tokens.css`](./src/app/tokens.css). More information on these practices can be found
on [ui.shadcn.com/docs](https://ui.shadcn.com/docs).

To use custom fonts, you can either use [`next/font/google`](https://nextjs.org/docs/pages/getting-started/fonts#google-fonts) or the [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face) CSS rule. 

## Running locally

1. Install Vercel CLI: `npm i -g vercel`
2. Link local instance with Vercel and GitHub accounts (creates `.vercel` directory): `vercel link`
3. Download your environment variables: `vercel env pull`

```bash
pnpm install
pnpm dev
```

Your app should now be running on [localhost:3000](http://localhost:3000).

## Testing your registry locally

To test your registry with the "Open in v0" functionality locally, you can use tools like [Local Tunnel](https://theboroer.github.io/localtunnel-www/) or [Ngrok](https://ngrok.com/docs/getting-started/) to expose your local development server to the internet. This will provide you with a temporary URL that can be used as the `baseUrl` for testing.

### Using Local Tunnel

1. Install Local Tunnel globally:

    ```bash
    npm install -g localtunnel
    ```

2. Start your local development server:

    ```bash
    pnpm dev
    ```

3. In a new terminal, run Local Tunnel to expose your local server:

    ```bash
    lt --port 3000
    ```

4. Local Tunnel will provide you with a URL. Use this URL as the `baseUrl` in your application to test the "Open in v0" functionality.

### Using Ngrok

1. Download and install Ngrok from [ngrok.com](https://ngrok.com/).

2. Start your local development server:

    ```bash
    pnpm dev
    ```

3. In a new terminal, run Ngrok to expose your local server:

    ```bash
    ngrok http 3000
    ```

4. Ngrok will provide you with a forwarding URL. Use this URL as the `baseUrl` in your application to test the "Open in v0" functionality.

By using either Local Tunnel or Ngrok, you can easily test the integration of your components with v0.dev by providing a publicly accessible URL for your local development environment.

## File Structure

`app/(design)` routes contains the registry pages.

`app/starter` routes contains both `store` and `dashboard` full starter pages

`@/components` contains all compound components

`@/components/ui` contains all base `shadcn/ui` components

`@/hooks` contains all React hooks

`@/lib` contains all business logic & utils