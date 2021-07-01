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
description: Verwenden Sie das eDiscovery-Tool für die Inhaltssuche im Security & Compliance Center, um E-Mails in Exchange Postfächern, Dokumenten in SharePoint Websites und OneDrive Speicherorten sowie Chatunterhaltungen in Skype for Business schnell zu finden.
ms.openlocfilehash: a70c234331d1329fb80f32fb81762391a862d487
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226059"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Suchen nach Inhalten mithilfe des Tools für die Inhaltssuche

Verwenden Sie das Tool für die Inhaltssuche im Security & Compliance Center, um E-Mails in Exchange Postfächern, Dokumenten in SharePoint Websites und OneDrive Speicherorten sowie Chatunterhaltungen in Skype for Business schnell zu finden. Sie können das Tool für die Inhaltssuche verwenden, um in Tools für die Zusammenarbeit wie Microsoft Teams und Microsoft 365 Gruppen nach E-Mails, Dokumenten und Chatunterhaltungen zu suchen.

## <a name="search-for-content"></a>Suchen nach Inhalten

Der erste Schritt besteht darin, mit der Verwendung des Inhaltssuche-Tools zu beginnen, um Inhaltsspeicherorte für die Suche auszuwählen und eine Stichwortabfrage so zu konfigurieren, dass nach bestimmten Elementen gesucht wird. Sie können auch einfach die Abfrage leer lassen und alle Elemente an den Zielspeicherorten zurückgeben.

- [Erstellen und Ausführen](content-search.md) einer Inhaltssuche

- [Featurereferenz] für die Inhaltssuche (content-search-reference.md)

- [Erstellen von Suchabfragen und Verwenden von Bedingungen](keyword-queries-and-search-conditions.md) zum Eingrenzen der Suche

- [Konfigurieren der Suchberechtigungsfilterung,](permissions-filtering-for-content-search.md) sodass ein eDiscovery-Manager nur eine Teilmenge von Postfächern oder Websites in Ihrer Organisation durchsuchen kann

- [Ausführen einer ID-Listensuche,](csv-file-for-an-id-list-content-search.md) um nach bestimmten E-Mail-Nachrichten zu suchen

- [Durchsuchen von cloudbasierten Postfächern](search-cloud-based-mailboxes-for-on-premises-users.md) für lokale Benutzer in Microsoft 365

- Anzeigen von [Schlüsselwortstatistiken](view-keyword-statistics-for-content-search.md) für die Ergebnisse einer Suche und ggf. Verfeinern der Abfrage

- [Suchen nach Drittanbieterdaten,](use-content-search-to-search-third-party-data-that-was-imported.md) die Ihre Organisation in Microsoft 365 importiert hat

- [Massenbearbeitung](bulk-edit-content-searches.md) der Abfrage- und Inhaltsspeicherorte für mehrere Suchvorgänge

- [Wiederholen einer Inhaltssuche](retry-failed-content-search.md) zum Beheben eines Inhaltsspeicherortfehlers

- [Beibehalten von Bcc-Empfängern,](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) damit Sie nach diesen suchen können

## <a name="perform-actions-on-content-you-find"></a>Ausführen von Aktionen für gefundene Inhalte

Nachdem Sie eine Suche ausgeführt und nach Bedarf verfeinern, besteht der nächste Schritt darin, etwas mit den von der Suche zurückgegebenen Ergebnissen zu tun. Sie können die Ergebnisse exportieren und auf Ihren lokalen Computer herunterladen oder im Falle eines E-Mail-Angriffs auf Ihre Organisation die Ergebnisse einer Suche aus Benutzerpostfächern löschen.

- [Exportieren sie die Ergebnisse einer Inhaltssuche,](export-search-results.md) und laden Sie sie auf Ihren lokalen Computer herunter.

- [Suchen und Löschen von E-Mail-Nachrichten,](search-for-and-delete-messages-in-your-organization.md) z. B. Nachrichten, die einen Virus, gefährliche Anlagen oder Phishingnachrichten enthalten

- [Exportieren eines Berichts](export-a-content-search-report.md) über die Ergebnisse einer Inhaltssuche, ohne die tatsächlichen Ergebnisse zu exportieren

## <a name="learn-more-about-content-search"></a>Weitere Informationen zur Inhaltssuche

Die Inhaltssuche ist einfach zu verwenden, ist aber auch ein leistungsstarkes Tool. Im Hintergrund ist viel los. Je mehr Sie darüber wissen und ihr Verhalten und seine Einschränkungen verstehen, desto erfolgreicher werden Sie es für die Such- und Untersuchungsanforderungen Ihrer Organisation verwenden. Informieren Sie sich über folgende Themen:

- [Teilweise indizierte Elemente in Exchange und SharePoint](partially-indexed-items-in-content-search.md) und wie sie beim Exportieren und Herunterladen von Suchergebnissen eingeschlossen oder ausgeschlossen werden

- [Untersuchen teilweise indizierter Elemente](investigating-partially-indexed-items-in-ediscovery.md) und Ermitteln der Gefährdung Ihrer Organisation für diese Elemente

- [Grenzwerte des Inhaltssuche-Tools,](limits-for-content-search.md)z. B. die maximale Anzahl von Suchvorgängen, die Gleichzeitig ausgeführt werden können, und die maximale Anzahl von Inhaltsspeicherorten, die Sie in eine einzelne Suche einschließen können

- [Geschätzte und tatsächliche Suchergebnisse](differences-between-estimated-and-actual-ediscovery-search-results.md) und die Gründe, warum es beim Exportieren und Herunterladen von Suchergebnissen unterschiede zwischen ihnen geben kann

- [Deduplizierung in Suchergebnissen,](de-duplication-in-ediscovery-search-results.md) die Sie aktivieren können, wenn Sie E-Mail-Nachrichten exportieren, die die Ergebnisse einer Suche sind

## <a name="use-scripts-for-advanced-scenarios"></a>Verwenden von Skripts für erweiterte Szenarien

Manchmal müssen Sie komplexere, komplexere und sich wiederholende Aufgaben für die Inhaltssuche ausführen. In diesen Fällen ist es einfacher und schneller, PowerShell-Befehle im Security & Compliance Center zu verwenden. Um dies zu vereinfachen, haben wir eine Reihe von Security & Compliance Center PowerShell-Skripts erstellt, mit denen Sie komplexe Aufgaben im Zusammenhang mit der Inhaltssuche erledigen können.

- [Durchsuchen Sie bestimmte Postfach- und Websiteordner](use-content-search-for-targeted-collections.md) (als *Zielsammlung bezeichnet), wenn Sie sicher sind, dass sich elemente, die für einen Fall relevant sind, in diesem Ordner befinden.

- [Durchsuchen des Postfachs und OneDrive Speicherorts](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) nach einer Liste von Benutzern

- [Erstellen, Melden und Löschen mehrerer Suchvorgänge,](create-report-on-and-delete-multiple-content-searches.md) um Suchdaten schnell und effizient zu identifizieren und zu löschen

- [Klonen Sie eine Inhaltssuche,](clone-a-content-search.md) und vergleichen Sie schnell die Ergebnisse verschiedener Stichwortsuchabfragen, die an denselben Inhaltsspeicherorten ausgeführt werden. oder verwenden Sie das Skript, um Zeit zu sparen, indem Sie beim Erstellen einer neuen Suche keine große Anzahl von Inhaltsspeicherorten erneut eingeben müssen.