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
description: Verwenden Sie PowerShell für Microsoft 365 zum Verwalten von Skype for Business Online-Richtlinien, benutzerspezifischen Richtlinien und Besprechungseinstellungen.
ms.openlocfilehash: ff35463dc0c2e16106432c393b10e31e6bf0a5d2
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477101"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="00858-103">Verwalten von Skype for Business Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="00858-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="00858-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="00858-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="00858-105">Für die Verwaltung von Richtlinien sind Skype for Business Online-Administratoren verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="00858-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="00858-106">Obwohl Sie einige dieser Aufgaben in Microsoft 365 Admin Center machen können, andere können in PowerShell einfacher gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="00858-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="00858-107">Vor der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="00858-107">Before you start</span></span>

  > [!Note]
   > <span data-ttu-id="00858-108">Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.</span><span class="sxs-lookup"><span data-stu-id="00858-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="00858-109">Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="00858-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
   
<span data-ttu-id="00858-110">Installieren Sie das [PowerShell-Modul von Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="00858-110">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>


## <a name="connect-using-admin-credentials"></a><span data-ttu-id="00858-111">Verbinden mit Administratoranmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="00858-111">Connect using admin credentials</span></span>

1. <span data-ttu-id="00858-112">Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="00858-112">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="00858-113">Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** den Namen und das Kennwort Ihres Administratorkontos ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="00858-113">In the **Windows PowerShell Credential Request** dialog box, type your administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="00858-114">Herstellung einer Verbindung mit einem Administratorkonto mit mehrstufiger Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="00858-114">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="00858-115">Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="00858-115">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="00858-116">Wenn Sie durch den Befehl **New-CsOnlineSession** dazu aufgefordert werden, geben Sie den Namen Ihres Skype for Business Online-Administratorkontos ein.</span><span class="sxs-lookup"><span data-stu-id="00858-116">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="00858-117">Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** Ihr Skype for Business Online-Administratorkennwort ein und wählen Sie dann **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="00858-117">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="00858-118">Folgen Sie den Anweisungen im Dialogfeld **Bei Ihrem Konto anmelden**, um zusätzliche Authentifizierungsinformationen anzugeben, z. B. einen Überprüfungscode, und wählen Sie dann **Bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="00858-118">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="00858-119">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="00858-119">For more information, see:</span></span>
  
- [<span data-ttu-id="00858-120">Verwalten von Skype for Business Online-Richtlinien mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="00858-120">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="00858-121">Zuweisen von benutzerspezifischen Skype for Business Online-Richtlinien mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="00858-121">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="00858-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00858-122">See also</span></span>

[<span data-ttu-id="00858-123">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="00858-123">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="00858-124">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="00858-124">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="00858-125">Referenzen zu Skype for Business PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="00858-125">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
