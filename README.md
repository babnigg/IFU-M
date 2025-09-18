# Integral Field Unit Workflow


### Installation

Install the parsl branch of the repository.
```
git clone --single-branch --branch parsl https://github.com/babnigg/IFU-M.git
```

Create a conda enviornment to run the pipeline. This will also include the installation of the ifum package, which has all necessary dependancies.
```
conda create --name <my-env>
conda activate <my-env>
```

```
cd ifum_pkg
python3 -m pip install .
```

---

### Usage

Modify the appropriate variables in run.py to ensure your data specifications are run for the workflow. This includes the variables:
```
directory, data_filenames, arc_filenames, flat_filenames, mode, wavelength, bad_blues, bad_reds, bin_to_2x1, sig_mult, wcs_stars
```

Next, use the appropriate configuration for Parsl. You can define your configuration in *config.py*, and use it in *run.py* to define **config**. Local and cluster examples are provided.  
See https://parsl.readthedocs.io/en/stable/userguide/configuration/index.html for more information.

Now, the pipeline can be run with the Python script. Either use *run.py* in the base directory, or use a slurm script. An example for running on UChicago's Midway is shown in *submission.sh*.

---

Example raw observation data can be provided through request, reach out to babnigg@uchicago.edu for questions and requests!