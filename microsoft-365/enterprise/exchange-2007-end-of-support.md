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
description: Erfahren Sie mehr über Ihre Optionen, nachdem Exchange Server 2007 das Ende der Unterstützung erreicht haben, und beginnen Sie mit der Planung der Migration zu Microsoft 365, Office 365 oder Exchange 2016.
ms.openlocfilehash: 864a4bc64f35a12dfea1a98b3d50430cd3e5714b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690831"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Ende der Unterstützung für Exchange 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Am **11. April 2017**Exchange Server 2007 das Ende der Unterstützung erreicht. Wenn Sie die Migration nicht bereits von Exchange 2007 zu Microsoft 365, Office 365 oder Exchange 2016 begonnen haben, ist es an der Zeit, mit der Planung zu beginnen. 
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet das Ende der Unterstützung?

Exchange Server, wie fast alle Microsoft-Produkte, verfügt über einen Support-Lebenszyklus, in dem wir neue Features, Fehlerbehebungen, Sicherheitsfixes usw. bereitstellen. Dieser Lebenszyklus dauert in der Regel 10 Jahre ab dem Datum der ersten Produktversion, und das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da Exchange 2007 am 11. April 2017 das Ende der Unterstützung erreicht hat, bietet Microsoft nicht mehr Folgendes:
  
- Technischer Support für Probleme, die auftreten können;
    
- Fehlerbehebungen für erkannte Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können;
    
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die erkannt werden und die den Server möglicherweise anfällig für Sicherheitsverletzungen machen;
    
- Zeitzonenaktualisierungen.
    
Die Installation von Exchange 2007 wird weiterhin nach diesem Datum ausgeführt. Aufgrund der oben aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie so bald wie möglich von Exchange 2007 migrieren.
  
Weitere Informationen zu Office 2007 Servern, die sich am Ende des Supports befinden, finden Sie unter [Planen des Upgrades von Office 2007 Servern und Produkten](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Nachdem Exchange 2007 das Ende der Unterstützung erreicht hat, wird dringend empfohlen, dass Sie sich mit ihren Optionen vertraut machen und einen Migrationsplan vorbereiten. Sie können:
  
- Migrieren zu Microsoft 365 mithilfe von Cutover, mehrstufiger oder hybrider Migration;
    
- Migrieren Sie Ihre Exchange 2007 Server zu einer neueren Version von Exchange auf Ihren lokalen Servern.
    
In den folgenden Abschnitten werden die einzelnen Optionen näher erläutert.
  
### <a name="migrate-to-microsoft-365"></a>Migrieren zu Microsoft 365

Die Migration Ihrer e-Mail-Adresse zu Microsoft 365 ist die beste und einfachste Option, die Sie beim Ruhestand Ihrer Exchange 2007-Bereitstellung unterstützt. Mit einer Migration zu Microsoft 365 können Sie einen einzelnen Hop von der 10-jährigen Technologie bis hin zu State-of-the-Art-Funktionen wie folgt erstellen:
  
- Compliance-Funktionen wie Aufbewahrungsrichtlinien, in-situ-und Beweissicherungsverfahren, in-situ-eDiscovery und mehr
    
- Microsoft 365 Gruppen;
    
- Fokussierter Posteingang;
    
- MyAnalytics
    
- Rest-APIs für den programmatischen Zugriff auf e-Mails, Kalender, Kontakte usw.
    
Microsoft 365 erhält auch neue Funktionen und Erfahrungen, die Sie und Ihre Benutzer in der Regel sofort verwenden können. Zusätzlich zu den neuen Features müssen Sie sich keine Gedanken machen:
  
- Einkauf und Wartung von Hardware;
    
- Bezahlen für das Heizen und kühlen Ihrer Server;
    
- Halten Sie sich auf dem Laufenden über Sicherheits-, Produkt-und Zeit Zonen Korrekturen;
    
- Wartung von Speicher und Software zur Unterstützung von Compliance-Anforderungen;
    
- Upgrade auf eine neue Version von Exchange – Sie haben immer die neueste Version von Exchange in Microsoft 365.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Wie sollte ich zu Microsoft 365 migrieren?

Je nach Ihrer Organisation stehen Ihnen einige Optionen zur Verfügung, die Sie bei der Bereitstellung von Microsoft 365 unterstützen. Bei der Auswahl einer Migrationsoption müssen Sie einige Dinge berücksichtigen, beispielsweise die Anzahl der zu verschiebenden Sitze oder Postfächer, die Dauer der Migration und ob Sie eine nahtlose Integration zwischen Ihrer lokalen Installation und Microsoft 365 während der Migration benötigen. In dieser Tabelle sind die Migrationsoptionen und die wichtigsten Faktoren aufgeführt, die die zu verwendende Methode bestimmen.
  
| |
|**Migrationsoption**|**Organisationsgröße**|**Duration**|
|:-----|:-----|:-----|
|Übernahmemigration  <br/> |Weniger als 150 Sitze  <br/> |Mindestens eine Woche  <br/> |
|Mehrstufige Migration  <br/> |Mehr als 150 Sitze  <br/> |Ein paar Wochen  <br/> |
|Vollständige Hybridmigration  <br/> |Mehrere hundert bis Tausende von sitzen  <br/> |Einige Monate oder mehr  <br/> |
   
In den folgenden Abschnitten erhalten Sie einen Überblick über diese Methoden. Auschecken entscheiden Sie sich für [einen Migrationspfad](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) , um die Details der einzelnen Methoden zu erfahren. 
  
#### <a name="cutover-migration"></a>Übernahmemigration

Bei einer Cutover Migration werden alle Postfächer, Verteilergruppen, Kontakte usw. zu einem vorab ausgewählten Datum und einer bestimmten Uhrzeit zu Microsoft 365 migriert. Wenn Sie fertig sind, schließen Sie Ihre lokalen Exchange-Server ab und verwenden ausschließlich Microsoft 365.
  
Die Cutover-Migrationsmethode eignet sich hervorragend für kleine Organisationen, die nicht über sehr viele Postfächer verfügen, Microsoft 365 schnell erhalten möchten und nicht mit einigen der Komplexitäten der anderen Methoden umgehen möchten. Es ist jedoch auch etwas limitiert, da es in einer Woche oder weniger ausgeführt werden sollte und weil Benutzer Ihre Outlook-Profile neu konfigurieren müssen. Während die Cutover-Migration bis zu 2.000 Postfächer verarbeiten kann, wird dringend empfohlen, dass Sie mit dieser Methode maximal 150 Postfächer migrieren. Wenn Sie versuchen, mehr als 150 Postfächer zu migrieren, können Sie keine Zeit mehr für die Übertragung aller Postfächer vor dem Stichtag haben, und Ihr IT-Supportmitarbeiter kann die Unterstützung von Benutzern bei der Neukonfiguration von Outlook überfordern.
  
Wenn Sie über eine Cutover-Migration nachdenken, sollten Sie Folgendes beachten:
  
- Microsoft 365 muss eine Verbindung mit Ihren Exchange 2007 Servern mit Outlook Anywhere über TCP-Port 443 herstellen;
    
- Alle lokalen Postfächer werden nach Microsoft 365 verschoben;
    
- Sie benötigen ein lokales Administratorkonto, das Zugriff hat, um den Inhalt der Postfächer Ihrer Benutzer zu lesen;
    
- Die Exchange 2007 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen im Dienst als verifizierte Domänen hinzugefügt werden.
    
- Zwischen dem Zeitpunkt, zu dem Sie die Migration starten, und nach Beginn der Abschlussphase synchronisiert Microsoft 365 in regelmäßigen Abständen die Microsoft 365-und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber machen zu müssen, dass e-Mails in Ihren lokalen Postfächern hinterlassen werden.
    
- Benutzer erhalten neue temporäre Kennwörter für Ihr Microsoft 365-Konto, die Sie ändern müssen, wenn Sie sich zum ersten Mal bei ihren Postfächern anmelden;
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren;
    
- Benutzer müssen auf jedem Ihrer Geräte ein neues Outlook-Profil einrichten und Ihre e-Mails erneut herunterladen. Die Menge an e-Mails, die von Outlook heruntergeladen werden können, kann variieren. Weitere Informationen finden Sie unter [Ändern der Nachrichtenmenge, die Offline aufbewahrt werden soll](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Weitere Informationen zur Migration von Cutover finden Sie unter:
  
- [Was Sie über eine Cutover-e-Mail-Migration wissen müssen](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Durchführen einer Cutover Migration von e-Mails](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Mehrstufige Migration

Bei einer mehrstufigen Migration handelt es sich um ein paar hundert oder einige tausend Postfächer, die Sie zu Microsoft 365 migrieren möchten, benötigen eine Woche oder länger, um die Migration abzuschließen, und benötigen keine der erweiterten Hybriden Migrationsfunktionen wie freigegebene Frei/Gebucht-Kalenderinformationen.
  
Die mehrstufige Migration eignet sich hervorragend für Unternehmen, die mehr Zeit benötigen, um ihre Postfächer zu Microsoft 365 zu migrieren, die Migration aber dennoch innerhalb weniger Wochen durchführen möchten. Sie können Postfächer in "Batches" migrieren, mit deren Hilfe Sie steuern, wie viele und welche Postfächer zu einem bestimmten Zeitpunkt migriert werden sollen. Sie können beispielsweise Postfächer von Benutzern in der gleichen Abteilung Stapeln, um sicherzustellen, dass alle gleichzeitig verschoben werden. Oder Sie können Executive-Postfächer bis zum letzten Batch verlassen. Wie bei Cutover-Migrationen müssen die Benutzer Ihre Outlook-Profile neu erstellen.
  
Wenn Sie an einer mehrstufigen Migration denken, sollten Sie Folgendes beachten:
  
- Microsoft 365 muss eine Verbindung mit Ihren Exchange 2007 Servern mit Outlook Anywhere über TCP-Port 443 herstellen;
    
- Sie benötigen ein lokales Administratorkonto, das Zugriff hat, um den Inhalt der Postfächer Ihrer Benutzer zu lesen;
    
- Die Exchange 2007 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen im Dienst als verifizierte Domänen hinzugefügt werden.
    
- Sie müssen eine CSV-Datei mit dem vollständigen Namen und der e-Mail-Adresse jedes Postfachs erstellen, das in einem Batch migriert werden soll. Sie müssen auch ein neues Kennwort für jedes zu migrierende Postfach hinzufügen und dann an jeden Benutzer ein Kennwort senden. Der Benutzer wird aufgefordert, das Kennwort zu ändern, wenn er sich das erste Mal bei seinem neuen Microsoft 365-Postfach anmeldet.
    
- Zwischen dem Zeitpunkt des Starts des Migrationsbatches und dem Beginn der Abschlussphase synchronisiert Microsoft 365 regelmäßig die im Batch enthaltenen Microsoft 365-und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber machen zu müssen, dass e-Mails in Ihren lokalen Postfächern hinterlassen werden.
    
- Benutzer erhalten neue temporäre Kennwörter für Ihr Microsoft 365-Konto, die Sie ändern müssen, wenn Sie sich zum ersten Mal bei Ihrem Postfach anmelden.
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren;
    
- Benutzer müssen auf jedem Ihrer Geräte ein neues Outlook-Profil einrichten und Ihre e-Mails erneut herunterladen. Die Menge an e-Mails, die von Outlook heruntergeladen werden können, kann variieren. Weitere Informationen finden Sie unter [Ändern der Nachrichtenmenge, die Offline aufbewahrt werden soll](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Weitere Informationen zur mehrstufigen Migration finden Sie unter:
  
- [Was Sie über eine mehrstufige e-Mail-Migration wissen müssen](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Durchführen einer mehrstufigen Migration von e-Mails](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Vollständige hybridbereitstellung

Eine vollständige Hybrid Migration ist eine, in der Ihre Organisation viele Hunderte, bis zu Zehntausende von Postfächern hat und Sie einige oder alle von Ihnen zu Microsoft 365 verschieben möchten. Da diese Migrationen normalerweise längerfristig sind, ermöglichen Hybrid Migrationen Folgendes:
  
- Zeigen Sie lokalen Benutzern die Frei/Gebucht-Kalenderinformationen für Benutzer in Microsoft 365 und umgekehrt;
    
- Siehe eine einheitliche globale Adressliste, die Empfänger sowohl in lokalen als auch in Microsoft 365 enthält;
    
- Anzeigen der vollständigen Outlook-Empfänger Eigenschaften für alle Benutzer, unabhängig davon, ob Sie lokal oder in Microsoft 365 sind;
    
- Sichere e-Mail-Kommunikation zwischen lokalen Exchange-Servern und Microsoft 365 mithilfe von TLS und Zertifikaten;
    
- Behandeln Sie Nachrichten, die zwischen lokalen Exchange-Servern und Microsoft 365 gesendet werden, als intern, sodass Sie folgende Möglichkeiten haben:
    
  - Durch Transport-und Compliance-Agents, die auf interne Nachrichten Zielen, ordnungsgemäß ausgewertet und verarbeitet werden;
    
  - Umgehen von Anti-Spam-Filtern.
    
Vollständige Hybrid Migrationen eignen sich am besten für Organisationen, die für mehrere Monate oder mehr in einer Hybrid Konfiguration bleiben möchten. Sie erhalten die weiter oben in diesem Abschnitt aufgeführten Features sowie die Verzeichnissynchronisierung, bessere integrierte Compliance-Features und die Möglichkeit, Postfächer mithilfe von Online Postfachverschiebungen von und nach Microsoft 365 zu verschieben. Microsoft 365 wird zu einer Erweiterung Ihrer lokalen Organisation.
  
Wenn Sie über eine vollständige Hybrid Migration nachdenken, sollten Sie Folgendes beachten:
  
- Vollständige Hybrid Migrationen sind nicht für alle Arten von Organisationen geeignet. Aufgrund der Komplexität von vollständigen Hybrid Migrationen sehen Organisationen mit weniger als ein paar hundert Postfächern normalerweise keine Vorteile, die den Aufwand und die Kosten rechtfertigen, die für die Einrichtung eines eingerichtet werden müssen. Wenn dies wie Ihre Organisation klingt, wird dringend empfohlen, stattdessen Cutover oder mehrstufige Migrationen zu verwenden.
    
- Sie müssen mindestens einen Exchange 2013 Server in Ihrer Exchange 2007 Organisation bereitstellen, um als "hybridserver" fungieren zu können. Dieser Server kommuniziert mit Microsoft 365 im Namen Ihrer Exchange 2007 Server;
    
- Microsoft 365 muss eine Verbindung mit dem "hybridserver" mit Outlook Anywhere über TCP-Port 443 herstellen;
    
- Sie müssen die Verzeichnissynchronisierung mithilfe von Azure Active Directory (Azure AD) zwischen Ihren lokalen Active Directory Servern und Microsoft 365 herstellen.
    
- Benutzer können sich bei Ihrem Microsoft 365-Postfach mit dem gleichen Benutzernamen und Kennwort anmelden, die Sie bei der Anmeldung beim lokalen Netzwerk verwenden (erfordert Azure AD Verbindung mit der Kennwortsynchronisierung und/oder Active Directory Verbunddiensten);
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren;
    
- Benutzer müssen kein neues Outlook-Profil auf den meisten Ihrer Geräte einrichten (einige ältere Android-Telefone benötigen möglicherweise ein neues Profil) und müssen Ihre e-Mails nicht erneut herunterladen.
    
Wenn eine vollständige Hybrid Migration für Sie richtig klingt, sehen Sie sich die folgenden Ressourcen an, um Sie bei der Migration zu unterstützen:
  
- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
    
- [Hybridbereitstellungen in Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [Assistent für die Hybridkonfiguration](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [FAQs zum Assistenten für die Hybridkonfiguration](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [Voraussetzungen für die Hybridbereitstellung](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrieren zu einer neueren Version von Exchange Server

Wir sind zwar der festen Überzeugung, dass Sie durch die Migration zu Microsoft 365 den besten Wert und die Benutzerfreundlichkeit erzielen können, aber wir verstehen auch, dass einige Organisationen ihre e-Mails lokal halten müssen. Dies kann an regulatorische Anforderungen liegen, um sicherzustellen, dass Daten nicht in einem Rechenzentrum in einem anderen Land gespeichert werden, und so weiter. Wenn Sie Ihre e-Mail-Adresse lokal behalten möchten, können Sie Ihre Exchange 2007 Umgebung zu Exchange 2010, Exchange 2013 oder Exchange 2016 migrieren.
  
Es wird empfohlen, dass Sie zu Exchange 2016 migrieren, wenn Sie nicht zu Microsoft 365 migrieren können. Exchange 2016 umfasst alle Features und Fortschritte, die in früheren Versionen von Exchange enthalten sind, und es entspricht am ehesten der verfügbaren Benutzeroberfläche von Microsoft 365 (obwohl einige Funktionen nur in Microsoft 365 verfügbar sind). Sehen Sie sich nur einige der Dinge an, die Ihnen fehlen:
  
|**Exchange-Version**|**Features**|
|:-----|:-----|
|Exchange 2010  <br/> | Rollenbasierte Zugriffssteuerung (Berechtigungen ohne ACLs)  <br/>  Outlook Web App-Postfachrichtlinien  <br/>  Möglichkeit zum Freigeben von frei/gebucht-und Delegieren von Kalendern zwischen Organisationen  <br/> |
|Exchange 2013  <br/> | *Features aus Exchange 2010 und...*  <br/>  Vereinfachte Architektur Verringerung der Anzahl von Serverrollen auf drei (Postfach, Client Zugriff, Edge-Transport)  <br/>  Datenverlust-Verhinderung-Richtlinien (DLP), mit denen vertrauliche Informationen vor Undichtigkeiten bleiben  <br/>  Erheblich verbesserte Outlook Web App Erfahrung  <br/> |
|Exchange 2016  <br/> | *Features aus Exchange 2013 und...*  <br/>  Weitere vereinfachte Serverrollen nur für Postfach-und Edge-Transport  <br/>  Verbesserte DLP zusammen mit der Integration in SharePoint  <br/>  Verbesserte Ausfallsicherheit der Datenbank  <br/>  Online Dokument Zusammenarbeit  <br/> |
   
#### <a name="which-version-should-i-migrate-to"></a>In welche Version sollte ich migrieren?

Es wird empfohlen, dass Sie zunächst davon ausgehen, dass Sie zu Exchange 2016 migrieren. Verwenden Sie dann die folgenden Informationen, um Ihre Annahme zu bestätigen oder Exchange 2016 auszuschließen. Wenn Sie aus einem bestimmten Grund nicht zu Exchange 2016 migrieren können, führen Sie denselben Vorgang mit Exchange 2013 aus usw.
  
|**Berücksichtigt**|**Weitere Informationen**|
|:-----|:-----|
|Ende der Support Daten  <br/> | Wie Exchange 2007 verfügt jede Version von Exchange über ein eigenes Datum für die Unterstützung des Supports:  <br/> **Exchange 2010** -Januar 2020  <br/> **Exchange 2013** -April 2023  <br/> **Exchange 2016** -Oktober 2025  <br/>  Je früher das Ende des Support Datums ist, desto schneller müssen Sie eine weitere Migration durchführen. Januar 2020 ist viel näher als Sie denken!  <br/> |
|Migrationspfad zu Exchange 2010 und 2013  <br/> |Im folgenden finden Sie die allgemeinen Phasen für die Migration zu Exchange 2010 oder Exchange 2013:  <br/> Installieren von Exchange 2010 oder 2013 in Ihrer vorhandenen Exchange 2007 Organisation verschieben von Diensten und anderen Infrastrukturen in Exchange 2010 oder 2013 Verschieben von Postfächern und öffentlichen Ordnern auf Exchange 2010 oder 2013 still gebliebenen Exchange 2007 Servern |
|Migrationspfad zu Exchange 2016  <br/> |Im folgenden finden Sie die allgemeinen Phasen für die Migration zu Exchange 2016:  <br/> Installieren Sie Exchange 2013 in Ihrer vorhandenen Exchange 2007 Organisation verschieben von Diensten und anderen Infrastrukturen, um Exchange 2013 Verschieben von Postfächern und öffentlichen Ordnern Exchange 2013 Stilllegung von Dienst Resten Exchange 2007 Server installieren Exchange 2016 in Ihrer vorhandenen Exchange 2013 Organisation. Verschieben von Postfächern, öffentlichen Ordnern, Diensten und anderen Infrastrukturen nach Exchange 2016 (Reihenfolge spielt keine Rolle). Stilllegung der verbleibenden Exchange 2013 Server > [!NOTE]> die Migration von Exchange 2013 zu Exchange 2016 ist einfach. Beide Versionen haben fast die gleichen Hardwareanforderungen. Dies und die Tatsache, dass diese Versionen so kompatibel sind, bedeutet, dass Sie einen Server, den Sie für Exchange 2013 gekauft haben, neu erstellen und Exchange 2016 darauf installieren können. Und bei Online Postfachverschiebungen wird den meisten Benutzern nie aufgefallen, dass Ihr Postfach vom Server verschoben und dann wieder zurückgegeben wird, nachdem Sie es mit Exchange 2016 neu erstellt haben.           |
|Versions Koexistenz  <br/> | Bei der Migration zu:  <br/> **Exchange 2016** Exchange 2016 kann nicht in einer Organisation installiert werden, die einen Exchange 2007 Server enthält. Zunächst müssen Sie zu Exchange 2010 oder 2013 migrieren (es wird dringend empfohlen, Exchange 2013), alle Exchange 2007 Server zu entfernen und dann zu Exchange 2016 zu migrieren.  <br/> **Exchange 2010 oder Exchange 2013** Sie können Exchange 2010 oder Exchange 2013 in einer vorhandenen Exchange 2007 Organisation installieren. Auf diese Weise können Sie einen oder mehrere Exchange 2010-oder 2013-Server installieren und die Migration durchführen.  <br/> |
|Serverhardware  <br/> | Die Server Hardwareanforderungen wurden von Exchange 2007 geändert. Sie müssen sicherstellen, dass die Hardware, die Sie verwenden werden, kompatibel ist. Hier finden Sie weitere Informationen zu den Hardwareanforderungen für jede Version:  <br/> [Exchange 2016-System Anforderungen](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Exchange 2013 System Anforderungen](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Exchange 2010 System Anforderungen](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Sie werden feststellen, dass Sie mit den signifikanten Verbesserungen bei der Exchange-Leistung und der erhöhten Rechenleistung und Speicherkapazität in neueren Servern wahrscheinlich weniger Server zur Unterstützung der gleichen Anzahl von Postfächern benötigen.  <br/> |
|Betriebssystemversion  <br/> | Für jede Version werden mindestens die folgenden Betriebssystemversionen unterstützt:  <br/> **Exchange 2016** Windows Server 2012  <br/> **Exchange 2013** Windows Server 2008 R2 SP1  <br/> **Exchange 2010** Windows Server 2008 SP2  <br/>  Weitere Informationen zur Betriebssystemunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Active Directory Gesamtstrukturfunktionsebene  <br/> | Für jede Version werden mindestens Active Directory Gesamtstrukturfunktionsebenen unterstützt:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Weitere Informationen zur Unterstützung der Gesamtstrukturfunktionsebene finden Sie unter [Exchange supportable Matrix](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
|Office-Clientversionen  <br/> | Für jede Version werden mindestens die folgenden Office-Clientversionen unterstützt:  <br/> **Exchange 2016** Office 2010 (mit den neuesten Updates)  <br/> **Exchange 2013** Office 2007 SP3  <br/> **Exchange 2010** Office 2003  <br/>  Weitere Informationen zur Office-Clientunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Wie kann ich migrieren?

Wenn Sie sich entschieden haben, Ihre e-Mail-Adresse lokal zu halten, können Sie die folgenden Ressourcen verwenden, um Sie bei der Migration zu unterstützen:
  
- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
    
- Active Directory Schemaänderungen für Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- System Anforderungen für Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)
    
- Voraussetzungen für Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx), [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx), [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)
    
## <a name="what-if-i-need-help"></a>Was kann ich tun, wenn ich Hilfe brauche?

Wenn Sie eine Migration zu Microsoft 365 durchführen, können Sie möglicherweise den Microsoft-kurzleistungs Dienst verwenden. In diesem Artikel werden bewährte Methoden, Tools und Ressourcen bereitgestellt, um die Migration zu Microsoft 365 so nahtlos wie möglich zu gestalten. Das beste daran ist, dass Sie einen echten Supporttechniker haben, der Sie durch die Migration führt – von der Planung und dem Entwurf bis hin zur Migration Ihres letzten Postfachs. Wenn Sie mehr über die Kurzzeit erfahren möchten, sehen Sie sich [Microsoft](https://fasttrack.microsoft.com/)kurzfall an.
  
Wenn bei der Migration zu Microsoft 365 Probleme auftreten und Sie nicht den Kurzlauf oder die Migration zu einer neueren Version von Exchange Server verwenden, helfen wir Ihnen gerne weiter. Hier sind einige Ressourcen, die Sie verwenden können:
  
- [Technische Community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Support für Kunden](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Verwandte Themen

[Ressourcen für ein Upgrade Ihrer Office 2007-Server und-Clients](upgrade-from-office-2007-servers-and-products.md)