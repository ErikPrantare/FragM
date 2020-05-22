
# FragM
This is derived from Mikael Hvidtfeldt Christensen's Fragmentarium representing a compilation of features and fixes contributed by many users at FractalForums since 2013.

Status
----------------------
[![Release][release-image]][releases]
[![License][license-image]][license]
[![Build Status](https://travis-ci.org/3Dickulus/FragM.svg?branch=master)](https://travis-ci.org/3Dickulus/FragM)

[release-image]: https://img.shields.io/badge/release-2.5.3-green.svg?style=flat
[releases]: https://github.com/3Dickulus/FragM/releases

[license-image]: https://img.shields.io/badge/license-GPL3-green.svg?style=flat
[license]: https://github.com/3Dickulus/FragM/blob/master/LICENSE

### FragM now uses submodules for the Examples folder and user contributed subfolders.
    when cloning the repo use 'git clone --recurse-submodules https://github.com/3Dickulus/FragM.git'
    when checking out a branch use 'git checkout --recurse-submodules <branchname>'
    when updating from the online repo 'git submodule update --init --remote --recursive'

    as a result of this the source archive files provided by github are lacking the Example/files
    so an auxiliary archive will be provided on the release page that has the complete sources.

----------------------

# Changes since v0.9.5
    Please see https://github.com/3Dickulus/FragM/blob/master/Fragmentarium-Source/3Dickulus.changes
    and git logs for all of the changes since 2.0.

----------------------

# Building with Ubuntu Linux


## Update the main repository...

      sudo apt-get -qq update

## Ensure these packages are installed...

      sudo apt-get -qq install cmake \
                               extra-cmake-modules \
                               libopenexr-dev \
                               libilmbase-dev \
                               libqt5scripttools5 \
                               libqt5gui5 \
                               libqt5svg5-dev \
                               libqt5opengl5-dev \
                               libqt5xmlpatterns5-dev \
                               qt5-qmake \
                               qttools5-dev \
                               qtbase5-dev \
                               qt5-style-plugins \
                               qt5-image-formats-plugins \
                               qtscript5-dev \
                               libglm-dev \
                               zlib1g-dev


## Get the source...

    git clone --recurse-submodules https://github.com/3Dickulus/FragM.git FragM
      
    or download and extract the source.zip archive from https://github.com/3Dickulus/FragM/releases/

## Build and install

      cd FragM/Fragmentarium-Source
      mkdir build
      cd build
      cmake -DUSE_OPEN_EXR=ON -DCMAKE_INSTALL_PREFIX=~/ ..
      make install

    The above will install in /home/username/Fragmentarium folder with includes and support files.

    To install for all users change -DCMAKE_INSTALL_PREFIX=~/ to -DCMAKE_INSTALL_PREFIX=/usr/local and use sudo make install


# Pre-built packages

   You can find pre-built packages for OSX 10.14.4, Ubuntu 18.0.4 Bionic, SuSE Leap 15.1 and Windows at https://github.com/3Dickulus/FragM/releases/

# Dependencies

   Recommends:  ffmpeg or mencoder for creating videos from a folder of images using the Video Dialog.

   Pre-depends: OpenEXR v2.4 https://github.com/AcademySoftwareFoundation/openexr/releases ( Win version uses static linked OpenEXR lib )

   Pre-depends: GLM https://glm.g-truc.net/ ( at compile time for all OSs )

   Depends:     Qt5Core, Qt5Gui, Qt5OpenGL, Qt5Script, Qt5Widgets, Qt5Xml

# Guidelines for contributing
    1. any new feature must work on the widest range of hardware, ( AMD Intel and nVidia ) all if possible
    2. any changes to existing features must be compatible with the existing fragment base
    3. existing features that only work on specific hardware should be phased out or modified to work on all hardware.
    4. when adding options or settings they must be in line with the existing structure for handling options and settings
       (unless you have a better idea that makes the current structure obsolete)
    5. priority should go towards handling more modern GLSL versions and practices
    6. changes and additions must be tested against all other features, animating, timeline management,
       easing curve controls etc... and render the base frags properly before merging will be considered.

...of course none of this is carved in stone and I'm always open for discussing ideas.


# License

Copyright (C) 2010-2014 Mikael Hvidtfeldt Christensen : 2015-2020 Digilantism by Richard Paquette

Fragmentarium is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

See COPYING or https://www.gnu.org/licenses/gpl-3.0.en.html for the full GPLv3 license.


## Notes

The deb and rpm packages should take care of any dependencies when installing via **apt / synaptic** or **yast / zypper**.

The Windows .7z file is an archive with everything FragM needs to run, includes all of the required Qt and runtime DLLs, this can be extracted and placed anywhere.

The best version will be the one you compile yourself because it will be optimized for your hardware setup.

And finally, please see the FAQ http://blog.hvidtfeldts.net/index.php/2011/12/fragmentarium-faq/ and https://fractalforums.org/fragmentarium/17 if you have any problems.

If you don't find an answer to your problem/question you can post on the Fragmentarium board at FractalForums.org or raise an issue here on github in the FragM repo.
