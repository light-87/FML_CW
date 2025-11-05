# EEEM066 Coursework - One-Page Visual Summary

## **15 Total Experiments Overview**

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                    SECTION 1: ARCHITECTURES (40 marks)                      │
│                         3 experiments (change model)                        │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Exp 1.1.1         Exp 1.2.1         Exp 1.3.1                            │
│  ┌──────────┐      ┌──────────┐      ┌──────────┐                          │
│  │ DEFAULT  │      │ CNN VAR  │      │  ARCH 2  │                          │
│  │ MODEL    │      │ (NEW CNN)│      │(ViT/CNN) │                          │
│  ├──────────┤      ├──────────┤      ├──────────┤                          │
│  │LR: DEF  │      │LR: DEF  │      │LR: DEF  │                          │
│  │BS: DEF  │      │BS: DEF  │      │BS: DEF  │                          │
│  │Aug: CJ  │      │Aug: CJ  │      │Aug: CJ  │                          │
│  └──────────┘      └──────────┘      └──────────┘                          │
│  log_sec1_q1.txt  log_sec1_q2.txt  log_sec1_q3.txt                        │
│       ↓                 ↓                 ↓                                 │
│    20 marks         10 marks         10 marks                             │
│                                                                             │
│  📝 Document:                                                              │
│  - Record Default LR & BS (use in all Section 2 & 3 experiments)          │
│  - Compare all 3 architectures                                             │
│  - Which architecture is best?                                             │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│             SECTION 2: DATA AUGMENTATION (30 marks)                         │
│                      4 experiments (change augmentation)                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Exp 2.1.1        Exp 2.1.2         Exp 2.1.3        Exp 2.2.1           │
│  ┌──────────┐      ┌──────────┐      ┌──────────┐      ┌──────────┐        │
│  │BASELINE  │      │ AUG1 ONLY│      │ AUG2 ONLY│      │COMBINED  │        │
│  │(DEFAULT) │      │(ROT/FLIP)│      │(FLIP/BUR)│      │AUG1+AUG2 │        │
│  ├──────────┤      ├──────────┤      ├──────────┤      ├──────────┤        │
│  │LR: DEF  │      │LR: DEF  │      │LR: DEF  │      │LR: DEF  │        │
│  │BS: DEF  │      │BS: DEF  │      │BS: DEF  │      │BS: DEF  │        │
│  │Aug: CJ  │      │Aug: CJ+ │      │Aug: CJ+ │      │Aug:CJ++│        │
│  │ONLY     │      │ROT/FLIP │      │FLIP/BUR │      │ALL 3    │        │
│  └──────────┘      └──────────┘      └──────────┘      └──────────┘        │
│  log_sec2_q1_    log_sec2_q1_    log_sec2_q1_    log_sec2_q2.txt         │
│  baseline.txt    aug1.txt        aug2.txt                                  │
│       ↓                 ↓               ↓                  ↓                │
│   20 marks (Q1)                                        10 marks (Q2)       │
│                                                                             │
│  📝 Document:                                                              │
│  - Pick two different augmentation techniques                              │
│  - How does each technique affect performance?                             │
│  - Does combining them help or hurt?                                       │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│        SECTION 3.1: LEARNING RATE EXPLORATION (10 marks)                    │
│                4 experiments (change learning rate only)                    │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Exp 3.1.0        Exp 3.1.1        Exp 3.1.2        Exp 3.1.3            │
│  ┌──────────┐      ┌──────────┐      ┌──────────┐      ┌──────────┐        │
│  │DEFAULT LR│      │ LR = LR1 │      │ LR = LR2 │      │ LR = LR3 │        │
│  │(Baseline)│      │(very low)│      │(low)     │      │(high)    │        │
│  ├──────────┤      ├──────────┤      ├──────────┤      ├──────────┤        │
│  │LR: DEF  │      │LR: LR1  │      │LR: LR2  │      │LR: LR3  │        │
│  │BS: DEF  │      │BS: DEF  │      │BS: DEF  │      │BS: DEF  │        │
│  │Aug: CJ  │      │Aug: CJ  │      │Aug: CJ  │      │Aug: CJ  │        │
│  └──────────┘      └──────────┘      └──────────┘      └──────────┘        │
│  log_sec3_q1_    log_sec3_q1_    log_sec3_q1_    log_sec3_q1_            │
│  lr_default.txt  lr1.txt         lr2.txt         lr3.txt                   │
│       ↓                ↓               ↓               ↓                    │
│                              10 marks                                      │
│                                                                             │
│  📝 Document:                                                              │
│  - Test 4 different LR values (1 default + 3 new)                         │
│  - Create comparison table with all LRs                                    │
│  - ⭐ IDENTIFY BEST LR (highest mAP)                                      │
│  - Use this BEST LR in Section 3.2!                                       │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────────────────┐
│       SECTION 3.2: BATCH SIZE EXPLORATION (10 marks)                        │
│           4 experiments (change batch size, use BEST LR from 3.1)          │
├─────────────────────────────────────────────────────────────────────────────┤
│                                                                             │
│  Exp 3.2.0        Exp 3.2.1        Exp 3.2.2        Exp 3.2.3            │
│  ┌──────────┐      ┌──────────┐      ┌──────────┐      ┌──────────┐        │
│  │DEFAULT BS│      │ BS = 16  │      │ BS = 64  │      │ BS = 256 │        │
│  │(Baseline)│      │(SMALL)   │      │(MEDIUM)  │      │(LARGE)   │        │
│  ├──────────┤      ├──────────┤      ├──────────┤      ├──────────┤        │
│  │LR: BEST  │      │LR: BEST  │      │LR: BEST  │      │LR: BEST  │        │
│  │BS: DEF  │      │BS: 16   │      │BS: 64   │      │BS: 256  │        │
│  │Aug: CJ  │      │Aug: CJ  │      │Aug: CJ  │      │Aug: CJ  │        │
│  └──────────┘      └──────────┘      └──────────┘      └──────────┘        │
│  log_sec3_q2_    log_sec3_q2_    log_sec3_q2_    log_sec3_q2_            │
│  bs_default.txt  bs1.txt         bs2.txt         bs3.txt                   │
│       ↓                ↓               ↓               ↓                    │
│                              10 marks                                      │
│                                                                             │
│  📝 Document:                                                              │
│  - Use the BEST LR from Section 3.1 (NOT the default!)                    │
│  - Test 4 different BS values (1 default + 3 new)                         │
│  - Create comparison table with all BS values                              │
│  - How does BS affect training and performance?                            │
│                                                                             │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## **Quick Reference Matrix**

| Parameter | Sec 1 | Sec 2 | Sec 3.1 | Sec 3.2 |
|-----------|-------|-------|---------|---------|
| **Model** | ❌ CHANGE (3 diff) | ✅ SAME (1.1.1) | ✅ SAME (1.1.1) | ✅ SAME (1.1.1) |
| **LR** | ✅ Record | ✅ SAME (recorded) | ❌ CHANGE (test 4) | ✅ BEST from 3.1 |
| **BS** | ✅ Record | ✅ SAME (recorded) | ✅ SAME (recorded) | ❌ CHANGE (test 4) |
| **Aug** | ✅ CJ only | ❌ CHANGE | ✅ CJ only | ✅ CJ only |
| **# Exps** | 3 | 4 | 4 | 4 |
| **# Logs** | 3 | 4 | 4 | 4 |
| **Marks** | 40 | 30 | 10 | 10 |

---

## **Execution Flow**

```
START
  │
  ├─→ Exp 1.1.1 (record LR & BS)
  │     ↓
  ├─→ Exp 1.2.1 (same LR & BS)
  │     ↓
  ├─→ Exp 1.3.1 (same LR & BS)
  │     ↓
  ├─→ Exp 2.1.1 (use recorded LR & BS)
  │     ↓
  ├─→ Exp 2.1.2 (use recorded LR & BS)
  │     ↓
  ├─→ Exp 2.1.3 (use recorded LR & BS)
  │     ↓
  ├─→ Exp 2.2.1 (use recorded LR & BS)
  │     ↓
  ├─→ Exp 3.1.0 (baseline LR)
  │     ↓
  ├─→ Exp 3.1.1 (test LR1)
  │     ↓
  ├─→ Exp 3.1.2 (test LR2)
  │     ↓
  ├─→ Exp 3.1.3 (test LR3)
  │     ↓
  │  [IDENTIFY BEST LR from 3.1 experiments]
  │     ↓
  ├─→ Exp 3.2.0 (baseline BS, use BEST LR)
  │     ↓
  ├─→ Exp 3.2.1 (test BS1, use BEST LR)
  │     ↓
  ├─→ Exp 3.2.2 (test BS2, use BEST LR)
  │     ↓
  ├─→ Exp 3.2.3 (test BS3, use BEST LR)
  │     ↓
  └─→ COMPILE FINAL REPORT (+ 10 marks for presentation)
      SUBMIT REPORT + 15 LOG FILES
```

---

## **Key Constraints to Remember**

✅ **DO:**
- Report metrics on TEST set (not train/validation)
- Keep ONLY ONE parameter different per experiment
- Use identical settings for fair comparisons
- Record default values (LR, BS) from Exp 1.1.1
- Use best LR from Section 3.1 when running Section 3.2
- Create comparison tables (side-by-side results)
- Add visualizations (plots/charts)
- Document findings progressively

❌ **DON'T:**
- Exceed 200 words per section (excluding tables/plots)
- Modify log file structure or names
- Change multiple parameters in one experiment
- Report train/validation metrics as final results
- Forget to record default values
- Use default LR/BS in Section 3.2
- Skip experiments or combine them
- Include unrelated documents in submission

---

## **Marks Breakdown**

```
Section 1 (40 marks)
├─ Q1: Default + understanding (20 marks)
├─ Q2: CNN variant (10 marks)
└─ Q3: Third architecture (10 marks)

Section 2 (30 marks)
├─ Q1: Augmentation techniques (20 marks)
└─ Q2: Combined best (10 marks)

Section 3 (20 marks)
├─ Q1: Learning rate exploration (10 marks)
└─ Q2: Batch size exploration (10 marks)

Presentation & Clarity (10 marks)
├─ Figures & labels (2 marks)
├─ Clear writing (6 marks)
└─ Tables usage (2 marks)

TOTAL: 100 marks (20% of module grade)
```

---

## **Quick Lookup: What to Use in Each Section**

### **Exp 1.1.1** → Document these values:
- Default LR: `_______`
- Default BS: `_______`
- Default Model: `_______`

### **Use in Section 2 & 3:**
- Model: Same as Exp 1.1.1
- LR: Same as Exp 1.1.1
- BS: Same as Exp 1.1.1

### **After Section 3.1:**
- Best LR from Q3.1: `_______` ← Use this in Section 3.2!

---

**Reminder**: You have until **Tuesday, 2nd December 2025 at 4:00 PM**
Submit: 1 Report (Word/PDF) + 15 Log Files via SurreyLearn
