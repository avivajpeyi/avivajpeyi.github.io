You may need two repositories, one for Hugo’s content, and a second one that will be a git submodule with the public folder’s content in it.

Check the Hugo docs Host on Github Step-by-step Instructions:

Create a <YOUR-PROJECT> (e.g. blog) repository on GitHub. This repository will contain Hugo’s content and other source files.

Create a <USERNAME>.github.io GitHub repository. This is the repository that will contain the fully rendered version of your Hugo website.

git clone <YOUR-PROJECT-URL> && cd <YOUR-PROJECT>

Make your website work locally (hugo server or hugo server -t ) and open your browser to http://localhost:1313.

Once you are happy with the results:

Press Ctrl+C to kill the server

rm -rf public to completely remove the public directory

git submodule add -b master git@github.com:<username>/<username>.github.io.git public. This creates a git submodule. Now when you run the hugo command to build your site to public, the created public directory will have a different remote origin (i.e. hosted GitHub repository). You can automate some of these steps with the following script.
