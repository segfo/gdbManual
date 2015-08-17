# pwntoolsとGDB

エントリーポイントにブレークポイントを打たせるスクリプト(init.py)

## 使い方
init.py < program file >  
gdb < program file > -x gdbScript  

## コード例
```
#!/usr/bin/python
from pwn import *
import sys

def putUsage():
    print   sys.argv[0]+" <elf file>"
    exit()

argv,argc = sys.argv, len(sys.argv)
if argc < 2 : putUsage()

elf = ELF(argv[1])
p = elf.entrypoint()

f = open("gdbScript","wb")
f.write("b *0x%x"%(p))
f.close()
```
