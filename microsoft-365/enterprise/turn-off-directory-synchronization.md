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
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Deaktivieren der Verzeichnissynchronisierung für Microsoft 365
Sie können die Verzeichnissynchronisierung mithilfe von PowerShell deaktivieren. Es wird jedoch nicht empfohlen, die Verzeichnissynchronisierung als Schritt zur Problembehandlung zu deaktivieren. Wenn Sie Unterstützung bei der Problembehandlung bei der Verzeichnissynchronisierung benötigen, lesen Sie den Artikel [Beheben von Problemen mit der Verzeichnissynchronisierung für Microsoft 365](fix-problems-with-directory-synchronization.md) . 
  
[Wenden Sie sich](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) bei Bedarf an den Support für Business-Produkte.
  
## <a name="turn-off-directory-synchronization"></a>Deaktivieren der Verzeichnissynchronisierung  
So deaktivieren Sie die Verzeichnissynchronisierung:
  
1. Installieren Sie zunächst die erforderliche Software, und stellen Sie eine Verbindung mit Ihrem Microsoft 365-Abonnement her. Anweisungen finden Sie unter [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Verwenden Sie die [Option "MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) ", um die Verzeichnissynchronisierung zu deaktivieren: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Wenn Sie diesen Befehl verwenden, müssen Sie 72 Stunden warten, bevor Sie die Verzeichnissynchronisierung wieder aktivieren können.
>
 
