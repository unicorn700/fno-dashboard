# F&O Performance Dashboard

A standalone browser-based dashboard for analyzing historical **Zerodha F&O tradebook and P&L exports**.

It runs entirely in the browser, generates a dark-mode analytics view, and helps review year-wise profitability, return %, cumulative P&L, and trading-day heatmaps.

## Highlights

- Single-file app: `fno_dashboard.html`
- No backend required
- Browser-side Excel parsing using SheetJS
- Interactive charts using Plotly
- Year-wise net profit/loss analysis
- Invested capital vs net profit vs turnover comparison
- Return % calculation from manually entered capital
- Cumulative P&L chart by financial year
- Trading-day heatmap
- Best/worst day, week, month, and year insights
- Local settings persistence using `localStorage`
- Export/import parsed dashboard state as JSON

## Demo / Usage

### Option 1: Open directly
Just open `fno_dashboard.html` in a browser.

### Option 2: Serve locally
If your browser is restrictive with local files, run:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000/fno_dashboard.html
```

## Expected input files

The dashboard is built around **Zerodha** exports and expects filenames like:

- `tradebook-*.xlsx`
- `pnl-*.xlsx`

It parses data such as:

- trade date
- symbol
- trade type
- quantity
- price
- realised P&L
- charges
- other credit/debit

If your broker export format differs, the parsing logic may need adjustment.

## How it works

1. Upload one or more yearly tradebook and P&L Excel files
2. The dashboard parses them in-browser
3. It groups results by financial year
4. You can manually enter invested capital for each year
5. You can add event annotations like election dates, budget days, war events, or Fed meetings
6. You can save the parsed state as JSON and reload it later

## Current limitations

- Optimized for Zerodha export formats, not generic broker statements
- Depends on CDN-delivered libraries:
  - SheetJS (`xlsx`)
  - Plotly
- No automated tests yet
- Best used on desktop/laptop screens for now
- Some labels/help text may still reflect local prototype assumptions

## Privacy

The dashboard processes uploaded files in the browser.

This HTML app does **not** upload your Excel files to a backend on its own.

## Disclaimer

This project is for analysis and educational use only. It is **not financial advice**. Always verify calculations independently before making trading decisions.
