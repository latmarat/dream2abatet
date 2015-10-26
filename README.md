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

## Known issues

1. The script requires grain centroids. The only option to export centroids in Dream.3D ver. 4.2.x seems to be Write Goal Attributes in _Pack Primary Phases_ filter. Since the generated microstructure does not necessarily match the goal attributes exactly, some grains may be missing in ABAQUS sets.
2. Generation of volume mesh may fail for some microstructures (Invalid PLC error). In such cases, rerun Dream.3D pipeline and try again or try different Dream.3D settings.

## Acknowledgment

dream2abatet heavily relies on [iso2mesh](http://iso2mesh.sf.net) toolbox - an image-based 3D surface and volumetric mesh generator.

- **Author**: Qianqian Fang, Massachusetts General Hospital (Harvard Medical School)
- **License**: GPL v.2 or later
- **URL**: [iso2mesh.sf.net](http://iso2mesh.sf.net)
