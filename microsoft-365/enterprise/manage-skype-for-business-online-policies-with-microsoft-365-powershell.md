---
title: Verwalten von Skype for Business Online-Richtlinien mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: ff93a341-6f0f-4f06-9690-726052e1be64
description: 'Zusammenfassung: Verwenden Sie PowerShell, um die Eigenschaften des Skype for Business Online Benutzerkontos mit Richtlinien zu verwalten.'
ms.openlocfilehash: 7657dae6fa1b27299e4cbc0cf6a311380cb90e9e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690740"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a><span data-ttu-id="feb68-103">Verwalten von Skype for Business Online-Richtlinien mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="feb68-103">Manage Skype for Business Online policies with PowerShell</span></span>

<span data-ttu-id="feb68-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="feb68-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="feb68-105">Um viele Eigenschaften des Benutzerkontos für Skype for Business Online zu verwalten, müssen Sie diese als Eigenschaften von Richtlinien mit PowerShell für Microsoft 365 angeben.</span><span class="sxs-lookup"><span data-stu-id="feb68-105">To manage many properties of user account for Skype for Business Online, you must specify them as properties of policies with PowerShell for Microsoft 365.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="feb68-106">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="feb68-106">Before you begin</span></span>

<span data-ttu-id="feb68-107">Bereiten Sie sich mithilfe dieser Anweisungen auf die Ausführung der Befehle vor (überspringen Sie die Schritte, die Sie bereits ausgeführt haben):</span><span class="sxs-lookup"><span data-stu-id="feb68-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
1. <span data-ttu-id="feb68-108">Laden Sie das [Connector-Modul für Skype for Business Online](https://www.microsoft.com/download/details.aspx?id=39366) herunter, und installieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="feb68-108">Download and install the [Skype for Business Online Connector module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span>
    
2. <span data-ttu-id="feb68-109">Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="feb68-109">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
  ```

<span data-ttu-id="feb68-110">Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort Ihres Skype for Business Online-Administratorkontos ein.</span><span class="sxs-lookup"><span data-stu-id="feb68-110">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="manage-user-account-policies"></a><span data-ttu-id="feb68-111">Verwalten von Richtlinien für Benutzerkonten</span><span class="sxs-lookup"><span data-stu-id="feb68-111">Manage user account policies</span></span>

<span data-ttu-id="feb68-p101">Viele Eigenschaften von Skype for Business Online-Benutzerkonten werden mithilfe von Richtlinien konfiguriert. Richtlinien sind einfach Sammlungen von Einstellungen, die auf einen oder mehrere Benutzer angewendet werden können. Um sich die Konfiguration einer Richtlinie anzusehen, können Sie diesen Beispielbefehl für die Richtlinie „FederationAndPICDefault" ausführen:</span><span class="sxs-lookup"><span data-stu-id="feb68-p101">Many Skype for Business Online user account properties are configured by using policies. Policies are simply collections of settings that can be applied to one or more users. To take a look at how the a policy has been configured, you can run this example command for the FederationAndPICDefault policy:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

<span data-ttu-id="feb68-115">Die Rückmeldung sollte in etwa so aussehen:</span><span class="sxs-lookup"><span data-stu-id="feb68-115">In turn, you should get back something similar to this:</span></span>
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

<span data-ttu-id="feb68-116">In diesem Beispiel bestimmen die Werte in dieser Richtlinie, was eine Verwendung für die Kommunikation mit Verbundbenutzern tun kann oder nicht.</span><span class="sxs-lookup"><span data-stu-id="feb68-116">In this example, the values within this policy determine what a use can or cannot do when it comes to communicating with federated users.</span></span> <span data-ttu-id="feb68-117">Beispielsweise muss die EnableOutsideAccess-Eigenschaft auf true festgelegt werden, damit ein Benutzer mit Personen außerhalb der Organisation kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="feb68-117">For example, the EnableOutsideAccess property must be set to True for a user to be able to communicate with people outside the organization.</span></span> <span data-ttu-id="feb68-118">Beachten Sie, dass diese Eigenschaft nicht im Microsoft 365 Admin Center angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="feb68-118">Note that this property does not appear in the Microsoft 365 admin center.</span></span> <span data-ttu-id="feb68-119">Stattdessen wird die Eigenschaft basierend auf den anderen ausgewählten Optionen automatisch auf true oder false festgelegt.</span><span class="sxs-lookup"><span data-stu-id="feb68-119">Instead, the property is automatically set to True or False based on the other selections that you make.</span></span> <span data-ttu-id="feb68-120">Die anderen beiden Eigenschaften von Interesse sind:</span><span class="sxs-lookup"><span data-stu-id="feb68-120">The other two properties of interest are:</span></span>
  
- <span data-ttu-id="feb68-121">**EnableFederationAccess** gibt an, ob der Benutzer mit Personen von Verbunddomänen kommunizieren darf.</span><span class="sxs-lookup"><span data-stu-id="feb68-121">**EnableFederationAccess** indicates whether the user can communicate with people from federated domains.</span></span>
    
- <span data-ttu-id="feb68-122">**EnablePublicCloudAccess** gibt an, ob der Benutzer mit Windows Live-Benutzern kommunizieren darf.</span><span class="sxs-lookup"><span data-stu-id="feb68-122">**EnablePublicCloudAccess** indicates whether the user can communicate with Windows Live users.</span></span>
    
<span data-ttu-id="feb68-p103">Sie ändern somit die partnerbezogenen Eigenschaften von Benutzerkonten (Beispiel: **Set-CsUser -EnableFederationAccess $True**) nicht direkt. Stattdessen weisen Sie einem Konto eine externe Zugriffsrichtlinie mit den gewünschten Eigenschaftswerten zu, die vorkonfiguriert wurden. Wenn ein Benutzer mit Partnerbenutzern und Windows Live-Benutzern kommunizieren können soll, muss diesem Benutzerkonto eine Richtlinie zugewiesen werden, die diese Arten der Kommunikation zulässt.</span><span class="sxs-lookup"><span data-stu-id="feb68-p103">Therefore, you don't directly change federation-related properties on user accounts (for example, **Set-CsUser -EnableFederationAccess $True**). Instead, you assign an account an external access policy that has the desired property values preconfigured. If we want a user to be able to communicate with federated users and with Windows Live users, that user account must be assigned a policy that allows those types of communication.</span></span>
  
<span data-ttu-id="feb68-126">Wenn Sie wissen möchten, ob jemand mit Benutzern außerhalb der Organisation kommunizieren kann, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="feb68-126">If you want to know whether or not someone can communicate with users from outside the organization, you have to:</span></span>
  
- <span data-ttu-id="feb68-127">Festlegen, welche externe Zugriffsrichtlinie dem betreffenden Benutzer zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="feb68-127">Determine which external access policy has been assigned to that user.</span></span>
    
- <span data-ttu-id="feb68-128">Festlegen, welche Funktionen durch diese Richtlinie erlaubt werden.</span><span class="sxs-lookup"><span data-stu-id="feb68-128">Determine which capabilities are or are not allowed by that policy.</span></span>
    
<span data-ttu-id="feb68-129">Sie können zu diesem Zweck beispielsweise den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="feb68-129">For example, you can do that by using this command:</span></span>
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

<span data-ttu-id="feb68-130">Dieser Befehl sucht nach der dem Benutzer zugewiesenen Richtlinie und dann in dieser Richtlinie nach den deaktivierten/aktivierten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="feb68-130">This command finds the policy assigned to the user, then finds the capabilities enabled or disabled within that policy.</span></span>
  
<span data-ttu-id="feb68-131">Informationen zum Verwalten von Skype for Business Online-Richtlinien mit PowerShell finden Sie unter den Cmdlets für:</span><span class="sxs-lookup"><span data-stu-id="feb68-131">To manage Skype for Business Online policies with PowerShell, see the cmdlets for:</span></span>

- <span data-ttu-id="feb68-132">[Client Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="feb68-132">[Client policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)</span></span>
- <span data-ttu-id="feb68-133">[Konferenzrichtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="feb68-133">[Conferencing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)</span></span>
- <span data-ttu-id="feb68-134">[Mobile Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="feb68-134">[Mobile policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)</span></span>
- <span data-ttu-id="feb68-135">[Online Voicemail-Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="feb68-135">[Online Voicemail policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)</span></span>
- <span data-ttu-id="feb68-136">[VoIP-Routing Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span><span class="sxs-lookup"><span data-stu-id="feb68-136">[Voice Routing policy](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)</span></span>


> [!NOTE]
> <span data-ttu-id="feb68-p104">Ein Skype for Business Online-Wählplan ist jeder Hinsicht mit Ausnahme des Namens eine Richtlinie. Der Name „Wählplan" wurde statt „Wählrichtlinie" oder einem ähnlichen Namen verwendet, um die Abwärtskompatibilität mit Office Communications Server und Exchange sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="feb68-p104">A Skype for Business Online dial plan is a policy in every respect except the name. The name "dial plan" was chosen instead of, say, "dialing policy" in order to provide backward compatibility with Office Communications Server and with Exchange.</span></span> 
  
<span data-ttu-id="feb68-139">Beispiel: Um alle für Sie verfügbaren VoIP-Richtlinien anzuzeigen, verwenden Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="feb68-139">For example, to look at all the voice policies available for your use, run this command:</span></span>
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> <span data-ttu-id="feb68-p105">Hiermit wird eine Liste mit den für Sie verfügbaren VoIP-Richtlinien zurückgegeben. Beachten Sie aber, dass nicht alle Richtlinien auch allen Benutzern zugewiesen werden können, da zahlreiche Beschränkungen hinsichtlich Lizenzierung und Region bestehen. (Der so genannte „[Verwendungsstandort](https://msdn.microsoft.com/library/azure/dn194136.aspx)".) Wenn Sie die externen Zugriffsrichtlinien und die Konferenzrichtlinien ermitteln möchten, die einem bestimmten Benutzer zugewiesen werden können, verwenden Sie Befehle ähnlich den folgenden:</span><span class="sxs-lookup"><span data-stu-id="feb68-p105">That returns a list of all the voice policies available to you. Keep in mind, however, that not all policies can be assigned to all users. This is due to various restrictions involving licensing and geographic location. (The so-called "[usage location](https://msdn.microsoft.com/library/azure/dn194136.aspx).") If you want to know the external access policies and the conferencing policies that can be assigned to a particular user, use commands similar to these:</span></span> 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

<span data-ttu-id="feb68-p106">Der Parameter "ApplicableTo" beschränkt die zurückgegebenen Daten auf Richtlinien, die einem bestimmten Benutzer zugewiesen werden können (zum Beispiel Alex Darrow). Je nach Lizenz- und Verwendungsstandortbeschränkungen kann dies eine Teilmenge aller verfügbaren Richtlinien sein.</span><span class="sxs-lookup"><span data-stu-id="feb68-p106">The ApplicableTo parameter limits the returned data to policies that can be assigned to the specified user (for example, Alex Darrow). Depending on licensing and usage location restrictions, that might represent a subset of all the available policies.</span></span> 
  
<span data-ttu-id="feb68-146">In einigen Fällen werden Eigenschaften von Richtlinien nicht mit Microsoft 365 verwendet, während andere nur von Microsoft-Supportmitarbeitern verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="feb68-146">In some cases, properties of policies are not used with Microsoft 365, while others can only be managed by Microsoft support personnel.</span></span> 
  
<span data-ttu-id="feb68-p107">Bei Skype for Business Online müssen Benutzer über eine Richtlinie verwaltet werden. Wenn eine gültige richtlinienbezogene Eigenschaft leer ist, bedeutet dies, dass der betreffende Benutzer von einer globalen Richtlinie verwaltet wird; dies ist ein Richtlinie, die automatisch auf einen Benutzer angewendet wird, es sei denn, dem Benutzer ist explizit eine benutzerspezifische Richtlinie zugewiesen. Da keine Clientrichtlinie für ein Benutzerkonto angezeigt wird, wird es durch die globale Richtlinie verwaltet. Sie können die globale Clientrichtlinie mit diesem Befehl ermitteln:</span><span class="sxs-lookup"><span data-stu-id="feb68-p107">With Skype for Business Online, users must be managed by a policy of some kind. If a valid policy-related property is blank, that means that the user in question is being managed by a global policy, which is a policy that is automatically applied to a user unless he or she is specifically assigned a per-user policy. Because we don't see a client policy listed for a user account, it is managed by the global policy. You can determine the global client policy with this command:</span></span>
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a><span data-ttu-id="feb68-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="feb68-151">See also</span></span>

[<span data-ttu-id="feb68-152">Verwalten von Skype for Business Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="feb68-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="feb68-153">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="feb68-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="feb68-154">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="feb68-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
