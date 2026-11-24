# Ritz TwinTrend Adaptive - open-source components

These two files are published under the **Mozilla Public License 2.0** (MPL-2.0). They are part of the commercial indicator "Ritz TwinTrend Adaptive" (MQL5 Market). The rest of that indicator is separate work and is not covered by this license.

| File | Content |
|---|---|
| `Ritz_TTA_KMeansST.mqh` | K-means adaptive SuperTrend maths (class `CSTKM`) and the Pine `na()` helpers |
| `Ritz_TTA_StFill.mqh` | Gradient trend fill and volatility cluster numbers, drawn on a Canvas layer |

## Origin and credits

- Original Pine Script indicator: "Machine Learning Adaptive SuperTrend [AlgoAlpha]", (c) AlgoAlpha, MPL-2.0 (TradingView script CLk71Qgy).
- MQL5 port: (c) 2026 Trung, same license (MPL-2.0).
- Modifications for Ritz TwinTrend Adaptive: (c) Ritz EAneha, same license (MPL-2.0).

## What was changed

- `CSTKM`: the calculation is done incrementally (`Push` adds a closed bar, `Pop` removes it) so a live bar can be previewed without changing the closed-bar history. The maths itself is unchanged.
- `Ritz_TTA_StFill.mqh`: the fill is drawn straight into a Canvas bitmap instead of with `DRAW_FILLING` plots. Band geometry (steps from the line to the candle body edge) and the colour blend (Transparency 1 / 2, dark-chart boost) follow the earlier MQL5 version.

## Notes

- `Ritz_TTA_StFill.mqh` calls helper functions and globals that live in the proprietary part of the indicator (for example the chart-to-pixel mapping), so it does not compile on its own. `Ritz_TTA_KMeansST.mqh` is self-contained.
- This license applies to these two files only. It gives no rights to the rest of Ritz TwinTrend Adaptive.

The full license text: https://mozilla.org/MPL/2.0/
