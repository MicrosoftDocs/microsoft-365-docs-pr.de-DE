---
title: Informationen zu Datensätzen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Erfahren Sie mehr über Datensätze, um Sie beim Implementieren einer Datensatzverwaltungslösung in Microsoft 365 zu unterstützen.
ms.openlocfilehash: e64e91aeef307d05f23c47987a84baaf386324df
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685441"
---
# <a name="learn-about-records"></a>Informationen zu Datensätzen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Verwaltung von Datensätzen in Microsoft 365 hilft Ihrer Organisation bei der Einhaltung von Unternehmensrichtlinien und gesetzlichen oder regulatorischer Verpflichtungen bei gleichzeitiger Verringerung der Risiken und der gesetzlichen Haftung.

Wenn Inhalt als Datensatz markiert ist:

- Die Elemente werden hinsichtlich der [zulässigen oder blockierten Aktionen](#compare-restrictions-for-what-actions-are-allowed-or-blocked) eingeschränkt.

- Andere Aktivitäten in Verbindung mit dem Element werden protokolliert.

- Sie haben einen Verfügungsnachweis, wenn die Elemente am Ende ihrer Aufbewahrungsfrist gelöscht werden.

Verwenden Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), um Inhalte als Datensätze zu kennzeichnen. Sie können diese Bezeichnungen entweder veröffentlichen, damit Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder diese Bezeichnungen automatisch auf Inhalte anwenden, die Sie als Datensatz markieren möchten.

Durch die Verwendung von Aufbewahrungsbezeichnungen zum Markieren von Inhalten als Datensätze können Sie eine einzige und konsistente Strategie für die Verwaltung von Datensätzen in Ihrer Microsoft 365-Umgebung implementieren.

## <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Vergleichen Sie die Einschränkungen für die zulässigen oder blockierten Aktionen

Verwenden Sie die folgende Tabelle, um zu ermitteln, welche Einschränkungen für den Inhalt durch das Anwenden einer Standardaufbewahrungsbezeichnung und von Aufbewahrungsbezeichnungen, die den Inhalt als Datensatz kennzeichnen, gelten. 

Eine Standardaufbewahrungsbezeichnung kann Daten speichern, ohne den Inhalt als Datensatz zu markieren.

>[!NOTE] 
> Der Vollständigkeit halber enthält die Tabelle Spalten für einen gesperrten und entsperrten Datensatz, die für SharePoint und OneDrive gelten, jedoch nicht für Exchange. Die Möglichkeit zum Sperren und Entsperren eines Datensatzes verwendet die [Datensatzversionsverwaltung](record-versioning.md), die für Exchange-Elemente nicht unterstützt wird. Für alle Exchange-Elemente, die als Datensatz markiert sind, ist das Verhalten der Spalte **Datensatz gesperrt** und der Spalte **Datensatz entsperrt** nicht relevant.


|Aktion| Aufbewahrungsbezeichnung |Datensatz – gesperrt| Datensatz – entsperrt|
|:-----|:-----|:-----|:-----|:-----|
|Inhalt bearbeiten|Zulässig | **Gesperrt** | Zulässig|
|Bearbeiten Sie Eigenschaften, einschließlich Umbenennen|Allowed |Zulässig | Allowed|
|Löschen|Zulässig <sup>1</sup> |**Gesperrt** | **Gesperrt**|
|Kopie|Allowed |Zulässig | Allowed|
|Innerhalb eines Containers bewegen<sup>2</sup>|Allowed |Zulässig | Allowed|
|Über Container hinweg bewegen <sup>2</sup>|Zulässig |Zulässig, wenn nie entsperrt | Zulässig|
|Öffnen/Lesen|Allowed |Zulässig | Allowed|
|Ändern der Bezeichnung|Zulässig |Zulässig – nur Container-Administrator | Zulässig – nur Container-Administrator|
|Bezeichnung entfernen|Zulässig |Zulässig – nur Container-Administrator | Zulässig – nur Container-Administrator|

Fußnoten:

<sup>1</sup> Unterstützt von OneDrive und Exchange durch Aufbewahren einer Kopie an einem gesicherten Ort, jedoch blockiert von SharePoint.

Nachricht, die ein Benutzer sieht, wenn er versucht, ein beschriftetes Dokument in SharePoint zu löschen:

![Nachricht, dass das Element nicht aus SharePoint gelöscht wurde](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)


<sup>2</sup> Zu den Containern gehören SharePoint-Dokumentbibliotheken und Exchange-Postfächer.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie noch keine Aufbewahrungsbezeichnungen für die Datensatzverwaltung besitzen, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Mehr zu Inhalte als Datensatz markieren finden Sie unter [Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren](declare-records.md).
