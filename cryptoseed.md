# CryptoSeed

nelle challange con un seed randomico tipo con random.seed(), si deve ricavare il seed criptando flag{ con seed randomico e trovando la parte che matcha, dopo aver trovato la parte che matcha si sostituisce il seed e si fa un for ancora per i valori fino a 255 per sicurezza, e random.randint dovrebbe restituire i valori uguali della flag siccome è stato usato un certo seed, e si fa lo xor byte a byte, dentro un array 


```py
flag = "088596df93697e62d71cb143352ccb45be15463219c6cc917f9be83c1aa1f7d0217b4586c1058009"
flag = bytes.fromhex(flag)
key = 53
random.seed(key)
for i in range(256):
    solux = []

    for c in flag:
        char = random.randint(0, 255) ^ c
        solux.append((char))

    print(bytes(solux).decode("latin-1"))
```