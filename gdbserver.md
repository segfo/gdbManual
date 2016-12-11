# gdbserver

## gdbserverでLD_PRELOADする方法
--wrapperオプションを使う。  
このオプションの説明：  
デバッグのためのプログラムを起動するラッパプログラムを指定します。  
  
注意点  
> --wrapper hogefuga -- ...

上記のように、必ず終端に -- を付ける必要がある。
詳しくは以下のリンクで。  
[https://sourceware.org/gdb/onlinedocs/gdb/Server.html](https://sourceware.org/gdb/onlinedocs/gdb/Server.html)  
  
例)
```
gdbserver --wrapper env LD_PRELOAD=./libc.so -- localhost:22222 ./execModule
```