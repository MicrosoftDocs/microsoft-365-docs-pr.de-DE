---
title: Anzeigen von Verzeichnissynchronisierungsfehlern in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: Erfahren Sie, wie Sie Verzeichnissynchronisierungsfehler und mögliche Korrekturen im Microsoft 365 Admin Center anzeigen.
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907504"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Anzeigen von Verzeichnissynchronisierungsfehlern in Microsoft 365

Sie können Verzeichnissynchronisierungsfehler im Microsoft 365 Admin Center anzeigen. Es werden nur die Fehler des User-Objekts angezeigt. Informationen zum Anzeigen von Fehlern mit PowerShell finden Sie unter [Identifizieren von Objekten mit DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Anzeigen von Verzeichnissynchronisierungsfehlern im Microsoft 365 Admin Center

So zeigen Sie Fehler im Microsoft 365 Admin Center an:
  
1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit einem globalen Administratorkonto an. 
    
2. Auf der **Startseite** wird die **Benutzerverwaltungskarte** angezeigt. 
    
    ![Die Benutzerverwaltungskarte im Microsoft 365 Admin Center](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. Wählen Sie auf der Karte **Synchronisierungsfehler** unter **Azure AD Connect aus,** um die Fehler auf der Seite **Verzeichnissynchronisierungsfehler zu** sehen.   
    
    ![Ein Beispiel für die Seite "Verzeichnissynchronisierungsfehler"](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Wählen Sie einen der Fehler aus, um den Detailbereich mit Informationen zum Fehler und Tipps zur Behebung anzuzeigen.

   ![Beispiel für die Details eines Verzeichnissynchronisierungsfehlers](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Informationen zum Beheben identifizierter Probleme finden Sie unter Beheben von Problemen mit der [Verzeichnissynchronisierung für Microsoft 365.](fix-problems-with-directory-synchronization.md)