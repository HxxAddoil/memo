# 模块与包(Module & Package)

- ## 模块

  简单讲，一个 `.py` 文件就是一个模块。 为了提高代码**复用率**，我们可以把一组相关的 Python 相关的定义、声明保存在同一个 `.py` 文件中。此时，这个 Python 脚本就是一个 Python 模块（Module）。 

  

  导入模块使用 `import` 语句，或者使用 `from ... import ...` 语句。当 运行模块本身，则`__name__==__main__` ，当模块被导入时，则`__name__!=__main__` ，可用作写模块的测试程序。

  

- ## 包

   包（package）是 Python 中对模块的更高一级的抽象， 包下面还能有包。 Python 要求每一个「包」目录下，都必须有一个名为 `__init__.py` 的文件。 

  包的导入与使用如下：

  ```python
  import package.subpackage.module
  package.subpackage.module.foo()
  ```

  简单的方式是：

  ```python
  from package.subpackage import moudle
  moudle.foo()
  ```

  

  `__init__.py`

  导入包时会被首先调用，其中首先可以 引入依赖的其他 Python 模块 ，其次有`__all__`列表，里面加入该包下可导入的子包/模块。

  例如mmdet/apis下的`__init__.py`内容如下：

  ```python
  from .env import get_root_logger, init_dist, set_random_seed
  from .inference import (inference_detector, init_detector, show_result,
                          show_result_pyplot)
  from .train import train_detector
  
  __all__ = [
      'init_dist', 'get_root_logger', 'set_random_seed', 'train_detector',
      'init_detector', 'inference_detector', 'show_result', 'show_result_pyplot'
  ]
  ```

  