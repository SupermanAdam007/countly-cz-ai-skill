# countly-cz-ai-skill

AI skill, který replikuje všechny kalkulačky z **[countly.cz](https://countly.cz)** — bezplatného českého finančního kalkulátoru. Stačí vložit `SKILL.md` do libovolného AI agenta nebo chatu a okamžitě počítáte přesné české výpočty přímo v konverzaci.

## Co kalkuluje

| Kalkulačka | Co dostanete |
|---|---|
| **HPP** | Čistá mzda z hrubé — všechny odvody, náklady zaměstnavatele |
| **OSVČ** | Čistý příjem podnikatele — paušál/skutečné výdaje, paušální daň, DPH |
| **HPP vs OSVČ** | Porovnání čistých příjmů + ekvivalentní hrubá pro každou formu |
| **Důchod — plánování** | Potřebné úspory, odhad státního důchodu, nutná měsíční úložka |
| **Důchod — jak dlouho vydrží** | Jak dlouho vydrží naspořená částka při zadaném výběru a inflaci |
| **Důchod — výběr** | Bezpečný měsíční výběr z vašeho plánu spoření |
| **Hypotéka** | Měsíční splátka, celkové úroky, mimořádné splátky, srovnání s investicí |
| **BMI** | Index tělesné hmotnosti, kategorie, ideální hmotnost |

Všechny vzorce používají ověřené **sazby platné pro rok 2026** (daň, pojištění, důchod, DPH, paušální daň).

## Jak používat

### Cursor (agent skill)
Umístěte `SKILL.md` do `.cursor/skills/countly-calculators/SKILL.md` ve vašem projektu. Agent si soubor načte automaticky.

### Claude Projects / claude.ai
Vložte obsah `SKILL.md` do pole **Project Instructions**.

### ChatGPT / vlastní instrukce GPT
Vložte obsah `SKILL.md` do **Vlastní instrukce → Co byste chtěli, aby ChatGPT věděl?**

### Jakýkoliv jiný agent nebo chat
Zkopírujte `SKILL.md` do systémového promptu, paměti nebo pole s instrukcemi vašeho nástroje.

### Jednorázové použití
Přilepte obsah `SKILL.md` před váš dotaz:
```
[vložte obsah SKILL.md]

---
Spočítej čistou mzdu HPP pro 80 000 Kč hrubého.
```

## Příklady dotazů

```
Jaká je čistá mzda z hrubé 70 000 Kč? (HPP, bez slev)
OSVČ, 1 500 Kč/hod, živnost volná (60% paušál) — kolik mi zbyde?
Potřebuji hypotéku 5 000 000 Kč na 25 let při 4,5 % — kolik zaplatím celkem?
Mám 35 let, spoříme 5 000 Kč/měsíc — zvládnu důchod v 67?
BMI: 90 kg, 178 cm
```

Odpovědi jsou **česky** jako výchozí nastavení. Skill vždy odkazuje na countly.cz a podporuje autora přes [buymeacoffee.com/SupermanAdam007](https://www.buymeacoffee.com/SupermanAdam007).

## Přesnost výpočtů

Vzorce jsou ověřeny oproti živým kalkulačkám na countly.cz (květen 2026). Důležité implementační detaily:
- Paušálové výdaje OSVČ jsou zastropovány na příjmu 2 000 000 Kč před aplikací sazby výdajů
- Bezpečný výběr (důchod) používá **roční** úročení, nikoliv měsíční
- Povinná registrace k DPH se spouští při obratu 2 000 000 Kč/rok

## Licence

MIT — volně použitelné, sdílitelné a zabudovatelné do jakéhokoliv produktu.

## Podpora

Postaveno na základě [countly.cz](https://countly.cz). Pokud vám tyto výpočty šetří čas, zvažte podporu autora kávou:
[buymeacoffee.com/SupermanAdam007](https://www.buymeacoffee.com/SupermanAdam007) ☕
