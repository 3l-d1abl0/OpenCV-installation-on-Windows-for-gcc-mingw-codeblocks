<h2>OpenCV installation on Windows for gcc/mingw/codeblocks</h2>

<b>1.</b> Firstly, we need to install 64bit Mingw as code blocks by Default installs 32bit.
 install it to C:\your_path\mingw64\

<b>2.</b> Add the path C:\your_path\mingw64\bin\ to environment variable path.

<b>3.</b> Install CMake to C:\your_path\CMake\.
	Again add the path C:\your_path\CMake\bin\ to environment variable path.

<b>4.</b> Extract opencv (any version :D ) to C:\your_path\opencv\
	You will see to folders Builds and Sources.
 Or if you have download it from Github or version<4.3,
 there will be only one folder. Dont worry the just the Sources.

 <b>5.</b> Now Open CMake:
  a) Where is the source code: Choose the sources folder in opencv.
  b) Where to build the binaries:  C:\your_path\foo
  c) Click on Configure-> choose Specify native Compilers->
  		i> 	Choose gcc from C:\your_path\mingw64\bin\ for C.
  		ii> Choose g++ from C:\your_path\mingw64\bin\ for C++

 <b>6.</b> Once the Configuring is done you could see Name-Value things colured in 'Red' below the Search Bar . Make sure you have checked 'Grouped'. Image: <a href="https://raw.githubusercontent.com/3l-d1abl0/OpenCV-installation-on-Windows-for-gcc-mingw-codeblocks/master/cmake.png"target="_blank">cmake.png</a>

 <b>7.</b> Now Click on BUILD. Check BUILD_EXAMPLES and BUILD_PACKAGE.
 <b>8.</b> Click on CMAKE. Type ‘foo’ in the CMAKE_BUILD_TYPE.
 <b>9.</b> Go to INSTALL. Check on INSTALL_C_EXAMPLES and INSTALL_PYTHON_EXAMPLES.

 <b>10.</b> Now Click on GENERATE.


 <b>11.</b> When its Complete,u r done with CMake close it and open folder foo. Shift+ Left Mouse Click anywhere inside and select ‘Open command window here’. Image: <a href="https://raw.githubusercontent.com/3l-d1abl0/OpenCV-installation-on-Windows-for-gcc-mingw-codeblocks/master/after_genrate.png"target="_blank">after_genrate.png</a>

 <b>12.</b>type “mingw32-make” on the terminal. Believe me it'll take a Hell Lot of time. You can Probably take a power nap. Enjoy ;)

 <b>13.</b> Now when you are awake type “mingw32-make install”. It won't take much time, no need for power Nap.

 <b>14.</b> After it is done. you couls see an new folder 'install' in the folder foo.	Image: <a href="https://raw.githubusercontent.com/3l-d1abl0/OpenCV-installation-on-Windows-for-gcc-mingw-codeblocks/master/after_install.png"target="_blank">after_install.png</a>

 <b>15.</b> That 'install' folder should contain folder include and X64 which contains files for MinGw.

 <b>16.</b> Now Open Code Blocks.
 	a. Setting -> Compiler -> Toolchain : Choose the installed minGw\bun path. and choose the corresponding exe from there.
 		(so that any c/cpp program will be run by 64bit gcc and g++)
 		Image: <a href="https://raw.githubusercontent.com/3l-d1abl0/OpenCV-installation-on-Windows-for-gcc-mingw-codeblocks/master/cb_toolchain.png"target="_blank">cb_toolchain.png</a>

 	b. Setting -> Compiler -> Search Directories -> Compiler:	Add
 		C:\your_path\foo\install\include
		C:\your_path\foo\install\include\opencv
		C:\your_path\foo\install\include\opencv2
		Image: <a href="https://raw.githubusercontent.com/3l-d1abl0/OpenCV-installation-on-Windows-for-gcc-mingw-codeblocks/master/search_directories.png"target="_blank">search_directories.png</a>

	c. Setting -> Compiler -> Search Directories -> Compiler:	Add
		C:\your_path\foo\install\x64\mingw\lib
		Image: <a href="https://raw.githubusercontent.com/3l-d1abl0/OpenCV-installation-on-Windows-for-gcc-mingw-codeblocks/master/Linker.png"target="_blank">Linker.png</a>

	d. Setting -> Compiler -> Linker Settings : Add
		Add all .dll.a files from C:\your_path\foo\install\x64\mingw\lib
		Image: <a href="https://raw.githubusercontent.com/3l-d1abl0/OpenCV-installation-on-Windows-for-gcc-mingw-codeblocks/master/lsetting.png"target="_blank">lsetting.png</a>

<b>17.</b> Lastly add C:\your_path\foo\install\x64\mingw\bin to ur Environment Variable path.

Now You are Done and Everyting Should Work fine !


<b>Sameer Barha (El_Diablo)</b>