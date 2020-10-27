La funzione sendresponse serve ad inviare una risposta ad una precedente richiesta.
Come una request, anche la response prevede un costo in transazioni ed è destinata ad uno specifico address. A differenza della request, la response si riferisce ad una specificata request identificata da un Id

### Invio ###

Si spedisce anch'essa alla porta dedicata alla comunicazione con l'adapter usando le stesse modalità delle request.
La response va spedita all'url
```
http://[::1]:<port>/sendresponse
```
```json
{
	"fnName": "pippo_2",
	"receiver": "1CQJNBZ2cn4nZ4Xeo9avf1VBNb7GvzsvhF",
	"requestIdentifier": "63d5e308b69fbdb09567a8cc090f660c021980866c3f66eba75279e7a8b04733",
	"result": "risultato della risposta"
}
```

Dopo aver fatto la validazione dei campi, trolley tratterà una response alla stessa maniera di una request.

### Ricezione ###

Vedi [funzione sendrequest](funzione_sendrequest.md#Ricezione)