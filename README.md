# AssetsSo
![1](https://raw.githubusercontent.com/scimence/AssetsSo/master/pics/app_install_fail.png)
AssetsSo （so库动态加载示例。从asset目录加载so库，安装时不导出so库，不会导致安装失败）


------------------------------------------------
1、将AssetsSo.jar添加至项目的lib目录下： 

2、剪切so对应的目录至assets/so/目录下

3、设置Application为sc.tool.so.AssetsSoApp

------------------------------------------------

/**
 * AssetsSoApp用于so文件运行时动态加载，加载目录为assets/so/
 * 
 * 用法：
 * 
 * 1、将原来libs/目录下的  armeabi、x86、 armeabi-v7a...，直接剪切至assets/so/目录下即可。
 * 2、将AndroidManifest.xml中的application设置为：  <application android:name="sc.tool.so.AssetsSoApp">;
 * 或者 调用 AssetsSoApp.LoadAssetsSo(this);
 * 
 * 注解： lib/目录下的so文件，在应用安装时就会输出，时常会报错导致应用无法正常安装。
 * ｛
 * 如：
 * 1、Google Play Store – Can’t install app (Error code: -504)
 * 2、is not page-aligned - will not be able to open it directly from apk
 * 3、Failure [INSTALL_FAILED_INVALID_APK: Failed to extract native libraries, res=-2] 
 * （此报错修改 aplication属性可以为 android:extractNativeLibs="true"编译的apk可正常运行，可从google play下载却无法安装，还是报第2个错误，
 * 干脆修改为so动态加载，就不会报错了，也可正常安装、运行）
 * ｝
 * 
 * 修复原理： so不添加至lib目录，不在应用安装时输出，正常安装。应用运行时，输出对应类型的so库，从该目录下动态加载
 * 
 * @author scimence@163.com
 */
 
 ![1](https://raw.githubusercontent.com/scimence/AssetsSo/master/pics/install_lib.png)
 ![1](https://raw.githubusercontent.com/scimence/AssetsSo/master/pics/user_lib.png)
 
 
 AssetsSo.jar（so动态载入库）: 
 https://raw.githubusercontent.com/scimence/AssetsSo/master/AssetsSo.jar
 
 AssetsSo.zip（源码）: 
 https://raw.githubusercontent.com/scimence/AssetsSo/master/AssetsSo.zip
 
 
