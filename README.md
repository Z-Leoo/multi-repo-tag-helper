# Multi Repository Tag Helper

:construction: Work In Progress

:warning: For now this helper works only on macOS with the help of [Oh My Zsh](https://ohmyz.sh/). But we can improve it with your help. **Feel free to fork this project and suggest improvements**. 

____________

### What is the tag helper

The tag helper is an open source script that assists in version control of projects with git sub-modules.

Its purpose is to replicate the tag in the parent repository to all child sub-modules. This makes it easier to control and visualize all the modules

____________

### How to implement helpers *(Only for Mac users)*
- with ohMyZsh installed. Open the terminal and run the command:
```
open ~/.zshrc
```
- In the file that you have opened, copy and paste the code blocks *(Tag Module Helper and Fetch Tags Helper)*. [You can find the codes by clicking here](HELPERS_MACOS.md).
- Save and close the file.
- Now, in terminal, run:
```
exec zsh
```
- If ohMyZsh is still enabled, everything is okay

____________

### How to use

- Open terminal in a git repository
- To create a new tag
```
tag_modules <tag>
```
- To fetch all project from tag
```
get_from_tag <tag>
```
- See how it works

[![Watch the video](https://i.imgur.com/vKb2F1B.png)](https://youtu.be/vt5fpE0bzSY)
