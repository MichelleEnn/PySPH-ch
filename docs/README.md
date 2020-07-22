# 欢迎使用PySPH文档！

> PySPH是用于平滑粒子流体动力学（SPH）模拟的开源框架。用户可以在纯[Python中](http://www.python.org/)实现SPH公式，但仍可获得出色的性能。PySPH可以通过OpenMP使用多个内核，也可以使用MPI无缝并行运行。

PySPH托管在[github上](http://github.com/pypr/pysph)。请参阅[github](http://github.com/pypr/pysph)网站以获取开发细节。



## 总览

### 特征

- 用户脚本和方程式是用纯Python编写的。
- 定义在粒子上运行的任意SPH方程的灵活性。
- 能够在纯Python中定义自己的多步集成器。
- 高性能：我们的性能可与FORTRAN中实现的手写求解器相媲美。
- OpenMP的无缝多核支持。
- [PyOpenCL](https://documen.tician.de/pyopencl/)支持无缝GPU 。
- Seamless parallel integration using [Zoltan](http://www.cs.sandia.gov/zoltan/).
- [BSD许可证](https://github.com/pypr/pysph/tree/master/LICENSE.txt)。

### SPH公式 

当前，PySPH有许多使用弱可压缩流体（WCSPH）方法求解粘性不可压缩的Navier-Stokes方程的示例。当前采用以下公式：

- 自由表面流动的[弱可压缩SPH（WCSPH）](http://www.tandfonline.com/doi/abs/10.1080/00221686.2010.9641250)（Gesteira等，2010，《水力研究杂志》，48，第6–27页）

  ![3D大坝突破障碍SPHERIC基准[测试2](https://wiki.manchester.ac.uk/spheric/index.php/Test2)](https://pysph.readthedocs.io/en/latest/_images/db3d.png)

- 不可压缩流体的[传输速度公式](http://dx.doi.org/10.1016/j.jcp.2013.01.043)（Adami等人，2013，JCP，241，第292-307页）。

![流线型腔](https://pysph.readthedocs.io/en/latest/_images/ldc-streamlines.png)

- [SPH用于弹性动力学](http://dx.doi.org/10.1016/S0045-7825(01)00254-7)（Gray等，2001，CMAME，第190卷，第6641–6662页）

![两个弹性环碰撞。](https://pysph.readthedocs.io/en/latest/_images/rings-collision.png)

- [可压缩SPH](http://dx.doi.org/10.1016/j.jcp.2013.08.060)（Puri等人，2014，JCP，第256卷，第308–333页）

- [广义传输速度公式（GTVF）](https://doi.org/10.1016/j.jcp.2017.02.016)（Zhang等人，2017，JCP，337，第216–232页）
- [熵阻尼人工可压缩性（EDAC）](http://dx.doi.org/10.1016/j.compfluid.2018.11.023)（Ramachandran等人，2019，计算机和流体，179，第579–594页）
- [SPH增量](http://dx.doi.org/10.1016/j.cma.2010.12.016)（Marrone等，CMAME，2011，200，第1526–1542页）
- [双重时间SPH（DTSPH）](https://arxiv.org/abs/1904.00861)（Ramachandran等人的arXiv预印本）
- [不可压缩（ISPH）](https://doi.org/10.1006/jcph.1999.6246)（Cummins等人，JCP，1999，152，第584–607页）
- [简单迭代SPH（SISPH）](https://arxiv.org/abs/1908.01762)（Muta等人arXiv预印本）
- [隐式Incompressibel SPH（IISPH）](https://doi.org/10.1109/TVCG.2013.105)（Ihmsen等人，2014年，IEEE Trans.Vis.Comput.Graph。，20，第426-435页）
- [Gudnov SPH（GSPH）](https://doi.org/10.1006/jcph.2002.7053)（Inutsuka等人，JCP，2002，179，第238–267页）
- [保守的可复制内核SPH（CRKSPH）](http://dx.doi.org/10.1016/j.jcp.2016.12.004)（Frontiere等人，JCP，2017，332，第160-209页）
- [近似古德诺夫SPH（AGSPH）](https://doi.org/10.1016/j.jcp.2014.03.055) （Puri等人，JCP，2014年，第432-458页）
- [自适应密度核估计（ADKE）](https://doi.org/10.1016/j.jcp.2005.06.016)（Sigalotti等人，JCP，2006，第124-149页）
- [Akinci](http://doi.acm.org/10.1145/2185520.2185558)（Akinci等人，ACM Trans。Graph。，2012，pp。62：1-62：8）

实施以下论文的边界条件：

- [广义Wall BC](http://dx.doi.org/10.1016/j.jcp.2012.05.005)（Adami等人，JCP，2012，第7057–7075页）
- [不做任何类型的BC出口](https://doi.org/10.1016/j.euromechflu.2012.02.002)（Federico等人，欧洲力学杂志-B /流体，2012年，第35-46页）
- [BC出口镜](http://dx.doi.org/10.1016/j.cma.2018.08.004)（Tafuni等人，CMAME，2018年，第604–624页）
- [BC的特征方法](http://dx.doi.org/10.1002/fld.1971)（Lastiwaka等人，《国际流体数值方法杂志》，2012年，第35-46页）
- 混合BC（Negi等人，arXiv预印本）

以下文件中提出的更正也是PySPH的一部分：

- [纠正了SPH](http://dx.doi.org/10.1016/S0045-7825(99)00051-1)（Bonet等人，CMAME，1999，第97-115页）
- [汞校正](https://doi.org/10.1080/00221686.2010.9641251)（Hughes等，水力研究杂志，第105–117页）
- [拉伸不稳定性校正”](https://doi.org/10.1006/jcph.2000.6439) （Monaghan JJ JCP，2000，第2990–311页）
- 粒子移位算法（[Xu等，](http://dx.doi.org/10.1016/j.jcp.2009.05.032) JCP，2009，pp。6703–6725），（[Skillen等，](http://dx.doi.org/10.1016/j.cma.2013.05.017) CMAME，2013，pp。163–173）

表面张力模型是通过以下方式实现的：

- [莫里斯表面张力](https://dx.doi.org/10.1002/1097-0363(20000615)33:3<333::AID-FLD11>3.0.CO;2-7)（Morris等人，《流体数值方法的内部杂志》，2000年，第333-353页）
- [阿达米表面](https://doi.org/10.1016/j.jcp.2010.03.022)张力公式（Adami等人，JCP，2010年，第5011至5021页）

### 鸣谢

PySPH主要由[孟买IIT航空航天工程系](http://www.aero.iitb.ac.in/)开发。我们感谢孟买IIT的支持。我们的主要目标是为应用程序和研究构建一个功能强大的基于SPH的工具。我们希望这可以使进行可重复的计算研究变得容易。

要查看贡献者列表，请参见[github贡献者页面](https://github.com/pypr/pysph/graphs/contributors)

上面未列出的一些早期开发人员是：

- Pankaj Pandey（压力求解器和改进的负载平衡，2011年）
- Chandrashekhar Kaushik（2009年最初的并行和串行实现）

### 引用PySPH

您可以使用以下文章来正式引用PySPH：

- Prabhu Ramachandran，Kunal Puri，Aditya Bhosale，A Dinesh，Abhinav Muta，Pawan Negi，Rahul Govind，Suraj Sanka，Pankaj Pandey，Chandrashekhar Kaushik，Anshuman Kumar，Ananyo Sen，Rohan Kaushik，Mrinalgouda Patils，Deep Kurtapatik，Dile ，Amal S Sebastian，Arkopal Dutt，Arpit Agarwal，“ PySPH：基于Python的平滑粒子流体动力学框架”，正在审查中（https://arxiv.org/abs/1909.04504）。

以下是较早的演示：

- Prabhu Ramachandran，*PySPH：用于平滑粒子流体动力学的可再现且高性能的框架*，在第15届Python in Science Conference中，第127-135页，2016年7月11日至17日。[链接到论文](http://conference.scipy.org/proceedings/scipy2016/prabhu_ramachandran_pysph.html)。
- Prabhu Ramachandran和Kunal Puri，*PySPH：并行粒子模拟的框架*，在第三届基于粒子方法国际会议（论文2013）上，德国斯图加特，2013年9月18日。

### 历史

- 2009年：PySPH从Prabhu编写的基于Cython的简单1D实现开始。
- 2009年至2010年：Chandrashekhar Kaushik致力于采用通用设计的完整3D SPH实施。该实现是Cython和Python的混合。
- 2010-2012年：先前的实施有点太复杂，并且很大程度上由Kunal和Pankaj进行了大修。这成为PySPH 0.9beta版本。这个版本的困难在于它几乎完全是用Cython编写的，从而使得在不编写更多Cython代码的情况下很难扩展或添加新的格式。这样做很困难，而且不太愉快。此外，它并没有我们所希望的快。最终感觉像我们可能也已经在C ++中实现了所有功能，并为此暴露了Python接口。
- 2011-2012年：Kunal还在[Cython中](https://bitbucket.org/kunalp/sph2d)实现了[SPH2D](https://bitbucket.org/kunalp/sph2d)和另一个内部版本，称为ZSPH，其中包括使用[PyZoltan的](https://github.com/pypr/pyzoltan)基于[Zoltan](http://www.cs.sandia.gov/zoltan/)的并行[化](https://github.com/pypr/pyzoltan)。这是他的博士研究所特有的，并且再次需要编写Cython，这使得普通用户很难扩展。
- 2013年至今2013年年初，Prabhu重新实现了PySPH的核心，几乎完全由纯Python自动生成。生成的代码比以前的实现更快，并且非常容易从纯Python完全扩展。Kunal和Prabhu将PyZoltan整合到PySPH中，并且当前版本的PySPH诞生了。随后，OpenMP支持也在2015年添加。

### 支持

如果您在使用PySPH时遇到任何疑问或遇到任何困难，请通过以下电子邮件将您的问题发送或发送到pysph-users邮件列表：https://groups.google.com/d/forum/pysph-users

还请查看[PySPH问题跟踪器](https://github.com/pypr/pysph/issues)。

### 变更日志

*1.0b1*

- 发布日期：仍在开发中。
- 将pyzoltan，cyarray移到pypi上自己的软件包中。

*1.0a6*

此版本已合并90个拉取请求。感谢以下对此发布做出贡献的人员（按字母顺序排列）：A Dinesh，Abhinav Muta，Aditya Bhosale，Ananyo Sen，Deep Tavker，Prabhu Ramachandran，Vikas Kurapati，nilsmeyerkit，Rahul Govind，Sanka Suraj。

- 发布日期：2018年11月26日。
- 增强功能：
  - 最初支持通过OpenCL在GPU上透明地运行PySPH。
  - 更改了用于计算自适应DT的API，现在可以在名为的粒子阵列属性中进行设置。`dt_cfl, dt_force, dt_visc`
  - 通过该`loop_all` 方法支持非成对粒子相互作用。这对于MD模拟很有用。
  - 在集成器中添加对方法的支持。`py_stage1, py_stage2 ...`
  - 添加支持`py_initialize`和`initialize_pair`方程。
  - 支持在集成的不同阶段使用不同的方程组。
  - 支持`Group`通过 `pre/post`回调参数从调用任意Python代码。
  - 传递给reduce方法。`t, dt`
  - 允许粒子阵列属性大步前进，这使我们可以定义具有多个组件的属性。例如，如果每个粒子需要3个值，则可以将步幅设置为3。
  - 如果将Mayavi Viewer保存在输出中，现在也可以显示非真实粒子。
  - 对粒子简单重新网格化的一些改进。
  - 添加简单的STL导入器以导入几何。
  - 允许用户指定openmp计划。
  - 关于方程式和使用其他编译器的更好文档。
  - 当颗粒发散或为零时，打印方便的警告。`h, m`
  - 将代码生成抽象为支持Cython，OpenCL和CUDA的通用内核。在下一个版本中，它将被拉入一个单独的软件包中。
  - 新的GPU NNPS算法包括非常快速的八叉树。
  - 在示例中添加了几个物理测试用例。
- 方案：
  - 添加有效的隐式不可压缩SPH方案（Ihmsen等人，2014）
  - 从SPH2D中添加GSPH方案，并从那里添加所有近似的黎曼求解器。
  - 添加用于基于Shepard和MLS的密度校正的代码。
  - 添加Bonet和Lok（1999）提出的内核更正
  - 添加来自CRKSPH论文的更正（2017）。
  - 添加Parshikov（2002）和Zhang，Hu，Adams（2017）的基本方程式
- Bug修复：
  - 确保保留方程的顺序。
  - 修复了转储VTK文件的错误。
  - 在连续性方程中修复Adami，Hu，Adams方案中的错误。
  - 修复WCSPH方案中的实体错误。
  - 沿z轴定期修复错误。

*1.0a5*

- 发布日期：2017年9月17日
- Mayavi Viewer现在支持空粒子阵列。
- 修复方案选择器中的错误，该错误导致默认方案属性值出现问题。
- 添加starcluster支持/文档，以便可以在EC2上轻松使用PySPH。
- 改进粒子数组，使其自动遍历传递的数组，并且每次都不需要数组就可以接受常量值。
- 添加一些新示例。
- 为Jupyter笔记本电脑添加了2D和3D查看器。
- 添加几个新的Wendland Quintic内核。
- 添加选项以测量Cython代码的覆盖率。
- 添加EDAC方案。
- 将项目移至github。
- 改进文档和参考部分。
- 修复各种错误。
- 切换为使用pytest而不是鼻子测试。
- 在中添加方便的几何图形创建模块 `pysph.tools.geometry`
- 添加支持以使用Python文件编写查看器脚本，请参阅。`pysph view -h`
- 添加一些新的NNPS方案，例如扩展空间哈希，SFC，八叉树等。
- 改进Mayavi Viewer，以便可以查看速度矢量和任何其他矢量。
- Viewer现在具有一个按钮，可轻松编辑可视化属性。
- 为所有可用内核添加简单测试。添加`SuperGaussian`内核。
- 为pysph添加一个基本的dockerfile，以帮助进行CI测试。
- 更新构建，以便可以使用`USE_TRILINOS`环境变量使用系统zoltan安装来构建pysph，该安装是trilinos的一部分。
- 将`Zoltan_Comm_Resize`功能包装在中`pyzoltan`。

*1.0a4*

- 发布日期：2016年7月14日。
- 改进许多示例，使其更易于进行比较。
- 许多方程式参数不再具有默认值，以防止意外错误未指定重要参数。
- 增加了对`Scheme`管理方程式和求解器生成的类的支持。用户只需要创建粒子并设置带有适当参数的方案即可模拟问题。
- 添加支撑以轻松处理多个刚体。
- 如果安装了[h5py，](http://www.h5py.org/)则添加对转储HDF5文件的支持。
- 添加支持以使用[Mayavi](http://code.enthought.com/projects/mayavi/)或[PyVisfile](http://github.com/inducer/pyvisfile)直接转储VTK文件，请参阅`pysph dump_vtk`
- 改进了最近邻居代码，这使3D性能提高了约30％。
- `windows_env.bat`在Windows上不需要脚本。这是在内部自动设置的。
- 添加测试以检查所有示例是否都运行。
- 删除未使用的命令行选项，并添加一个`--max-steps`选项以允许用户运行指定的迭代次数。
- 添加了Ghia等人的盖驱动型腔流动结果，以便于比较。
- 添加了一些有关溃坝问题的实验结果。
- 在Python 3.x中已弃用argparse而不是optparse。
- 添加`pysph.tools.automation`有助于简化PySPH模拟的自动化和可重复性。
- 添加空间哈希和扩展的空间哈希NNPS算法以进行比较。
- 重构和清理与NNPS相关的代码。
- 添加几个气体动力学示例，然后添加`ADEKEScheme`。
- 使用[mpi4py](http://mpi4py.scipy.org/) 2.0.0版和[更低](http://mpi4py.scipy.org/)版本。
- 修复了TVF实施的主要错误，并增加了对TVF的3D模拟的支持。
- 修复Windows上的上载tarball中断的错误。`pip install pysph`
- 修复查看器UI，以在推送刷新时继续播放文件。
- 使用输出中转储的timestep值修复错误。
- 修复带有时间步的浮点问题，在示例中，示例将运行最终的极短时间步以精确达到最终时间。

*1.0a3*

- 发布日期：2015年8月18日。
- 使用`output_at_times`求解程序规范修复错误。
- 将生成的源代码和扩展名放到特定于平台的目录中， `~/.pysph/sources/<platform-specific-dir>`以避免多个Python版本，操作系统等出现问题。
- 创建扩展模块时，请使用锁定，以防止多个进程生成相同的外出时出现问题。
- 改进`Application`类，以便用户可以将其子类化以创建示例。用户还可以添加自己的命令行参数，并通过创建适当的方法来添加前/后步骤/阶段回调。
- 将示例移至`pysph.examples`。这使得示例可以重用并且更容易运行，因为安装pysph还将使示例可用。这些示例还执行后处理，以使其完全独立。
- 添加支持以编写压缩输出。
- 添加支持以从命令行设置内核。
- 添加一个新`pysph`的脚本，支持`view`，`run`和`test` 子命令。在`pysph_viewer`现在被删除，使用 来代替。`pysph view`
- 在中添加一个简单的刷新工具`pysph.solver.tools.SimpleRemesher`。
- 清理用于实体力学问题的对称特征值计算例程，并将其与OpenMP一起使用。
- 现在，`vmag`即使数据中不存在速度幅值（），查看者也可以查看它。
- 移植所有示例以使用新的`Application`API。
- 没有错误时不要显示不必要的编译器警告，而在有错误时不要显示详细信息。

*1.0a2*

- 发布日期：2015年6月12日
- 对[tox的](https://pypi.python.org/pypi/tox)支持，这使得在py26，py27和py34上测试PySPH变得轻而易举（如果需要，还可以进行更多测试）。
- 修复了代码生成器中的错误，该错误在安装之前无法导入pysph。
- 通过`pip`允许`egg_info`不使用cython或numpy来运行来支持安装。
- 为py27和py34 添加了使用tox的[Codeship CI构建](https://codeship.com/projects/83729)。
- CI为Python 2.7.x和3.4.x构建。
- 支持Python-3.4.x。
- 支持Python-2.6.x。

*1.0a1*

- 发布日期：2015年6月3日。
- 新的PySPH代码首次公开发布，该代码使用代码生成并托管在[bitbucket上](http://bitbucket.org/pysph/pysph)。
- OpenMP支持。
- 使用[Zoltan的](http://www.cs.sandia.gov/zoltan/) MPI支持。
- 从高级Python代码自动生成代码。
- 支持各种多步积分器。
- 添加了一个插值器实用程序模块，该模块将粒子数据插值到所需的一组点（或网格）上。
- 支持进口和出口。
- 支持基本的[Gmsh](http://geuz.org/gmsh/)输入/输出。
- 各种SPH配方的大量示例。
- 改进了文档。
- 持续集成基础上[可发运](https://app.shippable.com/projects/540e849c3479c5ea8f9f030e/builds/latest)， [Drone.io](https://drone.io/bitbucket.org/pysph/pysph)和[AppVeyor](https://ci.appveyor.com/project/prabhuramachandran/pysph)
