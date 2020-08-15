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
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a><span data-ttu-id="0c553-103">Anzeigen von Verzeichnis Synchronisierungsfehlern in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0c553-103">View directory synchronization errors in Microsoft 365</span></span>

<span data-ttu-id="0c553-104">Sie können Verzeichnis Synchronisierungsfehler im Microsoft 365 Admin Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c553-104">You can view directory synchronization errors in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0c553-105">Es werden nur die Fehler des Benutzerobjekts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c553-105">Only the User object errors are displayed.</span></span> <span data-ttu-id="0c553-106">Informationen zum Anzeigen von Fehlern mit PowerShell finden Sie unter [Identifizieren von Objekten mit DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span><span class="sxs-lookup"><span data-stu-id="0c553-106">To view errors with PowerShell, see [Identify objects with DirSyncProvisioningErrors](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency).</span></span>

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a><span data-ttu-id="0c553-107">Anzeigen von Verzeichnis Synchronisierungsfehlern im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="0c553-107">View directory synchronization errors in the Microsoft 365 admin center</span></span>

<span data-ttu-id="0c553-108">So zeigen Sie Fehler im Microsoft 365 Admin Center an:</span><span class="sxs-lookup"><span data-stu-id="0c553-108">To view any errors in the Microsoft 365 admin center:</span></span>
  
1. <span data-ttu-id="0c553-109">Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) mit einem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="0c553-109">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with a global administrator account.</span></span> 
    
2. <span data-ttu-id="0c553-110">Auf der **Start** Seite sehen Sie die **Benutzer Verwaltungs** Karte.</span><span class="sxs-lookup"><span data-stu-id="0c553-110">On the **Home** page, you'll see the **User management** card.</span></span> 
    
    ![Die Benutzer Verwaltungskarte im Microsoft 365 Admin Center](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. <span data-ttu-id="0c553-112">Wählen Sie auf der Karte **Synchronisierungsfehler** unter **Azure AD Connect** aus, um die Fehler auf der Seite **Verzeichnis Synchronisierungsfehler** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c553-112">On the card, choose **Sync errors** under **Azure AD Connect** to see the errors on the **Directory sync errors** page.</span></span>   
    
    ![Ein Beispiel für die Seite "Verzeichnis Synchronisierungsfehler"](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. <span data-ttu-id="0c553-114">Wählen Sie einen der Fehler aus, um den Detailbereich mit Informationen zum Fehler und Tipps zur Problembehebung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c553-114">Choose any of the errors to display the details pane with information about the error and tips on how to fix it.</span></span>

   ![Beispiel für die Details eines Verzeichnis Synchronisierungsfehlers](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
<span data-ttu-id="0c553-116">Nach der Anzeige finden Sie unter [Beheben von Problemen mit der Verzeichnissynchronisierung für Microsoft 365](fix-problems-with-directory-synchronization.md) , um identifizierte Probleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="0c553-116">After viewing, see [fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) to correct any identified issues.</span></span>

