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
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574607"
---
# <a name="prerequisites-for-guest-accounts"></a>Voraussetzungen für Gastkonten

Microsoft Managed Desktop erfordert die folgenden Einstellungen in Ihrer Azure AD-Organisation für den Gastkontozugriff. Sie können diese Einstellungen im [Azure-Portal unter](https://portal.azure.com) **Externe Identitäten /Externe Zusammenarbeit anpassen:**

-   **Administratoren und Benutzer in der Gast einladenden Rolle können auf** Ja festlegen **einladen**
-   Wählen **Sie für Einschränkungen für** die Zusammenarbeit eine der folgenden Optionen aus:
    -   Wenn Sie Einladungen an eine Beliebige Domäne **(einschließlich)** zulassen auswählen, ist keine andere Konfiguration erforderlich.
    -   Wenn Sie **Einladungen an** die angegebenen Domänen verweigern auswählen, stellen Sie sicher, dass Microsoft.com nicht in den Zieldomänen aufgeführt ist.
    -   Wenn Sie Einladungen nur für die angegebenen **Domänen zulassen (am** restriktivsten) auswählen, stellen Sie sicher, dass Microsoft.com in den Zieldomänen aufgeführt ist. 

Wenn Sie Einschränkungen festlegen, die mit diesen Einstellungen interagieren, müssen Sie die Azure Active Directory **Modern Workplace Service Accounts ausschließen.** Wenn Sie beispielsweise über eine Richtlinie für bedingten Zugriff verfügen, die verhindert, dass Gastkonten auf das Intune-Portal zugreifen, schließen Sie die Gruppe **Moderne Arbeitsplatzdienstkonten** aus dieser Richtlinie aus.

## <a name="steps-to-get-ready"></a>Schritte für die ersten Schritte

1. Überprüfen [Sie die Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).
2. Verwenden [Sie Die Bereitschaftsbewertungstools](readiness-assessment-tool.md).
3. [Voraussetzungen für Gastkonten](guest-accounts.md) (Dieser Artikel)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Anwendungen in Microsoft Managed Desktop](apps.md)
8. [Voraussetzungen von zugeordneten Laufwerken für Microsoft Managed Desktop](mapped-drives.md)
9. [Voraussetzungen von Druckressourcen für Microsoft Managed Desktop](printing.md)