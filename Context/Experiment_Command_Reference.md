# EEEM066 Coursework - Experiment Commands Reference

This guide provides command templates for running each experiment in Google Colab.

---

## **SECTION 1: Testing Different Architectures**

### **Exp 1.1.1 - Default Model**
```bash
# Command structure (use default from provided codebase)
python train.py --model default --lr [DEFAULT_LR] --batch-size [DEFAULT_BS]
```
**After running, record:**
- Default LR value: `[DEFAULT_LR]` → Use this for ALL Section 2 & 3 experiments
- Default BS value: `[DEFAULT_BS]` → Use this for ALL Section 2 & 3 experiments
- Log file: `log_sec1_q1.txt`

---

### **Exp 1.2.1 - Different CNN Variant**
```bash
# Use a DIFFERENT CNN architecture
python train.py --model resnet50 --lr [DEFAULT_LR] --batch-size [DEFAULT_BS]
# OR
python train.py --model inception_v3 --lr [DEFAULT_LR] --batch-size [DEFAULT_BS]
# OR
python train.py --model densenet --lr [DEFAULT_LR] --batch-size [DEFAULT_BS]
```
**Key points:**
- Replace `[DEFAULT_LR]` with the value from Exp 1.1.1
- Replace `[DEFAULT_BS]` with the value from Exp 1.1.1
- Choose an architecture DIFFERENT from 1.1.1
- Log file: `log_sec1_q2.txt`

---

### **Exp 1.3.1 - Third Architecture (CNN or Vision Transformer)**
```bash
# Use a DIFFERENT architecture from 1.1.1 and 1.2.1
python train.py --model vit_base --lr [DEFAULT_LR] --batch-size [DEFAULT_BS]
# OR
python train.py --model efficientnet --lr [DEFAULT_LR] --batch-size [DEFAULT_BS]
# OR
python train.py --model mobilenet --lr [DEFAULT_LR] --batch-size [DEFAULT_BS]
```
**Key points:**
- Replace `[DEFAULT_LR]` with the value from Exp 1.1.1
- Replace `[DEFAULT_BS]` with the value from Exp 1.1.1
- Choose an architecture DIFFERENT from 1.1.1 AND 1.2.1
- If 1.1.1 & 1.2.1 used CNNs, try Vision Transformer here
- Log file: `log_sec1_q3.txt`

---

## **SECTION 2: Testing Data Augmentation Techniques**

### **Exp 2.1.1 - Baseline (Colour Jittering Only)**
```bash
# Default augmentation (baseline reference)
python train.py --model [DEFAULT_MODEL] --lr [DEFAULT_LR] --batch-size [DEFAULT_BS] --augmentation color_jitter
```
**Key points:**
- Use the default model from Exp 1.1.1
- Use the default LR from Exp 1.1.1
- Use the default BS from Exp 1.1.1
- Augmentation: Colour Jittering ONLY
- Log file: `log_sec2_q1_baseline.txt`

---

### **Exp 2.1.2 - Default + Augmentation Technique #1**
```bash
# Example: Adding Random Rotation to colour jittering
python train.py --model [DEFAULT_MODEL] --lr [DEFAULT_LR] --batch-size [DEFAULT_BS] \
  --augmentation color_jitter --augmentation random_rotation --rotation-angle 30
# OR with Horizontal Flip:
python train.py --model [DEFAULT_MODEL] --lr [DEFAULT_LR] --batch-size [DEFAULT_BS] \
  --augmentation color_jitter --augmentation horizontal_flip --flip-prob 0.5
```
**Key points:**
- Use the default model from Exp 1.1.1
- Use the default LR from Exp 1.1.1
- Use the default BS from Exp 1.1.1
- Add ONE new augmentation technique (e.g., random_rotation or horizontal_flip)
- Log file: `log_sec2_q1_aug1.txt`

---

### **Exp 2.1.3 - Default + Augmentation Technique #2**
```bash
# Add a DIFFERENT augmentation technique
# If Exp 2.1.2 used Random Rotation, use Horizontal Flip here:
python train.py --model [DEFAULT_MODEL] --lr [DEFAULT_LR] --batch-size [DEFAULT_BS] \
  --augmentation color_jitter --augmentation horizontal_flip --flip-prob 0.5
# OR if Exp 2.1.2 used Horizontal Flip, use Gaussian Blur here:
python train.py --model [DEFAULT_MODEL] --lr [DEFAULT_LR] --batch-size [DEFAULT_BS] \
  --augmentation color_jitter --augmentation gaussian_blur --blur-sigma 1.0
```
**Key points:**
- Use the default model from Exp 1.1.1
- Use the default LR from Exp 1.1.1
- Use the default BS from Exp 1.1.1
- Add a DIFFERENT augmentation technique (not the one from 2.1.2)
- Log file: `log_sec2_q1_aug2.txt`

---

### **Exp 2.2.1 - Combined Best Augmentations**
```bash
# Combine the two augmentation techniques from Exp 2.1.2 and 2.1.3
# Example: Random Rotation + Horizontal Flip + Colour Jitter
python train.py --model [DEFAULT_MODEL] --lr [DEFAULT_LR] --batch-size [DEFAULT_BS] \
  --augmentation color_jitter --augmentation random_rotation --rotation-angle 30 \
  --augmentation horizontal_flip --flip-prob 0.5
```
**Key points:**
- Use the default model from Exp 1.1.1
- Use the default LR from Exp 1.1.1
- Use the default BS from Exp 1.1.1
- Combine BOTH augmentation techniques + colour jittering
- Log file: `log_sec2_q2.txt`

---

## **SECTION 3.1: Testing Learning Rates**

### **Exp 3.1.0 - Baseline (Default LR)**
```bash
# Baseline with default learning rate
python train.py --model [DEFAULT_MODEL] --lr [DEFAULT_LR] --batch-size [DEFAULT_BS] \
  --augmentation color_jitter
```
**Key points:**
- Use the default model from Exp 1.1.1
- Use the SAME default LR from Exp 1.1.1
- Use the SAME default BS from Exp 1.1.1
- Log file: `log_sec3_q1_lr_default.txt`

---

### **Exp 3.1.1, 3.1.2, 3.1.3 - Different Learning Rates**
```bash
# Experiment with different learning rates
# Example 1: Very small LR (10x smaller than default)
python train.py --model [DEFAULT_MODEL] --lr 0.0001 --batch-size [DEFAULT_BS] \
  --augmentation color_jitter

# Example 2: Small LR (5x smaller than default, if default is 0.001)
python train.py --model [DEFAULT_MODEL] --lr 0.0005 --batch-size [DEFAULT_BS] \
  --augmentation color_jitter

# Example 3: Larger LR (10x larger than default)
python train.py --model [DEFAULT_MODEL] --lr 0.01 --batch-size [DEFAULT_BS] \
  --augmentation color_jitter
```
**Key points:**
- Use the default model from Exp 1.1.1
- Change ONLY the learning rate (test 3 different values)
- Keep BS constant (use default BS from Exp 1.1.1)
- Keep augmentation constant (colour jittering only)
- Log files: `log_sec3_q1_lr1.txt`, `log_sec3_q1_lr2.txt`, `log_sec3_q1_lr3.txt`
- **After running all LR experiments**: Identify which LR gave the best mAP (BEST_LR)

---

### **LR Strategy Guide:**
```
If DEFAULT_LR = 0.001:
- Exp 3.1.1: LR = 0.0001 (10x smaller) - test if training is too slow
- Exp 3.1.2: LR = 0.0005 (2x smaller) - test intermediate
- Exp 3.1.3: LR = 0.01 (10x larger) - test if training is unstable

If DEFAULT_LR = 0.01:
- Exp 3.1.1: LR = 0.001 (10x smaller)
- Exp 3.1.2: LR = 0.005 (2x smaller)
- Exp 3.1.3: LR = 0.1 (10x larger)
```

---

## **SECTION 3.2: Testing Batch Sizes**

### **Exp 3.2.0 - Baseline (Default BS)**
```bash
# Baseline with default batch size, using BEST LR from Section 3.1
python train.py --model [DEFAULT_MODEL] --lr [BEST_LR] --batch-size [DEFAULT_BS] \
  --augmentation color_jitter
```
**Key points:**
- Use the default model from Exp 1.1.1
- Use the BEST LR identified from Section 3.1 experiments (e.g., 3.1.1, 3.1.2, or 3.1.3)
- Use the SAME default BS from Exp 1.1.1
- Log file: `log_sec3_q2_bs_default.txt`

---

### **Exp 3.2.1, 3.2.2, 3.2.3 - Different Batch Sizes**
```bash
# Experiment with different batch sizes
# Example 1: Small batch size
python train.py --model [DEFAULT_MODEL] --lr [BEST_LR] --batch-size 16 \
  --augmentation color_jitter

# Example 2: Medium batch size
python train.py --model [DEFAULT_MODEL] --lr [BEST_LR] --batch-size 64 \
  --augmentation color_jitter

# Example 3: Large batch size
python train.py --model [DEFAULT_MODEL] --lr [BEST_LR] --batch-size 256 \
  --augmentation color_jitter
```
**Key points:**
- Use the default model from Exp 1.1.1
- **CRITICAL**: Use the BEST LR from Section 3.1 (not the default LR)
- Change ONLY the batch size (test 3 different values)
- Keep augmentation constant (colour jittering only)
- Log files: `log_sec3_q2_bs1.txt`, `log_sec3_q2_bs2.txt`, `log_sec3_q2_bs3.txt`

---

### **BS Strategy Guide:**
```
Small batches (noisy gradients, slower):
- BS = 8, 16, 32

Medium batches (balanced):
- BS = 32, 64, 128

Large batches (faster, may overfit):
- BS = 128, 256, 512

⭐ Recommendation: Test one from each category
- Example: BS = 16 (small), 64 (medium), 256 (large)
```

---

## **Quick Lookup: What to Keep Constant**

| Parameter | Section 1 | Section 2 | Section 3.1 | Section 3.2 |
|-----------|-----------|----------|-----------|-----------|
| Model | ❌ CHANGE | ✅ Same as 1.1.1 | ✅ Same as 1.1.1 | ✅ Same as 1.1.1 |
| LR | ✅ (record) | ✅ Same as 1.1.1 | ❌ CHANGE | ✅ BEST from 3.1 |
| BS | ✅ (record) | ✅ Same as 1.1.1 | ✅ Same as 1.1.1 | ❌ CHANGE |
| Augmentation | ✅ Default | ❌ CHANGE | ✅ Default | ✅ Default |

---

## **Troubleshooting Commands**

### Check available models:
```bash
python train.py --help
# Look for --model options
```

### Check available augmentations:
```bash
python train.py --help
# Look for --augmentation options
```

### Get experiment metrics:
```bash
# After running, check the log file for mAP, accuracy, training time:
cat log_sec1_q1.txt
```

### Run on GPU (important for speed):
```bash
# Most commands should automatically use GPU if available
python train.py --gpu 0 --model default --lr 0.001 --batch-size 32
```

---

## **Checklist for Each Experiment:**

Before running:
- [ ] Correct model architecture specified
- [ ] Correct LR value specified
- [ ] Correct BS value specified
- [ ] Correct augmentation specified
- [ ] Only ONE parameter changed from previous experiment
- [ ] Log file name prepared

After running:
- [ ] Log file generated with expected name
- [ ] mAP score recorded
- [ ] Training time noted
- [ ] Any errors/issues documented
- [ ] Results saved for final report

---

## **Useful Monitoring During Training:**

```bash
# Monitor GPU memory
!nvidia-smi

# Monitor training progress
!tail -f log_sec1_q1.txt

# Compare mAP scores across experiments
!grep "mAP" log_sec1_q1.txt log_sec1_q2.txt log_sec1_q3.txt
```

---

**Remember**: Report all metrics on TEST SET, not train/validation set!
