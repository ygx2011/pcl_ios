Point Cloud Library Sample for XCode 8
======================================

This is a complete XCode project for running the [Point Cloud Library](http://pointclouds.org/) in XCode 8. My intention is to get to a running app as quickly as possible.

To run, clone this repository and do the following:

- Install boost and have the headers available in `/usr/local/include`. I use Homebrew: `brew install boost`
- unzip the framework binaries (they are zipped to get around the 100Mb file limitation of github):
 - `frameworks/pcl.framework/pcl.zip -> frameworks/pcl.framework/pcl`
 - `frameworks/vtk.framework/vtk.zip -> frameworks/vtk.framework/vtk`

Open HelloPCL.xcodeproj in XCode 8. Choose "iOS Device" or the name of your attached device as target, then Compile or Run it.



##### PERSO , HOW TO CONFIGURE XCODE FOR PCL ####
In build phase setting : Need kiwi.framework, pcl.framework, vtk.framework
these framework need to be in a folder 'framework'
In build setting : 
1. add user-defined setting
frameworks_dir   --> value : ./frameworks
2. Framework search paths :
$(inherited)
$(frameworks_dir)
$(PROJECT_DIR)/frameworks

3. Header search paths :
$(frameworks_dir)/kiwi.framework/Headers/eigen
$(frameworks_dir)/kiwi.framework/Headers
$(frameworks_dir)/vtk.framework/Headers
$(frameworks_dir)/pcl.framework/Headers
/usr/local/Cellar/boost/1.60.0_2/include/

4. Library search path
/usr/local/lib

5. Always search user paths 
No
