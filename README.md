# Install YCM
Install the vim plug "YouCompleteMe".
*   For Msys2
    *   Install YCM  
            Install vim use ```pacman -S vim``` and vim plug from this repo https://github.com/junegunn/vim-plug.   
            Go to vim commandline mode and type ```PlugInstall``` to install YCM.  
            Mabye with some error, so you should go to the directory "~/.vim/plugged/YouCompleteMe" and run command
            ```git submodule update --init --recursive``` to fully install.  
            
    *   Install Dependencies  
        Run command in UCRT64 terminal: 
        <pre>
            pacman -S ucrt64/mingw-w64-ucrt-x86_64-python
            ...                                   -gcc
            ...                                   -clang
            ...                                   -make
            ...                                   -cmake
        <pre>
            
    *   Compile YCM  
            Go to YCM directory, create a new directory like "build" with ```mkdir build```.  
            then, run following command to compile ycm:
            <pre>
                cmake -G "MSYS Makefiles" -DUSE_SYSTEM_LIBCLANG=ON -DCMAKE_IGNORE_PATH=D:/msys64/usr/lib 
                -DCMAKE_MAKE_PROGRAM=/ucrt64/bin/mingw32-make.exe . ~/.vim/plugged/YouCompleteMe/third_party/ycmd/cpp/
            </pre>
            next, compile ycm_core with command ```mingw32-make.exe ycm_core```.
            
            ![image] (https://github.com/Jokia/install_YCM/blob/main/raw/msys2_1_0.png)
            
    *   Fix Problems  
        Unable to load python: ```pacman -S msys/python```.  
        No module named watchdog: ```pip install watchdog```.  
