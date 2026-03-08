# Agent Rules

> Curated AI agent rules for the AgentOps platform. Contains cursor rules (.mdc), coding standards, and security rules bundled as git submodules.

## What This Repository Contains

This repo aggregates **high-quality, vetted coding rules** from trusted open-source sources. Rules enforce coding standards, security practices, and best patterns across the AgentOps stack.

### Bundled Rule Repositories

| Submodule | Path | What It Provides |
|---|---|---|
| **ivangrynenko/cursorrules** | `vendor/ivangrynenko/cursorrules/` | 22+ OWASP Top 10 rules (PHP/JS/Python), Docker Compose standards, GitHub Actions standards, Vue/Tailwind/accessibility rules. Tag-based installer. |
| **PatrickJS/awesome-cursorrules** | `vendor/PatrickJS/awesome-cursorrules/` | 900+ curated cursor rules. Laravel PHP 8.3, TALL Stack, FastAPI, Vue 3, Next.js/React, TypeScript, DRY/SOLID, clean-code, database. Both `.cursorrules` and `.mdc` formats. |
| **Van-LLM-Crew/cursor-secure-coding** | `vendor/Van-LLM-Crew/cursor-secure-coding/` | OWASP ASVS Level 1 and Level 2 cursor rules (.mdc format). Security-focused coding standards. |
| **pekral/cursor-rules** | `vendor/pekral/cursor-rules/` | PHP 8.4 coding standards, Pest testing rules, code review, security analysis, and refactoring agent skills. |

## Installation

### As a Composer dependency (recommended for AgentOps)

Add this repository to your project's `composer.json`:

```json
{
    "repositories": [
        {
            "type": "vcs",
            "url": "git@github.com:garethdaine/agent-rules.git"
        }
    ],
    "require-dev": {
        "garethdaine/agent-rules": "dev-main"
    }
}
```

Then run:

```bash
composer update garethdaine/agent-rules --prefer-source
cd vendor/garethdaine/agent-rules && git submodule update --init --recursive
```

### Standalone clone

```bash
git clone --recurse-submodules git@github.com:garethdaine/agent-rules.git
```

## Usage

### Installing rules into your project

**ivangrynenko/cursorrules** (tag-based installer):

```bash
cd vendor/garethdaine/agent-rules/vendor/ivangrynenko/cursorrules
php install.php -- --tags "standard:owasp-top10 language:php"    # OWASP PHP rules
php install.php -- --tags "category:security"                     # All security rules
php install.php -- --tags "category:devops"                       # All DevOps rules
php install.php -- --all                                          # Everything
```

**PatrickJS/awesome-cursorrules** (copy to your project):

```bash
# .mdc rules (modern format)
cp vendor/garethdaine/agent-rules/vendor/PatrickJS/awesome-cursorrules/rules-new/fastapi.mdc .cursor/rules/
cp vendor/garethdaine/agent-rules/vendor/PatrickJS/awesome-cursorrules/rules-new/vue.mdc .cursor/rules/
cp vendor/garethdaine/agent-rules/vendor/PatrickJS/awesome-cursorrules/rules-new/typescript.mdc .cursor/rules/

# .cursorrules (legacy format)
cp vendor/garethdaine/agent-rules/vendor/PatrickJS/awesome-cursorrules/rules/laravel-php-83-cursorrules-prompt-file/.cursorrules .cursorrules
```

### Key rule paths

| Technology | Path |
|---|---|
| **Laravel PHP 8.3** | `vendor/PatrickJS/awesome-cursorrules/rules/laravel-php-83-cursorrules-prompt-file/` |
| **Laravel TALL Stack** | `vendor/PatrickJS/awesome-cursorrules/rules/laravel-tall-stack-best-practices-cursorrules-prom/` |
| **FastAPI** | `vendor/PatrickJS/awesome-cursorrules/rules-new/fastapi.mdc` |
| **Vue 3** | `vendor/PatrickJS/awesome-cursorrules/rules-new/vue.mdc` |
| **TypeScript** | `vendor/PatrickJS/awesome-cursorrules/rules-new/typescript.mdc` |
| **React** | `vendor/PatrickJS/awesome-cursorrules/rules-new/react.mdc` |
| **Next.js** | `vendor/PatrickJS/awesome-cursorrules/rules-new/nextjs.mdc` |
| **Tailwind** | `vendor/PatrickJS/awesome-cursorrules/rules-new/tailwind.mdc` |
| **Rust** | `vendor/PatrickJS/awesome-cursorrules/rules-new/rust.mdc` |
| **Python** | `vendor/PatrickJS/awesome-cursorrules/rules-new/python.mdc` |
| **Database** | `vendor/PatrickJS/awesome-cursorrules/rules-new/database.mdc` |
| **Clean Code** | `vendor/PatrickJS/awesome-cursorrules/rules-new/clean-code.mdc` |
| **Code Quality** | `vendor/PatrickJS/awesome-cursorrules/rules-new/codequality.mdc` |
| **DRY/SOLID** | `vendor/PatrickJS/awesome-cursorrules/rules/optimize-dry-solid-principles-cursorrules-prompt-file/` |
| **OWASP PHP** | `vendor/ivangrynenko/cursorrules/` → `--tags "language:php standard:owasp-top10"` |
| **OWASP JS** | `vendor/ivangrynenko/cursorrules/` → `--tags "language:javascript standard:owasp-top10"` |
| **OWASP Python** | `vendor/ivangrynenko/cursorrules/` → `--tags "language:python standard:owasp-top10"` |
| **ASVS Security** | `vendor/Van-LLM-Crew/cursor-secure-coding/` |

## Updating

```bash
git submodule update --remote --merge
git add . && git commit -m "chore: update rule submodules"
```

## Related

- **[agent-skills](https://github.com/garethdaine/agent-skills)** — Companion repository for SKILL.md agent skills
- **[agent](https://github.com/garethdaine/agent)** — The AgentOps platform

---

*Maintained as part of the AgentOps platform. See `agent-ops-engineering-rules.md` for the full standards document.*
