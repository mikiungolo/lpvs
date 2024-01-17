Questo file txt serve a spiegare la presenza di due file smv all'interno della cartella e cerca di porre una lettura sul lavoro che è stato svolto.   
I due file smv: Rfid_base.smv e Rfid_clipped.smv. Entrambi sono adeguatamente commentati ed entrambi sono inizializzati secondo l'esempio riportato 
dall'albero binario nel documento per una questione di praticità 

I due algoritmi sono stati modellati in modo tale da poter definire un sistema Rfid composto da un lettore e N tag attivi, come nell'esempio del documento. 
Nei due modelli i parametri impostati per il livello della batteria fanno sì che i tag anche se attivi non influenzano l'esecuzione,
ovvero non terminano mai le proprie risorse, perchè occorre raccogliere i dati utili a verificare il reale miglioramento dalla versione base a quella
clipped dell'algoritmo, in particolare si ragiona sul numero di collisioni durante l'esecuzione. 

Si può notare attraverso le proprietà descritte che l'algoritmo clipped non raggiunge mai il numero di collisioni che si verificano nella versione 
base dell'algoritmo, come si può notare dalla seguente proprietà: 
" AG (reader.state = collision -> reader.collision_count < 8) ", 

dove il valore 8 rappresenta il numero di collisioni che si raggiungono nella versione base, secondo la verfica delle seguenti proprietà: 
" EF reader.collision_count = 8 " 
" AG (reader.collision_count = 8 -> AG !(reader.state = collision)) " 

Alla fine dei file sorgenti vengono poste due tracce d'esecuzione, rispettivamente per la loro versione dell'algoritmo con i tag attivi influenti nell'esecuzione.
Per buildare il modello con i tag attivi ed influenti basta settare il valore di lev_battery nel modulo Tag ad un valore inferiore a 5. 
Rispettivamente per ognuno dei file viene già predisposta una traccia di esecuzione con il lev_battery inizializzato a {2, 3} in cui si mostrano la transizioni 
in un sistema Rfid completo con tag attivi. 
