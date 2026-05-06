# spm_setup_hold_fixed
SPM Setup & Hold Timing Fix (Physical Design Project)

# Overview

This project demonstrates fixing setup and hold timing violations in a simple SPM (Static Physical Module) design using a standard PD flow.

The goal was to convert negative slack (timing violations) into positive slack (timing clean design) and validate the improvement with logs, reports, and layout results.

---

# Design Details

- RTL Files: "rtl.v", "synthesis.v"
- Configuration: "config.json"
- Flow: Synthesis → Floorplan → Placement → CTS → Routing

---

# Problem Statement

Initial run (Run1_before_fix) showed:

- Negative Setup Slack
- Negative Hold Slack
-  Possible congestion / placement inefficiencies

These issues can lead to functional failure in silicon if not fixed.

---

# Root Cause (Assumed)

- Sub-optimal placement
- Routing congestion
- Clock tree imbalance
- Timing path delays

---

# Fix Applied

Timing was improved by tuning:

- Placement strategy
- Routing optimization
- Clock Tree Synthesis (CTS)
- Configuration parameters ("config.json")

---

# Results Comparison

* Before Fix (Run1)

- Setup Slack: Negative 
- Hold Slack: Negative 
- Evidence:
  - Logs: "Run1_before_fix/logs/"
  - DEF: "Run1_before_fix/results/"
  - Screenshots: timing violation & layout view


 * After Fix (Run2)
   tr
- Setup Slack: Positive 
- Hold Slack: Positive 
- Evidence:
  - Logs: "Run2_after_fixed/logs/"
  - DEF: "Run2_after_fixed/results/"
  - Screenshots: clean timing & improved layout

---

# Repository Structure

Run1_before_fix/
  ├── logs/
  ├── results/ (DEF)
  └── screenshots/

Run2_after_fixed/
  ├── logs/
  ├── results/ (DEF)
  └── screenshots/

rtl.v
synthesis.v
config.json
README.md

---

# Key Observations

- Timing violations successfully removed
- Improved placement and routing quality
- Clean final DEF indicates better physical implementation

---

 # Conclusion

This project shows a complete timing closure cycle:

- Identify timing violations
- Analyze root cause
- Apply PD optimizations
- Verify improvement with reports

---

* Future Improvements

- Add detailed timing report comparison (numerical values)
- Include congestion maps
- Automate flow using scripts
