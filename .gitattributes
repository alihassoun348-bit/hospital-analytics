import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

data = pd.read_csv("patient_health_data_20.csv")

def add_patient(data, new_patient):
    data.loc[len(data)] = new_patient
    print("Patient added successfully!")

def set_patient_as_healthy(data, patient_id):
    index = data[data['patient_id'] == patient_id].index

    if len(index) > 0:
        data.loc[index, 'discharge_status'] = "Recovered"
        print("Patient marked as Recovered!")
    else:
        print("Patient not found!")

def generate_report(data, report_type):

    if report_type == "department_count":
        print(data['department'].value_counts())

    elif report_type == "average_stay":
        print(data['length_of_stay_days'].mean())

    elif report_type == "diagnosis_frequency":
        print(data['primary_diagnosis'].value_counts())

    elif report_type == "visit_type":
        print(data['visit_type'].value_counts())

    elif report_type == "long_stay":
        print(data[data['length_of_stay_days'] >= 7])

    else:
        print("Invalid report type.")


while True:

    print("\n===== Hospital Analytics System =====")
    print("1. Add patient")
    print("2. Set patient as healthy")
    print("3. Generate report")
    print("4. Show graphs")
    print("5. Exit")

    choice = input("Enter choice: ")

    if choice == "1":

        new_patient = {
            'patient_id': int(input("Enter ID: ")),
            'department': input("Enter Department: "),
            'primary_diagnosis': input("Enter Diagnosis: "),
            'length_of_stay_days': int(input("Enter Stay Days: ")),
            'visit_type': input("Enter Visit Type: "),
            'discharge_status': input("Enter Status: ")
        }

        add_patient(data, new_patient)

    elif choice == "2":

        pid = int(input("Enter Patient ID: "))
        set_patient_as_healthy(data, pid)

    elif choice == "3":

        print("\nAvailable reports:")
        print("department_count")
        print("average_stay")
        print("diagnosis_frequency")
        print("visit_type")
        print("long_stay")

        report = input("Enter report type: ")
        generate_report(data, report)

    elif choice == "4":

        print("Showing graphs...")

        plt.figure(figsize=(8,5))
        sns.countplot(x='department', data=data)
        plt.title("Patient Count by Department")
        plt.xticks(rotation=45)
        plt.show()

        plt.figure(figsize=(8,5))
        data.groupby('department')['length_of_stay_days'].mean().plot(kind='bar')
        plt.title("Average Stay by Department")
        plt.ylabel("Days")
        plt.show()

        plt.figure(figsize=(8,5))
        data['primary_diagnosis'].value_counts().plot(kind='bar')
        plt.title("Diagnosis Frequency")
        plt.ylabel("Count")
        plt.show()

    elif choice == "5":
        print("Program Closed. Goodbye!")
        break

    else:
        print("Invalid choice. Try again.")# Auto detect text files and perform LF normalization
* text=auto
