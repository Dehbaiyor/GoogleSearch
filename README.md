# GoogleSearch
This is an updated version to suite Python 3.x execution environments

The original code can be found at https://pypi.org/project/google-search/#description or https://github.com/anthonyhseb/googlesearch but it is **not suitable for Python 3.x**. I have modified it slightly to suit the new syntax/libraries in Pyhton 3.x. Please let me know if you find any issues with this code when using with Python 3.x.


**Sometimes, python's default print() statement many not work with Windows Command Prompt and throw errors when priting the text from webpages**. This due to Windows Command Prompt's incompatibility with unicode encoding. A workaround is to use the following method:



```python
import sys
def uprint(*objects, sep=' ', end='\n', file=sys.stdout):
    enc = file.encoding
    if enc == 'UTF-8':
        print(*objects, sep=sep, end=end, file=file)
    else:
        f = lambda obj: str(obj).encode(enc, errors='backslashreplace').decode(enc)
        print(*map(f, objects), sep=sep, end=end, file=file)
```
