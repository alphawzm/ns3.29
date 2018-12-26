# ns3.29
ns3.29, Ubuntu18

# Error
### visualizer模块
依赖PythonBinding，NS3中的PythonBinding由pybindgen完成，但是pybindgen工具在ns-allinone-3.xx目录下，而不是在ns-3.xx目录下，如果移动了ns-3.xx的目录，就无法定位pybindgen进而完成PythonBinding

解决方法：

重新配置和编译NS-3，配置行用 --with-pybindgen加上pybindgen所在目录：

#### sudo ./waf -d debug --enable-examples --enable-tests configure --with-pybindgen=/home/ubuntu18ns3/ns-allinone-3.29/pybindgen-0.17.0.post58+ngcf00cc0/

sudo ./waf

### --vis报错：

NS3/src/visualizer/visualizer/core.py中'gi.repository.GooCanvas' object has no attribute 'LineDash'

解决办法：

将src/visualizer/visualizer/core.py中的

line_dash=GooCanvas.LineDash([10.0, 10.0 ])

更改为

#### line_dash=GooCanvas.CanvasLineDash.newv([10.0, 10.0 ])
--------------------- 
作者：ReonLeon 
来源：CSDN 
原文：https://blog.csdn.net/qq_22634949/article/details/83543311 
版权声明：本文为博主原创文章，转载请附上博文链接！
