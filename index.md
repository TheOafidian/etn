# Electronic Traineeship Notebook (ETN)

## Table of Contents
1. [Traineeship Documentation Plan](#TDP)
2. [Background information on the traineeship topic](#background)
3. [Personal Development](#pers-dev)
4. [Tasks](#tasks)  
  - [ ] [Exploration of raw data formats from HPLC instrument](#task1)  
  - [x] [Download and install DELPHI repository](#task2)
  - [ ] [Create a "visitor" for raw HPLC data and generate tsv file](#task3)
  - [ ] [Deal with compressed data HPLC files](#task4)   

[//]: # (Intermediate Evaluation Traineeship)

[//]: # (Self Assessment at the End of Traineeship)

[//]: # (Reflection on International/Intercultural Aspects)
# Traineeship Documentation Plan <a name="TDP"></a>

## Tentative Planning
- Which tasks to perform during traineeship (brief)
- When are tasks planned to be performed
- Look into DELPHI the Disqover data platform that serves as AelinTx's one stop shop for data on research & development activities. -> Current priority
- Find a way to decompress .lcra files. -> Halfway through the traineeship?

## Data Management
- How and where will data be stored and structured? (FAIR)
- Data will be visualized using the DELPHI platform, ensuring adherence to the FAIR principles upon which it is heavily inspired. The raw lcms data will be stored in a subfolder in "compound creation experiment" folders on the shared server, as a sibling to a lookup file pertaining the synthesis and purification of the compound. 

## Traceability of Steps and Methods
This git repository markdown page will be used to document the project steps in a traceable manner.

## Version Control of Code

The code will be stored in [this private git repository](https://github.com/TVR-AelinTX/traineeship). 
Access will be given to the internal and external traineeship coordinators before the start of the traineeship. 
Links to scripts pertaining to tasks and subtasks of the traineeship will be provided in the ETN and can be accessed by the authorized coordinators.

# Background Information on the traineeship topic <a name="background"></a>

## HPLC
For the purification of the peptides manufactured in the lab, a method on a Reverse Phase High Performance Liquid Chromatography (RP-HPLC) system is used. The reverse phase points to the fact that a hydrophobic stationary phase is used, while the mobile phase initially is more hydrophilic in nature. The peptide is dissolved and injected with a constant flow of mobile phase into a column, the stationary phase. After several minutes the gradient of the mobile phase is shifted towards a more hydrophobic end. The peptide and its impurities bound to the column then each have their own 'sweet spot' of hydrophobicity where they will start prefering the mobile phase over the column and they will elute. This principle is used to separate the peptide of interest from any unwanted side-products from synthesis.

[//]: # Personal Development <a name="pers-dev"></a>

# Tasks <a name="tasks"></a>
## Exploration of raw data formats from HPLC instrument <a name="task1"></a>
  **01/02/2022**: First look at the data with exploratory [jupyter notebook](https://github.com/TVR-AelinTX/traineeship/blob/main/data_exploration/HPLC/HPLC%20Data.ipynb)
  
## Download and install Delphi repository (ELN based on Ontoforce's Disqover platform) <a name="task2"></a>
  **01/02/2022**: 
  Download repo and installing dependencies.
  
  Install, explore and use Pycharm. Issues using WSL interpreter (only supported in professional version). 
  Continued using VS Code for now, perhaps come back to pyCharm later.

## Create a "visitor" that checks for new HPLC experiments on the server. <a name="task3"></a>
  **03/02/2022**:
   Mock directory containing some raw files that aren't compressed made to target wit ha visitor script. 
   
   "Visitors" are a python object that looks at folders and retrieves new, updated files according to some specifications. A visitor for the HPLC data would need to be made that  tracks changes in raw .lcra files during DELPHI's data ingestion.
  
## Deal with compressed .lcra raw HPLC files. <a name="task4"></a>
  **03/02/2022**:
  Some .lcra files exported from the machine undergo a compression to reduce the impact fo their size on the system. 
  
  Finding a way to read these compressed files is needed to    visualize the chromatograms contained in them. No immediate settings were found to prevent this behaviour on the machine, so the company was contacted.

[//]: # (Intermediate Evaluation Traineeship)

[//]: # (Self Assessment at the End of Traineeship)

[//]: # (Reflection on International/Intercultural Aspects)
