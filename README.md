# Olympic 2024 Medallist Data Analysis

## Overview

This project analyzes the Olympic 2024 Medallists dataset, focusing on medal-winning athletes and their attributes. The goal was to structure the project properly, merge relevant datasets, and ensure a reproducible workflow while keeping raw data files excluded from the repository.

## Project Structure and Data Sources

### Setting Up the File Structure

To ensure a well-organized project, a structured file system was created with the following directories:
* data/ – Contains raw datasets (excluded from GitHub via .gitignore)
* clean_data/ – Stores processed and merged datasets (excluded from GitHub via .gitignore)
* scripts/ – Includes Python scripts and Jupyter notebooks for analysis.
* results/ – Stores visualizations or generated reports.
* documents/ – For any additional notes or supporting files.

The datasets were sourced from Kaggle: https://www.kaggle.com/datasets/muhammadehsan02/olympic-summer-games-paris-2024/

### Datasets Used

* Olympic 2024 Medallists (Olympic2024_Medallists.csv)
    Contains details of all athletes who won medals, including event, country, and medal type.
* Olympic 2024 Athletes (Olympic2024_Athletes.csv)
    Provides personal details, nationality, and disciplines for all Olympic 2024 athletes.

Note: Data files are ignored in .gitignore, requiring manual download to run the scripts.

### Merging Process & Justification

The medallist data was merged with the athlete dataset using a Left Join (how='left'). This approach was chosen because:

* It ensures all medalists remain in the dataset, even if they have missing personal details in the athletes dataset.
* If an athlete is in medallists_data but missing from athletes_data, their information (e.g., height, weight) will appear as NaN instead of being removed.

Alternative joins were considered but rejected:
* Inner Join: Would exclude medalists missing from the athletes dataset.
* Right/Outer Join: Would introduce non-medalists, making the dataset less focused.

Branching & Merging Decision
This project followed best practices by working on a separate branch (File_Structure) instead of modifying main directly. The purpose of this branch was to:

Implement a clear folder structure for better organization.
Keep the main branch clean while testing changes.
Ensure the project was well-structured before merging.
Once all necessary updates (folder structure, dataset organization, and .gitignore setup) were complete, I merged File_Structure back into main because:

The structured project was finalized and ready for the main repository.
Merging ensured all improvements were included in the final version.
This allowed for better documentation while keeping the history of changes intact.

Branching & Merging Decision

This project followed best practices by working on a separate branch (File_Structure) instead of modifying main directly. The purpose of this branch was to:

Implement a clear folder structure for better organization.
Keep the main branch clean while testing changes.
Ensure the project was well-structured before merging.
After reviewing the structured project, I decided to merge File_Structure into main because:

The structured files were finalized and ready for the main repository.
Merging ensured all improvements were included in the final version.
Keeping everything in File_Structure would make it harder to maintain long-term.
By working in a separate branch first, I was able to make necessary changes without affecting main until everything was properly set up. Now, main contains the finalized version of the project





