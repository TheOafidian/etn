# Electronic Traineeship Notebook (ETN)

## Table of Contents
1. [Traineeship Documentation Plan](#TDP)
2. [Background information traineeship topic](#background)
3. [Personal Development](#pers-dev)
4. [Tasks](#tasks)  
    4.1. [Exploration of raw data formats from HPLC instrument](#task1) ✔️  
    4.2. [Download and install DELPHI repository](#task2) ✔️  
    4.3. [Create a "visitor" for raw HPLC data and generate tsv file](#task3) 🔲  
    4.4. [Deal with compressed data HPLC files](#task4) 🔲  
    4.5. [Exploration raw UPLC data](#task5) ✔️  
    4.6. [Align on need for UPLC data upload format](#task6) 🔲  
    4.7. [Meta-Analysis UPLC data](#task7) 🔲   
    4.8. [Upload Ion Chromatography data](#task8) 🔲

[//]: # (Intermediate Evaluation Traineeship)

[//]: # (Self Assessment at the End of Traineeship)

[//]: # (Reflection on International/Intercultural Aspects)
# Traineeship Documentation Plan <a name="TDP"></a>

## Tentative Planning
- Look into DELPHI the Disqover data platform that serves as AelinTx's one stop shop for data on research & development activities. -> Current priority
- Find a way to decompress .lcra files. -> Halfway through the traineeship?
- Upload of UPLC data -> in a few weeks
- Upload external Ion Chromatography data -> prioritized

## Data Management
Data about the progress of the traineeship project will be stored according to the FAIR principles in this ETN.
- Findable
Different tasks are listed at the start of the ETN and linked to their respective headers within the ETN. Where possible a link to code written for the traineeship is supplied at the start of the task. 
- Accessible
The ETN is publicly available adn a link is shared with the project coordinators. The repository of the code is stored in a private git repository that requires authentication and only the project coordinators will be allowed access as some of the data stored is not meant to be publicized.
- Interoperable

- Reusable

## Traceability of Steps and Methods
This git repository markdown page will be used to document the project steps and changes in the project in a traceable manner.

## Version Control of Code

The code will be stored in [this private git repository](https://github.com/TVR-AelinTX/traineeship). 
Access will be given to the internal and external traineeship coordinators before the start of the traineeship. 
Links to scripts pertaining to tasks and subtasks of the traineeship will be provided in the ETN and can be accessed by the authorized coordinators.

# Background Information traineeship topic <a name="background"></a>

## HPLC
For the purification of the peptides manufactured in the lab, a method on a Reverse Phase High Performance Liquid Chromatography (RP-HPLC) system is used. The reverse phase points to the fact that a hydrophobic stationary phase is used, while the mobile phase initially is more hydrophilic in nature. The peptide is dissolved and injected with a constant flow of mobile phase into a column, the stationary phase. After several minutes the gradient of the mobile phase is shifted towards a more hydrophobic end. The peptide and its impurities bound to the column then each have their own 'sweet spot' of hydrophobicity where they will start prefering the mobile phase over the column and they will elute. This principle is used to separate the peptide of interest from any unwanted side-products from synthesis.

## UPLC

## DELPHI
The DELPHI platform is AelinTx's source for data and information related to ongoing research and development activities. It is a tool build upon the [DISQOVER](https://www.ontoforce.com/platform/disqover/) semantic search platform that enables researchers and managers to quickly find the data they need from the ELN stored. DELPHI's main strength is its flexibility to adapt to any data source, trough the use of python coding, without disrupting the data flow. Additionally some routines can be written to expedite data analysis.

[//]: # Personal Development <a name="pers-dev"></a>

# Tasks <a name="tasks"></a>
## Exploration of raw data formats from HPLC instrument <a name="task1"></a>
### 01/02/2022: 
First look at the data with exploratory [jupyter notebook](https://github.com/TVR-AelinTX/traineeship/blob/main/data_exploration/HPLC/HPLC%20Data.ipynb)

### 08/02/2022: 
Fixing further issues with the parsing of the .lcra files. Script should be simplified, but entanglement of different samples in one file and no clear way to link them makes this difficult...
### 10/02/2022: 
Extracting raw data using pandas.read_xml to get a clearer dataframe to start with. 
A setting in the package needs to be adapted however to allow handling files of this size.

## Download and install Delphi repository <a name="task2"></a>
### 01/02/2022: 
Download repo and installing dependencies.

Install, explore and use Pycharm. Issues using WSL interpreter (only supported in professional version). 
Continued using VS Code for now, perhaps come back to pyCharm later.

### 08/02/2022:
Facing issues testing out the visitor script using VSCode. Tried switching to PyCharm again, using WSL graphic interface. Ran into issues due to not being able to contact graphic server (firewall issues?). 
### 10/02/2022:
Sat together with external coordinator and fixed the issue. 

## Create a "visitor" that checks for new HPLC experiments on the server. <a name="task3"></a>

Link to copy of script that has been encapsulated in the DELPHI structure: [hplc_visitor.py](https://github.com/TVR-AelinTX/traineeship/blob/main/hplc/hplc_visitor.py)

### 03/02/2022:
Mock directory containing some raw files that aren't compressed made to target with a visitor script. 

"Visitors" are a python object that looks at folders and retrieves new, updated files according to some specifications. A visitor for the HPLC data would need to be made that  tracks changes in raw .lcra files during DELPHI's data ingestion.

### 08/02/2022:
Incorporated methods distilled from the data exploration into the visitor script. Needs more work refining and restructuring. Issues testing code on local computer.

### 10/02/2022:
Fixed issues testing visitor script on local computer. Issue not clearly defined, but seems to be related to naming conventions of folders (to keep in mind!). 

Script was appended with new methods and debugged to a workable state. More finetuning needed by adding a lookup file before execution of the script. The script now generates plots for all the peptides in a .lcra file. It uses a standard gradient (can be improved by selecting the right gradient) for now as most often the HPLC runs use the same gradient and identifying the gradient with the run proves not to be straightforward, as gradients of preparatory and finishing gradients are also recorded. The plots look good on most runs, altough some seem to be missing fractions (to be investigated). The plots could also be prettified further.

## Deal with compressed .lcra raw HPLC files. <a name="task4"></a>
### 03/02/2022:
Some .lcra files exported from the machine undergo a compression to reduce the impact fo their size on the system. 

Finding a way to read these compressed files is needed to    visualize the chromatograms contained in them. No immediate settings were found to prevent this behaviour on the machine, so the company was contacted.

Some settings in the data acquisition could help generate reports with the needed data. This should first be investigated, alternatively the data is compressed on sql level and the company providing the sql database could be contacted by the supplier of the instrument for further help.

### 08/02/2022:
Asked to contact the company providing the sql database interaction from the software.

## Exploration raw UPLC Data. <a name="task5"></a>
### 08/02/2022:
Handling the UPLC raw data is much more straightforward. It can be exported in two .txt files per QC run performed. One file contains raw measurements to recreate the chromatogram, the other the area under the curve (AUC) per retention time calculated by the software of the UPLC.

### 15/02/2022:
UPLC data was explored. The software can spit out .txt files of the raw data and integration results. Parsing of both files and retrieving the interesting data with python is quite effective.

## Align on need for UPLC data upload format. <a name="task6"></a>
### 10/02/2022:
The possibility of uploading the UPLC data was discussed and the QC representative showed an interest, but wanted to first set in place more methods (Ion Chromatography) to analyze the peptides, which could be added to the reporting.

### 15/02/2022:
The need for upload of externally acquired Ion Chromatography data was adressed in a meeting. After sitting together with the external project coordinator, it was decided to work on this first. This is achieved by utilizing upload schemes of the DELPHI platform (xlsx files defining fields of pandas dataframes, templates, etc) and some internal logic.

## Meta Analysis UPLC data. <a name="task7"></a>
### 15/02/2022:
For two different methods the absorbance is measured at wavelengths 210nm and 216nm respectively. It would be easy to unionize this reading by only looking at one of both wavelengths. Therefore an analysis of previous UPLC runs needs to be made to show that the resulting purity(%) values between the two different wavelength measurements does not differ significantly.

A bash script was written to pick up and put together the files from a list of exported files. A python script is written that extracts retention time, sample name and detector wavelength. Next step is to compare both groups statistically.

### 17/02/2022:
A first exploratory visual analysis of the data reveals some differences between both readings for some samples. The distribution of the differences was tested for normalcy and the null hypothesis that the distribution was normal was rejected at a significance of 0.05.

## Upload Ion Chromatography data to DELPHI platform <a name="task8"></a>
### 15/02/2022:
A basic scheme for uploading data on the resulting ion percentages from ion chromatography experiments is made to allow upload onto the DELPHI platform. Upload schemes consist of excel sheets defining input and output fields for the data that is read from an excel template. These schemes are used by the internal logic of DELPHI in the form of python script to pre-process, ingest and display the data on the web platform.

Some basic logic is added to the script to preprocess the data.

## 17/02/2022:
The scheme is updated with fields for the date of upload, the person uploading the data and the location of the data to ensure traceability.

The internal logics are also polished with some data validation and cleanup to allow a more robust pre-processing. Ideas for future improvements: classification by main ion, comparison of salt_state vs experimental_salt_state.


[//]: # (Intermediate Evaluation Traineeship)

[//]: # (Self Assessment at the End of Traineeship)

[//]: # (Reflection on International/Intercultural Aspects)
