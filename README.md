#Intel Software Optimization for Theano*
---

This repo is dedicated to improving Theano performance when running on CPU, in particular Intel® Xeon® processors (HSW+).

Please refer to the document [Install_Guide.pdf](https://github.com/intel/theano/blob/master/Install_Guide.pdf) for the installation guide.

* Branch **master** is a general optimized version based on 0.9.0dev1, get and install it via below commands:
```
git clone https://github.com/intel/theano.git pcs-theano
cd pcs-theano
python setup.py build 
python setup.py install --user
```
* Branch **pcs-theano** is a general optimized codes based on 0.8.0rc1, get and install it via below commands:
```
git clone -b pcs-theano https://github.com/intel/theano.git pcs-theano
cd pcs-theano
python setup.py build 
python setup.py install --user
```
* Branch **mkl** is a special optimized version for CNN topologies which requires Intel® Math Kernel Library (Intel® MKL, after version 2017.0.0) based on 0.9.0dev1, get and install it via below commands:
```
git clone -b mkl https://github.com/intel/theano.git pcs-theano
cd pcs-theano
python setup.py build 
python setup.py install --user
```

Theano config files:

	* replace "~/.theanorc" with "pcs-theano/theanorc_icc" for ICPC compiler 
	* replace "~/.theanorc" with "pcs-theano/theanorc_gcc" for G++ compiler

We also provide an optimized Numpy and some demo cases, you can find optimized Numpy in [here](https://github.com/pcs-theano/numpy), and demo cases in Theano's root directory.
 

#Theano
---
To install the package, see this [page](http://deeplearning.net/software/theano/install.html)

For the documentation, see the project website [here](http://deeplearning.net/software/theano/)

[Related Projects](https://github.com/Theano/Theano/wiki/Related-projects)

It is recommended that you look at the documentation on the website, as it will be more current than the documentation included with the package.

In order to build the documentation yourself, you will need sphinx. Issue the following command:
    `python ./doc/scripts/docgen.py`

Documentation is built into html/

The PDF of the documentation can be found at html/theano.pdf


DIRECTORY LAYOUT

Theano (current directory) is the distribution directory.

* Theano/theano contains the package
* Theano/theano has several submodules:
    * gof + compile are the core
    * scalar depends upon core
    * tensor depends upon scalar
    * sparse depends upon tensor
    * sandbox can depend on everything else
* Theano/examples are copies of the example found on the wiki
* Theano/benchmark and Theano/examples are in the distribution, but not in
  the Python package
* Theano/bin contains executable scripts that are copied to the bin folder
  when the Python package is installed
* Tests are distributed and are part of the package, i.e. fall in
  the appropriate submodules
* Theano/doc contains files and scripts used to generate the documentation
* Theano/html is where the documentation will be generated

---
>\* Other names and trademarks may be claimed as the property of others.

