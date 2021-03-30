
The Wiki is hosted on https://ldssa.github.io/wiki/.


## How to create/edit a page

Each page is stored as a markdown on a subfolder of the `/docs/_docs/` directory.

**Example:** The page "Application Process" will be located in https://ldssa.github.io/wiki/Applicants/Application-process/, so it should be stored in the repo's folder `/docs/_docs/`**`Applicants`**. All pages follow this logic.

At the top of each `.md` page you have a heading that specifies to what sidebar category the page belongs to, its title and the order in which it appears on that sidebar category.

```markdown
---
title: Application Process
category: Applicants
order: 1
---
```

### Edit an existing page

If you want to edit an existing page, browse it in the pages directory [`/docs/_docs/`](https://github.com/LDSSA/wiki/tree/main/docs/_docs).

1. Locate the file (page) you want to edit and click on it;
1. Click the edit button (pencil symbol) on the top-right corner to edit the page;
1. When you're ready, insert a commit message at the end of the page and select the option `Create a new branch`. Click `Propose changes`;
1. The Documentation Team will review and approve your changes.

**Alternatively**, you can clone this repo, do your changes locally, commit and PR.



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