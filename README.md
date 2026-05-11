# Spatio TypeScript SDK

The official TypeScript client for the [SpatioAPI](https://www.spatio.app/developers). Notes, sheets, slides, tasks, mail, calendar, channels, DMs, files, contacts, repos, agents, and federated search. From any Node, Bun, Deno, or browser runtime.

```bash
npm install @spatio/sdk-ts
```

```ts
import { Configuration, NotesApi } from "@spatio/sdk-ts";

const notes = new NotesApi(
  new Configuration({
    basePath: "https://api.spatio.app",
    accessToken: process.env.SPATIO_PAT,
  }),
);

const envelope = await notes.listNotes();
console.log(envelope.items);
```

## Authentication

Two paths.

**Personal Access Token.** Mint one at *Settings → Tokens* in [Spatio Desktop](https://www.spatio.app) and pass it as `accessToken`. The right choice for scripts, automations, and your own backend services.

**OAuth 2.1 + OpenID Connect.** Build a "Sign in with Spatio" flow for your own product. The OIDC discovery document at [`/.well-known/openid-configuration`](https://api.spatio.app/.well-known/openid-configuration) drops into NextAuth, Auth.js, oidc-client-ts, passport-openidconnect, and every other conformant RP library.

## What you can build

Spatio's API is designed to be the substrate someone could build their own Spatio Desktop on top of. See [CLONE-PARITY.md](https://github.com/spatio-labs/spatio/blob/main/packages/api-spec/CLONE-PARITY.md) for the full surface: realtime collaboration via Yjs, federated cross-platform search, OAuth 2.1 dynamic client registration, self-hosted agent runtime.

## Links

- [SpatioAPI reference](https://www.spatio.app/developers/docs/api)
- [OpenAPI spec](https://api.spatio.app/openapi.json)
- [Clone parity guide](https://github.com/spatio-labs/spatio/blob/main/packages/api-spec/CLONE-PARITY.md)
- [Spatio on the web](https://www.spatio.app)

## About this package

Generated from the SpatioAPI OpenAPI spec on every release. Source mirrored from the [spatio-labs/spatio](https://github.com/spatio-labs/spatio) monorepo: PRs against generated files will be overwritten by the next release. File issues here; open spec changes against the upstream repo.

Licensed under [MIT](LICENSE).
