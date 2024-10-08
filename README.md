# [vsi2tif](https://github.com/andreped/vsi2tif#vsi2tif)

[![CI](https://github.com/andreped/vsi2tif/workflows/Build%20Package/badge.svg)](https://github.com/andreped/vsi2tif/actions)
[![CI](https://github.com/andreped/vsi2tif/workflows/Check%20Linting/badge.svg)](https://github.com/andreped/vsi2tif/actions)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Tool for converting WSIs from Olympus' cellSens VSI to Generic TIFF.

A simple Jupyter Notebook can be seen [here](https://github.com/andreped/vsi2tif/blob/main/notebooks/conversion_tutorial.ipynb) demonstrating how use the tool.

## [Requirements](https://github.com/andreped/vsi2tif#requirements)

To run the tool, you need to configure bftools and vips. To do that, follow the instructions below for the operating system of interest:

<details>
<summary>

### [Ubuntu](https://github.com/andreped/vsi2tif#ubuntu)</summary>

1. Download bftools (click [here](http://downloads.openmicroscopy.org/latest/bio-formats5.6/artifacts/bftools.zip))

2. Install vips and JDK
```
sudo apt update
sudo apt-get install openjdk-8-jdk
sudo apt install libvips-tools
```

</details>


<details>
<summary>

### [macOS](https://github.com/andreped/vsi2tif#macos)</summary>

1. Download bftools (click [here](http://downloads.openmicroscopy.org/latest/bio-formats5.6/artifacts/bftools.zip))

2. Install vips and JDK
```
brew install --cask zulu@8
brew install vips
```

</details>


## [Installation](https://github.com/andreped/vsi2tif#installation)

Install from source:
```
pip install git+https://github.com/andreped/vsi2tif
```

## [Usage](https://github.com/andreped/vsi2tif#usage)

The conversion tool is available through a command line interface (CLI).

Example for converting a single WSI:
```
vsi2tif -i /path/to/olympus/image.vsi -o /path/to/converted/image.tif -b /path/to/bftools/bfconvert
```

Here is an example to perform batch conversion of a folder of WSIs:
```
vsi2tif -i /path/to/olympus/wsis/ -o /path/to/converted/wsis/directory/ -b /path/to/bftools/bfconvert
```

Comprehensive CLI documentation can be seen below:

```
usage: vsi2tif [-h] -i INPUT -o OUTPUT -b BFCONVERT [-c COMPRESSION] [-s TILESIZE] [-p PLANE] [-q QUALITY] [-m MAX_MEM] [-v VERBOSE]

vsi2tif - simple tool for converting images from cellSens VSI to Generic TIFF

options:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        folder with input files
  -o OUTPUT, --output OUTPUT
                        folder for output files
  -b BFCONVERT, --bfconvert BFCONVERT
                        path to bfconvert tool
  -c COMPRESSION, --compression COMPRESSION
                        compression technique for final image
  -s TILESIZE, --tilesize TILESIZE
                        tile size to use during both conversion steps
  -p PLANE, --plane PLANE
                        which image plane to convert image from
  -q QUALITY, --quality QUALITY
                        compression quality used with JPEG compression
  -m MAX_MEM, --max-mem MAX_MEM
                        set maximum memory in the java vm
  -v VERBOSE, --verbose VERBOSE
                        set verbosity level
```

## [License](https://github.com/andreped/vsi2tif#license)

This project has [MIT license](https://github.com/andreped/vsi2tif/blob/main/LICENSE).
