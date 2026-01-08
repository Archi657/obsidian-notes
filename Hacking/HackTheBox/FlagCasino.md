**Link** : [Así se puede predecir un número “ALEATORIO” - YouTube](https://www.youtube.com/watch?v=owHLnpqZr2U)
## Steps
To open ghidra
File -> Open new project -> Non-shared porject -> next -> folder then import file and drag file to dragon.

![[Pasted image 20260108224411.png]]
```C
srand((int)local_d) //its the sève of the random. It might cause to always be the same.

if(rand_value != *(int *)(check + (long)(int) counter * 4))
// if(rand_value != check[i])
```


## Step to check binaries
```Python

# to have the same random of C
#locate libc.so.6
# usr/lib/libc.so.6

# main.py
#!/usr/bin/env python3


from pwn import *
import ctypes

libc= ctypes.CDLL("libc.so.6")
mapping = {}

for x in range(256):
	libc.srand(x)
	random_value = libc.rand()
	mapping[random_value] = chr(x)
	
print(mapping)

binary = ELF("./casino", checksec=False)

print(binary.sym)

# main.py | tr ',' '\n' | grep check
# 'check' : 1632
info(f"Check address : {hex {binary.sym['check']}}")

# based on the code, it has 30 positions so
flag = ""

for i in range(30):
	info(f"{hex(binary.sym['check'] + i*4)} -> {binary.u32(binary.sym['check'] + i*4)}") 
	flag += mapping[binary.u32(binary.sym['check'] + i*4 )]
```
## Notes

#hacking #hackthebox #ghidra #random
