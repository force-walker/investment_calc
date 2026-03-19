# Share Calculator MVP

Simple single-page web app to calculate project ownership share (total 100%) based on weighted monetary and non-monetary contributions.

## Run

Open `index.html` directly in your browser.

Or run a local static server from workspace root:

```bash
python3 -m http.server 8080
```

Then open:

`http://localhost:8080/restaurant_investment/app/index.html`

## Formula

For each stakeholder `i`:

- `moneyScore_i = M_i / ΣM`
- `nonMoneyScore_i = N_i / ΣN`
- `finalScore_i = wM * moneyScore_i + wN * nonMoneyScore_i`
- `share_i = finalScore_i * 100`

Where:

- `M_i` = monetary contribution
- `N_i` = non-monetary points
- `wM + wN = 1`

## Notes

- If `ΣM = 0`, monetary component is treated as 0 for all.
- If `ΣN = 0`, non-monetary component is treated as 0 for all.
- If both are 0, calculation is invalid.
- Display rounds to 2 decimals and adjusts rounding drift so visible total is 100.00%.
