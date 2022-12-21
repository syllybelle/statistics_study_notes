# About
Course notes for an intermediate statistics course, packaged as a docsified .md notebook for additional learning around 
documentation.
I am a python person:
I have about zero experience with R, and am experimenting with trying to use it in a standard python jupyter notebook.
I have approximately 1 experience with npm; i don't know how to use package.json files - I installed npm and docsify globally

## References
[Textbook](https://bookdown.org/probability/beta/)  Probability! by Matt DosSantos DiSorbo and Harvard Statistics Professor Joe Blitzstein.

# Quick access
[Access the notes]() hosted throguh GitHub pages


# Modification and local hosting
[conda](https://conda.io/projects/conda/en/stable/user-guide/getting-started.html)
[npm](https://github.com/cli/cli#installation)
> see `environment.yml` and `package.json` for project requirements

[Clone the repo](https://docs.github.com/en/repositories/creating-and-managing-repositories/cloning-a-repository) 
Navigate to the package directory in terminal and install python and npm dependencies by using `conda env create -f environment.yml` and `npm install` respectively.
This *should* install docsify-cli
Navigate inside the notebook folder and run `docsify serve .`, which should respond with 

`Serving /Users/syllybelle/w/prof_dev_notes now.  
Listening at http://localhost:#####`    

> the number will change with each serve

Open the URL in the browser
To kill the server, kill the terminal processs using the standard `ctl + C` 


# Todo
- Finish the course
- Add interactive codey bits
- do a bit more documentation
- fix the R env in the ipynb env, or give up and use an r notebook/r env
- test npm situation.


