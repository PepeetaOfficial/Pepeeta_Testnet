La funzione sendrequest serve ad inviare una request che ha come destinatario un nodo, identificato da un address, all'interno della rete trolley. 
prevede un costo calcolato in transazioni, senza le quali non si potrebbe effettuare il broadcast della richiesta stessa.

### Invio ###

Quando il nodo si avvia questo rimane in ascolto su due porte, una per la comunicazione p2p ed una per la comunicazione con l'adapter. L'invio di request deve essere effettuato verso quest'ultima porta (di default la 30001) usando il metodo "POST" del protocollo http. Il corpo della richiesta dovrà essere un json così fatto:

```
http://[::1]:<port>/sendrequest
```

```json
{
    "receiver": "1CQJNBZ2cn4nZ4Xeo9avf1VBNb7GvzsvhF",
	"fnName": "function_name",
	"params": [
		{
			"name": "p1",
			"value": "valore 1"
		},{
			"name": "p2",
			"value": "5"
		}
	]
}
```

Ulteriori parametri verrebbero scartati.
Quando il nodo riceve in input un request, dopo aver fatto la validazione dei vari campi, controllo se il mittente ha un bilancio di request sufficiente per spedire alla rete la richiesta.
Se affermativo viene creata la transazione che conterrà la richiesta presa dall'input, la inserirà nel proprio pool e la invierà a tutti i suoi nodi conosciuti. 

> NB: il decremento effettivo della transazione avverrà soltanto nel momento in cui viene minato il blocco che la contiene.

Nel momento dell'invio trolley genererà un id univoco per la richiesta, che verrà utilizzato per correlarla ad una eventuale response.

### Ricezione ###

Quando un qualsiasi nodo della rete spedisce una request, semplificando drasticamente il processo di broadcast di una transazione, tutti gli altri nodi della rete ricevono tale request all'interno di una transazione.
la transazione, dopo essere stata validata, viene aggiunta al pool in attesa di essere minata.
