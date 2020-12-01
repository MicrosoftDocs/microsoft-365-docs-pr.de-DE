---
title: Ende der Unterstützung für Exchange 2007 – Roadmap
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Erfahren Sie mehr über die Optionen nach Exchange Server 2007 Ende des Supports, und beginnen Sie mit der Planung der Migration zu Microsoft 365, Office 365 oder Exchange 2016.
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519845"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Ende der Unterstützung für Exchange 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Exchange Server 2007 am Ende der Unterstützung im April 2017 erreicht. Wenn Sie die Migration nicht von Exchange 2007 zu Microsoft 365, Office 365 oder Exchange 2016 gestartet haben, ist jetzt der Zeitpunkt für die Planung.
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende der Unterstützung* ?

Exchange Server, wie fast alle Microsoft-Produkte, verfügt über einen Support-Lebenszyklus, in dem wir neue Features, Fehlerbehebungen, Sicherheitsfixes usw. bereitstellen. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Version des Produkts. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da Exchange 2007 am 11. April 2017 das Ende der Unterstützung erreicht hat, bietet Microsoft nicht mehr Folgendes:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
    
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.
    
- Zeitzonenaktualisierungen.
    
Ihre Installation von Exchange 2007 wird weiterhin nach dem Ende des Support-Datums ausgeführt. Da es jedoch keine neuen Updates oder Unterstützung gibt, wird dringend empfohlen, dass Sie so bald wie möglich von Exchange 2007 migrieren.
  
Weitere Informationen zu Office 2007 Servern, die sich am Ende des Supports befinden, finden Sie unter [Planen des Upgrades von Office 2007 Servern und Produkten](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Sie können:
  
- Migrieren zu Microsoft 365 mithilfe von Cutover, mehrstufiger oder hybrider Migration.
    
- Migrieren Sie Ihre Exchange 2007 Server zu einer neueren Version von Exchange auf Ihren lokalen Servern.
    
In den folgenden Abschnitten werden die einzelnen Optionen näher erläutert.
  
### <a name="migrate-to-microsoft-365"></a>Migrieren zu Microsoft 365

Die Migration Ihrer e-Mail an Microsoft 365 ist die beste und einfachste Option, um Ihre Exchange 2007-Bereitstellung zu unterstützen. Mit einer Migration zu Microsoft 365 können Sie einen einzelnen Hop von der 10-jährigen Technologie zu den State-of-the-Art-Funktionen machen, einschließlich:
  
- Compliance-Funktionen wie Aufbewahrungsrichtlinien, In-Place und Beweissicherungsverfahren, in-situ-eDiscovery und mehr
    
- Microsoft 365-Gruppen
    
- Posteingang mit Relevanz
    
- MyAnalytics
    
- Rest-APIs für den programmatischen Zugriff auf e-Mails, Kalender, Kontakte usw.
    
Microsoft 365 erhält außerdem erste neue Features und Benutzeroberflächen, sodass Sie und Ihre Benutzer diese in der Regel sofort verwenden können. Und Sie müssen sich keine Gedanken machen:
  
- Einkauf und Wartung von Hardware.
    
- Bezahlen zum Heizen und kühlen Ihrer Server.
    
- Halten Sie sich auf dem Laufenden über Sicherheits-, Produkt-und Zeit Zonen Korrekturen.
    
- Aufrechterhaltung von Speicher und Software zur Unterstützung von Compliance-Anforderungen
    
- Aktualisieren auf eine neue Version von Exchange. Mit Microsoft 365 haben Sie immer die neueste Version von Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Wie sollte ich zu Microsoft 365 migrieren?

Sie haben einige Migrationsoptionen. Sie müssen ein paar Dinge beachten, einschließlich:

- Die Anzahl der Arbeitsplätze oder Postfächer, die Sie verschieben müssen.
- Wie lange die Migration dauern soll.
- Ob Sie eine nahtlose Integration zwischen Ihrer lokalen Installation und Microsoft 365 während der Migration benötigen.

In dieser Tabelle sind die Migrationsoptionen und die wichtigsten Faktoren aufgeführt, die die zu verwendende Methode bestimmen:
  

|**Migrationsoption**|**Organisationsgröße**|**Duration**|
|:-----|:-----|:-----|
|Übernahmemigration  <br/> |Weniger als 150 Sitze  <br/> |Mindestens eine Woche  <br/> |
|Mehrstufige Migration  <br/> |Mehr als 150 Sitze  <br/> |Ein paar Wochen  <br/> |
|Vollständige Hybridmigration  <br/> |Mehrere hundert bis Tausende von sitzen  <br/> |Einige Monate oder mehr  <br/> |
   
Die folgenden Abschnitte bieten eine Übersicht über diese Methoden. Weitere Informationen finden Sie unter [beschließen eines Migrationspfads](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Übernahmemigration

Bei einer Cutover Migration migrieren Sie alle Postfächer, Verteilergruppen, Kontakte usw. zu einem vorgewählten Datum und einer vorgewählten Uhrzeit zu Microsoft 365. Nachdem die Migration abgeschlossen ist, können Sie Ihre lokalen Exchange-Server herunterfahren und die Verwendung von Microsoft 365 ausschließlich starten.
  
Cutover Migration eignet sich hervorragend für kleine Organisationen, die nicht über viele Postfächer verfügen, Microsoft 365 schnell erhalten möchten und nicht mit einigen der Komplexitäten der anderen Methoden umgehen möchten. Sie sollte jedoch in einer Woche oder kürzer abgeschlossen werden, und es ist erforderlich, dass Benutzer Ihre Outlook-Profile neu konfigurieren. Die Cutover-Migration kann bis zu 2.000 Postfächer verarbeiten, es wird jedoch dringend empfohlen, dass Sie Sie zum Migrieren von maximal 150 Postfächern verwenden. Wenn Sie versuchen, mehr zu migrieren, können Sie keine Zeit mehr für die Übertragung aller Postfächer vor dem Stichtag haben, und Ihr IT-Supportmitarbeiter wird möglicherweise mit Anfragen zur Unterstützung von Benutzern für die Neukonfiguration von Outlook überhäuft.
  
Wenn Sie über eine Cutover-Migration nachdenken, sollten Sie folgende Punkte beachten:
  
- Microsoft 365 muss eine Verbindung mit Ihren Exchange 2007 Servern mit Outlook Anywhere über TCP-Port 443 herstellen.
    
- Alle lokalen Postfächer werden nach Microsoft 365 verschoben.
    
- Sie benötigen ein lokales Administratorkonto, das über Lesezugriff auf die Postfächer Ihrer Benutzer verfügt.
    
- Die Exchange 2007 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen im Dienst als verifizierte Domänen hinzugefügt werden.
    
- Zwischen dem Zeitpunkt, zu dem Sie die Migration starten, und nach Beginn der Abschlussphase synchronisiert Microsoft 365 in regelmäßigen Abständen die Microsoft 365-und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber machen zu müssen, dass e-Mails in Ihren lokalen Postfächern hinterlassen werden.
    
- Die Benutzer erhalten neue temporäre Kennwörter für Ihre Microsoft 365-Konten. Sie müssen Ihr Kennwort ändern, wenn Sie sich zum ersten Mal bei Ihrem Postfach anmelden.
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
    
- Benutzer müssen auf jedem Ihrer Geräte ein neues Outlook-Profil einrichten und Ihre e-Mails erneut herunterladen. Die Menge an e-Mails, die von Outlook heruntergeladen werden können, kann variieren. Weitere Informationen finden Sie unter [Ändern der Nachrichtenmenge, die Offline aufbewahrt werden soll](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Weitere Informationen zur Cutover-Migration finden Sie unter:
  
- [Was Sie über eine Cutover-e-Mail-Migration wissen müssen](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Durchführen einer Cutover Migration von e-Mails](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Mehrstufige Migration

Bei einer mehrstufigen Migration haben Sie ein paar hundert oder einige tausend Postfächer, die Sie zu Microsoft 365 migrieren möchten, benötigen eine Woche oder länger, um die Migration abzuschließen, und benötigen keine fortschrittlichen Hybriden Migrationsfunktionen wie freigegebene Frei/Gebucht-Kalenderinformationen.
  
Die mehrstufige Migration eignet sich hervorragend für Unternehmen, die mehr Zeit benötigen, um ihre Postfächer zu Microsoft 365 zu migrieren, die Migration aber dennoch innerhalb weniger Wochen durchführen möchten. Sie können Postfächer in Batches migrieren. Sie steuern, wie viele und welche Postfächer zu einem bestimmten Zeitpunkt migriert werden. Sie können beispielsweise Postfächer von Benutzern in der gleichen Abteilung Stapeln, um sicherzustellen, dass alle gleichzeitig verschoben werden. Oder Sie können Executive-Postfächer bis zum letzten Batch verlassen. Wie bei Cutover-Migrationen müssen die Benutzer Ihre Outlook-Profile neu erstellen.
  
Wenn Sie über eine mehrstufige Migration nachdenken, sollten Sie Folgendes beachten:
  
- Microsoft 365 muss mit Outlook Anywhere über TCP-Port 443 eine Verbindung zu Ihren Exchange 2007 Servern herstellen.
    
- Sie benötigen ein lokales Administratorkonto, das über Lesezugriff auf die Postfächer Ihrer Benutzer verfügt.
    
- Die Exchange 2007 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen im Dienst als verifizierte Domänen hinzugefügt werden.
    
- Sie müssen eine CSV-Datei mit dem vollständigen Namen und der e-Mail-Adresse jedes Postfachs erstellen, das Sie in einem Batch migrieren möchten. Sie müssen auch ein neues Kennwort für jedes zu migrierende Postfach hinzufügen und dieses Kennwort an jeden Benutzer senden. Der Benutzer wird aufgefordert, das Kennwort zu ändern, wenn er sich das erste Mal bei seinem neuen Microsoft 365-Postfach anmeldet.
    
- Zwischen dem Zeitpunkt des Starts des Migrationsbatches und dem Beginn der Abschlussphase synchronisiert Microsoft 365 regelmäßig die im Batch enthaltenen Microsoft 365-und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber machen zu müssen, dass e-Mails in Ihren lokalen Postfächern hinterlassen werden.
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
    
- Benutzer müssen auf jedem Ihrer Geräte ein neues Outlook-Profil einrichten und Ihre e-Mails erneut herunterladen. Die Menge an e-Mails, die von Outlook heruntergeladen werden können, kann variieren. Weitere Informationen finden Sie unter [Ändern der Nachrichtenmenge, die Offline aufbewahrt werden soll](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Weitere Informationen zur mehrstufigen Migration finden Sie unter:
  
- [Was Sie über eine mehrstufige e-Mail-Migration wissen müssen](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Durchführen einer mehrstufigen Migration von e-Mails](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Vollständige hybridbereitstellung

Bei einer vollständigen Hybrid Migration hat Ihre Organisation viele Hunderte, bis zu Zehntausende von Postfächern, und Sie möchten einige oder alle von Ihnen zu Microsoft 365 verschieben. Da diese Migrationen normalerweise längerfristig sind, ermöglichen Hybrid Migrationen Folgendes:
  
- Zeigen Sie lokalen Benutzern die Frei/Gebucht-Kalenderinformationen für Benutzer in Microsoft 365 an, und umgekehrt.
    
- Siehe eine einheitliche globale Adressliste, die Empfänger sowohl in lokal als auch in Microsoft 365 enthält.
    
- Zeigen Sie die vollständigen Outlook-Empfänger Eigenschaften für alle Benutzer an, unabhängig davon, ob Sie lokal oder in Microsoft 365 sind.
    
- Sichere e-Mail-Kommunikation zwischen lokalen Exchange-Servern und Microsoft 365 mithilfe von TLS und Zertifikaten.
    
- Behandeln Sie Nachrichten, die zwischen lokalen Exchange-Servern und Microsoft 365 gesendet werden, als intern, sodass Sie folgende Möglichkeiten haben:
    
  - Durch Transport-und Compliance-Agents, die auf interne Nachrichten Zielen, ordnungsgemäß ausgewertet und verarbeitet werden.
    
  - Umgehen von Anti-Spam-Filtern.
    
Die vollständige Hybrid Migration eignet sich am besten für Unternehmen, die für mehrere Monate oder mehr in einer Hybrid Konfiguration bleiben möchten. Sie erhalten die weiter oben in diesem Abschnitt aufgeführten Features sowie die Verzeichnissynchronisierung, bessere integrierte Compliance-Features und die Möglichkeit, Postfächer mithilfe von Online Postfachverschiebungen von und nach Microsoft 365 zu verschieben. Microsoft 365 wird zu einer Erweiterung Ihrer lokalen Organisation.
  
Wenn Sie über eine vollständige Hybrid Migration nachdenken, sollten Sie folgende Punkte beachten:
  
- Die vollständige Hybrid Migration eignet sich nicht für alle Arten von Organisationen. Aufgrund der Komplexität von vollständigen Hybrid Migrationen sehen Organisationen mit weniger als ein paar hundert Postfächern normalerweise keine Vorteile, die den Aufwand und die Kosten rechtfertigen, die für die Einrichtung eines eingerichtet werden müssen. Wenn dies wie Ihre Organisation klingt, empfehlen wir, stattdessen eine Cutover oder mehrstufige Migration zu verwenden.
    
- Sie müssen mindestens einen Exchange 2013 Server in Ihrer Exchange 2007 Organisation bereitstellen, um als "hybridserver" fungieren zu können. Dieser Server kommuniziert im Auftrag Ihrer Exchange 2007 Server mit Microsoft 365.
    
- Microsoft 365 muss eine Verbindung mit dem "hybridserver" mit Outlook Anywhere über TCP-Port 443 herstellen.
    
- Sie müssen die Verzeichnissynchronisierung mithilfe von Azure Active Directory (Azure AD) zwischen Ihren lokalen Active Directory Servern und Microsoft 365 herstellen.
    
- Benutzer können sich bei Ihrem Microsoft 365-Postfach mit dem gleichen Benutzernamen und Kennwort wie beim Anmelden beim lokalen Netzwerk anmelden. (Für diese Funktionalität ist Azure AD Verbindung mit der Kennwortsynchronisierung und/oder Active Directory Verbunddiensten erforderlich.)
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
    
- Benutzer müssen kein neues Outlook-Profil auf den meisten Ihrer Geräte einrichten, auch wenn einige ältere Android-Telefone möglicherweise ein neues Profil benötigen. Benutzer müssen Ihre e-Mails nicht erneut herunterladen.
    
Wenn die vollständige Hybrid Migration für Sie richtig klingt, lesen Sie die folgenden Ressourcen, die Sie bei der Migration unterstützen:
  
- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
    
- [Hybridbereitstellungen in Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Assistent für die Hybridkonfiguration](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [FAQs zum Assistenten für die Hybridkonfiguration](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Voraussetzungen für die Hybridbereitstellung](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrieren zu einer neueren Version von Exchange Server

Wir sind der festen Überzeugung, dass Sie durch die Migration zu Microsoft 365 den besten Wert und die Benutzeroberfläche erreichen können. Aber wir verstehen auch, dass einige Organisationen ihre e-Mails lokal halten müssen. Dies kann auf regulatorische Anforderungen hinweisen, um sicherzustellen, dass Daten nicht in einem Rechenzentrum in einem anderen Land oder ähnlich gespeichert werden. Wenn Sie Ihre e-Mail-Adresse lokal behalten möchten, können Sie Ihre Exchange 2007 Umgebung zu Exchange 2010, Exchange 2013 oder Exchange 2016 migrieren.
  
Wenn Sie nicht zu Microsoft 365 migrieren können, wird empfohlen, dass Sie zu Exchange 2016 migrieren. Exchange 2016 umfasst alle Features früherer Versionen von Exchange. Es entspricht auch am ehesten der verfügbaren Erfahrung mit Microsoft 365, obwohl einige Funktionen nur in Microsoft 365 verfügbar sind. Sehen Sie sich nur einige der Dinge an, die Ihnen fehlen:
  
|**Exchange-Version**|**Features**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based Zugriffssteuerung (Berechtigungen ohne ACLs)  <br/>  Outlook Web App-Postfachrichtlinien  <br/>  Möglichkeit zum Freigeben von frei/gebucht-und Delegieren von Kalendern zwischen Organisationen  <br/> |
|Exchange 2013  <br/> | *Features aus Exchange 2010 und...*  <br/>  Vereinfachte Architektur, die die Anzahl der Serverrollen auf drei reduziert (Postfach, Client Zugriff, Edge-Transport)  <br/>  Datenverlust-Verhinderung-Richtlinien (DLP), mit denen vertrauliche Informationen vor Undichtigkeiten bleiben  <br/>  Verbesserte Outlook Web App Erfahrung  <br/> |
|Exchange 2016  <br/> | *Features aus Exchange 2013 und...*  <br/>  Weitere vereinfachte Serverrollen nur für Postfach-und Edge-Transport  <br/>  Verbesserte DLP zusammen mit der Integration in SharePoint  <br/>  Verbesserte Ausfallsicherheit der Datenbank  <br/>  Online Dokument Zusammenarbeit |
   
#### <a name="which-version-should-i-migrate-to"></a>In welche Version sollte ich migrieren?

Es wird empfohlen, dass Sie zunächst davon ausgehen, dass Sie zu Exchange 2016 migrieren. Verwenden Sie dann die folgenden Informationen, um Ihre Annahme zu bestätigen oder Exchange 2016 auszuschließen. Wenn Sie aus irgendeinem Grund nicht zu Exchange 2016 migrieren können, führen Sie denselben Vorgang mit Exchange 2013 aus, und so weiter.
  
|**Überlegungen**|**Weitere Informationen**|
|:-----|:-----|
|Ende der Support Daten  <br/> | Wie Exchange 2007 hat jede Version von Exchange ein eigenes Datum für das Ende des Supports:  <br/> *Exchange 2010* -Januar 2020  <br/> *Exchange 2013* -April 2023  <br/> *Exchange 2016* -Oktober 2025  <br/>  Je früher das Ende der Unterstützung ist, desto schneller müssen Sie eine weitere Migration durchführen.<br/> |
|Migrationspfad zu Exchange 2010 und 2013.  <br/> |Im folgenden finden Sie die allgemeinen Phasen für die Migration zu Exchange 2010 oder Exchange 2013:  <br/> – Installieren Sie Exchange 2010 oder 2013 in Ihrer vorhandenen Exchange 2007 Organisation. <br/>-Verlagerung von Diensten und anderen Infrastrukturen auf Exchange 2010 oder 2013.<br/>-Verschieben von Postfächern und öffentlichen Ordnern nach Exchange 2010 oder 2013.<br/>-Außerbetriebnahme verbleibenden Exchange 2007 Server. |
|Migrationspfad zu Exchange 2016  <br/> |Im folgenden finden Sie die allgemeinen Phasen für die Migration zu Exchange 2016:  <br/> – Installieren Sie Exchange 2013 in Ihrer vorhandenen Exchange 2007 Organisation.<br/>-Verschiebe Dienste und andere Infrastruktur zu Exchange 2013.<br/>-Verschieben von Postfächern und öffentlichen Ordnern in Exchange 2013.<br/>-Außerbetriebnahme verbleibenden Exchange 2007 Server.<br/>– Installieren Sie Exchange 2016 in Ihrer vorhandenen Exchange 2013 Organisation.<br/>-Verschieben von Postfächern, öffentlichen Ordnern, Diensten und anderen Infrastrukturen nach Exchange 2016 (Reihenfolge ist nicht wichtig). Stilllegung der verbleibenden Exchange 2013 Server.<br/><br/> **Hinweis:** Die Migration von Exchange 2013 zu Exchange 2016 ist einfach. Die beiden Versionen haben fast die gleichen Hardwareanforderungen, und diese Versionen sind sehr kompatibel. Sie können also einen Server neu erstellen, den Sie für Exchange 2013 gekauft haben, und Exchange 2016 darauf installieren. Bei Online Postfachverschiebungen werden die meisten Benutzer nicht einmal bemerken, dass Ihr Postfach vom Server und dann zurück verschoben wurde, nachdem Sie es mit Exchange 2016 neu erstellt haben.           |
|Versions Koexistenz  <br/> | Bei der Migration zu...  <br/> **Exchange 2016:** Exchange 2016 kann nicht in einer Organisation installiert werden, die einen Exchange 2007 Server enthält. Zunächst müssen Sie zu Exchange 2010 oder 2013 migrieren (es wird dringend empfohlen, Exchange 2013), alle Exchange 2007 Server zu entfernen und dann zu Exchange 2016 zu migrieren.  <br/> **Exchange 2010 oder Exchange 2013:** Sie können Exchange 2010 oder Exchange 2013 in einer vorhandenen Exchange 2007 Organisation installieren. Auf diese Weise können Sie einen oder mehrere Exchange 2010-oder 2013-Server installieren und die Migration durchführen.  <br/> |
|Serverhardware  <br/> | Die Server Hardwareanforderungen wurden von Exchange 2007 geändert. Stellen Sie sicher, dass Ihre Hardware kompatibel ist. Weitere Informationen finden Sie unter:  <br/> [Exchange 2016-System Anforderungen](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Exchange 2013 System Anforderungen](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Exchange 2010 System Anforderungen](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Sie werden feststellen, dass die beträchtlichen Verbesserungen bei der Exchange-Leistung und die höhere Rechenleistung und Speicherkapazität in neueren Servern dazu führen, dass Sie wahrscheinlich weniger Server zur Unterstützung der gleichen Anzahl von Postfächern benötigen.  <br/> |
|Betriebssystemversion  <br/> | Für jede Version werden mindestens die folgenden Betriebssystemversionen unterstützt:  <br/> **Exchange 2016** -Windows Server 2012  <br/> **Exchange 2013** -Windows Server 2008 R2 SP1  <br/> **Exchange 2010** -Windows Server 2008 SP2  <br/>  Weitere Informationen zur Betriebssystemunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Active Directory Gesamtstrukturfunktionsebene  <br/> | Für jede Version werden mindestens Active Directory Gesamtstrukturfunktionsebenen unterstützt:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Weitere Informationen zur Unterstützung der Gesamtstrukturfunktionsebene finden Sie in der [Exchange-Unterstützungs Matrix](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Office-Clientversionen  <br/> | Für jede Version werden mindestens die folgenden Office-Clientversionen unterstützt:  <br/> **Exchange 2016** -Office 2010 (mit den neuesten Updates)  <br/> **Exchange 2013** -Office 2007 SP3  <br/> **Exchange 2010** -Office 2003  <br/>  Weitere Informationen zur Office-Clientunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Wie kann ich migrieren?

Wenn Sie Ihre e-Mail-Adresse lokal beibehalten möchten, verwenden Sie die folgenden Ressourcen, um die Migration zu erleichtern:
  
- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
    
- Active Directory Schemaänderungen für Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- System Anforderungen für Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Voraussetzungen für Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="get-help"></a>Hilfe erhalten

Wenn Sie eine Migration zu Microsoft 365 durchführen, können Sie möglicherweise den Microsoft-kurzleistungs Dienst verwenden. In diesem Artikel werden bewährte Methoden, Tools und Ressourcen bereitgestellt, um die Migration zu Microsoft 365 so nahtlos wie möglich zu gestalten. Das beste von allem: ein Supporttechniker führt Sie durch die Migration, von der Planung und dem Entwurf bis hin zur Migration des letzten Postfachs. Weitere Informationen zum kurzbegriff finden Sie unter [Microsoft](https://fasttrack.microsoft.com/)Kurzinfo.
  
Wenn bei der Migration zu Microsoft 365 Probleme auftreten und Sie nicht den Kurzlauf oder die Migration zu einer neueren Version von Exchange Server verwenden, helfen wir Ihnen gerne weiter. Hier sind einige Ressourcen, die Sie verwenden können:
  
- [Technische Community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Support für Kunden](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Verwandte Themen

[Ressourcen für ein Upgrade Ihrer Office 2007-Server und-Clients](upgrade-from-office-2007-servers-and-products.md)
