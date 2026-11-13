# SI-HCPN Observatory — English interface

Static version of the ICOSI dashboard, intended for https://nmessaoudi-icosi.github.io/CAI/.

## Enable deployment
In the CAI repository, open **Settings → Pages → Build and deployment → Source → GitHub Actions**.
Under **Actions → Deploy the SI-HCPN Observatory → Run workflow**, select `main` and run the workflow if needed.
The URL is available only after a successful deployment.

## Development
Node.js 22.13 or later:
```
cd observatoire
npm ci
npm test
npm run dev
npm run build
```

## Data and limitations
- Public interface; no ChatGPT sign-in required on GitHub Pages.
- No real experimental data included: the demo is explicitly fictional.
- CSV/JSON/ZIP imports are processed in the browser; sessions are stored locally and can be exported as JSON. Data from the previous domain are not transferred automatically: export and then restore the session.
- RF remains the valid reference. N/A means missing/not calculated, never zero.
- Per-asset totals come from `asset_totals.csv` (asset,discharge,shift). Raw cumulative traces are not automatically summed.
- `metrics.csv`: f1,precision,recall,auc,peaks,ens,ome,shift. Scores in [0,1].
- `sgrid_history.csv`: step,demand,supply,v2gdischarge.
- `final_sgrid.csv`: last row of the final state.
- PDF report through browser printing (Save as PDF).
- Ranking: adjustable weights, min–max normalization, complete runs only; the same scenario and step count are required. The full methodology is available in the interface.

The dashboard is not a repository of the experimental artifacts associated with the paper.
