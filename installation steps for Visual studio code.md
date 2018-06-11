* ### Download Mingw and install
    Link - https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe/download
    
* ### Add the bin folder into Environment variables
  Here, the directory for 'bin' folder has to be added into environment variables, so that it can be accessed from command prompt.

* ### Visual studio code
  Open and install the following extension: <br/>
  **C/C++ – IntelliSense, debugging, and code browsing for VS Code**

* ### Sample program
  Write down a sample C++ program in a file - "hello.cpp"
  
  ```c++
     #include <iostream>

     int main()
     {
        std::cout<<"Hello world"<<std::endl;
        return 0;
     }
  ```

* ### Editing configuration file
  Here, include has to be edited in the 'c_cpp_properties.json' file.
  
  So, in order to get that, here add this - <br/>
  "F:\\Softwares\\mingw-w64\\i686-8.1.0-posix-dwarf-rt_v6-rev0\\mingw32\\lib\\gcc\\i686-w64-mingw32\\8.1.0\\include\\c++"
   
   in the 'path' heading under 'browse' under 'Win32'.

* ### Create 'tasks.json' file
  Follow this steps - 
  
  	* 'Ctrl + Shift + P' for Command Palette
	* Enter 'tasks' and click on 'Tasks: Configure Task'.
	* select last option - 'Others' for C++
	* A file - 'tasks.json' is created.
