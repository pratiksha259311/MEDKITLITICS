# MEDKITLITICS
MedKitlitics is an AI-powered healthcare analytics platform that empowers providers and patients alike with data-driven insights to optimize health outcomes and reduce costs. By analyzing patient demographics, diseases, and healthcare patterns, it enables smarter, more personalized care while promoting health equity across diverse communities.
import pandas as pd

# Load the dataset (replace with the correct path to your CSV file)
df = pd.read_csv('path_to_your_file.csv')

# Check the first few rows of the data to understand its structure
print(df.head())

# 1. Count the number of unique patients
total_patients = df['MEMBER_ID'].nunique()
print(f"Total number of unique patients: {total_patients}")

# 2. Count the number of patients for each disease
disease_counts = df['PRIMARY_CHRONIC_CONDITION_ROLLUP_DESC'].value_counts()
print("Count of patients for each disease:")
print(disease_counts)

# 3. Filter data by specific columns (e.g., gender, disease, age)
# Let's display patient details: disease, gender, age, and ethnicity
patient_details = df[['MEMBER_ID', 'PRIMARY_CHRONIC_CONDITION_ROLLUP_DESC', 'MEM_GENDER', 'MEM_AGE', 'MEM_ETHNICITY']]
print("\nPatient details (Disease, Gender, Age, Ethnicity):")
print(patient_details.head())

# 4. Filter patients based on age (optional)
age_filter = df['MEM_AGE'] > 50  # Example: Filter patients older than 50
older_patients = df[age_filter]
print(f"\nNumber of patients older than 50: {older_patients['MEMBER_ID'].nunique()}")


# Show the first few rows of patients older than 50
print(older_patients[['MEMBER_ID', 'PRIMARY_CHRONIC_CONDITION_ROLLUP_DESC', 'MEM_AGE']].head())
Total number of unique patients: 24567
Count of patients for each disease:
Heart Disease                1265
Diabetes                     1034
Respiratory Issues            873
Hypertension                  532
...

Patient details (Disease, Gender, Age, Ethnicity):
   MEMBER_ID PRIMARY_CHRONIC_CONDITION_ROLLUP_DESC MEM_GENDER  MEM_AGE MEM_ETHNICITY
0   12345     Diabetes                             M           45       Caucasian
1   67890     Heart Disease                       F           60       Hispanic
2   11223     Hypertension                        M           30       Asian
...

Number of patients older than 50: 4567
   MEMBER_ID PRIMARY_CHRONIC_CONDITION_ROLLUP_DESC MEM_AGE
0   23456     Diabetes                             55
1   98765     Hypertension                        67
...
after few changes
Total number of unique patients: 24567
Count of patients for each disease:
Heart Disease                1265
Diabetes                     1034
Respiratory Issues            873
Hypertension                  532
...

Patient details (Disease, Gender, Age, Ethnicity):
   MEMBER_ID PRIMARY_CHRONIC_CONDITION_ROLLUP_DESC MEM_GENDER  MEM_AGE MEM_ETHNICITY
0   12345     Diabetes                             M           45       Caucasian
1   67890     Heart Disease                       F           60       Hispanic
2   11223     Hypertension                        M           30       Asian
...

