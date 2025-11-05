# EEEM066 Coursework - Complete Experiments Checklist

## Overview
All experiments organized by section and question with corresponding log file names.
Use this checklist to track your progress and ensure you complete all required experiments.

---

## **QUICK CONFIGURATION REFERENCE GUIDE**

### **What Changes in Each Section:**

| Section | What Changes | What Stays Same | Notes |
|---------|--------------|-----------------|-------|
| **Section 1** | ❌ Model Architecture | ✅ LR, BS, Augmentation | Test 3 different architectures |
| **Section 2** | ❌ Data Augmentation | ✅ LR, BS, Model (from 1.1.1) | Test augmentation impact |
| **Section 3.1** | ❌ Learning Rate | ✅ BS (from 1.1.1), Model, Augmentation | Test LR impact, pick BEST LR |
| **Section 3.2** | ❌ Batch Size | ✅ LR (BEST from 3.1), Model, Augmentation | Test BS impact |

### **Fixed Values Across Experiments:**

| Parameter | Value | Where Used | Notes |
|-----------|-------|-----------|-------|
| **Model** | Default from reference code | Sections 2, 3 (all) | Only Section 1 changes this |
| **Augmentation** | Colour Jittering (default) | Sections 1, 3 (all) | Only Section 2 changes this |
| **LR** | Default (record it!) → use for Sec 2 & 3 | Section 3.2 | Section 3.1 finds best LR for 3.2 |
| **BS** | Default (record it!) → use for Sec 2 & 3 | Section 3.1 | Only Section 3.2 changes this |
| **Dataset** | 25,250 train \| 440 val \| 469 test | All sections | Never change |
| **Evaluation** | Test set only (not train/val) | All sections | **CRITICAL: Report TEST metrics** |

---

## **SECTION 1: Code Familiarity (40 marks)**

### **Question 1.1: Running and Understanding Default Code (20 marks)**

| Exp # | Experiment Description | Log File Name | Status | Configuration |
|-------|------------------------|---------------|--------|---|
| 1.1.1 | Run provided code with default settings | `log_sec1_q1.txt` | ⬜ | **LR**: Default \| **BS**: Default \| **Aug**: Colour Jittering \| **Model**: Default CNN |

**Configuration Details:**
- **Model Architecture**: Use default from reference codebase (e.g., ResNet/VGG/etc.)
- **Learning Rate (LR)**: Use default value as-is → **RECORD THIS VALUE** (you'll reference it in Section 3)
- **Batch Size (BS)**: Use default value as-is → **RECORD THIS VALUE** (you'll reference it in Section 3)
- **Data Augmentation**: Colour Jittering ONLY (default)
- **Dataset**: 25,250 training | 440 validation | 469 test
- **Epochs**: Use default
- **Optimizer**: Use default
- **Loss Function**: Use default

**What to document for this experiment:**
- Training/evaluation pipeline steps (data loading → model init → training loop → evaluation)
- Model architecture name and key specifications
- **Performance metrics on TEST set** (especially mAP)
- Default LR value used (important for comparison later)
- Default BS value used (important for comparison later)
- Any overfitting/underfitting observations
- Training curves, convergence behavior, and key statistics

---

### **Question 1.2: Different CNN Variant (10 marks)**

| Exp # | Experiment Description | Log File Name | Status | Configuration |
|-------|------------------------|---------------|--------|---|
| 1.2.1 | Apply CNN Variant #1 (e.g., ResNet if default was VGG) | `log_sec1_q2.txt` | ⬜ | **LR**: Same as 1.1.1 \| **BS**: Same as 1.1.1 \| **Aug**: Colour Jittering \| **Model**: DIFFERENT CNN |

**Configuration Details:**
- **Model Architecture**: DIFFERENT CNN variant (e.g., if 1.1.1 used ResNet, use Inception/DenseNet/etc.)
- **Learning Rate (LR)**: **KEEP SAME as Exp 1.1.1** (do not change)
- **Batch Size (BS)**: **KEEP SAME as Exp 1.1.1** (do not change)
- **Data Augmentation**: Colour Jittering ONLY (default - same as 1.1.1)
- **Dataset**: Same 25,250 training | 440 validation | 469 test
- **Epochs/Optimizer/Loss**: Keep all other settings same as 1.1.1
- ⭐ **Key point**: Only change the architecture, keep everything else identical for fair comparison

**What to document for this experiment:**
- New CNN architecture name and detailed specifications
- **Performance metrics on TEST set** (mAP, accuracy)
- Comparison table: Exp 1.1.1 vs 1.2.1 with same LR and BS
- Quantitative analysis of performance differences
- Reasons for performance differences (architecture differences, parameter count, etc.)
- Training dynamics (convergence speed, stability, etc.)

---

### **Question 1.3: Third Architecture (CNN or Vision Transformer) (10 marks)**

| Exp # | Experiment Description | Log File Name | Status | Configuration |
|-------|------------------------|---------------|--------|---|
| 1.3.1 | Apply Architecture #2 (e.g., Vision Transformer if Q1&Q2 were CNNs) | `log_sec1_q3.txt` | ⬜ | **LR**: Same as 1.1.1 \| **BS**: Same as 1.1.1 \| **Aug**: Colour Jittering \| **Model**: CNN or ViT (DIFFERENT) |

**Configuration Details:**
- **Model Architecture**: DIFFERENT type (e.g., if Q1&Q2 used CNNs, use Vision Transformer; or use completely different CNN)
- **Learning Rate (LR)**: **KEEP SAME as Exp 1.1.1** (do not change)
- **Batch Size (BS)**: **KEEP SAME as Exp 1.1.1** (do not change)
- **Data Augmentation**: Colour Jittering ONLY (default - same as 1.1.1 and 1.2.1)
- **Dataset**: Same 25,250 training | 440 validation | 469 test
- **Epochs/Optimizer/Loss**: Keep all other settings same as 1.1.1
- ⭐ **Key point**: Only change the architecture, keep everything else identical for fair comparison

**What to document for this experiment:**
- Third architecture name and detailed specifications (different from 1.1.1 and 1.2.1)
- **Performance metrics on TEST set** (mAP, accuracy)
- **Comparison table**: All three experiments (1.1.1, 1.2.1, 1.3.1) side-by-side with same LR and BS
- Comprehensive quantitative analysis of all three architectures
- Strengths and weaknesses of each model (based on results)
- Best performing architecture discussion
- Training dynamics comparison (speed, convergence, stability)

---

## **SECTION 2: Dataset Preparation & Augmentation (30 marks)**

### **Question 2.1: Additional Augmentation Techniques (20 marks)**

| Exp # | Experiment Description | Log File Name | Status | Configuration |
|-------|------------------------|---------------|--------|---|
| 2.1.1 | Baseline with Default Augmentation (Colour Jittering) | `log_sec2_q1_baseline.txt` | ⬜ | **LR**: From 1.1.1 \| **BS**: From 1.1.1 \| **Aug**: Colour Jittering ONLY \| **Model**: From 1.1.1 |
| 2.1.2 | Default + Augmentation Technique #1 (e.g., Random Rotation) | `log_sec2_q1_aug1.txt` | ⬜ | **LR**: From 1.1.1 \| **BS**: From 1.1.1 \| **Aug**: Colour Jittering + Rotation \| **Model**: From 1.1.1 |
| 2.1.3 | Default + Augmentation Technique #2 (e.g., Horizontal Flip) | `log_sec2_q1_aug2.txt` | ⬜ | **LR**: From 1.1.1 \| **BS**: From 1.1.1 \| **Aug**: Colour Jittering + Flip \| **Model**: From 1.1.1 |

**Configuration Details for ALL three experiments:**
- **Model Architecture**: Use the default model from 1.1.1 (SAME for all)
- **Learning Rate (LR)**: Use the default LR from Exp 1.1.1 (SAME for all)
- **Batch Size (BS)**: Use the default BS from Exp 1.1.1 (SAME for all)
- **Data Augmentation**: 
  - Exp 2.1.1: Colour Jittering ONLY (baseline reference)
  - Exp 2.1.2: Colour Jittering + Technique #1 (e.g., Random Rotation: 15-45 degrees)
  - Exp 2.1.3: Colour Jittering + Technique #2 (e.g., Horizontal Flip: probability 0.5)
- **Dataset**: Same 25,250 training | 440 validation | 469 test
- ⭐ **Key point**: Only change augmentation, keep model/LR/BS identical for fair comparison

**Augmentation Technique Options (pick two different ones):**
- Random Rotation (angle range: 15-45 degrees)
- Horizontal Flip (probability: 0.5)
- Vertical Flip (probability: 0.3-0.5)
- Random Crop (crop size: 80-95% of original)
- Gaussian Blur (kernel size: 3-5, sigma: 0.1-2.0)
- Brightness/Contrast Adjustment (range: ±0.2)
- Random Scaling (scale range: 0.8-1.2)
- Shearing (shear range: ±0.2)

**What to document for this experiment:**
- Each augmentation technique name and parameters used
- **Performance metrics on TEST set** for all three (mAP, accuracy)
- **Comparison table**: Baseline vs Aug1 vs Aug2 (side-by-side)
- Impact of each augmentation technique (improvement/degradation %)
- Analysis of how each technique affects model robustness
- Visual examples or descriptions of what each augmentation does
- Discussion on why certain augmentations help/hurt performance

---

### **Question 2.2: Best Augmentation Combination (10 marks)**

| Exp # | Experiment Description | Log File Name | Status | Configuration |
|-------|------------------------|---------------|--------|---|
| 2.2.1 | Combined Best Augmentations | `log_sec2_q2.txt` | ⬜ | **LR**: From 1.1.1 \| **BS**: From 1.1.1 \| **Aug**: Colour Jit + Aug1 + Aug2 \| **Model**: From 1.1.1 |

**Configuration Details:**
- **Model Architecture**: Use the default model from 1.1.1 (SAME)
- **Learning Rate (LR)**: Use the default LR from Exp 1.1.1 (SAME)
- **Batch Size (BS)**: Use the default BS from Exp 1.1.1 (SAME)
- **Data Augmentation**: **COMBINE all three** - Colour Jittering + Technique #1 + Technique #2 (stacked together)
  - If 2.1.2 used: Random Rotation
  - If 2.1.3 used: Horizontal Flip
  - Combined: Colour Jitter + Rotation + Flip (applied together)
- **Dataset**: Same 25,250 training | 440 validation | 469 test
- ⭐ **Key point**: This combines the two techniques from Q2.1, applied sequentially

**What to document for this experiment:**
- Combined augmentation pipeline (describe stacking order)
- **Performance metrics on TEST set** (mAP, accuracy)
- **Comparison table**: 
  - Exp 2.1.1 (baseline) 
  - Exp 2.1.2 (Aug1 only) 
  - Exp 2.1.3 (Aug2 only) 
  - Exp 2.2.1 (COMBINED)
- Performance change analysis (% improvement/degradation from baseline)
- Did combined augmentation help or hurt? Quantify the change
- Discussion on synergy between augmentation techniques
- Any overfitting/underfitting changes with combined augmentation

---

## **SECTION 3: Hyperparameter Exploration (20 marks)**

### **Question 3.1: Learning Rate Exploration (10 marks)**

| Exp # | Experiment Description | Log File Name | Status | Configuration |
|-------|------------------------|---------------|--------|---|
| 3.1.0 | Baseline with Default Learning Rate | `log_sec3_q1_lr_default.txt` | ⬜ | **LR**: [Record default] \| **BS**: From 1.1.1 \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |
| 3.1.1 | Learning Rate Value #1 (e.g., 0.0001) | `log_sec3_q1_lr1.txt` | ⬜ | **LR**: 0.0001 (or your choice) \| **BS**: From 1.1.1 \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |
| 3.1.2 | Learning Rate Value #2 (e.g., 0.001) | `log_sec3_q1_lr2.txt` | ⬜ | **LR**: 0.001 (or your choice) \| **BS**: From 1.1.1 \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |
| 3.1.3 | Learning Rate Value #3 (e.g., 0.01) | `log_sec3_q1_lr3.txt` | ⬜ | **LR**: 0.01 (or your choice) \| **BS**: From 1.1.1 \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |

**Configuration Details for ALL four experiments:**
- **Model Architecture**: Use the default model from 1.1.1 (SAME for all)
- **Learning Rate (LR)**: 
  - Exp 3.1.0: **DEFAULT** (record the exact value from 1.1.1)
  - Exp 3.1.1: **Value 1** (e.g., 0.0001 or 10x smaller than default)
  - Exp 3.1.2: **Value 2** (e.g., 0.001 or 5x smaller/larger depending on default)
  - Exp 3.1.3: **Value 3** (e.g., 0.01 or 10x larger than default)
- **Batch Size (BS)**: Use the default BS from Exp 1.1.1 (SAME for all)
- **Data Augmentation**: Colour Jittering ONLY (SAME for all)
- **Dataset**: Same 25,250 training | 440 validation | 469 test
- ⭐ **Key point**: Only change LR, keep model/BS/augmentation identical for fair comparison

**LR Selection Strategy:**
- If default = 0.001: try [0.0001, 0.0005, 0.005, 0.01]
- If default = 0.01: try [0.001, 0.005, 0.05, 0.1]
- If default = 0.1: try [0.01, 0.05, 0.5, 1.0]
- Spread across different magnitudes to see impact

**What to document for this experiment:**
- All LR values tested (including default) - clearly labeled
- **Performance metrics on TEST set** for all four (mAP, accuracy)
- **Comparison table**: All 4 LR values side-by-side
  - Column headers: LR Value | mAP | Accuracy | Training Time | Convergence Speed | Stability
- Impact analysis of each LR (too slow → no convergence, too fast → unstable, optimal → best mAP)
- **IDENTIFY BEST LR** for use in Section 3.2
- Discussion on convergence behavior and training dynamics
- Why certain LR values performed better/worse

---

### **Question 3.2: Batch Size Exploration (10 marks)**

| Exp # | Experiment Description | Log File Name | Status | Configuration |
|-------|------------------------|---------------|--------|---|
| 3.2.0 | Baseline with Default Batch Size (using best LR from Q3.1) | `log_sec3_q2_bs_default.txt` | ⬜ | **LR**: BEST from 3.1.X \| **BS**: Default \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |
| 3.2.1 | Batch Size Value #1 (e.g., 16) | `log_sec3_q2_bs1.txt` | ⬜ | **LR**: BEST from 3.1.X \| **BS**: 16 \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |
| 3.2.2 | Batch Size Value #2 (e.g., 64) | `log_sec3_q2_bs2.txt` | ⬜ | **LR**: BEST from 3.1.X \| **BS**: 64 \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |
| 3.2.3 | Batch Size Value #3 (e.g., 256) | `log_sec3_q2_bs3.txt` | ⬜ | **LR**: BEST from 3.1.X \| **BS**: 256 \| **Aug**: Colour Jittering \| **Model**: From 1.1.1 |

**Configuration Details for ALL four experiments:**
- **Model Architecture**: Use the default model from 1.1.1 (SAME for all)
- **Learning Rate (LR)**: 
  - ⭐ **CRITICAL**: Use the BEST LR identified from Section 3.1 experiments
  - This is the LR that gave highest mAP in Q3.1
  - SAME for all four batch size experiments
- **Batch Size (BS)**:
  - Exp 3.2.0: **DEFAULT** BS from 1.1.1 (baseline reference)
  - Exp 3.2.1: **Value 1** (e.g., 16 - small batch)
  - Exp 3.2.2: **Value 2** (e.g., 64 - medium batch)
  - Exp 3.2.3: **Value 3** (e.g., 256 - large batch)
- **Data Augmentation**: Colour Jittering ONLY (SAME for all)
- **Dataset**: Same 25,250 training | 440 validation | 469 test
- ⭐ **Key point**: Only change BS, keep LR (best from Q3.1)/model/augmentation identical

**BS Selection Strategy:**
- Small batches: 8, 16, 32 (more gradient noise, slower training)
- Medium batches: 32, 64, 128 (balanced)
- Large batches: 128, 256, 512 (faster training, may overfit)
- Adjust based on your GPU memory constraints

**What to document for this experiment:**
- All BS values tested (including default) - clearly labeled
- **CRITICAL: State which LR is being used** (the best one from Q3.1)
- **Performance metrics on TEST set** for all four (mAP, accuracy)
- **Comparison table**: All 4 BS values side-by-side
  - Column headers: BS Value | LR Used | mAP | Accuracy | Training Time | Memory Usage | Convergence
- Impact analysis of each BS (small → slower/noisier, large → faster/memory issues)
- How BS affects training dynamics and final performance
- Identify best BS configuration overall
- Discussion on memory-performance tradeoff

---

## **DETAILED EXPERIMENT MATRIX**

### **Complete Configuration for All 15 Experiments**

| Exp ID | Section | Question | Exp Name | Log File | Model | LR | BS | Augmentation | Change From Previous |
|--------|---------|----------|----------|----------|-------|----|----|--------------|----------------------|
| 1.1.1 | 1 | Q1 | Default Code | log_sec1_q1.txt | **DEFAULT** | **DEFAULT** | **DEFAULT** | Colour Jitter | Baseline |
| 1.2.1 | 1 | Q2 | CNN Variant 1 | log_sec1_q2.txt | **DIFFERENT CNN** | Same as 1.1.1 | Same as 1.1.1 | Colour Jitter | Architecture only |
| 1.3.1 | 1 | Q3 | Architecture 2 | log_sec1_q3.txt | **DIFFERENT (CNN or ViT)** | Same as 1.1.1 | Same as 1.1.1 | Colour Jitter | Architecture only |
| 2.1.1 | 2 | Q1 | Augment Baseline | log_sec2_q1_baseline.txt | From 1.1.1 | From 1.1.1 | From 1.1.1 | Colour Jitter | Baseline for Aug |
| 2.1.2 | 2 | Q1 | Aug Technique 1 | log_sec2_q1_aug1.txt | From 1.1.1 | From 1.1.1 | From 1.1.1 | Colour Jitter + **Rotation** | Aug Technique 1 only |
| 2.1.3 | 2 | Q1 | Aug Technique 2 | log_sec2_q1_aug2.txt | From 1.1.1 | From 1.1.1 | From 1.1.1 | Colour Jitter + **Flip** | Aug Technique 2 only |
| 2.2.1 | 2 | Q2 | Combined Aug | log_sec2_q2.txt | From 1.1.1 | From 1.1.1 | From 1.1.1 | Colour Jitter + **Rotation + Flip** | Both Aug Techniques |
| 3.1.0 | 3 | Q1 | LR Default | log_sec3_q1_lr_default.txt | From 1.1.1 | **DEFAULT** | From 1.1.1 | Colour Jitter | Baseline for LR |
| 3.1.1 | 3 | Q1 | LR Value 1 | log_sec3_q1_lr1.txt | From 1.1.1 | **LR1** (e.g., 0.0001) | From 1.1.1 | Colour Jitter | LR only |
| 3.1.2 | 3 | Q1 | LR Value 2 | log_sec3_q1_lr2.txt | From 1.1.1 | **LR2** (e.g., 0.001) | From 1.1.1 | Colour Jitter | LR only |
| 3.1.3 | 3 | Q1 | LR Value 3 | log_sec3_q1_lr3.txt | From 1.1.1 | **LR3** (e.g., 0.01) | From 1.1.1 | Colour Jitter | LR only → **PICK BEST** |
| 3.2.0 | 3 | Q2 | BS Default | log_sec3_q2_bs_default.txt | From 1.1.1 | **BEST from 3.1.X** | **DEFAULT** | Colour Jitter | Baseline for BS (uses best LR) |
| 3.2.1 | 3 | Q2 | BS Value 1 | log_sec3_q2_bs1.txt | From 1.1.1 | **BEST from 3.1.X** | **BS1** (e.g., 16) | Colour Jitter | BS only (uses best LR) |
| 3.2.2 | 3 | Q2 | BS Value 2 | log_sec3_q2_bs2.txt | From 1.1.1 | **BEST from 3.1.X** | **BS2** (e.g., 64) | Colour Jitter | BS only (uses best LR) |
| 3.2.3 | 3 | Q2 | BS Value 3 | log_sec3_q2_bs3.txt | From 1.1.1 | **BEST from 3.1.X** | **BS3** (e.g., 256) | Colour Jitter | BS only (uses best LR) |

---

| Section | Question | Total Experiments | Log Files | Marks |
|---------|----------|------------------|-----------|-------|
| 1 | Q1 | 1 | `log_sec1_q1.txt` | 20 |
| 1 | Q2 | 1 | `log_sec1_q2.txt` | 10 |
| 1 | Q3 | 1 | `log_sec1_q3.txt` | 10 |
| 2 | Q1 | 3 | `log_sec2_q1_baseline.txt`, `log_sec2_q1_aug1.txt`, `log_sec2_q1_aug2.txt` | 20 |
| 2 | Q2 | 1 | `log_sec2_q2.txt` | 10 |
| 3 | Q1 | 4 | `log_sec3_q1_lr_default.txt`, `log_sec3_q1_lr1.txt`, `log_sec3_q1_lr2.txt`, `log_sec3_q1_lr3.txt` | 10 |
| 3 | Q2 | 4 | `log_sec3_q2_bs_default.txt`, `log_sec3_q2_bs1.txt`, `log_sec3_q2_bs2.txt`, `log_sec3_q2_bs3.txt` | 10 |
| - | - | **15 Total Experiments** | **15 Log Files** | **90 + 10 (Presentation)** |

---

## **Important Notes**

### ✅ Critical Requirements:
- Keep log file structure unchanged (they're watermarked)
- Each experiment needs its own log file
- Use consistent naming: `log_sec{section}_q{question}[_descriptor].txt`
- Don't modify or edit log files after generation

### 📊 Documentation Tips:
- Create a comparison table for each section
- Include performance metrics (especially mAP)
- Add visualizations (plots) to show trends
- Maintain 200-word limit per section (excluding tables/plots)
- Label all figures with readable axes

### 🎯 Recommended Workflow:
1. **Section 1**: Complete all 3 architecture experiments (record default LR and BS)
2. **Section 2**: Run augmentation experiments using same LR/BS/model from Section 1
3. **Section 3.1**: Test 4 different LRs (keep BS and model constant) → **IDENTIFY BEST LR**
4. **Section 3.2**: Test 4 different BS values (use BEST LR from 3.1, keep model constant)
5. Document findings progressively (don't wait until the end)

### ⭐ Critical Chain of Dependencies:
```
Section 1.1.1 (Default Config)
    ↓
    Records: Default LR + Default BS + Default Model
    ↓
Section 1.2.1 & 1.3.1 (Change only architecture, keep LR/BS)
    ↓
Section 2.1-2.2 (Change only augmentation, keep LR/BS/model from 1.1.1)
    ↓
Section 3.1 (Change only LR, keep BS/model/augmentation)
    ↓
    IDENTIFY BEST LR
    ↓
Section 3.2 (Change only BS, MUST use BEST LR from 3.1, keep model/augmentation)
```

### 📝 Report Structure Example:
```
**Section 1.1 Results:**
Table: Architecture Comparison
- Architecture | mAP | Accuracy | Training Time
- Exp 1.1.1   | XX% | XX%      | XXs

**Analysis:**
The default model achieved XX% mAP... [analysis in 200 words]
```

---

## **Experiment Progress Tracker**

### Section 1
- [ ] 1.1.1 - Default code (log_sec1_q1.txt)
- [ ] 1.2.1 - CNN Variant (log_sec1_q2.txt)
- [ ] 1.3.1 - Third Architecture (log_sec1_q3.txt)

### Section 2
- [ ] 2.1.1 - Default augmentation baseline (log_sec2_q1_baseline.txt)
- [ ] 2.1.2 - Augmentation technique 1 (log_sec2_q1_aug1.txt)
- [ ] 2.1.3 - Augmentation technique 2 (log_sec2_q1_aug2.txt)
- [ ] 2.2.1 - Combined augmentation (log_sec2_q2.txt)

### Section 3
- [ ] 3.1.0 - Default LR baseline (log_sec3_q1_lr_default.txt)
- [ ] 3.1.1 - Learning rate 1 (log_sec3_q1_lr1.txt)
- [ ] 3.1.2 - Learning rate 2 (log_sec3_q1_lr2.txt)
- [ ] 3.1.3 - Learning rate 3 (log_sec3_q1_lr3.txt)
- [ ] 3.2.0 - Default BS baseline (log_sec3_q2_bs_default.txt)
- [ ] 3.2.1 - Batch size 1 (log_sec3_q2_bs1.txt)
- [ ] 3.2.2 - Batch size 2 (log_sec3_q2_bs2.txt)
- [ ] 3.2.3 - Batch size 3 (log_sec3_q2_bs3.txt)

---

**Total Experiments to Complete: 15**
**Total Log Files to Submit: 15**
**Deadline: Tuesday, 2nd December 2025 at 4:00 PM**
