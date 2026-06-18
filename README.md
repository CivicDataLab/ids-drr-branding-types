# IDS-DRR Branding Types

TypeScript type definitions for the [IDS-DRR](https://github.com/CivicDataLab/IDS-DRR-Frontend) branding-package contract.

## Install

```bash
npm install github:CivicDataLab/ids-drr-branding-types
```

This package is not published to the npm registry (`"private": true` in `package.json`). The frontend depends on it from GitHub the same way.

## Usage

Use `import type` only. A branding package exports named bindings that satisfy `Exports`.

Follow the pattern in the frontend `[branding-stub](https://github.com/CivicDataLab/IDS-DRR-Frontend/blob/dev/branding-stub/src/index.ts)`:

```ts
import type { Exports } from 'ids-drr-branding-types';

export const config: Exports['config'] = {
  states: [
    {
      name: 'Example State',
      slug: 'example-state',
      icon: { src: '/icon.png', width: 64, height: 64 },
      status: 'active',
    },
  ],
};

export const AboutPage: Exports['AboutPage'] = undefined;
export const IntroSection: Exports['IntroSection'] = undefined;
export const OutroSection: Exports['OutroSection'] = undefined;
export const Footer: Exports['Footer'] = undefined;
export const Credits: Exports['Credits'] = undefined;
export const PartnerLogos: Exports['PartnerLogos'] = undefined;
```

The frontend imports the branding package as `ids-drr-branding` and checks conformance against `Exports` in `[config/branding.ts](https://github.com/CivicDataLab/IDS-DRR-Frontend/blob/dev/config/branding.ts)`.

## Types

All types are defined in `[src/index.ts](src/index.ts)`. Field-level documentation is in the comment above each property in that file.

Exported types:

- `StaticImageAsset`
- `State`
- `TileLayer`
- `TileLayers`
- `Resource`
- `Story`
- `Language`
- `Features`
- `GlossaryTerm`
- `DeploymentConfig` — main configuration object (`config` in `Exports`)
- `Exports` — required `config` plus optional React components: `AboutPage`, `IntroSection`, `OutroSection`, `Footer`, `Credits`, `PartnerLogos`

## License

GNU Affero General Public License v3.0 (AGPL-3.0). See [LICENSE](LICENSE).