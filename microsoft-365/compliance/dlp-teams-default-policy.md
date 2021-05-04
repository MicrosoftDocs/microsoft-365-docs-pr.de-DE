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
description: Erfahren Sie mehr über die standardmäßige Richtlinie zur Verhinderung von Datenverlust in Microsoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114143"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Weitere Informationen zur Standardrichtlinie zur Verhinderung von Datenverlust in Microsoft Teams (Vorschau)

[Die Funktionen zur Verhinderung von](dlp-learn-about-dlp.md) Datenverlust wurden um chat- Microsoft Teams Kanalnachrichten erweitert, einschließlich Nachrichten im privaten Kanal. Als Teil dieser Version haben wir eine Standard-DLP-Richtlinie für Erstkunden im Compliance Center erstellt.

## <a name="applies-to"></a>Betrifft

Jeder Mandant, der mit einer oder mehreren der folgenden Lizenzen lizenziert ist und über aktive Teams verfügt
 
- ME5, 
- MA5, 
- E5/A5 Compliance, 
- IP+G, 
- OE5, 
- O365 Advanced Compliance 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>Was macht die Standardrichtlinie?

Die Standardmäßige DLP-Richtlinie verfolgt alle Kreditkartennummern, die intern und extern für die Organisation freigegeben wurden. Diese Richtlinie ist standardmäßig für alle Benutzer des Mandanten aktiviert. Es generiert keine Richtlinientipps für Endbenutzer, generiert aber ein Warnungsereignis und löst auch eine E-Mail mit geringem Schweregrad an den Administrator aus (in der Richtlinie hinzugefügt). Der Administrator kann die Aktivitäten anzeigen und die Richtliniendetails bearbeiten, indem er sich beim Compliance Center einmeldet.

Administratoren können diese Richtlinie auf der Seite Compliance [Center >](https://compliance.microsoft.com/compliancesettings) Richtlinie zur Verhinderung von Datenverlust anzeigen.


> [!div class="mx-imgBorder"]
> ![Standardrichtlinie Teams DLP](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Bearbeiten oder Löschen der Standardrichtlinie

Um [die Standardrichtlinie zu](create-test-tune-dlp-policy.md#tune-a-dlp-policy)bearbeiten, um eine bessere Leistung zu erzielen oder sie zu löschen, verwenden Sie einfach ein Konto mit **DLP Compliance Management-Berechtigungen.** Weitere Informationen finden Sie unter [Permissions](create-test-tune-dlp-policy.md#permissions).

