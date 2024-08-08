# How to contribute to this project

## Overview

This project aims to develop the SBOL converter between versions 2.X and 3.X.

This project provides hands-on experience in Python, GitHub, unittest, CI/CD, pySBOL2 and pySBOL3.  

The repository where we are contributing is [SBOL-utilities](https://github.com/SynBioDex/SBOL-utilities).
The converter is in an SBOL-utilities module [sbol3_sbol2_conversion](https://github.com/SynBioDex/SBOL-utilities/blob/develop/sbol_utilities/sbol3_sbol2_conversion.py) 

The converter module has been architechtured in an easy to contribute format.
It defines two classes 'SBOL3To2ConversionVisitor' and 'SBOL2To3ConversionVisitor'.
These objects orchestrates the conversion visiting each member of a SBOL 'Document' to map it into the other version.
Each SBOL element has a function to be converted.

## Pick an object to convert

All the SBOL elements to convert where added as [issues](https://github.com/SynBioDex/SBOL-utilities/issues)

You can assign yourself any issue, try starting with low priority objects if you are still not confident, you will gain experience and be able to tarjet more difficult conversions.
Basically each issue looks for convert an SBOL element between the 2.X and 3.X versions. 
Create a branch to work in the issue that you selected, we recommend to name it with something relevant like 'converter' or the name of the issue that you selected.

## Define a mapping between SBOL2 to SBOL3

To check how to transform SBOL elements check the [SBOL scpecification](https://sbolstandard.org/datamodel-specification/version-3.1.0/).
An overview of SBOL is provided in section 3, the mapping between SBOL2 and SBOL3 is provided in section 10.2. Figure 26 can be usefull when trying to get the mapping.

Once you have an idea of the mapping you can let others know on the SBOL Devs Slack channel to get feedback.
The discussion on Sclak will polish the mapping.

## Code the conversion

Once you are ready to code you will modify the [sbol3_sbol2_conversion](https://github.com/SynBioDex/SBOL-utilities/blob/develop/sbol_utilities/sbol3_sbol2_conversion.py) file and code the mapping from SBOL3 to SBOL2 in 'SBOL3To2ConversionVisitor' and the mapping from SBOL2 to SBOL3 in 'SBOL2To3ConversionVisitor', scroll around and follow the pattern. Here is the documentation of some the used packages: [pySBOL2](https://pysbol2.readthedocs.io/en/latest/) to create SBOL2 objects, [pySBOL3](https://pysbol3.readthedocs.io/en/stable/) to create SBOL3 objects and [Tyto](https://tyto.readthedocs.io/en/latest/index.html) to manage ontologies.

Again, if you are stalled or have a question communicate in the Slack channel we are happy to help.
With the feedback provided in slack your code will be polished and ready to write a test.

Add your test to thi the [test_sbol2_sbol3_direct](https://github.com/SynBioDex/SBOL-utilities/blob/develop/test/test_sbol2_sbol3_direct.py) file, scroll around and follow the pattern.
Probably you will have issues implementing the test, ask in the Slack channel we are happy to help. You can find objects to use in your teste in the [SBOLTestSuite](https://github.com/SynBioDex/SBOLTestSuite) repository.

## Contribute your branch

Once your test passed succesfully you will see the gree dot that indicates that the CI/CD workflow runnned without errors.
Create a pull request and ask for review to the package maintainer Jake Beal, optionally you can add other SBOL Devs.
Work in the code reviews and once the PR is approved, merge it and delete the branch.

Congratulations! You finished your contribution, now you can take a break and pick another object when ready[.](https://youtu.be/K2VzuA6UZ7A)

