# TOPSIS Project – Sneha (102303723)

This repository contains the implementation of the **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** method as part of an academic assignment.  
The project is divided into **three parts**: command-line program, Python package, and a web service.

---

## Part-I: Command Line TOPSIS Program

A Python script to compute TOPSIS scores using command-line arguments.

**Command format**
python topsis.py <input_file> <weights> <impacts> <output_file>

**Example**
python topsis.py data.csv "1,1,1,1,1" "+,+,-,+,+" result.csv

**Output**
- Adds **Topsis Score** and **Rank** columns to the CSV
- Higher score indicates better alternative

---

## Part-II: Python Package (PyPI)

The TOPSIS program is converted into a Python package and uploaded to PyPI.

**PyPI Link**  
https://pypi.org/project/topsis-sneha-102303723/1.0.0/

**Installation**
pip install topsis-sneha-102303723

**Usage**
topsis <input_file> <weights> <impacts> <output_file>

If command is not recognized:
python -m topsis.topsis data.csv "2,1,3,1,2" "+,-,+,+,-" result.csv

A detailed user manual is available in `Part2/README.md`.

---

## Part-III: TOPSIS Web Service

A web-based TOPSIS application developed using **Flask**.

**Features**
- CSV file upload
- Weights and impacts input
- Email validation
- Result CSV sent via email

**Workflow**
1. Upload input CSV
2. Enter weights, impacts, and email ID
3. TOPSIS is executed on server
4. Result CSV is emailed to user

---

## Methodology (TOPSIS)

1. **Normalization**: The decision matrix is normalized using vector normalization so that all criteria are dimensionless and comparable.  
   Formula: rᵢⱼ = xᵢⱼ / √(∑xᵢⱼ²)

2. **Weighting**: Each normalized criterion is multiplied by its assigned weight to reflect its importance.  
   Formula: vᵢⱼ = wⱼ × rᵢⱼ

3. **Ideal Best / Worst**: For each criterion, determine the ideal best (maximum for beneficial, minimum for cost) and ideal worst (opposite).  
   - Benefit (+): best = max, worst = min  
   - Cost (−): best = min, worst = max  

4. **Separation Measures**: Calculate the Euclidean distance of each alternative from the ideal best and worst.  
   - Sᵢ⁺ = √(∑(vᵢⱼ − vⱼ⁺)²)  
   - Sᵢ⁻ = √(∑(vᵢⱼ − vⱼ⁻)²)

5. **TOPSIS Score**: Compute the relative closeness to the ideal solution.  
   - Cᵢ = Sᵢ⁻ / (Sᵢ⁺ + Sᵢ⁻)

6. **Ranking**: Alternatives are ranked based on their TOPSIS scores.  
   Higher score ⇒ Better rank

---

## Example Input (`data.csv`)



| Fund Name | P1   | P2   | P3  | P4   | P5    |
| --------- | ---- | ---- | --- | ---- | ----- |
| M1        | 0.84 | 0.71 | 6.7 | 42.1 | 12.59 |
| M2        | 0.91 | 0.83 | 7.0 | 31.7 | 10.11 |
| M3        | 0.79 | 0.62 | 4.8 | 46.7 | 13.23 |
| M4        | 0.78 | 0.61 | 6.4 | 42.4 | 12.55 |
| M5        | 0.94 | 0.88 | 3.6 | 62.2 | 16.91 |
| M6        | 0.88 | 0.77 | 6.5 | 51.5 | 14.91 |
| M7        | 0.66 | 0.44 | 5.3 | 48.9 | 13.83 |
| M8        | 0.93 | 0.86 | 3.4 | 37.0 | 10.55 |



---

## Example Output (`result.csv`)



| Fund Name | P1   | P2   | P3  | P4   | P5    | Topsis Score | Rank |
| --------- | ---- | ---- | --- | ---- | ----- | ------------ | ---- |
| M1        | 0.84 | 0.71 | 6.7 | 42.1 | 12.59 | 0.3821       | 6    |
| M2        | 0.91 | 0.83 | 7.0 | 31.7 | 10.11 | 0.3665       | 7    |
| M3        | 0.79 | 0.62 | 4.8 | 46.7 | 13.23 | 0.4964       | 4    |
| M4        | 0.78 | 0.61 | 6.4 | 42.4 | 12.55 | 0.3248       | 8    |
| M5        | 0.94 | 0.88 | 3.6 | 62.2 | 16.91 | 0.9721       | 1    |
| M6        | 0.88 | 0.77 | 6.5 | 51.5 | 14.91 | 0.5470       | 3    |
| M7        | 0.66 | 0.44 | 5.3 | 48.9 | 13.83 | 0.3950       | 5    |
| M8        | 0.93 | 0.86 | 3.4 | 37.0 | 10.55 | 0.5601       | 2    |



---


## Result Graph


![alt text](result_graph.png)


---


## Repository Structure


TOPSIS-SNEHA-102303723
├── Part1
├── Part2
├── Part3
├── Screenshots
│ ├── Part1
│ ├── Part2
│ └── Part3
├── data.csv
├── result.csv
├── README.md
└── .gitignore


---

## Author

**Sneha**  
Roll Number: **102303723**

---

