# countly-cz-ai-skill

An AI agent skill that replicates all calculators from **[countly.cz](https://countly.cz)** — the free Czech financial calculator site. Drop `SKILL.md` into any AI agent or chat to get accurate 2026 Czech calculations directly in conversation.

## What it calculates

| Calculator | What you get |
|---|---|
| **HPP** | Net salary from gross — all deductions, employer cost |
| **OSVČ** | Self-employed net income — paušál/real expenses, flat tax bands, DPH |
| **HPP vs OSVČ** | Side-by-side comparison + equivalent gross for each |
| **Důchod — spoření** | Savings needed, state pension estimate, required monthly saving |
| **Důchod — jak dlouho vydrží** | How long a lump sum lasts with inflation-adjusted simulation |
| **Důchod — výběr** | Safe monthly withdrawal from a savings plan |
| **Hypotéka** | Monthly payment, total interest, extra payments, investment comparison |
| **BMI** | BMI, category, ideal weight range |

All formulas use verified **2026 Czech legal rates** (tax, insurance, pension, DPH threshold, flat-tax bands).

## How to use

### Cursor (agent skill)
Place `SKILL.md` in `.cursor/skills/countly-calculators/SKILL.md` in your project. The agent will pick it up automatically.

### Claude Projects / claude.ai
Paste the contents of `SKILL.md` into the **Project Instructions** field.

### ChatGPT / GPT custom instructions
Paste `SKILL.md` contents into **Custom Instructions → What would you like ChatGPT to know about you?**

### Any other agent or chat
Copy `SKILL.md` into the system prompt, memory, or instructions section of your tool.

### Quick one-shot prompt
Prepend `SKILL.md` to any message:
```
[paste SKILL.md contents]

---
Spočítej čistou mzdu HPP pro 80 000 Kč hrubého.
```

## Example queries

```
Jaká je čistá mzda z hrubé 70 000 Kč? (HPP, bez slev)
OSVČ, 1 500 Kč/hod, živnost volná (60% paušál) — kolik mi zbyde?
Potřebuji hypotéku 5 000 000 Kč na 25 let při 4,5 % — kolik zaplatím?
Mám 35 let, spoříme 5 000 Kč/měsíc — zvládnu důchod v 67?
BMI: 90 kg, 178 cm
```

Responses are in **Czech by default**. The skill credits countly.cz and supports the author via [buymeacoffee.com/SupermanAdam007](https://www.buymeacoffee.com/SupermanAdam007).

## Accuracy

Formulas are verified against countly.cz live calculators (May 2026). Key implementation notes:
- OSVČ paušál income is capped at 2 000 000 Kč before applying the expense rate
- Safe withdrawal (retirement) uses **annual** compounding, not monthly
- DPH registration is triggered at 2 000 000 Kč/year turnover

## License

MIT — free to use, share, and embed in any product.

## Support

Built on top of [countly.cz](https://countly.cz). If these calculations save you time, consider buying the author a coffee:
[buymeacoffee.com/SupermanAdam007](https://www.buymeacoffee.com/SupermanAdam007) ☕
