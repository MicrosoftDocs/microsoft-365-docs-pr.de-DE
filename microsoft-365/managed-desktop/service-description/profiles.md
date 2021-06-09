---
title: Grundlegendes zu Geräteprofilen
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
ms.openlocfilehash: 5b5421d2b4001b813d3bcc1e804cae7fb05d0fa7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842002"
---
# <a name="device-profiles"></a>Geräteprofile

Sie können Geräten verschiedene vordefinierte Konfigurationen ("Geräteprofile") zuweisen, die jeweils für die Anforderungen bestimmter Benutzertypen optimiert sind. Drei Geräteprofile sind verfügbar:

- Standard
- Vertrauliche Daten
- Hauptbenutzer

Sie können sich Geräteprofile als Teil einer Hierarchie von Gerätekonfigurationsoptionen vorstellen.

:::image type="content" source="../../media/mmd-profile-options-heirarchy.png" alt-text="Als Pyramide dargestellte Gerätekonfigurationen. Beschreibung folgt":::

Im Grunde hat jedes Microsoft Managed Desktop Gerät eine Grundlage, die eine Standardsicherheitsgrundlinie, Compliancerichtlinien, Windows Updateeinstellungen und Gruppen umfasst. Um mit Microsoft Managed Desktop arbeiten zu können, muss jedes Gerät alle diese Elemente enthalten, die von Administratoren ohne eine Anforderung an Microsoft Managed Desktop nicht geändert werden können.

Geräteprofile werden auf der nächsthöheren Ebene angezeigt. Jedem Microsoft Managed Desktop Gerät muss ein (und nur ein) Profil zugewiesen sein. Administratoren können auswählen, welches Profil einem Gerät zugewiesen ist.

Auf einer noch höheren Ebene befinden sich zusätzliche [Anpassungen.](customizing.md) Jedes Gerät kann eine oder mehrere (oder keine) Anpassungen aufweisen. Sie können entweder eine untere Ebene (Geräteprofile oder die grundlegende Konfiguration) ändern oder eine völlig neue Anforderung sein, die über der Standardkonfiguration liegt.

An oberster Stelle stehen Ihre eigenen Änderungen, z. B. Netzwerkdetails oder Anwendungen. Ein Gerät kann eine beliebige Anzahl dieser Änderungen aufweisen, die nicht von Microsoft Managed Desktop verwaltet oder blockiert werden.


## <a name="device-profile-details"></a>Geräteprofildetails

In der folgenden Tabelle sind die Einstellungen und deren Standardwerte für jede von Geräteprofilen konfigurierte Einstellung zusammengefasst. (Im Hintergrund werden diese Einstellungen mit OMA-URIs mithilfe von benutzerdefinierten Konfigurationsprofilen in Microsoft Endpoint Manager konfiguriert.)

<br>

****

|Feature|Vertrauliche Daten|Hauptbenutzer|Standard|
|---|:---:|:---:|:---:|
|**Blockieren externer Storage**|Ja|Ja|Nein|
|**[Cloud-Blockebene](/graph/api/resources/intune-deviceconfig-defendercloudblockleveltype)**|Hoch|Hoch|Hoch|
|**Deaktivieren von Microsoft-Konten**|Ja|Ja|Nein|
|**Persönliche OneDrive deaktivieren**|Ja|Ja|Nein|
|**Wechseln zum sicheren Desktop zur Erhöhung der Rechte**|Nein|Ja|Nein|
|**Microsoft Defender für Endpunkt-Gerätetag**|M365Managed-SensitiveData|M365Managed-PowerUser|M365Managed-Standard|
|**Administrator auf dem Gerät?**|Nein|Ja|Nein|
|**Autopilot-Profil**|MMD Standard|MMD Power User|MMD Standard|
|**AppLocker**|Ja|Nein|Nein|
|**Blockieren öffentlicher Store**|Ja|Ja|Nein|
|

Jedes Geräteprofil umfasst auch die folgenden Elemente:

- AAD-Gerätegruppe (Dynamic Membership Azure Active Directory)
- AAD-Gerätegruppe für statische Mitgliedschaft
- Ein Microsoft Endpoint Manager-Konfigurationsprofil

> [!IMPORTANT]
> Ändern Sie die Mitgliedschaft dieser Gruppen nicht direkt. Verwenden Sie die Schnittstelle, wie unter [Neuzuweisen von Profilen](../working-with-managed-desktop/change-device-profile.md)beschrieben.

## <a name="limitations"></a>Einschränkungen

Sie können Ausnahmen von den Geräteprofilen und deren Details wie bei jeder anderen Richtlinie anfordern. Denken Sie daran, dass Sie nur eines jedes Geräteprofils in Ihrer Azure Active Directory Organisation ("Mandant") haben können. Sie können beispielsweise nicht anfordern, dass das Geräteprofil für vertrauliche Daten AppLocker nur für einige Ihrer Benutzer deaktiviert. Alle Geräte mit dem Profil "Vertrauliche Daten" müssen über die gleiche Konfiguration verfügen.

Jedes Gerät kann nur ein Profil aufweisen. Wenn ein bestimmtes Gerät von mehreren Benutzern verwendet wird, haben alle Benutzer auf diesem Gerät dieselbe Konfiguration.
