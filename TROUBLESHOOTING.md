# 🐛 Troubleshooting Guide

**Common issues and quick fixes.**

---

## 📋 Quick Diagnosis

**What's the issue?**
- [Can't find file error](#problem-cant-find-file-error)
- [Numbers look wrong](#problem-numbers-look-wrong)
- [Many "Unknown" stocks](#problem-many-unknown-stocks)
- [Dashboard is slow](#problem-dashboard-is-slow)
- [Cash showing as SPAXX/FDRXX](#problem-cash-showing-as-spaxx)
- [.pbix file won't open](#problem-pbix-file-wont-open)
- [Errors on first open](#problem-errors-when-first-opening)
- [Refresh fails](#problem-refresh-fails)
- [Custom stocks not working](#problem-custom-stocks-not-showing)

---

## 🔧 Common Issues

### **Problem: Can't find file error**

**Symptoms:**
- Error message when opening dashboard
- "Data source error" in Power Query
- Tables show "Error" in visuals

**Causes:**
- File moved to different location
- File renamed
- File on external drive that's not connected

**Fix:**
1. Click **Transform Data** (Home tab)
2. Left pane: Click the query with error (red icon)
3. Right pane: Click ⚙️ gear next to "Source" in Applied Steps
4. Browse to correct file location
5. Click OK
6. Repeat for any other queries with errors
7. Click **Close & Apply**

**Pro tip:** Keep all files in one folder and don't move them!

---

### **Problem: Numbers look wrong**

**Symptoms:**
- Portfolio total doesn't match broker
- Missing accounts
- Wrong stock prices
- Negative values

**Common causes & fixes:**

**Cause 1: Single account export (not "All Accounts")**
- ✅ Fix: Re-export using "All Accounts" option in Fidelity
- Must aggregate all accounts, not just one

**Cause 2: Old data file**
- ✅ Fix: Export fresh CSV from broker
- Check file date modified

**Cause 3: Wrong columns mapped**
- ✅ Fix: Verify CSV has required columns:
  - Account Number, Account Name, Symbol, Quantity, Last Price, Cost Basis Total

**Cause 4: Data corruption**
- ✅ Fix: Open CSV in Notepad (not Excel) - does data look correct?
- If garbled, re-export from broker

**Test:**
1. Open CSV in Notepad
2. Check first few rows have actual numbers
3. Verify columns are present
4. Look for obvious issues

---

### **Problem: Many "Unknown" stocks**

**This is expected!** Reference file has 300+ stocks, but thousands exist.

**Symptoms:**
- Unknown_Stocks_Count > 0 on Welcome page
- Stocks listed under "Unknown Stocks"
- Alert: "X stock(s) need classification"

**This affects:**
- Small-cap stocks
- International stocks (foreign tickers)
- Recently IPO'd companies
- Niche sector stocks
- ETFs not in reference

**Fix:**

Add them to `My_Custom_Stocks.csv`:

1. Note which stocks are unknown (Welcome page lists them)
2. Open `My_Custom_Stocks.csv` in Notepad
3. Add stocks following format:
   ```csv
   Symbol,Name,Sector,Subsector
   YOURTICKER,Company Name,Technology,Software
   ```
4. Save file
5. PowerBI → Home → Refresh
6. Unknown count should decrease

📖 **Detailed guide:** [CUSTOM_STOCKS_GUIDE.md](CUSTOM_STOCKS_GUIDE.md)

**Common sectors:** Technology, Healthcare, Financials, Consumer Discretionary, Consumer Staples, Energy, Industrials, Materials, Real Estate, Utilities, Communication Services

**Not sure of sector?** Google "[ticker] sector"

---

### **Problem: Dashboard is slow**

**Symptoms:**
- Takes long time to load
- Visuals lag when clicking
- Refresh takes minutes
- PowerBI freezes

**Causes & fixes:**

**Cause 1: Large portfolio (500+ positions)**
- ✅ Expected behavior for very large portfolios
- ✅ Fix: Upgrade computer RAM or close other programs

**Cause 2: Old PowerBI version**
- ✅ Fix: Update to latest PowerBI Desktop (2023+)
- ✅ Help → Check for Updates

**Cause 3: Too many programs running**
- ✅ Fix: Close browser, Excel, other heavy programs
- ✅ Restart computer before opening PowerBI

**Cause 4: Complex visuals**
- ✅ Fix: This dashboard is optimized, but if you added custom visuals, simplify them

**Cause 5: Antivirus scanning**
- ✅ Fix: Add PowerBI to antivirus exclusion list
- ✅ Close real-time scanning temporarily

**Performance tips:**
- Close PowerBI when not actively using
- Don't keep multiple .pbix files open
- Use "Refresh" sparingly (only when data changes)

---

### **Problem: Cash showing as SPAXX**

**This is NORMAL!** Not an error.

**Why:**
Fidelity uses money market fund symbols for cash:
- **SPAXX** = Fidelity Government Money Market
- **FDRXX** = Fidelity Treasury Money Market
- **FCASH** = Cash balance

**Dashboard handles this automatically:**
- Recognizes these as cash
- Includes in cash percentage
- Shows in cash analysis

**✅ No action needed!** This is working as designed.

**If you prefer:** You can manually edit your CSV to change SPAXX → CASH before importing, but it's unnecessary.

---

### **Problem: .pbix file won't open**

**Symptoms:**
- Double-click does nothing
- Error message when opening
- File opens in wrong program
- "File is corrupted"

**Fixes:**

**Fix 1: PowerBI Desktop not installed**
- ✅ Install PowerBI Desktop (not just PowerBI mobile/web)
- ✅ Download: [https://powerbi.microsoft.com/desktop/](https://powerbi.microsoft.com/desktop/)

**Fix 2: Old PowerBI version**
- ✅ Dashboard requires PowerBI Desktop 2023+
- ✅ Update: Help → Check for Updates

**Fix 3: File didn't download completely**
- ✅ Check file size: Should be ~200KB
- ✅ If smaller, re-download from GitHub

**Fix 4: File association issue**
- ✅ Right-click .pbix file
- ✅ Open With → Choose PowerBI Desktop
- ✅ Set as default

**Fix 5: Corrupted download**
- ✅ Delete downloaded file
- ✅ Re-download from GitHub Releases
- ✅ Don't open from browser - save to disk first

**Still won't open?**
- Try opening PowerBI Desktop first
- Then File → Open → Browse to .pbix file

---

### **Problem: Errors when first opening**

**Symptoms:**
- Red error messages in visuals
- "Can't load data"
- Blank charts
- "Data source settings" prompt

**This is NORMAL on first open!**

**Why:**
Dashboard doesn't know where YOUR data files are yet. You need to configure paths.

**Fix:**
Follow Step 4 of Setup Guide:
1. Transform Data
2. Update portfolio CSV path
3. Update stock_reference_base.csv path
4. Confirm My_Custom_Stocks.csv path (should work if in same folder)
5. Close & Apply

**After configuration:** Errors disappear and data loads! ✅

---

### **Problem: Refresh fails**

**Symptoms:**
- Click Refresh → Error
- "Data source error"
- Some tables refresh, others don't
- Refresh completes but shows old data

**Causes & fixes:**

**Cause 1: File moved/renamed**
- ✅ Fix: Update data source paths in Power Query
- ✅ Click error query → Gear icon → Update path

**Cause 2: File is open in another program**
- ✅ Fix: Close Excel, Notepad, any program with CSV open
- ✅ Then refresh again

**Cause 3: File locked by antivirus**
- ✅ Fix: Temporarily disable antivirus
- ✅ Add folder to exclusion list

**Cause 4: Corrupted CSV**
- ✅ Fix: Re-export from broker
- ✅ Don't edit CSV in Excel before import

**Cause 5: Missing custom stocks file**
- ✅ Fix: Ensure My_Custom_Stocks.csv exists in same folder
- ✅ Even if empty, file must exist

**Force refresh:**
1. Transform Data
2. Right-click Portfolio_Position query
3. Refresh Preview
4. Close & Apply

---

### **Problem: Custom stocks not showing**

**Symptoms:**
- Added stocks to My_Custom_Stocks.csv
- Refreshed dashboard
- Stocks still show as "Unknown"

**Checklist:**

**[ ] File saved correctly?**
- Open My_Custom_Stocks.csv in Notepad
- Verify changes are there
- File should end in .csv not .txt

**[ ] Symbol spelling exact?**
- Must match portfolio CSV exactly
- Case sensitive! (GOOGL ≠ googl)
- No extra spaces

**[ ] Header row present?**
- First line must be: Symbol,Name,Sector,Subsector
- Don't delete header!

**[ ] Format correct?**
- No spaces after commas
- All 4 columns present
- No blank rows in middle of data

**[ ] File imported to PowerBI?**
- Transform Data → Check left pane
- Should see "My_Custom_Stocks" query
- If missing, re-import: Home → New Source → CSV

**[ ] Refreshed after saving?**
- Must click Refresh in PowerBI
- Wait for refresh to complete (10-30 sec)

**Still not working?**

Try this:
1. Transform Data
2. Right-click Stock_Reference_Master query
3. Click "Refresh Preview"
4. Check if your stocks appear in preview
5. Close & Apply

**If they appear in preview but not dashboard:**
- Check if you own that stock in current portfolio
- Verify symbol spelling in portfolio matches custom stocks exactly

---

## 🔍 Advanced Debugging

### **Check Data in Power Query**

**View what PowerBI sees:**
1. Transform Data
2. Click any query (Portfolio_Position, Stock_Reference_Master)
3. Look at data preview - does it look correct?
4. Check "Applied Steps" - any errors (⚠️ icon)?
5. Click each step to see what it does

**Common Power Query issues:**
- "Type mismatch" → Column has mixed data types (numbers and text)
- "Expression.Error" → Formula syntax issue
- "DataSource.Error" → Can't find file

---

### **Reset Data Sources**

**Nuclear option - start fresh:**

1. Transform Data
2. Home → Data source settings
3. Click each data source
4. Click "Change Source"
5. Browse to correct file
6. Click OK
7. Close dialog
8. Close & Apply

This reconfigures ALL paths at once.

---

### **Check for Updates**

**Ensure latest version:**
- PowerBI Desktop: Help → Check for Updates
- Dashboard: Re-download from GitHub if >3 months old

---

## 🆘 Still Stuck?

**Before asking for help, gather this info:**
1. PowerBI Desktop version (Help → About)
2. Error message text (screenshot if possible)
3. What you were doing when error occurred
4. Steps you already tried

**Get help:**
- 📖 Check [FAQ.md](FAQ.md) for common questions
- 💬 [GitHub Discussions](https://github.com/girdharsumit-ctrl/portfolio-analysis-dashboard/discussions)
- 🐛 [Report Issue](https://github.com/girdharsumit-ctrl/portfolio-analysis-dashboard/issues)
- 📧 Email: girdharsumit@gmail.com (Add "PAD" in subject line)

---

## 💡 Prevention Tips

**Avoid issues before they happen:**

**File management:**
- Keep all files in one dedicated folder
- Don't rename files after setup
- Don't move files to different drives
- Use consistent naming (portfolio.csv, not portfolio_v2_final_FINAL.csv)

**Data hygiene:**
- Export fresh CSV from broker monthly
- Don't edit CSV in Excel (use Notepad if needed)
- Verify export completes fully before importing

**PowerBI best practices:**
- Close PowerBI when not using (saves RAM)
- Update PowerBI regularly
- Don't modify queries unless you know what you're doing
- Make backups before making changes

**Performance:**
- Refresh only when data actually changes
- Close other heavy programs when using PowerBI
- Consider upgrading RAM if you have 500+ positions

---

**Most issues have simple fixes!** Work through the checklist and you'll be back up and running. 🚀

*Last updated: November 2025*
