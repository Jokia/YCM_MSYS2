# Install YCM for MSYS2  

Open MSYS terminal.  

Install Vim: ```pacman -S vim```  

Install vim-plug: https://github.com/junegunn/vim-plug.  

Edit .vimrc and open vim, type ```:PlugInstall``` to install YCM. If there are some errors, try to go to the directory "~/.vim/plugged/YouCompleteMe" and run command: 
```git submodule update --init --recursive``` to install entirely.  

Install dependencies:    
   <pre>
      pacman -S python
      ...       gcc
      ...       clang
      ...       make
      ...       cmake
      ...       python-pip
      
      pip install watchdog  
   </pre>
            
Compile YCM:  
   ```cd ~/.vim/plugged/YouCompleteMe``` & ```mkdir build```.  
   
   next, input following command:
   <pre>
      cmake -DUSE_SYSTEM_LIBCLANG=ON -DCMAKE_MAKE_PROGRAM=/bin/make.exe . ~/.vim/plugged/YouCompleteMe/third_party/ycmd/cpp/
   </pre>
   
   finally, compile ycm_core with command: ```make ycm_core```.
   
   ![compile ycm_core](https://github.com/Jokia/install_YCM/blob/main/raw/msys2_ycm.png)
