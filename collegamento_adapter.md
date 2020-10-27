Come già detto nella sezione [funzione sendrequest](funzione_sendrequest.md) il nodo trolley si aspetta le richieste alla seguente url (la stessa logica vale per le response):

```url
http://[::1]:<port>/sendrequest
```
> TODO: scrivere la risposta che si ottiene nei casi in cui le transazioni vanno o non vanno a buon fine.

Nel momento in cui viene aggiunto un nuovo blocco alla chain, trolley automaticamente cercherà le transazioni destinate al wallet (identificato dal suo address) attualmente aperto.
Nel caso vengono trovate una o più transazioni, trolley spedirà le transazione al seguente indirizzo:

```url
http://<ip>:<port>/trolley/request
```

dove i parametri *ip* e *port* vengono presi dal file di configurazione (config.toml).
La stessa logica viene utilizzata per le response.   