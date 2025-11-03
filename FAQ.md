# ❓ Frequently Asked Questions (FAQ)

**Quick answers to common questions**

---

## 📋 Table of Contents

- [General Questions](#general-questions)
- [Installation & Setup](#installation--setup)
- [Data & Calculations](#data--calculations)
- [Features & Functionality](#features--functionality)
- [Customization](#customization)
- [Performance & Technical](#performance--technical)
- [Privacy & Security](#privacy--security)

---

## 🌟 General Questions

### Q: Is this really free?

**A:** Yes! Completely free and open source. No subscriptions, no premium tiers, no hidden costs.

You'll need PowerBI Desktop (also free from Microsoft), but the dashboard itself costs nothing.

---

### Q: Do I need to know PowerBI to use this?

**A:** No! If you can download a file and click "Refresh," you can use this.

Advanced users can customize it, but basic use requires no technical knowledge.

---

### Q: What brokers does this work with?

**A:** 
- ✅ **Natively:** Fidelity (just download & import)
- ✅ **With minor adjustments:** Schwab, Vanguard, E*TRADE, TD Ameritrade
- ✅ **With column mapping:** Most brokers that export CSV

See [CSV_FORMAT_GUIDE.md](CSV_FORMAT_GUIDE.md) for details.

---

### Q: Can I use this for retirement accounts (IRA, 401k)?

**A:** Yes! Works with any account type:
- Traditional IRA
- Roth IRA
- 401(k)
- Individual brokerage
- Joint accounts
- Trust accounts

As long as you can export the data, this will work.

---

### Q: How often should I update my data?

**A:** Monthly is ideal. More frequent updates won't hurt, but portfolio values don't change drastically day-to-day (unless day trading).

**Recommended:** First of every month.

---

### Q: Will my data be sent anywhere?

**A:** No. This runs 100% locally on your computer. No data is uploaded, transmitted, or shared. Your financial information never leaves your machine.

---

## 🛠️ Installation & Setup

### Q: PowerBI won't open on my Mac

**A:** PowerBI Desktop is Windows-only. Mac users need:
- **Option 1:** Parallels or VMware with Windows
- **Option 2:** Bootcamp (dual-boot Windows)
- **Option 3:** Use PowerBI Service (web version, requires subscription)

---

### Q: I get "Can't find file" errors

**A:** File paths are hard-coded. Fix:
1. Open PowerBI → **Transform Data**
2. Each query with error → Click gear icon next to "Source"
3. Browse to YOUR file location
4. Click OK
5. Close & Apply

**Pro tip:** Keep all files in one folder to minimize path issues.

---

### Q: Setup is taking forever / Dashboard won't load

**A:** First-time load can take 1-2 minutes depending on:
- Computer speed
- Portfolio size
- PowerBI version

**If it's stuck >5 minutes:**
- Close PowerBI
- Restart computer
- Try again
- Check Task Manager - is PowerBI responding?

---

### Q: Do I need all 16 columns from Fidelity export?

**A:** No. The dashboard only requires 7 core columns:
- Account Number/Name
- Symbol
- Quantity
- Last Price
- Cost Basis Total

Extra columns are fine (PowerBI ignores them), but not required.

---

## 📊 Data & Calculations

### Q: Why don't my numbers match Fidelity exactly?

**Possible reasons:**
1. **Timing:** You exported at different time than you're viewing
2. **Cash positions:** May be calculated differently
3. **Fractional shares:** Rounding differences
4. **Pending trades:** Not settled yet
5. **Currency conversion:** If holding international

**Usually differences are <$0.50 per position.**

---

### Q: What does "Unknown Stocks" mean?

**A:** Stocks not in the 500-stock reference list. They still appear in your portfolio, but show as "Unknown" sector.

**Fix:** Add them to custom stocks file. See [CUSTOM_STOCKS_GUIDE.md](CUSTOM_STOCKS_GUIDE.md)

---

### Q: How are sectors assigned?

**A:** 
1. Dashboard checks your stock symbol
2. Looks up in Stock Reference table (500 pre-loaded stocks)
3. Also checks My_Custom_Stocks file (your additions)
4. Assigns sector/subsector
5. If not found → "Unknown"

**Custom stocks override default classifications.**

---

### Q: Why is my cash showing as SPAXX?

**A:** Fidelity uses money market fund symbols for cash:
- **SPAXX** = Fidelity Government Money Market
- **FDRXX** = Fidelity Treasury Money Market
- **FDIC** = Bank sweep

The dashboard recognizes these as cash automatically.

---

### Q: Can I track multiple accounts?

**A:** Yes! The dashboard was designed for this. Just include all accounts in your CSV export.

You'll see:
- Total across all accounts
- Individual account breakdowns
- Per-account allocation (coming in v2.0)

---

### Q: Does this track dividends?

**A:** Not in v1.0. Current version shows:
- ✅ Position values
- ✅ Unrealized gains/losses
- ✅ Cost basis

**Future (v2.0):**
- Dividend tracking
- Income analysis
- Yield calculations

---

### Q: Can I see historical performance?

**A:** Not yet. v1.0 is a snapshot (current portfolio state).

**Workaround:** Save monthly copies:
- `PortfolioDashboard_2025-10.pbix`
- `PortfolioDashboard_2025-11.pbix`
- Compare manually

**v2.0 will have:** Historical tracking, performance charts, trend analysis.

---

## 🎨 Features & Functionality

### Q: Can I change colors/themes?

**A:** Yes! 
1. Click any visual
2. Format tab (paintbrush icon)
3. Change colors, fonts, sizes
4. File → Save

**Changes persist across data refreshes.**

---

### Q: How do I export to PDF?

**A:** 
1. File → Export → PDF
2. Choose pages to include
3. Save

**Or:** File → Print → Print to PDF (Windows)

---

### Q: Can I add my own calculations?

**A:** Yes! The .pbix is fully editable.

**To add a measure:**
1. Right-click `All_Measures_Tbl`
2. New Measure
3. Write DAX formula
4. Use in visuals

**Note:** Basic DAX knowledge helpful but not required for simple calculations.

---

### Q: Can I share this with my spouse/advisor?

**A:** Yes, but be careful:

**Safe:**
- Send screenshots
- Export to PDF
- Share with sample data

**Risky:**
- Don't email .pbix with real data (contains your financial info)
- If sharing actual .pbix, use secure file transfer

**Best:** Remove personal data first (File → Options → Data → Remove sensitive info)

---

### Q: Do you offer paid customization?

**A:** Not currently, but open to:
- Custom feature development
- Enterprise versions
- Consulting for specific needs

Contact via GitHub or LinkedIn to discuss.

---

## 🔧 Customization

### Q: Can I add more stocks to the reference list?

**A:** Yes! Two ways:

**Option 1:** Add to `my_custom_stocks.csv` (recommended)
- See [CUSTOM_STOCKS_GUIDE.md](CUSTOM_STOCKS_GUIDE.md)

**Option 2:** Edit `stock_reference_500.csv` directly
- Not recommended (harder to maintain)

---

### Q: Can I create my own sector categories?

**A:** Yes! In custom stocks file, use any sector name you want:

```csv
Symbol,Name,Sector,Subsector
TSLA,Tesla Inc,My EV Stocks,Electric Vehicles
```

This creates a new "My EV Stocks" sector.

---

### Q: Can I add more pages/visuals?

**A:** Absolutely! The .pbix is yours to modify.

**Tips:**
- Duplicate existing page (right-click → Duplicate)
- Use existing measures (don't recreate)
- Match color scheme for consistency
- Save often!

---

### Q: Can I translate to another language?

**A:** Labels and titles can be changed manually:
1. Click on text/title
2. Edit in place
3. Save

Measures and calculated text in DAX would need code changes (more complex).

---

## 🚀 Performance & Technical

### Q: Why is the dashboard slow?

**Common causes:**
- Large portfolio (500+ positions)
- Many visuals on one page
- Low RAM (<8GB)
- Old PowerBI version
- Background applications

**Fixes:**
- Close other programs
- Update PowerBI Desktop
- Simplify visuals (fewer per page)
- Consider upgrading computer

---

### Q: How big of a portfolio can this handle?

**Tested with:**
- ✅ Up to 1,000 positions
- ✅ 10+ accounts
- ✅ Multiple years of data

**Performance depends on your computer, not the dashboard.**

---

### Q: Can I use this on PowerBI Service (web version)?

**A:** Yes, but requires PowerBI Pro license ($10/month).

**Steps:**
1. Publish from Desktop → My Workspace
2. Set up scheduled refresh
3. Share with others (if desired)

**Most users don't need this** - Desktop version is sufficient.

---

### Q: What version of PowerBI do I need?

**A:** 
- **Minimum:** PowerBI Desktop from 2023 or later
- **Recommended:** Latest version (free updates)
- **Download:** https://powerbi.microsoft.com/desktop/

---

### Q: Can I use this on Linux?

**A:** No native support. Options:
- Wine (hit or miss)
- Virtual machine with Windows
- PowerBI Service (web, requires subscription)

---

## 🔒 Privacy & Security

### Q: Is my financial data safe?

**A:** Yes, because it never leaves your computer.

**Security notes:**
- Runs 100% locally
- No internet connection required (after initial download)
- No data transmitted anywhere
- No login required
- No cloud storage

**Your responsibility:**
- Secure your computer
- Don't share .pbix with sensitive data
- Back up files to secure location

---

### Q: Can I remove personal data before sharing?

**A:** Yes! Use sample data:

**Method 1:** Replace your CSV with `sample_portfolio.csv` → Refresh

**Method 2:** PowerBI options:
- File → Options → Data → Remove sensitive information

**Method 3:** Manually clear data:
- Transform Data → Delete rows → Keep structure

---

### Q: Should I store this on cloud (Dropbox, Google Drive)?

**A:** Personal choice:

**Pros:**
- Backup
- Access from multiple devices

**Cons:**
- Financial data in cloud
- Privacy concerns

**Recommendation:** 
- Use encrypted cloud (like Boxcryptor)
- Or keep local backups only

---

## 🆘 Still Need Help?

### Q: I have a question not listed here

**A:** Check these resources:

1. **Documentation:**
   - [README.md](README.md) - Overview
   - [SETUP_GUIDE.md](SETUP_GUIDE.md) - Installation
   - [CUSTOM_STOCKS_GUIDE.md](CUSTOM_STOCKS_GUIDE.md) - Adding stocks
   - [CSV_FORMAT_GUIDE.md](CSV_FORMAT_GUIDE.md) - Data format

2. **Community:**
   - [GitHub Issues](https://github.com/[username]/portfolio-analysis-dashboard/issues)
   - [GitHub Discussions](https://github.com/[username]/portfolio-analysis-dashboard/discussions)

3. **Direct Contact:**
   - Email: [your.email@example.com]
   - LinkedIn: [Your LinkedIn]

---

### Q: I found a bug!

**A:** Thanks for reporting! Please:

1. Check if already reported (GitHub Issues)
2. If new, open an issue with:
   - What you were doing
   - What happened (vs. what should happen)
   - Screenshots if possible
   - Your PowerBI version
   - Sample data if relevant

**We fix critical bugs ASAP.**

---

### Q: Can I contribute to this project?

**A:** Yes! Ways to contribute:

- 🐛 Report bugs
- 💡 Suggest features
- 📖 Improve documentation
- 🔧 Submit pull requests
- ⭐ Star the repository
- 🔗 Share with others

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

### Q: How can I support this project?

**A:** Many ways:

- ⭐ Star on GitHub
- 🔗 Share on LinkedIn/social media
- 📝 Write a review or blog post
- 💬 Answer questions in Discussions
- 🐛 Report bugs thoroughly
- ☕ Buy me a coffee (optional!)

**Your feedback is the best support!**

---

## 📞 Contact

**Creator:** [Your Name]  
**Email:** [your.email@example.com]  
**LinkedIn:** [Your LinkedIn URL]  
**GitHub:** [github.com/yourusername]

---

*Last Updated: October 2025*

---

**Didn't find your answer?** Open an issue on GitHub and we'll add it to this FAQ!
