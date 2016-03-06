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


