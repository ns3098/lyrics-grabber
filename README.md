# <img src="/docs/icon/icon.png?raw=true" height="48"> Quaver - Lyrics Finder
An app to find lyrics and save them to your song's metadata. Available on macOS and Windows.

[Download now!](https://github.com/cheeseisdisgusting/lyric-grabber/releases)

## Features

### Quickly find lyrics.
Quaver is multithreaded, using Qt5's QThread and Python's ThreadPoolExecutor with concurrent.futures. Depending on network speed, this means that Quaver can get lyrics for up to 100 songs in less than fifteen seconds!

<img src="/docs/screenshots/mac/list.png?raw=true" style="margin: 5px">
<img src="/docs/screenshots/mac/list_dark.png?raw=true" style="margin: 5px">

### Quickly add files.
Quaver supports over a dozen formats, including popular audio formats such as .mp3, .m4a, .flac, and more. Add files by drag and drop, selecting a file or folder in the submenu, or right-clicking a file in Finder or Windows Explorer.

<img src="/docs/screenshots/mac/empty_dark.png?raw=true" style="margin: 5px">

### Quickly correct lyrics.
Lyrics have a typo? Got something completely off base? Edit lyrics with the detail pane. With options to modify the source, which artist/title to search for, or just supplying a URL, incorrect lyrics can be fixed in a jiffy.

<img src="/docs/screenshots/windows/lyrics.png?raw=true" height="300" style="margin: 5px"> <img src="/docs/screenshots/windows/metadata.png?raw=true" height="300" style="margin: 5px">

### Quintessential power features.
Customize where the lyrics source, adding a song title, or even whether to enable sound effects. And, of course, keyboard shortcuts: song navigation, file addition, and settings are all accessible with both hands on keyboard. Power to the user.

<img src="/docs/screenshots/mac/lyrics.png?raw=true" height="350" style="margin: 5px"> <img src="/docs/screenshots/mac/settings.png?raw=true" height="350" style="margin: 5px">

### Quality updates.
Whenever an update's available, a notification will pop up as the app is opened. Or, since impatience is also a thing, manual checks can be triggered through the about screen. Conveniently packaged in a .msi installer, or portable .exe for Windows, and .app or .dmg for macOS.

<img src="/docs/screenshots/mac/about.png?raw=true" height="300" style="margin: 5px">

## Build and run

You'll need Python 3.5+.

### macOS

1. In your virtual environment of choice, run ```pip install -r requirements.txt``` from the root of the repository.
2. To generate the app bundle, ```cd src``` then ```pyinstaller quaver-onefile.spec```. The app bundle will appear in the ```dist``` folder generated by PyInstaller.
3. The app bundle will not have a complete Info.plist. A complete version is at the root of ```src```, so copy it into the application bundle. In src, ```cp Info.plist dist/Quaver.app/Contents```
4. The program expects to find a configuration file in the `/Resources/` folder in the macOS bundle. So, run ```cp modules/settings.ini dist/Quaver.app/Contents/Resources/```
5. The application bundle is now complete; drag into Applications. Voilà!

[OPTIONAL]
To generate the .dmg for distribution, you will need Node.js and create-dmg installed. If you do not have create-dmg installed, get it with ```npm install --global create-dmg```.

Then, switch into the distribution folder (```cd dist```), and create the dmg. ```create-dmg 'Quaver.app'```

### Windows
1. In your virtual environment of choice, run ```pip install -r requirements.txt``` from the root of the repository.
2. To generate the executable, ```cd src``` then ```pyinstaller quaver-onefile.spec```. The executable will appear in the ```dist``` folder generated by PyInstaller.
3. Voilà!

Unfortunately, generating an .msi requires more configuration than could be adequately explained in a README. See [this post](https://blog.aaronhktan.com/posts/2018/06/16/open-with-in-macos-windows-ubuntu#windows) and [this post](https://blog.aaronhktan.com/posts/2018/05/14/pyqt5-pyinstaller-executable#32-creating-a-msi-file-for-windows) for more details.

### Ubuntu

1. In your virtual environment of choice, run ```pip install -r requirements.txt``` from the root of the repository.
2. To generate the executable, ```cd src``` then ```pyinstaller quaver-onefile.spec```. The executable will appear in the ```dist``` folder generated by PyInstaller.
3. Voilà!

[OPTIONAL]
To generate the .deb for distribution, see [this post](https://blog.aaronhktan.com/posts/2018/05/14/pyqt5-pyinstaller-executable#33-creating-a-deb-file-for-ubuntu) for more information. It contains all the files and folder structure necessary.

## Contributing

If you're good at Python, this project probably needs you!

- There's a different branch for each operating system. Until changes have been tested on macOS, Windows, and Ubuntu, these branches are not merged into master.
- Fork and make a pull request!