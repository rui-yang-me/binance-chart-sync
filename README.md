# Binance Trading Data Chart Synchronizer - Tampermonkey Script

> **One-Click Sync All Trading Charts** | Instantly synchronize time intervals across all Binance **Futures** trading data charts | Works on Binance.com, BinanceZH.com, and Binance.us

⚠️ **Important**: This script **only works with Futures contracts**. It does NOT support Spot trading data charts.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Tampermonkey](https://img.shields.io/badge/Tampermonkey-Script-green.svg)](https://www.tampermonkey.net/)
[![Version](https://img.shields.io/badge/version-7.0.0-blue.svg)](https://github.com/yourusername/binance-chart-sync)

## 🎯 What Does It Do?

This Tampermonkey userscript automatically synchronizes time intervals across **all trading data charts** on Binance's **Futures** trading data tab. Instead of manually changing each chart's timeframe (5m, 15m, 1h, 4h, etc.) one by one, just **click once** and all charts update instantly.

Perfect for traders who:
- 📊 Analyze multiple futures trading indicators simultaneously
- ⏰ Need to switch timeframes frequently
- 🚀 Want to save time and increase efficiency
- 💹 Trade on Binance **Futures** markets

**Note**: This script is designed specifically for **Futures contracts only** and does not work with Spot trading charts.

## ✨ Key Features

- **🎯 One-Click Sync**: Sync all charts (Volume, Open Interest, Long/Short Ratio, Funding Rate, etc.) to the same timeframe instantly
- **⚡ Fast & Smooth**: Optimized delays (500ms between charts) for quick synchronization
- **🎨 Beautiful UI**: Modern, draggable floating panel with gradient design
- **🖱️ Drag & Drop**: Both main panel and mini button are draggable
- **📍 Smart Display**: Only shows in "Trading Data" tab, auto-hides elsewhere
- **⌨️ Keyboard Shortcut**: `Option+S` (Mac) / `Alt+S` (Windows/Linux) to toggle panel
- **✅ Auto-Complete**: Automatically scrolls to top and minimizes after sync
- **🔄 Progress Tracking**: Real-time progress bar shows sync status
- **🎯 Skip Duplicates**: Intelligently skips charts already at target interval
- **💾 Position Memory**: Remembers panel position across page reloads

## 📦 Installation

### Prerequisites
- Install [Tampermonkey](https://www.tampermonkey.net/) browser extension
  - Chrome: [Chrome Web Store](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo)
  - Firefox: [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/tampermonkey/)
  - Edge: [Edge Add-ons](https://microsoftedge.microsoft.com/addons/detail/tampermonkey/iikmkjmpaadaobahmlepeloendndfphd)
  - Safari: [Mac App Store](https://apps.apple.com/us/app/tampermonkey/id1482490089)

### Install Script

1. Click on the Tampermonkey icon in your browser
2. Select "Create a new script"
3. Copy and paste the entire script from `TEST copy.js`
4. Save (Ctrl+S / Cmd+S)
5. Navigate to Binance trading page and switch to "Trading Data" tab

## 🚀 Usage

### Basic Usage

1. **Navigate to Binance Futures Trading Data Tab**
   - Go to any Binance **Futures** trading page (e.g., BTCUSDT Perpetual)
   - Click on the "Trading Data" tab (交易数据)
   - ⚠️ **Must be on Futures**, not Spot trading page

2. **Open the Sync Panel**
   - The mini button (📈) will appear automatically
   - Click the mini button to expand the panel
   - Or press `Option+S` (Mac) / `Alt+S` (Windows/Linux)

3. **Sync Charts**
   - Click any timeframe button (5分, 15分, 30分, 1时, 2时, 4时, 6时, 12时, 1天)
   - Watch the progress bar as all charts sync
   - Panel auto-minimizes when complete

### Panel Controls

- **📈 Mini Button**: Click to expand panel, drag to reposition
- **_ (Minimize)**: Hide panel but keep mini button visible
- **✕ (Close)**: Completely hide panel and button (use shortcut to reopen)
- **🔍 Scan Charts**: List all detected charts in current view
- **⏹ Stop**: Cancel ongoing synchronization

### Supported Timeframes

- **5分** - 5 minutes
- **15分** - 15 minutes
- **30分** - 30 minutes
- **1时** - 1 hour
- **2时** - 2 hours
- **4时** - 4 hours
- **6时** - 6 hours
- **12时** - 12 hours
- **1天** - 1 day

## 🎬 How It Works

### Synchronization Process

1. **Chart Detection**: Scans all charts in the Trading Data tab
2. **Smart Filtering**: Identifies charts that need updating
3. **Sequential Sync**: Updates each chart with optimized delays
4. **Visual Feedback**: Shows real-time progress with animations
5. **Auto-Complete**: Scrolls to top and minimizes when finished

### Supported Charts

This script synchronizes ALL **Futures** trading data charts including:
- 📊 Volume (成交量)
- 💰 Open Interest (持仓量) - **Futures only**
- 📈 Long/Short Ratio - Positions (大户持仓量多空比) - **Futures only**
- 👥 Long/Short Ratio - Accounts (多空账户数比) - **Futures only**
- 🔄 Taker Buy/Sell Volume (合约主动买卖量) - **Futures only**
- 💸 Funding Rate (资金费率) - **Futures only**
- 📉 Basis (基差) - **Futures only**
- And more...

⚠️ **Important**: These charts are **only available in Futures trading**. Spot markets do not have these data tabs.

## ⚙️ Configuration

### Adjustable Settings (in code)

```javascript
const config = {
  debug: true,                    // Enable console logging
  clickDelay: 200,                // Delay between click actions (ms)
  chartSwitchDelay: 500,          // Delay between chart switches (ms)
  panelPosition: { x: 20, y: 100 } // Initial panel position
};
```

### Storage

The script uses `GM_setValue` / `GM_getValue` to remember:
- Panel position
- Chart switch delay preference

## 🎨 UI Customization

The panel features a modern, dark theme with:
- **Gradient backgrounds** with glowing effects
- **Smooth animations** for all interactions
- **Responsive design** adapts to window size
- **Color-coded notifications**:
  - 🟢 Green - Success
  - 🔴 Red - Error
  - 🟡 Yellow - Warning
  - 🔵 Blue - Info

## 🔧 Troubleshooting

### Panel Not Showing
- ✅ Ensure you're on the "Trading Data" tab
- ✅ Press `Option+S` / `Alt+S` to toggle visibility
- ✅ Check if Tampermonkey is enabled
- ✅ Verify script is installed and active

### Sync Not Working
- ✅ **Ensure you're on a Futures trading page, NOT Spot**
- ✅ Confirm you're on Binance Futures trading page
- ✅ Wait for page to fully load before syncing
- ✅ Check browser console for errors (F12)
- ✅ Try refreshing the page

### Charts Skipped
- ℹ️ Charts already at target interval are automatically skipped
- ℹ️ This is normal and expected behavior

## 🌐 Supported Websites

- ✅ https://www.binance.com/*
- ✅ https://www.binancezh.com/*
- ✅ https://www.binance.us/*

## 📝 Version History

### v7.0.0 (Current)
- ✨ Draggable mini button
- ✨ Tab-aware visibility (only shows in Trading Data tab)
- ✨ Auto-scroll to top after completion
- ⚡ Faster synchronization (500ms delay)
- 🎨 Enhanced UI with better animations
- 🐛 Fixed click/drag conflict on mini button
- 🔧 Improved dropdown detection logic

### Previous Versions
- v6.x - Auto-minimize after sync
- v5.x - Added keyboard shortcuts
- v4.x - Draggable panel
- v3.x - Progress tracking
- v2.x - Basic synchronization
- v1.x - Initial release

## 🤝 Contributing

Contributions are welcome! Feel free to:
- 🐛 Report bugs
- 💡 Suggest new features
- 🔧 Submit pull requests
- 📖 Improve documentation

## 📄 License

MIT License - feel free to use, modify, and distribute.

## 👤 Author

**YangRui**

## 🙏 Acknowledgments

- Built with love for the Binance trading community
- Powered by [Tampermonkey](https://www.tampermonkey.net/)
- Inspired by traders who value efficiency

## 📞 Support

If you find this script helpful:
- ⭐ Star this repository
- 🐛 Report issues on GitHub
- 💬 Share with fellow traders
- ☕ Buy me a coffee (optional)

---

**Happy Trading! 📈💰**

*Disclaimer: This script is provided as-is. Trade at your own risk. Always do your own research.*
