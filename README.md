# wordwall
Generates a word cloud wallpaper from user text files

## Features

- Detects your screen resolution
- Detects your Linux distribution and can use a default provided logo if available
- Use your own color(s) for foreground and background
- Use your own mask file (advanced)
- Reads from history and init files for different shells out of the box
- Reads commit messages from git repos out of the box
- Use your own text files

## How To Use

1. Get the latest release and extract the archive to your desired installation location.

   **OR**

   Clone this repository.

2. Run the `wordwall` script, with your desired output filename as the argument:

   ```shell
   $ ./wordwall wallpaper.png
   ```

3. Run `wordwall --help` for advanced usage and customization options. See examples below for details.

## Examples

```shell
$ wordwall wallpaper.png
```

![Default](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex1.png?raw=true "Default")

```shell
$ wordwall --logo=solus wallpaper.png
```

![Set Logo](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex2.png?raw=true "Set Logo")

```shell
$ wordwall --logo=solus --color='#8fbcbb' --color='#88c0d0' --color='#81a1c1' --bg-color='#3b4252' wallpaper.png
```

![Set Colors](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex3.png?raw=true "Set Colors")

```shell
$ wordwall --logo=arch --color='#268bd2' --bg-color='#eee8d5' --git-repo=~/dotfiles wallpaper.png
```

![git integration](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex4.png?raw=true "git integration")
