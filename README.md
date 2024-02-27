# Install YCM
Install the vim plug "YouCompleteMe".
*   For Msys2
    *   Install YCM  
            Install vim:
               ```pacman -S vim```.  
            Install vim-plug:
               https://github.com/junegunn/vim-plug.   
            Config vimrc and go to vim commandline mode type ```PlugInstall``` to install YCM.  
            If there are some errors, try to go to the directory "~/.vim/plugged/YouCompleteMe" and run command
            ```git submodule update --init --recursive``` to get entire installing.  
            
    *   Install Dependencies  
        Open Msys terminal and run following commands: 
        <pre>
            pacman -S python
            ...       gcc
            ...       clang
            ...       make
            ...       cmake
        <pre>
            
    *   Compile YCM  
            ```cd ~/.vim/plugged/YouCompleteMe``` & ```mkdir build```.  
            then, input follow command:
            <pre>
               cmake -DUSE_SYSTEM_LIBCLANG=ON -DCMAKE_MAKE_PROGRAM=/bin/make.exe . ~/.vim/plugged/YouCompleteMe/third_party/ycmd/cpp/
            </pre>
            finally, compile ycm_core with command ```make ycm_core```.
            
        ![compile ycm_core](https://github.com/Jokia/install_YCM/blob/main/raw/msys2_ycm.png)
            
    *   Fix Problems  
        *    Unable to load python: ```pacman -S msys/python```.
        
        *    No module named watchdog:  
            install pip: ```pacman -S python-pip```  
            install watchdog via pip: ```pip install watchdog```.  
