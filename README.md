# SMA Cloud with HUD

A professional TradingView indicator that displays up to 8 customizable Simple Moving Averages (SMAs) with a dynamic cloud visualization, Average True Range (ATR) overlay, and a heads-up display (HUD) for quick reference.

## Features

- **8 Configurable SMAs**: Display any combination of 5, 10, 20, 50, 60, 100, 120, and 200-period moving averages
- **Dynamic Cloud Shading**: Visual trend indicator between fast (MA1) and slow (MA2) moving averages
  - Green cloud when fast MA > slow MA (bullish)
  - Red cloud when fast MA < slow MA (bearish)
- **Heads-Up Display (HUD)**: Real-time display of daily SMA values and ATR in a customizable top-left overlay
  - Two-row format: SMA labels on top, values below for easy reading
- **Independent Visibility Controls**: Toggle each indicator on/off separately for chart and HUD
- **Full Customization**: Adjust periods, customize colors, and control transparency for all indicators

## Default Settings

### Moving Averages
- **MA1 (Fast)**: 5-period - Green (#95D47A)
- **MA2 (Slow)**: 10-period - Red (#E60049)
- **MA3**: 20-period - Blue (#3254FF)
- **MA4**: 50-period - Teal (#00BFA0)
- **MA5**: 60-period - Magenta (#DC0AB4)
- **MA6**: 100-period - Light Blue (#0BB4FF)
- **MA7**: 120-period - Purple (#9B19F5)
- **MA8**: 200-period - Orange (#FFA300)

### Cloud Colors
- **Bullish**: Green (#2ECC71)
- **Bearish**: Red (#E74C3C)

### ATR
- **Period**: 14 (customizable from 1-100)
  - 5-10: Scalpers/Day Traders
  - 14: Swing Traders (industry standard)
  - 20+: Mid/Long-term Traders
- **Color**: Light Blue (#B3D4FF)

## Customization

### Independent Visibility Controls
Each moving average (MA1-MA8) has **two separate toggle controls**:
- **Chart**: Show/hide the indicator line on the price chart
- **HUD**: Show/hide the indicator value in the heads-up display

This allows you to:
- Display short-term MAs on the chart while tracking only long-term MAs in the HUD
- Show all MAs in the HUD for reference without cluttering the chart
- Customize your workspace exactly how you need it

### Individual MA Settings
For each moving average, you can adjust:
- **Visibility**: Toggle chart and HUD display independently
- **Period**: Adjust the lookback length (1-500)
- **Color**: Choose your preferred color

### ATR Settings
- **HUD Visibility**: Toggle ATR display in the heads-up display
- **Period**: Adjust calculation period (1-100, default: 14)
  - 5-10 for scalpers and day traders (more responsive)
  - 14 for swing traders (balanced, industry standard)
  - 20+ for mid/long-term traders (smoother)
- **Color**: Customize the HUD cell color

### Cloud Settings
- **Bull Color**: Color displayed when MA1 > MA2
- **Bear Color**: Color displayed when MA1 < MA2
- **Trend Transparency**: Adjust cloud opacity (default: 80%)

### HUD Settings (Advanced)
Located in the Misc settings group:
- **HUD Text Size**: Adjust display size (Tiny/Small/Normal/Large/Huge)
- **HUD Left Offset**: Horizontal positioning (default: 13)
- **HUD Transparency**: Adjust cell background opacity (default: 10%)

## How to Use

### Trend Identification
- **Bullish Trend**: When the cloud is green (fast MA above slow MA)
- **Bearish Trend**: When the cloud is red (fast MA below slow MA)
- **Crossovers**: Watch for MA1/MA2 crossovers as potential entry/exit signals

### Support and Resistance
- Longer-period MAs (50, 100, 200) often act as dynamic support/resistance levels
- Price bouncing off a major MA can indicate trend continuation
- Price breaking through a major MA may signal trend reversal

### Multi-Timeframe Analysis
- The HUD displays daily SMA values regardless of your chart timeframe
- Compare current timeframe MAs with daily values for confluence

### Volatility Assessment
- ATR value increases during high volatility
- Use ATR for stop-loss placement and position sizing

## Technical Details

- **Version**: 1.1
- **Pine Script Version**: v6
- **Overlay**: Yes (plots on price chart)
- **License**: Mozilla Public License 2.0
- **Repainting Prevention**: Uses `lookahead=barmerge.lookahead_off` for reliable daily data
- **Input Validation**: All parameters have min/max constraints to prevent invalid values

## Performance Notes

- The indicator uses `request.security()` to fetch daily SMA values for the HUD
- HUD updates only on the last bar (`barstate.islast`) for optimal performance
- All MAs calculate on the chart's current timeframe
- Repainting is prevented using `lookahead=barmerge.lookahead_off` parameter

## Tips for Optimal Use

1. **Reduce Chart Clutter**: Use independent visibility controls to show only essential MAs on the chart while tracking all values in the HUD
2. **Adjust Transparency**: Increase cloud transparency if it obscures price action
3. **Customize ATR Period**: Match to your trading style
   - Scalping/Day Trading: 5-10 (captures intraday volatility changes)
   - Swing Trading: 14 (industry standard, balanced sensitivity)
   - Position/Long-term: 20+ (filters noise, shows major volatility shifts)
4. **Combine with Other Indicators**: Works well with RSI, MACD, or volume indicators
5. **Timeframe Considerations**: Longer MAs (100, 200) are more reliable on daily/weekly charts

## Common Use Cases

- **Day Trading**: Use MA1 (5) and MA2 (10) cloud for quick trend changes
- **Swing Trading**: Focus on MA3 (20) and MA4 (50) for swing trade setups
- **Position Trading**: Use MA6 (100) and MA8 (200) for long-term trend analysis
- **Multi-MA Strategy**: Use all 8 MAs to identify strong support/resistance zones

## Troubleshooting

**Chart is too crowded**: Use the independent "Chart" toggles to hide MAs on the chart while keeping them visible in the HUD

**HUD overlaps with other elements**: Adjust "HUD Left Offset" in Misc settings

**Cloud is too dark/light**: Adjust "Trend Transparency" in Misc settings

**Can't see certain MAs**: Check that both the "Chart" checkbox is enabled and the color contrasts with your chart background

**HUD text is too small/large**: Adjust "HUD Text Size" in Misc settings

## Author

**KUnit**

## License

This indicator is licensed under the Mozilla Public License 2.0. See [https://mozilla.org/MPL/2.0/](https://mozilla.org/MPL/2.0/) for details.

---

**Disclaimer**: This indicator is for educational and informational purposes only. It should not be considered financial advice. Always do your own research and consider your risk tolerance before making trading decisions.
