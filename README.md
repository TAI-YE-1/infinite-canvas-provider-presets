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
