<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Assessing Human-LLM Alignment in Odia Error Evaluation</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: "Times New Roman", Times, serif;
    font-size: 15px;
    line-height: 1.85;
    color: #1a1a1a;
    background: #fafaf8;
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 48px 80px;
    text-align: justify;
  }
  h1 {
    font-size: 1.9rem;
    font-weight: normal;
    text-align: center;
    margin-bottom: 28px;
    line-height: 1.3;
  }
  h2 {
    font-size: 1rem;
    font-weight: bold;
    margin: 36px 0 10px;
    text-transform: uppercase;
    letter-spacing: 0.06em;
  }
  p { margin-bottom: 12px; text-align: justify; }
  .keywords {
    font-size: 0.88rem;
    color: #555;
    margin-top: 16px;
  }
  .keywords span { font-weight: bold; color: #333; }
  hr { border: none; border-top: 1px solid #ccc; margin: 32px 0; }
  pre {
    font-family: "Courier New", Courier, monospace;
    font-size: 0.8rem;
    background: #f0ede8;
    border-left: 3px solid #aaa;
    padding: 20px 24px;
    overflow-x: auto;
    line-height: 1.65;
    margin: 12px 0;
    text-align: left;
  }
  .footer {
    text-align: right;
    margin-top: 52px;
    font-size: 0.82rem;
    color: #999;
    font-style: italic;
  }
</style>
</head>
<body>

<h1>Assessing Human-LLM Alignment in the Evaluation<br>of Odia Spelling and Grammatical Errors</h1>

<h2>Abstract</h2>

<p>This study measures how consistently humans and large language models evaluate Odia grammatical error correction outputs. Two LLMs, Sarvam-105B and LLaMA-4-Scout-17B, annotated 50 Odia sentences across five error categories: Script Normalization, Spelling, Grammatical, Code-Mixing, and Correct. Six raters (two human linguists and four LLM judges) scored every annotation on four criteria covering error detection, span quality, category assignment, and correction quality. Inter-annotator agreement was measured using eight metrics covering raw agreement, chance-corrected measures, ordinal reliability, and rank correlation. A system preference analysis further examined which annotator LLM each evaluator preferred per sentence, and whether self-evaluating LLMs showed measurable optimism bias. Results show strong human agreement and moderate to low human–LLM alignment, with self-evaluating LLMs showing consistent positive bias toward their own outputs particularly on correction tasks.</p>

<p class="keywords"><span>Keywords:</span> &nbsp; Odia NLP &nbsp;&middot;&nbsp; Grammatical Error Correction &nbsp;&middot;&nbsp; Inter-Annotator Agreement &nbsp;&middot;&nbsp; LLM-as-Judge &nbsp;&middot;&nbsp; Optimism Bias &nbsp;&middot;&nbsp; IAA Metrics</p>

<hr>

<h2>Project Root Folder</h2>

<pre>
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
</pre>

<p class="footer">Sai Sudeep Das</p>

</body>
</html>
