# Install YCM
Install the vim plug "YouCompleteMe".
*   For Msys2
    *   Install YCM  
            Install vim use ```pacman -S vim``` command.  
            Install vim plug from this repo https://github.com/junegunn/vim-plug.   
            Config vimrc and go to vim commandline mode type ```PlugInstall``` to install YCM.  
            Mabye with some errors, so you should go to the directory "~/.vim/plugged/YouCompleteMe" and run command
            ```git submodule update --init --recursive``` to get fully install.  
            
    *   Install Dependencies  
        Open UCRT64 terminal and run following commands: 
        <pre>
            pacman -S ucrt64/mingw-w64-ucrt-x86_64-python
            ...                                   -gcc
            ...                                   -clang
            ...                                   -make
            ...                                   -cmake
        <pre>
            
    *   Compile YCM  
            Go to the YCM fold "~/.vim/plugged/YouCompleteMe", create a new directory like "build" with ```mkdir build```.  
            then, run following command to compile ycm:
            <pre>
                cmake -G "MSYS Makefiles" -DUSE_SYSTEM_LIBCLANG=ON -DCMAKE_IGNORE_PATH=D:/msys64/usr/lib 
                -DCMAKE_MAKE_PROGRAM=/ucrt64/bin/mingw32-make.exe . ~/.vim/plugged/YouCompleteMe/third_party/ycmd/cpp/
            </pre>
            next, compile ycm_core with command ```mingw32-make.exe ycm_core```.
            
        ![compile ycm_core](https://github.com/Jokia/install_YCM/blob/main/raw/msys2_1_0.png)
            
    *   Fix Problems  
        Unable to load python: ```pacman -S msys/python```.  
        No module named watchdog:
           ```pacman -S ucrt64/mingw-w64-ucrt-x86_64-python-pip```
           ```pip install watchdog```.  
