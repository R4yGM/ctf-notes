# Enterpise Encryption

```py
l = len(flag)
assert l % 2 == 0

with open("encrypted.txt", "w") as f:
    f.write(b''.join(bytes([(x^31), (y^31)]) for x,y in zip(flag[:l//2], flag[l//2:])).hex())
```
fa semplicente lo xor con 31 con cisciun byte, e mischia i byte

```py
def find_flag(hex_str):
    flag = bytes.fromhex(hex_str)
    l = len(flag)
    decrypted_flag = b''.join(bytes([x ^ 31]) for x in flag)
    return decrypted_flag.decode()

with open("encrypted.txt", "r") as f:
    ss= []
    s2=[]
    hex_str = f.read()
    flag = find_flag(hex_str)
    print(flag)
    for x in range(len(flag)):
        if x%2==0:
            ss.append(flag[x])
        else:
            s2.append(flag[x])

print("".join(ss)+"".join(s2))
```

