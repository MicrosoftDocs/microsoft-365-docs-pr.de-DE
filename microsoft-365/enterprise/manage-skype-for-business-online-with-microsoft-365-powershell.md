---
title: Verwalten von Skype for Business Online mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365 zum Verwalten von Skype for Business Online-Richtlinien, benutzerspezifischen Richtlinien und Besprechungseinstellungen.'
ms.openlocfilehash: aea78d135a5d7ffbb5d8480c549d0fdee88f7d51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690739"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="5bac2-103">Verwalten von Skype for Business Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bac2-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="5bac2-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="5bac2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="5bac2-105">Eine der Hauptaufgaben eines jeden Skype for Business Online-Administrators ist die Verwaltung von Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="5bac2-105">One of the primary tasks of any Skype for Business Online administrator is managing policies.</span></span> <span data-ttu-id="5bac2-106">Obwohl Sie einige dieser Aufgaben in Microsoft 365 Admin Center durchführen können, können andere Aufgaben in PowerShell wesentlich schneller und einfacher durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5bac2-106">Although you can accomplish some of these tasks in the Microsoft 365 admin center, other tasks are much quicker and easier in PowerShell.</span></span> 

## <a name="before-you-start"></a><span data-ttu-id="5bac2-107">Vor der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="5bac2-107">Before you start</span></span>

<span data-ttu-id="5bac2-108">Laden Sie das [Connector-Modul für Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366) herunter, installieren Sie es, und starten Sie Ihren Computer dann neu.</span><span class="sxs-lookup"><span data-stu-id="5bac2-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-name-and-password"></a><span data-ttu-id="5bac2-109">Stellen Sie eine Verbindung unter Angabe des Namens und Kennworts Ihres Skype for Business Online-Administratorkontos her.</span><span class="sxs-lookup"><span data-stu-id="5bac2-109">Connect using a Skype for Business Online administrator account name and password</span></span>

1. <span data-ttu-id="5bac2-110">Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="5bac2-110">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="5bac2-111">Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** den Namen und das Kennwort für Ihr Skype for Business Online-Administratorkonto ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5bac2-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then click **OK**.</span></span>


## <a name="connect-using-a-skype-for-business-online-administrator-account-with-multi-factor-authentication"></a><span data-ttu-id="5bac2-112">Stellen Sie eine Verbindung unter Verwendung Ihres Skype for Business Online-Administratorkontos mit mehrstufiger Authentifizierung her.</span><span class="sxs-lookup"><span data-stu-id="5bac2-112">Connect using a Skype for Business Online administrator account with multi-factor authentication</span></span>

1. <span data-ttu-id="5bac2-113">Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="5bac2-113">Open a Windows PowerShell command prompt and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="5bac2-114">Wenn Sie durch den Befehl **New-CsOnlineSession** dazu aufgefordert werden, geben Sie den Namen Ihres Skype for Business Online-Administratorkontos ein.</span><span class="sxs-lookup"><span data-stu-id="5bac2-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="5bac2-115">Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** Ihr Skype for Business Online-Administratorkennwort ein und klicken Sie dann auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="5bac2-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password, and then click **Sign in**.</span></span>

4. <span data-ttu-id="5bac2-116">Folgen Sie den Anweisungen im Dialogfeld **Bei Ihrem Konto anmelden**, um zusätzliche Authentifizierungsinformationen anzugeben, z. B. einen Überprüfungscode, und klicken Sie dann auf **Bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="5bac2-116">Follow the instructions in the **Sign in to your account** dialog box to provide additional authentication information, such as a verification code, and then click **Verify**.</span></span>

<span data-ttu-id="5bac2-117">Weitere Informationen hierzu finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="5bac2-117">For more information, see the following topics:</span></span>
  
- [<span data-ttu-id="5bac2-118">Verwalten von Skype for Business Online-Richtlinien mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bac2-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="5bac2-119">Zuweisen von benutzerspezifischen Skype for Business Online-Richtlinien mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bac2-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="5bac2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bac2-120">See also</span></span>

[<span data-ttu-id="5bac2-121">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bac2-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="5bac2-122">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5bac2-122">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="5bac2-123">Referenzen zu Skype for Business PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5bac2-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)

