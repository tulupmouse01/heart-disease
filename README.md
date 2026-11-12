# heart-disease
a code that analyzes the data of a CSV file about heart failure and find death total and comorbidities
# #final project heart disease statistics

#numbers question
#NQ:Among the 299 patients with heart failure in the dataset,
#  what percentage died,
#  and what percentage of those who died had at least one of the
#  following comorbidities: smoking, diabetes, anemia, or high blood pressure? 
import pandas as pd
import matplotlib.pyplot as plt
import csv

with open(r"C:\Users\jenki\Downloads\heart_failure_clinical_records_dataset.csv") as file:
    data = csv.reader(file)
    first_line = next(data)
    #print("first:", first_line)
    num_comorbs = {"no comorbidities":0, "one comorbidity":0, 
                   "two comorbidities":0, "three comorbidities":0,
                     "four comorbidities":0}
    labels = list(num_comorbs.keys())

    morb=0
    death_count = 0
    patients = 0
    comorb = 0
    # finding the % of people that died in total
    for line in data:
        patients += 1 #numb of people 
        if line[12] != "0":
            death_count += 1  # num who died
            comorb = 0
            if line[1] != "0": #aneamia
                comorb += 1
            if line[3] != "0": #diabetes
                comorb += 1
            if line[5] != "0": #high blood sugar
                comorb += 1
            if line[10] != "0": #smoking
                comorb += 1
            key_name = labels[comorb]
            num_comorbs[key_name] += 1
            if comorb >=1:
                morb += 1  #at least one comorb 
            
    deci=death_count/patients  # decimal amount of paitents that died
    percent = round(deci*100,2)
    print("Percent of patients who died was ",percent, "%", sep="")   # % of paients that died
    print("Percent with comorbidity was ", round(morb/death_count *100,2),"%", sep="")
    print("Num of people with idiviual amount of comorbities", num_comorbs)

    

survival_count = patients - death_count 
pie_data = pd.Series(
    [survival_count, death_count],
    index=["Survived", "Deceased"]
)
#pie chart for death rate
plt.figure(1)
pie_data.plot.pie(
    autopct='%1.1f%%',
    ylabel='',
    title='Patient Survival vs Death'
)


# with or without any combidities
no_comorb_deaths = death_count - morb
plt.figure(2) #allows me to open the files all together
pie_data_2 = pd.Series(
    [morb, no_comorb_deaths],
    index=["Atleast one comorbidity", "No comorbidities"]
)
#pie chart for death rate
pie_data_2.plot.pie(
    autopct='%1.1f%%',
    ylabel='',
    title='Patient Death with Comorbidities vs Without Comorbidities'
)

# broken up for one two three or four
plt.figure(3)
bar_graph = pd.Series(num_comorbs)

bar_graph.plot.bar(
    rot=90,
    ylabel = 'Number of Patients',
    title = 'Number of Comorbidities Among Deseased Patients'
)



plt.tight_layout()
plt.show()



    
    



    





            
            









        




