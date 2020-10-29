Dopo aver installato e configurato l'ambiente Pepeeta e la blockchain trolley occorre collegare il proprio nodo alla testnet.

Il requisito è che si disponga di un indirizzo ipv6.
Se questo indirizzo non è provvisto dal proprio internet provider (ISP) consigliamo di ottenere un tunnel sul website di Hurricane Electric www.he.net .

### Passaggi ###

All'interno del file _config.toml_, nel campo `peers`, inserire gli indirizzi dei nodi disponibili. ESEMPIO:

```
peers = [
    "/ip6/2001:41d0:303:beaa::a0/tcp/30000/p2p/Qmb3GnaEpiCppVQYJa5FCkP15ckVGnrTdkjyVtsMep8xPb",
    "/ip6/2001:41d0:303:beaa::a2/tcp/30000/p2p/QmUg4wce8HQfuGDERzrcJzbvppMP6ia6jEcWucaFcrSrzb"
]
```

È possibile reperire la lista di tutti i nodi disponibili aprendo il seguente [file](nodi.md).

Per verificare che la connessione sia stata correttamente stabilita, avviare il nodo da terminale con il comando ```/path/eseguibile/TROLLEY-GO startnode``` e attendere il messaggio di connessione stabilita.

### Aggancio al servizio Pepeeta Stamp ###

Dopo aver installato correttamente il client di Pepeeta Stamp è necessario impostare l'indirizzo del servizio modificando il file `client.env`.

Il servizio di Pepeeta Stamp è raggiungibile al seguente address:

1B9hhHMPARa2Cy48qhnBHA4WQexgvZPFLm