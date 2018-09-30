# encode_and_decode
### personal understanding

## rule
![rule](https://github.com/Van-Yo/encode_and_decode/blob/master/rule.png)

## example(utf-8,unicode,gbk)
```
# Author:Vanyo
import sys
# python3中默认是utf-8,所以会输出utf-8，跟例如pycharm,notepad++等软件上的编码不是一个意思
# 若python上的编码和软件上的编码一致则ok，否则会报错
# 例如软件的编码是GBK，而python3的编码是utf-8,则就会报错，需要我们在python文件头部对编码进行声明
# 应该写上大括号内的东西，不包括{}   ============>    {#-*-coding:gbk-*-}
print(sys.getdefaultencoding())
name = "你好"
# 这里name始终是unicode,跟上面改编码不一直的情况不相关,unicode.encode("utf-8")会生成utf-8:byte:b'\xe4\xbd\xa0\xe5\xa5\xbd'
print(name.encode("utf-8"))

# unicode.encode("gbk")就表示Unicode转为gbk:b'\xc4\xe3\xba\xc3'
name_to_gbk = name.encode("gbk")
print(name_to_gbk)

# gbk再转成utf-8
# 先gbk转成unicode
gbk_to_unicode = name_to_gbk.decode("gbk")
print(gbk_to_unicode)
# 再由unicode转成utf-8
print(gbk_to_unicode.encode("utf-8"))
```
### result
![result](https://github.com/Van-Yo/encode_and_decode/blob/master/result.png)
