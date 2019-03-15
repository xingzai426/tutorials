# Steps for install the [ZCM](http://zerocm.github.io/zcm/) on Ubuntu 16.04

1. Prepare python-pip
    ```bash
    sudo apt-get install python-pip # if pip not installed
    sudo easy_install pip # if not upgraded to newer version than default, which is needed by ZCM.
    ```
1. Download the official tarball from [master branch](https://github.com/ZeroCM/zcm/tarball/master) or specific version from [github](https://github.com/ZeroCM/zcm).
1. Extract it and install the dependencies automatically
    ```bash
    $ tar -xzf ZeroCM-zcm-<hash>.tar.gz # you got to substitute the <hash>
    $ cd ZeroCM-zcm-<hash>
    $ sudo ./scripts install-deps.sh # grab yourself a cup of coffee, because this may cost a while, and if you meet an error with pip, try `sudo easy_install pip` again.
    ```
1. Configure environment
    ```bash
    $ ./waf configure --use-all 
    ```
1. it may ask for a setting of JAVA_HOME environment variable, try to add this to your `~/.bashrc` and then source it:
    ```bash
    export JAVA_HOME=/usr/bin
    export PATH=$JAVA_HOME/bin:$PATH
    ```
1. run `./waf build`, and you should see the notice "'build' finished successfully". Then run `sudo ./waf install` and you are fine.

After installation, commonly you can find your library in `/usr/local/lib/libzcm.so` and headers in `/usr/local/include/zcm/`. Use `-lzcm` with g++, `include_directories(...)` and `target_link_libraries(target zcm)` in CMake.

    

    
    
