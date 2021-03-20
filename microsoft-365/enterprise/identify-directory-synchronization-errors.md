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
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="b0b97-103">Anzeigen von Verzeichnissynchronisierungsfehlern in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b0b97-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="b0b97-104">Sie können Verzeichnissynchronisierungsfehler im Microsoft 365 Admin Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0b97-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="b0b97-105">Es werden nur die Fehler des User-Objekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0b97-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="b0b97-106">Informationen zum Anzeigen von Fehlern mit PowerShell finden Sie unter [Identifizieren von Objekten mit DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span><span class="sxs-lookup"><span data-stu-id="b0b97-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b0b97-107">Anzeigen von Verzeichnissynchronisierungsfehlern im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="b0b97-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="b0b97-108">So zeigen Sie Fehler im Microsoft 365 Admin Center an:</span><span class="sxs-lookup"><span data-stu-id="b0b97-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="b0b97-109">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit einem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="b0b97-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="b0b97-110">Auf der **Startseite** wird die **Benutzerverwaltungskarte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0b97-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![Die Benutzerverwaltungskarte im Microsoft 365 Admin Center](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="b0b97-112">Wählen Sie auf der Karte **Synchronisierungsfehler** unter **Azure AD Connect aus,** um die Fehler auf der Seite **Verzeichnissynchronisierungsfehler zu** sehen.</span><span class="sxs-lookup"><span data-stu-id="b0b97-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Ein Beispiel für die Seite "Verzeichnissynchronisierungsfehler"](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="b0b97-114">Wählen Sie einen der Fehler aus, um den Detailbereich mit Informationen zum Fehler und Tipps zur Behebung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b0b97-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Beispiel für die Details eines Verzeichnissynchronisierungsfehlers](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="b0b97-116">Informationen zum Beheben identifizierter Probleme finden Sie unter Beheben von Problemen mit der [Verzeichnissynchronisierung für Microsoft 365.](fix-problems-with-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="b0b97-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>