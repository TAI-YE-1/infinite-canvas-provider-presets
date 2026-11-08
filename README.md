# Infinite Canvas provider presets

Public, read-only distribution of reviewed model operation configurations.
No application source, provider accounts, API keys or signing private keys are published here.

- stable/: current signed client package (manifest, signature and model payload).
- releases/: immutable copies for inspection. Clients reject sequence rollback.
- public-key.json: public verification identity; clients trust only keys shipped with their application.
- catalog-reference.json: dated platform and CNY pricing references from the application catalog.
  This reference file is not a signed update payload and is not automatically applied by clients.
  Prices remain editable drafts and require explicit administrator publication.

The initial signed package contains 14 operation configurations covering Volcano, Bailian, MiniMax and DeepSeek.
It includes Bailian MiniMax H3 and the controlled MiniMax voice-clone configuration.
Downloading or verifying a package never installs a model, replaces administrator configuration,
publishes prices, grants billing admission or calls a paid model.
The application previews differences and requires explicit confirmation before applying configuration.

Publishing: use the application's existing scripts/build_provider_preset_release.py with the
maintainer's offline Ed25519 key. Increase sequence monotonically, preserve immutable archives,
review official model/API/pricing changes, and replace the three stable files in one commit.
Renew before the manifest expires; expired packages are rejected while installed configuration is preserved.
Never put the signing private key in Git or in provider configuration.

Format 2 (sequences 2, 3 and 4) includes 13 signed CNY request-price references alongside the 14 model configurations. References use reviewed official peak/list prices, with editable drafts and existing V3 billing contracts. Existing builtin-installed models can use new reference data; unknown model IDs need no catalog code change when their protocol and billing contracts are already supported. Refreshing data does not change runtime configuration, publish prices, open models or charge wallets. Existing selling prices require explicit administrator confirmation and publication before changing.

Applications must support package format 2 to read price references. Older applications reject the new format and retain installed configuration; the immutable format-1 release remains available under releases/2026-11-07.1/. The unsigned catalog-reference.json remains a human reference, not a trusted client update payload. MiniMax voice-clone lifecycle fees remain separate from request-price references.

Sequence 3 adds the reviewed Seedream 1K/1.5K/2K size configuration. It requires application compatibility baseline 2026.11.07.01 or newer, which supports two-character resolution tiers. Update the application before accepting this data; older applications reject the package and retain installed configuration. Sequence 2 is archived under releases/2026-11-07.2/. New sizes require explicit configuration preview and administrator confirmation; refreshing data does not change installed models.

Sequence 4 switches the four reviewed Bailian image presets to the official native synchronous API. It requires application compatibility baseline 2026.11.08.01 or newer. No workspace ID is required for the default Beijing public endpoint. Existing compatible-mode bindings and custom models remain supported; changes still require administrator preview and confirmation. Prices and all other templates are unchanged. Sequence 3 remains archived under releases/2026-11-07.3/.
