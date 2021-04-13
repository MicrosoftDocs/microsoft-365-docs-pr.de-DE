---
title: Verstehen von Geräteprofilen
description: Die verschiedenen Profile, die Administratoren Geräten zuweisen können
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e6b0c96d4e145a2e5df7c7555e262aefe891e483
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690616"
---
# <a name="device-profiles"></a>Geräteprofile

Sie können verschiedenen vordefinierten Konfigurationen ("Geräteprofile") Geräte zuweisen, die jeweils für die Anforderungen bestimmter Benutzertypen optimiert sind. Drei Geräteprofile sind verfügbar:

- Standard
- Vertrauliche Daten
- Power User

Sie können sich Geräteprofile als Teil einer Hierarchie von Gerätekonfigurationsoptionen denken.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Gerätekonfigurationen, die als Pyramide angezeigt werden. Beschreibung folgt":::

Grundsätzlich verfügt jedes Microsoft Managed Desktop-Gerät über eine Grundlage, die eine Standardsicherheitsbasis, Compliancerichtlinien, Windows Update-Einstellungen und Gruppen umfasst. Um mit Microsoft Managed Desktop arbeiten zu können, muss jedes Gerät alle diese Elemente enthalten, die von Administratoren ohne eine Anforderung an Microsoft Managed Desktop nicht geändert werden können.

Geräteprofile werden auf der nächsten höheren Ebene angezeigt. Jedem Microsoft Managed Desktop-Gerät muss ein (und nur ein) Profil zugewiesen sein. Administratoren können auswählen, welchem Profil ein Gerät zugewiesen ist.

Auf einer noch höheren Ebene sind zusätzliche [Anpassungen .](customizing.md) Jedes Gerät kann eine oder mehrere (oder keine) Anpassungen haben. Sie können entweder eine Ebene auf niedrigerer Ebene (Geräteprofile oder die Basiskonfiguration) ändern oder eine völlig neue Anforderung sein, die über die Standardkonfiguration hinaus liegt.

Oben stehen Ihre eigenen Änderungen, z. B. Netzwerkdetails oder Anwendungen. Ein Gerät kann eine beliebige Anzahl dieser Änderungen haben, die nicht von Microsoft Managed Desktop verwaltet oder blockiert werden.


## <a name="device-profile-details"></a>Geräteprofildetails

In der folgenden Tabelle sind die Einstellungen und deren Standardwerte für jede einstellung zusammengefasst, die durch Geräteprofile konfiguriert wurde. (Im Hintergrund werden diese Einstellungen mit OMA-URIs mithilfe von benutzerdefinierten Konfigurationsprofilen im Microsoft Endpoint Manager konfiguriert.)

| Feature | Vertrauliche Daten | Power User | Standard |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------|------------------------|-----------------------|
| **Blockieren des externen Speichers**                                                                                                                               | Ja                       | Ja                   | Nein                   |
| **[Cloud Block Level](https://docs.microsoft.com/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)** | Hoch                      | Hoch                  | Hoch                 |
| **Deaktivieren von Microsoft-Konten**                                                                                                                           | Ja                       | Ja                   | Nein                   |
| **Deaktivieren von persönlichem OneDrive**                                                                                                                            | Ja                       | Ja                   | Nein                   |
| **Wechseln zum sicheren Desktop für die Erhöhung**                                                                                                               | Nein                        | Ja                   | Nein                   |
| **Microsoft Defender for Endpoint Device Tag**                                                                                                           | M365Managed-SensitiveData | M365Managed-PowerUser | M365Managed-Standard |
| **Administrator auf dem Gerät?**                                                                                                                                 | Nein                        | Ja                   | Nein                   |
| **Autopilot-Profil**                                                                                                                                     | MMD Standard               | MMD Power User         | MMD Standard          |
| **AppLocker**                                                                                                                                            | Ja                       | Nein                    | Nein                   |
| **Blockieren des öffentlichen Speichers**                                                                                                                                   | Ja                       | Ja                   | Nein                   |

Jedes Geräteprofil umfasst auch die folgenden Elemente:

- Eine dynamische Azure Active Directory (AAD)-Gerätegruppe
- Eine statische AAD-Gerätegruppe für die Mitgliedschaft
- Ein Microsoft Endpoint Manager-Konfigurationsprofil

> [!IMPORTANT]
> Ändern Sie die Mitgliedschaft dieser Gruppen nicht direkt. Verwenden Sie die Schnittstelle, wie unter [Neu zuweisen von Profilen beschrieben.](../working-with-managed-desktop/change-device-profile.md)

## <a name="limitations"></a>Einschränkungen

Sie können Ausnahmen für die Geräteprofile und deren Details wie bei jeder anderen Richtlinie anfordern. Beachten Sie, dass Sie nur eines der Geräteprofile in Ihrer Azure Active Directory-Organisation ("Mandant") verwenden können. Sie können z. B. nicht anfordern, dass appLocker nur für einige Ihrer Benutzer durch das Geräteprofil für vertrauliche Daten deaktiviert wird. Alle Geräte mit dem Profil "Vertrauliche Daten" müssen die gleiche Konfiguration haben.

Jedes Gerät kann nur ein Profil haben. Wenn ein bestimmtes Gerät von mehreren Benutzern verwendet wird, haben alle Benutzer auf diesem Gerät dieselbe Konfiguration.
