---
tags:
  - Free
---

# Zonation

[Zonation](https://zonationteam.github.io/Zonation5/) is a spatial conservation prioritization framework for large-scale conservation planning. It identifies areas, or landscapes, important for retaining high habitat quality and connectivity for multiple biodiversity features (eg. species), providing a quantitative method for enhancing species' long term persistence.


## Available

__Zonation__ is available in Puhti with following versions:

* 5.1.0 (including Graphical User Interface)


## Usage

Zonation is available in the __zonation__ module and the command line interface can be loaded with

`module load zonation`

After loading the Zonation module you can run zonation commands in the following way:

```
z5 <command arguments>
```

Alternatively, if you want to use the Zonation Graphical User Interface (GUI) tool, Zonation can be started in Puhti web interface :

1. Log in to [Puhti web interface](https://puhti.csc.fi).
2. Open [Desktop app](../computing/webinterface/desktop.md). 
3. After launching the Desktop, double-click Zonation icon.

### Example

Here is an example with the Zonation tutorial data.


    
#### Zonation 5

Download the [zonation5-tutorial data](https://github.com/zonationteam/Zonation5/releases/download/v1.0/manual_and_example_setups.zip) to your project's __projappl__ or __scratch__ folder, unzip it; then

```
cd /scratch/<your_project>/manual_and_example_setups/example\ setups\ and\ data/1_w
srun --ntasks=1 --time=00:15:00 --mem=1G --account=project_<your_project_number> --partition=test --pty z5 -w --mode=ABF minimal_settings.z5 $HOME/example1_out
```
which will show you the process in the terminal and create the example1_out file in your $HOME folder.

**Example batch job script**

```
#!/bin/bash
#SBATCH --account=<YOUR-PROJECT>
#SBATCH --cpus-per-task=1
#SBATCH --partition=test
#SBATCH --time=00:15:00
#SBATCH --mem=1G

module load zonation
cd /scratch/<your_project>/manual_and_example_setups/example\ setups\ and\ data/1_w
srun z5 -w --mode=ABF minimal_settings.z5 <path_to_where_you_want_to_store_the_result>/example1_out
```

## License 

Zonation 5 is distributed as is, freely under [GNU General Public License (GPL) version 3 (#GNUGPL) (#GNUGPLv3) license.](https://www.gnu.org/licenses/gpl-3.0.html)


## Citation

`Moilanen, A., Lehtinen, P., Kohonen, I., Virtanen, E., Jalkanen, J. and Kujala, H. 2022. Novel methods for spatial prioritization with applications in conservation, land use planning and ecological impact avoidance. Methods in Ecology and Evolution`


## Acknowledgement

Please acknowledge CSC and Geoportti in your publications, it is important for project continuation and funding reports.
As an example, you can write "The authors wish to thank CSC - IT Center for Science, Finland (urn:nbn:fi:research-infras-2016072531) and the Open Geospatial Information Infrastructure for Research (Geoportti, urn:nbn:fi:research-infras-2016072513) for computational resources and support".


## Installation

Zonation was installed to Puhti with Apptainer using [Zonation Apptainer definition file written by Pauli Lehtinen from University of Helsinki](https://raw.githubusercontent.com/CSCfi/singularity-recipes/main/zonation/zonation5.def). 

The container was finally wrapped with [Tykky's wrap-container functionality](../computing/containers/tykky.md#container-based-installations): `wrap-container -w /squashfs-root/usr/bin/z5 --prefix install_dir z5.sif`


## References

* [Zonation homepage](https://zonationteam.github.io/Zonation5/)
* [Zonation Github](https://github.com/zonationteam/Zonation5)
* [Zonation 5 manual and tutorial data](https://github.com/zonationteam/Zonation5/releases/download/v1.0/manual_and_example_setups.zip)




