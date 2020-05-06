---
title: DSGVO für Exchange Server
description: Hier erfahren Sie, wie Sie DSGVO-Anforderungen für eine lokale Exchange Server-Instanz, z. B. bezüglich der Aufbewahrung von gelöschten Elementen und der automatischen Datensammlung, behandeln.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: c6cf5aa14c9b38f2d6a4323bd2d424d5abd72140
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036280"
---
# <a name="gdpr-for-exchange-server"></a>DSGVO für Exchange Server

Im Rahmen des Schutzes persönlicher Informationen empfehlen wir Folgendes:

-   Verwenden Sie [Aufbewahrungstags und -richtlinien](https://technet.microsoft.com/library/dd297955(v=exchg.160).aspx) in Exchange Server, um eine E-Mail-Lebenszyklusrichtlinie zu implementieren.

-   Stellen Sie die [Verwaltung von Informationsrechten](https://technet.microsoft.com/library/dd638140(v=exchg.160).aspx) bereit, um zu begrenzen, wer auf in Exchange Server gespeicherte Informationen zugreifen kann.

-   Aktivieren Sie die [BitLocker-Verschlüsselung](https://blogs.technet.microsoft.com/exchange/2015/10/20/enabling-bitlocker-on-exchange-servers/) auf den Servern.

## <a name="identifying-in-scope-content"></a>Identifizieren von betroffenen Inhalten

Exchange verwendet zwei primäre Speicher-Repositorys für von Endbenutzern generierte Inhalte: Postfächer und öffentliche Ordner. Inhalte, die im Postfach eines einzelnen Benutzers gespeichert werden, sind eindeutig diesem Benutzer zugeordnet und stellen dessen Standard-Repository in Exchange dar. Die in einem Benutzerpostfach gespeicherten Daten umfassen Inhalte, die mithilfe von Outlook, Outlook im Web (vormals Outlook Web App), Exchange ActiveSync, Skype for Business-Clients und anderen Tools von Drittanbietern, die über POP, IMAP oder Exchange-Webdienste (Exchange Web Services, EWS) eine Verbindung mit Exchange-Servern herstellen, erstellt wurden. Beispiele für diese Elemente sind: Nachrichten, Kalenderelemente (Besprechungen und Termine), Kontakte, Notizen und Aufgaben. Durch das Löschen des Postfachs eines einzelnen Benutzers werden Inhalte entfernt, die von dem Benutzer erstellt oder im Kontext des Postfachs direkt an den Benutzer gesendet wurden. Sie können Benutzerpostfächer im Exchange Admin Center (EAC) oder unter Verwendung des Cmdlet [Remove-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/remove-mailbox?view=exchange-ps) in der Exchange-Verwaltungsshell löschen.\
Hinweis: Der Parameter "Permanent" des Cmdlet "Remove-Mailbox" ist mit Vorsicht zu verwenden, da die Daten bei Verwendung dieser Option nicht wiederhergestellt werden können.

Exchange bietet auch freigegebene Postfächer, die einem oder mehreren Benutzern Zugriff gewähren, um in einem gemeinsamen Postfach gespeicherte Inhalte senden und empfangen zu können. Das freigegebene Postfach ist eine eindeutige Entität, die nicht mit einem einzigen Konto verknüpft ist. Stattdessen wird mehreren Benutzer Zugriff gewährt, um E-Mail-Inhalte im gemeinsamen Postfach senden, empfangen und prüfen zu können. Gemeinsame Postfächer werden über das Exchange Admin Center und die Cmdlets verwaltet, die auch zum Verwalten normaler Benutzerpostfächer verwendet werden. Wenn Sie einzelne Nachrichten aus einem Postfach entfernen müssen, stehen je nach Version von Exchange verschiedene Optionen zur Verfügung. In Exchange Server 2010 und 2013 können Sie mithilfe des Cmdlet [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) mit dem Parameter "DeleteContent" Nachrichten aus einem Postfach identifizieren und entfernen. In Exchange Server 2016 und höher müssen Sie die Funktion [New-ComplianceSearch](https://technet.microsoft.com/library/ff459253(v=exchg.160).aspx) verwenden.

Öffentliche Ordner sind eine freigegebene Speicherimplementierung, die keinem bestimmten Benutzer zugeordnet ist. Stattdessen wird Benutzern Zugriff auf öffentliche Ordner gewährt, um Inhalte zu generieren. Die tatsächliche Implementierung öffentlicher Ordner variiert je nach Version von Exchange (Exchange Server 2010 verwendet eine andere Implementierung als Exchange Server 2013 und höher). Es gibt eingeschränkte Tools für die Verwaltung der Inhalte in öffentlichen Ordnern. Clienttools (z. B. Outlook) sind der primäre Mechanismus zur Verwaltung von Inhalten in öffentlichen Ordnern. Es gibt Cmdlets für die Verwaltung von öffentlichen Ordnerobjekten, aber nicht für die Verwaltung von einzelnen Inhaltselementen in dem öffentlichen Ordner. Zur Verwaltung einzelner öffentlicher Ordnerelemente wird wahrscheinlich ein benutzerdefiniertes Skript benötigt, das Exchange-Webdienste (EWS) oder andere Tools von Drittanbietern nutzt.

Die primäre Anforderung wird wahrscheinlich die Verwaltung der Postfachinhalte einzelner Benutzer sein. Diese Anforderung wird ganz einfach mit den Grafik- oder Cmdlet-basierten Tools erfüllt, die Sie häufig zum Verwalten von Postfächern verwenden. Wenn Sie Inhalte über mehrere Postfächer oder Arten von Ressourcen hinweg verarbeiten müssen, ist [eDiscovery](https://technet.microsoft.com/library/dd298021(v=exchg.160).aspx) der bevorzugte Mechanismus innerhalb von Exchange zur Identifizierung von betroffenen Inhalten.

## <a name="deleted-item-retention"></a>Aufbewahrungszeit für gelöschte Elemente

Wenn Sie einzelne Nachrichten oder Elemente aus einem Postfach löschen (nicht das gesamte Postfach oder die öffentliche Ordner-Ressource selbst), wird der Inhalt in einer wiederherstellbaren Form basierend auf dem Wert des Parameters "DeletedItemRetention" für die Postfachdatenbank oder öffentliche Ordnerdatenbank aufbewahrt. Der Standardwert ist 14 Tage, wobei dieser Wert von einem Exchange-Administrator konfiguriert werden kann.

## <a name="removing-soft-deleted-and-disconnected-mailboxes"></a>Entfernen vorläufig gelöschter und getrennter Postfächer

Wenn ein Exchange-Postfach deaktiviert, gelöscht oder zwischen Datenbanken verschoben wird (z B. im Rahmen des Lastenausgleichs), wird dem Postfach je nach Operation der Status "deaktiviert", "vorläufig gelöscht" oder "getrennt" zugeordnet. Solange das Postfach einen dieser Zustände aufweist, bewahrt Exchange das Postfach (einschließlich dessen Inhalte) basierend auf dem aktuellen Wert des Parameters "MailboxRetention", der in der Postfachdatenbank festgelegt ist, auf. Der Standardwert ist 30 Tage, wobei dieser Wert von einem Exchange-Administrator konfiguriert werden kann. Mit dem Cmdlet [Remove-StoreMailbox](https://docs.microsoft.com/powershell/module/exchange/mailbox-databases-and-servers/remove-storemailbox?view=exchange-ps) können Sie erzwingen, dass Exchange alle mit einem Postfach verbundenen Daten vor dem natürlichen Ablauf eines Postfachs dauerhaft entfernt (löscht).

> [!IMPORTANT]
> Verwenden Sie das Cmdlet "Remove-StoreMailbox" mit Vorsicht, da es zu einem nicht wiederherstellbaren Verlust von Daten des Zielpostfachs führt. 

## <a name="on-prem-to-cloud-migrations"></a>Migrationen aus lokalen Installationen in die Cloud

Beim Migrieren von Daten aus Exchange Server in Exchange Online bleiben migrierte Daten möglicherweise auf dem lokalen Exchange-Quellserver in einer Form erhalten, die von einem Exchange-Administrator wiederhergestellt werden kann. Standardmäßig werden diese Daten innerhalb von 30 Tagen automatisch aus der Datenbank entfernt (siehe die Abschnitte zum Entfernen vorläufig gelöschter und getrennter Postfächer).

## <a name="automatic-data-collection-reported-to-microsoft-by-exchange-server"></a>Automatische Datensammlung durch Exchange Server gemeldet an Microsoft

Exchange Server, die in lokalen Umgebungen bereitgestellt sind, bieten keine automatisierten Berichte oder Endbenutzer-Datenerfassung für Microsoft. Exchange Server, bei denen Watson-Absturzspeicherabbildberichte im Windows-Betriebssystem aktiviert sind, erhalten zum Zeitpunkt der Erstellung des Absturzberichts möglicherweise eingeschränkte Speicherinhalte.
