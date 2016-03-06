This is the ODB static website

All that has to go in this repo is the content that the ODB site should contain. 
Pages can be created by putting them in the /content folder. 
The filename shuold be whatever is expected to form the URL, without the /content part.
Content files can include html or markdown. Markdown should be wrapped in opening and closing &lt:markdown&gt; tags.

Supporting content such as images, css files, etc, can be loaded from anywhere or included in this repo. 
To keep things neat, it is recommended to put such static content into a folder called /static.

The usual index.html file naming paradigm can be used inside any folder in the usual way, as the default file to be served if the URL entered matches only the folder name.

For example if the content of this repo is served at mysite.com then a request to mysite.com/my/file will serve the content found in the file at content/my/file.

If mysite.com/content/my is requested, then the content of the file at content/my/index will be served, or else content/my/index.html, or content/my/index.md.

If a file with the given name in the URL cannot be found in the specified folder, and cannot be found with .html (or .md) appended, and also an index or index.html file cannot be found, 
then the 404 file found in the top level directory will be served instead. If that does not exist, then a standard nginx 404 will occur.

All the content files are requested and served as javascript dynamic requests, to populate a section of the page from which the request is issued.

To edit the paraphernalia of the page, see the index.html file in the top level directory of this repository. Ignore the header.html and footer.html files but DO NOT delete them.

There is also an /email folder where email templates will get stored. Coming soon.


HOW TO EDIT THIS CONTENT, AND AUTOMATICALLY UPDATE THE SITE

This repo will automatically deploy changes committed to the site. There is a develop branch and a master branch. 
Changes should be committed to the develop branch first and viewed on the test site. Once confirmed as being acceptable, 
they should be committed to the master branch and they will appear on the live site. Here is how to do that:

    git clone git@github.com:OAButton/odb_static.git
    git checkout develop
    # edit the files as you see fit, create new files as necessary
    # you can use the status command to check what branch you are on, and what changes you have ready to commit
    git status
    git add .
    git commit -am 'I edited these files, yay me - or some more useful message'
    git pull origin develop
    # if others have mad changes there may be some merge fixes to make after the git pull - if so, fix them.
    git push origin develop
    # check the test site to see that things look how you want (there may be a couple of minutes delay)
    git checkout master
    git merge develop
    # again check for any merge conflict warnings and fix them
    git pull origin master
    # quick check for any more changes made by others, fix any conflicts, then push the merge
    git push origin master
    # now your changes are on the live site too!
    # so switch back to develop branch ready to do more editing
    git checkout develop
  

There are UI tools that can control git for you, any of them should be usable as long as you follow the above process.
Actual editing of the files themselves can be done in any text editor or code editing tool, as you prefer.
  
  