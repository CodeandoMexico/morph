## What's New
Here we show you the changes that you can see. We update this page every few weeks.
There's also lots of stuff that changes under the
hood. If you're interested in seeing those too, look at the
[full list of commits](https://github.com/openaustralia/morph/commits/master).

### May 17
For the case where people need to use secret keys in their scrapers (for instance
accessing an API that requires them), you can now set one or more environment variables in the
web interface that can be used in your scraper. Each scraper can have its own set
of environment variables. The variables are viewable only by
you or people who have write access to that scraper.

Go to the scraper settings to access.

On creating a scraper you can now optionally add a description.

### May 5
Added progress bar during the creation of a new scraper and adding a scraper from GitHub.

### May 1
Unfortunately we had our first case of abuse today. So, we suspended a user which of course
involved us adding support for suspending a user!

### April 26
There's now an [example page that you can try out your scraping skills on](#{examples_australian_members_of_parliament_documentation_index_path}). It's based on the official
list of Australian members of parliament.

### April 19
You can now write scrapers in Perl thanks to the effort of [@lkundrak](/lkundrak).

### April 18
* In the API add support for atom feeds. Thank you to [@pezholio](https://github.com/pezholio) for this!
  It works in a really flexible way where you can make any field of your data map to different
  bits of the atom feed like the content and the link in each item. [Have a look](#{api_documentation_index_path}).
* Added this "What's new" page

### April 17
* Morph now only needs to ask you for public repository read/write permissions for GitHub.
  This is what we previously said:

  > Why do you ask for read/write access to all my GitHub repositories, even the private ones?

  > We don't in fact access your private repositories at all. Unfortunately because of a limitation
  > in the GitHub API we have to ask for write permissions to private repositories to be able to
  > create public repositories. I know it seems crazy but that's how they're doing things. We're
  > hoping that soon GitHub will provide more fine-grained access control which will solve this.
  > To see in detail what's happened so far see the
  > [issue on GitHub](https://github.com/openaustralia/morph/issues/230).

  This is **no longer the case**. Thank you Github for
  [changing your API](https://developer.github.com/changes/2014-04-04-create-public-repo-without-repo-scope/).

* You might have heard about the [heartbleed bug](http://heartbleed.com/). On the day heartbleed was
  announced we patched the morph server. This stops anyone from exploiting the bug to gain
  access to the SSL private key. No passwords are stored on our server because we authenticate
  against GitHub using oauth. To be safe we've refreshed everyone's github oauth access token.

### April 16
* Made the scraper run button more prominent
* Speedup up the home page and the scraper pages
* Changed the scraper error behaviour. We used to consider any output to standard error from
  a scraper as an "error". This was put in place to catch certain types of errors in PHP
  which did not cause a non-zero exit status. We've realised the error in our way as it does
  mean in other languages legitimate warnings are causing scraper "errors" which isn't good.
  So, now only the exit status is used to determine whether the scraper has errored or not.

### April 12
* Small content tweaks
* Fixed some ScraperWiki URLs that had changed in ScraperWiki becoming read-only.

### April 11
* Fix problem caused by table names with spaces in SQLite

### Mar 28
* On each run it now shows you the number of database records that were added, removed or changed.

### Mar 27
* Improve error checking on ScraperWiki form page

### Mar 26
* Small visual design tweaks
* Show number of watchers on scraper pages with a link to the full list of watchers

### Mar 25
* Design fixes
* Redesigned user pages
* Updated API documentation

### And further back

If you're interested in looking further back then see the [full list of commits](https://github.com/openaustralia/morph/commits/master).
