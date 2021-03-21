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
description: Erfahren Sie mehr über Ihre Optionen Exchange Server 2007-Supportende, und beginnen Sie mit der Planung der Migration zu Microsoft 365, Office 365 oder Exchange 2016.
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924200"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Ende der Unterstützung für Exchange 2007 – Roadmap

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Exchange Server 2007 wurde im April 2017 das Ende der Unterstützung erreicht. Wenn Sie die Migration von Exchange 2007 zu Microsoft 365, Office 365 oder Exchange 2016 nicht gestartet haben, ist jetzt die Zeit für die Planung.
  
## <a name="what-does-end-of-support-mean"></a>Was bedeutet *das Ende der Unterstützung?*

Exchange Server wie fast alle #A0 verfügt über einen Supportlebenszyklus, in dem wir neue Features, Fehlerbehebungen, Sicherheitskorrekturen und so weiter bereitstellen. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Produktversion. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Seit Exchange 2007 am 11. April 2017 das Ende des Supportendes erreicht hat, bietet Microsoft nicht mehr:
  
- Technischer Support für Probleme, die auftreten können.
    
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
    
- Sicherheitsbehebungen für Sicherheitsrisiken, die den Server anfällig für Sicherheitsverletzungen machen können.
    
- Zeitzonenupdates.
    
Ihre Installation von Exchange 2007 wird nach dem End-of-Support-Datum fortgesetzt. Da es jedoch keine neuen Updates oder Support gibt, wird dringend empfohlen, so bald wie möglich von Exchange 2007 zu migrieren.
  
Weitere Informationen zu Office 2007-Servern, die sich dem Ende des Support nähern, finden Sie unter [Plan your upgrade from Office 2007 servers and products](upgrade-from-office-2007-servers-and-products.md).
  
## <a name="what-are-my-options"></a>Was sind meine Optionen?

Sie können:
  
- Migrieren Sie zu Microsoft 365 mithilfe von Umschalt-, Mehrstufiger oder Hybridmigration.
    
- Migrieren Sie Ihre Exchange 2007-Server zu einer neueren Version von Exchange auf Ihren lokalen Servern.
    
In den folgenden Abschnitten werden die einzelnen Optionen ausführlicher behandelt.
  
### <a name="migrate-to-microsoft-365"></a>Migrieren zu Microsoft 365

Das Migrieren Ihrer E-Mails zu Microsoft 365 ist die beste und einfachste Option, um Ihre Exchange 2007-Bereitstellung zurückzuziehen. Mit einer Migration zu Microsoft 365 können Sie einen einzigen Hop von einer 10 Jahre alten Technologie zu den modernsten Features erstellen, einschließlich:
  
- Compliancefunktionen wie Aufbewahrungsrichtlinien, In-Place und Rechtsstreitigkeiten, in-place eDiscovery und vieles mehr
    
- Microsoft 365-Gruppen
    
- Posteingang mit Relevanz
    
- MyAnalytics
    
- REST-APIs für programmgesteuerten Zugriff auf E-Mails, Kalender, Kontakte und so weiter
    
Microsoft 365 erhält auch zuerst neue Features und Erfahrungen, sodass Sie und Ihre Benutzer in der Regel sofort damit beginnen können, sie zu verwenden. Und Sie müssen sich keine Sorgen machen:
  
- Kaufen und Verwalten von Hardware.
    
- Bezahlen, um Ihre Server zu erhitze und zu coolen.
    
- Halten Sie die Sicherheits-, Produkt- und Zeitzonenkorrekturen auf dem neuesten Stand.
    
- Verwalten von Speicher und Software zur Unterstützung von Complianceanforderungen.
    
- Upgrade auf eine neue Version von Exchange. Mit Microsoft 365 sind Sie immer auf der neuesten Version von Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Wie sollte ich zu Microsoft 365 migrieren?

Sie haben einige Migrationsoptionen. Sie müssen einige Dinge berücksichtigen, z. B.:

- Die Anzahl der Zu verschiebende Sitze oder Postfächer.
- Wie lange die Migration dauern soll.
- Gibt an, ob Sie während der Migration eine nahtlose Integration zwischen Ihrer lokalen Installation und Microsoft 365 benötigen.

In dieser Tabelle sind die Migrationsoptionen und die wichtigsten Faktoren aufgeführt, die bestimmen, welche Methode verwendet werden soll:
  

|**Migrationsoption**|**Organisationsgröße**|**Duration**|
|:-----|:-----|:-----|
|Übernahmemigration  <br/> |Weniger als 150 Plätze  <br/> |Eine Woche oder weniger  <br/> |
|Mehrstufige Migration  <br/> |Mehr als 150 Plätze  <br/> |Ein paar Wochen  <br/> |
|Vollständige Hybridmigration  <br/> |Mehrere hundert bis tausende Arbeitsplätze  <br/> |Ein paar Monate oder mehr  <br/> |
   
Die folgenden Abschnitte bieten eine Übersicht über diese Methoden. Weitere Informationen finden Sie unter [Decide on a migration path](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27). 
  
#### <a name="cutover-migration"></a>Übernahmemigration

Bei einer Cutovermigration migrieren Sie alle Postfächer, Verteilergruppen, Kontakte und so weiter zu Microsoft 365 zu einem vorab ausgewählten Datum und uhrzeit. Nach Abschluss der Migration fahren Sie Ihre lokalen Exchange-Server herunter, und beginnen Sie mit der ausschließlichen Verwendung von Microsoft 365.
  
Die Umstiegsmigration ist ideal für kleine Organisationen, die nicht über viele Postfächer verfügen, schnell zu Microsoft 365 kommen möchten und sich nicht mit den Komplexitäten der anderen Methoden beschäftigen möchten. Sie sollte jedoch in einer oder weniger Wochen abgeschlossen sein und erfordert, dass Benutzer ihre Outlook-Profile neu konfigurieren. Die Cutovermigration kann bis zu 2.000 Postfächer verarbeiten, es wird jedoch dringend empfohlen, sie für die Migration von maximal 150 Postfächern zu verwenden. Wenn Sie versuchen, mehr zu migrieren, könnte ihnen die Zeit zum Übertragen aller Postfächer vor Ablauf des Stichtermins nicht mehr zur Verfügung kommen, und Ihre IT-Supportmitarbeiter sind möglicherweise überlastet mit Anforderungen, die Benutzern bei der Neukonfiguration von Outlook helfen.
  
Wenn Sie darüber nachdenken, eine Umstiegsmigration zu machen, sollten Sie dies berücksichtigen:
  
- Microsoft 365 muss mithilfe von Outlook Anywhere über TCP-Port 443 eine Verbindung mit Ihren Exchange 2007-Servern herstellen.
    
- Alle lokalen Postfächer werden zu Microsoft 365 verschoben.
    
- Sie benötigen ein lokales Administratorkonto mit Lesezugriff auf die Postfächer Ihrer Benutzer.
    
- Die akzeptierten Exchange 2007-Domänen, die Sie in Microsoft 365 verwenden möchten, müssen als überprüfte Domänen im Dienst hinzugefügt werden.
    
- Zwischen dem Beginn der Migration und dem Beginn der Abschlussphase synchronisiert Microsoft 365 regelmäßig die Microsoft 365- und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber zu machen, dass E-Mails in Ihren lokalen Postfächern zurückgelassen werden.
    
- Benutzer erhalten neue temporäre Kennwörter für ihre Microsoft 365-Konten. Sie müssen ihr Kennwort ändern, wenn sie sich zum ersten Mal bei ihrem Postfach anmelden.
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes migrierte Benutzerpostfach enthält.
    
- Benutzer müssen auf jedem Gerät ein neues Outlook-Profil einrichten und ihre E-Mails erneut herunterladen. Die Menge der E-Mails, die Outlook herunterladen wird, kann variieren. Weitere Informationen finden Sie unter [Change how much mail to keep offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Weitere Informationen zur Umstellungsmigration finden Sie unter:
  
- [Was Sie über eine E-Mail-Migration für die Umstellung wissen müssen](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [Durchführen einer Umstiegsmigration von E-Mails](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>Mehrstufige Migration

In einer mehrstufigen Migration verfügen Sie über ein paar hundert oder ein paar tausend Postfächer, die Sie zu Microsoft 365 migrieren möchten, eine Woche oder mehr benötigen, um die Migration abschließen zu können, und benötigen keine erweiterten Hybridmigrationsfunktionen wie freigegebene Frei/Gebucht-Kalenderinformationen.
  
Die mehrstufige Migration ist ideal für Organisationen, die mehr Zeit für die Migration ihrer Postfächer zu Microsoft 365 benötigen, aber dennoch planen, die Migration innerhalb weniger Wochen zu abschließen. Sie können Postfächer in Batches migrieren. Sie steuern, wie viele und welche Postfächer zu einem bestimmten Zeitpunkt migriert werden. Sie können Beispielsweise Postfächer von Benutzern in derselben Abteilung batchen, um sicherzustellen, dass alle gleichzeitig verschoben werden. Sie können auch die Postfächer von Führungskräften bis zum letzten Batch verlassen. Wie bei Denkmigrationen müssen Ihre Benutzer ihre Outlook-Profile neu erstellen.
  
Wenn Sie über eine mehrstufige Migration nachdenken, sollten Sie dies berücksichtigen:
  
- Microsoft 365 muss über Outlook Anywhere über TCP-Port 443 eine Verbindung mit Ihren Exchange 2007-Servern herstellen.
    
- Sie benötigen ein lokales Administratorkonto mit Lesezugriff auf die Postfächer Ihrer Benutzer.
    
- Die von Exchange 2007 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen als überprüfte Domänen im Dienst hinzugefügt werden.
    
- Sie müssen eine CSV-Datei mit dem vollständigen Namen und der E-Mail-Adresse jedes Postfachs erstellen, das Sie in einem Batch migrieren möchten. Sie müssen auch ein neues Kennwort für jedes Postfach angeben, das Sie migrieren, und dieses Kennwort an jeden Benutzer senden. Der Benutzer wird aufgefordert, das Kennwort bei der ersten Anmeldung beim neuen Microsoft 365-Postfach zu ändern.
    
- Zwischen dem Start des Migrationsbatches und dem Beginn der Abschlussphase synchronisiert Microsoft 365 regelmäßig die im Batch enthaltenen Microsoft 365- und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber zu machen, dass E-Mails in Ihren lokalen Postfächern zurückgelassen werden.
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes migrierte Benutzerpostfach enthält.
    
- Benutzer müssen auf jedem Gerät ein neues Outlook-Profil einrichten und ihre E-Mails erneut herunterladen. Die Menge der E-Mails, die Outlook herunterladen wird, kann variieren. Weitere Informationen finden Sie unter [Change how much mail to keep offline](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1).
    
Weitere Informationen zur mehrstufigen Migration finden Sie unter:
  
- [Was Sie über eine mehrstufige E-Mail-Migration wissen müssen](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [Durchführen einer mehrstufigen Migration von E-Mails](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>Vollständige Hybridbereitstellung

Bei einer vollständigen Hybridmigration verfügt Ihre Organisation über viele Hundert, bis zu Zehntausende von Postfächern, und Sie möchten einige oder alle Postfächer nach Microsoft 365 verschieben. Da es sich bei diesen Migrationen in der Regel um langfristige Migrationen handelt, ermöglichen Hybridmigrationen:
  
- Zeigen Sie lokalen Benutzern die Frei/Gebucht-Kalenderinformationen für Benutzer in Microsoft 365 an und umgekehrt.
    
- Sehen Sie sich eine einheitliche globale Adressliste an, die Empfänger sowohl lokal als auch in Microsoft 365 enthält.
    
- Zeigen Sie vollständige Outlook-Empfängereigenschaften für alle Benutzer an, unabhängig davon, ob sie lokal oder in Microsoft 365 sind.
    
- Sichere E-Mail-Kommunikation zwischen lokalen Exchange-Servern und Microsoft 365 mithilfe von TLS und Zertifikaten.
    
- Behandeln Sie Nachrichten, die zwischen lokalen Exchange-Servern und Microsoft 365 gesendet werden, als intern, sodass sie:
    
  - Sollten Sie von Transport- und Compliance-Agents, die auf interne Nachrichten zielen, ordnungsgemäß ausgewertet und verarbeitet werden.
    
  - Umgehen von Antispamfiltern.
    
Die vollständige Hybridmigration ist am besten für Organisationen, die erwarten, dass sie viele Monate oder länger in einer Hybridkonfiguration bleiben. Sie erhalten die oben in diesem Abschnitt aufgeführten Features sowie Verzeichnissynchronisierung, bessere integrierte Compliancefeatures und die Möglichkeit, Postfächer mithilfe von Onlinepostfachbewegungen zu und von Microsoft 365 zu verschieben. Microsoft 365 wird zu einer Erweiterung Ihrer lokalen Organisation.
  
Wenn Sie über eine vollständige Hybridmigration nachdenken, sollten Sie dies berücksichtigen:
  
- Die vollständige Hybridmigration ist nicht für alle Arten von Organisationen geeignet. Aufgrund der Komplexität vollständiger Hybridmigrationen sehen Organisationen mit weniger als ein paar hundert Postfächern in der Regel keine Vorteile, die den Aufwand und die Kosten rechtfertigen, die zum Einrichten eines Postfachs erforderlich sind. Wenn dies wie Ihre Organisation klingt, wird empfohlen, stattdessen eine Umstellung oder mehrstufige Migration in Betracht zu ziehen.
    
- Sie müssen mindestens einen Exchange 2013-Server in Ihrer Exchange 2007-Organisation bereitstellen, um als "Hybridserver" zu fungieren. Dieser Server kommuniziert im Namen Ihrer Exchange 2007-Server mit Microsoft 365.
    
- Microsoft 365 muss eine Verbindung mit dem "Hybridserver" über Outlook Anywhere über TCP-Port 443 herstellen.
    
- Sie müssen die Verzeichnissynchronisierung mithilfe von Azure Active Directory (Azure AD) Connect zwischen Ihren lokalen Active Directory-Servern und Microsoft 365 einrichten.
    
- Benutzer können sich bei ihrem Microsoft 365-Postfach mit demselben Benutzernamen und Kennwort wie bei der Anmeldung beim lokalen Netzwerk anmelden. (Diese Funktionalität erfordert Azure AD Connect mit Kennwortsynchronisierung und/oder Active Directory-Verbunddiensten.)
    
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes migrierte Benutzerpostfach enthält.
    
- Benutzer müssen auf den meisten Geräten kein neues Outlook-Profil einrichten, auch wenn einige ältere Android-Smartphones möglicherweise ein neues Profil benötigen. Benutzer müssen ihre E-Mails nicht erneut laden.
    
Wenn die vollständige Hybridmigration für Sie richtig klingt, sehen Sie sich die folgenden Ressourcen an, die Ihnen bei der Migration helfen:
  
- [Exchange-Bereitstellungs-Assistent](/exchange/exchange-deployment-assistant)
    
- [Hybridbereitstellungen in Exchange Server](/exchange/exchange-hybrid)
    
- [Assistent für die Hybridkonfiguration](/exchange/hybrid-configuration-wizard)
    
- [FAQs zum Assistenten für die Hybridkonfiguration](/exchange/hybrid-configuration-wizard-faqs)
    
- [Voraussetzungen für die Hybridbereitstellung](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>Migrieren zu einer neueren Version von Exchange Server

Wir sind fest davon überzeugt, dass Sie durch die Migration zu Microsoft 365 den besten Nutzen und eine optimale Benutzererfahrung erzielen können. Wir wissen aber auch, dass einige Organisationen ihre E-Mails lokal behalten müssen. Dies kann aufgrund gesetzlicher Anforderungen liegen, um zu gewährleisten, dass Daten nicht in einem Datencenter in einem anderen Land oder ähnlichen Ländern gespeichert werden. Wenn Sie Ihre E-Mail lokal behalten möchten, können Sie Ihre Exchange 2007-Umgebung zu Exchange 2010, Exchange 2013 oder Exchange 2016 migrieren.
  
Wenn Sie nicht zu Microsoft 365 migrieren können, wird empfohlen, zu Exchange 2016 zu migrieren. Exchange 2016 enthält alle Features früherer Versionen von Exchange. Sie entspricht auch am besten der mit Microsoft 365 verfügbaren Erfahrung, obwohl einige Features nur in Microsoft 365 verfügbar sind. Sehen Sie sich nur einige der Dinge an, die Ihnen fehlten:
  
|**Exchange-Version**|**Features**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based Zugriffssteuerung (Berechtigungen ohne Zugriffssteuerungsberechtigungen)  <br/>  Outlook Web App-Postfachrichtlinien  <br/>  Möglichkeit zum Freigeben von Frei/Gebucht- und Delegieren von Kalendern zwischen Organisationen  <br/> |
|Exchange 2013  <br/> | *Features aus Exchange 2010 und ...*  <br/>  Vereinfachte Architektur, die die Anzahl der Serverrollen auf drei reduzierte (Postfach, Clientzugriff, Edge-Transport)  <br/>  Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die dazu beitragen, vertrauliche Informationen vor Lecks zu bewahren  <br/>  Verbesserte Outlook Web App-Erfahrung  <br/> |
|Exchange 2016  <br/> | *Features aus Exchange 2013 und ...*  <br/>  Weitere vereinfachte Serverrollen für nur Postfach- und Edge-Transport  <br/>  Verbesserte DLP und Integration in SharePoint  <br/>  Verbesserte Ausfallsicherheit von Datenbanken  <br/>  Online-Dokumentzusammenarbeit |
   
#### <a name="which-version-should-i-migrate-to"></a>Zu welcher Version sollte ich migrieren?

Es wird empfohlen, zunächst davon aus zu gehen, dass Sie zu Exchange 2016 migrieren. Verwenden Sie dann die folgenden Informationen, um Ihre Annahme zu bestätigen oder Exchange 2016 zu ausschließen. Wenn Sie aus einem bestimmten Grund nicht zu Exchange 2016 migrieren können, müssen Sie denselben Prozess mit Exchange 2013 und so weiter machen.
  
|**Überlegungen**|**Weitere Informationen**|
|:-----|:-----|
|Ende der Supporttermine  <br/> | Wie Exchange 2007 hat jede Version von Exchange ein eigenes End-of-Support-Datum:  <br/> *Exchange 2010* – Januar 2020  <br/> *Exchange 2013* – April 2023  <br/> *Exchange 2016* – Oktober 2025  <br/>  Mit dem früheren Ende der Unterstützung müssen Sie früher eine weitere Migration durchführen.<br/> |
|Migrationspfad zu Exchange 2010 und 2013.  <br/> |Hier sind die allgemeinen Phasen für die Migration zu Exchange 2010 oder Exchange 2013:  <br/> – Installieren Sie Exchange 2010 oder 2013 in Ihrer vorhandenen Exchange 2007-Organisation. <br/>– Verschieben von Diensten und anderer Infrastruktur nach Exchange 2010 oder 2013.<br/>– Verschieben von Postfächern und öffentlichen Ordnern nach Exchange 2010 oder 2013.<br/>– Außerbetriebsetzen der verbleibenden Exchange 2007-Server. |
|Migrationspfad zu Exchange 2016  <br/> |Hier sind die allgemeinen Phasen für die Migration zu Exchange 2016:  <br/> – Installieren Sie Exchange 2013 in Ihrer vorhandenen Exchange 2007-Organisation.<br/>– Verschieben von Diensten und anderer Infrastruktur nach Exchange 2013.<br/>– Verschieben von Postfächern und öffentlichen Ordnern nach Exchange 2013.<br/>– Außerbetriebsetzen der verbleibenden Exchange 2007-Server.<br/>– Installieren Sie Exchange 2016 in Ihrer vorhandenen Exchange 2013-Organisation.<br/>- Verschieben von Postfächern, öffentlichen Ordnern, Diensten und anderer Infrastruktur nach Exchange 2016 (Reihenfolge spielt keine Rolle). Außerbetriebsetzen der verbleibenden Exchange 2013-Server.<br/><br/> **Hinweis:** Die Migration von Exchange 2013 zu Exchange 2016 ist einfach. Die beiden Versionen haben fast dieselben Hardwareanforderungen, und diese Versionen sind sehr kompatibel. Sie können also einen Server neu erstellen, den Sie für Exchange 2013 erworben haben, und Exchange 2016 auf diesem Server installieren. Bei Onlinepostfachbewegungen bemerken die meisten Benutzer nicht einmal, dass ihr Postfach vom Server und dann zurück verschoben wurde, nachdem Sie es mit Exchange 2016 neu erstellt haben.           |
|Versionskoexistenz  <br/> | Bei der Migration zu ...  <br/> **Exchange 2016:** Exchange 2016 kann nicht in einer Organisation installiert werden, die einen Exchange 2007-Server enthält. Sie müssen zunächst zu Exchange 2010 oder 2013 migrieren (wir empfehlen dringend Exchange 2013), alle Exchange 2007-Server entfernen und dann zu Exchange 2016 migrieren.  <br/> **Exchange 2010 oder Exchange 2013:** Sie können Exchange 2010 oder Exchange 2013 in einer vorhandenen Exchange 2007-Organisation installieren. Auf diese Weise können Sie einen oder mehrere Exchange 2010- oder 2013-Server installieren und die Migration durchführen.  <br/> |
|Serverhardware  <br/> | Die Serverhardwareanforderungen haben sich von Exchange 2007 geändert. Stellen Sie sicher, dass Ihre Hardware kompatibel ist. Weitere Informationen finden Sie unter:  <br/> [Exchange 2016-Systemanforderungen](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013-Systemanforderungen](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010-Systemanforderungen](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  Sie werden feststellen, dass die erhebliche Verbesserung der Exchange-Leistung und die erhöhte Rechenleistung und Speicherkapazität auf neueren Servern dazu führen, dass Sie wahrscheinlich weniger Server benötigen, um dieselbe Anzahl von Postfächern zu unterstützen.  <br/> |
|Betriebssystemversion  <br/> | Die mindestens unterstützten Betriebssystemversionen für jede Version sind:  <br/> **Exchange 2016** – Windows Server 2012  <br/> **Exchange 2013** – Windows Server 2008 R2 SP1  <br/> **Exchange 2010** – Windows Server 2008 SP2  <br/>  Weitere Informationen zur Betriebssystemunterstützung finden Sie unter [Exchange Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
|Active Directory-Gesamtstrukturfunktionsebene  <br/> | Die mindestens unterstützten Active Directory-Gesamtstrukturfunktionsebenen für jede Version sind:  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  Weitere Informationen zur Unterstützung der Gesamtstrukturfunktionsebene finden Sie unter [Exchange Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
|Office-Clientversionen  <br/> | Die mindestens unterstützten Office-Clientversionen für jede Version sind:  <br/> **Exchange 2016** – Office 2010 (mit den neuesten Updates)  <br/> **Exchange 2013** – Office 2007 SP3  <br/> **Exchange 2010** – Office 2003  <br/>  Weitere Informationen zur Office-Clientunterstützung finden Sie unter [Exchange Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix).  <br/> |
   
#### <a name="how-do-i-migrate"></a>Wie kann ich migrieren?

Wenn Sie sich entschieden haben, Ihre E-Mails lokal zu behalten, verwenden Sie die folgenden Ressourcen, um Bei der Migration zu helfen:
  
- [Exchange-Bereitstellungs-Assistent](/exchange/exchange-deployment-assistant)
    
- Active Directory-Schemaänderungen für Exchange [2016](/Exchange/plan-and-deploy/active-directory/ad-schema-changes), [2013](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help), [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- Systemanforderungen für Exchange [2016](/Exchange/plan-and-deploy/system-requirements), [2013](/exchange/exchange-2013-system-requirements-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))
    
- Voraussetzungen für Exchange [2016](/Exchange/plan-and-deploy/prerequisites), [2013](/exchange/exchange-2013-prerequisites-exchange-2013-help), [2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))
    
## <a name="get-help"></a>Hilfe erhalten

Wenn Sie zu Microsoft 365 migrieren, sind Sie möglicherweise berechtigt, unseren Microsoft FastTrack-Dienst zu verwenden. FastTrack bietet bewährte Methoden, Tools und Ressourcen, um Ihre Migration zu Microsoft 365 so nahtlos wie möglich zu gestalten. Das Beste ist, dass Sie von einem Supporttechniker durch Ihre Migration, von der Planung und dem Entwurf bis hin zur Migration Ihres letzten Postfachs, gehen. Weitere Informationen zu FastTrack finden Sie unter [Microsoft FastTrack](https://fasttrack.microsoft.com/).
  
Wenn während der Migration zu Microsoft 365 Probleme auftreten und Sie FastTrack nicht verwenden oder Ihre Migration zu einer neueren Version von Exchange Server, sind wir hier, um Ihnen zu helfen. Hier sind einige Ressourcen, die Sie verwenden können:
  
- [Technische Community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [Support für Kunden](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>Verwandte Themen

[Ressourcen, die Ihnen beim Upgrade Ihrer Office 2007-Server und -Clients helfen](upgrade-from-office-2007-servers-and-products.md)