# NMS vs Soft-NMS Comparison Report

## Performance Statistics

| Metric | Standard NMS | Soft-NMS |
|--------|-------------|----------|
| Files Processed | 852 | 852 |
| Total Detections | 18335 | 8024 |
| Average Detections per File | 21.52 | 9.42 |
| Total Processing Time (s) | 1.6961 | 3.0980 |
| Average Processing Time per File (s) | 0.001991 | 0.003636 |

## Analysis

### Detection Count Analysis

Soft-NMS detected -56.24% fewer objects than standard NMS.

### Processing Time Analysis

Soft-NMS was 82.65% slower than standard NMS.

### Key Differences

- **Standard NMS** completely removes overlapping boxes, which can be a problem for objects that are close together.
- **Soft-NMS** reduces the confidence of overlapping boxes instead of removing them completely.
- This usually results in **better recall** for Soft-NMS, especially in crowded scenes.
- Soft-NMS typically preserves more detections in areas where objects overlap.

### Recommendations

- Use **Standard NMS** when:
  - Processing speed is critical
  - Objects are well-separated
  - False positives are a concern

- Use **Soft-NMS** when:
  - Objects frequently overlap
  - Recall is more important than precision
  - You're working with crowded scenes
  - Missing detections is more problematic than having duplicate detections
