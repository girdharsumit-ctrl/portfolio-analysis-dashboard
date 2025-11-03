# 🛠️ Setup Guide

**Get your dashboard running in 10 minutes.**

---

## 📋 What You Need

- ✅ **PowerBI Desktop** (free) - [Download here](https://powerbi.microsoft.com/desktop/)
- ✅ **Portfolio CSV** from your broker

---

## 📥 Step 1: Export Your Portfolio Data

### **For Fidelity Users (Recommended - No Formatting Needed)**

**Quick export:**

1. Log into **Fidelity.com**
2. Go to **Accounts** tab
3. Click **"All Accounts"** (right side) ← **Important!**
4. Click **"Positions"** tab
5. Click **three dots (⋮)** in top-right corner above position columns
6. Select **"Download"** → **"Spreadsheet (CSV)"**
7. Save file (don't open it!). Keeping a common location for all dashboard related files is highly recommended.


**Why "All Accounts"?**
- Pulls data from ALL your accounts (IRA, Roth, Individual, TOD) in one file
- Dashboard aggregates everything automatically

**✅ That's it!** Import directly into PowerBI - no editing required.
---

## 🧹 What PowerBI Handles Automatically

**Important: Don't edit your CSV file!**

Your Fidelity export looks messy - blank rows, footer text, dollar signs. **That's normal!** 

**PowerBI automatically cleans:**

✅ **Blank rows** - Removed automatically  
✅ **Footer text** - "Positions are only..." filtered out  
✅ **Extra columns** - Ignored if not needed  
✅ **Cash symbols** - SPAXX, FDRXX recognized as cash  
✅ **Currency symbols** - $ converted to numbers  
✅ **Percentage signs** - 42.27% → 0.4227  
✅ **Messy formatting** - All cleaned behind the scenes  

**Power Query cleanup (automatic). Some examples:**
1. Removes rows where Symbol is blank
2. Filters out footer disclaimer text
3. Converts "$178.50" → 178.50
4. Converts "42.27%" → 0.4227
5. Sets correct data types
6. Creates table relationships


**You do nothing - PowerBI does it all!** Just download → import → done. ✅

---
### **For Other Brokers (Schwab, Vanguard, E*TRADE, etc.)**

**Your CSV needs these 6 data points:**

| Required Data | Your Broker Might Call It |
|---------------|---------------------------|
| Account Number/ID | `Account Number`, `Account ID`, `Account` |
| Account Name/Type | `Account Name`, `Account Type`, `Type` |
| Symbol/Ticker | `Symbol`, `Ticker`, `Stock Symbol` |
| Quantity/Shares | `Quantity`, `Shares`, `Units`, `Shares Held` |
| Current Price | `Last Price`, `Current Price`, `Price`, `Quote` |
| Cost Basis | `Cost Basis Total`, `Total Cost`, `Cost Basis`, `Book Value` |

**Example from Schwab export:**
```csv
Account,Description,Symbol,Quantity,Price,Cost Basis
12345678,IRA,AAPL,25,$150.25,"$3,500.00"
12345679,Individual,MSFT,50,$380.50,"$18,000.00"
```
**You do nothing - PowerBI does it all!** 
**Don't clean this!** PowerBI handles:
- ✅ $ signs → Removed automatically
- ✅ Commas in numbers → Removed automatically  
- ✅ Quotes around values → Handled automatically
- ✅ Different column names → You'll map them in setup

**Just export from your broker and import as-is.**


---
## 💻 Step 2: Install PowerBI Desktop

1. **Download PowerBI Desktop:**
   - Go to [Microsoft PowerBI](https://powerbi.microsoft.com/desktop/)
   - Click "Download Free"
   - Install (takes 2-3 minutes)

2. **System requirements:**
   - Windows 10/11 (native support)
   - Mac users: Use Parallels, VMware, or Boot Camp

**Don't open anything yet!** First, download the required files in Step 3.

---
## 🔄 Step 3: Load Your Data
### **📥 Download Required Files First**

**Before opening PowerBI, download these 3 files:**

1. **stock_reference_base.csv** - Pre-classified stock database (300+ stocks)
2. **My_Custom_Stocks.csv** - Template for adding your own stocks that are not available in the stock_reference_base.csv
3. **PortfolioAnalysisDashboard_v1.0.pbix** - The PowerBI dashboard

**Important:** Save all three files to the same folder on your computer (e.g., `Documents/PortfolioDashboard/`)

**What are these files?**

**stock_reference_base.csv:**  
Contains 300+ pre-classified stocks (AAPL, MSFT, GOOGL, TSLA, etc.) with their sectors and subsectors. The dashboard uses this to automatically classify stocks in your portfolio.

**My_Custom_Stocks.csv:**  
Template file for adding stocks not in the reference database. Includes example stocks (LLY, NVO) showing the correct format. You'll use this if you see "Unknown Stocks" alerts.

**Download from GitHub:**
- Go to [Releases](https://github.com/girdharsumit-ctrl/portfolio-analysis-dashboard/releases)
- Download all three files from the latest release
- Extract to a folder you'll remember

---
### 🔧 Step 4: Configure Data Sources

**Now open the dashboard and connect your data:**

**⚠️ Errors on first open are normal!** Data not connected yet - fix in next step.

1. **Open the dashboard:**
   - Double-click `PortfolioAnalysisDashboard_v1.0.pbix`
   - PowerBI Desktop opens

2. **Open Power Query:**
   - Click **Home** tab → **Transform Data**
   - Power Query Editor opens

3. **Update portfolio file path:**
   - Left pane: Click **Portfolio_Position** query
   - Right pane (Applied Steps): Click ⚙️ gear icon next to **"Source"**
   - Browse to YOUR `portfolio.csv` file (exported from broker)
   - Click OK

4. **Update stock reference path:**
   - Left pane: Click **Stock_Reference_Base** query
   - Right pane: Click ⚙️ gear next to **"Source"**
   - Browse to `stock_reference_base.csv`
   - Click OK
    **Right-click the new query** → **Uncheck "Enable Load"**
   - This connects the file but doesn't create a separate table

5. **Import custom stocks template (one-time setup):**
   - Click **Home** tab → **New Source** → **Text/CSV**
   - Browse to `My_Custom_Stocks.csv`
   - Click **Open** → Click **OK** (on preview screen)   
   - **Right-click the new query** → **Uncheck "Enable Load"**
   - This connects the file but doesn't create a separate table
   
   **Why do this now?** Even if you don't need custom stocks yet, setting this up 
   now means when you DO need it later, you just edit the CSV and refresh—no need 
   to mess with Power Query again!

6. **Apply changes:**
   - Click **Close & Apply** (top-left)
   - PowerBI will refresh with YOUR data (10-30 seconds)

**✅ Done!** Your dashboard is fully configured.

---
## ✅ Step 5: Verify Everything Works

**Check Welcome page:**
- Total Portfolio Value matches your actual total? ✅
- Total Stocks count looks right? ✅
- All accounts listed? ✅

**Check Sector Analysis:**
- Sectors showing correctly? ✅
- Pie chart makes sense? ✅
- Cash amount accurate? ✅

**See "Unknown Stocks" alert in your Dashboard?**

Some stocks aren't in the reference database (small-cap, international, niche sectors).

**Quick fix:**
1. Open `My_Custom_Stocks.csv` (already connected in Step 4)
2. Add your stocks following the format shown in the file
3. Save → Refresh PowerBI

📖 **Detailed guide:** [CUSTOM_STOCKS_GUIDE.md](CUSTOM_STOCKS_GUIDE.md)

---
## 🐛 Still Having Issues?

**Common problems:**
- **Can't find file error** → Power Query → Click error → Update file path
- **Numbers look wrong** → Verify using "All Accounts" export (not single account)
- **Many unknown stocks** → Edit My_Custom_Stocks.csv and refresh
- **.pbix won't open** → Ensure PowerBI Desktop 2023+ is installed

📖 **Full troubleshooting guide:** [TROUBLESHOOTING.md](TROUBLESHOOTING.md)
