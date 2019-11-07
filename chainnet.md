# ChainNet   

***


## communication protocol between gateway chain system   

Blockchain has evolved into various models. In the near future, standard communication protocols between these advanced system families will be needed. Unlike a centralized system, blockchain cannot forge data and protect digital assets from external heckers.   

In order to eliminate the weakness of the centralized system, the blockchain will be able to communicate with another blockchain, and even among those blockchain groups. It is likely that standardized communication protocols will be needed to enable such a system. We decided to call it a chainnet.   

In the future, chainnet will evolve into another giant internet. Chainnet will also be able to communicate with gateway groups, gateway, and public/private nodes.   
We simply defined a chainnet data packet.   


```
-----------------------------------------
header	chain transfer protocol (CTP)
-----------------------------------------

tid	top chain id key
cid	gateway chain id key
gid	gateway id key
pid	peer id key
pubkey	public key
pivkey	private key

-----------------------------------------
data	data information
-----------------------------------------

```

robinadaptor  
robin.adaptor@gmail.com