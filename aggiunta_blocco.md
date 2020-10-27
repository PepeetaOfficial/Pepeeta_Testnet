Ogni transazione in ingresso (di qualsiasi natura essa sia) trolley proverà a minare un nuovo blocco.
Affinché inizi effettivamente il processo di mining deve essere verificata una predeterminata condizione (attualmente la condizione è che il pool deve contenere un numero minimo di transazioni).
All'ingresso dell'i-esima transazione che innesca il processo di mining trolley sposterà tutte le transazioni contenute nel pool in una collezione temporanea, utillizzata solo per il processo di mining, per poi attendere nuove transazioni.

> Durante la fase di risoluzione del puzzle trolley non sarà in grado di iniziare altri processi di mining.
> Per iniziare un nuovo processo bisogna attendere la fine del precedente.

Una volta finito il processo di mining trolley cercherà di aggiungere il blocco alla chain.

### Aggiunta del blocco alla chain ###

Ci sono due modi per aggiungere un nuovo blocco alla chain:

1. Siamo noi a minare un nuovo blocco;
2. Qualcuno ci invia un blocco di altezza superiore al blocco più recente della nostra chain;

In entrambe i casi trolley, una volta ricevuto il nuovo blocco, effettuerà il broadcast nel resto della rete ed eseguirà le transazioni in esso contenute.
Nel caso di transazioni di request o response provvederà a spedire il contenuto al proprio adapter solo se il destinatario del contenuto è il suo address.
Mentre nel caso di azioni del master wallet eseguirà l'azione.
