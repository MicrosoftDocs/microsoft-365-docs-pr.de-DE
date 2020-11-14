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
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073224"
---
# <a name="prerequisites-for-guest-accounts"></a>Voraussetzungen für Gastkonten

Für Microsoft Managed Desktop sind die folgenden Einstellungen in ihrer Azure AD Organisation für den Zugriff auf Gastkonten erforderlich. Sie können diese Einstellungen im Azure- [Portal](https://portal.azure.com) unter **externe Identitäten/externe Zusammenarbeit** anpassen:

-   **Administratoren und Benutzer in der Rolle "Gast Inviter" können die Einstellung "Ja" einladen** . **Yes**
-   Wählen Sie unter Einschränkungen für die **Zusammenarbeit** eine der folgenden Optionen aus:
    -   Wenn Sie zulassen, dass **Einladungen an eine beliebige Domäne gesendet werden (am besten inklusive)** , ist keine andere Konfiguration erforderlich.
    -   Wenn Sie **Einladungen zu den angegebenen Domänen verweigern** auswählen, stellen Sie sicher, dass Microsoft.com nicht in den Zieldomänen aufgeführt ist.
    -   Wenn Sie **Einladungen nur für die angegebenen Domänen (am restriktivsten) zulassen** auswählen, stellen Sie sicher, dass Microsoft.com in den Zieldomänen aufgeführt *ist* .

Wenn Sie Einschränkungen festlegen, die mit diesen Einstellungen interagieren, stellen Sie sicher, dass Sie die Azure-Active Directory **moderne Arbeitsplatz-Dienstkonten** ausschließen. Wenn Sie beispielsweise über eine Richtlinie für den bedingten Zugriff verfügen, die verhindert, dass Gastkonten auf das InTune-Portal zugreifen können, schließen Sie die Gruppe **moderner Arbeitsplatz-Dienstkonten** aus dieser Richtlinie aus.

