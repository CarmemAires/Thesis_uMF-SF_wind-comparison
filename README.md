# A Comparison of Wind Velocity Predictions from Wind-Only and Thermally Coupled OpenFOAM Solvers in Urban Models with Complex Terrain

**Author:** Carmem Aires (MSc Geomatics - 3D Geoinformation Group — TU Delft)

This repository belongs to the master thesis "Comparison of Wind Velocity Predictions from Wind-Only and Thermally Coupled OpenFOAM Solvers in Urban Models with Complex Terrain" presented at the 3D Geoinformation Group, Delft University of Technology,Faculty of Architecture and the Built Environment.

## Repository Structure

This repository contains two case directories:

```
repository/
    ├── case_directories/
    |    ├── case_sF/    # simpleFoam case setup
    |    └── case_uMF/   # urbanMicroclimateFoam case setup
    └── model-reconstruction/
```
## Links

- [**TU Delft repository**]()
- [**Input data (4TU repository)**]()
  
## Requirements

To run the cases you will need (the cases were tested in these software versions):

- [OpenFOAM v7](https://openfoam.org/)
- [urbanMicroclimateFoam](https://github.com/OpenFOAM-BuildingPhysics/urbanMicroclimateFoam)
- [City4CFD](https://github.com/tudelft3d/city4cfd)


## Running a Case

**1. Add input data**

Download the geometry from [here](https://1drv.ms/f/c/b551ab2d27b6f2d9/IgARaZF3YqMaTZsbFhmNdffJAfG19q6ZlZbRdN08rSi7bWE?e=fYLDd9) and add it the respective triSurface directory
```
casedir/
├── 0/   
└── constant/  
    └── triSurface/   <- add the geometry here
```

**2. Prepare the case:**

```bash
./Allprepare
```

**3. Run the case:**

```bash
./Allrun
```

## Additional Utilities (urbanMicroclimateFoam)

The following utilities are included for use with `urbanMicroclimateFoam`:

 `DecomposeNewFields`
Redistributes field files to a decomposed case after changes in the fields.

 `ExportMeshProblems`
Exports mesh errors to VTK format.

 `FaceagglRerun`
Removes files created by a previous `faceAgglomerate` run, redistributes the new `viewFactorsDict`, and reruns `faceAgglomerate`. Useful when `faceAgglomerate` or `viewFactorsGen` crashes.


## Model Reconstruction 

The `model-reconstruction/` folder contains the configuration file used to reconstruct the model using [City4CFD](https://github.com/tudelft3d/city4cfd).

### Input Data

Before running, download the required data from [4TU]() and place it in the following structure:

```
model-reconstruction/
├── polygons/    # Building and Vegetation footprints
└── PC/          # Point clouds
```


