<div align="center">

<img src="doc/zl_tile_logo.png" width="50px">

**`zpy`: Synthetic data in Blender.**

<p align="center">
  <a href="https://zumolabs.ai/">Website</a> •
  <a href="#Install">Install</a> •
  <a href="#Tutorials">Tutorials</a> •
  <a href="#Contribute">Contribute</a> •
  <a href="#Licence">Licence</a>
</p>

[![PyPI - Python Version](https://img.shields.io/pypi/pyversions/pytorch-lightning)](https://pypi.org/project/pytorch-lightning/)
[![PyPI Status](https://badge.fury.io/py/pytorch-lightning.svg)](https://badge.fury.io/py/pytorch-lightning)
[![Slack](https://img.shields.io/badge/slack-chat-green.svg?logo=slack)](https://join.slack.com/t/pytorch-lightning/shared_invite/zt-f6bl2l0l-JYMK3tbAgAmGRrlNr00f1A)
[![license](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/PytorchLightning/pytorch-lightning/blob/master/LICENSE)
</div>

## Abstract

fooo [1] foooo [2] fooo [3].

## Install

The current version of zpy is:

```
export ZPY_VERSION="v1.1.13"
```

### Install: Blender


Blender is the best free and open 3D creation software in the world! Download the latest Blender [here](https://www.blender.org/download/). This code has been tested using Blender version:

```
export BLENDER_VERSION="2.90"
export BLENDER_VERSION_FULL="2.90.1"
```

### Install: Pip (Python Package)

These instructions install the pip package directly in your Blender folder. More information on how [Blender paths work](https://docs.blender.org/manual/en/latest/advanced/blender_directory_layout.html):

**You will have to change these paths depending on your system.**

```
export BLENDER_PATH="/home/ook/Downloads/blender-${BLENDER_VERSION_FULL}-linux64/${BLENDER_VERSION}"
export BLENDER_LIB_PY="${BLENDER_PATH}/python/lib/python3.7"
export BLENDER_BIN_PY="${BLENDER_PATH}/python/bin/python3.7m"
export BLENDER_BIN_PIP="${BLENDER_PATH}/python/bin/pip3"
```

You might have to install pip itself:

```
${BLENDER_BIN_PY} -m ensurepip && ${BLENDER_BIN_PIP} install --upgrade pip
```

Then install the pip module

```
$BLENDER_BIN_PIP install --extra-index-url=https://74ab8c3212f97d202fdfe59ce6ff9baa2fed10cae3552aee:@packagecloud.io/zumolabs/pypi/pypi/simple zpy-zumo
```

You might have to install more pip packages

```
$BLENDER_BIN_PIP install -r requirements.txt
```

OPTIONAL: Export packagecloud pypi as external index url.

```
export PIP_EXTRA_INDEX_URL="https://74ab8c3212f97d202fdfe59ce6ff9baa2fed10cae3552aee:@packagecloud.io/zumolabs/pypi/pypi/simple"
```

### Install: Blender Addon

Blender makes it easy to install Addons from a packaged zip file.

Start Blender and navigate to "Edit -> Preferences -> Add-ons". Search and enable "zpy_addon". Save your config.

![Enabling the addon](./doc/addon_setup_location.png)

The add-on will show up in the "N" panel. You can enable the N panel by just pressing "n" on your keyboard.

![The N panel](./doc/addon_panel_location.png)

### Install: Developer Environment

If you are setting up a development environment it will be easier to symlink the zpy pip module directly into the Blender python library. This can be achieved with something like:

```
ln -s ~/zumolabs/zpy/zpy ${BLENDER_LIB_PY}/site-packages/
```

You can also symlink the zpy addon in this way. For linux this is:

```
mkdir -p ~/.config/blender/${BLENDER_VERSION}/scripts/addons
ln -s ~/zumolabs/zpy/zpy_addon ~/.config/blender/${BLENDER_VERSION}/scripts/addons/zpy_addon
```

Some scenes require the path to the asset library as an environment variable. Example:

```
export ASSETS="~/assets"
```

## Tutorials

TODO

## Contributing

### Contributing: Community

TODO

### Contributing: Cutting a Release

Fetch and list existing tags

```
git fetch --tag
git tag
```

Cut a release candidate (e.g. `v1.0.0-rc0`) or release (e.g. `v1.0.0`)

```
git tag ${ZPY_VERSION} && \
git push origin ${ZPY_VERSION}
```
Release Candidates are available to download through pip through explicit version or `pip install --pre zpy`

Check progress on [CI](https://app.circleci.com/pipelines/github/ZumoLabs/zpy)

Check progress on [packagecloud](https://packagecloud.io/zumolabs/pypi)

## Licence

This release of zpy is under the GPLv3 license, a free copyleft license used by Blender.

## BibTeX

If you want to cite these tools:

```bibtex
@article{zpy,
  title={zpy: Synthetic data for Blender.},
  author={Ponte, H. and Ponte, N. and Karatas, K},
  journal={GitHub. Note: https://github.com/ZumoLabs/zpy},
  volume={1},
  year={2020}
}
```