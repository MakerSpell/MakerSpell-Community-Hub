# 🤖 AI Agent Documentation Governance Rule

> **MANDATORY POLICY FOR ALL AI ASSISTANTS:**  
> (Antigravity, Claude, Cursor, Windsurf, Command Code, Copilot, ChatGPT)

---

## 📌 1. Policy Definition: Zero Code Leakage & User-First

Whenever a new feature, screen, widget, or capability is added or modified in the Flutter app (`makersync_app`) or Web platform (`web/`), the agent **MUST** document it in **`community-hub/docs/`**.

### ⚠️ STRICT CONFIDENTIALITY & USER-GUIDE RULE:
- **NO PROPRIETARY SOURCE CODE IN DOCS:** Documentation pages must NEVER contain internal Dart classes, TypeScript implementations, internal methods, or proprietary architecture details.
- **USER GUIDE / HOW-TO FORMAT ONLY:** Guides must focus exclusively on step-by-step instructions for end users (buttons to click, options to configure, visual workflows).
- **MULTILINGUAL SYNCHRONIZATION:** Update both `en/` and `tr/` trees and keep `docs/manifest.json` fully synchronized.

---

## 📌 2. Verification Checklist

1. **Target the Right Folder:**
   - App screens -> `community-hub/docs/<lang>/app-guide/`
   - Web pages -> `community-hub/docs/<lang>/web-guide/`
   - Hardware -> `community-hub/docs/<lang>/printers/`
2. **Capture Screenshots:**
   - Run `tools/capture-web-screenshots.mjs` (Web) or `flutter test test/doc_screenshot_test.dart` (Flutter).
   - Save to `community-hub/docs/assets/screenshots/<category>/`.
   - Embed the image using `![Description](../../assets/screenshots/...)`.
3. **Update Manifest:**
   - Register new slugs and titles in `community-hub/docs/manifest.json`.
4. **Log Changes:**
   - Append notes to `MakerSpell-Vault/agents/antigravity_printer_connection_interface_logs.md`.
