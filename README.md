## How to intall Discovery Studio Visualizer on Manjaro Linux

## 1. Overview  

Discovery Studio Visualizer (DSV) is a free BIOVIA’s comprehensive predictive science application for the Life Sciences.  
DSV can be downloaded it from [here.](http://accelrys.com/products/collaborative-science/biovia-discovery-studio/visualization-download.php)  



## 2. Required packages
For Linux installations, certain system libraries may be required for the correct operation of DSV.  

### 2.1. Packages in Manjaro repositories
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
sudo pacman -Syu
sudo pacman -S audit lib32-alsa-lib lib32-e2fsprogs lib32-expat lib32-glibc lib32-keyutils lib32-krb5 lib32-gcc-libs lib32-libice lib32-libcap lib32-libsm lib32-libstdc++5 lib32-libx11 lib32-libxau lib32-libxdmcp lib32-libxext lib32-libxi lib32-libxmu libxpm lib32-libxrender lib32-libxtst lib32-pam lib32-cairo lib32-fontconfig lib32-glib2 lib32-bzip2 lib32-freetype2 lib32-libjpeg-turbo lib32-libtiff lib32-zlib lib32-libdrm lib32-libxdamage lib32-libxfixes lib32-libxxf86vm lib32-libxinerama tcsh bc --needed

```

The `--needed` option will skip the already installed package in your system.  



### 2.2. Packages in Arch repository

DSV requires additional packages that are not find in Manjaro repos. To solve this, we will use **yaourt**:

#### 2.2.1. Install yaourt package using

```
sudo pacman -S yaourt
```



#### 2.2.2. Now install required package:

```
yaourt -S lib32-libxpm gstreamer0.10 gstreamer0.10-base gstreamer0.10-base-plugins gstreamer0.10-good gstreamer0.10-good-plugins

```
## 3. DSV installation
Once you installed all the required libraries.  Fill the information in the [**BIOVA webpage**](http://accelrys.com/products/collaborative-science/biovia-discovery-studio/visualization-download.php). You'll receive an email to download the DSV binary (Let's call it **_DS2017R2Client.bin_** in this tutorial)
### 3.1. Make the binary executable
```
chmod +x DS2017R2Client.bin
```
### 3.2. Run the installer
```
./DS2017R2Client.bin
```
You have to select the place in your system for the BIOVIA folder. (Default is **$HOME**). Inside of it, the installer will create two additional folders for the program and the license, called **DiscoveryStudio2017RC** and **LicensePack**, respectively.

### 3.3. Setting DSV
We will get an error message if we try to run the application using the DSV Desktop Launcher. This system error is related to libpng16 library which need a higher version of libz.so.1 that is installed in BIOVIA folder. So, we are going to use libz installed in our Manjaro system. To do this, two steps are required:  


#### 3.3.1. Backup libz files
Go to **${HOME}/BIOVIA/DiscoveryStudio2017R2/lib** folder and change the name of the libz files:

```
mv libz.so bk_libz.so
mv libz.so.1 bk_libz.so.1

```
#### 3.3.2. Create a symbolic link
Staying in the **${HOME}/BIOVIA/DiscoveryStudio2017R2/lib** folder type:

```
sudo ln -s /usr/lib/libz.so ${PWD}/libz.so
sudo ln -s /usr/lib/libz.so.1 ${PWD}/libz.so.1

```

Now launch the application again.  

**_Don't forget to cross your fingers in the process!!_**
