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
ms.openlocfilehash: d50f35d7d5e81622eb8dfc3bbf8328a8c43e9676
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430034"
---
# <a name="manage-skype-for-business-online-with-powershell"></a><span data-ttu-id="a0e97-103">Verwalten von Skype for Business Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0e97-103">Manage Skype for Business Online with PowerShell</span></span>

<span data-ttu-id="a0e97-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="a0e97-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="a0e97-105">Für die Verwaltung von Richtlinien sind Skype for Business Online-Administratoren verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="a0e97-105">Skype for Business Online administrators are responsible for managing policies.</span></span> <span data-ttu-id="a0e97-106">Obwohl Sie einige dieser Aufgaben in Microsoft 365 Admin Center machen können, andere können in PowerShell einfacher gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a0e97-106">Although you can do some of these tasks in the Microsoft 365 admin center, others are easier to do in PowerShell.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a0e97-107">Vor der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="a0e97-107">Before you start</span></span>

<span data-ttu-id="a0e97-108">Laden Sie das [Windows PowerShell Modul für Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366) herunter, installieren Sie es, und starten Sie Ihren Computer dann neu.</span><span class="sxs-lookup"><span data-stu-id="a0e97-108">Download and install the [Skype for Business Online Windows PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer.</span></span>


## <a name="connect-using-skype-for-business-online-admin-credentials"></a><span data-ttu-id="a0e97-109">Herstellung einer Verbindung mit Skype for Business Online-Administratoranmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="a0e97-109">Connect using Skype for Business Online admin credentials</span></span>

1. <span data-ttu-id="a0e97-110">Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="a0e97-110">Open a Windows PowerShell command prompt window and run the following commands:</span></span>
    
   ```powershell
   Import-Module SkypeOnlineConnector
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="a0e97-111">Geben Sie im Dialogfeld **Bei Windows PowerShell anmelden** den Namen und das Kennwort für Ihr Skype for Business Online-Administratorkonto ein und wählen Sie dann **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0e97-111">In the **Windows PowerShell Credential Request** dialog box, type your Skype for Business Online administrator account name and password, and then select **OK**.</span></span>


## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a><span data-ttu-id="a0e97-112">Herstellung einer Verbindung mit einem Administratorkonto mit mehrstufiger Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a0e97-112">Connect using an admin account with multi-factor authentication</span></span>

1. <span data-ttu-id="a0e97-113">Öffnen Sie ein Windows PowerShell-Eingabeaufforderungsfenster und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="a0e97-113">Open a Windows PowerShell command prompt window, and run the following commands:</span></span>

   ```powershell
   Import-Module SkypeOnlineConnector
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

2. <span data-ttu-id="a0e97-114">Wenn Sie durch den Befehl **New-CsOnlineSession** dazu aufgefordert werden, geben Sie den Namen Ihres Skype for Business Online-Administratorkontos ein.</span><span class="sxs-lookup"><span data-stu-id="a0e97-114">When prompted by the **New-CsOnlineSession** command, enter your Skype for Business Online administrator account name.</span></span>

3. <span data-ttu-id="a0e97-115">Geben Sie im Dialogfeld **Bei Ihrem Konto anmelden** Ihr Skype for Business Online-Administratorkennwort ein und wählen Sie dann **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="a0e97-115">In the **Sign in to your account** dialog box, type your Skype for Business Online administrator password and select **Sign in**.</span></span>

4. <span data-ttu-id="a0e97-116">Folgen Sie den Anweisungen im Dialogfeld **Bei Ihrem Konto anmelden**, um zusätzliche Authentifizierungsinformationen anzugeben, z. B. einen Überprüfungscode, und wählen Sie dann **Bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="a0e97-116">In the **Sign in to your account** dialog box, follow the instructions to add authentication information, such as a verification code, and then select **Verify**.</span></span>

<span data-ttu-id="a0e97-117">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a0e97-117">For more information, see:</span></span>
  
- [<span data-ttu-id="a0e97-118">Verwalten von Skype for Business Online-Richtlinien mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0e97-118">Manage Skype for Business Online policies with PowerShell</span></span>](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
- [<span data-ttu-id="a0e97-119">Zuweisen von benutzerspezifischen Skype for Business Online-Richtlinien mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0e97-119">Assign per-user Skype for Business Online policies with PowerShell</span></span>](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)
    
## <a name="see-also"></a><span data-ttu-id="a0e97-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0e97-120">See also</span></span>

[<span data-ttu-id="a0e97-121">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0e97-121">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="a0e97-122">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a0e97-122">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="a0e97-123">Referenzen zu Skype for Business PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a0e97-123">Skype for Business PowerShell cmdlet references</span></span>](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)
