# Integrare pompa di calore Templari in Home Assistant tramite Modbus
Se possono essere utili a qualcun altro ho reso disponibili questi file di configurazione molto "artigianali" che sto utilizzando per integrare facilmente la pompa di calore, utilizzando tutti i registri modbus che vengono messi a disposizione. Non si tratta di una vera e propria integrazione ma di alcuni file che dovrete utilizzare, facendo anche dei trova-sostituisci a seconda di come avete nominato le vostre entità, installando altri componenti aggiutivi, ecc. Non basta quindi un clic, si presuppone una certa conoscenza di "smanettamento" con Home Assistant ;-)

# Prerequisiti
Oltre ad avere una pompa di calore Templari con pannello touch HCC, prima di fare qualsiasi cosa è necessario farsi abilitare la lettura del modbus/tcp, è necessario scrivere a updates@templari.com e chiedete di avere l'aggiornamento "supervisore SVK". Per prima cosa vi aggiorneranno il software del pannello (è quindi necessario averlo collegato ad internet), a me hanno messo la 1.8.55 che dovrebbe essere la versione minima necessaria per questa funzione, ma non basta avere solo la versione aggiornata, devono proprio attivarvi esplicitamente il servizio altrimenti i registri non sono leggibili. Per verificare questa attivazione dovete vedere nel menù avanzate "X" di fianco ad "altro" la presenza di un menù "supervisore" se lo vedete siete a posto, non serve settare nulla nel menù, basta solo verificarne la presenza. Quando vi abiliteranno il modbus vi forniranno anche un PDF con l'elenco dei vari registri, questi file di configurazione vi aiuteranno a configurarli velocemente e utilizzarli tutti in modo utile nell'interfaccia di HA oltre ad aggiungere alcune entità accessorie utili.

# Istruzioni
Leggete attentamente i 3 file che trovate nel repository, in particolare il commento iniziale di ognuno di essi ed eseguite tutte le istruzioni specificate per utilizzatli.
Dovete guardare nell'ordine:
1) templari_package.yaml
2) rename_bits.yaml
3) plancia.yaml

NOTA BENE: questi file sono calibrati per la versione software 1.8.55 del pannello HCC, altre versioni potrebbero avere differenze.

# Risultato finale
Questo è un esempio di plancia che vi troverete alla fine, ovviamente potete modificarla come meglio credete per aggiungere o togliere roba
<img width="2636" height="2216" alt="esempio-plancia" src="https://github.com/user-attachments/assets/fbdb878b-2f32-40c1-a0c6-2d36c62cf437" />
