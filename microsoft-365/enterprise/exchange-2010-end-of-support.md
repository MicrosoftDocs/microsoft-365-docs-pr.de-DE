---
title: Exchange 2010 – Roadmap zum Supportende
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 hat das Ende der Unterstützung erreicht. Verwenden Sie diese Planungsplanung, um ein Upgrade auf Exchange Online oder eine neuere Version von Exchange Server lokalen Versionen vorzubereiten.
ms.openlocfilehash: f3531802283368e533ba6646415d4acc019687bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926994"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 – Roadmap zum Supportende

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Exchange Server 2010 hat sein Ende der Unterstützung am **13. Oktober 2020 erreicht.** Wenn Sie noch nicht mit der Migration von Exchange 2010 zu Microsoft 365, Office 365 oder Exchange 2016 begonnen haben, können Sie jetzt mit der Planung beginnen.

## <a name="what-does-end-of-support-mean"></a>Was bedeutet *das Ende der Unterstützung?*

Die meisten #A0 verfügen über einen Supportlebenszyklus, in dem sie neue Features, Fehlerbehebungen, Sicherheitskorrekturen und so weiter erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Produktversion. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da Exchange 2010 sein Ende des Support am 13. Oktober 2020 erreicht hat, bietet Microsoft nicht mehr:

- Technischer Support für Probleme, die auftreten können.
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
- Sicherheitsbehebungen für Sicherheitsrisiken, die den Server anfällig für Sicherheitsverletzungen machen können.
- Zeitzonenupdates.

Ihre Installation von Exchange 2010 wird nach diesem Datum fortgesetzt. Aufgrund der oben aufgeführten Änderungen wird jedoch dringend empfohlen, so bald wie möglich von Exchange 2010 zu migrieren.

Weitere Informationen zum Ende des Supportendes finden Sie unter [Resources to help you upgrade from Office 2010 servers and clients](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Was sind meine Optionen?

Es ist eine großartige Zeit, Ihre Optionen zu erkunden und einen Migrationsplan vorzubereiten. Sie können:

- Migrieren Sie vollständig zu Microsoft 365. Migrieren von Postfächern mithilfe der Umschalt-, Minimalhybrid- oder vollständigen Hybridmigration. Entfernen Sie dann lokale Exchange server und Active Directory.
- Migrieren Sie Exchange 2010-Server zu Exchange 2016 auf Ihren lokalen Servern.

> [!IMPORTANT]
> Wenn Sich Ihre Organisation für die Migration von Postfächern zu Microsoft 365 entscheidet, aber plant, DirSync oder Azure AD Verbinden weiterhin zu verwalten, um Benutzerkonten aus lokalem Active Directory weiter zu verwalten, müssen Sie mindestens einen Microsoft Exchange-Server lokal halten. Wenn Sie alle Exchange entfernen, können Sie keine Änderungen an Exchange Empfängern in Exchange Online vornehmen, da die Autoritätsquelle in Ihrem lokalen Active Directory verbleibt. Dort müssen Änderungen vorgenommen werden. In diesem Szenario haben Sie die folgenden Optionen:
>
>- *Empfohlen:* Wenn Sie Ihre Postfächer zu Microsoft 365 migriert und Ihre Server bis zum 13. Oktober 2020 aktualisiert haben, verwenden Sie Exchange 2010, um eine Verbindung mit Microsoft 365 herzustellen und Postfächer zu migrieren. Migrieren Sie als Nächstes Exchange 2010 zu Exchange 2016, und außer Betrieb alle verbleibenden Exchange 2010-Server.
>- Wenn Sie die Postfachmigration und das lokale Serverupgrade bis zum 13. Oktober 2020 nicht abgeschlossen haben, aktualisieren Sie zuerst Ihre lokalen Exchange 2010-Server auf Exchange 2016. Verwenden Sie dann Exchange 2016, um eine Verbindung zu Microsoft 365 und Postfächer zu migrieren.

> [!NOTE]
> Es ist etwas komplizierter, aber Sie können Postfächer auch zu Microsoft 365 migrieren, während Sie Ihre lokalen Exchange 2010-Server zu Exchange 2016 migrieren.

Hier sind die drei Pfade, die Sie gehen können, um das Ende der Unterstützung für Exchange Server 2010 zu vermeiden.

![Exchange Server 2010-Upgradepfade](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

In den folgenden Abschnitten werden die einzelnen Optionen ausführlicher behandelt.

## <a name="migrate-to-microsoft-365"></a>Migrieren zu Microsoft 365

Das Migrieren Ihrer E-Mails zu Microsoft 365 ist die beste und einfachste Option, um Ihre Exchange 2010-Bereitstellung zurückzuziehen. Mit einer Migration zu Microsoft 365 können Sie einen einzelnen Hop von alter Technologie zu aktuellen Features erstellen, einschließlich:

- Compliancefunktionen wie Aufbewahrungsrichtlinien, In-Place und Rechtsstreitigkeiten, in-place eDiscovery und vieles mehr.
- Microsoft Teams.
- Power BI.
- Posteingang mit Fokus.
- MyAnalytics.

Microsoft 365 erhalten außerdem zuerst neue Features und Erfahrungen, damit Ihre Organisation sofort damit beginnen kann, sie zu verwenden. Darüber hinaus müssen Sie sich keine Sorgen machen:

- Kaufen und Verwalten von Hardware.
- Bezahlen, um Ihre Server zu erhitze und zu coolen.
- Halten Sie die Sicherheits-, Produkt- und Zeitzonenkorrekturen auf dem neuesten Stand.
- Verwalten von Speicher und Software zur Unterstützung von Complianceanforderungen.
- Upgrade auf eine neue Version von Exchange. Sie sind immer auf der neuesten Version von Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Wie sollte ich zu Microsoft 365?

Je nach Organisation stehen Ihnen einige Optionen zur Verfügung, um Microsoft 365. Zunächst müssen Sie einige Dinge berücksichtigen, z. B.:
- Die Anzahl der Zu verschiebende Sitze oder Postfächer.
- Wie lange die Migration dauern soll.
- Gibt an, ob Sie während der Migration eine nahtlose Integration zwischen ihrer lokalen Installation und Microsoft 365 benötigen.
 
In dieser Tabelle sind die Migrationsoptionen und die wichtigsten Faktoren aufgeführt, die bestimmen, welche Methode verwendet werden soll.

|Migrationsoption|Organisationsgröße|Dauer|
|---|---|---|
|Übernahmemigration|Weniger als 150 Plätze|Eine Woche oder weniger|
|Minimale Hybridmigration|Weniger als 150 Plätze|Ein paar Wochen oder weniger|
|Vollständige Hybridmigration|Mehr als 150 Plätze|Ein paar Wochen oder mehr|

In den folgenden Abschnitten erhalten Sie eine Übersicht über diese Methoden. Weitere Informationen finden Sie unter [Decide on a migration path](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Übernahmemigration

Bei einer Cutovermigration migrieren Sie alle Postfächer, Verteilergruppen, Kontakte und so weiter, um Office 365 datums- und uhrzeitgemäß zu löschen. Wenn Sie fertig sind, fahren Sie Ihre lokalen Server Exchange herunter und beginnen mit der verwendung von Microsoft 365.

Die Umstiegsmigration ist ideal für kleine Organisationen, die nicht über viele Postfächer verfügen, schnell zu Microsoft 365 und nicht mit der Komplexität der anderen Methoden umgehen möchten. Sie sollte jedoch in einer woche oder weniger abgeschlossen sein. Außerdem müssen Benutzer ihre Outlook neu konfigurieren. Bei der Umstiegsmigration können bis zu 2.000 Postfächer migriert werden, es wird jedoch empfohlen, sie für maximal 150 Postfächer zu verwenden. Wenn Sie versuchen, mehr zu migrieren, könnte ihnen die Zeit zum Übertragen aller Postfächer vor Ablauf des Stichtermins nicht mehr zur Verfügung sein, und Ihre IT-Supportmitarbeiter sind möglicherweise überlastet mit Anforderungen, die Benutzern beim Neukonfigurieren von Postfächern Outlook.

Hier sind einige Dinge, die Sie zur Umstellungsmigration berücksichtigen sollten:

- Microsoft 365 müssen eine Verbindung mit Ihren Exchange 2010-Servern mithilfe von Outlook Anywhere über TCP-Port 443 herstellen.
- Alle lokalen Postfächer werden in die Microsoft 365.
- Sie benötigen ein lokales Administratorkonto mit Lesezugriff auf die Postfächer Ihrer Benutzer.
- Die Exchange 2010 akzeptierte Domänen, die Sie in Microsoft 365 verwenden möchten, müssen als überprüfte Domänen im Dienst hinzugefügt werden.
- Zwischen dem Start der Migration und dem Beginn der Abschlussphase synchronisiert Microsoft 365 regelmäßig die Microsoft 365 und lokale Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber zu machen, dass E-Mails in Ihren lokalen Postfächern zurückgelassen werden.
- Benutzer erhalten neue temporäre Kennwörter für ihr Microsoft 365 Konto. Sie müssen diese ändern, wenn sie sich zum ersten Mal bei ihren Postfächern anmelden.
- Sie benötigen eine Microsoft 365, die Exchange Online benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf jedem Gerät ein neues Outlook einrichten und ihre E-Mails erneut herunterladen. Die Menge der E-Mails, die Outlook herunterladen, kann variieren. Weitere Informationen finden Sie unter [Offline arbeiten in Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Weitere Informationen zur Umstellung finden Sie unter:

- [Was Sie über eine E-Mail-Migration für die Umstellung wissen müssen](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Durchführen einer Umstiegsmigration von E-Mails zu Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimale Hybridmigration

Bei einer minimalen Hybridmigration oder einer express-Migration verschieben Sie innerhalb weniger Wochen ein paar hundert Postfächer Microsoft 365 Zu- und Abspeichern. Diese Methode unterstützt keine erweiterten Hybridmigrationsfeatures wie freigegebene Frei/Gebucht-Kalenderinformationen.

Die minimale Hybridmigration ist ideal für Organisationen, die mehr Zeit für die Migration ihrer Postfächer zu Microsoft 365 benötigen, aber dennoch planen, die Migration innerhalb weniger Wochen zu abschließen. Sie erhalten einige der Vorteile der fortgeschritteneren *Vollständighybridmigration* ohne einen großen Teil der Komplexität. Sie können steuern, wie viele und welche Postfächer zu einem bestimmten Zeitpunkt migriert werden sollen. Microsoft 365 Postfächer werden mit den Benutzernamen und Kennwörtern der lokalen Konten erstellt. Und im Gegensatz zu Umstiegsmigrationen müssen Ihre Benutzer ihre Outlook neu erstellen.

Hier sind einige Dinge, die Sie zur minimalen Hybridmigration berücksichtigen sollten:

- Sie müssen eine einmal durchgeführte Verzeichnissynchronisierung zwischen ihren lokalen Active Directory-Servern und Microsoft 365.
- Benutzer können sich bei ihrem Postfach Microsoft 365 Benutzernamen und Kennwort wie vor ihrem Postfach anmelden.
- Sie benötigen eine Microsoft 365, die Exchange Online benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf den meisten Geräten kein neues Outlook einrichten, obwohl einige ältere Android-Smartphones möglicherweise ein neues Profil benötigen. Benutzer müssen ihre E-Mails nicht erneut laden.

Weitere Informationen finden Sie unter [Use Minimal Hybrid to quickly migrate Exchange mailboxes to Office 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Vollständige Hybridbereitstellung

Bei einer vollständigen Hybridmigration verfügen Sie über viele Hunderte, bis zu Zehntausende von Postfächern, und Sie verschieben einige oder alle zu Microsoft 365. Da es sich bei diesen Migrationen in der Regel um langfristige Migrationen handelt, ermöglichen Hybridmigrationen:

- Zeigen Sie lokalen Benutzern die Frei/Gebucht-Kalenderinformationen für Benutzer in Microsoft 365 und umgekehrt.
- Sehen Sie sich eine einheitliche globale Adressliste an, die Empfänger in lokalen und lokalen Microsoft 365.
- Zeigen Sie Outlook Empfängereigenschaften für alle Benutzer an, unabhängig davon, ob sie lokal oder in Microsoft 365.
- Sichere E-Mail-Kommunikation zwischen lokalen Exchange und Office 365 TLS und Zertifikaten.
- Behandeln Sie Nachrichten, die zwischen lokalen servern Exchange und Microsoft 365 gesendet werden, als intern, sodass sie:
  - Sollten Sie von Transport- und Compliance-Agents, die auf interne Nachrichten zielen, ordnungsgemäß ausgewertet und verarbeitet werden.
  - Umgehen von Antispamfiltern.

Vollständige Hybridmigrationen sind am besten für Organisationen, die erwarten, dass sie viele Monate oder länger in einer Hybridkonfiguration bleiben. Sie erhalten die oben in diesem Abschnitt aufgeführten Features sowie Verzeichnissynchronisierung, bessere integrierte Kompatibilitätsfeatures und die Möglichkeit, Postfächer mithilfe von Onlinepostfachbewegungen Microsoft 365 zu verschieben. Microsoft 365 wird zu einer Erweiterung Ihrer lokalen Organisation.

Zu berücksichtigende Dinge zur Vollständighybridmigration:

- Sie sind nicht für alle Organisationen geeignet. Aufgrund der Komplexität vollständiger Hybridmigrationen sehen Organisationen mit weniger als ein paar hundert Postfächern in der Regel keine Vorteile, die den Aufwand und die damit verbunden Kosten rechtfertigen. In solchen Fällen wird empfohlen, stattdessen die Umstellung oder minimale Hybridmigration in Betracht zu ziehen.
- Sie müssen die Verzeichnissynchronisierung mithilfe von Azure Active Directory (Azure AD) Verbinden lokalen Active Directory-Servern und Microsoft 365.
- Benutzer können sich bei ihrem Postfach Microsoft 365 Benutzernamen und Kennwort anmelden, das sie bei der Anmeldung beim lokalen Netzwerk verwenden. (Für diese Funktionalität ist Azure AD Verbinden Kennwortsynchronisierung und/oder Active Directory Federation Services erforderlich).
- Sie benötigen eine Microsoft 365, die Exchange Online benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf den meisten Geräten kein neues Outlook einrichten, auch wenn einige ältere Android-Smartphones möglicherweise ein neues Profil benötigen. Benutzer müssen ihre E-Mails nicht erneut laden.

> [!IMPORTANT]
> Wenn Ihre Organisation postfächer zu Microsoft 365 migrieren will, aber plant, DirSync oder Azure AD Verbinden zu verwalten, um weiterhin Benutzerkonten aus lokalem Active Directory zu verwalten, müssen Sie mindestens einen Exchange-Server lokal halten. Wenn alle Exchange entfernt werden, können Sie keine Änderungen an Exchange Empfängern in Exchange Online. Dies liegt daran, dass die Autoritätsquelle in Ihrem lokalen Active Directory verbleibt und dort Änderungen vorgenommen werden müssen.

Wenn eine vollständige Hybridmigration für Sie richtig klingt, sehen Sie sich die folgenden hilfreichen Ressourcen an:

- [Exchange Bereitstellungs-Assistent](/exchange/exchange-deployment-assistant)
- [Hybridbereitstellungen in Exchange Server](/exchange/exchange-hybrid)
- [Assistent für die Hybridkonfiguration](/exchange/hybrid-configuration-wizard)
- [FAQs zum Assistenten für die Hybridkonfiguration](/exchange/hybrid-configuration-wizard-faqs)
- [Voraussetzungen für die Hybridbereitstellung](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Upgrade auf eine neuere Version Exchange Server lokalen Versionen

Wir sind fest davon überzeugt, dass Sie den bestmöglichen Nutzen und eine optimale Benutzererfahrung erhalten, indem Sie vollständig zu Microsoft 365. Wir wissen jedoch, dass einige Organisationen einige serverlokale Exchange müssen. Dies liegt möglicherweise an behördlichen Anforderungen, um zu gewährleisten, dass Daten nicht in einem fremden Rechenzentrum gespeichert werden, weil Sie über eindeutige Einstellungen oder Anforderungen verfügen, die in der Cloud nicht erfüllt werden können, oder weil Sie Exchange zum Verwalten von Cloudpostfächern benötigen, da Sie Active Directory weiterhin lokal verwenden. Wenn Sie die Exchange lokal verwenden, sollten Sie auf jeden Fall sicherstellen, dass Ihre Exchange 2010-Umgebung auf mindestens Exchange 2013 oder Exchange 2016 aktualisiert wird.

Für eine optimale Erfahrung empfehlen wir, die verbleibende lokale Umgebung auf Exchange 2016 zu aktualisieren. Sie müssen Exchange Server 2013 nicht installieren, wenn Sie direkt von Exchange Server 2010 bis Exchange Server 2016 wechseln möchten.

Exchange 2016 enthält alle Features früherer Versionen von Exchange. Sie entspricht am besten der mit den Microsoft 365, obwohl einige Features nur in der Microsoft 365. Sehen Sie sich nur einige der Dinge an, die Ihnen fehlten:

|Exchange Release|Features|
|---|---|
|**Exchange 2013**|Die vereinfachte Architektur reduziert die Anzahl der Serverrollen auf drei (Postfach, Clientzugriff, Edge-Transport)|
||Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die dazu beitragen, vertrauliche Informationen vor Lecks zu bewahren|
||Verbesserte Outlook Web App-Erfahrung|
|**Exchange 2016**|*Features aus Exchange 2013 und ...*|
||Weitere vereinfachte Serverrollen für nur Postfach- und Edge-Transport|
||Verbesserte DLP und Integration in SharePoint|
||Verbesserte Ausfallsicherheit von Datenbanken|
||Online-Dokumentzusammenarbeit|

|Überlegungen|Weitere Informationen|
|---|---|
|Ende der Supporttermine|Wie Exchange 2010 verfügt jede Version von Exchange über ein eigenes End-of-Support-Datum:<br/><br/>Exchange 2013 – April 2023<br/>Exchange 2016 – Oktober 2025<br/><br/>Mit dem früheren Enddatum des Supportdatums müssen Sie früher eine weitere Migration durchführen. April 2023 ist viel näher, als Sie denken!|
|Migrationspfad zu Exchange 2013 oder 2016|Der Migrationspfad von Exchange 2010 zu einer neueren Version ist identisch, unabhängig davon, ob Sie Exchange 2013 oder Exchange 2016 auswählen:<br/><br/>Installieren Exchange 2013 oder 2016 in Ihrer Exchange 2010-Organisation.<br/>Verschieben sie Dienste und andere Infrastruktur Exchange 2013 oder 2016.<br/>Verschieben von Postfächern und öffentlichen Ordnern in Exchange 2013 oder 2016 Außerbetriebnahme der verbleibenden Exchange 2010-Servern.|
|Versionskoexistenz|Bei der Migration zu Exchange 2013 oder Exchange 2016 können Sie eine version in einer vorhandenen Exchange 2010-Organisation installieren. Auf diese Weise können Sie einen oder mehrere Exchange 2013- oder Exchange 2016-Server installieren und Die Migrationen ausgeführt werden.|
|Serverhardware|Die Serverhardwareanforderungen haben sich von Exchange 2010 geändert. Stellen Sie sicher, dass Ihre Hardware kompatibel ist. Weitere Informationen zu den Hardwareanforderungen für jede Version finden Sie hier:<br/><br/>[Exchange 2016 – Systemanforderungen](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Exchange 2013 – Systemanforderungen](/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Mit der erheblichen Verbesserung der Exchange leistung und der erhöhten Rechenleistung und Speicherkapazität auf neueren Servern benötigen Sie wahrscheinlich weniger Server, um dieselbe Anzahl von Postfächern zu unterstützen.|
|Betriebssystemversion|Die mindestens unterstützten Betriebssystemversionen für jede Version sind:<br/><br/>Exchange 2016 – Windows Server 2012<br/>Exchange 2013 – Windows Server 2008 R2 SP1<br/><br/>Weitere Informationen zur Betriebssystemunterstützung finden Sie unter [Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).|
|Active Directory-Gesamtstrukturfunktionsebene|Die mindestens unterstützten Active Directory-Gesamtstrukturfunktionsebenen für jede Version sind:<br/><br/>Exchange 2016 – Windows Server 2008 R2 SP1<br/>Exchange 2013 – Windows Server 2003<br/><br/>Weitere Informationen zur Unterstützung der Gesamtstrukturfunktionsebene finden Sie unter [Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).|
|Office Clientversionen|Die mindestens unterstützten Office Clientversionen für jede Version sind:<br/><br/>Exchange 2016 – Office 2010 (mit den neuesten Updates)<br/>Exchange 2013 – Office 2007 SP3<br/><br/>Weitere Informationen zur Office finden Sie unter [Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).||| 


Verwenden Sie die folgenden Ressourcen, um Bei der Migration zu helfen:

- [Exchange Bereitstellungs-Assistent](/exchange/exchange-deployment-assistant)
- Active Directory-Schemaänderungen für Exchange [2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Systemanforderungen für Exchange [2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Voraussetzungen für Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010-Client und -Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende der Unterstützung für Office 2010-Clients und -Server und Windows 7 Poster](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses einseitige Poster veranschaulicht die verschiedenen Pfade, die Sie für die Reaktion auf Office 2010-Client- und Serverprodukte und Windows 7 zum Erreichen des Endes der Unterstützung verwenden können, mit bevorzugten Pfaden und Optionsunterstützung in Microsoft 365 Enterprise hervorgehoben.

Sie können dieses [Poster auch](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) herunterladen und im Letter-, Legal- oder Tabloidformat (11 x 17) drucken.

## <a name="what-if-i-need-help"></a>Was passiert, wenn ich Hilfe brauche?

Wenn Sie zu einer Microsoft 365, sind Sie möglicherweise berechtigt, unseren Microsoft FastTrack-Dienst zu verwenden. FastTrack bietet bewährte Methoden, Tools und Ressourcen, um Ihre Migration zu Microsoft 365 so nahtlos wie möglich zu gestalten. Das Beste ist, dass Sie von einem Supporttechniker von der Planung und dem Entwurf bis hin zur Migration Ihres letzten Postfachs durch einen Supporttechniker gehen. Weitere Informationen zu FastTrack finden Sie unter [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Wenn während der Migration zu Microsoft 365 Probleme auftreten und Sie FastTrack nicht verwenden oder sie zu einer neueren Version von Exchange Server migrieren, sind hier einige Ressourcen, die Sie verwenden können:

- [Technische Community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Support für Kunden](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Verwandte Artikel

[Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und -Clients helfen](upgrade-from-office-2010-servers-and-products.md)