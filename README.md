
# ML Legal Lab

## Introduction

ML Legal Lab is designed as a competitor to CoCounsel/Casetext, aiming to provide efficient and accurate legal document analysis and summarization. Currently under evaluation by the San Francisco Public Defenders office, this tool leverages LLMs to assist legal professionals in their case review.

### Key Findings

Our initial round of evaluations were promising. 

1. **Performance**: Summaries generated by ML Legal Lab, using Claude Haiku, performed on par with or outperformed CoCounsel/Casetext, which uses a variation of GPT-4.

2. **Efficiency**: ML Legal Lab achieves these results despite using a significantly smaller model compared to GPT-4.

3. **Cost-effectiveness**: Our approach is substantially more cost-efficient:
   - Approximately 40x less expensive for input tokens
   - Approximately 24x less expensive for output tokens

### Open-Source Model Evaluation

While our pipeline has shown promising results with Claude Haiku, we're also evaluating open-source alternatives:

- These models can be used with private endpoints, allowing for processing of sensitive documents that cannot be shared with large tech companies.
- Currently, open-source models are performing less consistently compared to our primary model. This is likely because I recycled parameters originally crafted for Claude without significant adaptation for open-source models.
- An alternative data processing pipeline has been developed specifically for these open-source models and is currently under evaluation.

This repository contains our evaluation results, comparing the performance of various models including LLAMA, CoCounsel, Claude, and Mixtral across different metrics.

## Summary stats
| Metric | LLAMA |  |  | CoCounsel |  |  | Claude |  |  | Mixtral |  |  |
|--------|-------|-------|-------|-----------|-------|-------|--------|-------|-------|---------|-------|-------|
|        | Completeness | Correctness | Conciseness | Completeness | Correctness | Conciseness | Completeness | Correctness | Conciseness | Completeness | Correctness | Conciseness |
| count  | 5.0   | 5.0   | 5.0   | 5.0       | 5.0   | 5.0   | 10.0   | 10.0  | 10.0  | 5.0     | 5.0   | 5.0   |
| mean   | 3.0   | 2.4   | 3.4   | 3.8       | 4.0   | 4.4   | 4.1    | 3.5   | 3.9   | 3.0     | 2.2   | 3.6   |
| std    | 1.0   | 0.55  | 1.14  | 1.30      | 1.41  | 0.89  | 1.10   | 1.27  | 0.99  | 1.0     | 0.84  | 1.14  |
| min    | 2.0   | 2.0   | 2.0   | 2.0       | 2.0   | 3.0   | 2.0    | 2.0   | 2.0   | 2.0     | 1.0   | 2.0   |
| 25%    | 2.0   | 2.0   | 3.0   | 3.0       | 3.0   | 4.0   | 3.25   | 2.25  | 3.25  | 2.0     | 2.0   | 3.0   |
| 50%    | 3.0   | 2.0   | 3.0   | 4.0       | 5.0   | 5.0   | 4.5    | 3.5   | 4.0   | 3.0     | 2.0   | 4.0   |
| 75%    | 4.0   | 3.0   | 4.0   | 5.0       | 5.0   | 5.0   | 5.0    | 4.75  | 4.75  | 4.0     | 3.0   | 4.0   |
| max    | 4.0   | 3.0   | 5.0   | 5.0       | 5.0   | 5.0   | 5.0    | 5.0   | 5.0   | 4.0     | 3.0   | 5.0   |

## Ranked as the best summary
| Model    | Count |
|----------|-------|
| LLAMA    | 0     |
| CoCounsel| 3     |
| Claude   | 2     |
| Mixtral  | 0     |

## Proportion of summaries that were not approved
| Model    | Proportion of Summaries Not Approved |
|----------|------------------------------------|
| LLAMA    | 80%                                |
| CoCounsel| 20%                                |
| Claude   | 30%                                |
| Mixtral  | 60%                                |