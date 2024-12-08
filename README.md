Python Code for handling missing values.

import pandas as pd
import numpy as np

# Load the dataset
data = pd.read_csv('demo.csv')

# Display the first few rows of the dataset to understand its structure
print("Original Dataset:")
print(data.head())

# Replace missing values in the 'price' column with NaN
data['price'] = data['price'].apply(lambda x: np.nan if pd.isnull(x) else x)

# Display the updated dataset
print("\nDataset after replacing missing values in 'price' column with NaN:")
print(data.head())

# Save the updated dataset
data.to_csv('demo_updated.csv', index=False)
print("\nUpdated dataset saved as 'demo_updated.csv'")
