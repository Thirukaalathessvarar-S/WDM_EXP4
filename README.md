# EX-04 Implementation of Cluster and Visitor Segmentation for Navigation patterns 
### Aim: 
To implement Cluster and Visitor Segmentation for Navigation patterns in Python. &emsp;&emsp;&emsp;&emsp;**DATE :02.06.2025**
### Description:
Cluster visitor segmentation refers to the process of grouping or categorizing visitors to a website,application, or physical location into distinct clusters or segments based on various characteristics or behaviors they exhibit.This segmentation allows businesses or organizations to better understand their audience and tailor their strategies, marketing efforts,or services to meet the specific needs and preferences of each cluster.
  
### Procedure:
1) Read the CSV file: Use pd.read_csv to load the CSV file into a pandas DataFrame.
2) Define Age Groups by creating a dictionary containing age group conditions using Boolean conditions.
3) Segment Visitors by iterating through the dictionary and filter the visitors into respective age groups.
4) Visualize the result using matplotlib.
### Program:
```python
import pandas as pd
visitor_df = pd.read_csv('clustervisitor.csv')
# Perform segmentation based on characteristics (e.g., age groups)
age_groups = {
    'Young': visitor_df['Age'] <= 30,
    'Middle-aged': (visitor_df['Age'] > 30) & (visitor_df['Age'] <= 50),
    'Elderly': visitor_df['Age'] > 50
}
for group, condition in age_groups.items():  
    visitors_in_group = visitor_df[condition] 
    print(f"Visitors in {group} age group:")
    print(visitors_in_group)
```
### Output:
<img height=43% src="https://github.com/user-attachments/assets/16c756c0-8e8a-4238-9060-912d51862340">

### Visualization:
```Python
import matplotlib.pyplot as plt
# Create a list to store counts of visitors in each age group
visitor_counts=[]
# Count visitors in each age group
for group,condition in age_groups.items():
  visitors_in_group=visitor_df[condition]
  visitor_counts.append(len(visitors_in_group))   
# Define age group labels and plot a bar chart
age_group_labels=list(age_groups.keys())
plt.figure(figsize=(8, 6))
plt.bar(age_group_labels, visitor_counts, color='pink')
plt.xlabel('Age Groups')
plt.ylabel('Number of Visitors')
plt.title('Visitor Distribution Across Age Groups')
plt.show()
```
### Output:
![image](https://github.com/user-attachments/assets/85a59c1c-1a07-4239-8ac1-9a0993df8e86)
### Result:
Thus the cluster and visitor segmentation for navigation patterns was implemented successfully in python.
