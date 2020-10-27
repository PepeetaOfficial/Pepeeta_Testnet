Attualmente le funzioni disponibili per interrogare il nodo e per conoscere lo stato della rete sono le seguenti:

*    **GET** gettxpool  
Restituisce le transazioni all'interno del transaction pool del nodo

*   **GET** getchain  
Restituisce l'intera blockchain

*   **GET** getblock/{height:[0-9]+}  
Restituisce il blocco con l'altezza passata come parametro

*   **GET** getblock/{hash:[0-9a-fA-F]{64}}  
Restituisce il block con l'hash passato come parametro

*   **GET** gettransaction/{hash:[0-9a-fA-F]{64}}  
Restituisce la transazione con l'hash passata come parametro

*   **GET** getbalance/{address:[1-9A-HJ-NP-Za-km-z]{34}}  
Restituisce il bilancio dell'address passato come parametro

*   **GET** getlastblocks/{n:[0-9]+}  
Restituisce l'ultimo blocco della chain

*   **GET** getaddresses  
Restituisce gli address all'interno del wallet dell'utente

*   **GET** getpublickey  
Restituisce la public key del master wallet

*   **GET** getmasteraddress  
Restituisce l'address del master wallet

*   **TUTTI I METODI** test  
Restituisce ciò che riceve in input. Non interagisce in alcun modo con la rete ne con il resto del software. Non è soggetto a controlli ne altro. Può essere usato semplicemente per controllare che il server del nodo risponda.

Queste richieste vanno fatte all'url

```url
http://[::1]:<port>/<function_name>
```