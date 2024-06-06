# Educational Toolkit to Navigate CESM1.0 Data

This repository contains three Jupyter notebooks focused on accessing, manipulating, and visualizaing mutliple climate variables within the Channel Islands National Marine Sanctuary (CINMS). This repository will allow for (novice) researchers and climate scientists to familiarize themselves with climate model data. The climate model data we are working with is CESM1.0. Feel free to reference the [NCAR](https://www2.cesm.ucar.edu/models/cesm1.0/). This repository is nested within the Channelislander organization created as a part of the Masters of Environmental Data Science within the Bren School of Environmental Science and Management at the University of California, Santa Barbara. 

In this repository, you'll notice three separate jupyter notebooks: 
- Mapping.ipynb
- Vertical_profile.ipynb
- Time_series.ipynb

A data folder containing all netCDF files produced from our toolkit and and environment.yaml file. 

## Structure

The structure of this repository is as follows:
```
toolkit
│  .DS_store
│  .gitignore
|  LICENSE
|  Mapping.ipynb
|  README.md
|  Time_series.ipynb
|  Vertical_profile.ipynb
|  environment.yml
|  toolkit.Rproj
└───data
      └─── cinms_py 
               |   cinms_py.dbf
               |   cinms_py.html
               |   cinms_py.kmz
               |   cinms_py.prj
               |   cinms_py.sbn
               |   cinms_py.sbx
               |   cinms_py.shp
               |   cinms_py.shp.xml
               |   cinms_py.shx
               |   cinms_py.xml
      └─── time_series
               |   20C_rcp85_o2.nc
               |   20C_rcp85_salt.nc
               |   20C_rcp85_sst.nc
               |   20C_rcp85_temp.nc
      └─── vertical_profile
               |   subset_TEMP_20C.nc
               |   subset_TEMP_RCP85.nc
      
```  

## About the Data 
Data is retrieved by using the Amazon Web Server Cloud. A subsetted dataset can be retrieved from the cloud following the steps listed in these notebooks. More information on this dataset can be found [here](https://ncar.github.io/cesm-lens-aws/)

Below are instructions for creating the environment necessary to run each of the toolkits: 

## Creating the environment

In order to work with this data, it is important to have the correct packages and dependencies in your environment to properly access the data. These are the steps we recommend you take to create the correct environment.

If the user is running through a server: 

1. Open up the terminal on the server.
*Note that the Channelislanders are using the Taylor server through Bren School.*
2. Run the following terminal commands: 

`conda create -n channelislanders python=3.9 anaconda` 

`conda activate channelislanders`

*Note: If you receive a message, such as "CommandNotFoundError: Your shell has not been properly configured to use conda activate", we recommend running the suggested command or just `conda init`. Once that has been done, please restart the whole session and continue the installation process by running the line below:*

`python -m ipykernel install --user --name=channelislanders`

Your output should say `Installed kernelspec channelislanders in ....` to correctly activate the kernal.

The name of the environment does not matter. For reference to the specific project, ‘channelislanders’ was used. The name is bolded in the instruction above. 

3. After confirming the correct environment, proceed with installing the following packages:

- `pip install xarray`
- `pip install intake`
- `pip install intake-esm`
- `pip install requests`
- `pip install aiohttp`
- `pip install s3fs`
- `pip install zarr`
- `pip install gcsfs`
- `pip install ipykernel`
- `pip install cfgrib`

4. Restart the session
5. Choose “channelislanders” as the kernel after you open the notebook
6. Run the toolkit. 

If the user is working locally: 

We recommend downloading [Anaconda](https://www.anaconda.com/download/) if you are working on a Windows computer. It is also optional to download this program if you are working on a MAC but should not be necessary. Once Anaconda has been downloaded, please be sure to open up the Anaconda Powershell Prompt app.

1. Open the terminal locally.
2. In the terminal window type:
   
`conda create -n cmip6 -c conda-forge dask distributed ipython netcdf4 xarray
intake-esm aiohttp`

This may take a few minutes depending on your computer. 
4. In the same terminal, type: 

`conda activate cmip6`

6. After this, open up the notebook on the platform of choice. These notebooks were created through JupyterLab on the Taylor server, and also utilized in VisualStudio code. 
If any of the packages are missing, an error message will appear to notify you which packages to download into the environment. 
There are multiple ways to download packages into the terminal, and the most common is 

`pip install package_name`

Another way to download packages into the environment is using the 

`conda search -c conda-forge package_name`

Conda search also searches for the package while conda-forge installs it. This same command can also be used in the terminal for the server if any other packages need to be installed.

At this point, you will have successfully created an environment and the user will run the code featured on these notebooks. 

In order to see the full list of the dependencies we used, please take a look at the [environment.yml](environment.yml) file. While we did not use all of these dependencies, most are necessary to have in order to properly retrieve the data from the AWS cloud.

Contributors

Project manager: Patricia Park

Communications manager: Olivia Holt

Data Manager/ Product Leader: Diana Navarro

Client/Faculty Advisor: Samantha Stevenson




