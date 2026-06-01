


https://github.com/user-attachments/assets/30f19727-5089-44c6-8598-965a7b3220e3



Log Default


# VIMES: VIsualization of Massive Evolving Stars
Creates a stellar evolution animation for binary systems simulated using COMPAS (or another population synthesis code).
Animation is reflective of the radius, separation, perceived color etc of the stars. 

ALL code related to temperature-color relationship is directly from the (TULIPS code)[https://bitbucket.org/elaplace/tulips/src/master/]. Read (the paper)[https://ui.adsabs.harvard.edu/abs/2022A%26C....3800516L/abstract] for more information.

## Installation

### Using uv (recommended)
This project is managed by [uv](https://docs.astral.sh/uv/), so the best way to install it is also using uv (follow [install instructions for uv](https://docs.astral.sh/uv/getting-started/installation/) if you don't have it):

    uv tool install git+https://github.com/layabinu/VIMES_VIsualization_of_Massive_Evolving_Stars.git

The project can also be cloned from Github as usual, and then installed by running the following command in the cloned directory:

    uv tool install -e .

The `-e` flag signals that local changes to the cloned codebase will also automatically be reflected in the installed tool.

### Using pip
If you'd rather just use pip, we recommend installing the cloned project to a virtual environment:

    python -m venv venv
    source venv/bin/activate
    pip install -e .

The project will then need to be run using the virtual environment, which is typically done by activating the environment before running the script.

## Usage
Once installed, the project should be able to be run as follows:

    vimes-preprocess <path-to-input>.h5 <output-path>.npz

In this case, it will take the input HDF5 file and create a frames file at the output path. Once the frames file has been created, we can create the animation by running:

    vimes <path-to-frames>.npz

This also comes with several optional inputs:
 - `--scaling` affects the scaling of the animation. It is `linear` by default, but can also accept `log`.
 - `--images` affects the images that are shown in the animation. The default value is `default`, which renders images of the objects at each stage of evolution, while the other option is `tulips`, which renders circles coloured by their temperature (using the [tulips project](https://bitbucket.org/elaplace/tulips/src/master/)).
 - `--save-mp4` saves the movie at the specified path.
 - `--no-display` stops the animation from being displayed (usually only useful if the animation is also being saved as mp4).



https://github.com/user-attachments/assets/7c057ed1-494a-4d30-a08d-a19cd3588de0



Linear Tulips

## Akcnowledgement:
VIMES was created by Laya Binu, please contact Laya for any questions.
If you make use of VIMES, we ask you to cite the following Zenodo publication

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18503545.svg)](https://doi.org/10.5281/zenodo.18503545)


@software{laya_binu_2026_18503545,
  author       = {Laya Binu},
  title        = {layabinu/VIMES\_VIsualization\_of\_Massive\_Evolving\_S
                   tars: VIMES Stellar Evolution Visualization Code
                  },
  month        = feb,
  year         = 2026,
  publisher    = {Zenodo},
  version      = {v0.1.0},
  doi          = {10.5281/zenodo.18503545},
  url          = {https://doi.org/10.5281/zenodo.18503545},
}


