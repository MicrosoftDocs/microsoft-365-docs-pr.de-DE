---
title: Voraussetzungen für Gastkonten
description: Konfigurationsrichtlinien für Gastkonten und deren Anpassung
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694245"
---
# <a name="prerequisites-for-guest-accounts"></a>Voraussetzungen für Gastkonten

Microsoft Managed Desktop erfordert die folgenden Einstellungen in Ihrer Azure AD-Organisation für den Gastkontozugriff. Sie können diese Einstellungen im [Azure-Portal unter](https://portal.azure.com) **Einstellungen für externe Identitäten/externe Zusammenarbeit anpassen:**

-   Für **Gast-Einladungseinschränkungen,** die auf Mitglieder festgelegt sind, und Benutzer, die bestimmten Administratorrollen zugewiesen sind, Können Gastbenutzer einladen, einschließlich **Gäste mit Mitgliedsberechtigungen**
-   Wählen **Sie für Einschränkungen für** die Zusammenarbeit eine der folgenden Optionen aus:
    -   Wenn Sie Einladungen an eine Beliebige Domäne **(einschließlich)** zulassen auswählen, ist keine andere Konfiguration erforderlich.
    -   Wenn Sie **Einladungen an** die angegebenen Domänen verweigern auswählen, stellen Sie sicher, dass Microsoft.com nicht in den Zieldomänen aufgeführt ist.
    -   Wenn Sie Einladungen nur für die angegebenen **Domänen zulassen (am** restriktivsten) auswählen, stellen Sie sicher, dass Microsoft.com in den Zieldomänen aufgeführt ist. 

Wenn Sie Einschränkungen festlegen, die mit diesen Einstellungen interagieren, müssen Sie die Azure Active Directory **Modern Workplace Service Accounts ausschließen.** Wenn Sie beispielsweise über eine Richtlinie für bedingten Zugriff verfügen, die verhindert, dass Gastkonten auf das Intune-Portal zugreifen, schließen Sie die Gruppe **Moderne Arbeitsplatzdienstkonten** aus dieser Richtlinie aus.

## <a name="steps-to-get-ready"></a>Schritte für die ersten Schritte

1. Überprüfung der [Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).
2. Verwendung des [Tools zur Bereitschaftsbewertung](readiness-assessment-tool.md).
3. [Voraussetzungen für Gastkonten](guest-accounts.md) (Dieser Artikel)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps im Microsoft Managed Desktop](apps.md)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md)
