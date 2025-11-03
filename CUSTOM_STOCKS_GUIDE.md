# 🎨 Custom Stocks Guide

**Add stocks not in the reference list - they stay classified forever.**

---

## 🤔 When You Need This

**Alert on Welcome page:**
```
ACTION REQUIRED
⚠️ 3 stock(s) need classification
HUCKOO, LLY, PUCOO
```

These stocks aren't in the reference database. Add them once - they stay forever!

---

## 🤖 AI Shortcut (30 Seconds) - Fastest Method

**Classify multiple stocks instantly:**

1. **Copy symbols** from Welcome page table (right-click → Copy)

2. **Ask AI:** Paste this into ChatGPT/Claude:
```
   Give me these stocks in CSV format (Symbol,Name,Sector,Subsector):
   [paste your symbols here]
```

3. **AI responds:**
```csv
   Symbol,Name,Sector,Subsector
   BRKB,Berkshire Hathaway Inc,Financials,Diversified Financials
   DGRO,iShares Dividend Growth ETF,Financials,ETF
```

4. **Copy AI response** → Paste into `My_Custom_Stocks.csv` → Save → Refresh PowerBI ✅

**Done! Multiple stocks classified in 30 seconds.**

---

## ✏️ Manual Method (If You Prefer)

**You already have `My_Custom_Stocks.csv` from setup.**

1. Open `My_Custom_Stocks.csv` in **Notepad** (NOT Excel)
2. Add your stocks following the format below
3. Save and close
4. PowerBI → **Home** → **Refresh** → Done! ✅

**🎉 They stay classified forever** - even when you upload next month's portfolio!

---

## 📋 Format Rules
```csv
Symbol,Name,Sector,Subsector
TICKER,Company Name,Sector,Subsector
```

**Must-know:**
- Keep header row (don't delete first line)
- Symbol must match portfolio exactly
- No spaces after commas
- Use Notepad (NOT Excel)

---

## 📚 Sector Examples

**Common sectors:** Technology, Healthcare, Financials, Consumer Discretionary, Consumer Staples, Energy, Industrials, Materials, Real Estate, Utilities, Communication Services

**Subsector examples:**
- Technology → Software, Hardware, Semiconductors
- Healthcare → Pharmaceuticals, Biotechnology, Medical Devices
- Financials → Banking, Insurance

**Not sure?** Google: "[stock ticker] sector"

---

## 💡 Example
```csv
Symbol,Name,Sector,Subsector
LLY,Eli Lilly and Co,Healthcare,Pharmaceuticals
NVO,Novo Nordisk A/S,Healthcare,Pharmaceuticals
SMCI,Super Micro Computer Inc,Technology,Hardware
```

**Your classifications override the reference file!** Use this to reclassify any stock.

---

## ❌ Common Mistakes

**Don't open in Excel** → Use Notepad  
**Don't add spaces** → `Symbol,Name` not `Symbol, Name`  
**Check spelling** → Symbol must match portfolio exactly  

---

## 🔄 Monthly Updates

**Every month:**
1. Export new portfolio from broker
2. Refresh PowerBI
3. **Custom stocks automatically stay classified** ✅

**Add once. Works forever.**

---

## 🐛 Still Not Working?

- Symbol matches portfolio exactly? (case sensitive!)
- File saved as `.csv` not `.txt`?
- Header row present?
- Refreshed PowerBI after saving?

**Still stuck?** girdharsumit@gmail.com

---

*Quick guide - detailed docs in main repository*
