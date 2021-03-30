

## How to create/edit a page


Each page is stored as a markdown in a folder inside `/docs/_docs/`. For example, the page `Application Process` will be located in `https://ldssa.github.io/wiki/`**`Applicants`**`/Application-process/`, and stored in folder `/docs/_docs/`**`Applicants`**. All pages follow this logic.

You can either:

(a) edit the page locally by cloning the repo, editing, commiting and do a Pull Request to `main`.

**or**

(b) edit the page on the browser by navigating to its location on the Wiki, for example https://github.com/LDSSA/wiki/blob/main/docs/_docs/Applicants/Application-process.md, and click the edit button (pencil icon) on the top-right corner of the file preview. After you're done just create a name for your `commit` (at the end of the same browswer page), and hit "Commit changes". A PR will be generated that should be reviewed and approved by the [Documentation Team](https://github.com/orgs/LDSSA/teams/documentation).

---

#TODO - Insert Documentation

#TODO - Insert picture depicting the edit button

---

## How to test the site locally (Ubuntu)

### **1. Install necessary packages**

1. Update and install all prerequisites:

    ```bash
    sudo apt-get update
    sudo apt-get install ruby-full build-essential zlib1g-dev
    ```

1. Add the environment variables to `~/.bashrc` by running:

    ```bash
    echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
    echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
    echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
    source ~/.bashrc
    ```

1. Install `jekyll` and `bundler`

    ```bash
    sudo gem install jekyll
    sudo gem install bundler -v '< 2.0'
    ```

**That's it!**

### **2. Run the site locally**

```bash
bundle install
```

```bash
bundle exec jekyll serve
```

## References

- [Template source](https://github.com/CloudCannon/edition-jekyll-template)

- [Installing Jekyll on Ubuntu](https://jekyllrb.com/docs/installation/ubuntu/)