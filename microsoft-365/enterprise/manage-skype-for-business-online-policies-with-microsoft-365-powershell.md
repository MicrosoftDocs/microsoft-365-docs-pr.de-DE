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
ms.openlocfilehash: 20a75fa1c131f693fcf30d20477af5c9ee7aed35
ms.sourcegitcommit: 22755cebfbfa2c4dc3f8b4f54ccb23636a211ee5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2020
ms.locfileid: "48477041"
---
# <a name="manage-skype-for-business-online-policies-with-powershell"></a>Verwalten von Skype for Business Online-Richtlinien mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Um viele Eigenschaften des Benutzerkontos für Skype for Business Online zu verwalten, müssen Sie diese als Eigenschaften von Richtlinien mit PowerShell für Microsoft 365 angeben.
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:

Bereiten Sie sich mithilfe dieser Anweisungen auf die Ausführung der Befehle vor (überspringen Sie die Schritte, die Sie bereits ausgeführt haben):

  > [!Note]
  > Skype for Business Online Connector ist derzeit Teil des aktuellen Teams-PowerShell-Moduls. Wenn Sie die neueste PowerShell-Version von Microsoft Teams verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

1. Installieren Sie das [PowerShell-Modul von Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Öffnen Sie eine Windows PowerShell-Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $userCredential
   Import-PSSession $sfbSession
   ```

   Wenn Sie dazu aufgefordert werden, geben Sie den Namen und das Kennwort Ihres Skype for Business Online-Administratorkontos ein.
    
## <a name="manage-user-account-policies"></a>Verwalten von Richtlinien für Benutzerkonten

Viele Eigenschaften von Skype for Business Online-Benutzerkonten werden mithilfe von Richtlinien konfiguriert. Richtlinien sind einfach Sammlungen von Einstellungen, die auf einen oder mehrere Benutzer angewendet werden können. Um sich die Konfiguration einer Richtlinie anzusehen, können Sie diesen Beispielbefehl für die Richtlinie „FederationAndPICDefault" ausführen:
  
```powershell
Get-CsExternalAccessPolicy -Identity "FederationAndPICDefault"
```

Die Rückmeldung sollte in etwa so aussehen:
  
```powershell
Identity                          : Tag:FederationAndPICDefault
Description                       :
EnableFederationAccess            : True
EnableXmppAccess                  : False
EnablePublicCloudAccess           : True
EnablePublicCloudAudioVideoAccess : True
EnableOutsideAccess               : True
```

In diesem Beispiel bestimmen die Werte in dieser Richtlinie, was eine Verwendung für die Kommunikation mit Verbundbenutzern tun kann oder nicht. Beispielsweise muss die EnableOutsideAccess-Eigenschaft auf true festgelegt werden, damit ein Benutzer mit Personen außerhalb der Organisation kommunizieren kann. Beachten Sie, dass diese Eigenschaft nicht im Microsoft 365 Admin Center angezeigt wird. Stattdessen wird die Eigenschaft basierend auf den anderen ausgewählten Optionen automatisch auf true oder false festgelegt. Die anderen beiden Eigenschaften von Interesse sind:
  
- **EnableFederationAccess** gibt an, ob der Benutzer mit Personen von Verbunddomänen kommunizieren darf.
    
- **EnablePublicCloudAccess** gibt an, ob der Benutzer mit Windows Live-Benutzern kommunizieren darf.
    
Sie ändern somit die partnerbezogenen Eigenschaften von Benutzerkonten (Beispiel: **Set-CsUser -EnableFederationAccess $True**) nicht direkt. Stattdessen weisen Sie einem Konto eine externe Zugriffsrichtlinie mit den gewünschten Eigenschaftswerten zu, die vorkonfiguriert wurden. Wenn ein Benutzer mit Partnerbenutzern und Windows Live-Benutzern kommunizieren können soll, muss diesem Benutzerkonto eine Richtlinie zugewiesen werden, die diese Arten der Kommunikation zulässt.
  
Wenn Sie wissen möchten, ob jemand mit Benutzern außerhalb der Organisation kommunizieren kann, müssen Sie Folgendes tun:
  
- Festlegen, welche externe Zugriffsrichtlinie dem betreffenden Benutzer zugewiesen wird.
    
- Festlegen, welche Funktionen durch diese Richtlinie erlaubt werden.
    
Sie können zu diesem Zweck beispielsweise den folgenden Befehl verwenden:
  
```powershell
Get-CsOnlineUser -Identity "Alex Darrow" | ForEach {Get-CsExternalAccessPolicy -Identity $_.ExternalAccessPolicy}
```

Dieser Befehl sucht nach der dem Benutzer zugewiesenen Richtlinie und dann in dieser Richtlinie nach den deaktivierten/aktivierten Funktionen.
  
Informationen zum Verwalten von Skype for Business Online-Richtlinien mit PowerShell finden Sie unter den Cmdlets für:

- [Client Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#client-policy-cmdlets)
- [Konferenzrichtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#conferencing-policy-cmdlets)
- [Mobile Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#mobile-policy-cmdlets)
- [Online Voicemail-Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#online-voicemail-policy-cmdlets)
- [VoIP-Routing Richtlinie](https://docs.microsoft.com/previous-versions//mt228132(v=technet.10)#voice-routing-policy-cmdlets)


> [!NOTE]
> Ein Skype for Business Online-Wählplan ist jeder Hinsicht mit Ausnahme des Namens eine Richtlinie. Der Name „Wählplan" wurde statt „Wählrichtlinie" oder einem ähnlichen Namen verwendet, um die Abwärtskompatibilität mit Office Communications Server und Exchange sicherzustellen. 
  
Beispiel: Um alle für Sie verfügbaren VoIP-Richtlinien anzuzeigen, verwenden Sie diesen Befehl:
  
```powershell
Get-CsVoicePolicy
```

> [!NOTE]
> Hiermit wird eine Liste mit den für Sie verfügbaren VoIP-Richtlinien zurückgegeben. Beachten Sie aber, dass nicht alle Richtlinien auch allen Benutzern zugewiesen werden können, da zahlreiche Beschränkungen hinsichtlich Lizenzierung und Region bestehen. (Der so genannte „[Verwendungsstandort](https://msdn.microsoft.com/library/azure/dn194136.aspx)".) Wenn Sie die externen Zugriffsrichtlinien und die Konferenzrichtlinien ermitteln möchten, die einem bestimmten Benutzer zugewiesen werden können, verwenden Sie Befehle ähnlich den folgenden: 

```powershell
Get-CsConferencingPolicy -ApplicableTo "Alex Darrow"
Get-CsExternalAccessPolicy -ApplicableTo "Alex Darrow"
```

Der Parameter "ApplicableTo" beschränkt die zurückgegebenen Daten auf Richtlinien, die einem bestimmten Benutzer zugewiesen werden können (zum Beispiel Alex Darrow). Je nach Lizenz- und Verwendungsstandortbeschränkungen kann dies eine Teilmenge aller verfügbaren Richtlinien sein. 
  
In einigen Fällen werden Eigenschaften von Richtlinien nicht mit Microsoft 365 verwendet, während andere nur von Microsoft-Supportmitarbeitern verwaltet werden können. 
  
Bei Skype for Business Online müssen Benutzer über eine Richtlinie verwaltet werden. Wenn eine gültige richtlinienbezogene Eigenschaft leer ist, bedeutet dies, dass der betreffende Benutzer von einer globalen Richtlinie verwaltet wird; dies ist ein Richtlinie, die automatisch auf einen Benutzer angewendet wird, es sei denn, dem Benutzer ist explizit eine benutzerspezifische Richtlinie zugewiesen. Da keine Clientrichtlinie für ein Benutzerkonto angezeigt wird, wird es durch die globale Richtlinie verwaltet. Sie können die globale Clientrichtlinie mit diesem Befehl ermitteln:
  
```powershell
Get-CsClientPolicy -Identity "Global"
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Skype for Business Online mit PowerShell](manage-skype-for-business-online-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

