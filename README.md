# How to intall Discovery Studio Visualizer on Manjaro Linux

## Overview  

[Discovery Studio Visualizer (DSV) is a free BIOVIA’s comprehensive predictive science application for the Life Sciences.  
DSV can be downloaded it from [here.](http://accelrys.com/products/collaborative-science/biovia-discovery-studio/visualization-download.php)  



## Required packages 
For Linux installations, certain system libraries may be required for the correct operation of DSV.  

### Packages in Manajaro repositories
* alsa-lib (i686)
* e2fsprogs-libs (i686)
* expat (i686)
* glibc (i686)
* keyutils-libs (i686)
* krb5-libs (i686)
* libgcc (i686)
* libICE (i686)
* libpcap (i686)
* libSM (i686)
* libstdc++ (i686)
* libX11 (i686)
* libXau (i686)
* libXdmcp (i686)
* libXext (i686)
* libXi (i686)
* libXmu (i686)
* libXpm (x86_64)
* libXrender (i686)
* libXt (i686)
* libXtst (i686)
* pam (i686)
* cairo (i686)
* fontconfig (i686)
* glib2 (i686)
* bzip2-libs (i686)
* freetype (i686)
* libjpeg-turbo (i686)
* libtiff (i686)
* zlib (i686)
* libdrm (i686)
* libXdamage (i686)
* libXfixes (i686)
* libXxf86vm (i686)
* libXinerama (i686)
* tcsh
* bc 

All these package can be installed by using the next command line:

```
sudo pacman -S audit lib32-alsa-lib lib32-e2fsprogs lib32-expat lib32-glibc lib32-keyutils lib32-krb5 lib32-gcc-libs lib32-libice lib32-libcap lib32-libsm lib32-libstdc++5 lib32-libx11 lib32-libxau lib32-libxdmcp lib32-libxext lib32-libxi lib32-libxmu libxpm lib32-libxrender lib32-libxtst lib32-pam lib32-cairo lib32-fontconfig lib32-glib2 lib32-bzip2 lib32-freetype2 lib32-libjpeg-turbo lib32-libtiff lib32-zlib lib32-libdrm lib32-libxdamage lib32-libxfixes lib32-libxxf86vm lib32-libxinerama tcsh bc --needed

```

The `--needed` option will skip the already installed package in your system.  


### Packages in Arch repository

DSV requires additional packages that are not find in Manjaro repos. To solve this, we will use **yaourt**:

1. Install yaourt package using
```
sudo pacman -S yaourt 
```
2. Now install requiered package:

```
yaourt -S lib32-libxpm 

```

