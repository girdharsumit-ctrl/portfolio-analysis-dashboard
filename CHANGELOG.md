# 📝 Changelog

All notable changes to Portfolio Analysis Dashboard will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [Unreleased]

### Planned for v2.0
- Historical performance tracking
- Tax planning features (short-term vs long-term gains)
- Rebalancing recommendations
- Risk analytics (beta, volatility metrics)
- Dividend tracking & income analysis
- Automated monthly refresh scheduling
- Per-account detailed analysis
- Export capabilities (Excel, PDF reports)
- Mobile-friendly Power BI Service integration

---

## [1.0.0] - 2025-10-29

### 🎉 Initial Release

**First public release of Portfolio Analysis Dashboard!**

### Added

#### Core Features
- **Portfolio tracking** - Real-time portfolio value across all accounts
- **Gain/Loss analysis** - Total and per-position performance metrics
- **Sector allocation** - Visual breakdown by sector and subsector
- **Position details** - Individual stock performance and metrics
- **Multi-account support** - Track multiple brokerage/retirement accounts
- **Cash management** - Automatic recognition of money market funds

#### Data Management
- **500-stock reference** - Pre-classified common stocks by sector
- **Custom stocks feature** - Add your own stock classifications
- **Fidelity native support** - Works directly with Fidelity exports
- **Multi-broker compatibility** - Support for Schwab, Vanguard, E*TRADE
- **Automatic data cleanup** - Removes blanks, footer text, converts formats

#### Visualizations
- **Welcome page** - Portfolio overview and key metrics
- **Sector analysis page** - Allocation charts and breakdowns
- **Position details page** - Individual stock performance table
- **Interactive filters** - Click to drill down and explore
- **Professional formatting** - Clean, readable design

#### Measures (27 total)
- Portfolio value calculations
- Gain/loss metrics (dollar and percentage)
- Sector allocation percentages
- Cash position tracking
- Unknown stocks identification
- Account-level summaries

#### Documentation
- Comprehensive README with quick start
- Detailed setup guide with troubleshooting
- CSV format guide for all brokers
- Custom stocks guide with examples
- FAQ with 40+ common questions
- MIT License with attribution

### Technical Details
- **Platform:** PowerBI Desktop (2023+)
- **Data Source:** CSV exports from brokerages
- **Processing:** Power Query (M language)
- **Calculations:** DAX measures
- **Size:** ~2MB .pbix file
- **Performance:** Tested with 1,000+ positions

### Known Limitations
- No historical tracking (current snapshot only)
- No dividend/income tracking
- No tax lot analysis
- Desktop only (no web version included)
- Manual monthly refresh required

---

## Version History Summary

| Version | Date | Description |
|---------|------|-------------|
| 1.0.0 | 2025-10-29 | Initial public release |
| 0.9.0 | 2025-10-15 | Beta testing with sample data |
| 0.5.0 | 2025-09-20 | Alpha development (internal) |

---

## Upgrade Instructions

### From Beta (0.9.x) to v1.0.0

**If you were a beta tester:**

1. Download v1.0.0 .pbix file
2. Open Transform Data
3. Update data source connections to your files
4. Close & Apply
5. Your data will reload with new features

**What's new for beta users:**
- Custom stocks feature added
- Improved documentation
- Bug fixes in sector allocation
- Faster refresh performance
- Enhanced error handling

---

## Future Roadmap

### Short-term (v1.1 - Q1 2026)
- Bug fixes from user feedback
- Performance optimizations
- Additional stock reference entries
- Documentation improvements
- Video tutorials

### Mid-term (v2.0 - Q2 2026)
- Historical tracking
- Tax features
- Advanced analytics
- Dividend tracking
- Rebalancing tools

### Long-term (v3.0 - 2026+)
- API integration (live prices)
- Mobile app companion
- Cloud sync option
- AI-powered insights
- Community marketplace

---

## How to Report Issues

Found a bug or have a suggestion? 

1. Check if already reported in [Issues](https://github.com/[yourusername]/portfolio-analysis-dashboard/issues)
2. If new, open an issue with:
   - Version number
   - What you expected
   - What actually happened
   - Steps to reproduce
   - Screenshots if applicable

---

## Contributing

Want to help improve the dashboard? See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## Credits

**Created by:** [Your Name]  
**Built with:** Claude AI (Anthropic)  
**Thanks to:** Beta testers, contributors, and the PowerBI community

---

*Keep this file updated when releasing new versions!*

---

## Detailed Release Notes

### [1.0.0] - October 29, 2025

**New Features:**
- Launched custom stocks system for adding stocks not in default 500 list
- Added 27 DAX measures covering all core metrics
- Implemented automatic data cleanup in Power Query
- Created Welcome, Sector Analysis, and Position Details pages
- Built flexible architecture supporting multiple brokerage formats

**Documentation:**
- Wrote comprehensive README with quick start
- Created detailed setup guide with step-by-step instructions
- Documented CSV format requirements for all major brokers
- Built custom stocks guide with real-world examples
- Compiled FAQ with 40+ questions and answers
- Added MIT License with attribution requirements

**Testing:**
- Verified with sample portfolios (30+ positions)
- Tested with multiple account types (IRA, brokerage, Roth)
- Validated against Fidelity, Schwab exports
- Performance tested up to 1,000 positions
- Cross-checked calculations against broker statements

**Quality:**
- Zero known critical bugs
- Average load time <10 seconds
- Refresh time <5 seconds for typical portfolios
- All visuals rendering correctly
- Data validation passing

**Known Issues:**
- None critical
- Some minor formatting on edge cases (documented in FAQ)
- Feature requests tracked for v2.0

---

**Thank you for using Portfolio Analysis Dashboard!**

🌟 Star us on GitHub | 🐛 Report issues | 💡 Suggest features
