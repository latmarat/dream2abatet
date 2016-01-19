## dream2abatet

MATLAB script to write ABAQUS tetrahedral (C3D4) mesh from Dream.3D surface mesh

The script

- Reads nodes, triangles of surface mesh and feature centroids generated in [Dream.3D](http://dream3d.bluequartz.net/) (ver. 4.2.x)
- Generates volume tetrahedral mesh using [iso2mesh](http://iso2mesh.sf.net) toolbox
- Writes the generated mesh into a file in ABAQUS input file format

Read more about the script [here](http://latmarat.net/blog/scripts/dream2abatet)

![Surface to volume](https://farm1.staticflickr.com/678/22464316136_3b726c739e_o_d.png)
![ABAQUS mesh](https://farm6.staticflickr.com/5768/22476919562_704bd12470_o_d.png)

## Acknowledgment

`dream2abatet.m` heavily relies on [iso2mesh](http://iso2mesh.sf.net) toolbox - an image-based 3D surface and volumetric mesh generator.

- **Author**: Qianqian Fang, Massachusetts General Hospital (Harvard Medical School)
- **License**: GPL v.2 or later
- **URL**: [iso2mesh.sf.net](http://iso2mesh.sf.net)
