
# Notater fra STRUCTURED COMPUTER ORGANIZATION SIXTH EDITION


Basert på Odd Runes *TDT4160 Haust 2021 Pensum og
stikkord*.

Merk: dette vil bare inkludere informasjon som er ansett som "ikke-triviell".

Dette dokumentet ligger ute på [magne.dev](https://magne.dev/TDT4160)
- [Norwegian version](https://magne.dev/TDT4160/norwegian.html)
- [English version](https://magne.dev/TDT4160)

# Table of contents
<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

- [Notater fra STRUCTURED COMPUTER ORGANIZATION SIXTH EDITION](#notater-fra-structured-computer-organization-sixth-edition)
- [Table of contents](#table-of-contents)
- [Generelle prinsipper](#generelle-prinsipper)
  - [1.1 Strukturert dataorganisasjon](#11-strukturert-dataorganisasjon)
  - [2.1 Prosessorer](#21-prosessorer)
    - [2.1.2 Utførelse av instruksjoner](#212-utførelse-av-instruksjoner)
    - [2.1.3 RISC vs CISC](#213-risc-vs-cisc)
    - [2.1.4 Designprinsipper for moderne datamaskiner](#214-designprinsipper-for-moderne-datamaskiner)
    - [2.1.5 Parallellisme på instruksjonsnivå (ILP)](#215-parallellisme-på-instruksjonsnivå-ilp)
      - [Rørføring](#rørføring)
      - [Superskalararkitekturer](#superskalararkitekturer)
    - [2.1.6 Parallellitet på prosessornivå](#216-parallellitet-på-prosessornivå)
      - [Dataparallelle datamaskiner](#dataparallelle-datamaskiner)
      - [Multiprosessorer](#multiprosessorer)
      - [Multidatamaskiner](#multidatamaskiner)
  - [2.2 Primærminne](#22-primærminne)
    - [2.2.5 Bufferminne](#225-bufferminne)
      - [Lokalitetsprinsipp](#lokalitetsprinsipp)
      - [Gjennomsnittlig tilgangstid](#gjennomsnittlig-tilgangstid)
      - [Cache-design](#cache-design)
  - [2.3 Sekundært minne](#23-sekundært-minne)
    - [2.3.1 Minnehierarkier](#231-minnehierarkier)
  - [2.4 Inngang og utgang (I/O)](#24-inngang-og-utgang-io)
    - [2.4.1 Busser](#241-busser)
      - [Avbruddsbehandler](#avbruddsbehandler)
      - [Bussdommer](#bussdommer)
- [Digitalt logikknivå](#digitalt-logikknivå)
  - [3.2 Grunnleggende digitale logiske kretser](#32-grunnleggende-digitale-logiske-kretser)
    - [3.2.2 Kombinasjonskretser](#322-kombinasjonskretser)
      - [Multipleksere](#multipleksere)
      - [Dekodere](#dekodere)
    - [3.2.3 Aritmetiske kretser](#323-aritmetiske-kretser)
      - [Addere](#addere)
        - [Halvhugger](#halvhugger)
        - [Full adder](#full-adder)
        - [Ripple bære huggorm](#ripple-bære-huggorm)
  - [3.3 Minne](#33-minne)
    - [3.3.2 Flip-flops](#332-flip-flops)
    - [3.3.3 Registrerer](#333-registrerer)
    - [3.3.5 Minnebrikker](#335-minnebrikker)
    - [3.3.6 RAM-er og ROM-er](#336-ram-er-og-rom-er)
      - [SRAM vs DRAM](#sram-vs-dram)
      - [Ikke-flyktige minnebrikker (ROM-er)](#ikke-flyktige-minnebrikker-rom-er)
  - [3.4 CPU-brikker og busser](#34-cpu-brikker-og-busser)
    - [3.4.2 Databusser](#342-databusser)
      - [Bussprotokoll](#bussprotokoll)
    - [3.4.3 Bussbredde](#343-bussbredde)
      - [Multipleks buss](#multipleks-buss)
    - [3.4.4 Bussklokke](#344-bussklokke)
    - [3.4.5 Buss voldgift](#345-buss-voldgift)
    - [3.4.6 Bussdrift](#346-bussdrift)
      - [Blokker overføring](#blokker-overføring)
      - [Lese-endre-skrive busssyklus](#lese-endre-skrive-busssyklus)
      - [Avbryter](#avbryter)
- [Microarchitecture level](#microarchitecture-level)
  - [4.2 An example ISA: IJVM](#42-an-example-isa-ijvm)
    - [4.2.1 Stacks](#421-stacks)
    - [4.2.2 The IJVM memory model](#422-the-ijvm-memory-model)
    - [4.2.3 The IJVM instruciton set](#423-the-ijvm-instruciton-set)
  - [4.3 An example implementation](#43-an-example-implementation)
    - [4.3.1 Microinstructions and notation](#431-microinstructions-and-notation)
    - [4.3.2 Implementation of IJVM using the mic-1](#432-implementation-of-ijvm-using-the-mic-1)
  - [4.4 Design of the microarchitecture level](#44-design-of-the-microarchitecture-level)
    - [4.4.1 Speed versus cost](#441-speed-versus-cost)
    - [4.4.2 Reducing the execution path length](#442-reducing-the-execution-path-length)
    - [4.4.3 A design with prefetching: the mic-2](#443-a-design-with-prefetching-the-mic-2)
    - [4.4.4 A pipelined design: the mic-3](#444-a-pipelined-design-the-mic-3)
    - [4.4.5 A seven-stage pipeline: the mic-4](#445-a-seven-stage-pipeline-the-mic-4)
  - [4.5 Improving performance](#45-improving-performance)
    - [4.5.1 Cache memory](#451-cache-memory)
    - [4.5.2 Branch prediction](#452-branch-prediction)
  - [8.1 On-chip parallelism](#81-on-chip-parallelism)
    - [8.1.1 Instruction-level parallelism (ILA)](#811-instruction-level-parallelism-ila)
    - [8.1.2 On-chip multithreading](#812-on-chip-multithreading)
- [Instruction set architecture level (ISA)](#instruction-set-architecture-level-isa)
  - [5.1 Overview of the ISA level](#51-overview-of-the-isa-level)
    - [5.1.1 Properties of the ISA level](#511-properties-of-the-isa-level)
    - [5.1.2 Memory models](#512-memory-models)
    - [5.1.3 Registers](#513-registers)
  - [5.3 Instruction formats](#53-instruction-formats)
    - [5.3.1 Design criteria for instruction formats](#531-design-criteria-for-instruction-formats)
    - [5.3.1 Expanding opcodes](#531-expanding-opcodes)
  - [5.4 Addressing](#54-addressing)
  - [5.5 Instruction types](#55-instruction-types)
  - [5.6 Flow of control](#56-flow-of-control)
    - [5.6.1 Sequential flow of control and branches](#561-sequential-flow-of-control-and-branches)
    - [5.6.2 Procedures](#562-procedures)
  - [7.1 Introduction to the Assembly language](#71-introduction-to-the-assembly-language)
  - [7.3 The Assembly process](#73-the-assembly-process)
- [Virtual memory](#virtual-memory)
  - [6.1 Virtual memory](#61-virtual-memory)
    - [6.1.1 Paging](#611-paging)
    - [6.1.2 Implementation of paging](#612-implementation-of-paging)
    - [6.1.3 Demand paging and the working-set model](#613-demand-paging-and-the-working-set-model)
    - [6.1.4 Page-replacement policy](#614-page-replacement-policy)
    - [6.1.5 Page size and fragmentation](#615-page-size-and-fragmentation)

<!-- /code_chunk_output -->

# Generelle prinsipper

## 1.1 Strukturert dataorganisasjon

| Nivå | Beskrivelse
|---|---|
|5|Problemorientert språknivå
|4|Forsamlingsspråknivå
|3|Operativsystem maskinnivå (OS)
|2|Instruksjonssettarkitekturnivå (ISA)
|1|Mikroarkitekturnivå
|0|Digitalt logikknivå

Merk at de følgende delene (etter *Generelle prinsipper*) er dedikert til de tre nederste nivåene, som starter med nivå null.

## 2.1 Prosessorer

### 2.1.2 Utførelse av instruksjoner
1. Hent neste instruksjon fra minnet til instruksjonsregisteret.
2. Endre programtelleren til å peke på følgende instruksjon.
3. Bestem hvilken type instruksjon som nettopp er hentet.
4. Hvis instruksjonen bruker et ord i minnet, avgjør hvor det er.
5. Hent ordet, om nødvendig, inn i et CPU-register.
6. Utfør instruksjonen.
7. Gå til trinn 1 for å begynne å utføre følgende instruksjon.

Denne sekvensen av trinn blir ofte referert til som hente-dekode-utfør-syklusen. Det er sentralt for driften av alle datamaskiner.

### 2.1.3 RISC vs CISC
Vi mener RISC er best, men det er spørsmålet om bakoverkompatibilitet og milliarder av dollar selskaper har investert i programvare for Intel-linjen (CISC).

RISC|CISC
---|---
Få, enkle og generelle instruksjoner|Mange, komplekse og spesialiserte instruksjoner
Registrer-til-registrer, LOAD/STORE-arkitektur| Minne-til-minne, last/lager innlemmet i instruksjoner
Få sykluser per instruksjon|Mange sykluser per instruksjon

### 2.1.4 Designprinsipper for moderne datamaskiner
- Alle instruksjoner utføres direkte av maskinvare
- Maksimer hastigheten som instruksjoner utstedes med
– Instruksjoner skal være enkle å avkode
- Bare laster og lagrer skal referere til minne
- Gi mange registre

Disse kalles noen ganger RISC-designprinsippene.

### 2.1.5 Parallellisme på instruksjonsnivå (ILP)
Dataarkitekter streber hele tiden etter å forbedre ytelsen til maskinene de designer. Å få brikkene til å løpe raskere ved å øke klokkehastigheten er én måte, men for hvert nytt design er det en grense for hva som er mulig med brute force i det øyeblikket i historien. Følgelig ser de fleste dataarkitekter på parallellisme (å gjøre to eller flere ting samtidig) som en måte å få enda mer ytelse for en gitt klokkehastighet. Ved parallellisme på instruksjonsnivå utnyttes parallellisme innenfor individuelle instruksjoner for å få flere instruksjoner per sekund ut av maskinen.

#### Rørføring
Det har vært kjent i årevis at selve henting av instruksjoner fra minnet er en stor flaskehals i instruksjonsutførelseshastigheten. I en pipeline er instruksjonsutførelse ofte delt inn i mange (ofte et dusin eller flere) deler, hver enkelt håndteres av en dedikert maskinvare, som alle kan kjøre parallelt. Pipelining tillater en avveining mellom *latens* (hvor lang tid det tar å utføre en instruksjon), og *prosessorbåndbredde* (hvor mange instruksjoner som kan utføres per sekund). Den maksimale klokkefrekvensen til CPUen bestemmes av det tregeste stadiet i rørledningen.

#### Superskalararkitekturer
Definisjonen av "superskalar" har utviklet seg noe over tid. Det brukes nå til å beskrive prosessorer som gir flere instruksjoner - ofte fire eller seks - i en enkelt klokkesyklus. Selvfølgelig må en superskalar CPU ha flere funksjonelle enheter å gi alle disse instruksjonene til.

### 2.1.6 Parallellitet på prosessornivå
Parallellitet på instruksjonsnivå hjelper litt, men pipelining og superskalardrift vinner sjelden mer enn en faktor på fem eller ti. For å få gevinster på 50, 100 eller mer, er den eneste måten å designe datamaskiner med flere CPUer, så vi skal nå se på hvordan noen av disse er organisert.

#### Dataparallelle datamaskiner
Et betydelig antall problemer innen beregningsdomener som fysiske vitenskaper, ingeniørvitenskap og datagrafikk involverer løkker og matriser, eller har på annen måte en svært regelmessig struktur. Ofte utføres de samme beregningene gjentatte ganger på mange forskjellige sett med data. Regelmessigheten og strukturen til disse programmene gjør dem spesielt enkle mål for å øke hastigheten gjennom parallell utførelse. To primære metoder har blitt brukt for å utføre disse svært vanlige programmene raskt og effektivt: SIMD-prosessorer og vektorprosessorer.

- En *Single Instruction-stream Multiple Data-stream* eller SIMD-prosessor består av et stort antall identiske prosessorer som utfører samme sekvens av instruksjoner på forskjellige sett med data.

- En *vektorprosessor* ser for programmereren veldig ut som en SIMD-prosessor. Som en SIMD-prosessor er den veldig effektiv til å utføre en sekvens av operasjoner på par av dataelementer. Men i motsetning til en SIMD-prosessor, utføres alle operasjonene i en enkelt funksjonell enhet med kraftig pipeline.
- 
#### Multiprosessorer
Behandlingselementene i en dataparallell prosessor er ikke uavhengige CPUer, siden det bare er én kontrollenhet som deles mellom dem alle. Vårt første parallelle system med flere fullverdige CPUer er multiprosessoren, et system med mer enn én CPU som deler et felles minne, som en gruppe mennesker i et rom som deler en felles tavle. Siden hver CPU kan lese eller skrive hvilken som helst del av minnet, må de koordinere (i programvare) for å unngå å komme i veien for hverandre.

#### Multidatamaskiner
Selv om multiprosessorer med et beskjedent antall prosessorer (≤ 256) er relativt enkle å bygge, er store overraskende vanskelige å konstruere. Vanskeligheten er å koble så mange prosessorer til minnet. For å omgå disse problemene har mange designere ganske enkelt forlatt ideen om å ha et delt minne og bare bygge systemer som består av et stort antall sammenkoblede datamaskiner, som hver har sitt eget private minne, men ikke noe felles minne. Disse systemene kalles multidatamaskiner. CPU-ene i en multidatamaskin sies å være *løst koblet*, for å kontrastere dem med de *tett koblede* multiprosessor-CPUene.

## 2.2 Primærminne
Minnet er den delen av datamaskinen der programmer og data er lagret.

### 2.2.5 Bufferminne
Historisk sett har CPUer alltid vært raskere enn minner. Hva denne ubalansen betyr i praksis er at etter at CPUen har sendt ut en minneforespørsel, vil den ikke få ordet den trenger i mange CPU-sykluser. Jo tregere minnet er, jo flere sykluser må CPU-en vente.

Problemet er faktisk ikke teknologi, men økonomi. Ingeniører vet hvordan de skal bygge minner som er like raske som CPUer, men for å kjøre dem i full hastighet, må de være plassert på CPU-brikken (fordi det går veldig tregt å gå over bussen til minnet). Det vi foretrekker er en stor mengde raskt minne til en lav pris. Interessant nok er teknikker kjent for å kombinere en liten mengde raskt minne med en stor mengde sakte minne for å få hastigheten til det raske minnet (nesten) og kapasiteten til det store minnet til en moderat pris. Det lille, raske minnet kalles en cache.

Den grunnleggende ideen bak en cache er enkel: de mest brukte minneordene holdes i cachen. Når CPU-en trenger et ord, ser den først i hurtigbufferen. Bare hvis ordet ikke er der, går det til hovedminnet. Hvis en betydelig del av ordene er i hurtigbufferen, kan den gjennomsnittlige tilgangstiden reduseres kraftig.

#### Lokalitetsprinsipp
Lokalitetsprinsippet er observasjonen at minnereferansene gjort i et hvilket som helst kort tidsintervall har en tendens til å bruke bare en liten brøkdel av det totale minnet.

- Temporal Locality: Programmer har en tendens til å få tilgang til de samme dataene gjentatte ganger over tid. Det vil si, hvis et program har brukt en variabel nylig, vil det sannsynligvis bruke den variabelen igjen snart.

- Romlig lokalitet: Programmer har en tendens til å få tilgang til data som er i nærheten av andre tidligere tilgang til data. "Nærliggende" refererer her til dataens minneadresse. For eksempel, hvis et program får tilgang til data på adressene N og N+4, vil det sannsynligvis få tilgang til N+8 snart.

Den generelle ideen er at når et ord refereres, blir det og noen av dets naboer hentet fra det store sakte minnet inn i hurtigbufferen, slik at neste gang det brukes, kan det nås raskt.

#### Gjennomsnittlig tilgangstid
La $c$ være cachetilgangstiden, $m$ hovedminnets tilgangstid og $h$ treffforholdet. Vi kan beregne gjennomsnittlig tilgangstid som følger:
$$t_{mean} = c + (1 - t)m$$

#### Cache-design
1. **Cachestørrelse**: jo større cache, desto bedre presterer den, men jo tregere er den å få tilgang til og jo mer koster den.
2. **Cachelinjestørrelse**: Eksempel: en 16-KB cache kan deles opp i 1024 linjer på 16 byte, 2048 linjer på 8 byte og andre kombinasjoner.
3. **Organisering av cachen**: hvordan holder cachen styr på hvilke minneord som for øyeblikket lagres?
4. **Enhet eller delt hurtigbuffer**: bør instruksjoner og data bruke samme hurtigbuffer?
5. **Antall cacher**: Det er vanlig i disse dager å ha brikker med en primær cache på brikke, en sekundær cache av brikke, men i samme pakke som CPU-brikken, og en tredje cache enda lenger unna (L1, L2, L3).

## 2.3 Sekundært minne
Uansett hvor stort hovedminnet er, er det generelt alt for lite til å holde alle dataene folk ønsker å lagre.

### 2.3.1 Minnehierarkier
![En visualisering av minnehierarkiet](https://diveintosystems.org/book/C11-MemHierarchy/_images/MemoryHierarchy.png)
Credit: https://diveintosystems.org/book/C11-MemHierarchy/mem_hierarchy.html
## 2.4 Inngang og utgang (I/O)
Som vi nevnte i begynnelsen av dette kapittelet, har et datasystem tre hovedkomponenter: CPU, minnene (primær og sekundær) og I/O (Input/Output).

### 2.4.1 Busser
Eksterne enheter utveksler informasjon med CPU-en på samme måte som vi vanligvis utveksler informasjon i en datamaskin, gjennom *busser*.

#### Avbruddsbehandler
En kontroller som leser eller skriver data til eller fra minnet uten CPU-intervensjon sies å utføre *Direct Memory Access* (DMA). Når overføringen er fullført, forårsaker kontrolleren normalt et *avbrudd*, som tvinger CPU-en til umiddelbart å stanse kjøringen av sitt nåværende program og begynne å kjøre en spesiell prosedyre, kalt en *avbruddsbehandler*, for å se etter feil, utføre eventuelle spesielle handlinger som trengs, og informer operativsystemet om at I/U-en nå er ferdig. Når avbruddsbehandleren er ferdig, fortsetter CPU med programmet som ble suspendert da avbruddet skjedde.

#### Bussdommer
Hva skjer hvis CPU og en I/O-kontroller vil bruke bussen samtidig? Svaret er at en brikke som kalles en bussdommer bestemmer hvem som går videre. Generelt gis I/O-enheter foretrukket fremfor CPU, fordi disker og andre bevegelige enheter ikke kan stoppes, og å tvinge dem til å vente vil resultere i tapte data. Når ingen I/O er i gang, kan CPUen ha alle busssyklusene for seg selv til å referere til minnet.

# Digitalt logikknivå

## 3.2 Grunnleggende digitale logiske kretser

### 3.2.2 Kombinasjonskretser

#### Multipleksere
En multiplekser er en krets med $2^n$ datainnganger, en datautgang og $n$ kontrollinnganger som velger en av datainngangene.

#### Dekodere
En dekoder er en krets som tar et $n$-bit nummer som input og bruker det til å velge (dvs. satt til $1$) nøyaktig en av $2^n$ utgangslinjene.

### 3.2.3 Aritmetiske kretser

#### Addere

##### Halvhugger
En halv adderer tar to 1-bits innganger $A$ og $B$ og gir ut $S$, summen av inngangene, og $C$, bærebiten. Den er bygget av én OG-port og én XOR-port.

##### Full adder
En full adderer tar tre 1-bits innganger $A$, $B$ og $C_{in}$, (carry in) og gir ut $S$, summen av inngangene, og $C_{out}$, carry-en bit. Den er bygget av to halvhuggormer.

##### Ripple bære huggorm
For å bygge en adderer for for eksempel to 16-bits ord, replikerer man bare hele adderen 16 ganger. Bæren av et bitt brukes som bære inn til venstre nabo. Bæren inn i biten lengst til høyre kobles til 0. Denne typen adderer kalles en *rippelbæreadderer*, fordi i verste fall, ved å legge til 1 til 111...111 (binær), kan addisjonen ikke fullføres før bæren har kruset hele veien fra biten lengst til høyre til biten lengst til venstre. Addere som ikke har denne forsinkelsen, og dermed er raskere, finnes også og foretrekkes vanligvis.
## 3.3 Minne

### 3.3.2 Flip-flops
I mange kretser er det nødvendig å sample verdien på en bestemt linje på et bestemt tidspunkt og lagre den. I denne varianten, kalt en flip-flop, skjer tilstandsovergangen ikke når klokken er 1, men under klokkeovergangen fra 0 til 1 (stigende flanke) eller fra 1 til 0 (fallende flanke) i stedet. Dermed er lengden på klokkepulsen uviktig, så lenge overgangene skjer raskt.

### 3.3.3 Registrerer
Flip-flops kan kombineres i grupper for å lage registre som inneholder datatyper som er større enn 1 bit i lengde.

### 3.3.5 Minnebrikker
En minnebrikke trenger vanligvis en adressebuss, databuss og noen få styresignaler. CS (chip select) brukes til å velge (aktivere) brikken.

### 3.3.6 RAM-er og ROM-er

#### SRAM vs DRAM
RAM-er kommer i to varianter, statisk og dynamisk. Statiske RAM-er
(SRAM-er) er konstruert internt ved å bruke kretser som ligner på vår grunnleggende D-flip-flop. Disse minnene har den egenskapen at innholdet beholdes så lenge strømmen holdes på: sekunder, minutter, timer, til og med dager. Statiske RAM-er er veldig raske. En typisk tilgangstid er i størrelsesorden et nanosekund eller mindre. Av denne grunn er statiske RAM-er populære som cache-minne. Dynamiske RAM-er (DRAM-er), derimot, bruker ikke flip-flops. I stedet er en dynamisk RAM en rekke celler, hver celle inneholder en transistor og en liten kondensator. Kondensatorene kan lades eller utlades, slik at 0-er og 1-ere kan lagres. Fordi den elektriske ladningen har en tendens til å lekke ut, må hver bit i en dynamisk RAM oppdateres (lastes på nytt) med noen millisekunder for å forhindre at dataene lekker bort. Fordi ekstern logikk må ta seg av oppfriskningen, krever dynamiske RAM-er mer komplekse grensesnitt enn statiske, selv om denne ulempen i mange applikasjoner kompenseres for av deres større kapasitet. Siden dynamiske RAM-er bare trenger én transistor og én kondensator per bit (mot seks transistorer per bit for best statisk RAM), har dynamiske RAM-er en veldig høy tetthet (mange biter per brikke). Av denne grunn er hovedminner nesten alltid bygget ut av dynamiske RAM-er. Denne store kapasiteten har imidlertid en pris: dynamiske RAM-er er trege (titalls nanosekunder). Dermed forsøker kombinasjonen av en statisk RAM-cache og et dynamisk RAM-hovedminne å kombinere de gode egenskapene til hver.

#### Ikke-flyktige minnebrikker (ROM-er)
RAM er ikke den eneste typen minnebrikker. I mange applikasjoner, som leker, apparater og biler, må programmet og noen av dataene forbli lagret selv når strømmen er slått av. Videre, når det er installert, endres verken programmet eller dataene noen gang. Disse kravene har ført til utviklingen av ROM-er (Read-Only Memories), som ikke kan endres eller slettes, med vilje eller på annen måte. Dataene i en ROM settes inn under fremstillingen, hovedsakelig ved å eksponere et fotosensitivt materiale gjennom en maske som inneholder det ønskede bitmønsteret og deretter etse bort den eksponerte (eller ueksponerte) overflaten. Den eneste måten å endre programmet i en ROM er å erstatte hele brikken.

## 3.4 CPU-brikker og busser

### 3.4.2 Databusser
En buss er en felles elektrisk vei mellom flere enheter. Busser kan kategoriseres etter funksjon. De kan brukes internt i CPU-en for å transportere data til og fra ALU, eller eksterne til CPU-en for å koble den til minne eller til I/O-enheter. Hver type buss har sine egne krav og egenskaper.

#### Bussprotokoll
For å gjøre det mulig for tavler designet av tredjeparter å feste seg til systembussen, må det være godt definerte regler for hvordan den eksterne bussen fungerer, som alle enheter som er koblet til den skal følge. Disse reglene kalles *bussprotokollen*.

Noen enheter som kobles til en buss er aktive og kan starte bussoverføringer, mens andre er passive og venter på forespørsler. De aktive kalles *mestere*; de passive kalles *slaver*. Når CPUen beordrer en diskkontroller til å lese eller skrive en blokk, fungerer CPU som en master og diskkontrolleren fungerer som en slave.

### 3.4.3 Bussbredde
Jo flere adresselinjer en buss har, jo mer minne kan CPU adressere direkte. Hvis en buss har $n$ adresselinjer, kan en CPU bruke den til å adressere $2^n$ forskjellige minneplasseringer.

#### Multipleks buss
Derfor er den vanlige tilnærmingen for å forbedre ytelsen å legge til flere datalinjer. Som du kanskje forventer, fører imidlertid ikke denne inkrementelle veksten til et rent design til slutt. For å omgå problemet med veldig brede busser, velger noen ganger designere en multipleksbuss. I denne utformingen, i stedet for at adresse- og datalinjene er separate, er det for eksempel 32 linjer for adresse og data sammen. Ved oppstart av en bussdrift brukes linjene til adressen. Senere brukes de til data. For en skriv til minne betyr dette for eksempel at adresselinjene må settes opp og forplantes til minnet før dataene kan settes på bussen. Multipleksing av linjene reduserer bussbredden (og kostnadene), men resulterer i et tregere system.
### 3.4.4 Bussklokke
Busser kan deles inn i to forskjellige kategorier avhengig av klokkeslett. En *synkron buss* har en linje drevet av en krystalloscillator. Signalet på denne linjen består av en firkantbølge med en frekvens vanligvis mellom 5 og 133 MHz. Alle bussaktiviteter tar et integrert antall av disse syklusene, kalt busssykluser. Den andre typen buss, *asynkron buss*, har ikke en masterklokke. Busssykluser kan være av hvilken som helst lengde som kreves og trenger ikke være den samme mellom alle par med enheter.

### 3.4.5 Buss voldgift
"Hva skjer hvis to eller flere enheter alle ønsker å bli bussmester samtidig?" Svaret er at det trengs en eller annen buss-voldgiftsmekanisme for å forhindre kaos. Voldgiftsmekanismer kan være sentraliserte eller desentraliserte. I sentralisert voldgift bestemmer en enkelt bussdommer hvem som går videre. Desentralisert voldgift kan implementeres på flere måter, men det innebærer vanligvis at enhetene må sjekke om bussen er gratis å bruke før den tas i bruk.

### 3.4.6 Bussdrift

#### Blokker overføring
Ofte kan blokkoverføringer gjøres mer effektive enn suksessive individuelle overføringer. Når en blokklesing startes, forteller bussmasteren slaven hvor mange ord som skal overføres, for eksempel ved å sette ordtellingen på datalinjene. I stedet for bare å returnere ett ord, sender slaven ut ett ord i løpet av hver syklus til tellingen er oppbrukt.

#### Lese-endre-skrive busssyklus
Lar enhver CPU lese et ord fra minnet, inspisere og endre det, og skrive det tilbake til minnet, alt uten å slippe bussen. Denne typen syklus forhindrer konkurrerende CPU-er fra å kunne bruke bussen og dermed forstyrre den første CPU-driften.

#### Avbryter
Når CPU-en kommanderer en I/O-enhet til å gjøre noe, forventer den vanligvis et avbrudd når arbeidet er gjort. Avbruddssignaleringen krever bussen. Siden flere enheter kanskje vil forårsake et avbrudd samtidig, er det samme type voldgiftsproblemer som vi hadde med vanlige busssykluser. Den vanlige løsningen er å tildele prioriteringer til enheter og bruke en sentralisert arbiter for å prioritere de mest tidskritiske enhetene.

# Microarchitecture level

## 4.2 An example ISA: IJVM
*Low priority*
### 4.2.1 Stacks
*Low priority*
### 4.2.2 The IJVM memory model
*Low priority*
### 4.2.3 The IJVM instruciton set
*Low priority*

## 4.3 An example implementation

### 4.3.1 Microinstructions and notation

### 4.3.2 Implementation of IJVM using the mic-1

## 4.4 Design of the microarchitecture level

### 4.4.1 Speed versus cost

### 4.4.2 Reducing the execution path length

### 4.4.3 A design with prefetching: the mic-2

### 4.4.4 A pipelined design: the mic-3

### 4.4.5 A seven-stage pipeline: the mic-4

## 4.5 Improving performance

### 4.5.1 Cache memory

### 4.5.2 Branch prediction

## 8.1 On-chip parallelism

### 8.1.1 Instruction-level parallelism (ILA)

### 8.1.2 On-chip multithreading

# Instruction set architecture level (ISA)

## 5.1 Overview of the ISA level

### 5.1.1 Properties of the ISA level

### 5.1.2 Memory models

### 5.1.3 Registers

## 5.3 Instruction formats

### 5.3.1 Design criteria for instruction formats

### 5.3.1 Expanding opcodes

## 5.4 Addressing
`TODO: Addressing modes 5.4.2-5.4.7`

## 5.5 Instruction types
`TODO: Instruction types 5.5.1-5.5.7`

## 5.6 Flow of control

### 5.6.1 Sequential flow of control and branches

### 5.6.2 Procedures

## 7.1 Introduction to the Assembly language
*Regarded as trivial.*

## 7.3 The Assembly process
*Regarded as trivial.*

# Virtual memory

## 6.1 Virtual memory

### 6.1.1 Paging

### 6.1.2 Implementation of paging

### 6.1.3 Demand paging and the working-set model

### 6.1.4 Page-replacement policy

### 6.1.5 Page size and fragmentation
 