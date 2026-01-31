# Integrare pompa di calore Templari in Home Assistant tramite Modbus
Se possono essere utili a qualcun altro ho reso disponibili questi file di configurazione molto "artigianali" che sto utilizzando per integrare facilmente la pompa di calore, utilizzando tutti i registri modbus che vengono messi a disposizione. Non si tratta di una vera e propria integrazione ma di alcuni file che dovrete utilizzare, facendo anche dei trova-sostituisci a seconda di come avete nominato le vostre entità, installando altri componenti aggiutivi, ecc. Non basta quindi un clic, si presuppone una certa conoscenza di "smanettamento" con Home Assistant ;-)

# Prerequisiti
Oltre ad avere una pompa di calore Templari con pannello touch HCC, prima di fare qualsiasi cosa è necessario farsi abilitare la lettura del modbus/tcp, è necessario scrivere a updates@templari.com e chiedete di avere l'aggiornamento "supervisore SVK". Per prima cosa vi aggiorneranno il software del pannello (è quindi necessario averlo collegato ad internet), a me hanno messo la versione 1.8.55, ma non basta avere solo la versione aggiornata, devono proprio attivarvi esplicitamente il servizio altrimenti i registri non sono leggibili. (Ad alcuni, ma non tutti, una volta attivata questa funzione nel menù avanzate "X" di fianco ad "altro" appare un menù "supervisore" se lo vedete siete a posto, non serve settare nulla nel menù, se non vi appare potreste comunque avere il modbus abilitato, dovete solo provare). Assieme all'attivazione vi forniranno anche un PDF con l'elenco dei vari registri, i miei file di configurazione vi aiuteranno a configurarli velocemente e utilizzarli tutti in modo utile nell'interfaccia di HA oltre ad aggiungere alcune entità accessorie utili.

NOTA BENE: questi file sono calibrati per la versione software 1.8.55 del pannello HCC, altre versioni potrebbero avere differenze. So per certo che le versioni 1.9.* che venivano installate tempo fa, ma ora non più, hanno una configurazione diversa.

# Istruzioni
Leggete attentamente i 3 file che trovate nel repository, in particolare il commento iniziale di ognuno di essi ed eseguite tutte le istruzioni specificate per utilizzatli.
Dovete guardare nell'ordine:
1) templari_package.yaml
2) rename_bits.yaml
3) plancia.yaml

NOTA: per una limitazione del modbus di HA gli id assegnati alle entità "bit" hanno per forza un numero di 1 inferiore al reale, da qui nasce la necessità dello script rename_bits.yaml che gli assegna un nome corretto, ma l'id rimane di 1 inferiore, non è un errore ma è l'unico modo di farlo funzionare al momento per far combaciare il nome con quanto specificato dalla documentazione ufficiale

# Risultato finale
Questo è un esempio di plancia che vi troverete alla fine, ovviamente potete modificarla come meglio credete per aggiungere o togliere roba
<img width="2606" height="1971" alt="esempio-plancia" src="https://github.com/user-attachments/assets/5f940fe9-921d-42d5-9152-fd3552276f15" />

PS: ho sviluppato anche uno "sniffer" per recuperare alcune informazioni che l'interfaccia modbus ufficiale attualmente non permette di ottenere, come le temperature rilevate dai sensori room, trovate maggiori info qui: https://github.com/wergio/addon-templari-modbus-sniffer/
