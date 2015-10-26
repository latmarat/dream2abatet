## dream2abatet
MATLAB script to write ABAQUS tetrahedral mesh from Dream.3D surface mesh

The script

- Reads nodes, triangles of surface mesh and feature centroids generated in [Dream.3D](http://dream3d.bluequartz.net/) (ver. 4.2.x)
- Generates volume tetrahedral mesh using [iso2mesh](http://iso2mesh.sf.net) toolbox
- Writes the generated mesh into a file in ABAQUS input file format

![Surface to volume](https://farm1.staticflickr.com/678/22464316136_3b726c739e_o_d.png)
![ABAQUS mesh](https://farm6.staticflickr.com/5768/22476919562_704bd12470_o_d.png)

## Usage

1. Download [iso2mesh](http://iso2mesh.sf.net) toolbox and add it to MATLAB path
2. [Download `dream2abatet.m`](https://github.com/latmarat/dream2abatet/archive/master.zip) script and put it to a MATLAB folder
3. Run Dream.3D pipeline to write nodes, triangles, features files
4. Run `dream2abatet.m` script pointing to the three Dream.3D files

## Example

This repository contains example files:

- ex_nodes.in
- ex_tri.in
- ex_features.in

You can use them to generate your first mesh:

1. Download the repo, extract the files to a MATLAB folder.
2. Run
```
dream2abatet('ex_nodes.in','ex_tri.in','ex_features.csv',0.75,0.5,true)
```

in MATLAB and you should get a file dream.inp containing your mesh. Check it in ABAQUS/CAE setting coloring according to Sets. It should look like the image above.

The repository also contains an example Dream.3D (ver. 4.2.5) pipeline - `ex_pipe.txt`, which writes the `ex_nodes.in`, `ex_tri.in`, `ex_features.csv` files for a 32x32x32 single-phase microstructure grid .

## Known issues

1. The script requires grain centroids. The only option to export centroids in Dream.3D ver. 4.2.x seems to be Write Goal Attributes in _Pack Primary Phases_ filter. Since the generated microstructure does not necessarily match the goal attributes exactly, some grains may be missing in ABAQUS sets.
2. Generation of volume mesh may fail for some microstructures (Invalid PLC error). In such cases, rerun Dream.3D pipeline and try again or try different Dream.3D settings.
3. No information on phases will be passed to ABAQUS in the current version of the script.

## Acknowledgment

`dream2abatet.m` heavily relies on [iso2mesh](http://iso2mesh.sf.net) toolbox - an image-based 3D surface and volumetric mesh generator.

- **Author**: Qianqian Fang, Massachusetts General Hospital (Harvard Medical School)
- **License**: GPL v.2 or later
- **URL**: [iso2mesh.sf.net](http://iso2mesh.sf.net)
