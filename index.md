# Electronic Traineeship Notebook (ETN)

## Table of Contents
1. [Traineeship Documentation Plan](#TDP)   
    1.1. [Tentative Planning](#TDP1)    
    1.2. [Data Management](#TDP2)   
    1.3. [Traceability of Steps and Methods](#TDP3)  
    1.4. [Version Control of Code](#TDP4)   
2. [Background information traineeship topic](#background)  
3. [Reflection and self-directed behaviour](#refl)  
    3.1 [Personal Development](#pers-dev)   
4. [Tasks](#tasks)  
    4.1. [✔️ Exploration of raw data formats from HPLC instrument](#task1)   
    4.2. [✔️ Download and install DELPHI repository](#task2)     
    4.3. [❌Create a "visitor" for raw HPLC data and generate tsv file](#task3)   
    4.4. [❌ Deal with compressed data HPLC files](#task4)   
    4.5. [✔️ Exploration raw UPLC data](#task5)   
    4.6. [✔️ Align on need for UPLC data upload format](#task6)   
    4.7. [🔲 Meta-Analysis UPLC data](#task7)    
    4.8. [✔️ Upload Ion Chromatography data](#task8)     
    4.9. [✔️ Generate PDFs from UPLC data](#task9)       
    4.10. [🔲 Add inhouse IC data to pdf generation](#task10)       
    4.11. [✔️ Establish IC data as new cannonical type on DELPHI](#task11)      

[//]: # (Intermediate Evaluation Traineeship)

[//]: # (Self Assessment at the End of Traineeship)

[//]: # (Reflection on International/Intercultural Aspects)
# Traineeship Documentation Plan <a name="TDP"></a>

## Tentative Planning <a name="TDP1"></a>
- Look into DELPHI the Disqover data platform that serves as AelinTx's one stop shop for data on research & development activities. -> Continuous
- Upload external Ion Chromatography data -> finished 26/02
- Build further robustness and pre-analysis IC data -> Finished 21/03
- HPLC vistor script -> Stopped
- Upload of UPLC data -> Finished 21/03
- Find a way to decompress .lcra files. -> Stopped
- Increase robustness PDF generation -> Current Priority
- Appending IC data to PDF generation -> Second priority; aim to finish in middle April


## Data Management <a name="TDP2"></a>
Data about the progress of the traineeship project will be stored according to the FAIR principles in this ETN.

**Findable**

Different tasks are listed at the start of the ETN and linked to their respective headers within the ETN.  

**Accessible**

The ETN is publicly available and a link is shared with the project coordinators. The repository of the code is stored in a private git repository that requires authentication and only the project coordinators will be allowed access as some of the data stored is not meant to be publicized.

**Interoperable**

Where possible a link to code written for the traineeship is supplied at the start of the task.

**Reusable**

The code repository is private, as the data used is confidential in nature. Descriptions in the ETN do not include any confidential data such as Pept-In:tm: codes or sequences, or any other identifiers that could allude to this data and it is therefore licensed under MIT.

## Traceability of Steps and Methods <a name="TDP3"></a>
This git repository markdown page will be used to document the project steps and changes in the project in a traceable manner.

## Version Control of Code <a name="TDP4"></a>

The code will be stored in [this private git repository](https://github.com/TVR-AelinTX/traineeship). 
Access will be given to the internal and external traineeship coordinators before the start of the traineeship. 
Links to scripts pertaining to tasks and subtasks of the traineeship will be provided in the ETN and can be accessed by the authorized coordinators.

# Background Information traineeship topic <a name="background"></a>

## HPLC
For the purification of the peptides manufactured in the lab, a method on a Reverse Phase High Performance Liquid Chromatography (RP-HPLC) system is used. The reverse phase points to the fact that a hydrophobic stationary phase is used, while the mobile phase initially is more hydrophilic in nature. The peptide is dissolved and injected with a constant flow of mobile phase into a column, the stationary phase. After several minutes the gradient of the mobile phase is shifted towards a more hydrophobic end. The peptide and its impurities bound to the column then each have their own 'sweet spot' of hydrophobicity where they will start prefering the mobile phase over the column and they will elute. This principle is used to separate the peptide of interest from any unwanted side-products from synthesis.

## UPLC
To analyze the purity of the peptides, an Ultra High Performance Liquid Chromatography (UPLC) system is used. It's concepts and inner workings are essentially the same as that of the HPLC, save for the higher pressure used in this system and the denser column material. This makes for a more efficient separation of analytes, but a higher retention time. This makes the system ideal for analytical purpose, while the HPLC is used for preparative purposes.

## Ion Chromatography
Another main source of variability between different peptide batches are the ion contents. Three ion types are analyzed in the lab (TFA, acetate and chloride) as these three are routinely used as counterions for the peptides. The software and principle are similar to the UPLC, except that the column now binds and separates ions with the use of positively charged beads that slow elution of the negative ions. 


## DELPHI
The DELPHI platform is AelinTx's source for data and information related to ongoing research and development activities. It is a tool build upon the [DISQOVER](https://www.ontoforce.com/platform/disqover/) semantic search platform that enables researchers and managers to quickly find the data they need from the ELN stored. DELPHI's main strength is its flexibility to adapt to any data source, trough the use of python coding, without disrupting the data flow. Additionally some routines can be written to expedite data analysis.

# Reflection and self-directed behaviour <a name="refl"></a>

## Personal Development <a name="pers-dev"></a>
**Concept of learning outcome**

Over the course of the traineeship, I will gain the skills and experience needed to familiarize myself with the DELPHI ELN-platform to help it grow by adding pre-processing, data uploading and curating subroutines to the pipeline. This will support my colleagues with their data management and allow for more reproducible experiments.

**Development activities**

- Python scripting: pandas, file IO
- Teamwork and communication: meetings with stakeholders, git
- Data visualization: R and Python, dashboards in DELPHI

**Desired results**

- Automatically generate a pdf summarizing some of the QC results of the lab in a clean and orderly manner.
- Process .txt, .xml files to extract the relevant information and upload it in a structured, curated manner
- Clearly communicate expectations, possibilities and changes related to projects to stakeholders and work together to achieve the best solution.

**Schedule**

The different activities run in parallel as they're heavily intertwined and give feedback to one another.

**Nescessary support and facilities**

Feedback is given when needed or whenever I feel stuck with a certain problem by the external coordinator. The course units of BIT provide support in handling issues (eg: Databases & Data Management, Python Scripting, Data Visualization).

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

### 22/02/2022:
Using pandas to read the data from the xml-like files is memory intensive and requires changing some lines of code in the pandas library. Therefore a re-write of the code to use a personalized handler that only extracts the needed data from the xml file in one go is initiated.

### 24/02/2022:
Finalizing the reader. Started linking the data to the Chromatogram class, which needs a rework to ift with the new structure.

### 01/03/2022: 
Work on the HPLC data was shelved in favor for looking at the UPLC data.

## Deal with compressed .lcra raw HPLC files. <a name="task4"></a>
### 03/02/2022:
Some .lcra files exported from the machine undergo a compression to reduce the impact fo their size on the system. 

Finding a way to read these compressed files is needed to    visualize the chromatograms contained in them. No immediate settings were found to prevent this behaviour on the machine, so the company was contacted.

Some settings in the data acquisition could help generate reports with the needed data. This should first be investigated, alternatively the data is compressed on sql level and the company providing the sql database could be contacted by the supplier of the instrument for further help.

### 08/02/2022:
Asked to contact the company providing the sql database interaction from the software.

### 24/02/2022:
Response from the supplier. There is a special module for sale that could extract the data in a non encrypted format. Discussion for the need of this investment is needed.

### 01/03/2022:
It was decided not to purchase the module after further discussion. The work on the HPLC data was put on hold, as the fraction of uncompressed data is minimal compared to that of the compressed data. 

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

### 10/03/2022:
A script was written to automate the transfer of UPLC exported data on the lab instruments in a specified folder to the server. During transfer a "_uplc" tag is provided to the text files as metadata to distinguish the files from raw ic data in the future. 

## Meta Analysis UPLC data. <a name="task7"></a>
### 15/02/2022:
For two different methods the absorbance is measured at wavelengths 210nm and 216nm respectively. It would be easy to unionize this reading by only looking at one of both wavelengths. Therefore an analysis of previous UPLC runs needs to be made to show that the resulting purity(%) values between the two different wavelength measurements does not differ significantly.

A bash script was written to pick up and put together the files from a list of exported files. A python script is written that extracts retention time, sample name and detector wavelength. Next step is to compare both groups statistically.

### 17/02/2022:
A first exploratory visual analysis of the data reveals some differences between both readings for some samples. The distribution of the differences was tested for normalcy and the null hypothesis that the distribution was normal was rejected at a significance of 0.05.

### 22/02/2022:
A second set of same sample readings was analyzed. Here the differences between both reading are normally distributed. A student t-test confirms that the difference between both datasets of the same sample is significant. Purities calculated by both methods for different samples show no significant difference accoring to a Wilcoxon's signed rank test.  

## Upload Ion Chromatography data to DELPHI platform <a name="task8"></a>

Link to copy of script that has been encapsulated in the DELPHI structure: [import_dlph_compounds_batches](https://github.com/TVR-AelinTX/traineeship/blob/main/ion_chrom/import_dlph_compounds_batches.py)

### 15/02/2022:
A basic scheme for uploading data on the resulting ion percentages from ion chromatography experiments is made to allow upload onto the DELPHI platform. Upload schemes consist of excel sheets defining input and output fields for the data that is read from an excel template. These schemes are used by the internal logic of DELPHI in the form of python script to pre-process, ingest and display the data on the web platform.

Some basic logic is added to the script to preprocess the data.

### 17/02/2022:
The scheme is updated with fields for the date of upload, the person uploading the data and the location of the data to ensure traceability.

The internal logics are also polished with some data validation and cleanup to allow a more robust pre-processing. Ideas for future improvements: classification by main ion, comparison of salt_state vs experimental_salt_state.

### 22/02/2022:
Testing the code on the production server led to errors involving the merging of the IC data to the batch data. The code was rewritten in a more memory efficient way and the joining of the dataframes was adapted to not produce any errors.

### 24/02/2022:
The code was tested on the production server and yielded no errors. The change was communicated to the rest of the team and data upload was initiated.

### 10/03/2022:
The presentation of the results was embellished trough the use of html and css and a python script that dynamically allocates colors based on fractions of values. 

### 15/03/2022:
The formatting was further optimized and the three divs whee joined in a container div with flexbox properties to account for different viewports. Replacing three fields to the data ingestion dataframe by one field of the combined results.


## Generate PDFs UPLC data <a name="task9"></a>
### 01/03/2022:
An automated method to generate certificates of analysis from the data obtained by UPLC would be a useful implementation for the company. 

The backbones for the script are tested out and written in [this jupyter notebook](https://github.com/TVR-AelinTX/traineeship/blob/main/data_exploration/UPLC/UPLC%20DATA%20exploration.ipynb). The means to extract the raw data from .txt files are written and a first small pdf was generated.

### 03/03/2022:
A more thorough pdf generation backbone script was made using reportlab. It takes variables from the delphi tables to supplement the raw data with other compound and batch related properties.

### 07/03/2022:
Incorporation of pieces of the code into DELPHI started. The process is as follows: a visitor script will scrape the ELN for new raw UPLC data (posted in a monthly folder) and retrieve relevant data needed for the report. It will also generate a chromatogram and save it to the server to be displayed on DELPHI and included in the report.

After this, an operation will join tables from batches, compounds and the uplc data to get all the relevant data for the report. This data is then fed to a function that generates the report. The function is wrapped by a method that keeps track of any changes and only runs the code when there are changes. 

### 10/03/2022:
The pdf generation was further polished and formatting was adapted to ammeliorate more extreme input data (eg. large integration tables).

### 15/03/2022:
The method for finding the UPLC data was improved to allow for nested directories. An error showed up and was traced to differences in regionality between used computers (lab vs DELPHI server). A date was printed in "%d.%b.%Y" format in German on the lab instrument, which was not recognized by the script on the server. The script was appended with the dateparser library to translate this format.

### 17/03/2022:
A button was styled in html and css to allow viewing the pdf from the batches dashboard. The code was tested on the sandbox server and a few bugs were fixed after testing. 

### 21/03/2022:
Some of the images urls did not allow for viewing the UPLC chromatograms. This was due to a '#' in the filename which causes the url not to function properly. The '#'s were replaced by 'n's in the script before url generation to allow the chromatograms to be displayed. The way of merging the UPLC data with the batch data in pandas was also adapted to prevent duplication of batches.

### 24/03/2022:
The code was wrapped in some error handling to report different parts of the code where things could go awry.

## Add inhouse IC data to pdf generation <a name="task10"></a>

### 21/03/2022:
The Ion Chromatography data was explored initially. The program used to process and export the IC data, Chromeleon, is the same as for the UPLC. This way a similar workflow could be set up to get the data exported to the server and read in by Delphi.

Some settings needed to be changed on the Chromeleon software to allow a one-click export by the user. Structure of the saved runs was also copied to that of the UPLC data, for inner consistency.

### 24/03/2022:
A bash script was written to transfer the data exported to the backport in the server to a permanent place in the server. During transfer an '_ic' metatag is added to the filenames.

Further preprocessing of the IC data was worked on in a jupyter notebook.

### 29/03/2022:

The script for handling the IC data was incorporated into DELPHI and tested on the sandbox.

### 07/04/2022:

Incorporation of the IC data into the generated PDFs. Formatting of the figures and pdf.

## Establish IC data as new cannonical type on DELPHI <a name="task11"></a>

### 29/03/2022:

It was decided to make the IC data their own category of data on DELPHI, to accomodate comparison of different measurements (on different dates, different technical replicates or from different sources). Code was refactored to create this new cannonical type and add the IC data to it.

## 31/03/2022:

The code was refactored further and the data was linked to batches and vice versa. Changes were tested on sandbox and further polishing of the code was done.

## 05/04/2022:

The dashboard on the sandbox server was adapted to properly display the IC data in its new cannonical type (front end).  

[//]: # (Intermediate Evaluation Traineeship)

[//]: # (Self Assessment at the End of Traineeship)

[//]: # (Reflection on International/Intercultural Aspects)

<script src="https://unpkg.com/vanilla-back-to-top@7.2.1/dist/vanilla-back-to-top.min.js"></script>
<script>addBackToTop({
  diameter: 56,
  backgroundColor: 'rgb(0,128,128)',
  textColor: '#fff'
})</script>
