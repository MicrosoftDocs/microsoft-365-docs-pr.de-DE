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
ms.openlocfilehash: 4978039d99704c0658fe22f3725167ac31276dcd
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804747"
---
# <a name="privacy-controls-for-productivity-score"></a>Datenschutz-Steuerelemente für Produktivitäts Bewertung

Die Produktivitäts Bewertung unterstützt Organisationen beim Transformieren der Arbeit mit Metriken, mit denen Sie Personen und Technologie Erfahrungen Messen und verbessern können. Es hilft Ihnen, Einblick in die Funktionsweise Ihrer Organisation zu erhalten, und stellt Metriken bereit, mit denen Sie sich auf verbesserte Erfahrungen konzentrieren können.  Sie können die Metriken auch mit Aktionen verbinden, die Sie beim Aktualisieren von Qualifikationen und Systemen unterstützen, damit jeder seine besten Aufgaben ausführen kann. Die Bewertung spiegelt die Leistung Ihrer Organisation wider und ermöglicht Ihnen auch, Ihre Punktzahl mit anderen Organisationen wie Ihrem sicher zu vergleichen.  Weitere Informationen finden Sie unter Übersicht über die [Produktivitäts Bewertung](productivity-score.md).

Ihre Privatsphäre ist uns wichtig. Informationen zum Schutz Ihrer Privatsphäre finden Sie in [der Datenschutzerklärung von Microsoft](https://privacy.microsoft.com/privacystatement). Das Produktivitäts Ergebnis bietet wichtige Informationen darüber, wie Personen in ihren Organisationen mit Steuerelementen zusammenarbeiten, um sicherzustellen, dass die Informationen Action fähig sind, ohne dabei die von Ihnen in Microsoft gegebene Vertrauensstellung zu gefährden.

Im Bereich "People Experiences" stehen Metriken auf Organisationsebene zur Verfügung und enthalten alle Benutzer in Ihrem Microsoft 365-Mandanten. In diesem Bereich wird die Verwendung von Microsoft 365 untersucht, indem die Kategorien der Inhalts Zusammenarbeit, Mobilität, Besprechungen, Teamarbeit und Kommunikation betrachtet werden. Um Ihnen die Schulung und Sensibilisierung für die richtigen Personen zu erleichtern, die möglicherweise Unterstützung für unsere Produkte benötigen, haben wir Ihnen auch Informationen auf der individuellen Ebene bereitgestellt. Während wir diesen Grad an Transparenz bieten, ermöglichen wir Ihnen auch verschiedene Ebenen von Steuerelementen, die Sie bei der Erfüllung ihrer internen Anforderungen an die Datenschutzrichtlinie unterstützen.
Die folgenden Steuerelemente bieten Ihnen Folgendes:

- Flexible Administratorrollen, um zu steuern, wer die Informationen in der Produktivitäts Bewertung sehen kann.
- Die Möglichkeit, Metriken auf Benutzerebene zu deidentifizieren.
- Möglichkeit zum Deaktivieren von Personen Erfahrungen.
- Möglichkeit zum Deaktivieren des Bereichs "People Experiences"

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>Flexible Administratorrollen, um zu steuern, wer die Informationen im Produktivitäts Ergebnis sehen kann

Um das gesamte Produktivitäts Ergebnis anzuzeigen, einschließlich Metriken auf Mandantenebene und benutzerspezifische Details, sollte ihre Rolle eine der folgenden Administratorrollen sein:

- Globaler Administrator
- Exchange-Administratoren
- SharePoint-Administrator
- Skype for Business-Administrator
- Teams Administrator
- Globaler Leser
- Berichtleseberechtigter

Weisen Sie jeder Person, die für die Änderungsverwaltung und-Einführung zuständig ist, die Rolle "berichtsleser" zu. Diese Rolle ermöglicht Ihnen den Zugriff auf die vollständige Benutzeroberfläche, einschließlich Metriken auf Mandantenebene und Details auf einzelnen Ebenen.

Personen Erfahrungsbericht enthält benutzerspezifische Aktivitätsdetails für jede Kategorie-Detailseite. Weisen Sie eine benutzerdefinierte Rolle mit dem Namen Verwendungs Zusammenfassungsberichte Leser zu (verfügbar ab 29. Oktober 2020), um den Zugriff auf die aggregierten Metriken der Personen Erfahrungen zu ermöglichen. Diese Rolle muss über PowerShell-Cmdlets zugewiesen werden, bis Sie vom Microsoft Admin Center auf 11/15/2020 zugeordnet werden kann.

So weisen Sie die Leserrolle "Verwendungs Zusammenfassungsberichte" mit PowerShell zu:

- Führen Sie die folgende PowerShell aus:

```powershell
Connect-AzureAD
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="Seite &quot;Kommunikation&quot; in Produktivitäts Berichten.":::

## <a name="de-identification-of-user-level-metrics"></a>Aufheben der Identifizierung von Metriken auf Benutzerebene

Damit die Daten, die für alle Berichte erfasst werden, anonym sind, müssen Sie ein globaler Administrator sein. Mit dieser Aktion werden identifizierbare Informationen wie Benutzer-, Gruppen-und Websitenamen in allen Berichten (einschließlich Produktivitäts Bewertung und Microsoft 365-Nutzung) ausgeblendet.

1. Wechseln Sie im Admin Center zu den **Einstellungen** der   >   **org** -Einstellungen, und wählen Sie unter **Dienste** die Registerkarte **Berichte** aus.
2. Wählen Sie  **Berichte** aus, und wählen Sie dann  **Anonyme Bezeichner für Benutzer-, Gruppen-und Websitenamen in Produktivitäts Bewertung und Verwendungsberichten anzeigen** aus. Diese Einstellung wird sowohl auf die Verwendungsberichte als auch auf die Vorlagen-App angewendet.
3. Wählen Sie  **Save Changes** aus.

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="Seite &quot;Kommunikation&quot; in Produktivitäts Berichten.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Möglichkeit zum Deaktivieren von Personen Erfahrungen

Wenn die Produktivitäts Bewertung allgemein verfügbar ist, können Sie auch den Bereich mit den Personen Erfahrungen mit der Produktivitäts Bewertung deaktivieren. Wenn Sie sich entscheiden, kann niemand aus der Organisation diese Metriken anzeigen, und Ihre Organisation wird aus allen Berechnungen entfernt, die Kommunikation, Besprechungen, Zusammenarbeit, Inhalts Zusammenarbeit und Mobilität beinhalten.

1. Wechseln Sie im Admin Center zu den **Einstellungen** der   >   **org** -Einstellungen, und wählen Sie unter **Dienste** die Registerkarte **Berichte** aus.
2. Wählen Sie  **Berichte** aus, und aktivieren Sie dann das Kontrollkästchen  **zulassen, dass Microsoft 365-Verwendungsdaten für personenbezogene Einblicke verwendet werden.** . Um zu erfahren, wie Sie die Einstellungen für die Datenfreigabe für die Endpunktanalyse im InTune-Konfigurations-Manager ändern, klicken Sie auf weitere **Informationen** .
3. Wählen Sie  **Save Changes** aus.

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="Seite &quot;Kommunikation&quot; in Produktivitäts Berichten.":::