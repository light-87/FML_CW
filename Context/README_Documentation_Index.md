# EEEM066 Coursework - Complete Documentation Index

## 📚 Overview

I've created comprehensive documentation for your coursework with all experiments, configurations, and detailed instructions. Below is a guide to all materials.

---

## **📋 Documents Created**

### **1. Coursework_Experiments_Checklist.md** (21 KB)
**Most Comprehensive Reference**

This is your main checklist document containing:
- ✅ Quick configuration reference guide (what changes in each section)
- ✅ Fixed values across experiments (what stays the same)
- ✅ Detailed breakdown of all 15 experiments with configurations
- ✅ Section-by-section explanation:
  - Section 1: 3 architecture experiments (1.1.1, 1.2.1, 1.3.1)
  - Section 2: 4 augmentation experiments (2.1.1, 2.1.2, 2.1.3, 2.2.1)
  - Section 3.1: 4 learning rate experiments (3.1.0, 3.1.1, 3.1.2, 3.1.3)
  - Section 3.2: 4 batch size experiments (3.2.0, 3.2.1, 3.2.2, 3.2.3)
- ✅ Complete experiment matrix with all configurations
- ✅ Progress tracker checklist
- ✅ Critical chain of dependencies

**👉 USE THIS FOR:** Detailed reference while working on coursework

---

### **2. Experiment_Command_Reference.md** (9.6 KB)
**Command-Line Guide**

This document provides:
- ✅ Example commands for Google Colab for each experiment
- ✅ Exact parameters to use for each section
- ✅ Troubleshooting tips
- ✅ Quick lookup tables
- ✅ GPU monitoring commands
- ✅ Augmentation technique options
- ✅ LR and BS strategy guides

**👉 USE THIS FOR:** Running experiments in Google Colab

---

### **3. One_Page_Visual_Summary.md** (15 KB)
**Visual Overview**

This document contains:
- ✅ ASCII art flowchart of all 15 experiments
- ✅ Visual representation of what changes in each section
- ✅ Quick reference matrix (what to keep constant)
- ✅ Execution flow diagram
- ✅ Key constraints (DO's and DON'Ts)
- ✅ Marks breakdown
- ✅ Quick lookup sheet for recording values

**👉 USE THIS FOR:** Quick visual understanding and planning

---

## **🎯 Quick Navigation**

### **Starting Out?**
1. Read: `One_Page_Visual_Summary.md` - Get the big picture
2. Reference: `Coursework_Experiments_Checklist.md` - Understand each experiment
3. Use: `Experiment_Command_Reference.md` - Run the experiments

### **Running an Experiment?**
1. Open: `Coursework_Experiments_Checklist.md`
2. Find your experiment (e.g., Exp 1.1.1)
3. Check configuration details
4. Use command template from `Experiment_Command_Reference.md`

### **Comparing Results?**
1. Use: `Coursework_Experiments_Checklist.md`
2. Look at: "What to document for this experiment"
3. Create comparison tables as specified

---

## **📊 Summary of All 15 Experiments**

### **SECTION 1: Architectures (40 marks)**
- Exp 1.1.1 → `log_sec1_q1.txt` → Default model (record LR & BS)
- Exp 1.2.1 → `log_sec1_q2.txt` → Different CNN (use recorded LR & BS)
- Exp 1.3.1 → `log_sec1_q3.txt` → Third architecture (use recorded LR & BS)

### **SECTION 2: Augmentation (30 marks)**
- Exp 2.1.1 → `log_sec2_q1_baseline.txt` → Default augmentation only
- Exp 2.1.2 → `log_sec2_q1_aug1.txt` → Augmentation technique #1
- Exp 2.1.3 → `log_sec2_q1_aug2.txt` → Augmentation technique #2
- Exp 2.2.1 → `log_sec2_q2.txt` → Combined augmentations

### **SECTION 3.1: Learning Rates (10 marks)**
- Exp 3.1.0 → `log_sec3_q1_lr_default.txt` → Default LR baseline
- Exp 3.1.1 → `log_sec3_q1_lr1.txt` → LR test value 1
- Exp 3.1.2 → `log_sec3_q1_lr2.txt` → LR test value 2
- Exp 3.1.3 → `log_sec3_q1_lr3.txt` → LR test value 3 ⭐ **PICK BEST**

### **SECTION 3.2: Batch Sizes (10 marks)**
- Exp 3.2.0 → `log_sec3_q2_bs_default.txt` → Default BS (use BEST LR from 3.1)
- Exp 3.2.1 → `log_sec3_q2_bs1.txt` → BS value 1 (use BEST LR from 3.1)
- Exp 3.2.2 → `log_sec3_q2_bs2.txt` → BS value 2 (use BEST LR from 3.1)
- Exp 3.2.3 → `log_sec3_q2_bs3.txt` → BS value 3 (use BEST LR from 3.1)

---

## **⭐ Key Points to Remember**

### **Critical Dependencies:**
```
Exp 1.1.1 (record Default LR & BS)
    ↓
Use in ALL Sec 2 & 3 experiments
    ↓
Sec 3.1: Find BEST LR
    ↓
Sec 3.2: Use BEST LR (not default!)
```

### **What Changes Where:**
- **Section 1**: Only model architecture changes
- **Section 2**: Only data augmentation changes
- **Section 3.1**: Only learning rate changes
- **Section 3.2**: Only batch size changes (use best LR from 3.1)

### **What Stays Same:**
- Keep all other parameters identical for fair comparison
- Report metrics on TEST SET (not train/validation)
- Each experiment: change only ONE thing

---

## **📝 How to Use These Documents**

### **Before Starting:**
- [ ] Read `One_Page_Visual_Summary.md` (5 mins)
- [ ] Understand the flow and dependencies
- [ ] Record default values in your notes

### **While Working:**
- [ ] Keep `Coursework_Experiments_Checklist.md` open
- [ ] Check configuration for each experiment
- [ ] Use `Experiment_Command_Reference.md` for commands
- [ ] Update progress tracker checklist

### **During Documentation:**
- [ ] Follow "What to document" sections
- [ ] Create comparison tables as specified
- [ ] Keep 200-word limit per section
- [ ] Report TEST set metrics only

### **When Comparing Results:**
- [ ] Use the detailed experiment matrix
- [ ] Create side-by-side comparison tables
- [ ] Explain differences in performance
- [ ] Link back to configuration changes

---

## **🔍 Quick Reference Lookup**

### **"How do I run Exp 2.1.2?"**
1. Open: `Coursework_Experiments_Checklist.md` → Search "Question 2.1"
2. Find: Section showing Exp 2.1.2 configuration details
3. Use: `Experiment_Command_Reference.md` → Search "Exp 2.1.2"
4. Copy: Command template and fill in values

### **"Which experiments use the same LR?"**
1. Open: `One_Page_Visual_Summary.md` → View experiment boxes
2. All experiments with ✅ next to LR use the SAME value
3. Only Section 3.1 and 3.2 have ❌ (meaning changes)

### **"What's my best LR for Section 3.2?"**
1. Run all Section 3.1 experiments (3.1.0, 3.1.1, 3.1.2, 3.1.3)
2. Compare mAP scores
3. The LR with HIGHEST mAP = BEST LR
4. Use that value in all Section 3.2 experiments

### **"How many log files do I need?"**
- **Total**: 15 log files
- **Section 1**: 3 files
- **Section 2**: 4 files
- **Section 3.1**: 4 files
- **Section 3.2**: 4 files

---

## **📊 Document Structure Map**

```
Coursework_Experiments_Checklist.md
├─ Quick Configuration Reference Guide
│  ├─ What Changes in Each Section
│  └─ Fixed Values Across Experiments
├─ Section 1: Code Familiarity (40 marks)
│  ├─ Q1.1: Default Code (1 experiment)
│  ├─ Q1.2: Different CNN (1 experiment)
│  └─ Q1.3: Third Architecture (1 experiment)
├─ Section 2: Augmentation (30 marks)
│  ├─ Q2.1: Additional Techniques (3 experiments)
│  └─ Q2.2: Best Combination (1 experiment)
├─ Section 3.1: Learning Rates (10 marks)
│  └─ Q3.1: LR Exploration (4 experiments)
├─ Section 3.2: Batch Sizes (10 marks)
│  └─ Q3.2: BS Exploration (4 experiments)
├─ Detailed Experiment Matrix
├─ Important Notes
├─ Experiment Progress Tracker
└─ Submission Checklist

Experiment_Command_Reference.md
├─ Section 1 Commands (3 experiments)
├─ Section 2 Commands (4 experiments)
├─ Section 3.1 Commands (4 experiments)
├─ Section 3.2 Commands (4 experiments)
├─ Quick Lookup Tables
├─ Troubleshooting
└─ Monitoring Commands

One_Page_Visual_Summary.md
├─ ASCII Art Visualization (all 15 experiments)
├─ Quick Reference Matrix
├─ Execution Flow Diagram
├─ Key Constraints
├─ Marks Breakdown
└─ Quick Lookup Sheet
```

---

## **✅ Submission Checklist**

### **Report Content:**
- [ ] Section 1.1: Default code explanation (20 marks)
- [ ] Section 1.2: CNN variant comparison (10 marks)
- [ ] Section 1.3: Third architecture comparison (10 marks)
- [ ] Section 2.1: Augmentation techniques (20 marks)
- [ ] Section 2.2: Best combination (10 marks)
- [ ] Section 3.1: Learning rate analysis (10 marks)
- [ ] Section 3.2: Batch size analysis (10 marks)
- [ ] Presentation & clarity (10 marks)

### **Files to Submit:**
- [ ] 15 Log files (naming: `log_sec{S}_q{Q}[_descriptor].txt`)
- [ ] 1 Report file (Word or PDF)
- [ ] Filename: `EEEM066-[YOUR_URN]-Assignment`

### **Requirements:**
- [ ] Report ≤ 200 words per section (excluding tables/plots)
- [ ] All metrics reported on TEST set
- [ ] Comparison tables included
- [ ] Figures/plots labeled clearly
- [ ] Harvard or IEEE references included
- [ ] No plagiarism (properly attributed sources)

---

## **📅 Timeline Recommendation**

### **Week 1-2:**
- Read all documentation
- Set up Google Colab
- Run Exp 1.1.1 and record default values

### **Week 3-4:**
- Complete all Section 1 experiments (1.1.1, 1.2.1, 1.3.1)
- Document findings

### **Week 5-6:**
- Complete all Section 2 experiments (2.1.1-2.2.1)
- Analyze augmentation impact

### **Week 7-8:**
- Complete Section 3.1 (identify best LR)
- Complete Section 3.2 (using best LR)
- Analyze hyperparameter impact

### **Week 9-10:**
- Compile final report
- Create comparison tables and visualizations
- Proofread and format
- Prepare all 15 log files

### **Before Deadline:**
- [ ] Final submission review
- [ ] Check file naming
- [ ] Verify all 15 log files present
- [ ] Submit via SurreyLearn before 4:00 PM, 2nd Dec 2025

---

## **🆘 Troubleshooting Guide**

### **"I'm confused about what to keep constant"**
→ Check `One_Page_Visual_Summary.md` Quick Reference Matrix

### **"What command should I use?"**
→ Go to `Experiment_Command_Reference.md` and search your experiment

### **"I don't understand what to document"**
→ Find your question in `Coursework_Experiments_Checklist.md` under "What to document"

### **"How do I know which experiments are done?"**
→ Use the Progress Tracker checklist in `Coursework_Experiments_Checklist.md`

### **"What's my best LR for Section 3.2?"**
→ Compare mAP scores from 3.1.0, 3.1.1, 3.1.2, 3.1.3 and pick the highest

---

## **Final Notes**

- These documents contain all details needed for 100% completion
- Keep them accessible while working
- Reference specific sections as needed
- Update your progress tracker as you complete experiments
- Document findings progressively (don't wait until the end)

**Good luck with your coursework! 🎯**

---

**Created**: November 5, 2025
**Module**: EEEM066 - Fundamentals of Machine Learning
**Deadline**: Tuesday, 2nd December 2025 at 4:00 PM
**Total Marks**: 100 (20% of module grade)
