
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

.. _flusso-di-rendicontazione:

7. Flusso di Rendicontazione  |image17|
============================

Le informazioni che devono essere messe a disposizione dell'Ente
Creditore sono organizzate in flussi omogenei di dati e devono essere
rese disponibili ai soggetti interessati a cura del prestatore di
servizi di pagamento che ha effettuato l’operazione di pagamento.

Entro e non oltre le ore 24 della seconda giornata lavorativa successiva
alla ricezione dell’ordine di pagamento (T+2), il prestatore di servizi
di pagamento che ha effettuato l’operazione provvede ad inviare al Nodo
dei Pagamenti-SPC il flusso di rendicontazione predisposto secondo lo
schema riportato nella successiva Tabella 4.

Le colonne *Liv*, *Gen*, *Occ* e *Len* della citata tabella assumono il
seguente significato:

+-------------+----------+-------------------------------------------------------------------------------+
| **colonna** | *Liv*    | indica il livello di                                                          |
|             |          | indentazione del dato al fine di rendere evidenti le strutture che contengono |
|             |          | ulteriori informazioni (colonna "Gen" uguale ad *s*): esempio, le strutture di|
|             |          | livello 1 sono formate da tutti i dati di livello superiore ad 1, quelle di   |
|             |          | livello 2 sono formate da tutti i dati di livello superiore a 2, e così via.  |
+-------------+----------+-------------------------------------------------------------------------------+
| **colonna** | *Gen*    | indica il genere (tipo) del dato da utilizzare; può assumere                  |
|             |          | i seguenti valori:                                                            |
|             |          |                                                                               |
|             |          | - s - struttura che può contenere altre strutture o dati,                     |
|             |          |                                                                               |
|             |          | - an - dato alfanumerico                                                      |
|             |          |                                                                               |
|             |          | - n - dato numerico.                                                          |
+-------------+----------+-------------------------------------------------------------------------------+
| **colonna** | *Occ*    | indica le “occorrenze” del dato nel formato **min..max.**                     |
+-------------+----------+-------------------------------------------------------------------------------+
| **colonna** | *Len*    | indica la lunghezza massima del dato nel formato                              |
|             |          | **min..max;** nel caso si tratti di una lunghezza fissa                       |
|             |          | comparirà solo il dato *len*, nel caso di lunghezze fisse                     |
|             |          | in alternativa la notazione sarà *len1 / len2.*                               |
+-------------+----------+-------------------------------------------------------------------------------+

**Tabella** **4 - Flusso per la rendicontazione - Schema dati**

+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| **Dato**                         | **Liv** | **Gen** | **Occ** | **Len** | **Contenuto**                                    |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| versioneOggetto                  | 1       | an      | 1..1    | 1..16   | Versione che identifica l’oggetto scambiato.     |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | Valori ammessi: **“1.0” e “1.1”**                |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| identificativoFlusso             | 1       | an      | 1..1    | 1..35   | Identificativo legato alla                       |
|                                  |         |         |         |         | generazione e trasmissione                       |
|                                  |         |         |         |         | del flusso di riversamento.                      |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | Deve essere univoco                              |
|                                  |         |         |         |         | nell’ambito dell’anno di                         |
|                                  |         |         |         |         | riferimento delle operazioni                     |
|                                  |         |         |         |         | di pagamento cui si                              |
|                                  |         |         |         |         | riferisce il flusso.                             |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | Per la composizione del dato si                  |
|                                  |         |         |         |         | faccia riferimento                               |
|                                  |         |         |         |         | al successivo paragrafo                          |
|                                  |         |         |         |         | :ref:`7.2 <stand-del-dato-identificativoflusso>` |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| dataOraFlusso                    | 1       | an      | 1..1    | 19      | Indica la data e ora di                          |
|                                  |         |         |         |         | creazione del flusso,                            |
|                                  |         |         |         |         | secondo il formato ISO 8601                      |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | **[YYYY]-[MM]-[DD]T[hh]:[mm]:[ss]**              |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| identificativoUnivocoRegolamento | 1       | an      | 1..1    | 1..35   | Riferimento assegnato dal prestatore di          |
|                                  |         |         |         |         | servizi di pagamento all’operazione di           |
|                                  |         |         |         |         | trasferimento fondi con la quale viene           |
|                                  |         |         |         |         | regolato contabilmente il riversamento           |
|                                  |         |         |         |         | delle somme incassate ovvero l’accumulo          |
|                                  |         |         |         |         | degli accrediti disposti dai clienti.            |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| dataRegolamento                  | 3       | an      | o       | 10      | Indica la data di esecuzione                     |
|                                  |         |         |         |         | dell’operazione di trasferimento                 |
|                                  |         |         |         |         | fondi con la quale viene regolato                |
|                                  |         |         |         |         | contabilmente il riversamento delle              |
|                                  |         |         |         |         | somme incassate, nel formato ISO                 |
|                                  |         |         |         |         | 8601 [YYYY]-[MM]-[DD].                           |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| istitutoMittente                 | 1       | s       | 1..1    |         | Aggregazione relativa al prestatore              |
|                                  |         |         |         |         | di servizi di pagamento mittente                 |
|                                  |         |         |         |         | che genera il presente flusso.                   |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| identificativoUnivocoMittente    | 2       | s       | 1..1    |         | Aggregazione che riporta le informazioni         |
|                                  |         |         |         |         | concernenti l’identificazione dell’Istituto      |
|                                  |         |         |         |         | mittente del flusso.                             |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| tipoIdentificativoUnivoco        | 3       | an      | 1..1    | 1       | Campo alfanumerico che descrive la               |
|                                  |         |         |         |         | codifica utilizzata per individuare              |
|                                  |         |         |         |         | l’Istituto Mittente; se presente può             |
|                                  |         |         |         |         | assumere i seguenti valori:                      |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | - **‘G’** = persona giuridica                    |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | - **‘A’** = Codice ABI                           |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | - **‘B’** = Codice BIC                           |
|                                  |         |         |         |         |   (standard ISO 9362)                            |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| codiceIdentificativoUnivoco      | 3       | an      | 1..1    | 1..35   | Campo alfanumerico che può contenere             |
|                                  |         |         |         |         | il codice fiscale o la partita IVA,              |
|                                  |         |         |         |         | il codice ABI o il codice BIC del                |
|                                  |         |         |         |         | prestatore di servizi di pagamento               |
|                                  |         |         |         |         | mittente, in funzione del dato                   |
|                                  |         |         |         |         | tipoIdentificativoUnivoco.                       |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| denominazioneMittente            | 2       | an      | 0..1    | 1..70   | Contiene la denominazione del                    |
|                                  |         |         |         |         | prestatore di servizi di pagamento               |
|                                  |         |         |         |         | mittente che genera il flusso.                   |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| codiceBicBancaDiRiversamento     | 2       | an      | 0..1    | 1..35   | Contiene il codice BIC del PSP che ha            |
|                                  |         |         |         |         | generato il SEPA Credit Transfer                 |
|                                  |         |         |         |         | di riversamento. Corrisponde al dato             |
|                                  |         |         |         |         | AT-09 del SCT.                                   |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| istitutoRicevente                | 1       | s       | 1..1    |         | Aggregazione relativa all’Ente                   |
|                                  |         |         |         |         | Creditore destinatario del flusso.               |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| identificativoUnivocoRicevente   | 2       | s       | 1..1    |         | Aggregazione che riporta le informazioni         |
|                                  |         |         |         |         | concernenti l’identificazione fiscale            |
|                                  |         |         |         |         | dell’Ente Creditore che riceve il flusso.        |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| tipoIdentificativoUnivoco        | 3       | an      | 1..1    | 1       | Campo alfanumerico che indica la natura          |
|                                  |         |         |         |         | dell’Ente Creditore; se presente deve            |
|                                  |         |         |         |         | assumere il valore **‘G’**,                      |
|                                  |         |         |         |         | Identificativo fiscale Persona Giuridica.        |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| codiceIdentificativoUnivoco      | 3       | an      | 1..1    | 1..35   | Campo alfanumerico contenente il                 |
|                                  |         |         |         |         | codice fiscale dell’Ente Creditore               |
|                                  |         |         |         |         | destinatario del flusso.                         |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| denominazioneRicevente           | 2       | an      | 0..1    | 1..70   | Contiene la denominazione dell’Ente              |
|                                  |         |         |         |         | Creditore che riceve il flusso.                  |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| numeroTotalePagamenti            | 1       | n       | 1..1    | 1..15   | Numero dei pagamenti presenti                    |
|                                  |         |         |         |         | nel flusso.                                      |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| importoTotalePagamenti           | 1       | n       | 1..1    | 1..18   | Importo totale dei pagamenti presenti            |
|                                  |         |         |         |         | nel flusso. Deve coincidere con la               |
|                                  |         |         |         |         | somma dei dati singoloImportoPagato              |
|                                  |         |         |         |         | presenti nel flusso.                             |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | **Deve essere maggiore di 0.**                   |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| datiSingoliPagamenti             | 1       | s       | 1 n     |         | Aggregazione con un numero di                    |
|                                  |         |         |         |         | occorrenze pari all’elemento                     |
|                                  |         |         |         |         | numeroTotalePagamenti                            |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| identificativoUnivocoVersamento  | 2       | an      | 1..1    | 1..35   | Riporta il dato codice IUV cui si                |
|                                  |         |         |         |         | riferisce il pagamento rendicontato              |
|                                  |         |         |         |         | nel flusso.                                      |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| identificativoUnivocoRiscossione | 2       | an      | 1..1    | 1..35   | Riferimento univoco dell’operazione              |
|                                  |         |         |         |         | assegnato al pagamento dal Prestatore            |
|                                  |         |         |         |         | dei servizi di Pagamento                         |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| indiceDatiSingoloPagamento       | 2       | n       | 0..1    | 1       | Indice dell’occorrenza del pagamento             |
|                                  |         |         |         |         | all’interno della struttura                      |
|                                  |         |         |         |         | datiSingoloPagamento                             |
|                                  |         |         |         |         | della Ricevuta Telematica.                       |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| singoloImportoPagato             | 2       | an      | 1..1    | 3..12   | Campo numerico indicante                         |
|                                  |         |         |         |         | l’importo relativo alla                          |
|                                  |         |         |         |         | somma pagata o revocata.                         |
|                                  |         |         |         |         | Deve essere diverso da 0.                        |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | Qualora il singolo importo                       |
|                                  |         |         |         |         | pagato è riferito                                |
|                                  |         |         |         |         | ad un pagamento revocato                         |
|                                  |         |         |         |         | (dato codiceEsitoSingoloPagamento =3)            |
|                                  |         |         |         |         | deve assumere un valore negativo.                |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| codiceEsitoSingoloPagamento      | 2       | n       | 1..1    | 1       | Campo numerico indicante l’esito                 |
|                                  |         |         |         |         | del pagamento. Può assumere i                    |
|                                  |         |         |         |         | seguenti valori:                                 |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | - **0** = Pagamento eseguito                     |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | - **3** = Pagamento revocato                     |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         |                                                  |
|                                  |         |         |         |         | - **9** = Pagamento eseguito                     |
|                                  |         |         |         |         |   in assenza di RPT                              |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+
| dataEsitoSingoloPagamento        | 2       | an      | 1..1    | 10      | Indica la data in cui è stato                    |
|                                  |         |         |         |         | disposto o revocato il pagamento,                |
|                                  |         |         |         |         | nel formato ISO 8601                             |
|                                  |         |         |         |         | [YYYY]-[MM]-[DD].                                |
+----------------------------------+---------+---------+---------+---------+--------------------------------------------------+

Per quanto riguarda gli Enti Creditori, tali flussi omogenei di dati
sono messi a loro disposizione attraverso l’infrastruttura di cui
all’articolo 5, comma 2 del CAD alla quale sono tenuti a collegarsi i
prestatori di servizi di pagamento che effettuano il riversamento, con
le modalità riportate nelle (Allegato B alle Linee guida).

Lo schema XML (XSD) descrittivo del contenuto dei file XML utilizzati
per trasferire le informazioni del flusso di rendicontazione è fornito
in formato elettronico nell’apposita sezione del sito dell’Agenzia per
l’Italia Digitale.

Si precisa che le Ricevute Telematiche soggette a “storno” o “revoca”
(`vedi rispettivamente §§ 2.1.4 <http://pagopa-specifichepagamenti.readthedocs.io/it/latest/_docs/Capitolo2.html#storno-del-pagamento>`_  
e `2.3 <http://pagopa-specifichepagamenti.readthedocs.io/it/latest/_docs/Capitolo2.html#revoca-della-ricevuta-telematica>`_  
delle *“Specifiche attuative del Nodo dei Pagamenti-SPC”*) devono essere sempre presenti nel flusso di
rendicontazione: il recupero di tali somme può avvenire contestualmente
nello stesso flusso o in un flusso successivo, in funzione del momento
di ricezione da parte del PSP dell’oggetto ER (“Esito Revoca”) avente
esito positivo.

Si sottolinea infine che, essendo il flusso di rendicontazione associato
ad un singolo SCT di riversamento, detto flusso è ovviamente sempre
correlato ad un unico codice IBAN di accredito.

.. _precisazioni-sulla-colonna-contenutodella-tabella-4:

7.1 Precisazioni sulla colonna “contenuto”della Tabella 4    |image18|    
---------------------------------------------------------

Tenuto presente che il significato dei dati richiesti per il flusso di
rendicontazione è riportato nella colonna “contenuto” della Tabella 4,
di seguito sono riportate alcune precisazioni sui dati presenti nel
flusso di rendicontazione:

**identificativoFlusso:** deve essere lo stesso riportato nel
componente **< idFlusso>** della causale del SEPA Credit Transfer di
Riversamento (dato “*Unstructured Remittance Information*” -
attributo AT-05, :ref:`vedi capitolo 6 <riversamento-agli-enti-creditori>`);

**identificativoUnivocoMittente:** la struttura deve coincidere con
quella presente nell’elemento identificativoUnivocoAttestante
indicato della RT rendicontata (`cfr. § 5.3.2 <http://pagopa-specifichepagamenti.readthedocs.io/it/latest/_docs/Capitolo5.html#ricevuta-telematica-rt>`_     dell’Allegato B alle Linee guida *“Specifiche Attuative del Nodo dei Pagamenti-SPC”*).

**identificativoUnivocoRegolamento:** ulteriore dato ‘non ambiguo’
utilizzato per abbinare il flusso di rendicontazione con l’accredito
ricevuto. Può contenere, in alternativa, uno dei seguenti dati
presenti nel SCT di riversamento (cfr. *SEPA Credit Transfert Scheme
Rulebook*):

- a) *Transaction Reference Number* (TRN, attributo AT-43 Originator
     Bank’s Reference), qualora il PSP, al momento della generazione
     del flusso di rendicontazione, disponga di tale dato;

- b) *EndToEndId* (attributo AT-41 Originator’s Reference), in caso
     contrario.

**identificativoUnivocoRiscossione:** rappresenta l’identificativo
con il quale il prestatore di servizi di pagamento individua la
singola operazione. Nel caso di utilizzo dell’infrastruttura di cui
all’articolo 81, comma 2-bis del CAD, tale informazione si riferisce
all’omonimo dato presente nella “Ricevuta Telematica” di cui alla
Sezione II delle , alle quali si rimanda per i dettagli;

**indiceDatiSingoloPagamento:** dato facoltativo che rappresenta la
i-esima occorrenza di pagamento all’interno della struttura
datiSingoloPagamento presente nell’oggetto RT (“Ricevuta
Telematica”) di cui alla Sezione II dell’Allegato B alle Linee guida;

**dataEsitoSingoloPagamento:** tale data deve coincidere con quella
dell’omologo dato presente nell’oggetto RT (“Ricevuta Telematica”) o
nell’elemento dataEsitoRevoca della struttura datiSingolaRevoca
presente nell’oggetto ER (“Esito Revoca”) di cui alla Sezione II
dell’Allegato B alle Linee guida .

.. _stand-del-dato-identificativoflusso:

7.2 Standardizzazione del dato identificativoFlusso 
---------------------------------------------------

Al fine di rendere omogenea la modalità di composizione del dato
identificativoFlusso presente nella causale standardizzata del SEPA
Credit Transfer (ref:`cfr. capitolo 6 <riversamento-agli-enti-creditori>`) ed anche nel flusso di rendicontazione
di cui ref:`al capitolo 7 <flusso-di-rendicontazione>` (cfr. Tabella 4 - Flusso per la rendicontazione -
Schema dati), sarà adottata la seguente struttura

**<data regolamento> <istituto mittente>”-“<flusso>**

dove i componenti sopra indicati assumono il seguente significato:


- **<data regolamento>** contiene le stesse informazioni dell’elemento dataRegolamento del file XML;


- **<istituto mittente>** contiene il codice del PSP che    predispone il flusso. Si precisa che tale 
codice deve coincidere con il dato identificativoPSP indicato dal PSP stesso nel 
“*Catalogo Dati Informativi*” di cui `al paragrafo 5.3.7 <http://pagopa-specifichepagamenti.readthedocs.io/it/latest/ 
_docs/Capitolo5.html#catalogo-dati-informativi>`_  della Sezione II dell’Allegato B alle Linee guida;

 
- **"-"** dato fisso;
                       

- **<flusso>** stringa alfanumerica che, insieme alle informazioni sopra indicate, consente di 
individuare univocamente il flusso stesso. I caratteri ammessi all’interno della stringa sono: numeri da 0 a 9, 
lettere dell’alfabeto latino maiuscole e minuscole ed seguenti caratteri.

+-------------------------------+-------------------+-------------+---------------------+
|                               | **ASCII**         | **Simbolo** | **Nome**            |
|                               +-------------------+             +                     +
|                               | **Dec** | **Hex** |             |                     |
|                               +---------+---------+-------------+---------------------+
|                               | 45      | 2D      | \-          | minus sign - hyphen |
|                               +---------+---------+-------------+---------------------+
|                               | 95      | 5F      | _           | underscore          |
+-------------------------------+---------+---------+-------------+---------------------+

Esempi: **2015-07-15xxxxxxxx-0000000001**

**2015-07-15xxxxxxxx-hh_mm_ss_nnn**


.. |pagoPA_logo| image:: media/header.png
.. |image17| image:: media/image7.png
   :width: 0.7874in
   :height: 0.22905in
.. |image18| image:: media/image7.png
   :width: 0.7874in
   :height: 0.22905in
