.. index::
   single: Sonde
   single: Curiosity

.. _probe-section:

========================
Sonde remote Curiosity
========================


Introduzione
============

Le :dfn:`sonde remote Curiosity` sono la soluzione ideale per gestire in modo semplice ed efficace il 
monitoraggio di host remoti localizzati in sedi periferiche.
Si tratta di veri e propri appliance autoconfiguranti che collegati ad una rete dotata di 
server DHCP sono in grado di recepire un indirizzo e mettersi in comunicazione con il |product| 
a cui vengono correlate, fungendo da veri e propri proxy di monitoraggio: una volta accese, le 
sonde possono scansionare la rete in cui vengono inserite, restituendo al |product| il 
risultato dell'attività di discovery.
Attraverso l'interfaccia :dfn:`Wizard` è possibile inviare alla sonda le configurazioni di monitoraggio 
predisposte centralmente per abilitare il controllo dei nodi della rete remota.

.. note:: Le sonde sono in grado di gestire **unicamente** controlli di tipo **attivo agentless**.

.. note:: Le sonde sono utilizzabili unicamente a fine di monitoraggio, **non sono in grado di effettuare
          operazioni di inventario**!

.. _probe-activation:

Attivazione sonde
=================

Per poter essere utilizzate, le :index:`sonde remote` :index:`Curiosity` necessitano di essere attivate e 
collegate ad una istanza di |product| attraverso una semplice procedura di abilitazione.

Ad ogni sonda è associato un :dfn:`hash`, un codice costituito da 16 alfanumerici - diviso in due gruppi
da 8 per facilitarne la leggibilità - (esempio: ``A1B2C3D4-5E6F7G8H``) che viene gerenrato in fase di 
assemblaggio della sonda e che la caratterizza :dfn:`univocamente`: non esisteono due sonde con il medesimo :index:`hash`.

L'*hash* è riportato in tre posti distinti:

* sull'imballaggio della :index:`sonda`;
* nel :dfn:`QRCode` visualizzabile collegando un monitor ad una sonda **non registrata**;
* in colore verde nel banner di login della console visulalizzabile collegando un monitor ad una sonda **registrata**.

Il codice alfanumerico univoco è indispensabile per attivare la sonda e metterla in comunicazione con il
|product| che fungerà da :dfn:`parent` della sonda, cioè attraverso cui la sonda potrà essere controllata
e gestita.
Una volta entrati in possesso della sonda si dovrà accedere al :dfn:`Centro Servizi`, recarsi nel pannello
:dfn:`Amministrazione`, scheda :dfn:`Nethmonitor`.
Nella sezione :dfn:`Sonde Libere` sarà possibile inserire la nuova sonda inserendo:

* :dfn:`Etichetta`: una stinga descrittiva;
* :dfn:`Code`: il codice *hash*;
* :dfn:`Note`: un campo libero.

.. warning:: L'*hash* andrà indicato nel campo *Code* **senza** il carattere separatore, inserendo tutti e 16 gli
             alfanumerici uno di seguito all'altro.
             In caso contrario l'operazione **genererà un errore**!

Inseriti i dati della nuova sonda, questa apparirà nell'elenco delle :index:`sonde libere`.

Spostandosi nella :index:`sezione Nethmonitor` della stessa pagina verranno visualizzati tutti i |product|
attivati precedentemente con la procedura di :ref:`qualification_section`.
Ciascun |product| in elenco avrà una icona a forma di simbolo ``+``: cliccando sull'icona si aprirà
una finestra pop-up  attraverso cui sarà possibile :index:`associare la sonda` al |product| che fungerà
da *parent*.


.. _probe-management:

Gestione sonde
==============

Terminato il procedimento di registrazione ed abilitazione della sonda, la sua gestione sarà completamente
demandata all'interfaccia :ref:`wizard-section`.

.. _probe-qualification:

Nel pannello accessibile tramite il menu :dfn:`Visualizza lista` nella sezione *Sonde* dell'interfaccia del *Wizard*
verranno elencate tutte le *sonde* correlate ad uno specifico |product|: per abilitarne le funzionalità di monitoraggio
sarà innanzitutto necessario :index:`attivare le sonde` inserndo il segno di spunta nella colonna :dfn:`Attivo?`
relativa alla sonda da inizializzare.
L'azione andrà confermata nel successivo box che si aprirà in pop-up che consentirà di aggiungere anche ulteriori
informazioni relative alla sonda in un campo :dfn:`note`.

Il sistema richiederà di ricaricare i file di configurazione di Nagios e di riavviarne i relativi servizi attraverso 
un :dfn:`banner` informativo di colore giallo che comparirà in alto nell'interfaccia del *Wizard*: da quel momento
sarà presente sia nella lista dei nodi controllati dal *Wizard* (menu :index:`Visualizza lista` della sezione *Sistemi*)
che tra gli *host* del forntend Adagios un nodo relativo alla sonda stessa che permettrà di verificare la raggiungibilità
della sonda appena attivata.

.. _probe-host:


Definizone host monitorato tramite sonda
========================================

Per definire un monitoraggio attraveso una sonda:

* si potrà utilizzare la funzione di :dfn:`Autodiscovery` del *Wizard*;
* si potrà definire direttamente un nuovo sistema dalla :index:`sezione Sistemi` del *Wizard*.

Autodiscovery
-------------

La funzionalità di :index:`autodiscovery` presente nell'interfaccia *Wizard* consente di pilotare una scansione
dei dispositivi presenti in una rete in cui opera una sonda *Curiosity*.
Scegliendo la voce :dfn:`Esegui scansione` nella sezione *Autodiscovery* del *Wizard* verrà richiesto quale sonda
pilotare e quali subnet e netmask esplorare.

I risultati della scansione saranno disponibili nel menu :dfn:`Visualizza risultati` della stessa sezione.

Dalla lista dei risultati sarà possibile importare gli host in |product| cliccando semplicemente sull'icona 
a forma di simbolo ``+`` disponibile accanto ad ogni host rilevato nella scansione: il click sull'icona porterà
automaticamente l'utente alla pagina di definizione di un nuovo sistema occupandosi di compilare automaticamente
tutti i campi relativi all'host prescelto, si dovrnno unicamente selezionare la corretta :dfn:`tipologia` di
host tra quelle per il :index:`monitoraggio via sonda` e selezionare le :dfn:`classi di servizio` di interesse.


Definizione diretta nuovo host dietro sonda
-------------------------------------------

Resta in ogni caso possibile definire manualmente un host da monitorare attraverso sonda remota inserendo
tutti i necessari parametri richiesti nella finestra di :dfn:`Inserimento nuovo sistema`.
Le attenzioni che si dovranno avere sono:

* di scegliere come dispositivo *Genitore* dell'host da inserire **la sonda dietro cui si trova l'host stesso**;
* di selezionare la corretta :dfn:`tipologia` di host tra quelle per il :index:`monitoraggio via sonda`;
* di selezionate le :dfn:`classi di servizio` di interesse.

