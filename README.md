# lv_sim_tpl
- ### 1、资源下载：
	- [lv_port_pc_eclipse](https://github.com/lvgl/lv_port_pc_eclipse/tree/release/v8.2)：LVGL PC模拟器
	- [lvgl](https://github.com/lvgl/lvgl.git)：LVGL源码
	- [lv_drivers](https://github.com/lvgl/lv_drivers.git)：LVGL驱动源码
	- [lv_fs_if](https://github.com/lvgl/lv_fs_if.git)：LVGL文件系统源码
	- [SDL](https://github.com/libsdl-org/SDL/releases/tag/release-2.26.4)：PC模拟器驱动
- ### 2、工程模板搭建
	- ①：打开QT，创建一个C语言版本的`Non-Qt Project`。
	- ②：将下载到的`lv_port_pc_eclipse`源码中的`lv_conf.h`、`lv_drv_conf.h`、`main.c`、`mouse_cursor_icon.c`拷贝到项目文件夹中，其中`main.c`会将项目中的同名文件替换掉；
	- ③：再LVGL仓库中下载想要使用的LVGL版本源码，这里下载的是8.0.1版本，将`lvgl-8.0.1`拷贝到项目文件夹下，并修改其名称为`lvgl`；
	- ④：相同的方式对`lv_drives`和`lv_fs_if`源码进行操作；
	- ⑤：将`SDL2-devel-2.26.4-mingw.zip\SDL2-2.26.4\x86_64-w64-mingw32`文件夹下的`lib`文件夹拷贝到项目文件夹下，同时进入`include`文件夹，将`SDL2`文件夹拷贝到项目文件夹下；
	- ⑥：将`SDL2-devel-2.26.4-mingw.zip\SDL2-2.26.4\x86_64-w64-mingw32\bin`中的`SDL2.dll`文件发到文件夹中备用，当项目构建完成后需要将其与应用程序放在同一路径下；
	- ⑦：双击`.pro`文件，打开项目；
	- ⑧：右击项目，点击`Add Existing Directory`,使用筛选器筛选`*.c;*.h`文件，点击`OK`完成外部文件导入，导入完成后打开`.pro`文件，加入`LIBS += -L$$PWD/lib/ -lmingw32 -lSDL2main -lSDL2`；
	- ⑨：将`mian.c`中`#include "lvgl/demos/lv_demos.h"`与`lv_demo_widgets();`代码注释掉，随便使用某一个例程eg`lv_example_switch_1();`，点击构建，构建完成后将`SDL2.dll`拷贝到`debug`文件夹，点击运行即可看到运行结果。
  
-
