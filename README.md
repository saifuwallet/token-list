## ⚠️ This is a fork off @solana/spl-token-registry

Use the original here: https://github.com/solana-labs/token-list

This fork solves the problem that token-list imports a huge JSON file with `import`, causing webpack to inline and import it.

This fork does not `import` the JSON file, instead it expects that you pass a `fallbackUrl` into the resolve method:

```typescript
await new TokenListProvider().resolve(Strategy.CDN, tokenListLocalUrl)
```

so, no automatic inclusion of the token list, you'll have to specify yourself where it should fallback to
