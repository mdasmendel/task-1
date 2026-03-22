# Integration of Multi-Omic Data for Identifying Biomarkers Associated with Type 2 Diabetes Mellitus

## 📁 Project Structure

```
├── data/
│   ├── NSPT_metabolomics.csv               # Original NSPT metabolomic dataset (3,037 obs × 351 vars)
│   ├── NSPT_proteomics.csv                 # Original NSPT proteomic dataset
│   ├── Summary_statistics_NSPT_EWAS.xlsx   # EWAS summary statistics
│   ├── Summary_statistics_NSPT_MWAS.xlsx   # MWAS summary statistics
│   ├── Summary_statistics_NSPT_PWAS.xlsx   # PWAS summary statistics
│   ├── NSPT_Assignment1_Database.xlsx      # Generated assignment database (200 obs × 23 vars)
│   └── NSPT_Assignment1_Database.csv       # Same database in CSV format
├── notebooks/
│   └── Assignment1_Database_Creation_NSPT.ipynb  # Assignment 1 notebook
├── figures/
│   ├── continuous_variables_distribution.png     # Histograms of continuous variables
│   ├── dichotomous_variables_distribution.png    # Pie charts of dichotomous variables
│   └── correlation_matrix.png                    # Correlation heatmap
├── requirements.txt                              # Python dependencies
└── README.md
```

## 🚀 Quick Start

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Launch Jupyter Lab:
```bash
jupyter lab
```

3. Open `notebooks/Assignment1_Database_Creation_NSPT.ipynb`

## 📓 Assignment 1 — Database Creation & Analysis

The notebook `Assignment1_Database_Creation_NSPT.ipynb` performs the following:

### Step 1 — Load Original NSPT Data
Loads the full NSPT (Nightingale Health Study) metabolomic dataset containing **3,037 observations × 351 variables** from `data/NSPT_metabolomics.csv`. Columns include lipid markers such as `TG`, `CH`, `ApoA1`, `ApoB`, `LHCR`, `GLC`, lipoprotein particle concentrations, and more.

### Step 2 — Construct the Research Database (200 × 23)
Creates a structured database of **200 patients** and **23 variables** derived from the original NSPT data, satisfying the assignment requirements:

| Requirement | Variables Created |
|---|---|
| **Text (≥1)** | `Patient_ID` (format: `NSPT_001`, `NSPT_002`, ...) |
| **Continuous (≥4, excl. age)** | `TG_mmol_L`, `CH_mmol_L`, `ApoA1_g_L`, `ApoB_g_L`, `HDL_mmol_L`, `GLC_mmol_L`, `TG_HDL_ratio`, `ApoB_ApoA1_ratio`, `LHCR_continuous`, `L0CH_continuous`, `V0PN_level`, `L0PN_level`, `IDPN_level` (13 total) |
| **Dichotomous (≥3, excl. sex/residence)** | `T2DM_Status` (16% positive), `High_CV_Risk` (25%), `Severe_Dyslipidemia` |
| **Ordinal (≥3)** | `TG_Category` (4 levels), `CH_Category` (4 levels), `Metabolic_Risk_Stage` (4 levels) |
| **Additional** | `Biological_Sex`, `Age`, `Residence` |

### Step 3 — Verification
Prints the full variable list and verifies that all assignment requirements are met (≥150 observations, ≥20 variables, correct variable type counts).

### Step 4 — Export
Saves the database to:
- `data/NSPT_Assignment1_Database.xlsx` (Excel)
- `data/NSPT_Assignment1_Database.csv` (CSV)

### Step 5 — Exploratory Data Analysis
- **Descriptive statistics** for all continuous variables (mean, std, min, max, quartiles)
- **Distribution of dichotomous variables** — counts and percentages for T2DM, CV risk, dyslipidemia
- **Distribution of ordinal variables** — category counts for TG, CH, metabolic risk

### Step 6 — Visualizations
Generates three figures saved to `figures/`:

| Figure | Description |
|---|---|
| `continuous_variables_distribution.png` | 3×3 grid of histograms with KDE for TG, CH, ApoA1, ApoB, HDL, GLC, TG/HDL ratio, ApoB/ApoA1 ratio, Age |
| `dichotomous_variables_distribution.png` | Pie charts showing distribution of T2DM Status, High CV Risk, Severe Dyslipidemia |
| `correlation_matrix.png` | Heatmap of Pearson correlations between clinically relevant variables |

##  Dependencies

`numpy`, `pandas`, `matplotlib`, `seaborn`, `scipy`, `scikit-learn`, `statsmodels`, `openpyxl`, `plotly`, `jupyterlab`

See `requirements.txt` for full list with versions.
