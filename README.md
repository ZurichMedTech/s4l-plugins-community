# Sim4Life Plugin Community Store

Welcome to the **Sim4Life Plugin Community Store**!
This repository serves as the index for third-party plugins that can be discovered, installed, and managed within the Sim4Life platform.

If you are a developer and would like to publish your plugin to the community, please follow the steps below.

---

## 🔌 How to Publish Your Plugin

To publish a plugin to the Sim4Life Community Store:

1. **Create a Git repository** for your plugin (self-hosted or on any public Git server).
2. **Ensure your plugin includes a `manifest.json`** in its root directory (see details below).
3. **Add a valid icon image** in `integration/simulator_icon.png` (or equivalent relative path).
4. **Tag your releases** using semantic versioning (`v1.0.0`, `v1.1.0`, etc.). See [Versioning](#-versioning--changelog) below.
5. **Open a Merge Request** against this repository:

   * Edit the `integration` file.
   * Add your plugin’s Git URL (as a string) to the JSON array.
   * Submit your Merge Request (MR) for review.

---

## 📦 `manifest.json` Specification

Your plugin must include a file named `manifest.json` in its root directory with the following fields:

| Field          | Required | Description                                                                               |
| -------------- | -------- | ----------------------------------------------------------------------------------------- |
| `icon`         | ✅       | Relative path to an icon image (e.g., `integration/simulator_icon.png`). Used in the UI.  |
| `title`        | ✅       | Display name of the plugin. Shown in the marketplace UI.                                  |
| `description`  | ✅       | Short explanation of the plugin’s purpose. Shown in the UI.                               |
| `version`      | ✅       | Current plugin version. Should match your Git tag or release version.                     |
| `sim4life`     | ✅       | Minimum compatible Sim4Life version (e.g., `9.0.0`).                                      |
| `author`       | ✅       | Your full name or organization name.                                                      |
| `author_email` | ✅       | Contact email address for support/questions.                                              |
| `details`      | ✅       | Path to a local file (e.g., `README.md`) containing long-form documentation.              |
| `license`      | ✅       | Path to the license file (e.g., `LICENSE`).                                               |
| `tags`         |          | Array of tags or keywords (e.g., `["Heat Equation", "Thermodynamics"]`).                  |
| `links`        |          | Dictionary of external links. Recommended keys: `repository`, `website`, `documentation`. |

### 🔍 Example

```json
{
  "icon": "integration/simulator_icon.png",
  "title": "Heat Conduction Simulator",
  "description": "Solves the heat equation in arbitrary 3D domains.",
  "version": "1.0.0",
  "sim4life": "9.0.0",
  "author": "Jane Doe",
  "author_email": "jane.doe@example.com",
  "details": "README.md",
  "license": "LICENSE",
  "tags": ["Heat Equation", "Thermodynamics"],
  "links": {
    "repository": "https://git.speag.com/oSparc/s4l-plugins/heat-conduction",
    "website": "https://example.com/heat-sim",
    "documentation": "https://example.com/heat-sim/docs"
  }
}
```

---

## 🔖 Versioning & Changelog

* Plugin versions are based on **Git tags** in your plugin repository (e.g., `v1.0.0`, `v1.1.2`).
* The version defined in your `manifest.json` must match the corresponding Git tag.
* The latest Git tag is used to determine the **currently installable version** in the marketplace.
* Tags are also used to **generate changelogs** automatically by comparing releases (e.g., based on release notes or commit diffs).

### Example

```bash
git tag v1.2.0
git push origin v1.2.0
```

If your changelog is derived from GitHub releases, make sure to **include a release message** when publishing a tag.

---

## 📅 Plugin Review Process

Once you submit your merge request:

* We will verify that the repository is accessible and contains a valid `manifest.json`.
* We will validate the presence of a plugin icon and required metadata fields.
* We will confirm that the version in `manifest.json` matches a Git tag.
* If everything looks good, your plugin will be added to the community store!

---

## 📜 Additional Resources

* [Sim4Life Plugin Development Guide](https://yourdocs.example.com)
* [Example Plugin Template](https://git.speag.com/oSparc/s4l-plugins/plugin-cookiecutter)

---

Happy coding! 🎉
— The Sim4Life Plugin Team
