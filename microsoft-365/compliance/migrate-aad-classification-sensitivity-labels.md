---
title: Azure Active Directory-Klassifizierung und Vertraulichkeitsbezeichnungen für Microsoft 365-Gruppen
ms.reviewer: vijagan
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
f1.keywords: NOCSH
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
description: In diesem Artikel werden die klassische Azure Active Directory-Klassifizierung und Vertraulichkeitsbezeichnungen behandelt.
ms.openlocfilehash: 07bc09afb3e490961a8cc5a88857ec49dd962856
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51221750"
---
# <a name="azure-active-directory-classification-and-sensitivity-labels-for-microsoft-365-groups"></a>Azure Active Directory-Klassifizierung und Vertraulichkeitsbezeichnungen für Microsoft 365-Gruppen

In diesem Artikel werden die klassische Azure Active Directory-Klassifizierung und Vertraulichkeitsbezeichnungen behandelt.

Vertraulichkeitsbezeichnungen werden von [diesen Diensten unterstützt.](./sensitivity-labels-teams-groups-sites.md)

Vollständige Informationen zu Vertraulichkeitsbezeichnungen finden Sie [unter Informationen zu Vertraulichkeitsbezeichnungen](sensitivity-labels.md).

Weitere Informationen zu Vertraulichkeitsbezeichnungen und deren Verhalten für Websites und Microsoft 365-Gruppen finden Sie unter Verwenden von Vertraulichkeitsbezeichnungen zum Schutz von [Inhalten in Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites.](sensitivity-labels-teams-groups-sites.md)

In den folgenden Szenarien finden Sie bewährte Methoden beim Migrieren von der klassischen AAD-Klassifizierung zu den Vertraulichkeitsbezeichnungen.

## <a name="scenario-1-tenant-never-used-classic-aad-classifications-or-sensitivity-labels-for-documents-and-emails"></a>Szenario 1: Der Mandant hat niemals klassische AAD-Klassifizierungen oder Vertraulichkeitsbezeichnungen für Dokumente und E-Mails verwendet.

- Mandantenadministrator aktiviert Vertraulichkeitsbezeichnungen für Gruppen, indem das Mandantenkennzeichen "EnableMIPLabels" über das AAD powershell-Cmdlet auf true festlegen.
- Der Mandantenadministrator erstellt die Vertraulichkeitsbezeichnungen im [Microsoft 365 Compliance Center.](https://compliance.microsoft.com)
    - Mandantenadministratoren können Datei- und E-Mail-bezogene Aktionen wie Verschlüsselung und Wasserzeichen auswählen.
    - Mandantenadministratoren können Microsoft 365-Gruppen und SharePoint Online-websitebezogene Aktionen für die Vertraulichkeitsbezeichnungen auswählen.
- Der Mandantenadministrator veröffentlicht die Richtlinie.
- **Kompatible Arbeitsauslastungen** zeigen Vertraulichkeitsbezeichnungen an. Verwenden Sie die Vertraulichkeitsbezeichnungen, um Gruppen zu erstellen. Kompatible Workloads sind die Dienste, die Vertraulichkeitsbezeichnungen unterstützen.
- **Nicht kompatible Workloads sind** die Dienste, die vertraulichkeitsbezeichnungen noch nicht unterstützen. Gruppen können jedoch nicht über nicht kompatible Arbeitsauslastungen der Vertraulichkeitsbezeichnung zugeordnet werden. Um solche Gruppen Vertraulichkeitsbezeichnungen zuzuordnen, können Mandantenadministratoren PowerShell-Cmdlets ausführen.

Tabelle 1. Verhalten kompatibler und nicht kompatibler Arbeitsauslastungen – Erstellen, Bearbeiten oder Löschen von Gruppen

|Arbeitslast|Welche Bezeichnungsliste wird benutzern im Gruppenfenster angezeigt?|Erstellen einer neuen Gruppe |Gruppe bearbeiten |Gruppe löschen |
|:-------|:-------|:--------|:--------|:--------|   
|Kompatibel   |Vertraulichkeitsbezeichnungen. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |
|Nicht kompatibel |Keine Vertraulichkeitsbezeichnungen sichtbar. |Der Benutzer kann eine Gruppe erstellen, ohne Vertraulichkeitsbezeichnungen auswählen zu müssen. <br><br> Hinweis: Der Administrator kann Cmdlets ausführen, um Vertraulichkeitsbezeichnungen im Hintergrund anzuwenden. |**Fall 1**: Keine zuvor ausgewählte Vertraulichkeitsbezeichnung. Der Benutzer kann eine Gruppe bearbeiten.<br><br> **Fall 2:** Vertraulichkeitsbezeichnung, die zuvor im Hintergrund mithilfe des Cmdlets angewendet wurde. Der Benutzer kann eine Gruppe erfolgreich bearbeiten, mit Ausnahme des Falls, in dem der Benutzer eine ungültige Kombination von Datenschutzeinstellungen im Hinblick auf die Bezeichnung auswählt. |Keine Änderungen im Verhalten.|

> [!NOTE]
> Im Fall des Outlook-Desktopclients (Win 32), nachdem der Administrator Vertraulichkeitsbezeichnungen für seinen Mandanten aktiviert hat und sich der Benutzer auf einer älteren Version des Outlook-Desktopclients befindet (Win 32):
>
> - Dem Benutzer werden Vertraulichkeitsbezeichnungen in der älteren Version des Outlook-Desktopclients angezeigt.
> - Wenn der Benutzer jedoch eine Gruppe bearbeitet und die Gruppe mit einer Vertraulichkeitsbezeichnung speichert, wird die ausgewählte Datenschutzeinstellung durch die Datenschutzeinstellung der angewendeten Vertraulichkeitsbezeichnung überschrieben.
>
> Es wird empfohlen, dass Ihre Benutzer auf einer alten Version des Outlook-Clients ein Upgrade auf die neuere Version durchführen.

## <a name="scenario-2-tenant-is-already-using-classic-aad-classifications"></a>Szenario 2: Mandant verwendet bereits klassische [AAD-Klassifizierungen](../enterprise/manage-microsoft-365-groups-with-powershell.md)

### <a name="case-a-tenant-never-used-sensitivity-labels-for-documents-and-emails"></a>Fall A: Der Mandant hat nieMals Vertraulichkeitsbezeichnungen für Dokumente und E-Mails verwendet.

1. Im [Microsoft 365 Compliance Center](https://compliance.microsoft.com)wird empfohlen, Vertraulichkeitsbezeichnungen mit demselben Namen wie die vorhandenen klassischen Azure AD-Bezeichnungen zu erstellen.
2. Verwenden Sie das PowerShell-Cmdlet, um diese Vertraulichkeitsbezeichnungen mithilfe der Namenszuordnung auf vorhandene Microsoft 365-Gruppen und SharePoint-Websites anzuwenden.
3. Der Administrator kann die klassischen Azure AD-Bezeichnungen löschen:
    - Kompatible Arbeitsauslastungen zeigen diese Vertraulichkeitsbezeichnungen und Gruppen an, die mit ihnen erstellt werden.
    - Nicht kompatible Arbeitsauslastungen funktionieren beim Erstellen von Gruppen, es ist jedoch keine Vertraulichkeitsbezeichnung an sie angefügt.
4. Administratoren können PowerShell-Cmdlets ausführen, um Vertraulichkeitsbezeichnungen auf diese Gruppen ohne Bezeichnungen anzuwenden.
    - Alternativ kann ein Administrator die klassischen Azure AD-Bezeichnungen behalten:
        - Kompatible Arbeitsauslastungen zeigen diese Vertraulichkeitsbezeichnungen an, und Gruppen werden mit diesen erstellt. Kompatible Workloads sind die Dienste, die Vertraulichkeitsbezeichnungen unterstützen.
        - Nicht kompatible Arbeitsauslastungen funktionieren beim Erstellen von Gruppen und zeigen klassische Azure AD-Bezeichnungen an. Diese klassischen Azure AD-Bezeichnungen werden diesen Gruppen zugeordnet, die mit nicht kompatiblen Workloads erstellt wurden.
5. Es wird dringend empfohlen, dass Administratoren PowerShell-Cmdlets ausführen, um Vertraulichkeitsbezeichnungen auf diese Gruppen mit klassischen Azure AD-Bezeichnungen anzuwenden.

Tabelle 2. Verhalten kompatibler und nicht kompatibler Arbeitsauslastungen – Erstellen, Bearbeiten oder Löschen von Gruppen

|Arbeitslast|Welche Bezeichnungsliste wird benutzern im Gruppenfenster angezeigt?|Erstellen einer neuen Gruppe |Gruppe bearbeiten |Gruppe löschen |
|:-------|:-------|:--------|:--------|:--------|   
|Kompatibel   |Vertraulichkeitsbezeichnungen. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |Keine Änderungen im Verhalten. |
|Nicht kompatibel |Alte klassische AAD-Bezeichnungen. |Benutzer können eine Gruppe mit ausgewählter klassischer Azure AD-Bezeichnung erstellen. <br><br>Hinweis: Der Administrator kann Cmdlets ausführen, um Vertraulichkeitsbezeichnungen im Hintergrund anzuwenden. |**Fall 1**: Keine zuvor ausgewählte Vertraulichkeitsbezeichnung. Der Benutzer kann eine Gruppe bearbeiten.<br><br> **Fall 2:** Klassische AAD-Bezeichnungen, die zuvor ausgewählt wurden. Der Benutzer kann eine Gruppe bearbeiten.<br><br> **Fall 3:** Vertraulichkeitsbezeichnung, die zuvor mithilfe des Cmdlets im Hintergrund angewendet wurde. Der Benutzer sollte in der Lage sein, eine Gruppe zu bearbeiten, mit Ausnahme eines Falls, in dem der Benutzer eine ungültige Kombination von Datenschutzeinstellungen im Hinblick auf die Bezeichnung auswählt. |Der Benutzer kann eine Gruppe löschen. |

> [!NOTE]
> Im Fall des Outlook-Desktopclients (Win 32), nachdem der Administrator Vertraulichkeitsbezeichnungen für seinen Mandanten aktiviert hat und sich der Benutzer auf einer älteren Version des Outlook-Desktopclients befindet (Win 32):
>
> - Dem Benutzer werden Vertraulichkeitsbezeichnungen in der älteren Version des Outlook-Desktopclients angezeigt.
> - Wenn der Benutzer jedoch eine Gruppe bearbeitet und die Gruppe mit einer Vertraulichkeitsbezeichnung speichert, wird die ausgewählte Datenschutzeinstellung durch die Datenschutzeinstellung der angewendeten Vertraulichkeitsbezeichnung überschrieben.
>
> Es wird empfohlen, dass Ihre Benutzer auf einer alten Version des Outlook-Clients ein Upgrade auf die neuere Version durchführen.

### <a name="case-b-tenant-used-sensitivity-labels-for-documents-and-emails"></a>Fall B: Mandant verwendete Vertraulichkeitsbezeichnungen für Dokumente und E-Mails

1. Sobald der Administrator das Feature für Vertraulichkeitsbezeichnungen für den Mandanten aktiviert, indem das Mandantenkennzeichen "EnableMIPLabels" auf true festgelegt wird, werden die Dokument- und E-Mail-Vertraulichkeitsbezeichnungen in den Dialogfeldern zum Erstellen und Bearbeiten von Gruppen/Website/Team angezeigt.
2. Ein Administrator kann dieselben Dokument- und E-Mail-Vertraulichkeitsbezeichnungen verwenden, um Datenschutz und externen Benutzerzugriff auf die Gruppe/Website/das Team durch Angeben verwandter Gruppeneinstellungen zu erzwingen:
    1. Wählen Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)die Registerkarte Websites und **Gruppen** aus.
    2. Bearbeiten sie ein Dokument oder eine E-Mail-Vertraulichkeitsbezeichnung.

## <a name="sample-script"></a>Beispielskript

Ein Beispielskript zum Migrieren von Gruppen mit klassischen AAD-Bezeichnungen zu Vertraulichkeitsbezeichnungen finden Sie unter [Classic Azure AD group classification](./sensitivity-labels-teams-groups-sites.md#classic-azure-ad-group-classification).