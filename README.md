# ActiveLearning


### 🧪 Uncertainty Sampling Strategies for Binary Classification

**Example Probabilities:**

- \( P(\text{Bioactive}) = 0.6439 \)
- \( P(\text{Non-active}) = 0.3561 \)

| **Method**               | **Formula**                                                                 | **Example Calculation**                                                         | **Score** | **Interpretation**                                                                   |
|--------------------------|------------------------------------------------------------------------------|----------------------------------------------------------------------------------|-----------|----------------------------------------------------------------------------------------|
| **Least Confidence**     | \( U = \left(1 - \max(P)\right) \times \frac{K}{K - 1} \)                    | \( (1 - 0.6439) \times \frac{2}{1} = 0.7122 \)                                   | 0.7122    | How far the top prediction is from full confidence                                   |
| **Margin of Confidence** | \( U = 1 - |P_1 - P_2| \)                                                    | \( 1 - |0.6439 - 0.3561| = 1 - 0.2878 = 0.7122 \)                                 | 0.7122    | Small difference between top two → high uncertainty                                  |
| **Ratio of Confidence**  | \( U = \frac{\min(P)}{\max(P)} \)                                            | \( \frac{0.3561}{0.6439} \approx 0.553 \)                                         | 0.553     | High ratio means close competition between top 2 predictions                         |
| **Entropy (Normalized)** | \( U = -\sum_i P_i \log_2 P_i \, \Big/ \log_2 K \)                           | \( -(0.6439 \log_2 0.6439 + 0.3561 \log_2 0.3561) / \log_2 2 \approx 0.939 \)    | 0.939     | Measures overall uncertainty across all predictions (max at 0.5/0.5 split)           |
