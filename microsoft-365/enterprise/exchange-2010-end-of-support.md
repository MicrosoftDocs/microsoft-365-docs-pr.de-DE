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
description: Exchange 2010 hat das Ende des Supports erreicht. Verwenden Sie diese Planungs-Roadmap, um das Upgrade auf Exchange Online oder eine neuere Version von Exchange Server lokal vorzubereiten.
ms.openlocfilehash: bbc7fb83537621a47a866bf0ca129a38e21f055e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289127"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 – Roadmap zum Supportende

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Exchange Server 2010 wurde der Support am **13. Oktober 2020 eingestellt.** Wenn Sie die Migration von Exchange 2010 zu Microsoft 365, Office 365 oder Exchange 2016 noch nicht begonnen haben, müssen Sie mit der Planung beginnen.

## <a name="what-does-end-of-support-mean"></a>Was bedeutet das *Ende des Supports?*

Die meisten Microsoft-Produkte verfügen über einen Supportlebenszyklus, in dem sie neue Features, Fehlerbehebungen, Sicherheitspatches usw. erhalten. Dieser Lebenszyklus dauert in der Regel 10 Jahre ab der ersten Veröffentlichung des Produkts. Das Ende dieses Lebenszyklus wird als Ende des Supports für das Produkt bezeichnet. Da Exchange 2010 am 13. Oktober 2020 das Ende des Supports erreicht hat, bietet Microsoft nicht mehr Folgendes:

- Technischer Support für Probleme, die auftreten können.
- Fehlerbehebungen für Probleme, die sich auf die Stabilität und Nutzbarkeit des Servers auswirken können.
- Sicherheitspatches für Sicherheitsrisiken, die den Server anfällig für Sicherheitsverletzungen machen können.
- Zeitzonenupdates.

Die Installation von Exchange 2010 wird nach diesem Datum weiterhin ausgeführt. Aufgrund der oben aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie so bald wie möglich von Exchange 2010 migrieren.

Weitere Informationen zum Ende des Supports finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und -Clients helfen.](upgrade-from-office-2010-servers-and-products.md)

## <a name="what-are-my-options"></a>Welche Optionen habe ich?

Es ist ein guter Zeitpunkt, ihre Optionen zu erkunden und einen Migrationsplan vorzubereiten. Sie haben folgende Möglichkeiten:

- Migrieren Sie vollständig zu Microsoft 365. Migrieren Von Postfächern mit Übernahme, minimaler Hybridmigration oder vollständiger Hybridmigration. Entfernen Sie dann lokale Exchange Server und Active Directory.
- Migrieren Sie Ihre Exchange 2010-Server zu Exchange 2016 auf Ihren lokalen Servern.

> [!IMPORTANT]
> Wenn Ihre Organisation Postfächer zu Microsoft 365 migrieren möchte, aber plant, DirSync oder Azure AD Verbinden beizubehalten, um die Verwaltung von Benutzerkonten aus dem lokalen Active Directory fortzusetzen, müssen Sie mindestens einen Microsoft Exchange-Server lokal beibehalten. Wenn Sie alle Exchange Server entfernen, können Sie keine Änderungen an Exchange Empfängern in Exchange Online vornehmen, da die Autoritätsquelle in Ihrem lokalen Active Directory verbleibt. Dort müssen Änderungen vorgenommen werden. In diesem Szenario stehen Ihnen die folgenden Optionen zur Verfügung:
>
>- *Empfohlen:* Wenn Sie Ihre Postfächer bis zum 13. Oktober 2020 zu Microsoft 365 migriert und ihre Server aktualisiert haben, verwenden Sie Exchange 2010, um eine Verbindung mit Microsoft 365 herzustellen und Postfächer zu migrieren. Migrieren Sie als Nächstes Exchange 2010 zu Exchange 2016, und deaktivieren Sie alle verbleibenden Exchange 2010-Server.
>- Wenn Sie die Postfachmigration und das lokale Serverupgrade bis zum 13. Oktober 2020 nicht abgeschlossen haben, aktualisieren Sie Ihre lokalen Server Exchange 2010 zuerst auf Exchange 2016. Verwenden Sie dann Exchange 2016, um eine Verbindung mit Microsoft 365 herzustellen und Postfächer zu migrieren.

> [!NOTE]
> Es ist etwas komplizierter, Aber Sie können Postfächer auch zu Microsoft 365 migrieren, während Sie Ihre lokalen Exchange 2010-Server zu Exchange 2016 migrieren.

Hier sind die drei Pfade, die Sie verwenden können, um das Ende der Unterstützung für Exchange Server 2010 zu vermeiden.

![Exchange Server 2010-Upgradepfade](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

In den folgenden Abschnitten werden die einzelnen Optionen ausführlicher erläutert.

## <a name="migrate-to-microsoft-365"></a>Migrieren zu Microsoft 365

Die Migration Ihrer E-Mails zu Microsoft 365 ist die beste und einfachste Option, mit der Sie ihre Exchange 2010-Bereitstellung beenden können. Mit einer Migration zu Microsoft 365 können Sie einen einzigen Hop von der alten Technologie zu den aktuellen Features machen, einschließlich:

- Compliancefunktionen wie Aufbewahrungsrichtlinien, In-Place und Beweissicherungsverfahren, in-situ eDiscovery und vieles mehr.
- Microsoft Teams.
- Power BI.
- Posteingang mit Relevanz.
- Myanalytics.

Microsoft 365 erhält außerdem zuerst neue Features und Erfahrungen, damit Ihre Organisation sofort mit der Verwendung beginnen kann. Außerdem müssen Sie sich keine Gedanken über Folgendes machen:

- Erwerb und Wartung von Hardware.
- Bezahlen Sie für Diehen und Ab coolen Ihre Server.
- Auf dem neuesten Stand zu Sicherheits-, Produkt- und Zeitzonenfixes.
- Verwalten von Speicher und Software zur Unterstützung von Complianceanforderungen.
- Upgrade auf eine neue Version von Exchange. Sie sind immer auf der neuesten Version von Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Wie sollte ich zu Microsoft 365 migrieren?

Je nach Organisation haben Sie einige Möglichkeiten, um zu Microsoft 365 zu gelangen. Zunächst müssen Sie einige Dinge berücksichtigen, z. B.:

- Die Anzahl der Arbeitsplätze oder Postfächer, die Sie verschieben müssen.
- Wie lange die Migration dauern soll.
- Ob Sie eine nahtlose Integration zwischen Ihrer lokalen Installation und Microsoft 365 während der Migration benötigen.

In dieser Tabelle sind Die Migrationsoptionen und die wichtigsten Faktoren aufgeführt, die bestimmen, welche Methode verwendet werden soll.

<br>

****

|Migrationsoption|Organisationsgröße|Dauer|
|---|---|---|
|Übernahmemigration|Weniger als 150 Arbeitsplätze|Eine Woche oder weniger|
|Minimale Hybridmigration|Weniger als 150 Arbeitsplätze|Ein paar Wochen oder weniger|
|Vollständige Hybridmigration|Mehr als 150 Arbeitsplätze|Ein paar Wochen oder mehr|
|

In den folgenden Abschnitten erhalten Sie einen Überblick über diese Methoden. Weitere Informationen finden Sie unter ["Entscheiden über einen Migrationspfad".](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)

### <a name="cutover-migration"></a>Übernahmemigration

Bei einer Übernahmemigration migrieren Sie alle Postfächer, Verteilergruppen, Kontakte usw. zu einem festgelegten Datum und zu einer festgelegten Uhrzeit, um Office 365. Wenn Sie fertig sind, fahren Sie Ihre lokalen Exchange Server herunter und verwenden Microsoft 365 exklusiv.

Die Übernahmemigration eignet sich hervorragend für kleine Organisationen, die nicht über viele Postfächer verfügen, schnell zu Microsoft 365 gelangen möchten und nicht mit der Komplexität der anderen Methoden umgehen möchten. Aber es sollte in einer Woche oder weniger abgeschlossen sein. Außerdem müssen Benutzer ihre Outlook Profile neu konfigurieren. Die Übernahmemigration kann bis zu 2.000 Postfächer migrieren, es wird jedoch empfohlen, sie für maximal 150 Postfächer zu verwenden. Wenn Sie versuchen, mehr zu migrieren, könnten Ihnen die Zeit zum Übertragen aller Postfächer vor Dem Stichtag knapp werden, und Ihre IT-Supportmitarbeiter sind möglicherweise überlastet mit Anfragen, die Benutzern helfen, Outlook neu zu konfigurieren.

Im Folgenden sind Punkte aufgeführt, die Sie bei der Übernahmemigration berücksichtigen sollten:

- Microsoft 365 müssen mithilfe von Outlook Anywhere über TCP-Port 443 eine Verbindung mit Ihren Exchange 2010-Servern herstellen.
- Alle lokalen Postfächer werden in Microsoft 365 verschoben.
- Sie benötigen ein lokales Administratorkonto, das Lesezugriff auf die Postfächer Ihrer Benutzer hat.
- Die Exchange 2010 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen dem Dienst als überprüfte Domänen hinzugefügt werden.
- Zwischen dem Beginn der Migration und dem Beginn der Abschlussphase synchronisiert Microsoft 365 regelmäßig die Microsoft 365 und lokale Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber machen zu müssen, dass E-Mails in Ihren lokalen Postfächern zurückgelassen werden.
- Benutzer erhalten neue temporäre Kennwörter für ihr Microsoft 365 Konto. Sie müssen diese ändern, wenn sie sich zum ersten Mal bei ihren Postfächern anmelden.
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf jedem ihrer Geräte ein neues Outlook Profil einrichten und ihre E-Mails erneut herunterladen. Die Menge der E-Mails, die Outlook herunterladen, kann variieren. Weitere Informationen finden Sie unter [Offlinearbeit in Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Weitere Informationen zur Übernahmemigration finden Sie unter:

- [Was Sie über eine Übernahme-E-Mail-Migration wissen müssen](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Durchführen einer Übernahmemigration von E-Mails zu Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimale Hybridmigration

Bei einer minimalen Hybrid- oder Expressmigration verschieben Sie innerhalb weniger Wochen ein paar Hundert Postfächer in Microsoft 365. Diese Methode unterstützt keine erweiterten Hybridmigrationsfunktionen wie freigegebene Frei/Gebucht-Kalenderinformationen.

Minimale Hybridmigration eignet sich hervorragend für Organisationen, die mehr Zeit benötigen, um ihre Postfächer zu Microsoft 365 zu migrieren, aber dennoch planen, die Migration innerhalb weniger Wochen abzuschließen. Sie erhalten einige der Vorteile der komplexeren *Vollständighybridmigration* ohne großen Teil der Komplexität. Sie können steuern, wie viele und welche Postfächer zu einem bestimmten Zeitpunkt migriert werden sollen. Microsoft 365 Postfächer werden mit den Benutzernamen und Kennwörtern der lokalen Konten erstellt. Und im Gegensatz zu Übernahmemigrationen müssen Ihre Benutzer ihre Outlook Profile nicht neu erstellen.

Folgende Punkte sollten Sie bei der minimalen Hybridmigration berücksichtigen:

- Sie müssen eine einmalige Verzeichnissynchronisierung zwischen Ihren lokalen Active Directory-Servern und Microsoft 365 durchführen.
- Benutzer können sich bei ihrem Microsoft 365 Postfach mit demselben Benutzernamen und Kennwort wie vor ihrem Postfach anmelden.
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf den meisten Geräten kein neues Outlook Profil einrichten, obwohl einige ältere Android-Smartphones möglicherweise ein neues Profil benötigen. Benutzer müssen ihre E-Mails nicht erneut herunterladen.

Weitere Informationen finden Sie unter [Verwenden von MinimalHybrid, um Exchange Postfächer schnell zu Office 365 zu migrieren.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)

### <a name="full-hybrid"></a>Vollständige Hybridbereitstellung

Bei einer vollständigen Hybridmigration verfügen Sie über viele Hunderte, bis zu Zehntausend Postfächer, und Sie verschieben einige oder alle in Microsoft 365. Da diese Migrationen in der Regel langfristig sind, ermöglichen Hybridmigrationen Folgendes:

- Zeigen Sie lokalen Benutzern die Frei/Gebucht-Kalenderinformationen für Benutzer in Microsoft 365 an und umgekehrt.
- Sehen Sie sich eine einheitliche globale Adressliste an, die Empfänger in lokalen und Microsoft 365 enthält.
- Zeigen Sie vollständige Outlook Empfängereigenschaften für alle Benutzer an, unabhängig davon, ob sie lokal oder in Microsoft 365 sind.
- Sichere E-Mail-Kommunikation zwischen lokalen Exchange Servern und Office 365 mitHILFE von TLS und Zertifikaten.
- Behandeln Sie Nachrichten, die zwischen lokalen Exchange Servern und Microsoft 365 gesendet werden, als intern, sodass sie:
  - Ordnungsgemäß ausgewertet und von Transport- und Compliance-Agents für interne Nachrichten verarbeitet werden.
  - Umgehen von Antispamfiltern.

Vollständige Hybridmigrationen eignen sich am besten für Organisationen, die davon ausgehen, dass sie über viele Monate oder mehr in einer Hybridkonfiguration verbleiben. Sie erhalten die weiter oben in diesem Abschnitt aufgeführten Features sowie die Verzeichnissynchronisierung, bessere integrierte Compliancefeatures und die Möglichkeit, Postfächer mithilfe von Onlinepostfachverschiebungen zu und von Microsoft 365 zu verschieben. Microsoft 365 wird zu einer Erweiterung Ihrer lokalen Organisation.

Aspekte, die Sie bei der Vollständighybridmigration berücksichtigen sollten:

- Sie sind nicht für alle Organisationen geeignet. Aufgrund der Komplexität von vollständigen Hybridmigrationen sehen Organisationen mit weniger als ein paar hundert Postfächern in der Regel keine Vorteile, die den Aufwand und die Kosten rechtfertigen. In solchen Fällen wird empfohlen, stattdessen eine Übernahme oder minimale Hybridmigration in Betracht zu ziehen.
- Sie müssen die Verzeichnissynchronisierung mit Azure Active Directory (Azure AD)-Verbinden zwischen Ihren lokalen Active Directory-Servern und Microsoft 365 einrichten.
- Benutzer können sich bei ihrem Microsoft 365 Postfach mit demselben Benutzernamen und Kennwort anmelden, das sie bei der Anmeldung beim lokalen Netzwerk verwenden. (Diese Funktion erfordert Azure AD-Verbinden mit Kennwortsynchronisierung und/oder Active Directory-Verbunddiensten).
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf den meisten Geräten kein neues Outlook Profil einrichten, obwohl einige ältere Android-Smartphones möglicherweise ein neues Profil benötigen. Benutzer müssen ihre E-Mails nicht erneut herunterladen.

> [!IMPORTANT]
> Wenn Ihre Organisation Postfächer zu Microsoft 365 migriert, dirSync oder Azure AD jedoch Verbinden beibehalten möchte, um weiterhin Benutzerkonten aus dem lokalen Active Directory verwalten zu können, müssen Sie mindestens einen Exchange lokalen Server beibehalten. Wenn alle Exchange Server entfernt werden, können Sie keine Änderungen an Exchange Empfängern in Exchange Online vornehmen. Dies liegt daran, dass die Autoritätsquelle in Ihrem lokalen Active Directory verbleibt und dort Änderungen vorgenommen werden müssen.

Wenn eine vollständige Hybridmigration für Sie geeignet ist, sehen Sie sich die folgenden hilfreichen Ressourcen an:

- [Exchange Bereitstellungs-Assistent](/exchange/exchange-deployment-assistant)
- [Hybridbereitstellungen in Exchange Server](/exchange/exchange-hybrid)
- [Assistent für die Hybridkonfiguration](/exchange/hybrid-configuration-wizard)
- [FAQs zum Assistenten für die Hybridkonfiguration](/exchange/hybrid-configuration-wizard-faqs)
- [Voraussetzungen für die Hybridbereitstellung](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Upgrade auf eine neuere Version von Exchange Server lokal

Wir sind fest davon überzeugt, dass Sie den besten Nutzen und die beste Benutzererfahrung erzielen, indem Sie vollständig zu Microsoft 365 migrieren. Wir wissen jedoch, dass einige Organisationen einige Exchange Server lokal beibehalten müssen. Dies liegt möglicherweise an gesetzlichen Anforderungen, um sicherzustellen, dass Daten nicht in einem fremden Rechenzentrum gespeichert werden, weil Sie eindeutige Einstellungen oder Anforderungen haben, die in der Cloud nicht erfüllt werden können, oder weil Sie Exchange zum Verwalten von Cloudpostfächern benötigen, da Sie Active Directory weiterhin lokal verwenden. Wenn Sie Exchange lokal beibehalten, sollten Sie auf jeden Fall sicherstellen, dass Ihre Exchange 2010-Umgebung auf mindestens Exchange 2013 oder Exchange 2016 aktualisiert wird.

Für eine optimale Benutzererfahrung empfehlen wir, die verbleibende lokale Umgebung auf Exchange 2016 zu aktualisieren. Sie müssen Exchange Server 2013 nicht installieren, wenn Sie direkt von Exchange Server 2010 auf Exchange Server 2016 wechseln möchten.

Exchange 2016 enthält alle Features der vorherigen Versionen von Exchange. Es entspricht am besten der mit Microsoft 365 verfügbaren Benutzeroberfläche, obwohl einige Features nur in Microsoft 365 verfügbar sind. Sehen Sie sich nur einige der Dinge an, die Sie noch nicht gesehen haben:

<br>

****

|Exchange-Version|Features|
|---|---|
|**Exchange 2013**|Vereinfachte Architektur reduziert die Anzahl der Serverrollen auf drei (Postfach, Clientzugriff, Edge-Transport)|
||Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), die dazu beitragen, vertrauliche Informationen vor Datenlecks zu schützen|
||Verbesserte Outlook Web App|
|**Exchange 2016**|*Features aus Exchange 2013 und ...*|
||Weitere vereinfachte Serverrollen für Postfach- und Edge-Transport|
||Verbesserte DLP zusammen mit der Integration in SharePoint|
||Verbesserte Datenbankresilienz|
||Zusammenarbeit an Onlinedokumenten|
|

<br>

****

|Überlegungen|Weitere Informationen|
|---|---|
|Ende des Supportdatums|Wie Exchange 2010 hat jede Version von Exchange ein eigenes Supportendedatum: <p> Exchange 2013 – April 2023 <p> Exchange 2016 – Oktober 2025 <p> Je früher das Ende des Supports, desto früher müssen Sie eine weitere Migration durchführen. April 2023 ist viel näher als Sie denken!|
|Migrationspfad zu Exchange 2013 oder 2016|Der Migrationspfad von Exchange 2010 zu einer neueren Version ist derselbe, unabhängig davon, ob Sie Exchange 2013 oder Exchange 2016 auswählen: <p> Installieren Sie Exchange 2013 oder 2016 in Ihrer vorhandenen Exchange 2010-Organisation. <p> Verschieben sie Dienste und andere Infrastruktur auf Exchange 2013 oder 2016. <p> Verschieben von Postfächern und öffentlichen Ordnern in Exchange 2013 oder 2016 Außerbetriebsetzung verbleibender Exchange 2010-Server.|
|Versions koexistenz|Bei der Migration zu Exchange 2013 oder Exchange 2016 können Sie beide Versionen in einer vorhandenen Exchange 2010-Organisation installieren. Auf diese Weise können Sie einen oder mehrere server Exchange 2013 oder Exchange 2016 installieren und die Migration durchführen.|
|Serverhardware|Die Serverhardwareanforderungen haben sich seit Exchange 2010 geändert. Stellen Sie sicher, dass Ihre Hardware kompatibel ist. Weitere Informationen zu den Hardwareanforderungen für jede Version finden Sie hier: <p> [Exchange 2016 – Systemanforderungen](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true) <p> [Exchange 2013 – Systemanforderungen](/Exchange/exchange-2013-system-requirements-exchange-2013-help) <p> Mit den erheblichen Verbesserungen bei Exchange Leistung und der erhöhten Rechenleistung und Speicherkapazität auf neueren Servern benötigen Sie wahrscheinlich weniger Server, um die gleiche Anzahl von Postfächern zu unterstützen.|
|Betriebssystemversion|Die mindestens unterstützten Betriebssystemversionen für jede Version sind: <p> Exchange 2016 – Windows Server 2012 <p> Exchange 2013 – Windows Server 2008 R2 SP1 <p> Weitere Informationen zur Betriebssystemunterstützung finden Sie unter [Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).|
|Funktionsebene der Active Directory-Gesamtstruktur|Die mindestens unterstützten Funktionsebenen der Active Directory-Gesamtstruktur für jede Version sind: <p> Exchange 2016 – Windows Server 2008 R2 SP1 <p> Exchange 2013 – Windows Server 2003 <p> Weitere Informationen zur Unterstützung der Gesamtstrukturfunktionsebene finden Sie unter [Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).|
|Office Clientversionen|Die mindestens unterstützten Office Clientversionen für jede Version sind: <p> Exchange 2016 – Office 2010 (mit den neuesten Updates) <p> Exchange 2013 – Office 2007 SP3 <p> Weitere Informationen zur Office Clientunterstützung finden Sie unter [Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix).|
|

Verwenden Sie die folgenden Ressourcen, um Bei der Migration zu helfen:

- [Exchange Bereitstellungs-Assistent](/exchange/exchange-deployment-assistant)
- Active Directory-Schemaänderungen für Exchange [2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Systemanforderungen für Exchange [2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Voraussetzungen für Exchange [2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016&preserve-view=true), [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010-Client und -Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Ende des Supports für Office 2010-Clients und -Server und Poster Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses einseitige Poster veranschaulicht die verschiedenen Pfade, die Sie zum Reagieren auf Office 2010-Client- und Serverprodukte und Windows 7 zum Erreichen des Endes des Supports verwenden können, wobei bevorzugte Pfade und Optionsunterstützung in Microsoft 365 Enterprise hervorgehoben sind.

Sie können dieses Poster auch [herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) und im Format "Brief", "Legal" oder "Tabloid" (11 x 17) drucken.

## <a name="what-if-i-need-help"></a>Was geschieht, wenn ich Hilfe benötiere?

Wenn Sie zu Microsoft 365 migrieren, sind Sie möglicherweise berechtigt, unseren Microsoft FastTrack-Dienst zu verwenden. FastTrack bietet bewährte Methoden, Tools und Ressourcen, um die Migration zu Microsoft 365 so nahtlos wie möglich zu gestalten. Das Beste daran ist, dass Sie von der Planung und dem Entwurf bis zur Migration Ihres letzten Postfachs durch einen Supporttechniker geführt werden. Weitere Informationen zu FastTrack finden Sie unter [Microsoft FastTrack](https://fasttrack.microsoft.com/).

Wenn während der Migration zu Microsoft 365 Probleme auftreten und Sie fastTrack nicht verwenden oder zu einer neueren Version von Exchange Server migrieren, finden Sie hier einige Ressourcen, die Sie verwenden können:

- [Technische Community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Support für Kunden](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>Verwandte Artikel

[Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und -Clients helfen](upgrade-from-office-2010-servers-and-products.md)
