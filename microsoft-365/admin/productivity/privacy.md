---
title: Microsoft Productivity Score – Datenschutz
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
description: Schutz des Datenschutzes mit dem Produktivitätsergebnis.
ms.openlocfilehash: 5b5997532ddcd1fdf43b4124f8e2d8183bb3d89e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579170"
---
# <a name="privacy-controls-for-productivity-score"></a>Datenschutzsteuerelemente für Produktivitätsergebnis

Die Produktivitätswertung bietet Einblicke in die digitale Transformationsreise Ihrer Organisation durch die Verwendung von Microsoft 365 und die Technologieerfahrungen, die sie unterstützen.  Die Bewertung Ihrer Organisation spiegelt Messungen der Benutzer- und Technologieerfahrung wider und kann mit Benchmarks von Organisationen vergleichbar mit Ihrer verglichen werden. Weitere Informationen finden Sie in der [Übersicht über die Produktivitätswertung.](productivity-score.md)

Ihr Datenschutz ist für Microsoft wichtig. Informationen zum Schutz Ihrer Privatsphäre finden Sie in [der Microsoft-Datenschutzbestimmungen](https://privacy.microsoft.com/privacystatement). Produktivitätsergebnis bietet Ihnen als IT-Administrator Ihrer Organisation Zugriff auf Datenschutzeinstellungen, um sicherzustellen, dass alle angezeigten Produktivitätsergebnisinformationen aktionensfähig sind, ohne das Vertrauen Ihrer Organisation in Microsoft zu beeinträchtigen.

Im Bereich "Personenerfahrungen" sind Metriken nur auf Organisatorischer Ebene verfügbar. In diesem Bereich wird die Microsoft 365 von Personen betrachtet, indem die Kategorien Zusammenarbeit, Mobilität, Besprechungen, Teamarbeit und Kommunikation betrachtet werden. Wir ermöglichen Ihnen mehrere Ebenen von Steuerelementen, um Ihnen bei der Erfüllung Ihrer internen Datenschutzrichtlinienanforderungen zu helfen.
Die Steuerelemente bieten Ihnen:

- Flexible Administratorrollen, um zu steuern, wer die Informationen in Produktivitätsergebnis sehen kann.
- Die Möglichkeit, den Bereich "Personenerfahrungen" abmelden.

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexible Administratorrollen zum Steuern, wer die Informationen im Produktivitätsergebnis sehen kann

Zum Anzeigen des gesamten Produktivitätsergebniss benötigen Sie eine der folgenden Administratorrollen:

- Globaler Administrator
- Exchange-Administrator
- SharePoint-Administrator
- Skype for Business-Administrator
- Microsoft Teams-Administrator
- Globaler Leser
- Berichteleser
- Leseberechtigter für Verwendungszusammenfassungsberichte

Weisen Sie den Leser für Berichte oder die Rolle Leser für Verwendungszusammenfassungen jedem zu, der für die Änderungsverwaltung und -einführung zuständig ist, aber nicht unbedingt einen IT-Administrator. Diese Rolle bietet ihnen Zugriff auf die vollständige Produktivitätsergebniserfahrung im Microsoft 365 Admin Center.

Die Rolle "Leser für Verwendungszusammenfassungsberichte" muss über PowerShell-Cmdlets zugewiesen werden, bis sie später im Microsoft 365 Admin Center zugewiesen werden kann.

So weisen Sie die Rolle "Leser für Verwendungszusammenfassungsberichte" mit PowerShell zu:

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


## <a name="capability-to-opt-out-of-people-experiences"></a>Möglichkeit zum Abmelden von Personenerfahrungen

Sie können auch den Bereich "Personenerfahrungen" der Produktivitätswertung abmelden. Wenn Sie sich abmelden, kann niemand aus Ihrer Organisation diese Metriken anzeigen, und Ihre Organisation wird aus allen Berechnungen entfernt, die Kommunikation, Besprechungen, Teamarbeit, Inhaltszusammenarbeit und Mobilität umfassen. Sie müssen ein globaler Administrator sein, um Ihre Organisation von den Berichten über Die Erfahrungen von Personen abmelden zu können.

So melden Sie sich ab:

1. Wechseln Sie im Admin Center zu **Einstellungen**   >   **Org Einstellungen** Productivity  >  **Score**.
2. Aktivieren Sie das Kontrollkästchen Allow **Microsoft 365 usage data to be used for people experiences insights**. Um zu verstehen, wie Sie Einstellungen für die Datenfreigabe für Endpoint Analytics im Intune-Konfigurations-Manager ändern, wählen Sie **Weitere Informationen aus.**
3. Wählen Sie **Speichern aus.**

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Seite &quot;Organisationseinstellungen&quot;, auf der Sie Benutzererfahrungen abmelden können.":::
