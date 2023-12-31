## Blog site using GitHub Pages and Jekyll
> This site is intended for Students.   This is to record plans, complete hacks, and do extra work for your learning.
- This can be customized to support computer science as you work through pathway (JavaScript, Python/Flask, Java/Spring)
- All tangible artifact work is in a _posts or in a _notebooks.  
- Front matter (aka meta data) is used to organize information according to week and column.

## Preview Site 
> GitHub Pages development is optimized by testing and developing on your local machine.  This is called previewing you work, prior to commit and push.

### WSL installation requirements
- Install for Ubuntu using apt, full details on [jekyllrb.com](https://jekyllrb.com/docs/installation/ubuntu/)
```bash
# ruby
sudo apt install ruby-full build-essential zlib1g-dev
# avoid root user, set up a gem installation directory for your user account
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
# install jekyll and bundler
gem install jekyll bundler
```

### MacOs installation requirements 
- Install for MacOS using brew, full details on [jekyllrb.com](https://jekyllrb.com/docs/installation/macos/)
```bash
# ruby
brew install chruby ruby-install xz
ruby-install ruby 3.1.3
# configure ruby into shell .zshrc or change to .bash_profile
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.1.3" >> ~/.zshrc # run 'chruby' to see actual version
#
# quit and relaunch terminal
#
# install jekyll
gem install jekyll
```

### Run Locally
- Result of these step is server running on: http://0.0.0.0:4100/teacher/.  Regeneration messages will run in terminal on any save.  Press Enter key in terminal at any time to type commands.

- Complete installation
```bash
bundle install
```
- Now the project is ready for preview.  To simplify running, typing, and review logging details a ```Makefile``` is used.  Review the Makefile for deeper analysis on these instructions.

    - Run preview server, re-run any time you feel things are not working correctly
    ```bash
    make
    ```

    - Stop preview server and Clean constructed files, best stop choice
    ```bash
    make clean
    ```

    - Stop preview server, leaves constructed files in project for your review
    ```bash
    make stop
    ```

    - Test notebook conversions, best choice to see if IPYNB is acting up
    ```bash
    make convert
    ```
    