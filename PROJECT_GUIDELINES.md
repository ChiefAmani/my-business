# PROJECT_GUIDELINES.md

## Project Overview
This document establishes the foundational guidelines for the "My Business — Autonomous Improvement Engine" project, a hybrid initiative encompassing both code development and extensive documentation. Its purpose is to ensure consistency, facilitate collaboration, and mitigate risks associated with revision control and file management across all project artifacts. This serves as the single authoritative contract for these operational aspects.

## Version Control Strategy

### 1. Git Branching Model
- **Model:** Adopt a simplified GitHub Flow or Trunk-Based Development approach.
- **Main Branch:** `main` branch is the single source of truth, always deployable.
- **Feature Branches:** All new development (code or significant document changes) occurs on short-lived feature branches.
  - Naming: `feature/descriptive-name` or `bugfix/issue-id`.
  - Merge: Feature branches are merged into `main` via Pull Requests (PRs) after review and approval.
- **Commit Messages:**
  - Format: `Type: Subject line (max 50 chars)`
  - Body: (Optional) More detailed explanation, if necessary.
  - Types: `feat`, `fix`, `docs`, `style`, `refactor`, `test`, `chore`.
  - Example: `feat: Add user authentication endpoint`

### 2. Pull Request (PR) Workflow
- **Purpose:** Facilitate code and document review, ensure quality, and maintain `main` branch integrity.
- **Requirements:**
  - At least one approved review.
  - All automated checks (if applicable) must pass.
- **Merging:** Use 'Squash and Merge' or 'Rebase and Merge' to maintain a clean `main` branch history.

## File Naming Conventions

### 1. General Principles
- **Case:** Use `kebab-case` (lowercase, hyphens for spaces) for all file and directory names.
- **Descriptive:** Names should clearly indicate content or purpose.
- **Avoid:** Spaces, special characters (except hyphens), version numbers (e.g., `v1`, `final`) in file names themselves (Git handles versioning).

### 2. Code Files
- **Modules/Components:** `module-name.py`, `component-name.js`.
- **Tests:** `test_module-name.py`.

### 3. Documentation Files
- **Markdown:** `document-title.md`.
- **Images:** `image-description.png`, `diagram-name.svg`.
- **Data Files:** `data-set-name.json`, `report-name.csv`.

## Project Directory Structure

### 1. Top-Level Structure
- `src/`: All source code (backend, frontend, scripts).
- `docs/`: All project documentation (specifications, guides, reports).
- `assets/`: Static assets (images, media, design files).
- `config/`: Configuration files (environment variables, settings).
- `tests/`: All test files.
- `.github/`: GitHub-specific workflows and templates.
- `.gitignore`: Specifies intentionally untracked files.
- `README.md`: Project overview.
- `LICENSE`: Project license.

### 2. Sub-Directory Examples
- `src/backend/`: Backend code.
- `src/frontend/`: Frontend code.
- `docs/specifications/`: Technical specs, API contracts.
- `docs/guides/`: User guides, developer guides.
- `docs/reports/`: Research reports, sprint summaries.

## Document Management and Approval

### 1. Versioning
- All Markdown-based documents within `docs/` are versioned via Git.
- For binary documents (e.g., PDFs, complex spreadsheets), store them in `docs/` and rely on Git for version history. Major revisions may warrant a new file name with a date suffix (e.g., `report-2026-05-17.pdf`) if the content is fundamentally different and not easily diffable by Git.

### 2. Review and Approval
- **Drafts:** All new or significantly revised documents start as drafts on a feature branch.
- **Review:** Documents undergo peer review via Git Pull Requests (for Markdown) or designated review processes for other formats.
- **Approval:** Final approval is indicated by merging the PR (for Git-versioned docs) or by explicit sign-off from the relevant stakeholder(s) for other formats, with a record of approval maintained (e.g., in a `docs/approvals.md` log).
- **Final Version:** Approved documents are merged into the `main` branch.

### 3. Archiving
- Obsolete documents should be moved to an `archive/` sub-directory within `docs/` rather than deleted, preserving historical context.

## Next Actions for Approval Queue
1.  **Action:** Conduct a project-wide audit of existing files and directories to ensure compliance with `PROJECT_GUIDELINES.md`.
    - **Deliverable:** Audit Report (`audit_report.md`) detailing compliance status and required refactoring.
    - **Owner:** CIO
    - **Due Date:** 2026-06-01
2.  **Action:** Develop and implement a CI/CD pipeline for automated linting and formatting of code and Markdown documents.
    - **Deliverable:** CI/CD pipeline configuration files (`.github/workflows/lint-format.yml`).
    - **Owner:** CTO
    - **Due Date:** 2026-06-15
3.  **Action:** Integrate a dedicated document management system (DMS) for non-Markdown documents requiring advanced features (e.g., granular permissions, workflow automation).
    - **Deliverable:** DMS selection report (`dms_selection_report.md`) and initial setup plan.
    - **Owner:** CIO
    - **Due Date:** 2026-07-01
