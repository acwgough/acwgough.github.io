# Steps taken to install pylians3 on Mac

- Download the pylians3 code from the [github](https://github.com/franciscovillaescusa/Pylians3/blob/master/documentation/Documentation.md)
- In a new conda environment (conda create --name myenv python=3.x.x) install the dependent packages laid out in the documentation
- Homebrew install the following
	- brew install llvm
	- brew install libomp
- navigate to the Pylians3-master/library directory. In there, open setup.py. Need to delete every instance of '-fopenmp'
- in terminal while in library directory, run python setup.py install
- This should work!