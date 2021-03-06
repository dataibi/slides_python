
## Corso Python
### Contact & Sales S.r.l. e Ineko srl

+++

Una cosa accomuna Google, Star Wars e la Nasa: 

![Logo](assets/python_orig.png)

+++ 

Quale versione? 

![Logo](assets/python-2-vs-python-3.jpg)

+++

Ci sono attualmente due diverse versioni di Python: Python 2.x e Python 3.x. 

Le differenze tra le versioni sono importanti, quindi non c'è compatibilità tra il codice scritto in Python 2.x e quello scritto in Python 3.x. 

+++

Python 2.0 fu introdotto nel 2000

Python 3.0 è stato introdotto alla fine del 2008. A quel tempo moltissime librerie erano già state distribuite usando Python 2.

Gran parte della comunità  di sviluppatori non è passata immediatamente a Python 3.0 ed è rimasta "fedele" a Python 2.7. 

+++

Ad oggi quasi tutte le librerie più importanti sono state portate su Python 3

Python 2.7 è ancora mantenuto, quindi è possibile scegliere una o l'altra versione.

+++

## Integrated Development Environment (IDE)

### IDE comuni (PyCharm, Spider, ...)

### Web Integrated Development Environment (WIDE)

---

## Installare Python

+++

![Logo](assets/logo-anaconda.png)

+++

Ci sono due versioni della distribuzione di Anaconda:
* _Miniconda_ fornisce l'interprete Python, e anche uno strumento da riga di comando chiamato _conda_ che funge da gestore di pacchetti multipiattaforma, simile agli strumenti _apt_ o _yum_ che usano gli utenti Linux.
* _Anaconda_ include sia Python che _conda_ e in aggiunta include una suite di altri pacchetti preinstallati orientati verso l'elaborazione scientifica.

+++

https://www.anaconda.com/download/

+++

```sql

conda install ipython-notebook

```

---

## Iniziamo

+++

Alcune note di sintassi
* Commenti
* Terminare una istruzione 
* Indentare il codice (non solo per leggibilità)

+++

## Varibili e oggetti

+++

Assegnare il valore ad una variabile:

```python
x = 4
```

+++

Diffrenze con altri linguaggi di programmazione: 
* Varibili come puntatori
* Python è _dynamically-typed_

+++

Conseguenze delle variabili come puntatori

```python
x=[1,2,3] 
y=x
print(y)
x.append(4) # inseriamo 4 alla lista puntata da x 
print(y)
```

+++

```python
x = 'una stringa' 
print(y) # y non cambia
```

+++

Che succede se...

```python
x=10 
y=x
x += 5
print("x =", x)
print("y =", y)
```
+++

Numberi, stringhe, e altri tipi semplici sono immutabili.

Quando chiamiamo x += 5 non stiamo modificando il valore 5 dell'oggetto puntato da x, ma piuttosto stiamo cambiando l'oggetto a cui x punta. 

Per questo motivo il valore di y non è influenzato da questa operazione.

+++

Python è _dynamically-typed_

```python
x = 1 	      # x è un intero 
x = 'hello'   # x è una stringa 
x = [1, 2, 3] # x è una lista
```

+++

Questo non significa che Python è _type free_

```python
x = 1 	      # x è un intero 
type(x)
x = 'hello'   # x è una stringa 
type(x)
x = [1, 2, 3] # x è una lista
type(x)
```

+++

In Python, ogni cosa è un oggetto, questo significa che ogni entità ha attributi e metodi a essa associati. 
Gli attributi e i metodi vengono richiamati con la sintassi detta _dot syntax (.)_

Questo sembra ovvio per le liste (es. append), ma vale anche per i tipi semplici.

es:
```python
x=4.5
print(x.real, "+", x.imag, 'i')
x = 4.5
x.is_integer()
```

+++

## Operatori

+++

|Operator	|Name	|Description |
|-----------|-------|------------|
|a + b	|Addition	|Sum of a and b|
|a - b	|Subtraction	|Difference of a and b|
|a * b	|Multiplication	|Product of a and b|
|a / b	|True division	|Quotient of a and b|
|a // b	|Floor division	|Quotient of a and b, removing fractional parts|

+++

|Operator	|Name	|Description |
|-----------|-------|------------|
|a % b	|Modulus	|Integer remainder after division of a by b|
|a ** b	|Exponentiation	|a raised to the power of b|
|-a	|Negation	|The negative of a|
|+a	|Unary plus	|a unchanged (rarely used)|

+++

|Operator	|Name	|Description |
|-----------|-------|------------|
|a & b	|Bitwise AND	|Bits defined in both a and b |
|a pipe b	|Bitwise OR	|Bits defined in a or b or both |
|a ^ b	|Bitwise XOR	|Bits defined in a or b but not both |
|a << b	|Bit shift left	|Shift bits of a left by b units|
|a >> b	|Bit shift right	|Shift bits of a right by b units|
|~a	|Bitwise NOT	|Bitwise negation of a|

+++

|Operation	|Description		|Operation	Description|
|-----------|-------------------|----------------------|
|a == b	|a equal to b		|a != b	a not equal to b|
|a < b	|a less than b		|a > b	a greater than b|
|a <= b	|a less than or equal to b	|	a >= b	a greater than or equal to b|

+++

Tipi semplici

| Tipo	| Esempio |	Descrizione |
|-------|---------|-------------|
| int	|x = 1	  |numeri interi  |
|float	|x = 1.0  |	numeri reali |
|complex|	x = 1 + 2j	| numeri complessi |
|bool	|x = True |	booleani |
|str	|x = 'abc'|	Stringhe |
|NoneType|	x = None  |null |

+++

Gli interi Python sono un po' più sofisticati dei numeri interi in altri linguaggi come C. In C gli interi sono a precisione fissa, e di solito raggiungono un overflow a valori vicino a $2^{31}$ o $2^{63}$. Gli interi in Python sono a precisione variabili, ciò consente di calcoli che in altri linguaggi porterebbero ad un overflow:

```python
x = 2
2 ** 200

```

+++

Una caratteristica di Python (nota: versione 3) è che la divisione tra interi per default viene considerata come tipo floating-point:

In: 5/2
Out: 2.5

+++

Promemoria sui floating point:

La precisione dell'aritmentica floating-point è limitata, questo fa si che i testi di uguaglianza sono instabili. 

0.1+0.2==0.3 ?

N.B. Questo comportamento non dipende dal python!

+++

Numeri complessi:

```python
c = 3 + 4j
c.real
c.imag
c.conjugate()
abs(c)  # sqrt(c.real ** 2 + c.imag ** 2)
```

+++

Stringhe:
```python
s="Open Data"
s*3
s+" "+b
len(s)
s.upper()
s.lower()
s.find("open")
s.capitalize()
s.lower().find("open")
```
+++

Attenzione agli operatori sulle stringhe:
```python
s+5
s+str(5)
```
+++

Nota: le variabili non possono avere come nome le **Parole riservate**

and
assert
break
class
continue  else
def       except
del       exec
elif      finally
for      import    not
from     in        or
global   is        pass
if       lambda    print
raise
return
try
while

+++

### Strutture Dati (built-in)

| Nome | Esempio               | Descrizione                         |
|------|-----------------------|-------------------------------------|
| list | [1, 2, 3]             | Collezione mutabile di elementi     |
| tuple| (1, 2, 3)             | Collezione immutabile di elementi   |
| dict | {'a':1, 'b':2, 'c':3} | Mappa non ordinata (chiave, valore) |
| set  | {1, 2, 3}             | Insiemi non ordinato di valori unici|

+++

### Tutte le legislature per cui ci sono dati sulle votazioni
```sql
	SELECT ?leg WHERE {
		?votazione a ocd:votazione .
		?votazione ocd:rif_leg ?leg
	}
```

+++

### Tutte le legislature per cui ci sono dati sulle votazioni
```sql
	SELECT distinct ?leg WHERE {
		?votazione a ocd:votazione .
		?votazione ocd:rif_leg ?leg
	}
```

+++

```sql
	SELECT distinct * WHERE {
		?votazione a ocd:votazione; 
		dc:date ?data; 
		dc:title ?denominazione; 
		dc:description ?descrizione;
		ocd:votanti ?votanti;
		ocd:rif_leg <http://dati.camera.it/ocd/legislatura.rdf/repubblica_17>
	} 
	ORDER BY DESC(?data)
```

+++

## Query su ISTAT
http://datiopen.istat.it/sparqlIstat.php

+++

_lasciamo perdere...._

+++

_aspetta un attimo..._

+++

	http://datiopen.istat.it/sparql/oracle?query=<QUERY>&format=<FORMATO>

+++

	select * where { ?s ?p ?o } limit 10
	
https://meyerweb.com/eric/tools/dencoder/
	
	select%20*%20where%20%7B%20%3Fs%20%3Fp%20%3Fo%20%7D%20limit%2010

+++

http://datiopen.istat.it/sparql/oracle?query=select%20*%20where%20%7B%20%3Fs%20%3Fp%20%3Fo%20%7D%20limit%2010&format=csv

+++

	PREFIX ORACLE_SEM_FS_NS: <http://oracle.com/semtech#timeout=600,allow_dup=t,strict_default=f> 

	PREFIX+ORACLE_SEM_FS_NS%3A+%3Chttp%3A%2F%2Foracle.com%2Fsemtech%23timeout%3D600%2Callow_dup%3Dt%2Cstrict_default%3Df%3E%20

+++

http://datiopen.istat.it/sparql/oracle?query=PREFIX+ORACLE_SEM_FS_NS%3A+%3Chttp%3A%2F%2Foracle.com%2Fsemtech%23timeout%3D600%2Callow_dup%3Dt%2Cstrict_default%3Df%3E%20select%20*%20where%20%7B%20%3Fs%20%3Fp%20%3Fo%20%7D%20limit%2010&format=csv

+++

Comuni più alti d'Italia

```sql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX ter: <http://datiopen.istat.it/odi/ontologia/territorio/>
PREFIX cen: <http://datiopen.istat.it/odi/ontologia/censimento/>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#> 

SELECT  ?Comune ?Codice_Istat_Comune ?Provincia (replace(str(?Alt),"<http://www.w3.org/2001/XMLSchema#decimal>", "") as ?Altitudine) 
WHERE { 
	?com rdf:type ter:EntitaTerritoriale .
	?com ter:haNome ?Comune . 
	?com ter:haCodIstat ?Codice_Istat_Comune . 
	?com ter:haAltitudineMaxCOM ?Alt .
	?com ter:provincia_di_COM ?prov . 
	?prov ter:haNome ?Provincia .
	FILTER (?Alt > 4000)
} ORDER BY DESC (?Alt) 
```

+++

http://datiopen.istat.it/sparql/oracle?query=PREFIX+ORACLE_SEM_FS_NS%3A+%3Chttp%3A%2F%2Foracle.com%2Fsemtech%23timeout%3D600%2Callow_dup%3Dt%2Cstrict_default%3Df%3E%20PREFIX%20rdf%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E%0APREFIX%20rdfs%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0APREFIX%20ter%3A%20%3Chttp%3A%2F%2Fdatiopen.istat.it%2Fodi%2Fontologia%2Fterritorio%2F%3E%0APREFIX%20cen%3A%20%3Chttp%3A%2F%2Fdatiopen.istat.it%2Fodi%2Fontologia%2Fcensimento%2F%3E%0APREFIX%20qb%3A%20%3Chttp%3A%2F%2Fpurl.org%2Flinked-data%2Fcube%23%3E%0APREFIX%20xsd%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E%20%0ASELECT%20%20%3FComune%20%3FCodice_Istat_Comune%20%3FProvincia%20(replace(str(%3FAlt)%2C%22%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23decimal%3E%22%2C%20%22%22)%20as%20%3FAltitudine)%20%0AWHERE%20%7B%20%0A%3Fcom%20rdf%3Atype%20ter%3AEntitaTerritoriale%20.%0A%3Fcom%20ter%3AhaNome%20%3FComune%20.%20%0A%3Fcom%20ter%3AhaCodIstat%20%3FCodice_Istat_Comune%20.%20%0A%3Fcom%20ter%3AhaAltitudineMaxCOM%20%3FAlt%20.%0A%3Fcom%20ter%3Aprovincia_di_COM%20%3Fprov%20.%20%0A%3Fprov%20ter%3AhaNome%20%3FProvincia%20.%0AFILTER%20(%3FAlt%20%3E%204000)%0A%7D%20ORDER%20BY%20DESC%20(%3FAlt)+limit+10&format=csv

+++

Elenco località della provincia di Palermo con numero di stranieri di origine asiatica

```sql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX ter: <http://datiopen.istat.it/odi/ontologia/territorio/>
PREFIX cen: <http://datiopen.istat.it/odi/ontologia/censimento/>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#> 

SELECT  ?Localita (replace(str(?Stranieri),"<http://www.w3.org/2001/XMLSchema#decimal>", "") as ?Stranieri_origine_Asiatica) 
WHERE {
	?loc rdf:type ter:LOC . 
	?loc ter:haNome ?Localita .
	?loc ter:provincia_di_LOC ?prov .
	?loc ter:haIndicatoreCensimento ?o .   
	?o cen:provieneDa cen:Asia .
	?o cen:haStranieriApolidiResidentiItalia ?Stranieri.
	FILTER(?prov = <http://datiopen.istat.it/odi/risorsa/territorio/province/Palermo>) 
} ORDER BY DESC (?Stranieri)
```

+++

http://datiopen.istat.it/sparql/oracle?query=PREFIX+ORACLE_SEM_FS_NS%3A+%3Chttp%3A%2F%2Foracle.com%2Fsemtech%23timeout%3D600%2Callow_dup%3Dt%2Cstrict_default%3Df%3E%20PREFIX%20rdf%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F1999%2F02%2F22-rdf-syntax-ns%23%3E%0APREFIX%20rdfs%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2000%2F01%2Frdf-schema%23%3E%0APREFIX%20ter%3A%20%3Chttp%3A%2F%2Fdatiopen.istat.it%2Fodi%2Fontologia%2Fterritorio%2F%3E%0APREFIX%20cen%3A%20%3Chttp%3A%2F%2Fdatiopen.istat.it%2Fodi%2Fontologia%2Fcensimento%2F%3E%0APREFIX%20qb%3A%20%3Chttp%3A%2F%2Fpurl.org%2Flinked-data%2Fcube%23%3E%0APREFIX%20xsd%3A%20%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23%3E%20%0ASELECT%20%20%3FLocalita%20(replace(str(%3FStranieri)%2C%22%3Chttp%3A%2F%2Fwww.w3.org%2F2001%2FXMLSchema%23decimal%3E%22%2C%20%22%22)%20as%20%3FStranieri_origine_Asiatica)%20%0AWHERE%20%7B%0A%3Floc%20rdf%3Atype%20ter%3ALOC%20.%20%0A%3Floc%20ter%3AhaNome%20%3FLocalita%20.%0A%3Floc%20ter%3Aprovincia_di_LOC%20%3Fprov%20.%0A%3Floc%20ter%3AhaIndicatoreCensimento%20%3Fo%20.%20%20%20%0A%3Fo%20cen%3AprovieneDa%20cen%3AAsia%20.%0A%3Fo%20cen%3AhaStranieriApolidiResidentiItalia%20%3FStranieri.%0AFILTER(%3Fprov%20%3D%20%3Chttp%3A%2F%2Fdatiopen.istat.it%2Fodi%2Frisorsa%2Fterritorio%2Fprovince%2FPalermo%3E)%20%0A%7D%20ORDER%20BY%20DESC%20(%3FStranieri)%0A&format=csv

## Query su LinkedGeoData
http://linkedgeodata.org/sparql

+++

```sql
Prefix lgdo: <http://linkedgeodata.org/ontology/>
Prefix geom: <http://geovocab.org/geometry#>
Prefix ogc: <http://www.opengis.net/ont/geosparql#>
Prefix owl: <http://www.w3.org/2002/07/owl#>

Select * {
  ?s
    owl:sameAs <http://dbpedia.org/resource/Palermo> ;
    geom:geometry [
      ogc:asWKT ?sg
    ] .

  ?x
    a lgdo:Hospital ;
    rdfs:label ?l ;    
    geom:geometry [
      ogc:asWKT ?xg
    ] .


    Filter(bif:st_intersects (?sg, ?xg, 10)) .
}
```

+++

```sql
Prefix lgdo:<http://linkedgeodata.org/ontology/>
Prefix geom:<http://geovocab.org/geometry#>
Prefix ogc: <http://www.opengis.net/ont/geosparql#>
SELECT * WHERE {
    ?p a lgdo:Helipad ; geom:geometry/ogc:asWKT ?pgv .
    ?h a lgdo:Hospital; geom:geometry/ogc:asWKT ?hgv . 

    Filter(bif:st_intersects(?pgv, ?hgv, 0.5))
}
LIMIT 10
```
---

# Query Utili

+++

Chiedere a uno SPARQL Endpoint quali RDF Graphs sono disponibili

+++

```sql
	SELECT DISTINCT ?g
	WHERE {
		GRAPH ?g { ?s ?p ?o . }
	}
```

+++

Farsi restituire tutte le proprietà

+++

Farsi restituire tutte le classi (typi, utilizati)

---						

# Usare i risultati

+++

## Google spreadsheet	

+++				

	=IMPORTDATA("http://factforge.net/repositories/ff-news?query=%23+F4%3A+Top-level+industries+by+number+of+companies%0A%23+-+benefits+from+the+mapping+and+consolidation+of+industry+classifications%0A%23+++and+predicates+in+DBPedia+done+in+the+FactForge%0A%23+-+benefits+from+reasoning+-+transitive+and+symmetric+properties+across%0A%23+++the+industry+classification+taxonomy+of+FactForge%0A%0APREFIX+dbo%3A+%3Chttp%3A%2F%2Fdbpedia.org%2Fontology%2F%3E%0APREFIX+ff-map%3A+%3Chttp%3A%2F%2Ffactforge.net%2Fff2016-mapping%2F%3E%0A%0ASELECT+DISTINCT+%3Ftop_industry+(COUNT(*)+AS+%3Fcount)%0A%7B%0A+++%3Fcompany+dbo%3Aindustry+%3Findustry+.%0A+++%3Findustry+%5Eff-map%3AindustryVariant+%2F+ff-map%3AindustryCenter+%3Ftop_industry+.%0A%7D%0AGROUP+BY+%3Ftop_industry+ORDER+BY+DESC(%3Fcount)+")

+++

## cURL

+++
						
	curl -H Accept:text/tab-separated-values "http://factforge.net/repositories/ff-news?infer=true&sameAs=false&query=PREFIX+dbo%3A+%3Chttp%3A%2F%2Fdbpedia.org%2Fontology%2F%3E%0ASELECT+%3Findustry+%7B%24company+dbo%3Aindustry+%3Findustry%7D%0A&$company=<http://dbpedia.org/resource/Google>"

--- 

### e tanto altro ancora...
					
+++

Spraklis
					
http://www.irisa.fr/LIS/ferre/sparklis/
						
http://www.irisa.fr/LIS/ferre/sparklis/osparklis.html?endpoint=http%3A//dbpedia.org/sparql&regexp_hidden_URIs=%5E%28http%3A//www.w3.org/2002/07/owl%23%7Chttp%3A//www.openlinksw.com/%7CnodeID%3A//%7C%23%7Chttp%3A//www.wikidata.org/%29

+++

NLquery
http://nlquery.ayoungprogrammer.com/
						
Hokudai
http://wnews.ist.hokudai.ac.jp/wc3?search=Songs+written+by+Paul+McCartney
						
Quepy
http://quepy.machinalis.com/

+++

### Visualizziamo i risultati
