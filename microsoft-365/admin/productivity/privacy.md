---
title: Microsoft Productivity Score – Datenschutz
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Wie Datenschutz mit dem Produktivitäts Ergebnis geschützt wird.
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604326"
---
# <a name="privacy-controls-for-productivity-score"></a>Datenschutz-Steuerelemente für Produktivitäts Bewertung

Die Produktivitäts Bewertung bietet Einblicke in die digitale Transformationsreise Ihrer Organisation durch die Verwendung von Microsoft 365 und die damit unterstützten Technologie-Erlebnisse.  Die Bewertung Ihrer Organisation reflektiert Personen-und Technologie Erfahrungs Messungen und kann mit Benchmarks von Organisationen vergleichbar mit Ihnen verglichen werden. Weitere Informationen finden Sie in der [Übersicht über die Produktivitäts Bewertung](productivity-score.md).

Ihr Datenschutz ist für Microsoft wichtig. Informationen zum Schutz Ihrer Privatsphäre finden Sie in [der Datenschutzerklärung von Microsoft](https://privacy.microsoft.com/privacystatement). Das Produktivitäts Ergebnis ermöglicht Ihnen als IT-Administrator Ihrer Organisation den Zugriff auf Datenschutzeinstellungen, um sicherzustellen, dass alle von Ihnen eingegebenen Produktivitäts Bewertungsinformationen für Aktionen aktiviert werden, ohne dass die Vertrauensstellung Ihrer Organisation in Microsoft beeinträchtigt wird.

Im Bereich "People Experiences" sind Metriken nur auf Organisationsebene verfügbar. In diesem Bereich wird die Verwendung von Microsoft 365 untersucht, indem die Kategorien der Inhalts Zusammenarbeit, Mobilität, Besprechungen, Teamarbeit und Kommunikation betrachtet werden. Wir ermöglichen Ihnen verschiedene Ebenen von Steuerelementen, die Sie bei der Erfüllung ihrer internen Anforderungen an die Datenschutzrichtlinie unterstützen.
Die Steuerelemente geben Ihnen Folgendes:

- Flexible Administratorrollen, um zu steuern, wer die Informationen in der Produktivitäts Bewertung sehen kann.
- Die Möglichkeit, den Bereich "Personen Erlebnisse" zu deaktivieren.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexible Administratorrollen, um zu steuern, wer die Informationen im Produktivitäts Ergebnis sehen kann

Um das gesamte Produktivitäts Ergebnis anzuzeigen, müssen Sie eine der folgenden Administratorrollen sein:

- Globaler Administrator
- Exchange-Administrator
- SharePoint-Administrator
- Skype for Business-Administrator
- Microsoft Teams-Administrator
- Globaler Leser
- Berichteleser
- Verwendungs Zusammenfassungsberichte-Leser

Zuweisen der Leserrolle "Berichte" oder "Verwendungs Zusammenfassungsberichte" für alle Benutzer, die für Änderungsverwaltung und-Annahme zuständig sind, jedoch nicht unbedingt als IT-Administrator. Durch diese Rolle erhalten Sie Zugriff auf die vollständige Produktivitäts BEWERTUNGSUMGEBUNG im Microsoft 365 Admin Center.

Die Leserrolle Verwendungs Zusammenfassungsberichte muss über PowerShell-Cmdlets zugewiesen werden, bis Sie später in 2020 vom Microsoft 365 Admin Center zugeordnet wird.

So weisen Sie die Leserrolle "Verwendungs Zusammenfassungsberichte" mit PowerShell zu:

- Führen Sie die folgende PowerShell aus:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>Möglichkeit zum Deaktivieren von Personen Erfahrungen

Sie können auch den Bereich mit den Personen Erlebnissen der Produktivitäts Bewertung deaktivieren. Wenn Sie sich entschließen, kann niemand aus Ihrer Organisation diese Metriken anzeigen, und Ihre Organisation wird aus allen Berechnungen entfernt, die Kommunikation, Besprechungen, Zusammenarbeit, Inhalts Zusammenarbeit und Mobilität beinhalten. Sie müssen ein globaler Administrator sein, um Ihre Organisation aus den Berichten über Personen Erfahrung zu entscheiden.

So wählen Sie Put:

1. Wechseln Sie im Admin Center zu den **Einstellungen** der   >   **org**-Einstellungen, und wählen Sie unter **Dienste** die Option **Berichte** aus.
2. Deaktivieren Sie das Kontrollkästchen zulassen, dass  **Microsoft 365-Nutzungsdaten für personenbezogene Einblicke verwendet werden**. Wenn Sie wissen möchten, wie Sie die Einstellungen für die Datenfreigabe für die Endpunktanalyse im InTune-Konfigurations-Manager ändern, wählen Sie **Weitere Informationen** aus.
3. Wählen Sie  **Speichern** aus.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Seite &quot;org-Einstellungen&quot;, auf der Sie sich von Personen Erfahrungen abmelden können.":::