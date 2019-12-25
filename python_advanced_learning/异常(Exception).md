# 异常(Exception)

- ##  处理异常

  我们可以通过使用 try..except 来处理异常状况。 一般来说我们会把通常的语句放在 try 代
  码块中， 将我们的错误处理器代码放置在 except 代码块中。  

  ```python
  try:
  	text = input('Enter something --> ')
  except EOFError:
  	print('Why did you do an EOF on me?')
  except KeyboardInterrupt:
  	print('You cancelled the operation.')
  else:
  	print('You entered {}'.format(text))
  ```

- ## 抛出异常

    你可以通过 **raise** 语句来引发一次异常， 具体方法是提供错误名或异常名以及要抛出
  （ Thrown） 异常的对象。
  你能够引发的错误或异常必须是直接或间接从属于 Exception （ 异常） 类的派生类。  

  ```python
  class ShortInputException(Exception):
  '''一个由用户定义的异常类'''
      def __init__(self, length, atleast):
          Exception.__init__(self)
          self.length = length
          self.atleast = atleast
      try:
          text = input('Enter something --> ')
          if len(text) < 3:
          raise ShortInputException(len(text), 3)
          # 其他工作能在此处继续正常运行
      except EOFError:
      	print('Why did you do an EOF on me?')
      except ShortInputException as ex:
      	print(('ShortInputException: The input was ' +
      	'{0} long, expected at least {1}')
      	.format(ex.length, ex.atleast))
      else:
      	print('No exception was raised.')
  ```

- ## Try ... Finally

  就是finally，不赘述。

