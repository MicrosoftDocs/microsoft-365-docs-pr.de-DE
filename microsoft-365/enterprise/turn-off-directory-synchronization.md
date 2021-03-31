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
ms.openlocfilehash: 26f8729078ea06657ced565db780b57c7e537aa4
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445708"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a>Deaktivieren der Verzeichnissynchronisierung für Microsoft 365
Sie können PowerShell verwenden, um die Verzeichnissynchronisierung zu deaktivieren und die synchronisierten Benutzer in die Cloud zu konvertieren. Es wird jedoch nicht empfohlen, die Verzeichnissynchronisierung als Problembehandlungsschritt zu deaktivieren. Wenn Sie Unterstützung bei der Problembehandlung bei der Verzeichnissynchronisierung benötigen, lesen Sie den Artikel Beheben von Problemen mit der [Verzeichnissynchronisierung für Microsoft 365.](fix-problems-with-directory-synchronization.md) 
  
[Wenden Sie sich](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) bei Bedarf an den Support für Geschäftsprodukte.
  
## <a name="turn-off-directory-synchronization"></a>Deaktivieren der Verzeichnissynchronisierung  
So deaktivieren Sie die Verzeichnissynchronisierung:
  
1. Installieren Sie zunächst die erforderliche Software, und stellen Sie eine Verbindung mit Ihrem Microsoft 365-Abonnement herzustellen. Anweisungen finden Sie [unter Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).
    
2. Verwenden [Sie Set-MsolDirSyncEnabled,](/previous-versions/azure/dn194097(v=azure.100)) um die Verzeichnissynchronisierung zu deaktivieren: 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
>Wenn Sie diesen Befehl verwenden, müssen Sie 72 Stunden warten, bevor Sie die Verzeichnissynchronisierung wieder aktivieren können.
>
