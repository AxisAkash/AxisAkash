# Profile Optimization Guide

A comprehensive guide to transforming your GitHub presence into a world-class developer profile.

---

## 1. README Change Explanation

### Key Changes Made

| Change | Rationale |
|--------|-----------|
| Username corrected to `AxisAkash` | Original used `atik806` — stats/graphs pointed to wrong user |
| Name corrected to `Rakibul Islam Akash` | Original used "Atik" — identity inconsistency hurts credibility |
| Removed fabricated tech stack items | No evidence of NestJS, Next.js, Supabase, PostgreSQL, Firebase, C# usage in any repo |
| Removed "AI-Powered IDEs" section | Listing IDEs as tech skills is a beginner signal that reduces credibility |
| Removed childish taglines | "Robot whisperer", "ML tinkerer", "plotting world domination" → sounds hobbyist, not professional |
| Removed duplicate stats card | Second stats block at line 130 was redundant |
| Removed contribution snake animation | Adds visual clutter on mobile, no recruiter value |
| Replaced table-based About Me | Tables for personal info look like a template, not professional |
| Added Featured Projects section | The #1 thing recruiters look for was completely missing |
| Added professional social links | No LinkedIn, portfolio, or resume links existed |
| Added Current Focus section | Shows active development and direction |
| Added Open Source roadmap | Signals intent to contribute — attractive to maintainers |
| Introduced dark/light mode support | Uses `<picture>` elements for adaptive theming |

### What Was Preserved
- Dark theme aesthetic (improved with indigo accent palette)
- Streak stats and activity graph (valuable engagement metrics)
- Badge-based tech stack display (just with verified technologies)
- Clean section structure (improved hierarchy and spacing)

---

## 2. Folder Structure Recommendations

```
AxisAkash/                          # GitHub profile repo
├── README.md                       # Profile README (this file)
├── assets/
│   ├── images/
│   │   ├── hero-banner.png         # Fallback hero image
│   │   ├── projects/
│   │   │   ├── offline-finance.png # Project screenshot
│   │   │   ├── currency-converter.png
│   │   │   ├── student-manager.png
│   │   │   ├── portfolio-site.png
│   │   │   ├── car-rental.png
│   │   │   └── ai-calculator.png
│   │   ├── og-image.png            # Social preview (1200×630)
│   │   └── github-profile-preview.png
│   └── svg/
│       ├── logo.svg                # Personal brand logo
│       └── divider.svg             # Custom section divider
├── .github/
│   ├── FUNDING.yml                 # GitHub Sponsors config
│   ├── profile/
│   │   └── README.md               # Org profile (if applicable)
│   └── workflows/
│       ├── metrics.yml             # GitHub Metrics action
│       ├── snake.yml               # Contribution snake generator
│       └── update-stats.yml        # WakaTime stats updater
└── docs/
    └── profile-guide.md            # This document
```

For each project repository:

```
OfflineFinanceManager/
├── README.md                       # Project README
├── CONTRIBUTING.md                 # Contribution guide
├── LICENSE                         # License file
├── SECURITY.md                     # Security policy
├── CODE_OF_CONDUCT.md              # Code of conduct
├── .github/
│   ├── ISSUE_TEMPLATE/
│   │   ├── bug_report.yml
│   │   └── feature_request.yml
│   ├── PULL_REQUEST_TEMPLATE.md
│   └── dependabot.yml
├── assets/
│   ├── screenshots/
│   │   ├── home-screen.png
│   │   ├── transactions.png
│   │   └── settings.png
│   └── og-image.png
└── src/
    └── ...
```

---

## 3. Missing Assets List

### Immediate Needs

| Asset | Purpose | Specification |
|-------|---------|---------------|
| **Profile avatar** | GitHub avatar, professional photo or logo | 460×460px, PNG, clear headshot or brand mark |
| **Social preview image** | OG image shown when sharing GitHub link | 1200×630px, PNG, dark bg with name/tagline |
| **Portfolio website** | Personal site linked from profile | React/Vite (already exists as AxisAkash_Portfolio) |
| **LinkedIn profile** | Professional networking | Fill out completely with skills, experience, education |
| **Resume PDF** | Downloadable resume | Host on portfolio or Google Drive |

### Nice-to-Have

| Asset | Purpose |
|-------|---------|
| **Project screenshots** | Showcase UI in project READMEs (consistent 1280×720) |
| **Demo GIFs** | Short (5-10s) screen recordings of app interactions |
| **Personal logo/SVG mark** | Simple geometric logo for branding |
| **Custom badge set** | Consistent tech badge styling across repos |

---

## 4. Recommended GitHub Actions

### Essential Workflows

**1. Metrics Generator**
Updates profile with rich GitHub statistics.

```yaml
# .github/workflows/metrics.yml
name: Metrics
on:
  schedule: [{cron: "0 0 * * *"}]
  workflow_dispatch:
jobs:
  metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          token: ${{ secrets.METRICS_TOKEN }}
          user: AxisAkash
          template: classic
          base: header, activity, community, repositories
          config_timezone: Asia/Dhaka
```

**2. Contribution Snake**
Generates snake animation for profile README.

```yaml
# .github/workflows/snake.yml
name: Generate Snake
on:
  schedule: [{cron: "0 0 * * *"}]
  workflow_dispatch:
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: Platane/snk@v3
        with:
          github_user_name: AxisAkash
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Recommended Additional Workflows

| Workflow | Purpose |
|----------|---------|
| **WakaTime Stats** | Display coding activity stats (requires WakaTime account) |
| **Label Sync** | Synchronize issue labels across repos |
| **Stale Issues** | Auto-close stale issues/PRs |
| **Dependabot** | Automated dependency updates |

---

## 5. Repository Optimization Checklist

### Every Repository Should Have

- [ ] **README.md** — professional description, setup instructions, tech stack, screenshots
- [ ] **LICENSE** — MIT recommended for most projects
- [ ] **.gitignore** — appropriate for the tech stack
- [ ] **Topics** — 3-8 relevant topics (e.g., `react-native`, `expo`, `finance`)
- [ ] **Description** — 1-line clear description in repo settings
- [ ] **Website link** — if deployed, add to repo sidebar
- [ ] **Consistent badges** — build status, license, version

### Quality Standards

- [ ] Clean commit history (squash WIP commits before push)
- [ ] Semantic commit messages (`feat:`, `fix:`, `docs:`, `chore:`)
- [ ] Branch naming convention (`feature/`, `fix/`, `docs/`)
- [ ] No secrets or API keys in code
- [ ] `README.md` renders correctly on mobile (test with GitHub mobile)
- [ ] All links work (no broken image URLs)

### Repository Description Examples

| Repository | Current | Recommended |
|---|---|---|
| OfflineFinanceManager | *(none)* | Local-first personal finance tracker for Bangladesh. Built with React Native, Expo & SQLite. Biometric auth, offline-first. |
| Mobile-App-Development | *(none)* | Student ID card management app built with React Native & Expo Router. |
| Mobile-App-Development_2 | *(none)* | Student directory app showcasing Expo Router navigation patterns. |
| Mobile-App-Development_3 | *(none)* | News reader app built with React Navigation stack patterns. |
| online-car-rent | *(long description)* | *(trim to 1-2 lines)* Web-based car rental management system built with PHP. |
| My_Portfolio | *(long description)* | Vanilla portfolio site — personal landing page with projects and contact info. |
| AxisAkash_Portfolio | *(none)* | Modern developer portfolio built with React, Vite, Tailwind CSS & shadcn/ui. |
| Digital-Currency-Converter | *(long description)* | PWA currency converter with live rates, offline support, and glassmorphic UI. |
| Ai_Calculator | *(long description)* | Multi-mode PWA calculator with standard, scientific, unit conversion & AI solver. |
| Student_Manager | *(long description)* | Browser-based student management with CRUD, attendance tracking & dark mode. |

### Rename Recommendations

| Current Name | Problem | Suggestion |
|---|---|---|
| Mobile-App-Development | Vague, no context | `student-card-app` |
| Mobile-App-Development_2 | Underscore suffix looks messy | `student-directory-app` |
| Mobile-App-Development_3 | Same pattern, unhelpful | `news-reader-app` |
| Health-Navigation-Management-System-.- | Trailing dash-dot, unwieldy | `healthcare-management-system` |
| GithubLabtask | Misspelled "GitHub" | `ml-lab-tasks` |
| GithubLabtask2 | Same issue | `github-practice` |
| Calculator_Normal- | Trailing dash | `simple-calculator` |
| Personal-Code | Too vague | `cpp-algos` |
| Matrix--Problem | Double dash | `cse-matrix-problems` |
| Matrix-Problem | Redundant with above | *(merge or delete)* |

---

## 6. Branding Recommendations

### Color Palette

```
Primary:    #6366F1 (Indigo-500)
Secondary:  #8B5CF6 (Violet-500)
Accent:     #06B6D4 (Cyan-500)
Dark BG:    #0D1117 (GitHub Dark)
Light BG:   #F9FAFB (GitHub Light)
Text Dark:  #C9D1D9
Text Light: #1F2937
Muted:      #6B7280
Success:    #22C55E
Error:      #EF4444
```

### Typography

- **Primary font**: JetBrains Mono (code), Inter (UI)
- **Markdown font**: GitHub's default (system-ui, -apple-system, sans-serif)
- **Consistency**: Use the same font across portfolio, READMEs, and blog

### Logo / Visual Identity

- A simple geometric mark using the initial "A" or "RA"
- Monogram-style logo for GitHub avatar and portfolio favicon
- Consistent treatment across all platforms

### Tone of Voice

| Context | Style | Example |
|---------|-------|---------|
| Profile intro | Professional, warm | "I build mobile applications and full-stack systems that solve practical problems." |
| Project descriptions | Technical, clear | "Local-first personal finance tracker built with React Native, Expo, and SQLite." |
| Social media | Enthusiastic, helpful | "Just shipped offline-first finance tracking for Bangladesh. Thread on architecture decisions ↓" |
| Error messages | Direct, not apologetic | "This feature requires an internet connection." |

### Developer Positioning

**Current position**: CS student at AIUB, early-career mobile developer
**Target position**: Mobile app developer with full-stack capabilities, AI-curious, open-source contributor
**Differentiator**: Local-first approach (building for markets with unreliable connectivity), practical problem-solver
**Niche**: React Native apps for developing markets

---

## 7. Future Roadmap (30-60-90 Day Plan)

### Phase 1: Foundation (Days 1-14)

- [ ] Create `AxisAkash/AxisAkash` GitHub repo and add profile README
- [ ] Fix all repo descriptions and add topics
- [ ] Add MIT license to all applicable repos
- [ ] Rename repos per recommendations above
- [ ] Create professional LinkedIn profile with detailed experience
- [ ] Set up portfolio site domain (axisakash.dev or rakibulakash.dev)
- [ ] Add proper `.gitignore` to all repos
- [ ] Create project READMEs for top 5 repos

### Phase 2: Quality (Days 15-30)

- [ ] Add screenshots to all project READMEs
- [ ] Set up GitHub Pages for applicable repos
- [ ] Implement semantic versioning (v1.0.0) on stable projects
- [ ] Add issue templates and PR templates to top repos
- [ ] Enable Discussions on main projects
- [ ] Set up Dependabot for dependency updates
- [ ] Create contribution guides
- [ ] Write 1-2 technical blog posts on Dev.to

### Phase 3: Growth (Days 31-60)

- [ ] Make 5+ meaningful open-source contributions (documentation, bug fixes)
- [ ] Publish first reusable package (React Native hook / component)
- [ ] Reach 10+ GitHub followers through community engagement
- [ ] Set up GitHub Sponsors profile
- [ ] Create GitHub Actions workflows for CI/CD
- [ ] Implement project boards for active repos
- [ ] Create Wiki documentation for major projects

### Phase 4: Excellence (Days 61-90)

- [ ] Contribute to a popular open-source project (Expo, React Native)
- [ ] Create a demo video walking through your best project
- [ ] Write a "How I Built This" technical case study
- [ ] Build an "Awesome List" (e.g., Awesome React Native Bangladesh)
- [ ] Reach consistent weekly commit streak (7+ weeks)
- [ ] Set up Google Analytics on portfolio site
- [ ] Apply for GitHub Student Developer Pack (if not already done)

---

## 8. World-Class Profile Suggestions

### What separates good profiles from great profiles

| Dimension | Good | Great |
|-----------|------|-------|
| **Projects** | Lists what they built | Shows architecture diagrams, explains trade-offs, links to live demos |
| **Code quality** | Code compiles | Clean code, tests, CI passing, documentation |
| **Consistency** | Commits weekly | Commits daily, has maintained a 100+ day streak |
| **Community** | Has followers | Answers issues, reviews PRs, writes guides, speaks at meetups |
| **Portfolio** | Simple static page | Case studies with metrics ("Reduced load time by 40%"), blog, testimonials |
| **Network** | Connected on LinkedIn | Appears in GitHub trending, featured in newsletters, has sponsors |

### Specific Actions for AxisAkash

1. **Commit daily** — Even small commits. Consistency signals reliability to recruiters.
2. **Write project READMEs with architecture** — Show you think in systems, not just code.
3. **Engage on issues** — Comment on 1-2 open-source issues per week (even just asking clarifying questions).
4. **Build in public** — Share progress on LinkedIn/Twitter. "Today I shipped X because Y."
5. **Create one "hero project"** — Pick OfflineFinanceManager and make it genuinely polished. Submit to product hunt/hacker news.
6. **Teach what you learn** — Write a short tutorial after each major feature. Dev.to loves React Native content.
7. **Network intentionally** — Follow developers at companies you admire. Engage meaningfully with their content.
8. **Get involved in local tech community** — Bangladeshi developer meetups, Facebook groups, etc.

### Profile Goals (Measurable)

| Metric | Current | 3-Month Goal | 6-Month Goal | 1-Year Goal |
|--------|---------|--------------|--------------|-------------|
| Followers | 1 | 15 | 50 | 100+ |
| Total Stars | 0 | 10 | 50 | 200+ |
| Repos with descriptions | 2/24 | 24/24 | 24/24 | 24/24 |
| Repos with licenses | 0/24 | 24/24 | 24/24 | 24/24 |
| Commit streak (days) | ~3 | 30 | 60 | 100+ |
| Open-source contributions | 0 | 5 | 15 | 30+ |
| Blog posts | 0 | 2 | 6 | 12+ |
| LinkedIn connections | N/A | 200 | 500 | 1000+ |

---

## 9. GitHub SEO Optimization

### Profile Discoverability

- **Username** (`AxisAkash`) — unique and memorable. Consider if you want "Rakibul" or "Akash" in it for searchability.
- **Bio** — Include keywords: `React Native`, `Mobile Developer`, `Bangladesh`, `Expo`
- **README headings** — Use terms recruiters search: `Mobile App Developer`, `React Native`, `Full-Stack`
- **Repository topics** — Add relevant topics to every repo

### Repository SEO

- **README keywords** — Include relevant terms in the first 100 words of each README
- **Topics** — Add 4-8 topics per repo
- **Description** — One clear sentence with primary technology mentioned first
- **README filename** — Always `README.md` (GitHub displays this by default)

---

## 10. Additional Improvements

### Pinned Repositories Strategy

Pin these 6 repos:

1. **OfflineFinanceManager** — Most active, most technically impressive
2. **AxisAkash_Portfolio** — Shows web skills, links to live portfolio
3. **Digital-Currency-Converter** — PWA, live demo, polished
4. **Student_Manager** — Complete CRUD app, shows frontend skills
5. **Ai_Calculator** — Multi-mode, PWA, interesting features
6. **online-car-rent** — PHP backend, shows full-stack range

### What NOT to Pin
- Lab task repos (`WebTech_LabTask`, `GithubLabtask`, etc.)
- Empty or skeleton repos
- Repos with no README or description

### Issue Template Strategy

For each major project, add two issue templates:

**Bug Report** (`bug_report.yml`):
```yaml
name: Bug Report
description: Report a bug to help us improve
title: "[Bug]: "
labels: [bug]
body:
  - type: textarea
    id: description
    attributes:
      label: Description
      description: What happened?
    validations:
      required: true
  - type: textarea
    id: reproduction
    attributes:
      label: Steps to reproduce
      placeholder: |
        1. Go to...
        2. Click on...
        3. See error
  - type: input
    id: device
    attributes:
      label: Device / OS / Browser
```

**Feature Request** (`feature_request.yml`):
```yaml
name: Feature Request
description: Suggest an idea for this project
title: "[Feature]: "
labels: [enhancement]
body:
  - type: textarea
    id: problem
    attributes:
      label: Problem
      description: What problem does this solve?
  - type: textarea
    id: solution
    attributes:
      label: Proposed solution
```

### Pull Request Template

```markdown
## Description
<!-- Briefly describe what this PR does -->

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation
- [ ] Refactor

## Testing
- [ ] Tested on Android
- [ ] Tested on iOS
- [ ] Tested on Web

## Screenshots
<!-- If UI changes -->

## Related Issues
Closes #<!-- issue number -->
```

### Semantic Versioning

For stable projects, use `MAJOR.MINOR.PATCH`:
- `v1.0.0` — First stable release
- `v1.1.0` — New feature, backward compatible
- `v1.1.1` — Bug fix, backward compatible

Create releases on GitHub for each version.

---

## Summary: Instant Wins (Do These Today)

1. Create `AxisAkash/AxisAkash` repo and add the new README
2. Add descriptions to all 24 repos
3. Add 3-5 topics to each repo
4. Add MIT license to all repos
5. Rename poorly-named repos (Mobile-App-Development_2, etc.)
6. Create LinkedIn profile with "Mobile App Developer at AIUB"
7. Fix broken image links in current project pages
8. Set up GitHub Pages for the 4 deployable apps
9. Add `.gitignore` to repos that are missing it
10. Remove/archive old, empty, or demo repos

---

*This guide was generated as part of a comprehensive profile audit. Revisit quarterly to track progress and adjust strategy.*
