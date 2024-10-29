# OpenRefine
OpenRefine is a data-cleaning tool that can help significantly with the process of cleaning inputs.

OpenRefine is a Java program that runs on your machine that uses your web browser as a graphical interface, and regularly saves so we can pick up where we left off at any point.

Data cleaning steps often need repeating with multiple files. It is important to know what you did to your data. This makes it possible for you to repeat these steps again with similarly structured data. OpenRefine is perfect for speeding up repetitive tasks by replaying previous actions on multiple datasets.
Additionally, journals, granting agencies, and other institutions are requiring documentation of the steps you took when working with your data. With OpenRefine, you can capture all actions applied to your raw data and share them with your publication as supplemental material.

The version we will use in this lab is 3.8.4. It is an open source program that is free. Download the linux version from the [downloads page of openrefine](https://openrefine.org/download).

## Setting up OpenRefine
You can unzip the program using `tar -xvzf openrefine-linux-3.8.4.tar.gz -C ~/`
This places the program into ~/openrefine-3.8.4. You can change the directory it is installed, but DO NOT place it in your github repo!

Then, to run it, we can `cd` into the installed directory, and run the `./refine` script!
It will open a browser window to handle the UI for openrefine!

![The openrefine start](./images/openrefine-ui "An example of the openrefine start.")

## Importing Data

