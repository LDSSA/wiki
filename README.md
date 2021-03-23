

## How to create/edit a page

#TODO

## How to test the site locally (Ubuntu)

### **1. Install necessary packages**

1. Update your system:

    ```bash
    sudo apt-get update
    ```

 2. Install all prerequisites:

    ```bash
    sudo apt-get install ruby-full build-essential zlib1g-dev
    ```

3. Add the environment variables to `~/.bashrc` by running:

    ```bash
    echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
    ```
    ```bash
    echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
    ```
    ```bash
    echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.
    bashrc
    ```
    ```bash
    source ~/.bashrc
    ```

4. Install `jekyll` and `bundler`

    ```bash
    sudo gem install jekyll
    ```

    ```bash
    sudo gem install bundler -v '< 2.0'
    ```


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