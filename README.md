# SPxml

SPxml is a Python library to get ECG data from Philips Sierra ECG XML format.

## Prerequisites

* **[libxml2:](http://xmlsoft.org/index.html)** The XML C parser and toolkit of Gnome

```sh
sudo apt-get install libxml2
sudo apt-get install libxml2-dev
```

* **[sierra-ecg-tools](https://github.com/sixlettervariables/sierra-ecg-tools)** Tools to work with the Philips Sierra ECG XML format.

*The library sierra-ecg-tools has code for work with the Philips Sierra ECG XML format in different programming languages, however, a minimalist version is included in this repository, as it only uses its support for the C language.*


## Installation

Clone this repository
```sh
git clone https://github.com/EmanuelSanchez/SPxml.git
```

Move to cloned repository
```sh
cd spxml/
```

Install the library with the following command
```sh
python3 setup.py install --user
```
## Software tested

This project was tested in Ubuntu 16.04 with the following software:

* Python 3.5.2
* Python 2.7.12
* libxml2 2.9.4

## Example
```python
import SPxml

file_path = "spxml/xml/example0.xml"
ecg = SPxml.getLeads(file_path)

for lead in ecg:
    # lead['name']  -  name of ECG lead
    # lead['nsamples'] - number of samples
    # lead['duration'] - total msec of the recording
    # lead['data'] - lead sample data in mv
    print(lead['name'] + " - " + str(lead['nsamples']))
```

## License

This project is licensed under the MIT License - see the LICENSE.md file for details