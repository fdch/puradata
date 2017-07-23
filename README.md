# Puradata

This is a set of helper scripts to translate Pd's internal documentation (docs) into other languages.

# Use

1. Create a template
2. Translate using your prefered tool (Google toolkit, OmegaT, etc)
3. Integrate the translated back to Pd.

# 1 : Template

Run 

`  $ ./template

Specifying all the following arguments:

1 : File-Directory (***)
2 : Author Name (e.g. \"Name Lastname\") 
3 : Author email
4 : Target language
5 : Target language id (e.g. de, es, fr...)

For example:

`  $ ./template 5.reference \"Fede Camara Halac\" camarafede@gmail.com Spanish es

(***) There is a list of all found File-Directories inside pd/docs

If you did things right, you get a bunch of files created and a 'successful' message

# 2 : Human Translate

This is where Google Toolkit (or OmegaT, or whatever) and expertise comes in handy

# 3 : Translate

Run 

`  $ ./translate "5.reference"

This will insert your translation into the current version of pd.


# ERRATA:

Note that this only translates the 'comments' inside patches, i.e., 'text X Y' objects. This means that some patch cords might break afterwards depending on the case. Also, some realignment might be needed afterwards, so you need to check every patch just in case.
