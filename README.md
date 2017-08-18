# Orodja za pripravo http://jankoslavic.github.io/pypinm/

The website is generated using the [Pelican](http://docs.getpelican.com/) static site generator.
The website generator is based on: https://github.com/jakevdp/PythonDataScienceHandbook.git

## Building the Website

Clone the repository & make sure submodules are included

```
$ git clone https://github.com/jankoslavic/pypinm.git
$ git checkout origin/website
$ git submodule update --init --recursive
$ cd website
```

Install the required packages:

```
$ pip install pelican Markdown ghp-import
```

Copy the notebook content to the right location (this script also modifies some links for the HTML):
```
$ python copy_notebooks.py
```

To generate the production site in the output directory:
```
$ pelican content -o output -s pelicanconf.py
$ ghp-import output
$ git push origin gh-pages
```

To generate the content for your debug site in the output directory:
```
$ pelican content --debug --autoreload  --output output --settings pelicanconf.py
```
