# NajdPulse Tracker CDN

**Public hosting repository for NajdPulse tracker artifacts.**

This repository contains only the built tracker.js file for distribution via GitHub Pages. The source code is maintained in a private repository.

## 🔗 CDN URLs

- **Latest (auto-updates):** https://AbubakerSallam.github.io/najdpulse-tracker-cdn/tracker.js
- **Pinned version:** https://AbubakerSallam.github.io/najdpulse-tracker-cdn/tracker.vX.Y.Z.js

## 📝 Installation in Salla

Add this snippet to your Salla store's **Custom Code** section:

**Location:** Theme Settings → Custom Code → Header Scripts (Before `</head>`)

```html
<script>
  window.__NAJDPULSE_CONTEXT__ = {
    store: { 
      id: "{{ store.id }}", 
      domain: "{{ store.domain }}", 
      username: "{{ store.username }}" 
    },
    customer: { 
      id: "{{ customer.id }}", 
      name: "{{ customer.name }}" 
    }
  };
</script>
<script defer src="https://AbubakerSallam.github.io/najdpulse-tracker-cdn/tracker.js"></script>
```

The Salla template variables (`{{ store.id }}`, etc.) will be automatically replaced when your store renders.

## 🎯 Version Pinning

To use a specific version instead of auto-updating:

```html
<script defer src="https://AbubakerSallam.github.io/najdpulse-tracker-cdn/tracker.v1.0.0.js"></script>
```

## 🚀 Publishing Process

This repository is automatically updated from the private monorepo:

1. Developer tags a release in the private repo: `git tag v1.0.0 && git push --tags`
2. GitHub Actions builds the tracker
3. Security scan checks for leaked secrets
4. Artifacts are pushed to this public repo
5. GitHub Pages deployment is triggered automatically

## 📦 Repository Contents

```
/pages/
  ├── tracker.js              # Latest version (overwritten on each release)
  ├── tracker.vX.Y.Z.js       # Pinned versions (never overwritten)
  └── index.html              # Landing page with file listing
```

## 🔒 Security

- This repository contains ONLY built artifacts
- All source code remains in the private monorepo
- Automated scans prevent secret leakage
- No API keys, credentials, or sensitive data are published

## 📊 Version History

See [Releases](https://github.com/AbubakerSallam/najdpulse-tracker-cdn/releases) for version history and changelogs.

## 🆘 Support

For issues with the tracker, please contact the NajdPulse development team.

---

**NajdPulse** — AI Sales Assistant & Store Intelligence for Salla
