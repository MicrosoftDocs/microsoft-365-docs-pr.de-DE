---
title: Exchange 2010 – Roadmap zum Supportende
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 09/16/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 nähert sich dem Ende der Unterstützung. Verwenden Sie diese Planungs Roadmap als Leitfaden für die Vorbereitung des Upgrades auf Exchange Online oder eine neuere Version von Exchange Server lokal.
ms.openlocfilehash: 128abd1e98c3e9d1ec4dd8a58683ee0ab019af18
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950820"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 – Roadmap zum Supportende

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Am **13. Oktober 2020**werden Exchange Server 2010 das Ende der Unterstützung erreichen. Wenn Sie die Migration nicht bereits von Exchange 2010 zu Microsoft 365, Office 365 oder Exchange 2016 begonnen haben, ist es an der Zeit, mit der Planung zu beginnen.

## <a name="what-does-end-of-support-mean"></a>Was bedeutet das Ende der Unterstützung?

Exchange Server, wie fast alle Microsoft-Produkte, verfügt über einen Support-Lebenszyklus, in dem wir neue Features, Fehlerbehebungen, Sicherheitsfixes usw. bereitstellen. Dieser Lebenszyklus dauert in der Regel 10 Jahre ab dem Datum der ersten Produktversion, und das Ende dieses Lebenszyklus wird als Ende der Unterstützung des Produkts bezeichnet. Wenn Exchange 2010 am 13. Oktober 2020 das Ende der Unterstützung erreicht, stellt Microsoft nicht mehr Folgendes bereit:

- Technischer Support für Probleme, die auftreten können.
- Fehlerbehebungen für entdeckte Probleme, die sich auf die Stabilität und Benutzerfreundlichkeit des Servers auswirken können.
- Sicherheitsfixes für Sicherheitsanfälligkeiten, die erkannt werden und die den Server möglicherweise anfällig für Sicherheitsverletzungen machen.
- Zeitzonenaktualisierungen.

Die Installation von Exchange 2010 wird weiterhin nach diesem Datum ausgeführt. Aufgrund der oben aufgeführten Änderungen wird jedoch dringend empfohlen, dass Sie so bald wie möglich von Exchange 2010 migrieren.

Weitere Informationen zu Office 2010 Servern, die sich am Ende des Supports befinden, finden Sie unter [Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und-Clients helfen](upgrade-from-office-2010-servers-and-products.md).

## <a name="what-are-my-options"></a>Was sind meine Optionen?

Wenn Exchange 2010 das Ende der Unterstützung erreicht hat, ist dies eine gute Zeit, um Ihre Optionen zu erkunden und einen Migrationsplan vorzubereiten. Sie können:

- Migrieren Sie vollständig zu Microsoft 365. Migrieren von Postfächern mithilfe von Cutover, minimaler Hybrid-oder vollständiger Hybrid Migration und Entfernen von lokalen Exchange-Servern und Active Directory.
- Migrieren Sie Ihre Exchange 2010 Server zu Exchange 2016 auf Ihren lokalen Servern.

> [!IMPORTANT]
> Wenn sich Ihre Organisation für die Migration von Postfächern zu Microsoft 365 entscheidet, aber Dirsync oder Azure AD eine Verbindung herstellen möchten, um die Verwaltung von Benutzerkonten aus lokalen Active Directory fortzusetzen, müssen Sie mindestens einen lokalen Exchange-Server beibehalten. Wenn der letzte Exchange-Server entfernt wird, können Sie in Exchange Online keine Änderungen an Exchange-Empfängern vornehmen. Dies liegt daran, dass die Autoritäts Quelle in Ihrem lokalen Active Directory bleibt und dass dort Änderungen vorgenommen werden müssen. In diesem Szenario stehen Ihnen die folgenden Optionen zur Ver:

- (**Empfohlen**) Wenn Sie Ihre Postfächer zu Microsoft 365 migrieren und Ihre Server bis zum 13. Oktober 2020 aktualisieren können, verwenden Sie Exchange 2010, um eine Verbindung mit Microsoft 365 herzustellen und Postfächer zu migrieren. Migrieren Sie als nächstes Exchange 2010 zu Exchange 2016, und setzen Sie alle verbleibenden Exchange 2010-Server außer Betrieb.
- Wenn Sie die Postfachmigration und das lokale Server Upgrade bis zum 13. Oktober 2020 nicht abschließen können, führen Sie zuerst ein Upgrade Ihrer lokalen Exchange 2010 Server auf Exchange 2016 durch, und verwenden Sie dann Exchange 2016, um eine Verbindung mit Microsoft 365 herzustellen und Postfächer zu migrieren.

> [!NOTE]
> Während Sie ein wenig komplizierter sind, können Sie auch Postfächer zu Microsoft 365 migrieren, während Sie Ihre lokalen Exchange 2010 Server zu Exchange 2016 migrieren.

Hier sind die drei Pfade, die Sie ausführen können, um das Ende der Unterstützung für Exchange Server 2010 zu vermeiden.

![Exchange Server 2010 Aktualisierungspfade](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

In den folgenden Abschnitten werden die einzelnen Optionen näher erläutert.

## <a name="migrate-to-microsoft-365"></a>Migrieren zu Microsoft 365

Die Migration Ihrer e-Mail-Adresse zu Microsoft 365 ist die beste und einfachste Option, die Sie beim Ruhestand Ihrer Exchange 2010-Bereitstellung unterstützt. Mit einer Migration zu Microsoft 365 können Sie einen einzelnen Hop von der alten Technologie zu modernen Funktionen machen, wie beispielsweise:

- Compliance-Funktionen wie Aufbewahrungsrichtlinien, in-situ-und Beweissicherungsverfahren, in-situ-eDiscovery und vieles mehr.
- Microsoft Teams
- Power BI
- Posteingang mit Relevanz
- MyAnalytics

Microsoft 365 erhält auch neue Funktionen und Erfahrungen, die Sie und Ihre Benutzer in der Regel sofort verwenden können. Zusätzlich zu den neuen Features müssen Sie sich keine Gedanken machen:

- Einkauf und Wartung von Hardware.
- Bezahlen für das Heizen und kühlen Ihrer Server.
- Halten Sie sich auf dem Laufenden über Sicherheits-, Produkt-und Zeit Zonen Korrekturen
- Wartung von Speicher und Software zur Unterstützung von Compliance-Anforderungen
- Upgrade auf eine neue Version von Exchange – Sie haben immer die neueste Version von Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>Wie sollte ich zu Microsoft 365 migrieren?

Je nach Ihrer Organisation stehen Ihnen einige Optionen zur Verfügung, die Sie bei der Bereitstellung von Microsoft 365 unterstützen. Bei der Auswahl einer Migrationsoption müssen Sie einige Dinge berücksichtigen, beispielsweise die Anzahl der zu verschiebenden Sitze oder Postfächer, die Dauer der Migration und ob Sie eine nahtlose Integration zwischen Ihrer lokalen Installation und Microsoft 365 während der Migration benötigen. In dieser Tabelle sind die Migrationsoptionen und die wichtigsten Faktoren aufgeführt, die die zu verwendende Methode bestimmen.

|Migrationsoption|Organisationsgröße|Dauer|
|---|---|---|
|Übernahmemigration|Weniger als 150 Sitze|Mindestens eine Woche|
|Minimale Hybrid Migration|Weniger als 150 Sitze|Ein paar Wochen oder weniger|
|Vollständige Hybridmigration|Mehr als 150 Sitze|Ein paar Wochen oder mehr|

In den folgenden Abschnitten erhalten Sie einen Überblick über diese Methoden. Auschecken entscheiden Sie sich für [einen Migrationspfad](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) , um die Details der einzelnen Methoden zu erfahren.

### <a name="cutover-migration"></a>Übernahmemigration

Bei einer Cutover Migration werden alle Postfächer, Verteilergruppen, Kontakte usw. zu einem vorab ausgewählten Datum und einer bestimmten Uhrzeit in Office 365 migriert. Wenn Sie fertig sind, schließen Sie Ihre lokalen Exchange-Server ab und verwenden ausschließlich Microsoft 365.

Die Cutover-Migrationsmethode eignet sich hervorragend für kleine Organisationen, die nicht über sehr viele Postfächer verfügen, Microsoft 365 schnell erhalten möchten und nicht mit einigen der Komplexitäten der anderen Methoden umgehen möchten. Es ist jedoch auch etwas limitiert, da es in einer Woche oder weniger ausgeführt werden sollte und weil Benutzer Ihre Outlook-Profile neu konfigurieren müssen. Während die Cutover-Migration bis zu 2.000 Postfächer verarbeiten kann, wird dringend empfohlen, dass Sie mit dieser Methode maximal 150 Postfächer migrieren. Wenn Sie versuchen, mehr als 150 Postfächer zu migrieren, können Sie keine Zeit mehr für die Übertragung aller Postfächer vor dem Stichtag haben, und Ihr IT-Supportmitarbeiter kann die Unterstützung von Benutzern bei der Neukonfiguration von Outlook überfordern.

Wenn Sie über eine Cutover-Migration nachdenken, sollten Sie Folgendes beachten:

- Microsoft 365 muss eine Verbindung mit Ihren Exchange 2010 Servern mit Outlook Anywhere über TCP-Port 443 herstellen.
- Alle lokalen Postfächer werden nach Microsoft 365 verschoben.
- Sie benötigen ein lokales Administratorkonto, das Zugriff hat, um den Inhalt der Postfächer Ihrer Benutzer zu lesen.
- Die Exchange 2010 akzeptierten Domänen, die Sie in Microsoft 365 verwenden möchten, müssen im Dienst als verifizierte Domänen hinzugefügt werden.
- Zwischen dem Zeitpunkt, zu dem Sie die Migration starten, und nach Beginn der Abschlussphase synchronisiert Microsoft 365 in regelmäßigen Abständen die Microsoft 365-und lokalen Postfächer. Auf diese Weise können Sie die Migration abschließen, ohne sich Gedanken darüber machen zu müssen, dass e-Mails in Ihren lokalen Postfächern hinterlassen werden.
- Benutzer erhalten neue temporäre Kennwörter für Ihr Microsoft 365-Konto, die Sie ändern müssen, wenn Sie sich zum ersten Mal bei ihren Postfächern anmelden.
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen auf jedem Ihrer Geräte ein neues Outlook-Profil einrichten und Ihre e-Mails erneut herunterladen. Die Menge an e-Mails, die von Outlook heruntergeladen werden können, kann variieren. Weitere Informationen finden Sie unter [Work Offline in Outlook](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

Weitere Informationen zur Migration von Cutover finden Sie unter:

- [Was Sie über eine Cutover-e-Mail-Migration wissen müssen](https://docs.microsoft.com/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Durchführen einer Cutover Migration von e-Mails zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>Minimale Hybrid Migration

Eine minimale Hybrid-oder Express-Migration ist eine, bei der Sie ein paar hundert Postfächer haben, die Sie zu Microsoft 365 migrieren möchten, die Migration innerhalb weniger Wochen abschließen können und keine der erweiterten Hybrid Migrations Features wie freigegebene Frei/Gebucht-Kalenderinformationen benötigen.

Die minimale Hybrid Migration eignet sich hervorragend für Unternehmen, die mehr Zeit benötigen, um ihre Postfächer zu Microsoft 365 zu migrieren, aber dennoch die Migration innerhalb weniger Wochen abschließen möchten. Sie erhalten einige Vorteile der fortgeschritteneren vollständigen Hybrid Migration ohne viele der Komplexitäten. Sie können steuern, wie viele und welche Postfächer zu einem bestimmten Zeitpunkt migriert werden. Microsoft 365-Postfächer werden mit dem Benutzernamen und den Kennwörtern Ihrer lokalen Konten erstellt. Und im Gegensatz zu Cutover-Migrationen müssen Ihre Benutzer Ihre Outlook-Profile nicht neu erstellen.

Wenn Sie über eine minimale Hybrid Migration nachdenken, sollten Sie folgende Punkte beachten:

- Sie müssen eine einmalige Verzeichnissynchronisierung zwischen Ihren lokalen Active Directory Servern und Microsoft 365 durchführen.
- Benutzer können sich bei Ihrem Microsoft 365-Postfach mit dem gleichen Benutzernamen und Kennwort anmelden, die Sie beim Migrieren Ihres Postfachs verwendet haben.
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen kein neues Outlook-Profil auf den meisten Ihrer Geräte einrichten (einige ältere Android-Telefone benötigen möglicherweise ein neues Profil) und müssen Ihre e-Mails nicht erneut herunterladen.

Weitere Informationen zur minimalen Hybrid Migration finden Sie unter [use minimal Hybrid to Quick migrate Exchange mailboxes to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate).

### <a name="full-hybrid"></a>Vollständige hybridbereitstellung

Eine vollständige Hybrid Migration ist eine, in der Ihre Organisation viele Hunderte, bis zu Zehntausende von Postfächern hat und Sie einige oder alle von Ihnen zu Microsoft 365 verschieben möchten. Da diese Migrationen normalerweise längerfristig sind, ermöglichen Hybrid Migrationen Folgendes:

- Zeigen Sie lokalen Benutzern die Frei/Gebucht-Kalenderinformationen für Benutzer in Microsoft 365 an, und umgekehrt.
- Siehe eine einheitliche globale Adressliste, die Empfänger sowohl in lokal als auch in Microsoft 365 enthält.
- Zeigen Sie die vollständigen Outlook-Empfänger Empfänger Eigenschaften für alle Benutzer an, unabhängig davon, ob Sie lokal oder in Microsoft 365 sind.
- Sichere e-Mail-Kommunikation zwischen lokalen Exchange-Servern und Office 365 mithilfe von TLS und Zertifikaten.
- Behandeln Sie Nachrichten, die zwischen lokalen Exchange-Servern und Microsoft 365 gesendet werden, als intern, sodass Sie folgende Möglichkeiten haben:
  - Durch Transport-und Compliance-Agents, die auf interne Nachrichten Zielen, ordnungsgemäß ausgewertet und verarbeitet werden.
  - Umgehen von Anti-Spam-Filtern.

Vollständige Hybrid Migrationen eignen sich am besten für Organisationen, die für mehrere Monate oder mehr in einer Hybrid Konfiguration bleiben möchten. Sie erhalten die weiter oben in diesem Abschnitt aufgeführten Features sowie die Verzeichnissynchronisierung, bessere integrierte Compliance-Features und die Möglichkeit, Postfächer mithilfe von Online Postfachverschiebungen von und nach Microsoft 365 zu verschieben. Microsoft 365 wird zu einer Erweiterung Ihrer lokalen Organisation.

Wenn Sie über eine vollständige Hybrid Migration nachdenken, sollten Sie Folgendes beachten:

- Vollständige Hybrid Migrationen sind nicht für alle Arten von Organisationen geeignet. Aufgrund der Komplexität von vollständigen Hybrid Migrationen sehen Organisationen mit weniger als ein paar hundert Postfächern normalerweise keine Vorteile, die den Aufwand und die Kosten rechtfertigen, die für die Einrichtung eines eingerichtet werden müssen. Wenn dies wie Ihre Organisation klingt, wird dringend empfohlen, stattdessen Cutover oder minimale Hybrid Migrationen zu verwenden.
- Sie müssen die Verzeichnissynchronisierung mithilfe von Azure Active Directory (Azure AD) zwischen Ihren lokalen Active Directory Servern und Microsoft 365 herstellen.
- Benutzer können sich bei Ihrem Microsoft 365-Postfach mit dem gleichen Benutzernamen und Kennwort anmelden, die Sie bei der Anmeldung beim lokalen Netzwerk verwenden (erfordert Azure AD Verbindung mit der Kennwortsynchronisierung und/oder Active Directory Verbunddienste).
- Sie benötigen eine Microsoft 365-Lizenz, die Exchange Online für jedes Benutzerpostfach enthält, das Sie migrieren.
- Benutzer müssen kein neues Outlook-Profil auf den meisten Ihrer Geräte einrichten (einige ältere Android-Telefone benötigen möglicherweise ein neues Profil) und müssen Ihre e-Mails nicht erneut herunterladen.

> [!IMPORTANT]
> Wenn sich Ihre Organisation für die Migration von Postfächern zu Microsoft 365 entscheidet, aber Dirsync oder Azure AD eine Verbindung herstellen möchten, um die Verwaltung von Benutzerkonten aus lokalen Active Directory fortzusetzen, müssen Sie mindestens einen lokalen Exchange-Server beibehalten. Wenn der letzte Exchange-Server entfernt wird, können Sie in Exchange Online keine Änderungen an Exchange-Empfängern vornehmen. Dies liegt daran, dass die Autoritäts Quelle in Ihrem lokalen Active Directory bleibt und dass dort Änderungen vorgenommen werden müssen.

Wenn eine vollständige Hybrid Migration für Sie richtig klingt, sehen Sie sich die folgenden Ressourcen an, um Sie bei der Migration zu unterstützen:

- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
- [Hybridbereitstellungen in Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid)
- [Assistent für die Hybridkonfiguration](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)
- [FAQs zum Assistenten für die Hybridkonfiguration](https://docs.microsoft.com/exchange/hybrid-configuration-wizard-faqs)
- [Voraussetzungen für die Hybridbereitstellung](https://docs.microsoft.com/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>Upgrade auf eine neuere Version von Exchange Server lokal

Wir sind zwar der festen Überzeugung, dass Sie durch eine vollständige Migration auf Microsoft 365 den besten nutzen und die optimale Benutzererfahrung erzielen können, aber wir verstehen auch, dass einige Organisationen Exchange-Server lokal halten müssen. Dies kann an regulatorische Anforderungen liegen, um sicherzustellen, dass Daten nicht in einem Rechenzentrum in einem anderen Land gespeichert werden, oder dass es sich möglicherweise um eindeutige Einstellungen oder Anforderungen handelt, die in der Cloud nicht erfüllt werden können, oder dass Exchange zum Verwalten von Cloud-Postfächern benötigt wird, da Sie weiterhin Active Directory lokal verwenden. In jedem Fall, für den Sie Exchange lokal auswählen oder halten müssen, sollten Sie sicherstellen, dass Ihre Exchange 2010 Umgebung auf mindestens Exchange 2013 oder Exchange 2016 aktualisiert wird und Exchange 2010 vor dem Ende des Support Datums entfernt wird.

Für eine optimale Benutzerfreundlichkeit wird empfohlen, dass Sie die verbleibende lokale Umgebung auf Exchange 2016 aktualisieren. Sie müssen Exchange Server 2013 nicht installieren, wenn Sie direkt von Exchange Server 2010 zu Exchange Server 2016 gehen möchten.

Exchange 2016 umfasst alle Features und Fortschritte, die in früheren Versionen von Exchange enthalten sind, und es entspricht am ehesten der verfügbaren Benutzeroberfläche von Microsoft 365 (obwohl einige Funktionen nur in Microsoft 365 verfügbar sind). Sehen Sie sich nur einige der Dinge an, die Ihnen fehlen:

|Exchange-Version|Features|
|---|---|
|**Exchange 2013**|Vereinfachte Architektur Verringerung der Anzahl von Serverrollen auf drei (Postfach, Client Zugriff, Edge-Transport)|
||Datenverlust-Verhinderung-Richtlinien (DLP), mit denen vertrauliche Informationen vor Undichtigkeiten bleiben|
||Erheblich verbesserte Outlook Web App Erfahrung|
|**Exchange 2016**|*Features aus Exchange 2013 und...*|
||Weitere vereinfachte Serverrollen nur für Postfach-und Edge-Transport|
||Verbesserte DLP zusammen mit der Integration in SharePoint|
||Verbesserte Ausfallsicherheit der Datenbank|
||Online Dokument Zusammenarbeit|

|Berücksichtigt|Weitere Informationen|
|---|---|
|Ende der Support Daten|Wie Exchange 2010 verfügt jede Version von Exchange über ein eigenes Datum für die Unterstützung des Supports:|
||**Exchange 2013** -April 2023|
||**Exchange 2016** -Oktober 2025|
||Je früher das Ende des Support Datums ist, desto schneller müssen Sie eine weitere Migration durchführen. April 2023 ist viel näher als Sie denken!|
|Migrationspfad zu Exchange 2013 oder 2016|Der Migrationspfad von Exchange 2010 zu einer neueren Version ist unabhängig davon, ob Sie Exchange 2013 oder Exchange 2016 wählen:|
||Installieren von Exchange 2013 oder 2016 in Ihrer vorhandenen Exchange 2010 Organisation verschieben von Diensten und anderen Infrastrukturen in Exchange 2013 oder 2016 Verschieben von Postfächern und öffentlichen Ordnern auf Exchange 2013 oder 2016 still gebliebenen Exchange 2010 Servern|
|Versions Koexistenz|Bei der Migration zu Exchange 2013 oder Exchange 2016 können Sie beide Versionen in einer vorhandenen Exchange 2010 Organisation installieren. Auf diese Weise können Sie einen oder mehrere Exchange 2013-oder Exchange 2016-Server installieren und die Migration durchführen.|
|Serverhardware|Die Server Hardwareanforderungen wurden von Exchange 2010 geändert. Sie müssen sicherstellen, dass die Hardware, die Sie verwenden werden, kompatibel ist. Hier finden Sie weitere Informationen zu den Hardwareanforderungen für jede Version:|
||[Exchange 2016-System Anforderungen](https://docs.microsoft.com/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)|
||[Exchange 2013 System Anforderungen](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)|
||Sie werden feststellen, dass Sie mit den signifikanten Verbesserungen bei der Exchange-Leistung und der erhöhten Rechenleistung und Speicherkapazität in neueren Servern wahrscheinlich weniger Server zur Unterstützung der gleichen Anzahl von Postfächern benötigen.|
|Betriebssystemversion|Für jede Version werden mindestens die folgenden Betriebssystemversionen unterstützt:|
||**Exchange 2016** Windows Server 2012|
||**Exchange 2013** Windows Server 2008 R2 SP1|
||Weitere Informationen zur Betriebssystemunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Active Directory Gesamtstrukturfunktionsebene|Für jede Version werden mindestens Active Directory Gesamtstrukturfunktionsebenen unterstützt:|
||**Exchange 2016** Windows Server 2008 R2 SP1|
||**Exchange 2013** Windows Server 2003|
||Weitere Informationen zur Unterstützung der Gesamtstrukturfunktionsebene finden Sie unter [Exchange supportable Matrix](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|
|Office-Clientversionen|Für jede Version werden mindestens die folgenden Office-Clientversionen unterstützt:|
||**Exchange 2016** Office 2010 (mit den neuesten Updates)|
||**Exchange 2013** Office 2007 SP3|
||Weitere Informationen zur Office-Clientunterstützung finden Sie unter [Unterstützungs Matrix für Exchange](https://docs.microsoft.com/exchange/plan-and-deploy/supportability-matrix).|

Sie können die folgenden Ressourcen verwenden, um Sie bei der Migration zu unterstützen:

- [Exchange-Bereitstellungs-Assistent](https://aka.ms/exdeploy)
- Active Directory Schemaänderungen für Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- System Anforderungen für Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/system-requirements?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Voraussetzungen für Exchange [2016](https://docs.microsoft.com/exchange/plan-and-deploy/prerequisites?view=exchserver-2016), [2013](https://docs.microsoft.com/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Zusammenfassung der Optionen für Office 2010 Client und Server und Windows 7

Eine visuelle Zusammenfassung der Optionen für Upgrades, Migration und die Cloud für Office 2010-Clients und -Server sowie für Windows 7 finden Sie auf unter dem [Poster zum Supportende](../downloads/Office2010Windows7EndOfSupport.pdf).

[![Bild des Posters zum Ende des Supports für Office 2010-Clients und -Server sowie Windows 7](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

Dieses einseitige Poster veranschaulicht auf einfache Weise, welche verschiedenen Pfade Sie wählen können, um zu verhindern, dass Office 2010-Clients und -Serverprodukte sowie Windows 7 das Ende des Supports erreichen. Bevorzugte Pfade und unterstützte Optionen in Microsoft 365 Enterprise sind hervorgehoben.

Sie können dieses Poster in den Formaten „Brief“, „Legal“ oder „Tabloid“ (27,94 x 43,18 cm) [herunterladen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) und ausdrucken.

## <a name="what-if-i-need-help"></a>Was kann ich tun, wenn ich Hilfe brauche?

Wenn Sie eine Migration zu Microsoft 365 durchführen, können Sie möglicherweise den Microsoft-kurzleistungs Dienst verwenden. In diesem Artikel werden bewährte Methoden, Tools und Ressourcen bereitgestellt, um die Migration zu Microsoft 365 so nahtlos wie möglich zu gestalten. Das beste daran ist, dass Sie einen echten Supporttechniker haben, der Sie durch die Migration führt – von der Planung und dem Entwurf bis hin zur Migration Ihres letzten Postfachs. Wenn Sie mehr über die Kurzzeit erfahren möchten, sehen Sie sich [Microsoft](https://fasttrack.microsoft.com/)kurzfall an.

Wenn bei der Migration zu Microsoft 365 Probleme auftreten und Sie nicht den Kurzlauf oder die Migration zu einer neueren Version von Exchange Server verwenden, helfen wir Ihnen gerne weiter. Hier sind einige Ressourcen, die Sie verwenden können:

- [Technische Community](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [Support für Kunden](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-topics"></a>Verwandte Themen

[Ressourcen, die Ihnen beim Upgrade von Office 2010-Servern und -Clients helfen](upgrade-from-office-2010-servers-and-products.md)
