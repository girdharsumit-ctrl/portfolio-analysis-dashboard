# 💼 Portfolio Analysis Dashboard - Project Overview

**For recruiters and hiring managers**

*Project completed November 2025*

**Seeking Product Manager, Technical Analyst, or Business Intelligence roles that leverage operational analytics, product strategy, and technical execution.**

---

## 🎯 Project Summary

**What:** Open-source PowerBI dashboard for multi-account investment portfolio analysis  
**Timeline:** September - November 2025 (2 months)  
**Status:** Live v1.0   
**Role:** Product Manager, Developer, Technical Writer

**Repository:** [github.com/girdharsumit-ctrl/portfolio-analysis-dashboard](https://github.com/girdharsumit-ctrl/portfolio-analysis-dashboard)

---

## 💡 The Problem

**User pain point identified:**
Investors with multiple accounts (IRA, Roth, 401k, Individual) lack visibility into total portfolio allocation. Major brokerages (Fidelity, Schwab, Vanguard) only show account-level data, forcing manual Excel aggregation.

**Gap in market:**
- Brokers won't aggregate across account types (regulatory/technical limitations)
- Third-party tools require linking accounts (privacy concerns + $99+/year)
- No solution for actionable insights (alerts, unknown stock handling)

**Target user:** Self-directed investors with 2+ accounts wanting privacy and control

---

## ✅ Solution Delivered

**Built:** Multi-account portfolio aggregation dashboard with intelligent alerts and custom classification system

**Core capabilities:**
- Aggregate unlimited accounts in single view
- Sector/subsector analysis with visual breakdown
- Smart alerts (cash deployment, unknown stocks)
- Extensible classification system (300+ stocks + user additions)
- 100% offline privacy (no cloud, no account linking)

**Value proposition:** "Get insights in 5 minutes that take brokers' tools 30+ minutes to piece together manually"

---

## 🛠️ Technical Implementation

**Technology stack:**
- PowerBI Desktop (visualization & data modeling)
- DAX (27+ custom measures for calculations)
- Power Query (M language for ETL pipeline)
- GitHub (version control & distribution)
- Claude AI (development acceleration)

**Key technical achievements:**

**1. Automated ETL Pipeline**
- Handles messy broker exports (blank rows, footer text, currency symbols)
- Zero manual preprocessing required by user
- Reduced setup time from 30+ minutes to <5 minutes

**2. Dynamic Data Model**
- Relationships across 4 fact tables
- Append query for custom stock integration
- Persistent classifications across monthly refreshes

**3. Custom DAX Measures (27+)**
Examples:
- `Total_Portfolio_Value` - Sum across all accounts with error handling
- `Cash_Percentage` - Identifies SPAXX/FDRXX as cash automatically
- `Unknown_Stocks_Count` - Alerts users to unclassified positions
- `Sector_Allocation` - Multi-level drill-down (Sector → Subsector → Position)

**4. Scalable Architecture**
- Designed to support v2.0 features (time-based analytics, API integration)
- Documented data model for future contributors
- Modular query structure

---

## 📊 Skills Demonstrated

### **Product Management**
- Identified real user problem through personal experience
- Defined MVP scope (shipped v1.0 in 8 weeks)
- Created product roadmap with user feedback loops
- Prioritized features by user impact vs. development effort

### **Technical Execution**
- Data modeling & DAX optimization
- ETL pipeline development (Power Query)
- Version control (Git/GitHub)
- Open source deployment & release management

### **User-Centric Design**
- Actionable alerts (not just data dumps)
- Progressive disclosure (simple default view, details on click)
- Error prevention (automated data cleaning)
- Self-service documentation (users deploy without support)

### **Technical Writing**
- 8 comprehensive guides (Setup, Troubleshooting, FAQ, Custom Stocks, Roadmap)
- ~100 pages total documentation
- Structured for progressive learning (Quick Start → Deep Dive)
- Screenshots & examples throughout

### **AI-Assisted Development**
- Collaborated with Claude AI for code optimization
- Human-defined requirements, AI-accelerated implementation
- 3-4x development speed vs. solo effort
- Demonstrates modern workflow proficiency

---

## 📈 Impact & Results

**User benefits:**
- Reduce portfolio analysis time from 30+ minutes to instant
- Get actionable alerts brokers don't provide
- Maintain 100% data privacy (vs. account linking)
- Classify 100% of holdings (vs. "Unknown" in broker tools)

**Quantifiable outcomes:**
- 300+ pre-classified stocks included
- Zero setup errors reported (automated validation)
- <5 minute average setup time (tracked via user feedback)
- 100% offline functionality (no dependencies)

**Open source impact:**
- MIT license (freely usable)
- GitHub deployment with release management
- Community contribution framework
- Professional documentation standard

---

## 🎯 Product Roadmap Management

**Shipped (v1.0):**
Core aggregation, sector analysis, alerts, custom classifications

**Planned (v2.0):**
Time-based performance tracking, holding period analysis

**Exploring (v3.0):**
Dividend Income Tracking
And/Or 
Real-time price APIs, tax optimization, risk analytics

**Philosophy:** Ship MVP fast, iterate based on real user feedback vs. building assumed features

---

## 🤝 Human-AI Collaboration

**My role (Product & Strategy):**
- Identified investor problem
- Defined product requirements
- Designed data model architecture
- Specified financial calculations
- Made all product decisions
- Created user experience flows

**Claude AI's role (Development Acceleration):**
- DAX formula optimization
- Power Query best practices
- Documentation structure
- Code pattern suggestions
- Development speed: 3-4x faster

**Key insight:** AI accelerates execution but doesn't replace product thinking, domain expertise, or strategic decision-making

---

## 💼 Relevant to Product Manager Roles

**This project demonstrates:**

✅ **Problem identification** - Recognized gap through personal experience  
✅ **User research** - Analyzed broker limitations & user needs  
✅ **MVP scoping** - Shipped v1.0 in 8 weeks with core value  
✅ **Technical collaboration** - Worked with AI like working with engineering team  
✅ **Documentation excellence** - 8 guides enabling self-service  
✅ **Roadmap planning** - Vision with user feedback integration  
✅ **Stakeholder communication** - Clear documentation for multiple audiences  
✅ **Shipping mindset** - Launched real product vs. perpetual planning  

**Transferable to PM roles in:**
- Financial technology
- Data visualization
- Analytics tools
- B2C products
- Self-service platforms
- Workforce Management / Optimization- Forecast, Capacity Planning, Scheduling
- ETL

https://www.linkedin.com/in/sumitgirdhar/

---

## 📞 Discussion Points for Interviews

**Technical depth:**
- Data modeling decisions (star schema, fact tables)
- DAX optimization for performance
- Error handling strategy (graceful degradation)

**Product thinking:**
- Why MVP first vs. feature-complete v1.0?
- How to prioritize v2.0 features based on user feedback?
- Trade-offs: privacy vs. convenience (offline vs. API integration)

**Process:**
- How AI collaboration works in practice
- Documentation as product (not afterthought)
- Open source community management

---

## 🔗 Resources

**Live project:**
- GitHub: [portfolio-analysis-dashboard](https://github.com/girdharsumit-ctrl/portfolio-analysis-dashboard)
- Download: [Latest release](https://github.com/girdharsumit-ctrl/portfolio-analysis-dashboard/releases)
- Documentation: [Full guides](https://github.com/girdharsumit-ctrl/portfolio-analysis-dashboard#documentation)

**Contact:**
- Email: girdharsumit@gmail.com
- LinkedIn: [linkedin.com/in/sumitgirdhar](https://www.linkedin.com/in/sumitgirdhar)

---

## 🎓 Key Takeaways

**For hiring managers:**

This project shows I can:
1. **Identify real problems** and scope solutions
2. **Ship products** end-to-end (not just plans)
3. **Use modern tools** (AI, GitHub, PowerBI) effectively
4. **Document thoroughly** for user success
5. **Think strategically** (roadmap, user feedback loops)

**Bottom line:** Built a working product that solves a real problem, deployed it professionally, and positioned it for growth based on user needs.

---

*Project completed November 2025*

**Seeking Product Manager, Technical Analyst, or Business Intelligence roles that leverage operational analytics, product strategy, and technical execution.**