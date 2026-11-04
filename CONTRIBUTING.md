# Contributing to BSQF

Welcome to the GitHub organization of **BSQF – Bocconi Students Quantitative Finance**.
These guidelines apply to every repository in the organization, unless a repository has its own `CONTRIBUTING.md`.

Please read them before your first contribution. They keep our work organized, secure and easy for everyone to build on.

---

## 1. Before you start

- Use your **personal GitHub account**. Accounts are never shared.
- Turn on **two-factor authentication (2FA)**. It is required to stay in the organization.
- Make sure you've been added to the right **team**. If you can't push or open a pull request on a repository, ask an Owner.
- When you leave BSQF, let an Owner know so your access can be removed.

## 2. Roles

| Role | Who | Responsibilities |
|------|-----|------------------|
| **Owner** | Organization administrators (max. 2) | Manage members, teams and settings; final approval on changes |
| **Maintainer** | Project leads | Review and merge pull requests for their project |
| **Member** | Everyone else | Open issues and pull requests |

Access is granted through teams, and only at the level each person needs.

## 3. Workflow

Every change goes through a pull request. **Nobody pushes directly to `main`.**

1. **Start from an issue.** Open one (or pick an existing one) describing what you want to do, and assign it to yourself.
2. **Create a branch** from `main` with a short, descriptive name:
   - `feature/momentum-backtest`
   - `fix/sharpe-ratio-calculation`
   - `docs/update-readme`
3. **Commit in small, meaningful steps**, with messages that say what changed:
   - ✅ `Add rolling volatility to risk module`
   - ✅ `Fix off-by-one error in backtest date range`
   - ❌ `update`, `fix`, `final version 2`
4. **Open a pull request** to `main`. In the description, include:
   - what you changed and why;
   - how you tested it;
   - a link to the issue (e.g. `Closes #12`).
5. **Get at least one approval** from a Maintainer or Owner before merging.
6. **Delete your branch** after the merge.

## 4. Code and research standards

- **Readable over clever.** Use clear variable names and comment the reasoning behind non-obvious choices (assumptions, formulas, parameters).
- **Naming conventions.** Don't use camelCase.
  - Variables and functions use `snake_case`: `daily_returns`, `compute_sharpe_ratio()`
    - ❌ `dailyReturns`, `computeSharpeRatio()`
  - Constants use `UPPER_SNAKE_CASE`: `RISK_FREE_RATE`, `TRADING_DAYS_PER_YEAR`
  - Classes use `PascalCase`: `BacktestEngine`, `PortfolioOptimizer`
- **Keep documentation up to date.** Every project has the following structure:
  ```
  project-name/
  ├── README.md        ← short overview: what the project does, how to run it
  │                       and where the data comes from
  └── docs/
      ├── README.md    ← index of the documentation
      └── ...          ← detailed docs (methodology, data sources, modules)
  ```
  When you change how something works, update the root `README.md` and the relevant files in `docs/` in the same pull request. Explain the code inside the code too: add comments that say what a function does, what its inputs and outputs are (including units, e.g. daily vs. annualized, simple vs. log returns) and why it was written that way.
- **Test your code before you push it.** Run it and check that it works and gives sensible results. For example: the script runs from start to finish without errors, outputs have the expected shape and range, and results match a simple case you can verify by hand. If the project has tests, run them and make sure they pass. Never push code you haven't run.
- **Reproducible results.** List your dependencies (e.g. `requirements.txt` or `environment.yml`) and fix random seeds where relevant.
- **Notebooks.** Clear outputs before committing unless the outputs are the point of the notebook. Move reusable logic into `.py` files.
- **No hidden look-ahead bias.** In backtests, make clear what data is available at each point in time.

## 5. What must never be committed

All of our public repositories are visible to anyone, **including their full history**. Deleting a file in a later commit does **not** remove it.

Never commit:

- 🔑 **Secrets**: passwords, API keys, tokens (broker, data provider, cloud). Use environment variables or a local `.env` file listed in `.gitignore`.
- 📊 **Licensed or proprietary data**, e.g. exports from Bloomberg, Refinitiv/LSEG, FactSet or university databases. Their licenses do not allow redistribution. Commit the code that fetches or processes the data, not the data itself.
- 👤 **Personal data**: member lists, emails, phone numbers, student IDs.
- 📦 **Large files**: datasets, model weights, binaries. Keep files under a few MB and document where to get large ones.

**If something sensitive gets committed by mistake, tell an Owner immediately.** Don't try to fix it alone. Leaked keys must be revoked, not just deleted.

## 6. Communication

- Use **Issues** for bugs, ideas and tasks; use pull request comments for feedback on specific changes.
- Be respectful and constructive in reviews. Comment on the code, not the person.
- If you're stuck, ask. A question in an issue is better than a broken `main` branch.

## 7. Disclaimer

Everything in this organization is for **educational and research purposes only** and does not constitute investment advice.

## 8. Contacts

For questions about access, permissions or these guidelines, contact the organization Owners through the BSQF official email address.
