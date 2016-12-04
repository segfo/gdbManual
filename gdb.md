# gdbのブレークポイント一覧
* **b** _address_  
 普通のブレークポイント

* **tb** _address_  
 一時的なブレークポイント
 一度通ったら消える

* **advance** _address_  
 tb address  
 c  
 の省略形

* **pbreak**
 すべてのpltにブレークポイントを自動的に貼る

# gdbでLD_PRELOAD
## API Hook/Anti-Anti-Debuggingで有用
普段のLD_PRELOADのやり方
```
$ LD_PRELOAD=./myHook.so debugeeApp  
```
gdb上でLD_PRELOADのやり方（意味は上記と同じ）
```
$ gdb debugeeApp  
gdb-peda$ set environment LD_PRELOAD=./myHook.so  
gdb-peda$ start  
```
