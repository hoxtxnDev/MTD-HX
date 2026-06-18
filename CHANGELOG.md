# Changelog

All notable changes to MTD-HX are documented here.

The format is based on [Keep a Changelog](https://keepachangelog.com/),
and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [v2.0.0] — 2026-06-18

### Added
- Full MITRE ATT&CK mapping in hypothesis (Phase 3) and taxonomy (Phase 4) templates with tactic, technique, sub-technique, and detection data source fields
- CVSS 4.0 scoring table in risk template (Phase 5) with all Base metrics (AV/AC/AT/PR/UI/VC/VI/VA/SC/SI/SA), numeric score, and qualitative label
- YAML frontmatter standard on all 8 templates (`mtd_hx_version`, `phase`, `case_id`, `author`, `status`, `mitre_tactics`, `cvss_version`, `legal_framework`)
- Chilean legal template (Phase 7) mapping to specific articles: Ley 19.628 Art. 23, Ley 21.663 Art. 8, CSIRT 72h reporting, PDI referral criteria
- Stakeholder matrix in recommendations template (Phase 6) targeting CISO, Developer, Legal Counsel, and Executive roles
- Bilingual report template (Phase 8) with executive summary, technical body, appendices, and integrity declaration
- SECURITY.md with responsible disclosure policy
- CONTRIBUTING.md with guidelines for template and translation contributions
- Badges in README: version badge, MIT license badge, language badge (ES/EN)
- Mermaid flow diagram visualizing the 8-phase methodology pipeline
- Quick Start section with a 3-step walkthrough using the Clínica Dávila case
- Comparison table positioning MTD-HX vs PTES vs OWASP Testing Guide
- `docs/en/methodology.md` updated with MITRE ATT&CK integration guidance

### Changed
- Bumped version from v1.0.0 → v2.0.0 across all files
- README.md completely modernized with professional tone, badges, and navigation
- README.es.md synchronized as a full Spanish mirror of the new README (previously was a shorter translation)
- All 8 templates upgraded from placeholder fields to realistic fictional examples based on the Clínica Dávila data breach case
- Template footers updated: `MTD-HX v2 — Cybersecurity Research Framework by hoxtxnDev`
- `.gitignore` updated with additional OS and editor patterns

### Fixed
- Template path references in README now point to correct filenames under `templates/`
- Consistent bilingual structure (Spanish primary, English secondary) across all templates

---

## [v1.0.0] — 2026-05-03

### Added
- Initial 8-phase methodology framework
- Template files for all phases (01-scope through 08-report)
- English and Spanish documentation in `docs/en/` and `docs/es/`
- Bilingual README (English + Spanish)
- Ethical principles and legal grounding sections
- Clínica Dávila case study as applied validation
