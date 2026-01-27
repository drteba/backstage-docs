# Arquitectura de referència de Salut. Arquitectura CTTI. Generalitat de Catalunya

[Saltar al contingut principal](#main)

*   [Inici](/)
*   [Arquitectura](/arquitectura/)
*   [Àmbits Departamentals](/arquitectura/ambits/)
*   [Departament de Salut](/arquitectura/ambits/salut/)
*   Arquitectura de referència de Salut

# Arquitectura de referència de Salut

* * *

## Context

L’**Àrea d’Arquitectura i Qualitat de Salut** presenta el seu manifest d’**arquitectura de referència** per garantir solucions escalables, segures i coherents, amb l’objectiu de millorar l’eficiència operativa i la disponibilitat dels serveis, reduir els riscos tecnològics, i facilitar la col·laboració entre equips.

Una arquitectura estandarditzada facilita l’escalabilitat i robustesa de les solucions, millora la seguretat, resiliència i fiabilitat, i permet optimitzar costos de desenvolupament i manteniment a llarg termini.

Aquestes decisions han de ser conegudes per els nostres proveïdors, i s’han de considerar de **compliment obligatori** per qualsevol desenvolupament o implantació d’una nova iniciativa de Salut, i estenen i amplien els principis d’arquitectura establerts pel CTTI:

*   [https://canigo.ctti.gencat.cat/arquitectura/principis/](https://canigo.ctti.gencat.cat/arquitectura/principis/)
*   [https://canigo.ctti.gencat.cat/arquitectura/manifest-cloud/](https://canigo.ctti.gencat.cat/arquitectura/manifest-cloud/)

La majoria d’aquestes decisions ja s’han anat comunicant i compartint dins l’àmbit del Departament de Salut, o també en les trobades trimestrals d’Arquitectura CTTI.

* * *

## Document de descripció de l’arquitectura (DA)

Es necessari formalitzar l’arquitectura d’una nova solució segons el format estàndard definit pel CTTI, i seguir el procediment d’**ISOL** impulsat per la **Unitat d’Integració de Solucions**.

Des de l’**octubre de 2025**, el CTTI ha establert l’**AiDA** com a eina única per presentar les descripcions d’arquitectura de noves solucions.

*   [https://canigo.ctti.gencat.cat/arquitectura/da/](https://canigo.ctti.gencat.cat/arquitectura/da/)

Addicionalment, des de l’Àmbit de Salut, hem publicat també un apartat de suport específic per als nostres proveïdors i lots d’aplicacions. Aquest espai està pensat per orientar els nous usuaris que utilitzen l’eina per primer cop per presentar una solució al Departament de Salut.

*   [https://canigo.ctti.gencat.cat/arquitectura/ambits/salut/](https://canigo.ctti.gencat.cat/arquitectura/ambits/salut/)

Es demana presentar les vistes de context i desplegament en format **C4model**:

*   [https://c4model.com/](https://c4model.com/)

No s’aprovaran DA’s que no compleixin uns mínims (apartats sense complimentar, informació inconsistent, incoherències respecte d’aquesta arquitectura de referència, comentaris sense resoldre, etc.).

* * *

## Descomposició en dominis funcionals

Cal plantejar enfocaments que permetin descompondre una solució en **dominis funcionals**, amb responsabilitat única de les seves dades i els serveis que exposa, segons un enfocament _Domain Driven Design_.

Cada domini ofereix una abstracció del seu coneixement respecte de la resta, mitjançant una API d’operacions o una integració asíncrona.

No es permeten interaccions ni acoblaments entre dominis a nivell de base de dades, ni tampoc compartir una mateixa base de dades a mode de monòlit. Es pretén evitar possibles punts de fallida únics amb afectació a tot el sistema.

[Image: Vista de desplegament de l’arquitectura de referència de Salut](https://converturltomd.com/images/ambits/salut/manifest/vista-desplegament-salut.png)

* * *

## Decisions sobre la tecnologia

Les iniciatives o dominis funcionals han de presentar una arquitectura desacoblada entre **presentació**, **negoci** i **dades**.

Els components de presentació i negoci han de complir les característiques d’un desplegament **cloud native**, que permetin elasticitat i autoescalat segons demanda, i també l’actualització o la substitució d’un component de forma autònoma, sense afectar tota la solució.

**Totes les capes** de l’arquitectura han d’oferir:

*   **Alta disponibilitat multizona**: amb una distribució balancejada dels recursos en diferents ubicacions, per oferir robustesa i resiliència davant d’una possible caiguda o fallida d’una ubicació única.
    
*   **Autoescalat horitzontal o vertical de recursos** configurable segons demanda, que ens permeti ser més sostenibles i eficients en costos gràcies a una despesa per consum en temps real (model OpEx), en lloc del pagament per reserva fixa (model CapEx).
    
*   Aturada planificada d’entorns no-productius fora d’horari laboral, també amb l’objectiu d’estalvi de recursos.
    

Per assegurar el compliment d’aquests requeriments, cal desplegar els components de la solució en **hiperescalars de núvol públic**. En aquest escenari, el proveïdor d’aplicació és responsable únic de la configuració, instal·lació i monitoratge end-to-end del sistema aprovisionat, i de garantir que no esdevenen costos inesperats per una mala definició de la infraestructura com a codi de la solució.

Tal com recullen els principis d’arquitectura de CTTI, cal donar preferència a **productes gestionats** (SaaS/DBaaS) o administrats pel propi proveïdor de núvol públic, davant desenvolupaments o instal·lacions a mida, per reduir esforços d’operativa i manteniment d’aquests.

* * *

## Arquitectura de frontals web

Existeixen en el mercat diferents _frameworks_ de presentació. Per garantir que les noves solucions de Salut puguin ser fàcilment integrables entre ells en forma de pàgina única, i evitar el manteniment o càrrega de múltiples versions d’estils, llibreries i components de presentació, establim que els nous desenvolupaments de frontals web hauran d’estar basats en el framework **React**.

*   **Microfrontals**: és obligatori utilitzar Single-SPA per a la implementació i configuració del component _Shell_ principal que hostatja els microfrontends incrustats en aquest.
    
*   **Components gràfics per frontals i microfrontals web**: cal utilitzar la llibreria de **Design System de Salut**:
    
    *   [https://codisisdisseny.salut.gencat.cat](https://codisisdisseny.salut.gencat.cat)

* * *

## Arquitectura de components de negoci

Establim per defecte una arquitectura basada en **serveis** de _backend_ orquestrats en forma de contenidors o funcions serverless.

Actualment disposem diferents implantacions de l’ecosistema Java (Sprint Boot, Quarkus, Kotlin), també .NET Core o Node/Javascript. Per processos de backend analítics també tenim casos en Python o R.

Aquest _backend_ de serveis d’un domini funcional pot estar desacoblat en diferents _microserveis_, en cas que requereixin una escalabilitat a mida o si són gestionats per diferents equips tècnics.

Malgrat això, els serveis o microserveis d’un mateix domini no haurien d’operar amb diferents motors de bases de dades concurrentment. En cas estrictament necessari: la solució ha d’oferir una recuperabilitat consistent i coordinada de les dades en aquests diferents motors, de manera que la possible pèrdua i restauració d’una BD no causi una descompensació amb les altres.

En el cas de contenidors, es prioritzaran solucions gestionades i administrades en la capa de _control-plane_: com _ECS Fargate_ o _EKS Fargate_ (AWS), _Container Apps_ o _AKS_ (Azure), _Cloud Run_ o _GKE_ (Google Cloud),…

Cal incorporar mecanismes de **Feature Toggles** que permetin activar o desactivar funcionalitats dinàmicament, sense requerir desplegaments o configuracions amb reinicis o talls de servei.

Com a mecanismes d’interoperabilitat entre diferents sistemes d’informació contemplarem:

*   **Interacció síncrona**: basada en la publicació de serveis exposats en forma d’API REST. La implementació del component que exposa l’API ha de possibilitar la generació de la documentació d’aquesta com a codi, segons l’especificació OpenAPI 3.
    
    *   [https://www.openapis.org/](https://www.openapis.org/)
    
    La majoria de fonts de dades centrals interoperen segons estàndards FHIR, openEHR, HL7, o IHE.
    
*   **Interacció asíncrona**: basada en la incorporació d’un sistema de publicació i subscripció d’esdeveniments en tòpics de missatges sota uns esquemes definits.
    
*   **Integració per frontend**: components web que consumeixen serveis de negoci amb requeriments de seguretat i d’autorització específics.
    

* * *

## Arquitectura de base de dades

### Base de dades operacionals

Establim **MongoDB Atlas** en modalitat _DBaaS_, com a motor de base de dades operacional de referència per qualsevol nova iniciativa en construcció.

*   [https://cloud.mongodb.com](https://cloud.mongodb.com)

Alguns dels motius que ens han portat a aquesta decisió són:

*   Models no estructurats i flexibles, ideals per arquitectures de serveis que generen i consumeixen objectes de dades.
*   Alta disponibilitat multi-zona o multi-cloud de les dades. Autoescalament vertical. Despesa per consum.
*   _OPS_ gestionades: encriptació en repòs amb clau pròpia (BYOK), _online archiving_, _point-in-time recovery_, aturada programada d’entorns no productius, _roadmap_ de versions.
*   _Query Insights_ i _Performance Advisor_.
*   Operacions més escalables i amb millor rendiment per grans volums de dades.
*   Plans de suport Professional i Enterprise pels entorns no productius i productius.
*   Tendències d’innovació com _Vector Search_, per integracions en projectes d’IA o analítics.

La cadena de connexió ha d’utilitzar sempre adreçaments privats hostatjats en el proveïdor de núvol públic, evitant l’accés a les dades directament per Internet.

*   [https://www.mongodb.com/docs/atlas/security-configure-private-endpoints/](https://www.mongodb.com/docs/atlas/security-configure-private-endpoints/)

### Bases de dades relacionals

En cas de necessitar una base de dades relacional (per requeriments justificats de caire tecnològic o funcional de la solució, i amb la corresponent aprovació d’Arquitectura), el motor escollit haurà de complir les característiques ja indicades d’**alta disponibilitat multizona**, **autoescalament**, i també **PITR** (_point-in-time recovery_), i **RPO** (_recovery point objective_) / **RTO** (_recovery time objective_) properes a zero.

També prioritzarem solucions gestionades davant instal·lacions a mida. Per exemple: _RDS Aurora Postgres_ (AWS), _Azure Database SQL_ (Azure) o _Cloud SQL_ (GoogleCloud).

### Bases de dades en memòria

Per a la persistència de dades de sessió, o magatzems en memòria cau d’informació de consulta recurrent) cal anteposar l’ús de solucions ja gestionades pel proveïdor de núvol públic on es desplega el sistema.

Si es requereix una solució a mida per un desplegament onprem o en cloud privat, la solució també haurà de complir les característiques d’alta disponibilitat i recuperabilitat de les dades.

### Bases de dades textuals

Disposem d’**Elastic Cloud** o **Algolia** com a DBaaS per donar cobertura a aquests requeriments.

### Processos de dades transaccionals vs analítics

Per dissenyar processos de replicació de dades entre diferents sistemes d’informació (CDC, ETL,…) disposem de la plataforma corporativa _Eventhub_ basada en Confluent Kafka. Tenim un ecosistema de **connectors Kafka Connect** per realitzar aquestes tasques, amb implementacions oficials segons l’origen de les dades (Oracle, MongoDB, Postgres…).

*   [https://canigo.ctti.gencat.cat/plataformes/interop\_connectors/](https://canigo.ctti.gencat.cat/plataformes/interop_connectors/)

No podem permetre que processos de caire analític puguin afectar el rendiment o la disponibilitat de processos transaccionals d’una aplicació o domini funcional. Per tant, sempre cal utilitzar solucions que es puguin executar en infraestructures desacoplades.

Pels sistemes en convivència temporal, s’ha de detallar el pla de desconnexió del sistema antic un cop el nou sistema que el substitueix ja assumeix tota la seva operativa i servei.

Per últim, a nivell de _data lakes_, disposem en el Departament de Salut de les iniciatives:

*   **DataWareHouse de Salut** per a l’explotació d’indicadors d’activitat i extracció de dades per analítica.
    
*   **Espai de Dades de Salut de Catalunya** pel tractament avançat de les dades, amb agents i sistemes complexos, i la estandarització, consolidació i govern de les dades.
    

* * *

## Observabilitat i monitorització

El CTTI ha establert el llibre blanc per definir els estàndards d’observabilitat aplicables per qualsevol nou sistema d’informació de Salut.

*   [https://canigo.ctti.gencat.cat/plataformes/observabilitat/](https://canigo.ctti.gencat.cat/plataformes/observabilitat/)

Principalment, els sistemes d’informació han de ser capaços de generar de manera homogènia els següents ítems:

*   Logs d’aplicació.
*   Mètriques de sistema i indicadors de negoci
*   Sondes de navegació o sondes d’invocació de serveis
*   Dependències d’altres sistemes

I integrar amb les eines transversals del CTTI la disponibilització d’aquestes dades, per implementar la monitorització amb els sistemes del Centre de Control, sobretot en el cas d’aplicacions classificades com a crítiques.

A més, dins el Departament estem treballant en la implantació d’una solució de _traçabilitat distribuïda_ que permeti l’agregació de traces correlacionades per serveis que interoperen entre ells.

* * *

## Components _core_ de Salut

Les solucions han d’integrar-se amb els principals sistemes estratègics tecnològics de Salut, en lloc d’implementar solucions a mida:

### Repositori de dades clíniques (RDC)

Plataforma de gestió del coneixement clínic, d’acord amb l’estàndard **openEHR**.

### Mestre de pacients (MPI)

Repositori de dades demogràfiques dels ciutadans, basat en estàndard **FHIR**.

### Servidor terminològic (ST)

Inventari de catàlegs de terminologies de Salut, basat en estàndard **FHIR**.

### Plataforma de seguretat de Salut (PDS)

Proveïdor d’autenticació i autorització transversal de Salut basat en l’estàndard **Oauth2/OIDC** o **SAML2**, que permet un model de fluxos d’autorització específics per cada iniciativa adherida, segons rols o atributs identificatius acordats en cada cas.

Ofereix una passarel·la delegada d’autenticació amb les eines corporatives VALID (ciutadans) i GICAR (professionals), i també la delegació a credencials de sistemes de Salut com GSA o ECAP.

*   [https://openid.net/connect/](https://openid.net/connect/)
*   [https://www.aoc.cat/es/serveis-aoc/valid/](https://www.aoc.cat/es/serveis-aoc/valid/)
*   [https://ctti.gencat.cat/ca/ctti/solucions-corporatives/gestio-didentitats/gicar/](https://ctti.gencat.cat/ca/ctti/solucions-corporatives/gestio-didentitats/gicar/)

### Plataforma d’auditoria (PAUD)

Repositori transversal d’esdeveniments d’auditoria basat en l’estàndard **ATNA FHIR**, amb publicació asíncrona des de les diferents iniciatives de Salut.

*   [https://hl7.org/fhir/R4/auditevent.html](https://hl7.org/fhir/R4/auditevent.html)

* * *

## Components _core_ del CTTI

Les solucions han d’integrar-se amb els principals components tecnològics del CTTI, en lloc d’implementar desenvolupaments a mida:

### Plataforma Kafka Eventhub

Com a broker per implementar comunicacions asíncrones entre sistemes d’informació, sobre tòpics amb un model d’autorització basat en MTLS i un registre d’esquemes basat en JSON, AVRO o altres models de serialització de missatges:

*   [https://canigo.ctti.gencat.cat/plataformes/eventhub/](https://canigo.ctti.gencat.cat/plataformes/eventhub/)

En sistemes que interoperen de forma asíncrona, és important revisar la configuració del _throughput_ d’escriptura o lectura de missatges als tòpics, per adaptar-se a una capacitat màxima que no permeti saturar els seus recursos.

### Api Manager CTTI

Plataforma corporativa de publicació i gestió d’API REST, segons un model de subscripció a aquestes basat en credencials pròpies del producte o integrat amb la Plataforma de Seguretat.

*   [https://canigo.ctti.gencat.cat/plataformes/apim/](https://canigo.ctti.gencat.cat/plataformes/apim/)

### Plataformes de CI/CD

És obligatori utilitzar els sistemes corporatius de desplegament i d’integració contínua del CTTI:

*   **SIC3.0** per a desplegaments en núvol privat o Api Manager:
    
    *   [https://canigo.ctti.gencat.cat/plataformes/sic/](https://canigo.ctti.gencat.cat/plataformes/sic/)
*   **SIC+** per a desplegaments al núvol públic:
    
    *   [https://canigo.ctti.gencat.cat/plataformes/ghec/](https://canigo.ctti.gencat.cat/plataformes/ghec/)

* * *

## Consideracions en la capa de networking

Cal ajustar-se al model de connectivitat i seguretat perimetral de NUS i CTTI en el que es coneix com a context de “NET0”: rangs d’adreçament CIDR enrutables respecte rangs no enrutables, proxies de sortida a internet i servidors DNS en cada proveïdor de núvol públic, tallafocs i regles de seguretat d’aplicació i web, publicacions i terminacions SSL segons domini Internet respecte domini Intranet, etc.

Tota comunicació híbrida entre sistemes desplegats on-premises o núvol privat i components en el núvol públic ha de ser gestionada a través de la **Coordinació TI de NUS** (Transit Gateway, Express Route, Google Interconnect…) per utilitzar la línia dedicada privada de la NET0.

És responsabilitat del proveïdor de l’aplicació entendre aquesta arquitectura de xarxa, i implementar els fluxos de comunicacions de la manera més òptima possible al respecte.

*   [https://canigo.ctti.gencat.cat/plataformes/public\_cloud/estandards/](https://canigo.ctti.gencat.cat/plataformes/public_cloud/estandards/)

### Connectivitat _Anella de Salut_ i al NET0

El Departament de Salut disposa del CIDR _146.219.0.0/16_ per publicacions pròpies d’àmbit intranet. Aquest rang permet evitar sol·lapaments amb les configuracions de xarxa privades de diferents seus o hospitals de l’ecosistema sanitari.

En cas de requerir una publicació d’anella per a un sistema d’informació desplegat dins la NET0, disposem del següent procediment acordat amb NUS al respecte:

*   [https://canigo.ctti.gencat.cat/arquitectura/ambits/salut/](https://canigo.ctti.gencat.cat/arquitectura/ambits/salut/)

* * *

## Resolució de discrepàncies en el disseny d’arquitectures

### Principi de Responsabilitat professional

L’arquitecte de l’integrador té la responsabilitat professional de comprendre i adherir-se als criteris establerts per l’Àrea d’Arquitectura i QA de Salut. Aquests criteris han estat publicats i formen part del marc contractual que ha de complir, respectar i aplicar en presentar una solució. En aquest sentit, els criteris són de coneixement previ i obligatori, fet que redueix, en la mesura del possible, les discrepàncies. Aquestes només s’iniciaran quan es plantegi una proposta molt innovadora i amb un valor afegit demostrable, aspecte que serà determinat per l’Àrea d’Arquitectura i QA de Salut.

### Procés de resolució de discrepàncies

En el cas que l’arquitecte de l’integrador elevi una discrepància, el procés a seguir és el següent:

1.  **Justificació d’innovació**: qualsevol discrepància presentada per l’arquitecte de l’integrador haurà de demostrar amb dades i evidències el seu caràcter innovador, així com el valor afegit específic que aportaria el sistema a desenvolupar per al Departament de Salut. Sense justificació la discrepància queda automàticament sense efectes i es continua el desenvolupament seguint el criteri comú de l’Àrea d’Arquitectura i QA.
    
2.  **Detecció i notificació**: quan l’integrador identifiqui una proposta innovadora que discrepi dels criteris establerts, haurà de notificar-ho per escrit a l’Àrea d’Arquitectura i QA mitjançant una anotació a la descripció d’arquitectura, en l’apartat de la justificació de les decisions d’arquitectura. L’integrador presentarà la seva proposta innovadora, acompanyada d’una justificació tècnica i d’impacte basada en dades contrastables.
    
3.  **Avaluació i resposta**: L’Àrea d’Arquitectura i QA avaluarà la proposta continguda al DA i emetrà una resposta en la validació del DA, en un màxim de 5 dies laborables. Aquesta resposta pot contenir una contraproposta d’arquitectura adaptada als criteris de l’Àrea d’Arquitectura i QA.
    
4.  **Decisió final**: en el cas de contraproposta, l’integrador disposarà de 2 dies laborables des de la recepció de la validació del DA per acceptar-la. Si no s’accepta, prevaldrà el criteri de l’Àrea d’Arquitectura i el desenvolupament continuarà sense més dilacions.
    
5.  **Comitè d’Escalat**: per a casos excepcionals, es convocarà un comitè d’escalat que prendrà una decisió en el termini de 24 hores després de la reunió del comitè, presidit pel Cap de l’Àrea d’Arquitectura i QA de Salut.
    

### Clàusula Antibloqueig i penalitzacions

1.  **Prohibició de discrepàncies injustificades**: es considerarà una pràctica inacceptable l’ús de discrepàncies sobre l’arquitectura no innovadores com a mecanisme per justificar retards o eludir responsabilitats contractuals.
    
2.  **Registre de discrepàncies**: l’Àrea d’Arquitectura i QA mantindrà un registre de les discrepàncies plantejades per cada integrador. Si s’observa que de forma reiterada un integrador promou les discrepàncies serà sotmès a un procediment d’escalat en els òrgans de direcció del contracte, prèvia advertència escrita.
    
3.  **Prevalença de la continuïtat del desenvolupament**: en cap cas una discrepància sobre l’arquitectura proposada justificarà retards en el lliurament del projecte. Si no s’arriba a un acord en els terminis establerts, el desenvolupament continuarà segons el criteri de l’Àrea d’Arquitectura i QA.
    

Aquest apartat busca fomentar una col·laboració constructiva orientada a la innovació real i desincentivar l’ús de la discrepància com a estratègia dilatòria o evasiva de responsabilitats professionals, especialment en un context d’utilització de recursos públics.

* * *

## Cloenda

Aquestes directrius tenen l’objectiu de garantir una arquitectura escalable, moderna i coherent en tots els nostres sistemes, essent d’obligat compliment. Us agrairem que tingueu en compte aquestes pautes per a qualsevol nova licitació, projecte o actualització.

Per a qualsevol dubte o aclariment, no dubteu a posar-vos en contacte amb nosaltres mitjançant el correu: [\[email protected\]](/cdn-cgi/l/email-protection#53322122263a273630272621327d20323f26271334363d3032277d303227).

* * *

Data d'actualització:   01-12-2025

[Image: Torna amunt](https://ctti.gencat.cat/web/resources/fwkResponsive/fpca_peu/img/chevron-up-w.svg)

[Edita](/admin/#/collections/arquitectura/entries/ambits/salut/manifest)