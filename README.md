# Vergleich-Routingprotokolle-Uebersicht

-

Grundkenntnisse und Überblich zu den Routing Protokollen

-

ÜBERSETZUNG BEİDER WÖRTER:

intermediate 	= dazwischenliegend

interior			= inneres

-

ALTE ROUTING PROTOKOLLE:

RIP:    routing information protocol

IGRP:   interior gateway routing protocol

-

GÄNGIGE ROUTING PROTOKOLLE:

OSPF    open shortest path first

EIGRP   enhanced interior gateway routing protocol

IS-IS    intermediate-system to intermediate-system

BGP     border gateway protocol

-

OSPF & EIGRP Konfiguration einfacher

IS-IS & BGP Konfiguration komplexer

-

BGP am seltensten verbreitet unter den vier: 
  da BGP komplexer zu konfigurieren und zu verwalten. 
Erfordert tieferes Verständnis und spezialisierte Kenntnisse, für viele Unternehmen weniger attraktiv.

Anwendungsbereich: BGP wird hauptsächlich für Routing zwischen autonomen Systemen im Internet verwendet, also für Routing zwischen verschiedenen Netzwerken.

-

IS-IS weniger verbreitet als OSPF & EIGRP: 
Is-is wurde ursprünglich für grosse Service-Provider-Netzwerke entwickelt und hat sich dort etabliert. Unternehmensnetzwerke haben traditionell eher OSPF verwendet, das speziell für IP-Netzwerke entwickelt wurde.

-


Übersicht der typischen Anwendungsorte der vier Routingprotokolle:

Protokoll
	Typische Anwendungsorte
OSPF	Große Unternehmensnetzwerke, Campus-Netzwerke, Service-Provider-Netzwerke
EIGRP	Unternehmensnetzwerke, insbesondere Cisco-basierte Netzwerke
BGP	Internet Service Provider (ISP), grosss Unternehmensnetzwerke, die mehrere autonome Systeme verbinden
IS-IS	Große Service-Provider-Netzwerke, Backbone-Netzwerke

-

Übersicht der Stärken und Schwächen der vier Routingprotokolle:

Protokoll

	Stärken	

Schwächen

OSPF	- Schnelle Konvergenz- Skalierbar- Unterstützt VLSM und CIDR	- Komplexe Konfiguration- Hoher Ressourcenbedarf

-

EIGRP	- Schnelle Konvergenz- Einfach zu konfigurieren- Unterstützt VLSM und CIDR	- Proprietär (Cisco)- Begrenzte Interoperabilität

-

BGP	- Sehr skalierbar- Flexibel- Weit verbreitet im Internet	- Komplexe Konfiguration- Langsame Konvergenz

-

IS-IS	- Schnelle Konvergenz- Skalierbar- Robust	- Weniger verbreitet als OSPF- Komplexe Konfiguration

-

Vergleich von OSPF & EIGRP:

OSPF

Stärken:
Standardisiert: OSPF ist ein offener Standard, was bedeutet, dass es auf Geräten verschiedener Hersteller verwendet werden kann.

Skalierbarkeit: Gut geeignet für große Netzwerke mit vielen Routern.

Schnelle Konvergenz: Reagiert schnell auf Änderungen im Netzwerk.

Schwächen:
Komplexe Konfiguration: Erfordert detaillierte Kenntnisse über Netzwerkdesign und -topologie.

Ressourcenintensiv: Kann mehr CPU- und Speicherressourcen benötigen.

EIGRP

Stärken:Einfachere Konfiguration: Oft einfacher zu konfigurieren als OSPF, besonders in Cisco-Netzwerken.
Schnelle Konvergenz: Bietet schnelle Reaktionszeiten auf Netzwerkänderungen.
Flexibilität: Unterstützt sowohl Distance-Vector- als auch Link-State-Routing-Merkmale.
Schwächen:Proprietär: EIGRP ist ein proprietäres Protokoll von Cisco, was die Interoperabilität mit Geräten anderer Hersteller einschränken kann.
Begrenzte Verbreitung: Weniger verbreitet in Netzwerken, die nicht ausschließlich Cisco-Hardware verwenden.
Insgesamt kann gesagt werden, dass OSPF tendenziell komplexer zu konfigurieren ist, insbesondere in großen und heterogenen Netzwerken. EIGRP hingegen ist oft einfacher zu konfigurieren, aber seine proprietäre Natur kann in gemischten Netzwerkumgebungen zu Einschränkungen führen.







Distanzvektor Protokolle  vs.  Link State Protokolle
DVP    Router sendet die ganze Routingtabelle an seine Nachbarn.
LSP   Router sendet eine Liste seiner Links mit den dazugehörigen Distanzen an alle Router

DVP = EIGRP
LSP= OSPF, IS-IS

Distanzvektorprotokolle

Prinzip: Jeder Router teilt seinen Nachbarn regelmäßig seine gesamte Routing-Tabelle mit. Diese Tabelle enthält Informationen über die Entfernung (in Hops) zu allen bekannten Netzwerken. 
Funktionsweise: Router berechnen die kürzesten Wege zu Netzwerken, indem sie die Informationen ihrer Nachbarn berücksichtigen.


Link-State-Protokolle

Prinzip: Jeder Router sendet regelmäßig Informationen über seine direkt angeschlossenen Verbindungen (Links) an alle anderen Router im Netzwerk. 
Funktionsweise: Jeder Router erstellt eine vollständige Karte des Netzwerks, basierend auf den empfangenen Link-State-Informationen. Anschließend berechnet er den kürzesten Weg zu jedem Netzwerk mithilfe eines Algorithmus wie Dijkstra.



Vergleichstabelle Distanzvektor - Linkstate


Merkmal	Distanzvektorprotokolle	Link-State-Protokolle
Informationsaustausch	Gesamte Routing-Tabelle mit Nachbarn geteilt	Link-State-Informationen mit allen Routern geteilt
Routing-Berechnung	Basiert auf Informationen von Nachbarn	Basiert auf einer vollständigen Netzwerktopologie
Konvergenzzeit
(annäherung, übereinstimmung)	Langsam	Schnell
Routing-Loops	Anfällig	Weniger anfällig
Skalierbarkeit	Schlecht	Gut
Beispiele	RIP, IGRP	OSPF, IS-IS

