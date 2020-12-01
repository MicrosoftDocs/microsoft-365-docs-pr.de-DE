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
description: Exchange 2010 hat das Ende der Unterstützung erreicht. Verwenden Sie diesen Planungs Plan, um das Upgrade auf Exchange Online oder eine neuere Version von Exchange Server lokal vorzubereiten.
ms.openlocfilehash: 23384d93c4e65fb25a66ca6f2f0bcbe46b34ee18
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519691"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 – Roadmap zum Supportende

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Exchange Server 2010 **hat am 13. Oktober 2020** das Ende der Unterstützung erreicht. Wenn Sie die Migration nicht bereits von Exchange 2010 zu Microsoft 365, Office 365 oder Exchange 2016 begonnen haben, ist es an der Zeit, mit der Planung zu beginnen.

## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende der Unterstützung* ?

Die meisten Microsoft-Produkte haben einen Support-Lebenszyklus, in dem Sie neue Funktionen, Bugfixes, Sicherheitsfixes usw. erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre nach der ersten Version des Produkts. Das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Da Exchange 2010 am 13. Oktober 2020 das Ende der Unterstützung erreicht hat, bietet Microsoft nicht mehr Folgendes:

- Technischer Support für Probleme, die auftreten können.
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.
- Zeitzonenaktualisierungen.

Die Installation von Exchange 2010 wird weiterhin nach diesem Datum ausgeführt. Aufgrund der oben aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie so bald wie möglich von Exchange 2010 migrieren.

Weitere Informationen zum Ende der Unterstützung finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und-Clients helfen](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Was sind meine Optionen?

Es ist eine gute Zeit, Ihre Optionen zu erkunden und einen Migrationsplan vorzubereiten. Sie können:

- Migrieren Sie vollständig zu Microsoft 365. Migrieren von Postfächern mithilfe von Cutover, minimaler hybridbereitstellung oder vollständiger Hybrid Migration. Entfernen Sie dann lokale Exchange-Server und Active Directory.
- Migrieren Sie Ihre Exchange 2010 Server zu Exchange 2016 auf Ihren lokalen Servern.

> [!IMPORTANT]
> Wenn sich Ihre Organisation für die Migration von Postfächern zu Microsoft 365 entscheidet, aber Dirsync oder Azure AD eine Verbindung herstellen möchten, um weiterhin Benutzerkonten von lokalen Active Directory verwalten zu können, müssen Sie mindestens einen Microsoft Exchange Server lokal aufbewahren. Wenn Sie alle Exchange-Server entfernen, können Sie in Exchange Online keine Änderungen an Exchange-Empfängern vornehmen, da die Autoritäts Quelle in Ihrer lokalen Active Directory verbleiben wird. Es müssen Änderungen vorgenommen werden. In diesem Szenario stehen Ihnen die folgenden Optionen zur Ver:
>
>- *Empfohlen:* Wenn Sie Ihre Postfächer zu Microsoft 365 migriert und Ihre Server bis zum 13. Oktober 2020 aktualisiert haben, verwenden Sie Exchange 2010, um eine Verbindung mit Microsoft 365 herzustellen und Postfächer zu migrieren. Migrieren Sie als nächstes Exchange 2010 zu Exchange 2016, und setzen Sie alle verbleibenden Exchange 2010-Server außer Betrieb.
>- Wenn Sie die Postfachmigration und das lokale Server Upgrade bis zum 13. Oktober 2020 nicht abgeschlossen haben, führen Sie zuerst ein Upgrade Ihrer lokalen Exchange 2010 Server auf Exchange 2016 durch. Stellen Sie dann mithilfe von Exchange 2016 eine Verbindung mit Microsoft 365 her, und migrieren Sie Postfächer.

> [!NOTE]
> Es ist etwas komplizierter, aber Sie können auch Postfächer zu Microsoft 365 migrieren, während Sie Ihre lokalen Exchange 2010 Server zu Exchange 2016 migrieren.

Hier sind die drei Pfade, die Sie ausführen können, um das Ende der Unterstützung für Exchange Server 2010 zu vermeiden.

![Exchange Server 2010 Aktualisierungspfade](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

In den folgenden Abschnitten werden die einzelnen Optionen näher erläutert.

## <a name="migrate-to-microsoft-365"></a>Migrieren zu Microsoft 365

Die Migration Ihrer e-Mail an Microsoft 365 ist die beste und einfachste Option, um Ihre Exchange 2010-Bereitstellung zu unterstützen. Mit einer Migration zu Microsoft 365 können Sie einen einzelnen Hop von der alten Technologie zu den aktuellen Features machen, einschließlich:

- Compliance-Funktionen wie Aufbewahrungsrichtlinien, In-Place und Beweissicherungsverfahren, in-situ-eDiscovery und vieles mehr.
- Microsoft Teams.
- Power BI.
- Fokussierter Posteingang.
- MyAnalytics.

Microsoft 365 erhält außerdem erste neue Features und Benutzeroberflächen, sodass Ihre Organisation diese sofort nutzen kann. Darüber hinaus müssen Sie sich keine Gedanken machen:

- Einkauf und Wartung von Hardware.
- Bezahlen zum Heizen und kühlen Ihrer Server.
- Halten Sie sich auf dem Laufenden über Sicherheits-, Produkt-und Zeit Zonen Korrekturen.
- Aufrechterhaltung von Speicher und Software zur Unterstützung von Compliance-Anforderungen
- Aktualisieren auf eine neue Version von Exchange. Sie befinden sich immer in der neuesten Version von Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Wie sollte ich zu Microsoft 365 migrieren?

Je nach Organisation stehen Ihnen einige Optionen zur Verfügung, um Microsoft 365 zu erhalten. Zunächst müssen Sie einige Dinge beachten, beispielsweise:
- Die Anzahl der Arbeitsplätze oder Postfächer, die Sie verschieben müssen.
- Wie lange die Migration dauern soll.
- Ob Sie eine nahtlose Integration zwischen Ihrer lokalen Installation und Microsoft 365 während der Migration benötigen.
 
In dieser Tabelle sind die Migrationsoptionen und die wichtigsten Faktoren aufgeführt, die die zu verwendende Methode bestimmen.

|Migrationsoption|Organisationsgröße|Dauer|
|---|---|---|
|Übernahmemigration|Weniger als 150 Sitze|Mindestens eine Woche|
|Minimale Hybrid Migration|Weniger als 150 Sitze|Ein paar Wochen oder weniger|
|Vollständige Hybridmigration|Mehr als 150 Sitze|Ein paar Wochen oder mehr|

In den folgenden Abschnitten erhalten Sie einen Überblick über diese Methoden. Weitere Informationen finden Sie unter [beschließen eines Migrationspfads](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27).

### <a name="cutover-migration"></a>Übernahmemigration

Bei einer Cutover Migration migrieren Sie alle Postfächer, Verteilergruppen, Kontakte usw. zu einem festgelegten Datum und einer bestimmten Uhrzeit Office 365. Wenn Sie fertig sind, können Sie Ihre lokalen Exchange-Server herunterfahren und ausschließlich Microsoft 365 verwenden.

Die Cutover-Migration eignet sich hervorragend für kleine Organisationen, die nicht über viele Postfächer verfügen, Microsoft 365 schnell erhalten möchten und nicht mit der Komplexität der anderen Methoden umgehen möchten. Aber es sollte in einer Woche oder kürzer abgeschlossen werden. Außerdem müssen Benutzer Ihre Outlook-Profile neu konfigurieren. Cutover Migration kann bis zu 2.000 Postfächer migrieren, es wird jedoch empfohlen, Sie für maximal 150 zu verwenden. Wenn Sie versuchen, mehr zu migrieren, können Sie keine Zeit mehr für die Übertragung aller Postfächer vor dem Stichtag haben, und Ihr IT-Supportmitarbeiter wird möglicherweise mit Anfragen zur Unterstützung von Benutzern für die Neukonfiguration von Outlook überhäuft.

Hier sind Dinge, die Sie über die Cutover-Migration beachten sollten:

- Microsoft 365 muss mit Outlook Anywhere über TCP-Port 443 eine Verbindung zu Ihren Exchange 2010 Servern herstellen.
- Alle lokalen Postfächer werden nach Microsoft 365 verschoben.
- Sie benötigen ein lokales Administratorkonto, das über Lesezugriff auf die Postfächer Ihrer Benutzer verfügt.
- Die Exchange 2010 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen im Dienst als verifizierte Domänen hinzugefügt werden.
- Zwischen beim Starten der Migration und dem Beginn der Abschlussphase synchronisiert Microsoft 365 regelmäßig die Microsoft 365-und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber machen zu müssen, dass e-Mails in Ihren lokalen Postfächern hinterlassen werden.
- Die Benutzer erhalten neue temporäre Kennwörter für Ihr Microsoft 365-Konto. Sie müssen diese ändern, wenn Sie sich zum ersten Mal bei ihren Postfächern anmelden.
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf jedem Ihrer Geräte ein neues Outlook-Profil einrichten und Ihre e-Mails erneut herunterladen. Die Menge an e-Mails, die von Outlook heruntergeladen werden können, kann variieren. Weitere Informationen finden Sie unter [Work Offline in Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Weitere Informationen zur Migration von Cutover finden Sie unter:

- [Was Sie über eine Cutover-e-Mail-Migration wissen müssen](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Durchführen einer Cutover Migration von e-Mails zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimale Hybrid Migration

In einer minimalen Hybrid-oder Express-Migration verschieben Sie innerhalb weniger Wochen ein paar hundert Postfächer nach Microsoft 365. Diese Methode unterstützt keine erweiterten Features für die Hybrid Migration wie freigegebene Frei/Gebucht-Kalenderinformationen.

Die minimale Hybrid Migration eignet sich hervorragend für Unternehmen, die mehr Zeit benötigen, um ihre Postfächer zu Microsoft 365 zu migrieren, aber dennoch die Migration innerhalb weniger Wochen abschließen möchten. Sie erhalten einige Vorteile der fortgeschritteneren *Voll-Hybrid Migration* ohne einen Großteil der Komplexität. Sie können steuern, wie viele und welche Postfächer zu einem bestimmten Zeitpunkt migriert werden sollen. Microsoft 365-Postfächer werden mit den Benutzernamen und Kennwörtern der lokalen Konten erstellt. Und im Gegensatz zu Cutover-Migrationen müssen Ihre Benutzer Ihre Outlook-Profile nicht neu erstellen.

Hier sind die folgenden Aspekte bei der minimalen Hybrid Migration zu beachten:

- Sie müssen eine einmalige Verzeichnissynchronisierung zwischen Ihren lokalen Active Directory Servern und Microsoft 365 durchführen.
- Benutzer können sich mit dem gleichen Benutzernamen und Kennwort wie vor Ihrem Postfach bei Ihrem Microsoft 365-Postfach anmelden.
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen kein neues Outlook-Profil auf den meisten Ihrer Geräte einrichten, obwohl einige ältere Android-Telefone möglicherweise ein neues Profil benötigen. Benutzer müssen Ihre e-Mails nicht erneut herunterladen.

Weitere Informationen finden Sie unter [use minimal Hybrid to quickly migrate Exchange mailboxes to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Vollständige hybridbereitstellung

Bei einer vollständigen Hybrid Migration haben Sie viele Hunderte, bis zu Zehntausende von Postfächern, und Sie verschieben einige oder alle nach Microsoft 365. Da diese Migrationen normalerweise längerfristig sind, ermöglichen Hybrid Migrationen Folgendes:

- Zeigen Sie lokalen Benutzern die Frei/Gebucht-Kalenderinformationen für Benutzer in Microsoft 365 an, und umgekehrt.
- Siehe eine einheitliche globale Adressliste, die Empfänger sowohl in lokal als auch in Microsoft 365 enthält.
- Zeigen Sie die vollständigen Outlook-Empfänger Eigenschaften für alle Benutzer an, unabhängig davon, ob Sie lokal oder in Microsoft 365 sind.
- Sichere e-Mail-Kommunikation zwischen lokalen Exchange-Servern und Office 365 mithilfe von TLS und Zertifikaten.
- Behandeln Sie Nachrichten, die zwischen lokalen Exchange-Servern und Microsoft 365 gesendet werden, als intern, sodass Sie folgende Möglichkeiten haben:
  - Durch Transport-und Compliance-Agents, die auf interne Nachrichten Zielen, ordnungsgemäß ausgewertet und verarbeitet werden.
  - Umgehen von Anti-Spam-Filtern.

Vollständige Hybrid Migrationen eignen sich am besten für Organisationen, die für mehrere Monate oder mehr in einer Hybrid Konfiguration bleiben möchten. Sie erhalten die weiter oben in diesem Abschnitt aufgeführten Features sowie die Verzeichnissynchronisierung, bessere integrierte Compliance-Features und die Möglichkeit, Postfächer mithilfe von Online Postfachverschiebungen von und nach Microsoft 365 zu verschieben. Microsoft 365 wird zu einer Erweiterung Ihrer lokalen Organisation.

Dinge, die bei der vollständigen Hybrid Migration zu beachten sind:

- Sie eignen sich nicht für alle Organisationen. Aufgrund der Komplexität von vollständigen Hybrid Migrationen sehen Organisationen mit weniger als ein paar hundert Postfächern normalerweise keine Vorteile, die den Aufwand und die Kosten begründen. In diesen Fällen wird empfohlen, stattdessen Cutover oder eine minimale Hybrid Migration zu verwenden.
- Sie müssen die Verzeichnissynchronisierung mithilfe von Azure Active Directory einrichten (Azure AD) zwischen Ihren lokalen Active Directory Servern und Microsoft 365 herstellen.
- Benutzer können sich bei Ihrem Microsoft 365-Postfach mit dem gleichen Benutzernamen und Kennwort anmelden, die Sie bei der Anmeldung beim lokalen Netzwerk verwenden. (Diese Funktionalität erfordert Azure AD Verbindung mit der Kennwortsynchronisierung und/oder Active Directory Verbunddiensten).
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen kein neues Outlook-Profil auf den meisten Ihrer Geräte einrichten, auch wenn einige ältere Android-Telefone möglicherweise ein neues Profil benötigen. Benutzer müssen Ihre e-Mails nicht erneut herunterladen.

> [!IMPORTANT]
> Wenn sich Ihre Organisation für die Migration von Postfächern zu Microsoft 365 entscheidet, aber Dirsync oder Azure AD eine Verbindung herstellen möchten, um weiterhin Benutzerkonten von lokalen Active Directory verwalten zu können, müssen Sie mindestens einen lokalen Exchange-Server beibehalten. Wenn alle Exchange-Server entfernt werden, können Sie in Exchange Online keine Änderungen an Exchange-Empfängern vornehmen. Dies liegt daran, dass die Autoritäts Quelle in Ihrem lokalen Active Directory bleibt und dass dort Änderungen vorgenommen werden müssen.

Wenn eine vollständige Hybrid Migration für Sie richtig klingt, lesen Sie die folgenden hilfreichen Ressourcen:

- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
- [Hybridbereitstellungen in Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Assistent für die Hybridkonfiguration](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [FAQs zum Assistenten für die Hybridkonfiguration](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Voraussetzungen für die Hybridbereitstellung](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Upgrade auf eine neuere Version von Exchange Server lokal

Wir sind der festen Überzeugung, dass Sie die beste Wert-und Benutzererfahrung erzielen, wenn Sie vollständig auf Microsoft 365 migrieren. Aber wir verstehen, dass einige Organisationen lokale Exchange-Server beibehalten müssen. Dies kann an regulatorische Anforderungen liegen, um sicherzustellen, dass Daten nicht in einem fremden Rechenzentrum gespeichert werden, da Sie eindeutige Einstellungen oder Anforderungen haben, die in der Cloud nicht erfüllt werden können, oder weil Sie Exchange zum Verwalten von Cloud-Postfächern benötigen, da Sie weiterhin Active Directory lokal verwenden. Wenn Sie Exchange lokal beibehalten, sollten Sie in jedem Fall sicherstellen, dass Ihre Exchange 2010 Umgebung auf mindestens Exchange 2013 oder Exchange 2016 aktualisiert wird.

Für eine optimale Benutzerfreundlichkeit wird empfohlen, dass Sie die verbleibende lokale Umgebung auf Exchange 2016 aktualisieren. Sie müssen Exchange Server 2013 nicht installieren, wenn Sie direkt von Exchange Server 2010 zu Exchange Server 2016 gehen möchten.

Exchange 2016 umfasst alle Features früherer Versionen von Exchange. Es entspricht am ehesten der verfügbaren Erfahrung mit Microsoft 365, obwohl einige Funktionen nur in Microsoft 365 verfügbar sind. Sehen Sie sich nur einige der Dinge an, die Ihnen fehlen:

|Exchange-Version|Features|
|---|---|
|**Exchange 2013**|Vereinfachte Architektur reduziert die Anzahl der Serverrollen auf drei (Postfach, Client Zugriff, Edge-Transport)|
||Datenverlust-Verhinderung-Richtlinien (DLP), mit denen vertrauliche Informationen vor Undichtigkeiten bleiben|
||Verbesserte Outlook Web App Erfahrung|
|**Exchange 2016**|*Features aus Exchange 2013 und...*|
||Weitere vereinfachte Serverrollen nur für Postfach-und Edge-Transport|
||Verbesserte DLP zusammen mit der Integration in SharePoint|
||Verbesserte Ausfallsicherheit der Datenbank|
||Online Dokument Zusammenarbeit|

|Überlegungen|Weitere Informationen|
|---|---|
|Ende der Support Daten|Wie Exchange 2010 hat jede Version von Exchange ein eigenes Datum für das Ende des Supports:<br/><br/>Exchange 2013-April 2023<br/>Exchange 2016-Oktober 2025<br/><br/>Je früher das End-of-Support-Datum ist, desto schneller müssen Sie eine weitere Migration durchführen. April 2023 ist viel näher als Sie denken!|
|Migrationspfad zu Exchange 2013 oder 2016|Der Migrationspfad von Exchange 2010 zu einer neueren Version ist unabhängig davon, ob Sie Exchange 2013 oder Exchange 2016 wählen:<br/><br/>Installieren Sie Exchange 2013 oder 2016 in Ihrer vorhandenen Exchange 2010 Organisation.<br/>Verlagerung von Diensten und anderen Infrastrukturen auf Exchange 2013 oder 2016.<br/>Verschieben von Postfächern und öffentlichen Ordnern auf Exchange 2013 oder 2016 still gebliebenen Exchange 2010 Servern.|
|Versions Koexistenz|Bei der Migration zu Exchange 2013 oder Exchange 2016 können Sie beide Versionen in einer vorhandenen Exchange 2010 Organisation installieren. Auf diese Weise können Sie einen oder mehrere Exchange 2013-oder Exchange 2016-Server installieren und Ihre Migration durchführen.|
|Serverhardware|Die Server Hardwareanforderungen wurden von Exchange 2010 geändert. Stellen Sie sicher, dass Ihre Hardware kompatibel ist. Hier finden Sie weitere Informationen zu den Hardwareanforderungen für jede Version:<br/><br/>[Exchange 2016 – Systemanforderungen](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Exchange 2013 – Systemanforderungen](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Aufgrund der signifikanten Verbesserungen bei der Exchange-Leistung und der erhöhten Rechenleistung und Speicherkapazität in neueren Servern benötigen Sie wahrscheinlich weniger Server, um die gleiche Anzahl von Postfächern zu unterstützen.|
|Betriebssystemversion|Für jede Version werden mindestens die folgenden Betriebssystemversionen unterstützt:<br/><br/>Exchange 2016-Windows Server 2012<br/>Exchange 2013-Windows Server 2008 R2 SP1<br/><br/>Weitere Informationen zur Betriebssystemunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Active Directory Gesamtstrukturfunktionsebene|Für jede Version werden mindestens Active Directory Gesamtstrukturfunktionsebenen unterstützt:<br/><br/>Exchange 2016-Windows Server 2008 R2 SP1<br/>Exchange 2013-Windows Server 2003<br/><br/>Weitere Informationen zur Unterstützung der Gesamtstrukturfunktionsebene finden Sie unter [Exchange supportable Matrix](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Office-Clientversionen|Für jede Version werden mindestens die folgenden Office-Clientversionen unterstützt:<br/><br/>Exchange 2016-Office 2010 (mit den neuesten Updates)<br/>Exchange 2013-Office 2007 SP3<br/><br/>Weitere Informationen zur Office-Clientunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).||| 


Verwenden Sie die folgenden Ressourcen, um die Migration zu erleichtern:

- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
- Active Directory Schemaänderungen für Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- System Anforderungen für Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Voraussetzungen für Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010 Client und Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende der Unterstützung für Office 2010-Clients und-Server und Windows 7 Poster](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses ein-Seiten-Poster zeigt die verschiedenen Pfade, die Sie ergreifen können, um auf Office 2010 Client-und Serverprodukte zu reagieren, und Windows 7 erreichen des Endes der Unterstützung, wobei bevorzugte Pfade und Options Unterstützung in Microsoft 365 Enterprise hervorgehoben werden.

Sie können dieses Poster auch [herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) und im Format "Letter", "Legal" oder "Tabloid" (11 x 17) ausdrucken.

## <a name="what-if-i-need-help"></a>Was kann ich tun, wenn ich Hilfe brauche?

Wenn Sie eine Migration zu Microsoft 365 durchführen, können Sie möglicherweise den Microsoft-kurzleistungs Dienst verwenden. In diesem Artikel werden bewährte Methoden, Tools und Ressourcen bereitgestellt, um die Migration zu Microsoft 365 so nahtlos wie möglich zu gestalten. Das beste daran ist, dass Sie einen Supporttechniker von der Planung und dem Entwurf bis hin zur Migration Ihres letzten Postfachs begleiten. Weitere Informationen zum kurzbegriff finden Sie unter [Microsoft](https://fasttrack.microsoft.com/)Kurzinfo.

Wenn bei der Migration zu Microsoft 365 Probleme auftreten und Sie nicht mit dem Kurzzeit-Feature arbeiten oder zu einer neueren Version von Exchange Server migrieren, finden Sie hier einige Ressourcen, die Sie verwenden können:

- [Technische Community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Support für Kunden](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Verwandte Artikel

[Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und -Clients helfen](upgrade-from-office-2010-servers-and-products.md)
