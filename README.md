## SLADE  
It's a Doom Editor

### About

SLADE3 is a modern editor for Doom-engine based games and source ports. It has the ability to view, modify, and write many different game-specific formats, and even convert between some of them, or from/to other generic formats such as [PNG](http://doomwiki.org/wiki/PNG).

SLADE3 can be considered a successor to both [SLumpEd](http://doomwiki.org/wiki/SLumpEd) and [SLADE](http://doomwiki.org/wiki/SLADE) - it combines the [features](https://github.com/sirjuddington/SLADE/wiki/Features) of both, to create an all-in-one editor. Why does it keep the name of what was previously just a map editor? Because it fits :)

### Features

Here is a brief list of features implemented in the current version of SLADE:

**Basic archive/resource editing**  
All the basic resource management features you'd expect: Create/Open/Save archives, import/export, ordering, rename, etc.

**Simple tabbed interface**  
Open multiple archives at once and switch between them easily via tabs. This enables simple copy/paste from one archive to another, among many other benefits.

**Many supported game formats**  
In addition to full Doom [WAD](http://doomwiki.org/wiki/WAD) and [ZIP/PK3](http://doomwiki.org/wiki/PK3) support, many other game formats are supported, including:
* Quake PAK/WAD2 and HUD image format
* Build GRP and ART format images
* Shadowcaster DAT/LIB along with most of its image formats
* Amulets & Armor RES, MipImage and UI gfx
* [Many more](https://github.com/sirjuddington/SLADE/wiki/Supported-Data-Formats)

**Advanced text editor**  
The SLADE3 text editor can recognise many text based languages, and provide syntax hilighting, function calltips and autocomplete for them. It also has a bunch of other useful text editing features such as autoindent and find / replace.

**Graphic conversion**  
All supported graphic formats can be converted to PNG/DoomGfx/DoomFlat and more, with an advanced graphic conversion dialog that provides conversion options and previews.

**Texture editing**  
Edit Doom composite textures (TEXTUREx) with the easy-to-use SLADE3 texture editor. Also fully supports ZDoom's enhanced composite texture format (TEXTURES).

### Building on linux
http://slade.mancubus.net/index.php?page=wiki&wikipage=Ubuntu-Step-by-Step-Compilation

This section will detail how to compile SLADE in Ubuntu (and probably anything else using apt-get, like Debian). This method has been tested on a fresh install of Ubuntu 15.04 and should work fine.

Step 1: Download and install the required libraries and tools
First things first, we'll need to install all the libraries and tools required by SLADE and wxWidgets. Open a terminal window and type the following line:


```
sudo apt install -y build-essential  libgtk2.0-dev libglew-dev libfreeimage-dev libftgl-dev libfluidsynth-dev libsfml-dev libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev libgconf2-dev freeglut3-dev cmake libmodplug-dev git libwebkit2gtk-4.1-dev libwxgtk3.0-gtk3-dev libwxgtk-media3.0-gtk3-dev libcurl4-openssl-dev libwxgtk-webview3.0-gtk3-dev libbz2-dev liblua5*-dev libmpg123-dev
```



If any of the above libraries can't be found, try running apt-cache search -n <libname>, as the library name may have changed or updated since this was written.

Step 2: Download SLADE sources from the GitHub repository
The next step is to download the SLADE sources from GitHub. First up, open Terminal and cd to some directory (or you can just use home if you want). Then enter the following line:


```
git clone https://github.com/sirjuddington/SLADE.git slade
```

This should download the SLADE sources and put them in the slade directory.

Optional Step - Switch to the stable branch
By default you will be on the master branch. As it is the 'in development' branch, it will include more cutting-edge features and improvements at the potential cost of stability.

If you would rather stick with the latest stable release of SLADE, enter the following command:


```
git checkout stable
```

This will switch over to the stable branch and sources.

Step 3: Compile SLADE
Finally, enter the following commands to compile SLADE (using CMake):


```
cd slade/dist
cmake .. -DUSE_WEBKIT_STARTPAGE=ON
make -jn
```

To speed up compilation if you have a multi-core processor, add -j X after make where X is the number of cores your CPU has, 'jn' arg will use all cores.

And that should be it, you should now be able to run SLADE by entering ./slade in the terminal window (from the SLADE directory).

If you wish to help support SLADE development, feel free to make a small [donation](https://www.paypal.me/sirjuddington), though by no means is this a requirement for continued development. I work on SLADE in my free time as a hobby project and generally enjoy it, which is enough for me.

Additionally, any help on the coding side of things is greatly appreciated - take a look at the list of [issues](https://github.com/sirjuddington/SLADE/issues), and feel free to submit a [pull request](https://github.com/sirjuddington/SLADE/pulls).
