---
title: Deaktivieren der Verzeichnissynchronisierung für Microsoft 365
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
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: In diesem Artikel finden Sie Informationen zum Deaktivieren der Verzeichnissynchronisierung für Microsoft 365 mithilfe von PowerShell.
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690256"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="e8b14-103">Deaktivieren der Verzeichnissynchronisierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e8b14-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="e8b14-104">Sie können die Verzeichnissynchronisierung mithilfe von PowerShell deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e8b14-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="e8b14-105">Es wird jedoch nicht empfohlen, die Verzeichnissynchronisierung als Schritt zur Problembehandlung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e8b14-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="e8b14-106">Wenn Sie Unterstützung bei der Problembehandlung bei der Verzeichnissynchronisierung benötigen, lesen Sie den Artikel [Beheben von Problemen mit der Verzeichnissynchronisierung für Microsoft 365](fix-problems-with-directory-synchronization.md) .</span><span class="sxs-lookup"><span data-stu-id="e8b14-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="e8b14-107">[Wenden Sie sich](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) bei Bedarf an den Support für Business-Produkte.</span><span class="sxs-lookup"><span data-stu-id="e8b14-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="e8b14-108">Deaktivieren der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="e8b14-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="e8b14-109">So deaktivieren Sie die Verzeichnissynchronisierung:</span><span class="sxs-lookup"><span data-stu-id="e8b14-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="e8b14-110">Installieren Sie zunächst die erforderliche Software, und stellen Sie eine Verbindung mit Ihrem Microsoft 365-Abonnement her.</span><span class="sxs-lookup"><span data-stu-id="e8b14-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="e8b14-111">Anweisungen finden Sie unter [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="e8b14-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="e8b14-112">Verwenden Sie die [Option "MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) ", um die Verzeichnissynchronisierung zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="e8b14-112">Use [Set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="e8b14-113">Wenn Sie diesen Befehl verwenden, müssen Sie 72 Stunden warten, bevor Sie die Verzeichnissynchronisierung wieder aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="e8b14-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
 
