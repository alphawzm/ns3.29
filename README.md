# ns3.29
ns3.29, Ubuntu18

# Error
visualizer模块依赖PythonBinding，NS3中的PythonBinding由pybindgen完成，但是pybindgen工具在ns-allinone-3.xx目录下，而不是在ns-3.xx目录下，如果移动了ns-3.xx的目录，就无法定位pybindgen进而完成PythonBinding

解决方法：

重新配置和编译NS-3，配置行用 --with-pybindgen加上pybindgen所在目录：

sudo ./waf -d debug --enable-examples --enable-tests configure --with-pybindgen=/home/ubuntu18ns3/ns-allinone-3.29/pybindgen-0.17.0.post58+ngcf00cc0/

sudo ./waf
