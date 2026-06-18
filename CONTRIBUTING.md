# Contributing to MTD-HX

Thank you for your interest in improving MTD-HX. This is a community-driven methodology framework, and contributions of all kinds are welcome.

---

## Types of Contributions

### Templates
- Add new templates for additional phases or sub-phases
- Improve existing templates with better examples or clearer instructions
- Add translations of templates to other languages

### Translations
- Spanish is the primary language; English is the secondary
- We welcome translations to Portuguese, French, German, and other languages
- Translation files should follow the same structure: `docs/{lang}/` and template files should include `({lang})` in their headers

### Documentation
- Fix typos, broken links, or unclear explanations
- Add diagrams, flowcharts, or visual aids
- Expand the methodology guide with real-world examples

### Legal Framework
- Add legal mappings for other jurisdictions (Argentina, Mexico, Spain, EU GDPR, etc.)
- Update existing legal references when legislation changes

---

## How to Contribute

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-feature-name`
3. Make your changes following the project conventions:
   - YAML frontmatter on all templates
   - Bilingual where possible (Spanish primary, English secondary)
   - Professional tone — readable by a CISO in 5 minutes
   - No placeholder text — use realistic fictional examples
4. Test: verify your file renders correctly as Markdown
5. Commit: `git commit -m "feat: add [description]"`
6. Push: `git push origin feature/your-feature-name`
7. Open a Pull Request

---

## Style Guide

- **Markdown:** GitHub Flavored Markdown
- **Frontmatter:** YAML enclosed in `---`, placed at the very top of each template
- **Language priority:** Spanish first, English second (e.g., `## 3.1 Hypothesis Statement / Enunciado de la hipótesis`)
- **Version:** Always reference `mtd_hx_version: "2.0"` in frontmatter
- **Filenames:** English lowercase with hyphens (`01-scope.md`)
- **No placeholders:** Replace `[INSERT HERE]` with realistic examples

## Code of Conduct

Be respectful, constructive, and inclusive. This project is for educational and research purposes — no toxicity, no gatekeeping.
