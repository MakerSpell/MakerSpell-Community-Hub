# Contributing to MakerSpell Community Hub

Thank you for your interest in contributing to the MakerSpell ecosystem! We welcome community contributions for printer hardware profiles, documentation improvements, and bug fixes.

## Contribution Guidelines

1. **Safety First:**
   - Any printer integration for hardware not in the verified bench test suite (Creality K1, Snapmaker U1) must define `safeModeOnly: true`.
   - Never implement automatic heating or head movement without explicit user initiation on community hardware.

2. **JSON Profile Standards:**
   - Profiles must follow strict semantic schema validation.
   - Bed sizes must reflect true physical limits (mm).
   - Maximum temperatures must not exceed manufacturer safety specifications.

3. **Submitting Changes:**
   - Create a feature branch: `git checkout -b feature/my-printer-profile`
   - Commit your changes with conventional commit messages: `feat(printers): add Anycubic Kobra 3 profile`
   - Open a Pull Request against `main`.

Thank you for helping build an open, multi-brand 3D printing ecosystem!
