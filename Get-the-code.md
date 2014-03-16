### Goal

Download the source code for the Sagan application to your local machine.

### Prerequisites

Depending on the option you choose below, you'll need a local Git or Subversion installation, or you can simply download and unpack a zip file. The choice is yours, but we recommend the git-based approach.

### Steps

The main repository for the Sagan application can be found at <https://github.com/spring-io/sagan>. You have a few options as to how to sync these sources to your local machine:

#### Option 1: Fork and clone using Git

The recommended approach is to _fork and clone_ this repository using Git – this will allow you maximum freedom to make changes, commit and push them to your own repository, share with others, and issue pull requests.

If you've forked and cloned repositories on GitHub before, then you'll know what to do.

If this is your first time, or you don't yet have a GitHub account, we recommend you read and follow these instructions:

 - <https://github.com/join>
 - <https://help.github.com/articles/set-up-git>
 - <https://help.github.com/articles/fork-a-repo>

> **TIP**: If you're not a fan of the command line, you may also want to look into GitHub's desktop clients for [Mac](http://mac.github.com) and [Windows](http://windows.github.com).

In any case, the goal is to clone your fork of the main repository, which should look like this:

    $ git clone git@github.com:$GHUSER/sagan.git

... where `$GHUSER` is your GitHub username.


#### Option 2: Clone the main repository using Git

If you do not wish to create your own fork of the repository, you can always clone the main repo directly:

    $ git clone git@github.com:spring-io/sagan.git

> **NOTE:** This approach does not require you to have a GitHub account; it only requires that you have Git installed.


#### Option 3: Check out using Subversion

If using Subversion is more convenient for you than Git, you can check out the sources with the following command:

    $ svn checkout https://github.com/spring-io/sagan


#### Option 4: Download and unpack zip file

Simply download and unpack <https://github.com/spring-io/sagan/archive/master.zip> in the directory of your choice.


### Take a look around

Once you've completed any of the steps above, you should be able to

    $ cd sagan

where you'll find a directory structure that looks something like this:

    $ ls -1
    CONTRIBUTING.md
    README.md
    build.gradle
    gradle
    gradlew
    gradlew.bat
    sagan-client
    sagan-common
    sagan-indexer
    sagan-site
    settings.gradle
    style
    wiki

### Next steps

Now that you've got the code, you'll want to learn how to [[build everything]] and [[run the site locally]]. From there you can explore many other options. Browse the wiki to see what's possible.
