# Puradata

This is a set of helper scripts to translate Pd's internal documentation (docs, extra) into other languages.

# Steps

1. Create a template out of all patches inside specified File-Directory
2. Human Translate using your prefered tool (Google toolkit, OmegaT, etc)
3. Translate the patches back to Pd.

# 1 : Create a Template

This fetches all pd 'comments' inside all patches in the specified File-Directory: (to change where pd is, see below)

Run  `$ ./template` specifying **all** the following arguments:

1. File-Directory
2. Author Name (e.g. \"Name Lastname\") 
3. Author email
4. Target language
5. Target language id (e.g. de, es, fr...)

For example:

`$ ./template doc/5.reference \"Fede Camara Halac\" camarafede@gmail.com Spanish es`

Or "extra/sigmund~", "extra/bob~", "doc/2. etc..

If you did things right, you get the following files:

* "5.reference".po
* "5.reference".index

# 2 : Human Translate

This is where Google Toolkit (or OmegaT, or whatever) and expertise comes in handy. Load the generated "File".po into the translating software. Once you are done, save it in the same "File".po (i.e., overwrite the file). 

NOTE: The "File".index is only meant for internal use and should not be touched.

# 3 : Translate

This will insert your translation into the current version of pd:

Run  `$ ./translate "5.reference"`

NOTE: if pd is inside the Applications directory, this might require running:

`$ sudo ./translate "5.reference"`

# PDDIR:

To change where pd is, go inside both template and translate and change the PDDIR variable to your installation.

# ERRATA:

Note that this only translates the 'comments' inside patches, i.e., 'text X Y' objects. This means that:

* Some patch cords might break afterwards depending on the case.
* Some realignment might be needed afterwards.
* The translation character set is bound to pd's comments character set.

In other words: **use at your own risk**, keep a backup of original patches, and check every translated patch just in case. 
