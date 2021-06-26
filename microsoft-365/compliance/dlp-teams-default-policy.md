---
title: Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Erfahren Sie mehr über die Standardmäßige Richtlinie zur Verhinderung von Datenverlust in Microsoft Teams
ms.openlocfilehash: c6b7413fdd4017fe1211e804c00a2e9c0684468d
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149118"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)

Die Funktionen [zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md) wurden erweitert, um Microsoft Teams Chat- und Kanalnachrichten, einschließlich Nachrichten im privaten Kanal, einzuschließen. Als Teil dieser Version haben wir eine Standard-DLP-Richtlinie für Microsoft Teams für Erstmalige Kunden im Compliance Center erstellt.

## <a name="applies-to"></a>Gilt für

Jeder Mandant, der mit einer oder mehreren der folgenden Lizenzen lizenziert ist und über aktive Teams Benutzer verfügt
 
- ME5, 
- MA5, 
- E5/A5 Compliance, 
- IP+G, 
- OE5, 
- O365 Advanced Compliance 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>Was bewirkt die Standardrichtlinie?

Die Standardmäßige DLP-Richtlinie für Teams verfolgt alle Kreditkartennummern nach, die intern und extern für die Organisation freigegeben wurden. Diese Richtlinie ist standardmäßig für alle Benutzer des Mandanten aktiviert. Es generiert keine Richtlinientipps für Endbenutzer, generiert jedoch ein Warnungsereignis und löst auch eine E-Mail mit geringem Schweregrad an den Administrator aus (hinzugefügt in der Richtlinie). Der Administrator kann die Aktivitäten anzeigen und die Richtliniendetails bearbeiten, indem er sich beim Compliance Center anmeldet.

Administratoren können diese Richtlinie im [Compliance Center](https://compliance.microsoft.com/compliancesettings) > Seite "Richtlinien zur Verhinderung von Datenverlust" anzeigen.


> [!div class="mx-imgBorder"]
> ![Standardmäßige Teams DLP-Richtlinie](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Bearbeiten oder Löschen der Standardrichtlinie

Um [die Standardrichtlinie für eine bessere Leistung zu bearbeiten oder zu löschen,](create-test-tune-dlp-policy.md#tune-a-dlp-policy)verwenden Sie einfach ein Konto mit **DLP-Complianceverwaltungsberechtigungen.** Weitere Informationen finden Sie unter ["Berechtigungen".](create-test-tune-dlp-policy.md#permissions)

