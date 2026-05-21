# geo876-final-project
The main aim is to design an automated pipeline that reads wildfire data, extracts the most useful information, performs a targeted analysis, and presents the results clearly on an interactive map.

# Research Question
Where are the most severe wildfires located in India?

Severity is measured using **Fire Radiative Power (FRP)** from the VIIRS satellite dataset.

# Dataset
VIIRS SNPP VRT Active Fire Product

Key attributes used:
- latitude
- longitude
- acquisition_date
- acquisition_time
- frp (Fire Radiative Power)

## The plan 

1. Define study area (India boundary)
2. Access VIIRS fire detection dataset
3. Clean data
   - Clip to India
   - Remove duplicates
   - Remove missing values
   - Convert acquisition time
4. Calculate summaries
   - Identify fires with highest FRP
5. Visualize
   - One map per day showing fire severity
6. Interpret spatial patterns to be able to explain what the maps show

## Running the Project

Clone repository:

```bash
git clone https://github.com/ruvenekoshava/geo876-final-project.git

# Step 1 in Notebook 1
Load the data 
Select only the region of India using coordinates
Remove duplicates (there were no duplicates)
Remove fires with low confidence
Convert date and time to datetime
Keep only relevant columns
Save to csv

# Step 2 in Notebook 2
Load new csv
Normalise the frps by taking the value of the frp and then divide by the max frp and rename the new column as frp_norm
Take only the date from the datetime
Choose the color scheme for the fires
For all the days:
    - Plot the fire points
    - Plot the kernel density


#Interpretation
Fire severity can mean intensity (i.e. frp) or the impact it has on the environment. The points show where there are the most fires because many little fires can be just as destructive. One intense fire can also be extremely destructive if it is over a huge area or last very long. 