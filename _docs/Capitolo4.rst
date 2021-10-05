
|pagoPA_logo|
   
+---------------------------------------------------------------------------------------------------+
| **SPECIFICHE ATTUATIVE DEI CODICI IDENTIFICATIVI DI VERSAMENTO, RIVERSAMENTO E RENDICONTAZIONE**  |
|                                                                                                   |
|                                                                                                   |
| *Allegato A alle "Linee guida per l'effettuazione dei pagamenti elettronici a favore delle*       |
| *pubbliche amministrazioni e dei gestori di pubblici servizi"*                                    |
|                                                                                                   |
|                                                                                                   |
| **Versione 1.4.0 - ottobre 2021**                                                                 |
+---------------------------------------------------------------------------------------------------+

.. _operazione-di-trasferimento-fondi:

4. Operazione di trasferimento fondi |image6|
====================================

Per l’operazione di trasferimento dei fondi a ogni Ente Creditore il PSP
utilizza unicamente lo strumento SEPA Credit Transfer. Le operazioni di
trasferimento sono cadenzate temporalmente in ogni giornata operativa
secondo quanto meglio specificato nel paragrafo successivo. 
In coerenza con gli articoli 15 e 20 del D. lgs n. 11/2010 il PSP
del pagatore deve effettuare il riversamento delle somme incassate in
modalità cumulativa per ogni giornata operativa, disponendo un solo SCT
per ogni IBAN di incasso specificato nelle richieste di pagamento ricevute.

Per l’esecuzione dell’operazione devono essere utilizzati gli schemi
previsti del SEPA Credit Transfer (cfr SEPA *Credit Transfert Scheme
Rulebook* pubblicato da EPC [6]_).

La tabella indica come valorizzare gli attributi dello schema di un SCT: 

+--------+--------------------------+------------------------------------------------+---------+
| **ID** | **Nome**                 | **Valore**                                     | **nota**|
+========+==========================+================================================+=========+
| AT-02. | Ordinante.               | <Ragione Sociale PSP> Servizio pagoPA.         |.        |
+--------+--------------------------+------------------------------------------------+---------+
| AT-05. | Remittance Information.  | /PUR/LGPE-RIVERSAMENTO <Descrizione> pagamenti |         |
|.       |                          | del <aaaammgg>/URI/<identificativoFlusso>      |         |
+--------+--------------------------+------------------------------------------------+---------+
| AT-10. | Codice Identificativo.   | <CF Ordinante>                                 | opt.    |
|.       |.Ordinante.               |                                                |.        |
+--------+--------------------------+------------------------------------------------+---------+
| AT-20. | Iban Beneficiario.       | <Ragione Sociale Ente Creditore>               |.        |
+--------+--------------------------+------------------------------------------------+---------+
| AT-24. | Codice Indentificativo.  | <CF Beneficiario>                              |.        |
|.       | Beneficiario.            |                                                |.        |
+--------+--------------------------+------------------------------------------------+---------+
| AT-42. | Referenza ordinante.     | <aaaammgg><EndToEndID>                         |.        |
+--------+--------------------------+------------------------------------------------+---------+
La nota "opt" indica che la valorizzazione è opzionale.

Legenda: 

-  <Descrizione>: assume di default il valore “Cumulativo” (ovvero
   “Cumulativo same day” nel caso che la data del trasferimento e quella di
   incasso coincidano). Nel caso il PSP disponga ulteriori SCT, relativi alla
   stessa giornata operativa di incasso, assume il valore “Integrativo”<numero d’ordine>,
   dove il numero d’ordine è un progressivo di una cifra compreso fra 1 e 9.
   NB: Il numero massimo di SCT per la stessa giornata operativa dovrà essere
   tassativamente pari a 10. 
-  <aaaammgg>: data della giornata operativa di incasso delle richieste di pagamento
-  <Iban Beneficiario>: Il PSP attinge tale dato dalle richieste di pagamento eseguite.
-  <Ragione Sociale Ente Creditore>: Il PSP attinge tale dato dalle richieste di pagamento
   eseguite.
-  <CF Beneficiario>: Il PSP attinge tale dato dalle richieste di pagamento eseguite.
-  <idFlusso>: specifica il dato relativo all’informazione identificativoFlusso presente
   nel flusso di rendicontazione descritto nel successivo :ref:`capitolo 7 <flusso-di-rendicontazione>`.
-  <EndToEndID>: è riportato il dato identificativoUnivocoRiscossione indicato nel
   Flusso di rendicontazione. Viene valorizzato solo nel casi in cui il PSP al momento
   della predisposizione del flusso di rendicontazione non disponga del TRN. L’utilizzo
   tuttavia è deprecato e verrà dismesso in futuro.

NB: Al fine di effettuare una riconciliazione automatica del versamento le informazioni
dell’attributo AT-05 sono state composte secondo la struttura proposta dall’Associazione
Europea dei Tesorieri di Impresa (EACT) nel documento EACT FORMATTING RULES OF SEPA
“UNSTRUCTURED” 140 CHRS FIELD FOR REMITTANCE INFORMATION e finalizzata al trattamento
automatizzato delle informazioni tra partner commerciali. In particolare le stringe
“/PUR/” e “/URI/” sono tag costanti il cui significato è definito dallo standard EACT.

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
.. |image6| image:: media/image6.png
   :width: 0.7874in
   :height: 0.22651in
.. |image7| image:: media/image4.png
   :width: 0.7874in
   :height: 0.22651in
