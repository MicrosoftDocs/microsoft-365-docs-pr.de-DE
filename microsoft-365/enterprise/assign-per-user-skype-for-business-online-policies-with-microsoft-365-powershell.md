---
title: Zuweisen von benutzerbezogenen Skype for Business Onlinerichtlinien mit PowerShell für Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: 36743c86-46c2-46be-b9ed-ad9d4e85d186
description: 'Zusammenfassung: Verwenden Sie PowerShell für Microsoft 365 zum Zuweisen von Benutzerkommunikationseinstellungen mit Skype for Business Onlinerichtlinien.'
ms.openlocfilehash: d7f369e96f3db95c741e6d4f2178eaf9032ab0bb
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288083"
---
# <a name="assign-per-user-skype-for-business-online-policies-with-powershell-for-microsoft-365"></a><span data-ttu-id="0b345-103">Zuweisen von benutzerbezogenen Skype for Business Onlinerichtlinien mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b345-103">Assign per-user Skype for Business Online policies with PowerShell for Microsoft 365</span></span>

<span data-ttu-id="0b345-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0b345-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0b345-105">Die Verwendung von PowerShell für Microsoft 365 ist eine effiziente Möglichkeit, benutzerspezifische Kommunikationseinstellungen mit Skype for Business Onlinerichtlinien zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0b345-105">Using PowerShell for Microsoft 365 is an efficient way to assign per-user communication settings with Skype for Business Online policies.</span></span>
  
## <a name="prepare-to-run-the-powershell-commands"></a><span data-ttu-id="0b345-106">Vorbereiten der Ausführung der PowerShell-Befehle</span><span class="sxs-lookup"><span data-stu-id="0b345-106">Prepare to run the PowerShell commands</span></span>

<span data-ttu-id="0b345-107">Bereiten Sie sich mithilfe dieser Anweisungen auf die Ausführung der Befehle vor (überspringen Sie die Schritte, die Sie bereits ausgeführt haben):</span><span class="sxs-lookup"><span data-stu-id="0b345-107">Use these instructions to get set up to run the commands (skip the steps you have already completed):</span></span>
  
  > [!Note]
   > <span data-ttu-id="0b345-108">Der Skype for Business Online-Connector ist derzeit Bestandteil des aktuellen PowerShell-Moduls von Teams.</span><span class="sxs-lookup"><span data-stu-id="0b345-108">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="0b345-109">Wenn Sie die neueste Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="0b345-109">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="0b345-110">Installieren Sie das [PowerShell-Modul von Teams](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="0b345-110">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="0b345-111">Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus:</span><span class="sxs-lookup"><span data-stu-id="0b345-111">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
    
   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

   <span data-ttu-id="0b345-112">Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort Ihres Skype for Business Online-Administratorkontos ein.</span><span class="sxs-lookup"><span data-stu-id="0b345-112">When prompted, enter your Skype for Business Online administrator account name and password.</span></span>
    
## <a name="updating-external-communication-settings-for-a-user-account"></a><span data-ttu-id="0b345-113">Aktualisieren externer Kommunikationseinstellungen für ein Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="0b345-113">Updating external communication settings for a user account</span></span>

<span data-ttu-id="0b345-p102">Angenommen, Sie möchten Einstellungen für die externe Kommunikation für ein Benutzerkonto ändern. Sie möchten z. B. festlegen, dass Alex mit Partnerbenutzern kommunizieren darf (EnableFederationAccess = True), jedoch nicht mit Windows Live-Benutzern (EnablePublicCloudAccess = False). Hierzu müssen Sie zwei Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="0b345-p102">Suppose you want to change external communication settings on a user account. For example, you want to allow Alex to communicate with federated users (EnableFederationAccess is equal to True) but not with Windows Live users (EnablePublicCloudAccess equals False). To do that, you need to do two things:</span></span>
  
1. <span data-ttu-id="0b345-117">Suchen Sie nach eine externe Zugriffsrichtlinie, die unsere Kriterien erfüllt.</span><span class="sxs-lookup"><span data-stu-id="0b345-117">Find an external access policy that meets our criteria.</span></span>
    
2. <span data-ttu-id="0b345-118">Weisen Sie Alex diese externe Zugriffsrichtlinie ist.</span><span class="sxs-lookup"><span data-stu-id="0b345-118">Assign that external access policy to Alex.</span></span>
    
<span data-ttu-id="0b345-119">Wie bestimmen Sie, welche Externe Zugriffsrichtlinie Alex zugewiesen werden soll?</span><span class="sxs-lookup"><span data-stu-id="0b345-119">How do you determine which external access policy to assign Alex?</span></span> <span data-ttu-id="0b345-120">Der folgende Befehl gibt alle externen Zugriffsrichtlinien zurück, in denen EnableFederationAccess auf „True“ und EnablePublicCloudAccess auf „False“ festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="0b345-120">The following command returns all the external access policies where EnableFederationAccess is set to True and EnablePublicCloudAccess is set to False:</span></span>
  
```powershell
Get-CsExternalAccessPolicy -Include All| Where-Object {$_.EnableFederationAccess -eq $True -and $_.EnablePublicCloudAccess -eq $False}
```

<span data-ttu-id="0b345-121">Sofern Sie keine benutzerdefinierten Instanzen von ExternalAccessPolicy erstellt haben, gibt dieser Befehl eine Richtlinie zurück, die unseren Kriterien entspricht (FederationOnly).</span><span class="sxs-lookup"><span data-stu-id="0b345-121">Unless you have created any custom instances of ExternalAccessPolicy, that command returns one policy that meets our criteria (FederationOnly).</span></span> <span data-ttu-id="0b345-122">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0b345-122">Here is an example:</span></span>
  
```powershell
Identity                          : Tag:FederationOnly
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : False
EnablePublicCloudAudioVideoAccess : False
EnableOutsideAccess               : True
```

<span data-ttu-id="0b345-p105">Nachdem wir Sie wissen, welche Richtlinie Sie Alex zuweisen müssen, können Sie die Richtlinie mithilfe des Cmdlets [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) zuweisen: Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0b345-p105">Now that you know which policy to assign to Alex, we can assign that policy by using the [Grant-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy) cmdlet. Here is an example:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName "FederationOnly"
```

<span data-ttu-id="0b345-125">Das Zuweisen einer Richtlinie ist ganz einfach: Sie geben einfach die Identität des Benutzers und den Namen der zuzuweisenden Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="0b345-125">Assigning a policy is pretty simple: you simply specify the Identity of the user and the name of the policy to be assigned.</span></span> 
  
<span data-ttu-id="0b345-p106">Und bei Richtlinien und Richtlinienzuweisungen sind Sie nicht darauf beschränkt, mit nur jeweils einem einzelnen Benutzerkonto zu arbeiten. Angenommen beispielsweise, Sie benötigen eine Liste aller Benutzer, die mit Partnerbenutzern und Windows Live-Benutzern kommunizieren dürfen. Wir wissen bereits, dass diesen Benutzern die externe Benutzerzugriffsrichtlinie „FederationAndPICDefault" zugewiesen wurde. Da wir dies wissen, können Sie eine Liste all dieser Benutzer anzeigen, indem Sie den folgenden einfachen Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="0b345-p106">And when it comes to policies and policy assignments, you're not limited to working with user accounts one a time. For example, suppose you need a list of all the users who are allowed to communicate with federated partners and with Windows Live users. We already know that those users have been assigned the external user access policy FederationAndPICDefault. Because we know that, you can display a list of all those users by running one simple command. Here is the command:</span></span>
  
```powershell
Get-CsOnlineUser -Filter {ExternalAccessPolicy -eq "FederationAndPICDefault"} | Select-Object DisplayName
```

<span data-ttu-id="0b345-p107">Anders gesagt, wir können alle Benutzer anzeigen, bei denen die ExternalAccessPolicy-Eigenschaft auf FederationAndPICDefault festgelegt ist. (Und zum Einschränken der am Bildschirm angezeigten Informationsmenge können Sie das Select-Object-Cmdlet verwenden, um nur die Anzeigenamen der Benutzer anzuzeigen).</span><span class="sxs-lookup"><span data-stu-id="0b345-p107">In other words, show us all the users where the ExternalAccessPolicy property is set to FederationAndPICDefault. (And, in order to limit the amount of information that appears onscreen, use the Select-Object cmdlet to display show us only each user's display name.)</span></span> 
  
<span data-ttu-id="0b345-133">Um alle Benutzerkonten so zu konfigurieren, dass sie die gleiche Richtlinie verwenden, geben Sie diesen Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="0b345-133">To configure all our user accounts to use that same policy, use this command:</span></span>
  
```powershell
Get-CsOnlineUser | Grant-CsExternalAccessPolicy "FederationAndPICDefault"
```

<span data-ttu-id="0b345-134">Dieser Befehl verwendet „Get-CsOnlineUser“, um eine Sammlung aller Benutzer zurückzugeben, die für Lync aktiviert wurden. Anschließend werden alle diese Informationen an „Grant-CsExternalAccessPolicy“ gesendet, das die Richtlinie „FederationAndPICDefault“ jedem Benutzer in der Sammlung zuweist.</span><span class="sxs-lookup"><span data-stu-id="0b345-134">This command uses Get-CsOnlineUser to return a collection of all the users who have been enabled for Lync, then sends all that information to Grant-CsExternalAccessPolicy, which assigns the FederationAndPICDefault policy to each and every user in the collection.</span></span>
  
<span data-ttu-id="0b345-135">Ein weiteres Beispiel: Angenommen, Sie haben Alex zuvor die Richtlinie „FederationAndPICDefault" zugewiesen, haben aber nun Ihre Meinung geändert und möchten, dass er von der globalen externen Zugriffsrichtlinie verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="0b345-135">As an additional example, suppose you've previously assigned Alex the FederationAndPICDefault policy and now you've changed your mind and would like him to be managed by the global external access policy.</span></span> <span data-ttu-id="0b345-136">Sie können die globale Richtlinie niemandem explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0b345-136">You can't explicitly assign the global policy to anyone.</span></span> <span data-ttu-id="0b345-137">Stattdessen wird die globale Richtlinie für einen bestimmten Benutzer verwendet, wenn diesem Benutzer keine Benutzerrichtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0b345-137">Instead, the global policy is used for a given user if no per-user policy is assigned to that user.</span></span> <span data-ttu-id="0b345-138">Wenn Sie also möchten, dass Alex von der globalen Richtlinie verwaltet wird, müssen Sie die Zuweisung aller zuvor zugewiesenen benutzerspezifischen Richtlinien wieder  *aufheben*  .</span><span class="sxs-lookup"><span data-stu-id="0b345-138">Therefore, if we want Alex to be managed by the global policy, you need to  *unassign*  any per-user policy previously assigned to him.</span></span> <span data-ttu-id="0b345-139">Hier ein Beispielbefehl:</span><span class="sxs-lookup"><span data-stu-id="0b345-139">Here is an example command:</span></span>
  
```powershell
Grant-CsExternalAccessPolicy -Identity "Alex Darrow" -PolicyName $Null
```

<span data-ttu-id="0b345-p109">Dieser Befehl legt den Namen der Alex zugewiesenen externen Zugriffsrichtlinie auf einen Nullwert ($Null) fest. Null bedeutet „nichts". Anders ausgedrückt, Alex wird keine externe Zugriffsrichtlinie zugewiesen. Wenn einem Benutzer keine externe Zugriffsrichtlinie zugewiesen ist, wird der Benutzer von der globalen Richtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0b345-p109">This command sets the name of the external access policy assigned to Alex to a null value ($Null). Null means "nothing". In other words, no external access policy is assigned to Alex. When no external access policy is assigned to a user, that user then gets managed by the global policy.</span></span>

## <a name="managing-large-numbers-of-users"></a><span data-ttu-id="0b345-144">Verwalten einer großen Anzahl von Benutzern</span><span class="sxs-lookup"><span data-stu-id="0b345-144">Managing large numbers of users</span></span>

<span data-ttu-id="0b345-145">Um eine große Anzahl von Benutzern (1000 oder mehr) zu verwalten, müssen Sie die Befehle mithilfe des Cmdlets ["Invoke-Command"](/powershell/module/microsoft.powershell.core/invoke-command) über einen Skriptblock stapeln.</span><span class="sxs-lookup"><span data-stu-id="0b345-145">To manage large numbers of users (1000 or more), you need to batch the commands via a script block using the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span>  <span data-ttu-id="0b345-146">In früheren Beispielen muss jedes Mal, wenn ein Cmdlet ausgeführt wird, der Aufruf eingerichtet und dann auf das Ergebnis gewartet werden, bevor es zurück gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b345-146">In previous examples, each time a cmdlet is executed, it must set up the call and then wait for the result before sending it back.</span></span>  <span data-ttu-id="0b345-147">Bei Verwendung eines Skriptblocks können die Cmdlets auf diese Weise remote ausgeführt werden, und nach Abschluss senden Sie die Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="0b345-147">When using a script block, this allows the cmdlets to be executed remotely, and once completed, send the data back.</span></span>

```powershell
$users = Get-CsOnlineUser -Filter { ClientPolicy -eq $null } -ResultSize 500

$batch = 50
$filter = ''
$total = $users.Count
$count = 0
    $users | ForEach-Object {
    $upn = $_.UserPrincipalName
    $filter += "(UserPrincipalName -eq '$upn')"
    $batch--
    $count++
    if (($batch -eq 0) -or ($count -eq $total)) {
        $filterSB=[ScriptBlock]::Create($filter)
        Invoke-Command -Session $s -ScriptBlock {param($f) Get-CsOnlineUser -filter $f | Grant-CsClientPolicy -PolicyName "ClientPolicyNoIMURL" -Passthru | Grant-CsExternalAccessPolicy -PolicyName "FederationAndPICDefault"} -ArgumentList $filterSB

        # Reset
        $batch = 50
        $filter = ''
    } else {
        $filter += " -or "
    }
}
```

<span data-ttu-id="0b345-148">Dadurch werden jeweils 500 Benutzer gefunden, die nicht über eine Clientrichtlinie verfügen.</span><span class="sxs-lookup"><span data-stu-id="0b345-148">This will find 500 users at a time who do not have a client policy.</span></span> <span data-ttu-id="0b345-149">Sie gewährt ihnen die Clientrichtlinie "ClientPolicyNoIMURL" und die Richtlinie für den externen Zugriff "FederationAndPicDefault".</span><span class="sxs-lookup"><span data-stu-id="0b345-149">It will grant them the client policy "ClientPolicyNoIMURL" and the external access policy "FederationAndPicDefault".</span></span> <span data-ttu-id="0b345-150">Die Ergebnisse werden in Gruppen von 50 zusammengefasst, und jeder Batch von 50 wird dann an den Remotecomputer gesendet.</span><span class="sxs-lookup"><span data-stu-id="0b345-150">The results are batched into groups of 50 and each batch of 50 is then sent to the remote machine.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b345-151">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="0b345-151">See also</span></span>

[<span data-ttu-id="0b345-152">Verwalten von Skype for Business Online mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b345-152">Manage Skype for Business Online with PowerShell</span></span>](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0b345-153">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b345-153">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="0b345-154">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0b345-154">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)