---
title: Datensatzverwaltung in Microsoft 365
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Mit der Datensatzverwaltung in Microsoft 365 können Sie Ihre Aufbewahrungszeitpläne auf einen Dateiplan anwenden, der die Aufbewahrung, die Datensatzdeklaration und die Löschung verwaltet.
ms.openlocfilehash: 883fd65e3fba716018a1ed35cc457c2eb8f06c52
ms.sourcegitcommit: 5756896ad87e28fac20f7981eaaeacfb0c098254
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2020
ms.locfileid: "49730166"
---
# <a name="learn-about-records-management-in-microsoft-365"></a>Weitere Informationen zur Datensatzverwaltung in Microsoft 365

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Organisationen aller Art benötigen eine Datensatzverwaltungslösung, um gesetzliche, rechtliche sowie unternehmenskritische Datensätze in ihren Unternehmensdaten zu verwalten. Die Datensatzverwaltung in Microsoft 365 unterstützt eine Organisation bei der Verwaltung ihrer gesetzlichen Verpflichtungen, bietet die Möglichkeit, die Einhaltung von Vorschriften nachzuweisen und erhöht die Effizienz bei der regelmäßigen Disposition von Elementen, die nicht mehr aufbewahrt werden müssen oder nicht mehr von Wert oder für Geschäftszwecke erforderlich sind.

Verwenden Sie die folgenden Funktionen zur Unterstützung Ihrer Datensatzverwaltungslösung in Microsoft 365:

- **Bezeichnen von Inhalt als Datensatz** Erstellen und Konfigurieren von Aufbewahrungsbezeichnungen zum Kennzeichen von Inhalten als [Datensatz](#records), die von Benutzern oder automatisch durch das Identifizieren vertraulicher Informationen, Stichwörter oder Inhaltstypen angewendet werden können.

- **Migrieren und verwalten Sie Ihre Aufbewahrungsanforderungen mit dem Dateiplan**. Mithilfe eines [Dateiplans](file-plan-manager.md) können Sie einen vorhandenen Aufbewahrungsplan in Microsoft 365 integrieren oder einen neuen Plan für verbesserte Verwaltungsfunktionen erstellen.

- **Konfigurieren Sie Einstellungen für Aufbewahrungs-und Löschvorgänge mit der Aufbewahrungsbezeichnung**. Konfigurieren Sie [Aufbewahrungsbezeichnungen](retention.md#retention-labels), bei denen die Aufbewahrungszeiträume und Aktionen auf zahlreichen Faktoren basieren, z. B. dem Datum der letzten Änderung oder dem Erstellungsdatum.

- **Starten Sie verschiedene Aufbewahrungszeiträume beim Auftreten eines Ereignisses** mit [ereignisbasierter Aufbewahrung](event-driven-retention.md).

- **Überprüfen und validieren Sie die Disposition** mit [Dispositionsüberprüfungen](disposition.md#disposition-reviews) und Nachweis der [Eintragslöschung](disposition.md#disposition-of-records).

- **Exportieren Sie Informationen zu allen Elementen**, die mit der [Exportoption](disposition.md#filter-and-export-the-views) verworfen wurden.

- **Legen Sie spezifische Berechtigungen für Datensatzverwalterfunktionen in Ihrer Organisation fest**, um [über den richtigen Zugriff zu verfügen](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

Mit diesen Funktionen können Sie die Aufbewahrungspläne Ihrer Organisation und die Anforderungen in eine Lösung für die Datensatzverwaltung integrieren, mit der Aufbewahrung, Deklaration von Datensätzen und Disposition zur Unterstützung des gesamten Inhaltslebenszyklus verwaltet werden.

Zusätzlich zur Onlinedokumentation können Sie sich bei Bedarf die [Webinaraufzeichnung](https://aka.ms/MIPC/Video-RecordsManagementWebinar) für die Datensatzverwaltung anhören und das zugehörige [Deck mit häufig gestellten Fragen](https://aka.ms/MIPC/Blog-RecordsManagementWebinar) herunterladen.

## <a name="records"></a>Datensätze

Wenn Inhalt zum Datensatz erklärt wird:

- Die Elemente werden hinsichtlich der [zulässigen oder blockierten Aktionen](#compare-restrictions-for-what-actions-are-allowed-or-blocked) eingeschränkt.

- Andere Aktivitäten in Verbindung mit dem Element werden protokolliert.

- Sie haben einen Verfügungsnachweis, wenn die Elemente am Ende ihrer Aufbewahrungsfrist gelöscht werden.

Sie verwenden [Aufbewahrungsbezeichnungen](retention.md#retention-labels), um Inhalte als **Datensatz** oder **regulatorischen Datensatz** zu kennzeichnen. Der Unterschied zwischen diesen beiden wird im nächsten Abschnitt erläutert. Sie können diese Bezeichnungen entweder veröffentlichen, so dass Benutzer und Administratoren sie manuell auf Inhalte anwenden können, oder Sie können diese Labels automatisch auf Inhalte anwenden, die Sie als Datensatz oder regulatorischen Datensatz markieren möchten.

Durch die Verwendung von Aufbewahrungsbezeichungen zur Deklaration von Aufzeichnungen können Sie eine einheitliche und konsistente Strategie für die Verwaltung von Datensätzen in Ihrer Microsoft 365-Umgebung implementieren.

### <a name="compare-restrictions-for-what-actions-are-allowed-or-blocked"></a>Vergleichen Sie Einschränkungen dazu, welche Aktionen erlaubt oder blockiert sind.

Verwenden Sie die folgende Tabelle, um zu ermitteln, welche inhaltlichen Einschränkungen sich aus der Anwendung einer Standard-Aufbewahrungsbezeichnung und von Aufbewahrungsbezeichnungen ergeben, die den Inhalt als Datensatz oder regulatorischen Datensatz kennzeichnen. 

Eine Standard-Aufbewahrungsbezeichnung verfügt über Aufbewahrungseinstellungen und -aktionen, kennzeichnet den Inhalt jedoch nicht als Datensatz oder alsregulatorischen Datensatz.

>[!NOTE] 
> Der Vollständigkeit halber enthält die Tabelle Spalten für einen gesperrten und entsperrten Datensatz, die für SharePoint und OneDrive gelten, jedoch nicht für Exchange. Die Möglichkeit zum Sperren und Entsperren eines Datensatzes verwendet die [Datensatzversionsverwaltung](record-versioning.md), die für Exchange-Elemente nicht unterstützt wird. Für alle Exchange-Elemente, die als Datensatz markiert sind, ist das Verhalten der Spalte **Datensatz gesperrt** und der Spalte **Datensatz entsperrt** nicht relevant.


|Aktion| Aufbewahrungsbezeichnung |Datensatz – gesperrt| Datensatz – entsperrt| Regulatorischer Datensatz |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Inhalt bearbeiten|Zulässig | **Gesperrt** | Allowed | **Gesperrt**|
|Bearbeiten Sie Eigenschaften, einschließlich Umbenennen|Allowed |Zulässig | Zulässig| **Gesperrt**|
|Löschen|Zulässig <sup>1</sup> |**Gesperrt** |**Gesperrt**| **Gesperrt**|
|Kopie|Zulässig |Allowed | Zulässig| Zulässig|
|Innerhalb eines Containers bewegen<sup>2</sup>|Zulässig |Zulässig | Allowed| Zulässig|
|Über Container hinweg bewegen <sup>2</sup>|Zulässig |Zulässig, wenn nie entsperrt | Zulässig| **Gesperrt**|
|Öffnen/Lesen|Zulässig |Zulässig | Zulässig| Allowed|
|Ändern der Bezeichnung|Zulässig |Zulässig – nur Container-Administrator | Zulässig – nur Container-Administrator| **Gesperrt**
|Bezeichnung entfernen|Zulässig |Zulässig – nur Container-Administrator | Zulässig – nur Container-Administrator| **Gesperrt**

Fußnoten:

<sup>1</sup> Unterstützt von OneDrive und Exchange durch Aufbewahren einer Kopie an einem gesicherten Ort, jedoch blockiert von SharePoint.

Nachricht, die ein Benutzer sieht, wenn er versucht, ein beschriftetes Dokument in SharePoint zu löschen:

![Nachricht, dass das Element nicht aus SharePoint gelöscht wurde](../media/d0020726-1593-4a96-b07c-89b275e75c49.png)

<sup>2</sup> Zu den Containern gehören SharePoint-Dokumentbibliotheken und Exchange-Postfächer.

>[!IMPORTANT] 
> Der wichtigste Unterschied für einen regulatorischen Datensatz besteht darin, dass nach der Anwendung auf den Inhalt niemand, nicht einmal ein globaler Administrator, die Bezeichnung entfernen kann. 
>
> Darüber hinaus gelten für Aufbewahrungsbezeichnungen, die für regulatorische Datensätze konfiguriert sind, die folgenden administrativen Einschränkungen:
> - Die Aufbewahrungsfrist kann nach dem Speichern der Bezeichnung nicht verkürzt, sondern nur verlängert werden.
> - Diese Bezeichnungen werden nicht durch Autobezeichnungsrichtlinien unterstützt und müssen mit Hilfe von [Richtlinien für Aufbewahrungsbezeichnungen](create-apply-retention-labels.md) angewendet werden. 
> 
> Vergewissern Sie sich aufgrund dieser irreversiblen Aktionen, dass Sie wirklich regulatorische Datensätze verwenden müssen, bevor Sie diese Option für Ihre Aufbewahrungsbezeichnungen wählen. Um eine versehentliche Konfiguration zu verhindern, ist diese Option nicht standardmäßig verfügbar, sondern muss zunächst mithilfe von PowerShell aktiviert werden. Anweisungen sind in [Deklarieren von Datensätzen unter Verwendung von Aufbewahrungsbezeichnungen](declare-records.md) enthalten.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Siehe [Erste Schritte mit der Datensatzverwaltung](get-started-with-records-management.md).

Mehr zu Inhalte als Datensatz markieren finden Sie unter [Datensätze mithilfe von Aufbewahrungsbezeichnungen deklarieren](declare-records.md).
