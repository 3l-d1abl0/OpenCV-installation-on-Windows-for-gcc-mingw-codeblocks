<h2>OpenCV installation on Windows for gcc/mingw/codeblocks</h2>

<b>1.</b> Firstly, we need to install 64bit Mingw as code blocks by Default installs 32bit.
 install it to C:\your_path\mingw64\

2. Add the path C:\your_path\mingw64\bin\ to environment variable path.

3. Install CMake to C:\your_path\CMake\.
	Again add the path C:\your_path\CMake\bin\ to environment variable path.

4. Extract opencv (any version :D ) to C:\your_path\opencv\
	You will see to folders Builds and Sources.
 Or if you have download it from Github or version<4.3,
 there will be only one folder. Dont worry just the Sources.

 5. Now Open CMake:
  a) Where is the source code: Choose the sources folder in opencv.
  b) Where to build the binaries:  C:\your_path\foo
  c) Click on Configure-> choose Specify native Compilers->
  		i> 	Choose gcc from C:\your_path\mingw64\bin\ for C.
  		ii> Choose g++ from C:\your_path\mingw64\bin\ for C++

 6. Once the Configuring is done you could see Name-Value things colured in 'Red' below the Search Bar . Make sure you have checked 'Grouped'. Image: cmake.png

 7.Now Click on BUILD. Check BUILD_EXAMPLES and BUILD_PACKAGE.
 8.Click on CMAKE. Type ‘foo’ in the CMAKE_BUILD_TYPE.
 9.Go to INSTALL. Check on INSTALL_C_EXAMPLES and INSTALL_PYTHON_EXAMPLES.

 10. Now Click on GENERATE.


 11. When its Complete,u r done with CMake close it and open folder foo. Shift+ Left Mouse Click anywhere inside and select ‘Open command window here’. Image: after_genrate.png

 12.type “mingw32-make” on the terminal. Believe me it'll take a Hell Lot of time. You can Probably take a power nap. Enjoy ;)

 13.Now when you are awake type “mingw32-make install”. It won't take much time, no need for power Nap.

 14. After it is done. you couls see an new folder 'install' in the folder foo.	Image: after_install.png

 15.that 'install' folder should contain folder include and X64 which contains files for MinGw.

 16. Now Open Code Blocks.

 	a ) Setting -> Compiler -> Toolchain : Choose the installed minGw\bun path. and choose the corresponding exe from there.
 		(so that any c/cpp program will be run by 64bit gcc and g++)
 		Image: cb_toolchain.png

 	b ) Setting -> Compiler -> Search Directories -> Compiler:	Add
 		C:\your_path\foo\install\include
		C:\your_path\foo\install\include\opencv
		C:\your_path\foo\install\include\opencv2
		Image : search_directories.png

	c ) Setting -> Compiler -> Search Directories -> Compiler:	Add
		C:\your_path\foo\install\x64\mingw\lib
		Image: Linker.png

	d ) Setting -> Compiler -> Linker Settings : Add
		Add all .dll.a files from C:\your_path\foo\install\x64\mingw\lib
		Image: lsetting.png

17. Lastly add C:\your_path\foo\install\x64\mingw\bin to ur Environment Variable path.

Now You are Done Everyting Should Work fine !


Sameer Barha (El_Diablo)