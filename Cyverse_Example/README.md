# Instructions for Running LANDIS-II VICE app on Cyverse 

This folder contains an example scenario folder titled, 'SingleCell', which includes input files for running a single cell LANDIS-II simulation using the DGS succession extension. <br> 

*NOTE:* The specific input parameters in this scenario are for demonstration purposes only and do not necessarily reflect parameters used in any published simulations. <br> 

## To run this example, follow these steps: 

1. Upload SingleCell folder into the Data Store of the Cyverse Discovery Environment.

2. Navigate to the CloudShell LANDIS-II app within the Cyverse Discovery Environment and open.

3. Proceed through the steps outlined in the app   
    * *Analysis Info:* If desired, name analysis and specify output folder (not necessary to run this example)
    * *Parameters:* Define Input Folder parameter as the path to the SingleCell folder in the Data Store <br> e.g., /iplant/home/[username]/Inputs/SingleCell <br>*NOTE: This step is not required to run the app, but will result in the correct file structure to run this example)*
    * *Advanced Settings (optional):* Here, if desired, specify CPU cores and memory options 
    * *Review and launch:* Review parameters for accuracy, then Launch Analysis
5. Navigate to analysis session (click 'Go to Analysis button on analysis page)
6. Run LANDIS-II
    * Within the analysis, copy the SingleCell input folder from inputs folder into a new folder:
      <br>``` cp -rf data/input/SingleCell/ . ```
    * Navigate into SingleCell folder:
      <br>``` cd SingelCell ```
    * Initiate LANDIS-II (dotnet command pointing to Landis.Console.dll, followed by the name of the scenario text file):
      <br>``` dotnet /opt/Core-Model-v7-LINUX-7/build/Release/Landis.Console.dll scenario_DGS_SC.txt ```
    * *When message* `Attach process to Visual Studio for debugging and hit return` *appears, hit return/enter key and run will continue*    

7. Once run has completed, SingleCell folder (or any specific files generated from the run) can be zipped and copied back into Data Store.
    ```
    cd ..
    Zip -r SingleCell.zip SingleCell
    cp -r SingleCell.zip [desired directory within Data Store]
    ```

## Screenshot of example session initiating LANDIS-II (DGS extension): 
![alt text](https://github.com/TEEL-Lab/LANDIS-II-Container-VICE/blob/main/Cyverse_Example/InitiatingLANDISII_withinCyverse.png)
