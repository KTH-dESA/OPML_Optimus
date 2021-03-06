# Overview
This is a repository to host the osemosys and onsset country models for Afghanistan, Ethiopia, Sierra Leone and Uganda developed under the project "National energy planning and policy support for the achievement of sustainable development goals" in collaboration with each country´s researchers and the Division of Energy Systems at KTH. The project was funded by the Applied Research Programme on Energy for Economic Growth (EEG), led by Oxford Policy Management. The programme is funded by the UK Government, through UK Aid.

The OSeMOSYS model published as a Frictionless Data [Tabular Data Package](https://frictionlessdata.io/specs/tabular-data-package/).

The Data Package for the osemosys models were constructed with the help of the Python **otoole** package available on [PyPI](https://pypi.org/project/otoole/) and [Github](https://github.com/OSeMOSYS/otoole).

The osemosys models require `v0.5.4` or later of **otoole**.
You can use **otoole** to generate a GNU MathProg data file for each one of the corresponding countries from the dataset with the following commands and then run OSeMOSYS.

```bash
# Install the OSeMOSYS toolkit
pip install otoole>=0.5.4
# Download the dataset and build a GNU MathProg datafile
otoole convert datapackage datafile https://zenodo.org/record/3479823/files/OSeMOSYS/<countryname>.zip ./<countryname>.txt
# Solve the model
glpsol -m OSeMOSYS.txt -d <countryname>.txt
