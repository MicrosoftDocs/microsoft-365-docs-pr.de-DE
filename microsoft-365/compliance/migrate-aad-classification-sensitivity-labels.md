---
title: Azure Active Directory Klassifizierungs-und Sensitivitäts Bezeichnungen für Microsoft 365-Gruppen
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
description: In diesem Artikel werden die klassischen Azure Active Directory Klassifizierungs-und Sensitivitäts Bezeichnungen erläutert.
ms.openlocfilehash: 38a3dbe727f3d0759d427944016ae98440f2686f
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308172"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Azure Active Directory Klassifizierungs-und Sensitivitäts Bezeichnungen für Microsoft 365-Gruppen

In diesem Artikel werden die klassischen Azure Active Directory Klassifizierungs-und Sensitivitäts Bezeichnungen erläutert.

Vertraulichkeits Bezeichnungen werden von [diesen Diensten](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#support-for-the-sensitivity-labels)unterstützt.

Ausführliche Informationen zu Sensitivitäts Bezeichnungen finden Sie unter [erfahren Sie mehr über Sensitivitäts Bezeichnungen](sensitivity-labels.md).

Weitere Informationen zu Sensitivitäts Bezeichnungen und deren Verhalten für Websites und Microsoft 365-Gruppen finden Sie unter [use Sensitivity Labels to Protect Content in Microsoft Teams, Microsoft 365 Groups und SharePoint Sites](sensitivity-labels-teams-groups-sites.md).

Lesen Sie die folgenden Szenarien für bewährte Methoden beim Migrieren von der klassischen Aad-Klassifizierung zu den Sensitivitäts Bezeichnungen.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Szenario 1: Mandant nie verwendet klassischen Aad Klassifizierungen oder Sensitivitäts Bezeichnungen für Dokumente und e-Mails

- Der mandantenadministrator aktiviert Vertraulichkeits Bezeichnungen für Gruppen, indem das Mandanten Kennzeichen "EnableMIPLabels" über das Aad PowerShell-Cmdlet auf true festgelegt wird.
- Der mandantenadministrator erstellt die Sensitivitäts Bezeichnungen im [Microsoft 365 Compliance Center](https://compliance.microsoft.com).
    - Der mandantenadministrator kann Datei-und e-Mail-bezogene Aktionen wie Verschlüsselung und Wasserzeichen auswählen.
    - Mandantenadministrator kann Microsoft 365-Gruppen auswählen und Website bezogene Aktionen für die Sensitivitäts Bezeichnungen SharePoint Online.
- Der mandantenadministrator veröffentlicht die Richtlinie.
- **Kompatible Arbeitslasten** zeigen Sensitivitäts Bezeichnungen an. Verwenden Sie die Sensitivitäts Bezeichnungen zum Erstellen von Gruppen. Kompatible Arbeitslasten sind die Dienste, die Vertraulichkeits Bezeichnungen unterstützen.
- **Nicht kompatible Arbeitsauslastungen** sind die Dienste, die noch keine Vertraulichkeits Bezeichnungen unterstützen. Gruppen können erstellt werden, Sie können jedoch nicht über nicht kompatible Arbeitsauslastungen der Sensitivitäts Bezeichnung zugeordnet werden. Um solche Gruppen mit Sensitivitäts Bezeichnungen zu verknüpfen, können mandantenadministratoren PowerShell-Cmdlets ausführen.

Tabelle 1. Verhalten kompatibler und nicht kompatibler Arbeitsauslastungen – erstellen, bearbeiten oder Löschen von Gruppen

|Arbeitslast|Welche Beschriftungsliste wird dem Benutzer im Gruppenfenster angezeigt?|Neue Gruppe erstellen |Gruppe bearbeiten |Gruppe löschen |
|:-------|:-------|:--------|:--------|:--------|   
|Kompatibel   |Vertraulichkeits Bezeichnungen. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |
|Nicht kompatibel |Keine Sensitivitäts Bezeichnungen sichtbar. |Benutzer kann eine Gruppe erstellen, ohne Vertraulichkeits Bezeichnung auszuwählen. <br><br> Beachten Sie, dass der Administrator Cmdlets ausführen kann, um Sensitivitäts Bezeichnungen im Hintergrund anzuwenden. |**Fall 1**: keine Sensitivitäts Bezeichnung zuvor ausgewählt. Benutzer kann eine Gruppe bearbeiten.<br><br> **Fall 2**: Sensitivitäts Bezeichnung, die zuvor im Hintergrund mithilfe von Cmdlet angewendet wurde. Benutzer kann eine Gruppe erfolgreich bearbeiten, ohne den Fall, in dem der Benutzer eine ungültige Kombination der Datenschutzeinstellung in Bezug auf die Bezeichnung auswählt. |Keine Änderungen im Verhalten.|

> [!NOTE]
> Im Fall von Outlook-Desktop-Client (Win 32), nachdem Administrator die Vertraulichkeits Bezeichnungen auf Ihrem Mandanten aktiviert und sich der Benutzer in einer älteren Version des Outlook-Desktop Clients (Win 32) befindet:
> - Benutzer sieht Sensitivitäts Bezeichnungen werden in der älteren Version des Outlook-Desktop Clients angezeigt.
> - Wenn der Benutzer jedoch eine Gruppe bearbeitet und die Gruppe mit einer Vertraulichkeits Bezeichnung speichert, wird die ausgewählte Datenschutzeinstellung durch die Datenschutzeinstellung der angewendeten Vertraulichkeits Bezeichnung außer Kraft gesetzt.
> Es wird empfohlen, dass Ihre Benutzer auf einer alten Version des Outlook-Clients auf die neuere Version aktualisieren.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Szenario 2: der Mandant verwendet bereits klassische Aad- [Klassifikationen](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Fall A: Mandant verwendet keine Sensitivitäts Bezeichnungen für Dokumente und e-Mails.

1. Im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)wird empfohlen, Vertraulichkeits Bezeichnungen mit dem gleichen Namen wie die vorhandenen klassischen Azure AD Beschriftungen zu erstellen.
2. Verwenden Sie das PowerShell-Cmdlet, um diese Sensitivitäts Bezeichnungen auf vorhandene Microsoft 365-Gruppen und SharePoint-Websites mithilfe der Namenszuordnung anzuwenden.
3. Der Administrator kann die klassischen Azure AD Bezeichnungen löschen:
    - Kompatible Arbeitsauslastungen zeigen diese Vertraulichkeits Bezeichnungen und Gruppen werden mit Ihnen erstellt.
    - Nicht kompatible Arbeitsauslastungen funktionieren beim Erstellen von Gruppen, aber keine Vertraulichkeits Bezeichnung ist Ihnen zugeordnet.
4. Administratoren können PowerShell-Cmdlets ausführen, um Vertraulichkeits Bezeichnungen auf diese Gruppen ohne Bezeichnungen anzuwenden.
    - Alternativ kann ein Administrator auswählen, dass die klassischen Azure AD Bezeichnungen beibehalten werden:
        - Kompatible Arbeitsauslastungen zeigen diese Sensitivitäts Bezeichnungen an, und Gruppen werden mit Ihnen erstellt. Kompatible Arbeitslasten sind die Dienste, die Vertraulichkeits Bezeichnungen unterstützen.
        - Nicht kompatible Arbeitsauslastungen funktionieren beim Erstellen von Gruppen und beim Anzeigen von klassischen Azure AD Bezeichnungen. Diese klassischen Azure AD Bezeichnungen sind an diese Gruppen angehängt, die mit nicht kompatiblen Arbeitsauslastungen erstellt wurden.
5. Es wird dringend empfohlen, dass Administratoren PowerShell-Cmdlets ausführen, um Sensitivitäts Bezeichnungen auf diese Gruppen mit klassischen Azure AD Bezeichnungen anzuwenden.

Tabelle 2. Verhalten kompatibler und nicht kompatibler Arbeitsauslastungen – erstellen, bearbeiten oder Löschen von Gruppen

|Arbeitslast|Welche Beschriftungsliste wird dem Benutzer im Gruppenfenster angezeigt?|Neue Gruppe erstellen |Gruppe bearbeiten |Gruppe löschen |
|:-------|:-------|:--------|:--------|:--------|   
|Kompatibel   |Vertraulichkeits Bezeichnungen. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |
|Nicht kompatibel |Alte klassische Aad-Bezeichnungen. |Benutzer kann eine Gruppe mit klassischer Azure AD Bezeichnung erstellen ausgewählt. <br><br>Beachten Sie, dass der Administrator Cmdlets ausführen kann, um Sensitivitäts Bezeichnungen im Hintergrund anzuwenden. |**Fall 1**: keine Sensitivitäts Bezeichnung zuvor ausgewählt. Benutzer kann eine Gruppe bearbeiten.<br><br> **Fall 2**: klassische Aad-Bezeichnungen, die zuvor ausgewählt wurden. Benutzer kann eine Gruppe bearbeiten.<br><br> **Fall 3**: Vertraulichkeits Bezeichnung, die zuvor im Hintergrund mithilfe von Cmdlet angewendet wurde. Benutzer sollte in der Lage sein, eine Gruppe zu bearbeiten, ohne einen Fall, bei dem der Benutzer eine ungültige Kombination der Datenschutzeinstellung in Bezug auf die Bezeichnung auswählt. |Benutzer kann eine Gruppe löschen. |

> [!NOTE]
> Im Fall von Outlook-Desktop-Client (Win 32), nachdem Administrator die Vertraulichkeits Bezeichnungen auf Ihrem Mandanten aktiviert und sich der Benutzer in einer älteren Version des Outlook-Desktop Clients (Win 32) befindet:
> - Benutzer sieht Sensitivitäts Bezeichnungen werden in der älteren Version des Outlook-Desktop Clients angezeigt.
> - Wenn der Benutzer jedoch eine Gruppe bearbeitet und die Gruppe mit einer Vertraulichkeits Bezeichnung speichert, wird die ausgewählte Datenschutzeinstellung durch die Datenschutzeinstellung der angewendeten Vertraulichkeits Bezeichnung außer Kraft gesetzt.
> Es wird empfohlen, dass Ihre Benutzer auf einer alten Version des Outlook-Clients auf die neuere Version aktualisieren.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Fall B: Mandant verwendet Sensitivitäts Bezeichnungen für Dokumente und e-Mails

1. Sobald der Administrator das Feature für die Vertraulichkeits Kennzeichnung auf dem Mandanten aktiviert, indem das Mandanten Kennzeichen "EnableMIPLabels" auf true festgelegt wird, werden die Dialogfelder Dokument-und e-Mail-Empfindlichkeits Bezeichnungen in Gruppen/Standort/Team erstellen und bearbeiten angezeigt.
2. Ein Administrator kann dieselben Dokument-und e-Mail-Vertraulichkeits Bezeichnungen verwenden, um den Datenschutz und den Zugriff durch externe Benutzer in der Gruppe/dem Standort/Team durch die Angabe verwandter Gruppeneinstellungen zu erzwingen:
    1. Wählen Sie im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)die Registerkarte **Websites und Gruppen** aus.
    2. Bearbeiten einer Bezeichnung für ein Dokument oder eine e-Mail-Vertraulichkeit.

## <a name="sample-script"></a>Beispielskript

Ein Beispielskript zum Migrieren von Gruppen mit klassischen Aad-Bezeichnungen zu Sensitivitäts Bezeichnungen finden Sie unter [klassische Azure Ad Gruppen Klassifizierung](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).

