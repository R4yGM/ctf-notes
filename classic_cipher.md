# CLassic cipher
Crpyto
viene data una challange con un codice in python che decripta una scritta, e leggendo bene il codice si può vedere come prende i caratteri e li ruota in base all'alfabeto di 32 posizioni, e poi crea una key che è una chiave che usa per fare il rot

per ottenre la flag basta fare la stessa cosa di encrypt solo usando la key giusta che si trova encriptando flag{ e vedere quando è uguale con quale key, 

    plaintextFLAG = "xcqv{gvyavn_zvztv_etvtddlnxcgy}"
    key = generateKey()
    ciphertext = encrypt(plaintextFLAG, "stuvwxyzabcdefghijklmnopqr")
    for i in range(30):
        ciphertext = encrypt(ciphertext, "stuvwxyzabcdefghijklmnopqr")
        print(ciphertext)
    
    return

e poi qua si fa il bruteforce 25 volte e si cerca la flag, rot all'incontrario praticamente