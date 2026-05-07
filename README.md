# Assessing Human-LLM Alignment in the Evaluation of Odia Spelling and Grammatical Errors

## Abstract

This study measures how consistently humans and large language models evaluate Odia grammatical error correction outputs. Two LLMs, Sarvam-105B and LLaMA-4-Scout-17B, annotated 50 Odia sentences across five error categories: Script Normalization, Spelling, Grammatical, Code-Mixing, and Correct. Six raters (two human linguists and four LLM judges) scored every annotation on four criteria covering error detection, span quality, category assignment, and correction quality. Inter-annotator agreement was measured using eight metrics covering raw agreement, chance-corrected measures, ordinal reliability, and rank correlation. A system preference analysis further examined which annotator LLM each evaluator preferred per sentence, and whether self-evaluating LLMs showed measurable optimism bias. Results show strong human agreement and moderate to low human–LLM alignment, with self-evaluating LLMs showing consistent positive bias toward their own outputs particularly on correction tasks.

**Keywords:** Odia NLP · Grammatical Error Correction · Inter-Annotator Agreement · LLM-as-Judge · Optimism Bias · IAA Metrics

---

## Project Root Folder

```text
Project_Root_Folder/
│
├── Analysis_Report.pdf
├── _PPT_Sai_Sudeep_Das.pdf
├── _APPENDIX_Sai_Sudeep_Das.pdf
├── Input_Data_With_Error_Details.xlsx
│
├── Annotation_Phase/
│   ├── Input_Data_GEC.xlsx
│   ├── Codes/
│   │   ├── Sarvam.ipynb
│   │   ├── LLAMA.ipynb
│   │   ├── GPT.ipynb
│   │   └── Gemini.ipynb
│   └── Data/
│       ├── Sarvam_Responses_Data_GEC.xlsx
│       ├── Llama4_Scout_17B_Responses_Data_GEC.xlsx
│       ├── GPT_Responses_Data_GEC.xlsx
│       ├── Gemini_31FlashLitePreview_Responses_Data_GEC.xlsx
│       └── Extra/
│           ├── Gemini_20Flash_Responses_Data_GEC.xlsx
│           ├── Gemini_25Flash_Responses_Data_GEC.xlsx
│           ├── Gemini_25FlashLite_Responses_Data_GEC.xlsx
│           ├── Gemini_25FlashLitePreview_Responses_Data_GEC.xlsx
│           ├── Gemini_3FlashPreview_Responses_Data_GEC.xlsx
│           ├── Llama33_70B_Responses_Data_GEC.xlsx
│           └── Qwen3_32B_Responses_Data_GEC.xlsx
│
├── Evaluation_Phase/
│   ├── Evaluation_Setup.md
│   ├── Master_Eval_Sheet.xlsx
│   ├── Human/
│   │   ├── Ashish_Bharat_EvalForm_Part_1 (Responses).xlsx
│   │   ├── Ashish_Bharat_EvalForm_Part_2 (Responses).xlsx
│   │   ├── Code/
│   │   │   └── Google_Forms_Preparation.ipynb
│   │   └── Google_Forms/
│   │       ├── Complete_Export_Error_Detection_Evaluation_Task_-_1_FORM.pdf
│   │       └── Complete_Export_Error_Detection_Evaluation_Task_-_2_FORM.pdf
│   └── LLM/
│       ├── Codes/
│       │   ├── Sarvam_Evaluator.ipynb
│       │   ├── LLAMA_Evaluator.ipynb
│       │   ├── GPT_Evaluator.ipynb
│       │   └── Gemini_Evaluator.ipynb
│       ├── LLM_Scores_Sarvam/
│       │   ├── Sarvam_EvalForm_Part_1 (Responses).xlsx
│       │   └── Sarvam_EvalForm_Part_2 (Responses).xlsx
│       ├── LLM_Scores_Llama4Scout/
│       │   ├── Llama_EvalForm_Part_1 (Responses).xlsx
│       │   └── Llama_EvalForm_Part_2 (Responses).xlsx
│       ├── LLM_Scores_GPT/
│       │   ├── GPT_EvalForm_Part_1 (Responses).xlsx
│       │   └── GPT_EvalForm_Part_2 (Responses).xlsx
│       └── LLM_Scores_Gemini/
│           ├── Gemini_EvalForm_Part_1 (Responses).xlsx
│           └── Gemini_EvalForm_Part_2 (Responses).xlsx
│
└── Analysis_Phase/
    ├── Codes/
    │   ├── NB1_Raw_Agreement_Analysis.ipynb
    │   ├── NB1_Raw_Agreement_Plots.ipynb
    │   ├── NB2_Cohen_Kappa_Analysis.ipynb
    │   ├── NB2_Cohen_Kappa_Plots.ipynb
    │   ├── NB3_Fleiss_Kappa_Analysis.ipynb
    │   ├── NB3_Fleiss_Kappa_Plots.ipynb
    │   ├── NB4_Gwet_AC_Analysis.ipynb
    │   ├── NB4_Gwet_AC_Plots.ipynb
    │   ├── NB5_Krippendorff_Analysis.ipynb
    │   ├── NB5_Krippendorff_Plots.ipynb
    │   ├── NB6_ICC_Analysis.ipynb
    │   ├── NB6_ICC_Plots.ipynb
    │   ├── NB7_Correlation_Analysis.ipynb
    │   ├── NB7_Correlation_Plots.ipynb
    │   ├── NB8_Pariksha_Ranking_Analysis.ipynb
    │   └── NB8_Pariksha_Ranking_Plots.ipynb
    └── outputs/
        ├── tables/
        │   ├── NB1_Raw_Agreement_Results.xlsx
        │   ├── NB2_Cohen_Kappa_Results.xlsx
        │   ├── NB3_Fleiss_Kappa_Results.xlsx
        │   ├── NB4_Gwet_AC_Results.xlsx
        │   ├── NB5_Krippendorff_Results.xlsx
        │   ├── NB6_ICC_Results.xlsx
        │   ├── NB7_Correlation_Results.xlsx
        │   ├── NB8_Agreement_Rate.xlsx
        │   ├── NB8_Item_Labels.xlsx
        │   ├── NB8_Multi_Rater_Metrics.xlsx
        │   ├── NB8_Optimism_Bias.xlsx
        │   ├── NB8_Pairwise_Cohen_Kappa.xlsx
        │   ├── NB8_Preference_Table.xlsx
        │   ├── NB8_System_Preference_Results.xlsx
        │   ├── table1_slt_agreement.xlsx
        │   ├── table1_slt_agreement.pdf
        │   ├── table2_score_agreement.xlsx
        │   └── table2_score_agreement.pdf
        └── graphs/
            ├── NB1_Raw_Agreement/
            ├── NB2_Cohen_Kappa/
            ├── NB3_Fleiss_Kappa/
            ├── NB4_Gwet_AC/
            ├── NB5_Krippendorff/
            ├── NB6_ICC/
            ├── NB7_Correlation/
            └── NB8_System_Preference/
```

*Sai Sudeep Das*
