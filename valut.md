# Flagvalut writeup
Binary reverse

Il mio vault non si apre a meno che tu non sappia la password. Che è difficile, dato che è generata casualmente.

Puoi collegarti al servizio remoto con:

nc flagvault.challs.olicyber.it 34000

## Procedimento
aprire ghidra e vedere come la password è generata randomica ma non del tutto perchè il rand() di c è un po' fatto male, inoltre non ci può essere buffer overflow siccome il buff di fgets è molto minore della variabile, poi 'fgets' è più sicuro di 'gets' e strncmp è anche più sicuro perchè verifica carattere per carattere che è correttamente uguale, quindi l'unica cosa che si può fare è runnare il file e vedere i valori nel registro, specificatamente la password che viene comparata, e si può fare ciò con 'break strncmp' oppure fai disass main e guardi le funzioni e prendi l'indirizzo e setti un breakpoint, in ogni caso 
poi inserisci una password quando te lo chiede, e dopo si triggera il breakpoint, e con info registers ti farà vedere tutte le variabili, e le variabili che comparano sono in sostanza quelle che iniziano per rax,rcx,rdx  //poi forse anche rbx

e con x/s e il nome della variabile, tipo x/s $rax, oppure usando il valore hex in memoria

poi si troverà il proprio valore di input e poi il valore con cui lo compara che lo si prende manualmente e lo si mette a parte e si troverà la flag