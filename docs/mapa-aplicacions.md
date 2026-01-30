```mermaid
graph TB
  linkStyle default fill:#ffffff

  subgraph diagram ["System Landscape View"]
    style diagram fill:#ffffff,stroke:#ffffff

    subgraph group1 ["Serveis Externs Core"]
      style group1 fill:#ffffff,stroke:#cccccc,color:#cccccc,stroke-dasharray:5

      1["<div style='font-weight: bold'>CDR/RDC</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Repositori Dades Clíniques.<br />Plataforma de gestió del<br />coneixement clínic d'acord<br />amb l'estàndard openEHR</div>"]
      style 1 fill:#ffffff,stroke:#444444,color:#444444
      10["<div style='font-weight: bold'>ECAP</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Sistema d'informació per<br />Atenció Primària</div>"]
      style 10 fill:#ffffff,stroke:#444444,color:#444444
      11["<div style='font-weight: bold'>SIRE</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Sistema de recepta<br />electrònica</div>"]
      style 11 fill:#ffffff,stroke:#444444,color:#444444
      12["<div style='font-weight: bold'>FHES</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Habilitador de Formularis del<br />HES</div>"]
      style 12 fill:#ffffff,stroke:#444444,color:#444444
      13["<div style='font-weight: bold'>LMS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Portal d'aplicacions de Salut<br />per al ciutadà</div>"]
      style 13 fill:#ffffff,stroke:#444444,color:#444444
      14["<div style='font-weight: bold'>RGV ARGOS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Registre de Variables<br />Clíniques i laboratori</div>"]
      style 14 fill:#ffffff,stroke:#444444,color:#444444
      2["<div style='font-weight: bold'>MPI</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Mestre de Pacients segons<br />l'estàndard FHIR R4</div>"]
      style 2 fill:#ffffff,stroke:#444444,color:#444444
      3["<div style='font-weight: bold'>SERVIDOR TERMILOGIC (IS3)</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Repositori de catàlegs<br />terminològics segons<br />estàndard FHIR R4</div>"]
      style 3 fill:#ffffff,stroke:#444444,color:#444444
      4["<div style='font-weight: bold'>PDS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Plataforma de Seguretat.<br />Proveïdor transversal<br />d'identitat i accés, basat en<br />tokens OpenId Connect o SAML,<br />i compatible amb models<br />RBAC/ABAC d'autorització</div>"]
      style 4 fill:#ffffff,stroke:#444444,color:#444444
      5["<div style='font-weight: bold'>PAUD</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Plataforma de Auditoria.<br />Component transversal<br />d'auditoria segons<br />l'estàndard ATNA FHIR<br />AuditEvent</div>"]
      style 5 fill:#ffffff,stroke:#444444,color:#444444
      6["<div style='font-weight: bold'>EVENTHUB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Plataforma Eventhub. Broker<br />transversal de missatgeria<br />asíncrona sobre Kafka<br />Confluent, per donar suport a<br />dissenys d'arquitectura<br />basats en esdeveniments</div>"]
      style 6 fill:#ffffff,stroke:#444444,color:#444444
      7["<div style='font-weight: bold'>SAP ARGOS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HIS de l'ICS basat en SAP</div>"]
      style 7 fill:#ffffff,stroke:#444444,color:#444444
      8["<div style='font-weight: bold'>HC3</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Història Clínica Compartida<br />de Catalunya</div>"]
      style 8 fill:#ffffff,stroke:#444444,color:#444444
      9["<div style='font-weight: bold'>GICAR</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Gestió d’identitats i control<br />d’accés als recursos de<br />persones que interactuen amb<br />els sistemes d’informació.</div>"]
      style 9 fill:#ffffff,stroke:#444444,color:#444444
    end

    subgraph group2 ["Sistema ARGOS"]
      style group2 fill:#ffffff,stroke:#cccccc,color:#cccccc,stroke-dasharray:5

      15[("<div style='font-weight: bold'>CERCADOR DIAGNÒSTICS DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>ElasticSearch</div>")]
      style 15 fill:#005571,stroke:#003b4f,color:#ffffff
      16["<div style='font-weight: bold'>CERCADOR DIAGNÒSTICS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Cercador de diagnòstics basat<br />en tecnologia Lucent</div>"]
      style 16 fill:#0d5091,stroke:#093865,color:#ffffff
      19[("<div style='font-weight: bold'>ARGOSTECA DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MySQL</div>")]
      style 19 fill:#00758f,stroke:#005164,color:#ffffff
      20["<div style='font-weight: bold'>ARGOSTECA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Plataforma reproducció vídeos<br />en Streaming</div>"]
      style 20 fill:#0d5091,stroke:#093865,color:#ffffff
      23["<div style='font-weight: bold'>GESTIÓ VISITES</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Enviar un SMS que contindrà<br />un enllaç</div>"]
      style 23 fill:#0d5091,stroke:#093865,color:#ffffff
      25[("<div style='font-weight: bold'>RGV DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDb</div>")]
      style 25 fill:#47a248,stroke:#317132,color:#ffffff
      26["<div style='font-weight: bold'>RGV</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Registre de Variables<br />Clíniques i laboratori</div>"]
      style 26 fill:#0d5091,stroke:#093865,color:#ffffff
      30[("<div style='font-weight: bold'>ETC DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB</div>")]
      style 30 fill:#47a248,stroke:#317132,color:#ffffff
      31[("<div style='font-weight: bold'>ETC DB REDIS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Redis</div>")]
      style 31 fill:#d82c20,stroke:#971e16,color:#ffffff
      32["<div style='font-weight: bold'>ETC</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Estació de Treball Clínica de<br />Argos</div>"]
      style 32 fill:#0d5091,stroke:#093865,color:#ffffff
      37["<div style='font-weight: bold'>ETINF</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Estació Treball d'Infermeria<br />de Argos</div>"]
      style 37 fill:#0d5091,stroke:#093865,color:#ffffff
      41[("<div style='font-weight: bold'>ETEPAT DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgrSQL</div>")]
      style 41 fill:#336791,stroke:#234865,color:#ffffff
      42[("<div style='font-weight: bold'>ETEPAT DB 2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>ElasticSearch</div>")]
      style 42 fill:#005571,stroke:#003b4f,color:#ffffff
      43["<div style='font-weight: bold'>ETPAT</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Sistema d’Informació<br />d’Anatomia Patològica</div>"]
      style 43 fill:#0d5091,stroke:#093865,color:#ffffff
      48["<div style='font-weight: bold'>PUBLICADOR DADES</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Publicar variables clíniques<br />i escales funcionals a HC3 a<br />partir de les dades<br />registrades prèviament a RGV</div>"]
      style 48 fill:#0d5091,stroke:#093865,color:#ffffff
      53[("<div style='font-weight: bold'>ALBA DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDbAtlas</div>")]
      style 53 fill:#47a248,stroke:#317132,color:#ffffff
      54["<div style='font-weight: bold'>ALBA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Entorn descriptiu,<br />diagnòstic, predictiu i<br />prescriptiu de lactivitat<br />quirúrgica hospitalària</div>"]
      style 54 fill:#0d5091,stroke:#093865,color:#ffffff
      57[("<div style='font-weight: bold'>ETPAT_SISCAT DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 57 fill:#336791,stroke:#234865,color:#ffffff
      58["<div style='font-weight: bold'>ETPAT SISCAT</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Sistema d’informació per la<br />coordinació de les actuacions<br />de salut laboral</div>"]
      style 58 fill:#0d5091,stroke:#093865,color:#ffffff
      64[("<div style='font-weight: bold'>RIS_SISCAT DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>SqlServer</div>")]
      style 64 fill:#a91d22,stroke:#761417,color:#ffffff
      65["<div style='font-weight: bold'>RIS SISCAT</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>RIS de serveis de radiologia<br />i medicina nuclear</div>"]
      style 65 fill:#0d5091,stroke:#093865,color:#ffffff
    end

    subgraph group3 ["Sistema HES"]
      style group3 fill:#ffffff,stroke:#cccccc,color:#cccccc,stroke-dasharray:5

      103[("<div style='font-weight: bold'>HES FORMULARIS DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Oracle</div>")]
      style 103 fill:#f80000,stroke:#ad0000,color:#ffffff
      104[("<div style='font-weight: bold'>HES FORMULARIS DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 104 fill:#336791,stroke:#234865,color:#ffffff
      105["<div style='font-weight: bold'>HES FORMULARIS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Aplicació que permeti crear<br />formularis web de forma<br />dinàmica. Així com permetre<br />la governança de publicació<br />de nous formularis</div>"]
      style 105 fill:#0d5091,stroke:#093865,color:#ffffff
      110[("<div style='font-weight: bold'>HES LANDING PAGE DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 110 fill:#336791,stroke:#234865,color:#ffffff
      111["<div style='font-weight: bold'>HES LANDING PAGE</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Plana d'inici integrada en<br />ECAP</div>"]
      style 111 fill:#0d5091,stroke:#093865,color:#ffffff
      120[("<div style='font-weight: bold'>HES SERVIDOR RECURSOS DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB Atlas</div>")]
      style 120 fill:#47a248,stroke:#317132,color:#ffffff
      121["<div style='font-weight: bold'>HES SERVIDOR RECURSOS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES - Servidor de recursos</div>"]
      style 121 fill:#0d5091,stroke:#093865,color:#ffffff
      126[("<div style='font-weight: bold'>HES PLANS ACCIÓ ADMINISTRATIUS DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDbAtlas</div>")]
      style 126 fill:#47a248,stroke:#317132,color:#ffffff
      127[("<div style='font-weight: bold'>HES PLANS ACCIÓ ADMINISTRATIUS DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>AmazonElasticCache</div>")]
      style 127 fill:#005571,stroke:#003b4f,color:#ffffff
      128["<div style='font-weight: bold'>HES PLANS ACCIÓ ADMINISTRATIUS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES - Plans d'acció<br />administratius</div>"]
      style 128 fill:#0d5091,stroke:#093865,color:#ffffff
      135[("<div style='font-weight: bold'>HES CENTRE D'AJUDA I MOTOR DE CERCA DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB Atlas</div>")]
      style 135 fill:#47a248,stroke:#317132,color:#ffffff
      136[("<div style='font-weight: bold'>HES CENTRE D'AJUDA I MOTOR DE CERCA DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>ElasticSearch</div>")]
      style 136 fill:#005571,stroke:#003b4f,color:#ffffff
      137["<div style='font-weight: bold'>HES CENTRE D'AJUDA I MOTOR DE CERCA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES - Centre d'ajuda i motor<br />de cerca</div>"]
      style 137 fill:#0d5091,stroke:#093865,color:#ffffff
      143[("<div style='font-weight: bold'>HES CENTRE CONFIGURACIÓ DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 143 fill:#336791,stroke:#234865,color:#ffffff
      144[("<div style='font-weight: bold'>HES CENTRE CONFIGURACIÓ DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Redis</div>")]
      style 144 fill:#d82c20,stroke:#971e16,color:#ffffff
      145["<div style='font-weight: bold'>HES CENTRE CONFIGURACIÓ</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES - Centre de configuració</div>"]
      style 145 fill:#0d5091,stroke:#093865,color:#ffffff
      151[("<div style='font-weight: bold'>HES IMMUNITZACIONS DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 151 fill:#336791,stroke:#234865,color:#ffffff
      152["<div style='font-weight: bold'>HES IMMUNITZACIONS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES Immunitzacions</div>"]
      style 152 fill:#0d5091,stroke:#093865,color:#ffffff
      160[("<div style='font-weight: bold'>HES VISOR DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Oracle</div>")]
      style 160 fill:#f80000,stroke:#ad0000,color:#ffffff
      161["<div style='font-weight: bold'>HES VISOR</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Visor del HES</div>"]
      style 161 fill:#0d5091,stroke:#093865,color:#ffffff
      170[("<div style='font-weight: bold'>HES eCONSULTA DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Oracle</div>")]
      style 170 fill:#f80000,stroke:#ad0000,color:#ffffff
      171[("<div style='font-weight: bold'>HES eCONSULTA DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDb</div>")]
      style 171 fill:#47a248,stroke:#317132,color:#ffffff
      172["<div style='font-weight: bold'>HES eCONSULTA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES eConsulta</div>"]
      style 172 fill:#0d5091,stroke:#093865,color:#ffffff
      177[("<div style='font-weight: bold'>HES RDC DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDb</div>")]
      style 177 fill:#47a248,stroke:#317132,color:#ffffff
      178[("<div style='font-weight: bold'>HES RDC DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 178 fill:#336791,stroke:#234865,color:#ffffff
      179["<div style='font-weight: bold'>HES RDC</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES RDC</div>"]
      style 179 fill:#0d5091,stroke:#093865,color:#ffffff
      187[("<div style='font-weight: bold'>HES SISTEMA EXPERT DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 187 fill:#336791,stroke:#234865,color:#ffffff
      188["<div style='font-weight: bold'>HES SISTEMA EXPERT</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Nou sistema “expert” de<br />prescripció farmacèutica</div>"]
      style 188 fill:#0d5091,stroke:#093865,color:#ffffff
      193[("<div style='font-weight: bold'>HES ECAP DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 193 fill:#336791,stroke:#234865,color:#ffffff
      194["<div style='font-weight: bold'>HES ECAP</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Comunicacions amb ECAP</div>"]
      style 194 fill:#0d5091,stroke:#093865,color:#ffffff
      200[("<div style='font-weight: bold'>HES PRESCRIPCIÓ DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 200 fill:#336791,stroke:#234865,color:#ffffff
      201[("<div style='font-weight: bold'>HES PRESCRIPCIÓ DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Redis</div>")]
      style 201 fill:#d82c20,stroke:#971e16,color:#ffffff
      202["<div style='font-weight: bold'>HES PRESCRIPCIÓ</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Prescripció</div>"]
      style 202 fill:#0d5091,stroke:#093865,color:#ffffff
      211[("<div style='font-weight: bold'>HES PLATAFORMA DE SEGURETAT DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 211 fill:#336791,stroke:#234865,color:#ffffff
      212["<div style='font-weight: bold'>HES PLATAFORMA DE SEGURETAT</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Plataforma de Seguretat</div>"]
      style 212 fill:#0d5091,stroke:#093865,color:#ffffff
      217[("<div style='font-weight: bold'>HES PROMs DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 217 fill:#336791,stroke:#234865,color:#ffffff
      218["<div style='font-weight: bold'>HES PROMs</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Patient Reported Outcome<br />Measure</div>"]
      style 218 fill:#0d5091,stroke:#093865,color:#ffffff
      226[("<div style='font-weight: bold'>HES CONSENTIMENT INFORMAT DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 226 fill:#336791,stroke:#234865,color:#ffffff
      227["<div style='font-weight: bold'>HES CONSENTIMENT INFORMAT</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Custodia dels documents amb<br />els que els ciutadans donen<br />la seva conformitat davant un<br />procés mèdic</div>"]
      style 227 fill:#0d5091,stroke:#093865,color:#ffffff
      234[("<div style='font-weight: bold'>HES PROBS DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDb</div>")]
      style 234 fill:#47a248,stroke:#317132,color:#ffffff
      235["<div style='font-weight: bold'>HES PROBS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Gestió del procés Obstètric</div>"]
      style 235 fill:#0d5091,stroke:#093865,color:#ffffff
      245[("<div style='font-weight: bold'>HES MPI DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Oracle</div>")]
      style 245 fill:#f80000,stroke:#ad0000,color:#ffffff
      246[("<div style='font-weight: bold'>HES MPI DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDb</div>")]
      style 246 fill:#47a248,stroke:#317132,color:#ffffff
      247["<div style='font-weight: bold'>HES MPI</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Master Patient Index</div>"]
      style 247 fill:#0d5091,stroke:#093865,color:#ffffff
      252[("<div style='font-weight: bold'>HES VACUNES DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 252 fill:#336791,stroke:#234865,color:#ffffff
      253["<div style='font-weight: bold'>HES VACUNES</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Gestió de Vacunes</div>"]
      style 253 fill:#0d5091,stroke:#093865,color:#ffffff
      262[("<div style='font-weight: bold'>HES PROGRAMACIÓ PER MOTIUS DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 262 fill:#336791,stroke:#234865,color:#ffffff
      263[("<div style='font-weight: bold'>HES PROGRAMACIÓ PER MOTIUS DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDb</div>")]
      style 263 fill:#47a248,stroke:#317132,color:#ffffff
      264["<div style='font-weight: bold'>HES PROGRAMACIÓ PER MOTIUS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Programació per Motius</div>"]
      style 264 fill:#0d5091,stroke:#093865,color:#ffffff
      270[("<div style='font-weight: bold'>HES ALERTES I NOTIFICACIONS DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 270 fill:#336791,stroke:#234865,color:#ffffff
      271["<div style='font-weight: bold'>HES ALERTES I NOTIFICACIONS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Alertes i Notificacions</div>"]
      style 271 fill:#0d5091,stroke:#093865,color:#ffffff
      278[("<div style='font-weight: bold'>HES PLANIFICAT ADMINISTRATIU DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 278 fill:#336791,stroke:#234865,color:#ffffff
      279["<div style='font-weight: bold'>HES PLANIFICAT ADMINISTRATIU</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Planificat Administratiu</div>"]
      style 279 fill:#0d5091,stroke:#093865,color:#ffffff
      287[("<div style='font-weight: bold'>HES ALÈRGIES I REACCIONS ADVERSES DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 287 fill:#336791,stroke:#234865,color:#ffffff
      288[("<div style='font-weight: bold'>HES ALÈRGIES I REACCIONS ADVERSES DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Redis</div>")]
      style 288 fill:#d82c20,stroke:#971e16,color:#ffffff
      289["<div style='font-weight: bold'>HES ALÈRGIES I REACCIONS ADVERSES</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Alèrgies i Reaccions Adverses</div>"]
      style 289 fill:#0d5091,stroke:#093865,color:#ffffff
      300[("<div style='font-weight: bold'>HES GOD DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 300 fill:#336791,stroke:#234865,color:#ffffff
      301[("<div style='font-weight: bold'>HES GOD DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDb</div>")]
      style 301 fill:#47a248,stroke:#317132,color:#ffffff
      302["<div style='font-weight: bold'>HES GOD</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Gestió de l’Oferta i la<br />Demanda</div>"]
      style 302 fill:#0d5091,stroke:#093865,color:#ffffff
      310[("<div style='font-weight: bold'>HES CIPDS DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB Atlas</div>")]
      style 310 fill:#47a248,stroke:#317132,color:#ffffff
      311[("<div style='font-weight: bold'>HES CIPDS DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Amazon Elastic Cache</div>")]
      style 311 fill:#005571,stroke:#003b4f,color:#ffffff
      312["<div style='font-weight: bold'>HES CIPDS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Condicionants i Problemes de<br />Salut</div>"]
      style 312 fill:#0d5091,stroke:#093865,color:#ffffff
      320[("<div style='font-weight: bold'>HES TST Servidor Terminològic DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB Atlas</div>")]
      style 320 fill:#47a248,stroke:#317132,color:#ffffff
      321[("<div style='font-weight: bold'>HES TST Servidor Terminològic DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>AWS ElasticCache</div>")]
      style 321 fill:#005571,stroke:#003b4f,color:#ffffff
      322["<div style='font-weight: bold'>HES TST Servidor Terminològic</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Servidor Terminològic al<br />Cloud AWS</div>"]
      style 322 fill:#0d5091,stroke:#093865,color:#ffffff
      328[("<div style='font-weight: bold'>HES DISP DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB Atlas</div>")]
      style 328 fill:#47a248,stroke:#317132,color:#ffffff
      329["<div style='font-weight: bold'>HES DISP</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Dispensacions</div>"]
      style 329 fill:#0d5091,stroke:#093865,color:#ffffff
      339["<div style='font-weight: bold'>HES HISTORIAL SALUT CATALUNYA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Historial Salut Catalunya</div>"]
      style 339 fill:#0d5091,stroke:#093865,color:#ffffff
      346[("<div style='font-weight: bold'>HES FARMA (TFAR) DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 346 fill:#336791,stroke:#234865,color:#ffffff
      347[("<div style='font-weight: bold'>HES FARMA (TFAR) DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>AmazonOpenSearch</div>")]
      style 347 fill:#005571,stroke:#003b4f,color:#ffffff
      348["<div style='font-weight: bold'>HES FARMA (TFAR)</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Farma</div>"]
      style 348 fill:#0d5091,stroke:#093865,color:#ffffff
      357["<div style='font-weight: bold'>HES EDA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>eda</div>"]
      style 357 fill:#0d5091,stroke:#093865,color:#ffffff
      362[("<div style='font-weight: bold'>HES CONNECTA DB1</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 362 fill:#336791,stroke:#234865,color:#ffffff
      363[("<div style='font-weight: bold'>HES CONNECTA DB2</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB Atlas</div>")]
      style 363 fill:#47a248,stroke:#317132,color:#ffffff
      364["<div style='font-weight: bold'>HES CONNECTA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>CONNECTA</div>"]
      style 364 fill:#0d5091,stroke:#093865,color:#ffffff
      70[("<div style='font-weight: bold'>HES CURS CLÍNIC DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDbAtlas</div>")]
      style 70 fill:#47a248,stroke:#317132,color:#ffffff
      71["<div style='font-weight: bold'>CURS CLÍNIC</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Nova Estació de treball per<br />professionals assistencials</div>"]
      style 71 fill:#0d5091,stroke:#093865,color:#ffffff
      79[("<div style='font-weight: bold'>HES INTEGRADOR D'IMATGES DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Oracle</div>")]
      style 79 fill:#f80000,stroke:#ad0000,color:#ffffff
      80["<div style='font-weight: bold'>HES INTEGRADOR D'IMATGES</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Capturar un conjunt d’imatges<br />i associar-les a una cita</div>"]
      style 80 fill:#0d5091,stroke:#093865,color:#ffffff
      86[("<div style='font-weight: bold'>HES SERVIDOR TERMINOLÒGIC DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>PostgreSQL</div>")]
      style 86 fill:#336791,stroke:#234865,color:#ffffff
      87["<div style='font-weight: bold'>HES SERVIDOR TERMINOLÒGIC</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Gestiona, manté i permet<br />consultar els catàlegs de<br />dades clíniques i no<br />clíniques</div>"]
      style 87 fill:#0d5091,stroke:#093865,color:#ffffff
      91[("<div style='font-weight: bold'>HES PLATAFORMA AUDITORIA DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>MongoDB Atlas</div>")]
      style 91 fill:#47a248,stroke:#317132,color:#ffffff
      92["<div style='font-weight: bold'>HES PLATAFORMA AUDITORIA</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>HES - Plataforma d'auditoria</div>"]
      style 92 fill:#0d5091,stroke:#093865,color:#ffffff
      98[("<div style='font-weight: bold'>HES CERCADOR DIAGNÒSTICS DB</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Oracle</div>")]
      style 98 fill:#f80000,stroke:#ad0000,color:#ffffff
      99["<div style='font-weight: bold'>HES CERCADOR DIAGNÒSTICS</div><div style='font-size: 70%; margin-top: 0px'>[Software System]</div><div style='font-size: 80%; margin-top:10px'>Cercador de diagnòstics del<br />HES</div>"]
      style 99 fill:#0d5091,stroke:#093865,color:#ffffff
    end


    99-- "<div></div><div style='font-size: 70%'></div>" -->98
    99-. "<div></div><div style='font-size: 70%'></div>" .->8
    99-. "<div></div><div style='font-size: 70%'></div>" .->10
    105-- "<div></div><div style='font-size: 70%'></div>" -->103
    105-- "<div></div><div style='font-size: 70%'></div>" -->104
    105-. "<div></div><div style='font-size: 70%'></div>" .->3
    105-. "<div></div><div style='font-size: 70%'></div>" .->6
    111-- "<div></div><div style='font-size: 70%'></div>" -->110
    111-. "<div></div><div style='font-size: 70%'></div>" .->2
    111-- "<div></div><div style='font-size: 70%'></div>" -->4
    111-. "<div></div><div style='font-size: 70%'></div>" .->5
    111-. "<div></div><div style='font-size: 70%'></div>" .->6
    111-. "<div></div><div style='font-size: 70%'></div>" .->8
    111-. "<div></div><div style='font-size: 70%'></div>" .->10
    111-. "<div></div><div style='font-size: 70%'></div>" .->12
    121-- "<div></div><div style='font-size: 70%'></div>" -->120
    121-. "<div></div><div style='font-size: 70%'></div>" .->3
    121-- "<div></div><div style='font-size: 70%'></div>" -->4
    121-. "<div></div><div style='font-size: 70%'></div>" .->6
    128-- "<div></div><div style='font-size: 70%'></div>" -->126
    128-- "<div></div><div style='font-size: 70%'></div>" -->127
    128-. "<div></div><div style='font-size: 70%'></div>" .->2
    128-- "<div></div><div style='font-size: 70%'></div>" -->4
    128-. "<div></div><div style='font-size: 70%'></div>" .->6
    128-. "<div></div><div style='font-size: 70%'></div>" .->10
    137-- "<div></div><div style='font-size: 70%'></div>" -->135
    137-- "<div></div><div style='font-size: 70%'></div>" -->136
    137-. "<div></div><div style='font-size: 70%'></div>" .->3
    137-- "<div></div><div style='font-size: 70%'></div>" -->4
    137-. "<div></div><div style='font-size: 70%'></div>" .->6
    145-- "<div></div><div style='font-size: 70%'></div>" -->143
    145-- "<div></div><div style='font-size: 70%'></div>" -->144
    145-- "<div></div><div style='font-size: 70%'></div>" -->4
    145-. "<div></div><div style='font-size: 70%'></div>" .->5
    145-. "<div></div><div style='font-size: 70%'></div>" .->6
    152-- "<div></div><div style='font-size: 70%'></div>" -->151
    152-. "<div></div><div style='font-size: 70%'></div>" .->1
    152-. "<div></div><div style='font-size: 70%'></div>" .->2
    152-. "<div></div><div style='font-size: 70%'></div>" .->3
    152-- "<div></div><div style='font-size: 70%'></div>" -->4
    152-. "<div></div><div style='font-size: 70%'></div>" .->5
    152-. "<div></div><div style='font-size: 70%'></div>" .->13
    161-- "<div></div><div style='font-size: 70%'></div>" -->160
    161-. "<div></div><div style='font-size: 70%'></div>" .->2
    161-. "<div></div><div style='font-size: 70%'></div>" .->3
    161-- "<div></div><div style='font-size: 70%'></div>" -->4
    161-. "<div></div><div style='font-size: 70%'></div>" .->8
    161-. "<div></div><div style='font-size: 70%'></div>" .->10
    161-. "<div></div><div style='font-size: 70%'></div>" .->11
    161-. "<div></div><div style='font-size: 70%'></div>" .->13
    16-- "<div></div><div style='font-size: 70%'></div>" -->15
    172-- "<div></div><div style='font-size: 70%'></div>" -->170
    172-- "<div></div><div style='font-size: 70%'></div>" -->171
    172-. "<div></div><div style='font-size: 70%'></div>" .->6
    172-. "<div></div><div style='font-size: 70%'></div>" .->13
    16-. "<div></div><div style='font-size: 70%'></div>" .->7
    179-- "<div></div><div style='font-size: 70%'></div>" -->177
    179-- "<div></div><div style='font-size: 70%'></div>" -->178
    179-. "<div></div><div style='font-size: 70%'></div>" .->2
    179-. "<div></div><div style='font-size: 70%'></div>" .->3
    179-- "<div></div><div style='font-size: 70%'></div>" -->4
    179-. "<div></div><div style='font-size: 70%'></div>" .->6
    179-. "<div></div><div style='font-size: 70%'></div>" .->9
    188-- "<div></div><div style='font-size: 70%'></div>" -->187
    188-. "<div></div><div style='font-size: 70%'></div>" .->1
    188-- "<div></div><div style='font-size: 70%'></div>" -->4
    188-. "<div></div><div style='font-size: 70%'></div>" .->6
    194-- "<div></div><div style='font-size: 70%'></div>" -->193
    194-. "<div></div><div style='font-size: 70%'></div>" .->2
    194-. "<div></div><div style='font-size: 70%'></div>" .->6
    194-. "<div></div><div style='font-size: 70%'></div>" .->8
    194-. "<div></div><div style='font-size: 70%'></div>" .->10
    202-- "<div></div><div style='font-size: 70%'></div>" -->200
    202-- "<div></div><div style='font-size: 70%'></div>" -->201
    202-. "<div></div><div style='font-size: 70%'></div>" .->2
    202-- "<div></div><div style='font-size: 70%'></div>" -->4
    202-. "<div></div><div style='font-size: 70%'></div>" .->8
    202-. "<div></div><div style='font-size: 70%'></div>" .->10
    202-. "<div></div><div style='font-size: 70%'></div>" .->11
    20-- "<div></div><div style='font-size: 70%'></div>" -->19
    202-. "<div></div><div style='font-size: 70%'></div>" .->6
    212-- "<div></div><div style='font-size: 70%'></div>" -->211
    212-. "<div></div><div style='font-size: 70%'></div>" .->2
    212-. "<div></div><div style='font-size: 70%'></div>" .->9
    212-. "<div></div><div style='font-size: 70%'></div>" .->6
    218-- "<div></div><div style='font-size: 70%'></div>" -->217
    20-. "<div></div><div style='font-size: 70%'></div>" .->7
    218-. "<div></div><div style='font-size: 70%'></div>" .->1
    218-. "<div></div><div style='font-size: 70%'></div>" .->2
    218-- "<div></div><div style='font-size: 70%'></div>" -->4
    218-. "<div></div><div style='font-size: 70%'></div>" .->6
    218-. "<div></div><div style='font-size: 70%'></div>" .->12
    218-. "<div></div><div style='font-size: 70%'></div>" .->13
    227-- "<div></div><div style='font-size: 70%'></div>" -->226
    227-. "<div></div><div style='font-size: 70%'></div>" .->2
    227-. "<div></div><div style='font-size: 70%'></div>" .->3
    227-- "<div></div><div style='font-size: 70%'></div>" -->4
    227-. "<div></div><div style='font-size: 70%'></div>" .->6
    227-. "<div></div><div style='font-size: 70%'></div>" .->13
    235-- "<div></div><div style='font-size: 70%'></div>" -->234
    235-. "<div></div><div style='font-size: 70%'></div>" .->1
    235-. "<div></div><div style='font-size: 70%'></div>" .->2
    235-. "<div></div><div style='font-size: 70%'></div>" .->3
    23-. "<div></div><div style='font-size: 70%'></div>" .->7
    235-- "<div></div><div style='font-size: 70%'></div>" -->4
    235-. "<div></div><div style='font-size: 70%'></div>" .->6
    235-. "<div></div><div style='font-size: 70%'></div>" .->8
    235-. "<div></div><div style='font-size: 70%'></div>" .->12
    235-. "<div></div><div style='font-size: 70%'></div>" .->10
    247-- "<div></div><div style='font-size: 70%'></div>" -->245
    247-- "<div></div><div style='font-size: 70%'></div>" -->246
    247-. "<div></div><div style='font-size: 70%'></div>" .->3
    247-. "<div></div><div style='font-size: 70%'></div>" .->10
    253-- "<div></div><div style='font-size: 70%'></div>" -->252
    253-. "<div></div><div style='font-size: 70%'></div>" .->1
    253-. "<div></div><div style='font-size: 70%'></div>" .->3
    253-. "<div></div><div style='font-size: 70%'></div>" .->2
    253-- "<div></div><div style='font-size: 70%'></div>" -->4
    253-. "<div></div><div style='font-size: 70%'></div>" .->6
    253-. "<div></div><div style='font-size: 70%'></div>" .->8
    253-. "<div></div><div style='font-size: 70%'></div>" .->13
    264-- "<div></div><div style='font-size: 70%'></div>" -->262
    264-- "<div></div><div style='font-size: 70%'></div>" -->263
    264-. "<div></div><div style='font-size: 70%'></div>" .->2
    264-. "<div></div><div style='font-size: 70%'></div>" .->3
    264-- "<div></div><div style='font-size: 70%'></div>" -->4
    26-- "<div></div><div style='font-size: 70%'></div>" -->25
    271-- "<div></div><div style='font-size: 70%'></div>" -->270
    271-. "<div></div><div style='font-size: 70%'></div>" .->2
    271-- "<div></div><div style='font-size: 70%'></div>" -->4
    271-. "<div></div><div style='font-size: 70%'></div>" .->6
    271-. "<div></div><div style='font-size: 70%'></div>" .->8
    271-. "<div></div><div style='font-size: 70%'></div>" .->10
    26-. "<div></div><div style='font-size: 70%'></div>" .->7
    279-- "<div></div><div style='font-size: 70%'></div>" -->278
    279-. "<div></div><div style='font-size: 70%'></div>" .->2
    279-. "<div></div><div style='font-size: 70%'></div>" .->3
    279-- "<div></div><div style='font-size: 70%'></div>" -->4
    279-. "<div></div><div style='font-size: 70%'></div>" .->6
    279-. "<div></div><div style='font-size: 70%'></div>" .->8
    279-. "<div></div><div style='font-size: 70%'></div>" .->10
    26-. "<div></div><div style='font-size: 70%'></div>" .->10
    289-- "<div></div><div style='font-size: 70%'></div>" -->287
    289-- "<div></div><div style='font-size: 70%'></div>" -->288
    289-. "<div></div><div style='font-size: 70%'></div>" .->1
    289-. "<div></div><div style='font-size: 70%'></div>" .->2
    289-. "<div></div><div style='font-size: 70%'></div>" .->3
    289-- "<div></div><div style='font-size: 70%'></div>" -->4
    289-. "<div></div><div style='font-size: 70%'></div>" .->5
    289-. "<div></div><div style='font-size: 70%'></div>" .->8
    289-. "<div></div><div style='font-size: 70%'></div>" .->10
    289-. "<div></div><div style='font-size: 70%'></div>" .->6
    302-- "<div></div><div style='font-size: 70%'></div>" -->300
    302-- "<div></div><div style='font-size: 70%'></div>" -->301
    302-. "<div></div><div style='font-size: 70%'></div>" .->2
    302-. "<div></div><div style='font-size: 70%'></div>" .->3
    302-- "<div></div><div style='font-size: 70%'></div>" -->4
    302-. "<div></div><div style='font-size: 70%'></div>" .->6
    302-. "<div></div><div style='font-size: 70%'></div>" .->10
    312-- "<div></div><div style='font-size: 70%'></div>" -->310
    312-- "<div></div><div style='font-size: 70%'></div>" -->311
    312-. "<div></div><div style='font-size: 70%'></div>" .->2
    312-. "<div></div><div style='font-size: 70%'></div>" .->3
    312-- "<div></div><div style='font-size: 70%'></div>" -->4
    312-. "<div></div><div style='font-size: 70%'></div>" .->6
    312-. "<div></div><div style='font-size: 70%'></div>" .->10
    322-- "<div></div><div style='font-size: 70%'></div>" -->320
    322-- "<div></div><div style='font-size: 70%'></div>" -->321
    322-- "<div></div><div style='font-size: 70%'></div>" -->4
    322-. "<div></div><div style='font-size: 70%'></div>" .->6
    322-. "<div></div><div style='font-size: 70%'></div>" .->10
    32-- "<div></div><div style='font-size: 70%'></div>" -->30
    329-- "<div></div><div style='font-size: 70%'></div>" -->328
    329-. "<div></div><div style='font-size: 70%'></div>" .->2
    329-- "<div></div><div style='font-size: 70%'></div>" -->4
    329-. "<div></div><div style='font-size: 70%'></div>" .->6
    329-. "<div></div><div style='font-size: 70%'></div>" .->3
    329-. "<div></div><div style='font-size: 70%'></div>" .->5
    329-. "<div></div><div style='font-size: 70%'></div>" .->11
    329-. "<div></div><div style='font-size: 70%'></div>" .->10
    329-. "<div></div><div style='font-size: 70%'></div>" .->12
    32-- "<div></div><div style='font-size: 70%'></div>" -->31
    339-. "<div></div><div style='font-size: 70%'></div>" .->1
    339-. "<div></div><div style='font-size: 70%'></div>" .->2
    339-- "<div></div><div style='font-size: 70%'></div>" -->4
    339-. "<div></div><div style='font-size: 70%'></div>" .->5
    339-. "<div></div><div style='font-size: 70%'></div>" .->6
    339-. "<div></div><div style='font-size: 70%'></div>" .->3
    348-- "<div></div><div style='font-size: 70%'></div>" -->346
    32-. "<div></div><div style='font-size: 70%'></div>" .->6
    348-- "<div></div><div style='font-size: 70%'></div>" -->347
    348-. "<div></div><div style='font-size: 70%'></div>" .->1
    348-. "<div></div><div style='font-size: 70%'></div>" .->2
    348-. "<div></div><div style='font-size: 70%'></div>" .->3
    348-- "<div></div><div style='font-size: 70%'></div>" -->4
    348-. "<div></div><div style='font-size: 70%'></div>" .->6
    348-. "<div></div><div style='font-size: 70%'></div>" .->11
    357-. "<div></div><div style='font-size: 70%'></div>" .->2
    357-. "<div></div><div style='font-size: 70%'></div>" .->3
    32-. "<div></div><div style='font-size: 70%'></div>" .->7
    357-- "<div></div><div style='font-size: 70%'></div>" -->4
    357-. "<div></div><div style='font-size: 70%'></div>" .->6
    364-- "<div></div><div style='font-size: 70%'></div>" -->362
    364-- "<div></div><div style='font-size: 70%'></div>" -->363
    364-. "<div></div><div style='font-size: 70%'></div>" .->1
    364-. "<div></div><div style='font-size: 70%'></div>" .->2
    364-. "<div></div><div style='font-size: 70%'></div>" .->3
    364-- "<div></div><div style='font-size: 70%'></div>" -->4
    364-. "<div></div><div style='font-size: 70%'></div>" .->6
    364-. "<div></div><div style='font-size: 70%'></div>" .->10
    364-. "<div></div><div style='font-size: 70%'></div>" .->12
    364-. "<div></div><div style='font-size: 70%'></div>" .->13
    37-. "<div></div><div style='font-size: 70%'></div>" .->14
    37-. "<div></div><div style='font-size: 70%'></div>" .->6
    37-. "<div></div><div style='font-size: 70%'></div>" .->7
    43-- "<div></div><div style='font-size: 70%'></div>" -->41
    43-- "<div></div><div style='font-size: 70%'></div>" -->42
    43-. "<div></div><div style='font-size: 70%'></div>" .->14
    43-. "<div></div><div style='font-size: 70%'></div>" .->7
    48-. "<div></div><div style='font-size: 70%'></div>" .->14
    48-. "<div></div><div style='font-size: 70%'></div>" .->7
    48-. "<div></div><div style='font-size: 70%'></div>" .->6
    48-. "<div></div><div style='font-size: 70%'></div>" .->8
    54-- "<div></div><div style='font-size: 70%'></div>" -->53
    54-. "<div></div><div style='font-size: 70%'></div>" .->7
    58-- "<div></div><div style='font-size: 70%'></div>" -->57
    58-. "<div></div><div style='font-size: 70%'></div>" .->7
    58-. "<div></div><div style='font-size: 70%'></div>" .->6
    58-. "<div></div><div style='font-size: 70%'></div>" .->14
    58-- "<div></div><div style='font-size: 70%'></div>" -->4
    65-- "<div></div><div style='font-size: 70%'></div>" -->64
    65-. "<div></div><div style='font-size: 70%'></div>" .->3
    65-. "<div></div><div style='font-size: 70%'></div>" .->7
    65-. "<div></div><div style='font-size: 70%'></div>" .->8
    71-- "<div></div><div style='font-size: 70%'></div>" -->70
    71-. "<div></div><div style='font-size: 70%'></div>" .->1
    71-- "<div></div><div style='font-size: 70%'></div>" -->4
    71-. "<div></div><div style='font-size: 70%'></div>" .->6
    71-. "<div></div><div style='font-size: 70%'></div>" .->7
    71-. "<div></div><div style='font-size: 70%'></div>" .->8
    71-. "<div></div><div style='font-size: 70%'></div>" .->10
    80-- "<div></div><div style='font-size: 70%'></div>" -->79
    80-- "<div></div><div style='font-size: 70%'></div>" -->4
    80-. "<div></div><div style='font-size: 70%'></div>" .->6
    80-. "<div></div><div style='font-size: 70%'></div>" .->8
    80-. "<div></div><div style='font-size: 70%'></div>" .->10
    87-- "<div></div><div style='font-size: 70%'></div>" -->86
    87-. "<div></div><div style='font-size: 70%'></div>" .->8
    87-. "<div></div><div style='font-size: 70%'></div>" .->3
    92-- "<div></div><div style='font-size: 70%'></div>" -->91
    92-- "<div></div><div style='font-size: 70%'></div>" -->4
    92-. "<div></div><div style='font-size: 70%'></div>" .->2
    92-. "<div></div><div style='font-size: 70%'></div>" .->6
    92-. "<div></div><div style='font-size: 70%'></div>" .->3

  end
```
