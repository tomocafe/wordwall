# wordwall
Generates a word cloud wallpaper from user text files

## Features

- Detects your screen resolution
- Detects your Linux distribution and can use a default provided logo if available
- Use your own color(s) for foreground and background
- Use your own mask file (advanced)
- Use a background image to superimpose the word cloud onto
- Reads from history and init files for different shells out of the box
- Reads commit messages from git repos out of the box
- Use your own text files

## How To Use

1. Get the [latest release](https://github.com/tomocafe/wordwall/releases) and extract the archive to your desired installation location. The `logo` directory must be kept in the same directory as the `wordwall` script.

   **OR**

   Clone this repository.

2. Install required and desired optional dependencies

   Run the provided `setup` script, or refer to the list of dependencies below. By default, it will install the dependencies to your user home directory. You may install these modules systemwide by giving the `--system` flag to the `setup` script. If you want to install the modules with your distro's package manager, do not use the `setup` script.

3. Run the `wordwall` script, with your desired output filename as the argument:

   ```shell
   $ ./wordwall wallpaper.png
   ```

4. Run `wordwall --help` for advanced usage and customization options. See examples below for details.

## Dependencies

#### Required

* [WordCloud](https://pypi.org/project/wordcloud/)

#### Optional

* [distro](https://pypi.org/project/distro/) - for detecting your Linux distribution to select a default logo
* [xlib](https://pypi.org/project/xlib/) - for detecting your screen resolution to select a default width and height
* [GitPython](https://pypi.org/project/GitPython/) - for reading git logs

## Examples

```shell
$ ./wordwall wallpaper.png
```

![Default](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex1.png?raw=true "Default")

```shell
$ ./wordwall --logo=solus --color='#8fbcbb' --color='#88c0d0' --color='#81a1c1' --bg-color='#3b4252' wallpaper.png
```

![Set Logo and Colors](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex2.png?raw=true "Set Logo and Colors")

```shell
$ ./wordwall --logo=arch --color='#268bd2' --bg-color='#eee8d5' --git-repo=~/dotfiles wallpaper.png
```

![git integration](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex3.png?raw=true "git integration")

```shell
$ ./wordwall --logo=manjaro --color='#ffffff' --bg-image='gradienta-coj7UZ7iN60-unsplash.png' wallpaper.png
```

![Background Image](https://raw.githubusercontent.com/tomocafe/assets/master/wordwall/ex4.png?raw=true "Background Image")

<small>Image credit: [Gradienta on Unsplash](https://unsplash.com/photos/coj7UZ7iN60)</small>

## Contributing

Pull requests to contribute logos are welcomed in order to provide a better out-of-the-box experience.

The logo mask file should be:

* square
* at least 120px, but no more than 480px
* in PNG format
* with transparent background
* named with lowercase alphanumeric characters only
* match the Distro ID of the [`distro`](https://distro.readthedocs.io/en/latest/#distro.id) module (if the logo is for a distro)

Please also note any applicable trademarks (or similar) in the `logo/ATTRIBUTION` file, in alphabetical order.

Note: by default, pure white pixels (`#ffffff`) are masked out. This behavior can be overridden with the `--mask-show-white` flag. Transparent pixels (alpha 255) are always masked out.

## License

All content outside of the `logo` directory is licensed according to the LICENSE file in this repository.

Please refer to the ATTRIBUTION file inside the `logo` directory for image attribution.
