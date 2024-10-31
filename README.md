# Learning from the Best: Replicating Equity Analyst Skills with AI for Top 100 Indian Stocks

## Overview

This project aims to replicate and adapt the methodologies from the research paper:

**"Learning from the Best: Can Artificial Intelligence Replicate Equity Analyst Skill?"**

Our objective is to apply the same approach to the top 100 Indian companies by market capitalization. By leveraging Large Language Models (LLMs) like GPT-4, we seek to emulate the skills of equity analysts in interpreting earnings call transcripts and predicting stock performance in the Indian market.

## Table of Contents

- [Overview](#overview)
- [Project Structure](#project-structure)
- [Methodology](#methodology)
  - [1. Data Collection](#1-data-collection)
  - [2. Transcript Summarization](#2-transcript-summarization)
  - [3. Template Creation](#3-template-creation)
  - [4. Analyst Insight Score (AIS) Calculation](#4-analyst-insight-score-ais-calculation)
  - [5. Empirical Evaluation](#5-empirical-evaluation)
- [Data Requirements](#data-requirements)
- [Dependencies](#dependencies)
- [Getting Started](#getting-started)
  - [1. Clone the Repository](#1-clone-the-repository)
  - [2. Install Dependencies](#2-install-dependencies)
  - [3. Data Preparation](#3-data-preparation)
  - [4. Run the Notebook](#4-run-the-notebook)
- [Project Files](#project-files)
- [Results and Findings](#results-and-findings)
- [Considerations](#considerations)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Project Structure

- `data/`: Contains all the data files required for the analysis.
- `notebooks/`: Jupyter notebooks used for data analysis and modeling.
- `scripts/`: Python scripts for data processing and analysis.
- `results/`: Output files, figures, and tables generated from the analysis.
- `README.md`: Project overview and instructions.
- `requirements.txt`: List of Python dependencies.

## Methodology

Our approach follows the two-stage methodology outlined in the original paper, adapted for the Indian market context.

### 1. Data Collection

- **Earnings Call Transcripts**: Collected transcripts for the top 100 Indian companies by market capitalization over the past two years.
- **Financial Data**: Obtained financial metrics such as market capitalization, price-to-book ratios, and Standardized Unexpected Earnings (SUE).
- **Analyst Revisions Data**: Gathered data on analysts' consensus price targets, recommendations, and EPS forecasts.
- **Stock Returns Data**: Collected historical stock returns for the asset pricing tests.

### 2. Transcript Summarization

- Used GPT-4 to generate concise summaries of the earnings call transcripts.
- Summaries focus on key points from both the presentation and Q&A sections.
- Summarization helps reduce processing costs and standardize content for analysis.

### 3. Template Creation

- Developed a template of evaluation criteria reflecting the concerns of Indian equity analysts.
- Analyzed the implied intent behind analysts' questions to identify key themes.
- Organized these themes into major criteria and sub-criteria:
  - **Growth Potential**
  - **Earnings Quality**
  - **Quality of Management**
  - **Business Risks**

### 4. Analyst Insight Score (AIS) Calculation

- Employed GPT-4 to evaluate each company's earnings call summary against the developed template.
- Assigned scores to each sub-criterion (-1, 0, +1) based on the information in the summaries.
- Calculated the AIS for each company by averaging the scores of the major criteria.

### 5. Empirical Evaluation

- **Alignment Test**: Assessed whether the AIS aligns with actual analysts' revision behaviors in the Indian market.
- **Asset Pricing Test**: Examined the AIS's ability to forecast cross-sectional returns for Indian stocks.
- **Baseline Comparison**: Evaluated the effectiveness of a baseline AIS score generated without the analyst template.
- **Bias Investigation**: Investigated potential biases in AIS scores using counterfactual transcript tests.

## Data Requirements

The following data files are required to run the analysis:

- `data/ais_scores.csv`: AIS scores for the top 100 Indian stocks.
- `data/analyst_revisions.csv`: Analyst revisions data (consensus price targets, recommendations, EPS forecasts).
- `data/financial_data.csv`: Financial metrics (SUE, market capitalization, price-to-book ratios).
- `data/stock_returns.csv`: Historical stock returns data.
- `data/risk_free_rate.csv`: Risk-free rate data for excess return calculations.
- `data/ff_factors.csv`: Fama-French factor data for the Indian market.

**Note**: Ensure all data files are properly formatted and stored in the `data/` directory.

## Dependencies

- Python 3.7 or higher
- Required Python packages (listed in `requirements.txt`):
  - pandas
  - numpy
  - statsmodels
  - scipy
  - matplotlib
  - seaborn
  - scikit-learn
- GPT-4 or GPT-3.5 API access for generating summaries and calculating AIS.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name
```

### 2. Install Dependencies

Create a virtual environment (optional but recommended):

```bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
```

Install the required packages:

```bash
pip install -r requirements.txt
```

### 3. Data Preparation

- Place all required data files in the `data/` directory.
- Ensure data files are named correctly and formatted as per the requirements.

### 4. Run the Notebook

Navigate to the `notebooks/` directory and launch Jupyter Notebook or JupyterLab:

```bash
jupyter notebook
```

Open the main analysis notebook (e.g., `notebooks/ais_analysis.ipynb`) and run the cells sequentially.

## Project Files

- `notebooks/ais_analysis.ipynb`: Main notebook containing the empirical evaluation.
- `data/`: Directory containing all required data files.
- `scripts/`: Contains any additional Python scripts used for data processing.
- `results/`: Output files, including figures and tables generated from the analysis.
- `requirements.txt`: List of Python dependencies.
- `README.md`: Project description and instructions.

## Results and Findings

- **Alignment with Analysts**: AIS scores show significant correlation with analysts' revision behaviors, indicating that the AI model effectively captures analysts' qualitative assessments.
- **Predictive Power**: Portfolios formed based on AIS scores demonstrate the ability to earn abnormal returns, outperforming those based on traditional metrics like SUE.
- **Baseline Comparison**: Incorporating analyst expertise into the AIS calculation enhances its predictive accuracy compared to a baseline AIS generated without the template.
- **Bias Investigation**: Counterfactual transcript tests suggest that AIS scores are primarily driven by content sentiment rather than inherent biases in the AI model.

**Note**: Detailed results, figures, and tables can be found in the `results/` directory and within the analysis notebook.

## Considerations

- **Cultural and Market Differences**: Adjustments were made to account for differences between the U.S. and Indian markets, such as regulatory environments and reporting standards.
- **Data Quality**: The accuracy of the analysis depends on the quality of the input data. Efforts were made to ensure data completeness and reliability.
- **Model Adaptation**: The AI model was fine-tuned to handle nuances specific to the Indian market, including industry-specific terminology and context.

## Contributing

We welcome contributions to enhance the project. Please follow these steps:

1. Fork the repository.
2. Create a new branch: `git checkout -b feature/your-feature-name`.
3. Commit your changes: `git commit -am 'Add new feature'`.
4. Push to the branch: `git push origin feature/your-feature-name`.
5. Submit a pull request.

Please ensure that your contributions align with the project's objectives and that you have the rights to share any code or data you contribute.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- **Original Paper Authors**: We acknowledge the authors of the paper "*Learning from the Best: Can Artificial Intelligence Replicate Equity Analyst Skill?*" for their groundbreaking work.
- **OpenAI**: For providing access to GPT-4, enabling advanced natural language processing capabilities.
- **Financial Data Providers**: We thank the providers of financial and market data used in this analysis.

---

If you have any questions or need further assistance, please feel free to contact the project maintainer at benjochem@gmail.com
