---
title: Anzeigen von Verzeichnis Synchronisierungsfehlern in Microsoft 365
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
description: In diesem Artikel erfahren Sie, wie Sie Verzeichnis Synchronisierungsfehler und mögliche Korrekturen im Microsoft 365 Admin Center anzeigen können.
ms.openlocfilehash: 5103b1f8a8f0514ca30fd71b94dee2530f0b082f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690757"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>Anzeigen von Verzeichnis Synchronisierungsfehlern in Microsoft 365

Sie können Verzeichnis Synchronisierungsfehler im Microsoft 365 Admin Center anzeigen. Es werden nur die Fehler des Benutzerobjekts angezeigt. Informationen zum Anzeigen von Fehlern mit PowerShell finden Sie unter [Identifizieren von Objekten mit DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>Anzeigen von Verzeichnis Synchronisierungsfehlern im Microsoft 365 Admin Center

So zeigen Sie Fehler im Microsoft 365 Admin Center an:
  
1. Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit einem globalen Administratorkonto an. 
    
2. Auf der **Start** Seite sehen Sie die **Benutzer Verwaltungs** Karte. 
    
    ![Die Benutzer Verwaltungskarte im Microsoft 365 Admin Center](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. Wählen Sie auf der Karte **Synchronisierungsfehler** unter **Azure AD Connect** aus, um die Fehler auf der Seite **Verzeichnis Synchronisierungsfehler** anzuzeigen.   
    
    ![Ein Beispiel für die Seite "Verzeichnis Synchronisierungsfehler"](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. Wählen Sie einen der Fehler aus, um den Detailbereich mit Informationen zum Fehler und Tipps zur Problembehebung anzuzeigen.

   ![Beispiel für die Details eines Verzeichnis Synchronisierungsfehlers](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
Nach der Anzeige finden Sie unter [Beheben von Problemen mit der Verzeichnissynchronisierung für Microsoft 365](fix-problems-with-directory-synchronization.md) , um identifizierte Probleme zu beheben.

