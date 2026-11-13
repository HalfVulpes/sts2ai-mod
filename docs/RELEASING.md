# Releasing

A release is a git tag `vX.Y`, plus a GitHub release with the mod zip and `SHA256SUMS`.

1. **Policies.** Put the files the mod expects in one folder: `model_<character>.bin` for each character, and
   `model.bin` (the default; the release uses the Defect policy). Every policy must have been evaluated on held-out
   seeds with the same simulator build as the game version the release supports.
2. **Version.** Set `"version"` in `mod/sts2ai.json` (for example `1.2.0`). The packer names the zip after it
   (`sts2ai-mod-v1.2.zip`) and stamps the DLL with it.
3. **Docs.** Update `CHANGELOG.md` (game version, what changed, numbers) and the README table and chart
   (`docs/winrate-*.svg`).
4. **Commit and tag**, then build from the tagged commit, so the DLL records it:

   ```
   git tag -a v1.2 -m "STS2 AI v1.2"
   tools/pack_release_mod.sh <policies folder> "" "<game folder>"
   (cd dist && sha256sum sts2ai-mod-v1.2.zip > SHA256SUMS)
   ```

5. **Check before publishing.**
   - Run `tools/install_release_mod.sh dist/sts2ai-mod-v1.2.zip "<game folder>"` on a copy of the game.
   - The zip must not contain game files or the vocabulary. The packer refuses them; `unzip -l` to confirm.
   - Run a secret scan over the tree: no keys, tokens, emails or machine paths.
6. **Publish.** Push the branch and tag, then create the release with the zip and `SHA256SUMS`, and attach the
   release notes (the CHANGELOG entry).
