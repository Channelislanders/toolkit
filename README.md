# Toolkit on Channel Island variable observations

This repository will be housing three notebooks that include information on:
- Mapping various climate variables within different experiments 
- Creating a time series that will display trends by each climate variable according to each experiment
- Creating a vertical profile that displays the change in depth by each variable according to each experiment

## Creating the environment

In order to work with this data, it is important to have the correct packages and dependencies in your environment to properly access the data. These are the steps we recommend you take to create the correct environment.

If the user is running through a server: 

1. Open up the terminal on the server.
*Note that the Channelislanders are using the Taylor server through Bren School.*
2. Run the following terminal commands: 

`conda create -n channelislanders python=3.9 anaconda` 

`conda activate channelislanders`

*Note: If you receive a message, such as "CommandNotFoundError: Your shell has not been properly configured to use 'conda activate'.", we recommend running the suggested command or just `conda init`. Once that has been done, please restart the whole session and continue the installation process by running the line below:*

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

## Note on Data Access
Data is retrieved by using the Amazon Web Server Cloud. A subsetted dataset can be retrieved from the cloud following the steps listed in these notebooks. More information on this dataset can be found [here](https://ncar.github.io/cesm-lens-aws/)
