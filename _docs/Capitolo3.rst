
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

.. _formato-della-causale-di-versamento:

3. Formato della Causale di versamento 
======================================

La causale di versamento è il dato, predisposto dall’Ente Creditore, che
il pagatore o il soggetto versante deve indicare - insieme al codice
IBAN o al codice di conto corrente postale dell’Ente Creditore - al
proprio prestatore di servizi di pagamento.

Al fine di effettuare una riconciliazione automatica del versamento,
detta informazione dovrà essere composta secondo la struttura proposta
dall’Associazione Europea dei Tesorieri di Impresa (EACT) nel documento
`EACT FORMATTING RULES OF SEPA “UNSTRUCTURED” 140 CHRS FIELD FOR REMITTANCE INFORMATION <http://www.europeanpaymentscouncil.eu/content.cfm?page=eact_standard_for_unstructured_remittance_information>`_
e finalizzata al trattamento automatizzato delle informazioni tra partner commerciali.

In particolare, utilizzando questa configurazione, potranno essere
utilizzate due stringhe di caratteri alternative tra loro in funzione
della modalità di generazione del codice IUV da parte dell’Ente
Creditore (vedi capitolo 2):

+-------------------------------------------------+-----------------------------------------------------------------------+
| **/RFS/<IUV>/<importo>[/TXT/<descrizione >]**   | Schemi (D), (F)                                                       |  
|                                                 | (:ref:`vedi § 2.3 <codice-iuv-caso-pagamenti-ente-creditore>`)        |
+-------------------------------------------------+-----------------------------------------------------------------------+
| **/RFB/<IUV>[/<importo>][/TXT/<descrizione >]** | Schemi (A), (B), (C), (E)                                             |
|                                                 | :ref:`vedi §§ 2.2, <umero-avviso-e-codice-IUV-pagamenti-presso-psp>`) |
|                                                 | :ref:`§ 2.3 <codice-iuv-caso-pagamenti-ente-creditore>`)              |
+-------------------------------------------------+-----------------------------------------------------------------------+

Dove **“/RFS/”** e **“/RFB/”** sono costanti (*tag*), **<IUV>**
è l’Identificativo Univoco di Versamento di cui al precedente capitolo
2, mentre **<importo>** (facoltativo nel secondo caso) rappresenta
l’importo delle somme dovute, dove i decimali sono preceduti dal punto
anziché dalla virgola.

Infine il dato facoltativo **<descrizione>** può contenere una
descrizione testuale del pagamento stesso.

Nel caso di utilizzo del primo formato (cioè utilizzo dello standard ISO
11649) il codice IUV è presentato all’utilizzatore finale in gruppi di 4
caratteri separati da uno spazio, secondo quanto indicato nel paragrafo
6.1 del citato documento “RF Creditor reference” (vedi nota 5 a pagina
17).

Il formato indicato nel presente paragrafo dovrà essere riportato nel
dato “*Unstructured Remittance Information*” di cui al tracciato del
SEPA Credit Transfer nel caso di versamento effettuato tramite bonifico
ovvero nel campo causale nel caso di versamento effettuato tramite
bollettino di conto corrente postale.

.. _attività-facoltative-dei-prestatori-di-servizi-di-pagamento:

3.1 Attività facoltative dei prestatori di servizi di pagamento
---------------------------------------------------------------

Nel caso di utilizzo del primo formato indicato nel paragrafo precedente
(standard ISO 11649:2009) i prestatori di servizi di pagamento saranno
in grado, analizzando la stringa relativa alla causale di versamento, di
verificare sia la correttezza del dato **<check digits>** dello
“*Structured Creditor Reference*” sia la congruità del dato
“importo” presente nella stessa stringa, che deve coincidere con
l’importo dell’accredito da eseguire (SCT o bollettino postale).

Nel caso di utilizzo del secondo formato (cioè IUV diverso da formato
ISO 11649:2009) i prestatori di servizi di pagamento in fase di
generazione del SCT potranno completare detta stringa inserendo, sempre
nel limite di caratteri definiti per il dato in esame, eventuali
ulteriori comunicazioni al debitore inserendo il “*tag* ” **TXT**
secondo il seguente formato:

**/TXT/<testo libero>**

.. _esempi-di-composizione-della-stringa-di-formattazione:

3.2 Esempi di composizione della stringa di formattazione
---------------------------------------------------------

Di seguito si riportano alcuni esempi di stringhe di formattazione della
causale di versamento che devono essere generate dagli enti creditori ed
utilizzate nella disposizione di accredito (SCT):

**/RFS/RF23 5674 8393 7849 4505 5087 5/45.56**

la stringa riporta un pagamento il cui codice IUV è generato secondo
lo standard ISO 11649 ed il cui importo è di € 45,56. Si noti che lo
“*Structured Creditor Reference*” è riprodotto a gruppi di
quattro caratteri separati da uno spazio.

**/RFB/9876096598656344**

la stringa riporta un pagamento il cui codice IUV non è conforme
allo standard ISO 11649 ed è generato secondo un algoritmo
proprietario stabilito dall’amministrazione

**/RFB/9876096598656344/12.34/TXT/Richiesta certificato**

la stringa riporta un pagamento il cui codice IUV non è conforme allo
standard ISO 11649, il cui importo è di € 12,34 e contiene una
comunicazione del debitore inserita dal PSP successivamente
all’imputazione della disposizione di accredito (SCT).


.. |pagoPA_logo| image:: media/header.png
   
