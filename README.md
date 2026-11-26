# FIFA World Cup 2022: Group Stage Analysis

Exploratory data analysis of the 2022 FIFA World Cup group stage
using Python, Pandas, and Matplotlib.

This project examines team performance, scoring patterns, and
qualification outcomes through data cleaning, validation,
summary statistics, and visualizations.

## Project Objectives

- Clean and validate the original points table.
- Identify the highest-scoring teams and teams conceding the fewest goals.
- Compare goal differences and scoring totals across groups.
- Explore the relationship between points and qualification.
- Present findings through charts and written insights.

## Tools

- Python
- Pandas
- Matplotlib
- Jupyter Notebook

## Data and Reference

The analysis uses `Fifa World Cup Points Table.csv`, containing
group-stage records for 32 teams across 8 groups.

The Kaggle resource used to locate the data is:

- [fifa worldcup pts table — Nikhat Abdul Salam](https://www.kaggle.com/code/nikhatabdulsalam/fifa-worldcup-pts-table)

This link points to a Kaggle notebook rather than a standalone
dataset page. The original CSV publisher and dataset license
have not been independently confirmed.

### Data Dictionary

| Column | Description |
|---|---|
| Teams | Team name; `(Q)` indicates qualification |
| MP | Matches played |
| W | Wins |
| D | Draws |
| L | Losses |
| GF | Goals scored |
| GA | Goals conceded |
| +/- | Goal difference |
| Pts | Points earned |
| Group | Group assignment |

During cleaning:

- `Teams` is renamed to `Team`.
- `+/-` is renamed to `GD`.
- A Boolean `Qualified` column is extracted from `(Q)`.
- The unnecessary exported index column is removed.

## Analysis Workflow

### 1. Explore the Data

Inspect the dataset's dimensions, column types, missing values,
duplicate records, and descriptive statistics.

### 2. Clean the Data

Standardize column names, clean team names, extract qualification
status, and correct inconsistent values.

### 3. Validate the Data

Check that:

- Matches played equal wins plus draws plus losses.
- Points equal three times wins plus draws.
- Goal difference equals goals scored minus goals conceded.
- Goals scored and conceded balance within each group.
- Each group contains four teams and two qualifiers.

### 4. Analyze and Visualize

Answer six questions:

1. Which teams scored the most goals?
2. Which teams conceded the fewest goals?
3. Which teams had the highest and lowest goal differences?
4. Which group produced the most goals?
5. What was the most common points total?
6. Did four points guarantee qualification?

## Key Findings

The following findings are based on the cleaned dataset.

| Metric | Result |
|---|---:|
| Teams | 32 |
| Groups | 8 |
| Matches | 48 |
| Total goals | 119 |
| Goals per match | 2.48 |

### Team Performance

- **England and Spain** were the highest-scoring teams,
  with **9 goals each**.
- **England** recorded the highest goal difference at **+7**.
- **Costa Rica** recorded the lowest goal difference at **−8**.
- Netherlands, USA, Tunisia, Morocco, Croatia, and Brazil
  conceded only **1 goal each**.
- Tunisia was the only team among those six that did not qualify.

### Group Scoring

- **Group E** produced the most goals, with **22**.
- **Groups D and F** produced the fewest, with **11 each**.
- Group E produced twice as many goals as either Group D or Group F.

These totals describe scoring volume, not group strength
or competitiveness.

### Points and Qualification

- **4 points** was the most common total, achieved by **10 teams**.
- Only **3 of those teams** qualified: Poland, Spain, and South Korea.
- All **13 teams with at least 5 points** qualified.
- All **9 teams with 3 points or fewer** were eliminated.

These outcomes describe the 2022 group stage only.
They are not guaranteed qualification thresholds for future tournaments.

## Repository Structure

```text
fifa-world-cup-2022-analysis/
├── data/
│   └── Fifa World Cup Points Table.csv
├── outputs/
│   ├── .gitkeep
│   ├── corrections_log.csv
│   └── worldcup_clean.csv
├── README.md
├── requirements.txt
└── world_cup_2022_analyst.ipynb
```

## Project Files

- [Analysis notebook](world_cup_2022_analyst.ipynb)
- [Original CSV](data/Fifa%20World%20Cup%20Points%20Table.csv)
- [Cleaned dataset](outputs/worldcup_clean.csv)
- [Correction log](outputs/corrections_log.csv)

## How to Run

1. Download or clone this repository.
2. Open a terminal in the project folder.
3. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Start Jupyter Notebook:

   ```bash
   jupyter notebook
   ```

5. Open `world_cup_2022_analyst.ipynb`.
6. Run the cells from top to bottom.

The notebook uses a relative input path:

```python
file_path = Path("data") / "Fifa World Cup Points Table.csv"
```

Run it from the project folder so this path resolves correctly.
Generated CSV files are saved in `outputs`.

## Data Quality

The original CSV contains inconsistent values.

Selected values for Saudi Arabia, Australia, Tunisia, Morocco,
and Belgium are corrected in the notebook. The correction log
records each affected team, column, original value, and new value.

Numerical checks pass after correction. These checks establish
internal consistency, but do not independently verify historical
accuracy. Supporting sources for the corrections remain to be documented.

## Limitations

- The dataset covers the group stage only.
- Team totals do not show individual match scores or the order
  in which results occurred.
- Comparisons do not account for opponent strength.
- Descriptive patterns do not establish causation or predict
  future tournament outcomes.

## Conclusion

Goals scored, goals conceded, goal difference, and points
provide different perspectives on team performance.

Scoring many goals or conceding few goals did not independently
guarantee qualification. Qualification also depended on each team's
position within its group and the applicable tiebreaking criteria.

## Acknowledgments

Thanks to Nikhat Abdul Salam for sharing the
[Kaggle notebook](https://www.kaggle.com/code/nikhatabdulsalam/fifa-worldcup-pts-table)
referenced for this project.
