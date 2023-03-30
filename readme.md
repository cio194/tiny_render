## 介绍

参考 [GitHub - ssloy/tinyrenderer: A brief computer graphics / rendering course](https://github.com/ssloy/tinyrenderer) 实现的软光栅化渲染器，支持相机移动、多光源设置、纹理贴图等。

渲染核心步骤为：

* 顶点着色器：模型变换、观察变换、投影变换；

* 裁剪 + 屏幕映射（透视投影）；

* 光栅化：三角形遍历（包围盒模型） + 片元着色 + 深度缓冲（z-buffer算法），其中片元着色实现了纹理贴图、blinn phone光照模型，利用透视矫正插值保证了插值正确性。

## 构建 & 运行

windows（mingw）:

* ```cmake -G "MinGW Makefiles" -B build```
* ```cmake --build build```

可执行文件（简单测试）位于 ztest/static/exe 文件夹下

执行时，通过命令行参数指定 obj files