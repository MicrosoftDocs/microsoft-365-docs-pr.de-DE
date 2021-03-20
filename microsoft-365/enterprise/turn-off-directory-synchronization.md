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
description: In diesem Artikel finden Sie Informationen zur Verwendung von PowerShell zum Deaktivieren der Verzeichnissynchronisierung für Microsoft 365.
ms.openlocfilehash: 036130b70382e28ad9d8cb10786ad5e266375c20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909310"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="9c5b3-103">Deaktivieren der Verzeichnissynchronisierung für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9c5b3-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="9c5b3-104">Sie können PowerShell verwenden, um die Verzeichnissynchronisierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c5b3-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="9c5b3-105">Es wird jedoch nicht empfohlen, die Verzeichnissynchronisierung als Problembehandlungsschritt zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9c5b3-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="9c5b3-106">Wenn Sie Unterstützung bei der Problembehandlung bei der Verzeichnissynchronisierung benötigen, lesen Sie den Artikel Beheben von Problemen mit der [Verzeichnissynchronisierung für Microsoft 365.](fix-problems-with-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="9c5b3-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="9c5b3-107">[Wenden Sie sich](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) bei Bedarf an den Support für Geschäftsprodukte.</span><span class="sxs-lookup"><span data-stu-id="9c5b3-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="9c5b3-108">Deaktivieren der Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="9c5b3-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="9c5b3-109">So deaktivieren Sie die Verzeichnissynchronisierung:</span><span class="sxs-lookup"><span data-stu-id="9c5b3-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="9c5b3-110">Installieren Sie zunächst die erforderliche Software, und stellen Sie eine Verbindung mit Ihrem Microsoft 365-Abonnement herzustellen.</span><span class="sxs-lookup"><span data-stu-id="9c5b3-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="9c5b3-111">Anweisungen finden Sie [unter Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9c5b3-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="9c5b3-112">Verwenden [Sie Set-MsolDirSyncEnabled,](/previous-versions/azure/dn194097(v=azure.100)) um die Verzeichnissynchronisierung zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="9c5b3-112">Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="9c5b3-113">Wenn Sie diesen Befehl verwenden, müssen Sie 72 Stunden warten, bevor Sie die Verzeichnissynchronisierung wieder aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="9c5b3-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
