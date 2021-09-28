
|pagoPA_logo|
   
+---------------------------------------------------------------------------------------------------+
| **SPECIFICHE ATTUATIVE DEI CODICI IDENTIFICATIVI DI VERSAMENTO, RIVERSAMENTO E RENDICONTAZIONE**  |
|                                                                                                   |
|                                                                                                   |
| *Allegato A alle "Linee guida per l'effettuazione dei pagamenti elettronici a favore delle*       |
| *pubbliche amministrazioni e dei gestori di pubblici servizi"*                                    |
|                                                                                                   |
|                                                                                                   |
| **Versione 1.3.1 - gennaio 2018**                                                                 |
+---------------------------------------------------------------------------------------------------+

.. _operazione-di-trasferimento-fondi:

4. Operazione di trasferimento fondi |image4|
====================================

Per l’esecuzione dell’operazione devono essere utilizzati gli schemi
previsti del SEPA Credit Transfer (cfr SEPA *Credit Transfert Scheme
Rulebook* pubblicato da EPC [6]_).

In particolare la causale di versamento, il cui formato è stato
descritto nel capitolo 3, **deve essere riportata** nel dato
“*Unstructured Remittance Information*” presente nel tracciato del
SEPA Credit Transfer (attributo AT-05).

È inoltre opportuno che il prestatore di servizi di pagamento indichi,
nel dato “\ *End To End Id”* (attributo AT-41 Originator’s Reference),
lo stesso identico valore che è stato indicato nell’elemento
identificativoUnivocoRiscossione della Ricevuta Telematica a cui il SCT
fa riferimento.

Il prestatore di servizi di pagamento che tratta l’operazione potrà
altresì indicare il codice fiscale dell’ordinante, laddove conosciuto,
nel dato “*Originator Identification Code”* (attributo AT-10) presente
nel tracciato del SEPA Credit Transfer.

.. _giornata-operativa-ed-invio-del-sepa-credit-transfer: 

4.1 Giornata operativa ed invio del SEPA Credit Transfer
--------------------------------------------------------

In coerenza con quanto previsto all’articolo 20 del D. lgs n. 11/2010,
il PSP del pagatore assicura che l'importo dell'operazione venga
accreditato sul conto dell’Ente Creditore entro la fine della giornata
operativa successiva a quella indicata nella relativa Ricevuta
Telematica.

Al fine di assicurare l’applicazione uniforme dei tempi di esecuzione
massima delle operazioni e tenendo altresì conto dei diversi modelli
operativi adottati dai PSP, indipendentemente dal termine della giornata
operativa stabilito da ciascun PSP, il termine della giornata operativa
per la ricezione delle operazioni di pagamento da effettuarsi tramite il
Nodo dei Pagamenti-SPC è stabilito in via generale alle ore 13,00
(cosiddetta “giornata operativa del Nodo dei Pagamenti-SPC”).

Ai fini dell’adempimento dell’obbligazione dell’utilizzatore finale nei
confronti dell’Ente Creditore fa fede la data di emissione della
Ricevuta Telematica, indipendentemente dall’effettiva ora o giornata
operativa di accredito del pagamento in favore dell’Ente Creditore.

Dallo scadere del termine per l’esecuzione dell’accredito sul conto
dell’Ente Creditore dell’importo dell’operazione di pagamento decorrono
gli interessi legali moratori pari al tasso BCE maggiorato di otto punti
percentuali.

Inoltre, nell’eventualità in cui il PSP per causa a lui imputabile non
accrediti sul conto dell’Ente Creditore l'importo dell'operazione entro
la fine della giornata operativa successiva a quella indicata nella
relativa Ricevuta Telematica, ferma restando la debenza degli interessi
moratori, il PSP risulterà altresì responsabile del danno arrecato
all’Ente Creditore per effetto del ritardo nell’accredito dell'importo
dell'operazione, ivi inclusi i danni connessi all’applicazione di
sanzioni in capo all’Ente Creditore stabilite da una specifica normativa
di riferimento [7]_.

Si precisa che il PSP risulterà responsabile del danno arrecato all’Ente
Creditore nella misura economica direttamente imputabile al PSP.

.. _utilizzo-del-bollettino-di-conto-corrente-postale:

4.2 Utilizzo del bollettino di conto corrente postale |image5| 
-----------------------------------------------------


La causale del versamento - obbligatoria per le pubbliche
amministrazioni ai sensi dell’articolo 4, comma 4, del DPR 144/2001 -
deve essere compilata anche per i versamenti a favore dei gestori di
pubblici servizi e deve essere conforme al formato descritto nel
:ref:`capitolo 3 <formato-della-causale-di-versamento>`.

.. _rifiuto-del-sepa-credit-transfer:

4.3 Rifiuto del SEPA Credit Transfer |image7|
------------------------------------

Qualora il SEPA Credit Transfer venga restituito con messaggio di REJECT
al prestatore di servizi di pagamento che lo ha inviato, quest’ultimo
dovrà darne immediata comunicazione al servizio operativo di gestione
del sistema pagoPA attraverso un messaggio di posta elettronica nel
quale dovrà indicare le informazioni di Tabella 4.

**Tabella** **3 – Dati da inviare da parte del PSP in caso di REJECT del SCT**

+-----------------------------------+----------------------------------------------------------+
| **Dato**                          | **Contenuto**                                            |
+===================================+==========================================================+
| Identificativo del PSP            | così come indicato nella componente <istituto mittente>  |
|                                   | del dato identificativoFlusso,                           |
|                                   | :ref:`vedi § 7.2 <stand-del-dato-identificativoflusso>`  |
+-----------------------------------+----------------------------------------------------------+
| Denominazione del PSP             |                                                          |
+-----------------------------------+----------------------------------------------------------+
| Codice Fiscale dell'Ente          |                                                          |
| Creditore                         |                                                          |
+-----------------------------------+----------------------------------------------------------+
| Denominazione dell'Ente Creditore |                                                          |
+-----------------------------------+----------------------------------------------------------+
| Data dell'emissione della RT      | elemento dataOraMessaggioRicevuta                        |
+-----------------------------------+----------------------------------------------------------+
| IBAN di accredito del SCT         | attributo AT-20 IBAN of the account of the Beneficiary   |
+-----------------------------------+----------------------------------------------------------+
| Importo del SCT                   | attributo AT-04 Amount                                   |
+-----------------------------------+----------------------------------------------------------+
| Causale del SCT                   | attributo AT-05 Remittance Information                   |
+-----------------------------------+----------------------------------------------------------+
| TRN del SCT                       | attributo AT-43 Originator Bank's reference number       |
+-----------------------------------+----------------------------------------------------------+
| *EndToEndId* del SCT              | attributo AT-41 Originator's reference                   |
+-----------------------------------+----------------------------------------------------------+
| Motivo del messaggio di REJECT    | attributo AT-R3 reason code for non-acceptance           |
+-----------------------------------+----------------------------------------------------------+
| Note                              | a cura del PSP                                           |
+-----------------------------------+----------------------------------------------------------+

Sulla base delle indicazioni ricevute dal servizio operativo di gestione
del sistema pagoPA, l’Ente Creditore ed il PSP si attivano per rimuovere
le cause del rifiuto e per il successivo completamento dell’operazione
di trasferimento fondi.

Una volta completata tale operazione, l’Ente Creditore dovrà darne
immediata comunicazione al servizio operativo di gestione del sistema
pagoPA attraverso un messaggio di posta elettronica nel quale dovrà
indicare le stesse informazioni sopra riportate (Tabella 4).


.. [6]
   Cfr documentazione all’indirizzo
   `http://www.europeanpaymentscouncil.eu/content.cfm?page=sepa_credit_transfer <http://www.europeanpaymentscouncil.eu/content.cfm?page=sepa_credit_transfer>`__

.. [7]
   A titolo esemplificativo e non esaustivo, per gli Enti Creditori che
   svolgono il servizio di riscossione, si segnalano le sanzioni
   stabilite all’articolo 47 del Decreto legislativo del 13 aprile 1999,
   n. 112.


.. |pagoPA_logo| image:: media/header.png
.. |image4| image:: media/image7.png
   :width: 0.7874in
   :height: 0.22905in
.. |image5| image:: media/image5.png
   :width: 0.7874in
   :height: 0.24059in
.. |image7| image:: media/image4.png
   :width: 0.7874in
   :height: 0.22651in
