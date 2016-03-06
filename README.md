This is the Cottage Labs website.

It is a simple static website that uses getter to allow for sort-of templating by using dynamic content loading.

Just put this folder on a server somehwere, install nginx, and use the provided nginx config file to have it served at 
the domain name of your choice (obviously, assuming you also purchase that domain name and point it to your server).

Codeship is used so that any commit to the master branch automatically updates the live site.

All that has to go in this repo is the content that the CL site should contain. Supporting content such as images, css files, etc, can be loaded from anywhere or included in this repo.

To keep things neat, it is recommended to put such static content into a folder called /static.

Pages can be created by putting them in the /content folder. The filename shuold be whatever is expected to form the URL, without the /content part.

Content files can include html or markdown. Markdown should be wrapped in opening and closing &lt:markdown&gt; tags.

The usual index.html file naming paradigm can be used inside any folder in the usual way, as the default file to be served if the URL entered matches only the folder name.

For example if the content of this repo is served at mysite.com then a request to mysite.com/my/file will serve the content found in the file at content/my/file.

If mysite.com/content/my is requested, then the content of the file at content/my/index will be served, or else content/my/index.html.

If a file with the given name in the URL cannot be found in the specified folder, and cannot be found with .html appended, and also an index or index.html file cannot be found, 
then the 404 file found in the top level directory will be served instead. If that does not exist, then a standard nginx 404 will occur.

All the content files are requested and served as javascript dynamic requests, to populate a section of the page from which the request is issued.

To edit the paraphernalia of the page, see the index.html, header.html, and footer.html files in the top level directory of this repository.



