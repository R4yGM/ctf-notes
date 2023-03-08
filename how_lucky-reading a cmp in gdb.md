# how lucky you are


si nota che la key è generata con rand() che senza seed è sempre uguale

quindi dal mio binario, lo apro con gdb-peda e setto un breakpoint esattamente nell'istruzione del cmp

```
   0x55555555529a <main+98>:    lea    rdi,[rip+0xd8a]        # 0x55555555602b
   0x5555555552a1 <main+105>:   call   0x5555555550d0 <puts@plt>
   0x5555555552a6 <main+110>:   mov    eax,DWORD PTR [rbp-0x80]
=> 0x5555555552a9 <main+113>:   cmp    DWORD PTR [rbp-0x7c],eax
   0x5555555552ac <main+116>:   jne    0x555555555307 <main+207>
   0x5555555552ae <main+118>:   lea    rdi,[rip+0xd8f]        # 0x555555556044
   0x5555555552b5 <main+125>:   call   0x5555555550d0 <puts@plt>
   0x5555555552ba <main+130>:   lea    rsi,[rip+0xd9a]        # 0x55555555605b
```

rbp-0x7c è il valore che dobbiamo ottenere, eax si trova semplicemente facendo `info registers eax`
per trovare questa variabile basta fare un examine con il nome della variabile con davanti un dollaro

`x/d $rbp-0x7c`
