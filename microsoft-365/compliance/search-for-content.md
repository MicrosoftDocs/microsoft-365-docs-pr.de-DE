---
title: Suchen nach Inhalten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: 'Verwenden Sie das eDiscovery-Tool für die Inhaltssuche im Security & Compliance Center, um E-Mails in &, Dokumente auf #A1 und #A2 sowie Chatunterhaltungen in Skype for Business schnell zu finden.'
ms.openlocfilehash: 80234a512d13deda29a61073bec62990d135f30e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333686"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Suchen nach Inhalten mithilfe des Inhaltssuchtools

Verwenden Sie das Tool für die Inhaltssuche im Security & Compliance Center, um E-Mails in &, Dokumente auf #A1 und OneDrive-Standorten sowie Chatunterhaltungen in Skype for Business schnell zu finden. Sie können das Inhaltssuchtool verwenden, um in Tools für die Zusammenarbeit wie Microsoft Teams und Microsoft 365-Gruppen nach E-Mails, Dokumenten und Chatunterhaltungen zu suchen.
  
## <a name="search-for-content"></a>Suchen nach Inhalten

Der erste Schritt besteht in der Verwendung des Inhaltssuchtools zum Auswählen von Inhaltsstandorten zum Suchen und Konfigurieren einer Schlüsselwortabfrage für die Suche nach bestimmten Elementen. Sie können die Abfrage auch einfach leer lassen und alle Elemente an den Zielstandorten zurückgeben.
  
- [Erstellen und Ausführen einer](content-search.md) Inhaltssuche

- [Featurereferenz] für die Inhaltssuche (content-search-reference.md)

- [Erstellen von Suchabfragen und Verwenden von Bedingungen zum](keyword-queries-and-search-conditions.md) Einen der Suche 

- [Konfigurieren der Filterung von](permissions-filtering-for-content-search.md) Suchberechtigungen, sodass ein eDiscovery-Manager nur eine Teilmenge von Postfächern oder Websites in Ihrer Organisation durchsuchen kann 

- [Ausführen einer ID-Listensuche](csv-file-for-an-id-list-content-search.md) zum Suchen nach bestimmten E-Mail-Nachrichten 

- [Durchsuchen cloudbasierter Postfächer ](search-cloud-based-mailboxes-for-on-premises-users.md) nach lokalen Benutzern in Microsoft 365

- [Anzeigen von Schlüsselwortstatistiken](view-keyword-statistics-for-content-search.md) für die Ergebnisse einer Suche und anschließendes Verfeinern der Abfrage bei Bedarf

- [Suchen nach Drittanbieterdaten,](use-content-search-to-search-third-party-data-that-was-imported.md) die Ihre Organisation nach Microsoft 365 importiert hat

- [Massenbearbeitung](bulk-edit-content-searches.md) der Abfrage- und Inhaltsstandorte für mehrere Suchabfragen

- [Wiederholen einer Inhaltssuche zum](retry-failed-content-search.md) Beheben eines Inhaltsspeicherortfehlers

- [Beibehalten von Bcc-Empfängern,](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) damit Sie nach ihnen suchen können 

## <a name="perform-actions-on-content-you-find"></a>Ausführen von Aktionen für Inhalte, die Sie finden

Nachdem Sie eine Suche ausgeführt und bei Bedarf verfeinern haben, müssen Sie im nächsten Schritt etwas mit den von der Suche zurückgegebenen Ergebnissen tun. Sie können die Ergebnisse auf Ihren lokalen Computer exportieren und herunterladen oder im Falle eines E-Mail-Angriffs auf Ihre Organisation die Ergebnisse einer Suche aus Benutzerpostfächern löschen.
  
- [Exportieren sie die Ergebnisse einer Inhaltssuche,](export-search-results.md) und laden Sie sie auf Ihren lokalen Computer herunter. 

- [Suchen und Löschen von](search-for-and-delete-messages-in-your-organization.md) E-Mail-Nachrichten, z. B. Nachrichten, die einen Virus enthalten, gefährliche Anlagen oder Phishingnachrichten

- [Exportieren eines Berichts](export-a-content-search-report.md) über die Ergebnisse einer Inhaltssuche, ohne die tatsächlichen Ergebnisse zu exportieren 

## <a name="learn-more-about-content-search"></a>Weitere Informationen zur Inhaltssuche

Die Inhaltssuche ist einfach zu verwenden, aber sie ist auch ein leistungsstarkes Tool. Hinter den Kulissen ist viel los. Wenn Sie mehr über sie wissen und ihr Verhalten und ihre Einschränkungen verstehen, werden Sie es erfolgreicher für die Such- und Untersuchungsanforderungen Ihrer Organisation verwenden. Informieren Sie sich über folgende Themen:
  
- [Teilweise indizierte Elemente in Exchange und SharePoint](partially-indexed-items-in-content-search.md) und wie Sie sie beim Exportieren und Herunterladen von Suchergebnissen ein- oder ausschließen

- [Untersuchen teilweise indizierter Elemente](investigating-partially-indexed-items-in-ediscovery.md) und Bestimmen der Gefährdung Ihrer Organisation für diese Elemente

- [Beschränkungen des](limits-for-content-search.md)Inhaltssuchtools, z. B. die maximale Anzahl von Suchen, die Sie gleichzeitig ausführen können, und die maximale Anzahl von Inhaltsstandorten, die Sie in einer einzelnen Suche enthalten können

- [Geschätzte und tatsächliche Suchergebnisse und](differences-between-estimated-and-actual-ediscovery-search-results.md) die Gründe, warum beim Exportieren und Herunterladen von Suchergebnissen Unterschiede zwischen diesen bestehen können

- [Deduplizierung in Suchergebnissen,](de-duplication-in-ediscovery-search-results.md) die Sie aktivieren können, wenn Sie E-Mail-Nachrichten exportieren, die die Ergebnisse einer Suche sind

## <a name="use-scripts-for-advanced-scenarios"></a>Verwenden von Skripts für erweiterte Szenarien

Manchmal müssen Sie komplexere und sich wiederholende Inhaltssuchaufgaben ausführen. In diesen Fällen ist es einfacher und schneller, PowerShell-Befehle im Security & Compliance Center zu verwenden. Um dies zu vereinfachen, haben wir eine Reihe von Security & Compliance Center -PowerShell-Skripts erstellt, die Ihnen dabei helfen, komplexe Aufgaben im Zusammenhang mit der Inhaltssuche auszuführen.
  
- [Durchsuchen bestimmter Postfach- und Websiteordner](use-content-search-for-targeted-collections.md) (als *targeted collection bezeichnet), wenn Sie sicher sind, dass sich elemente befinden, die auf einen Fall reagieren, sich in diesem Ordner befinden

- [Durchsuchen des Postfachs und des #A0](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) nach einer Liste von Benutzern 

- [Erstellen, Melden und Löschen mehrerer Suchen](create-report-on-and-delete-multiple-content-searches.md) zum schnellen und effizienten Identifizieren und Auslöschen von Suchdaten 

- [Klonen Sie eine Inhaltssuche,](clone-a-content-search.md) und vergleichen Sie schnell die Ergebnisse verschiedener Schlüsselwortsuchabfragen, die an denselben Inhaltsstandorten ausgeführt werden. oder verwenden Sie das Skript, um Zeit zu sparen, indem Sie beim Erstellen einer neuen Suche keine große Anzahl von Inhaltsstandorten erneut eingeben müssen