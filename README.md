# Coela Can't Website

[![CI Build](https://github.com/coelacant1/coelacant.github.io/actions/workflows/ci.yaml/badge.svg?branch=main)](https://github.com/coelacant1/coelacant.github.io/actions/workflows/ci.yaml)[![pages-build-deployment](https://github.com/coelacant1/coelacant.github.io/actions/workflows/pages/pages-build-deployment/badge.svg?branch=gh-pages)](https://github.com/coelacant1/coelacant.github.io/actions/workflows/pages/pages-build-deployment)



Welcome to the repository for [coelacant1.github.io](https://coelacant1.github.io/)—the personal site of **Coela Can't**.

---

## Table of Contents
- [About the Site](#about-the-site)
- [Technologies](#technologies)
- [Local Development](#local-development)
- [Continuous Integration (CI)](#continuous-integration-ci)
- [File/Folder Structure](#filefolder-structure)

---

## About the Site
This GitHub Pages site is a personal website for Coela Can't.
- Guides on Protogens
- All social links and contact information 
- Links to projects
- Files for Protogens

---

## Technologies
- **[Jekyll](https://jekyllrb.com/):** A Ruby-based static site generator used to build GitHub Pages.
- **[GitHub Actions](https://docs.github.com/en/actions):** Automated workflows to check, build, and deploy the site.
- **Ruby Gems:** 
  - [w3c_validators](https://github.com/sparklemotion/w3c_validators) for HTML/CSS validation
  - [html-proofer](https://github.com/gjtorikian/html-proofer) for link checking
  - [rubocop](https://rubocop.org/) for Ruby style checks (optional, if you have Ruby code)
- **Sass/CSS:** The site may use SCSS partials under `_sass/` or similar.

---

## Local Development

1. **Clone the Repo**  
   ```bash
   git clone https://github.com/coelacant1/coelacant1.github.io.git
   cd coelacant1.github.io
   ```

2. **Install Dependencies**
    Make sure you have Ruby installed (version 3.3+ recommended), then run:
    ```bash
    gem install bundler
    bundle install
    ```
    This installs all needed gems (Jekyll, etc.).

3. **Build & Serve Locally**
    ```bash
    bundle exec jekyll serve
    ```

4. **Running Tests/Checks**
    The script/cibuild (or equivalent) may include steps such as:
    ```bash
    #!/bin/sh
    set -e

    # Build the site
    bundle exec jekyll build

    # Check for broken links
    bundle exec htmlproofer ./_site

    # Run RuboCop (if configured)
    bundle exec rubocop -D

    # Validate HTML/CSS
    bundle exec script/validate-html
    ```

---

## Continuous Integration (CI)
GitHub Actions workflow (e.g. ci.yaml):
- Runs on push or pull_request.
- Checks out the code, sets up Ruby/Node, installs dependencies, and runs script/cibuild.
- If the build or validation fails, the workflow reports an error.

---

## File/Folder Structure
- _config.yml — Main Jekyll configuration.
- _sass/ — SCSS partials.
- _site/ — Generated build output (should not be committed if .gitignore is set).
- assets/ — Images, stylesheets, JavaScript, etc.
- script/ — Custom scripts (e.g., cibuild, validate-html).
- ci.yaml (in .github/workflows/) — The GitHub Actions workflow definition.
- Gemfile — Ruby dependencies.
