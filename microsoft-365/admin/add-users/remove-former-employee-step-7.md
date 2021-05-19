---
title: 'Schritt 7 : Löschen des Benutzerkontos eines ehemaligen Mitarbeiters'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Führen Sie die folgenden Schritte aus, um das Benutzerkonto eines ehemaligen Mitarbeiters zu löschen.
ms.openlocfilehash: 5ca428079091c4af44ef1efa9be3d7340e254995
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535938"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Schritt 7 : Löschen des Benutzerkontos eines ehemaligen Mitarbeiters

Nachdem Sie auf alle Benutzerdaten des ehemaligen Mitarbeiters zugegriffen und diese gespeichert haben, können Sie das Konto des ehemaligen Mitarbeiters löschen.

> [!IMPORTANT]
> Löschen Sie das Konto nicht, wenn Sie eine E-Mail-Weiterleitung eingerichtet oder das Konto in ein freigegebenes Postfach konvertiert haben. Für beide Funktionen wird das Konto benötigt, damit die Weiterleitung oder Postfachfreigabe funktioniert.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Namen des Mitarbeiters aus, den Sie löschen möchten.
3. Wählen Sie unter dem Namen des Benutzers Benutzer **löschen aus.** Wählen Sie die optionen aus, die Sie für diesen Benutzer wünschen, und wählen Sie dann **Benutzer löschen aus.** Wenn Sie bereits einem anderen Benutzer Zugriff auf die E-Mails und OneDrive dieses Benutzers gegeben haben, müssen Sie dies hier nicht erneut tun.

Wenn Sie einen Benutzer löschen, wird das Konto ungefähr 30 Tage lang deaktiviert (inaktiv). Sie haben in dieser Zeit noch die Möglichkeit, das Konto wiederherzustellen, bevor es endgültig gelöscht wird.

## <a name="watch-delete-a-former-employees-user-account"></a>Watch: Löschen des Benutzerkontos eines ehemaligen Mitarbeiters

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../../business-video/index.yml) an.

## <a name="does-your-organization-use-active-directory"></a>Verwendet Ihre Organisation Active Directory?

Wenn Ihre Organisation Benutzerkonten mit Microsoft 365 einer lokalen Active Directory-Umgebung synchronisiert, müssen Sie diese Benutzerkonten in Ihrem lokalen Active Directory-Dienst löschen und wiederherstellen. Sie können sie nicht in Office 365 löschen und wiederherstellen.

Informationen zum Löschen und Wiederherstellen des Benutzerkontos in Active Directory finden Sie [unter Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).
  
Wenn Sie eine Azure Active Directory, lesen Sie [das Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell-Cmdlet.
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters

Hier finden Sie Informationen dazu, wie Sie die E-Mail-Nutzung für einen Mitarbeiter beenden können (Exchange).
  
|||
|:-----|:-----|
|**Mögliche Aktionen** <br/> |**Wie geht das?** <br/> |
|Sitzung beenden (z. B. Outlook im Web, Outlook, Exchange Active Sync usw.) und Öffnen einer neuen Sitzung erzwingen  <br/> |Kennwort zurücksetzen  <br/> |
|Sitzung beenden und Zugriff auf zukünftige Sitzungen (für alle Protokolle) sperren  <br/> |Deaktivieren Sie das Konto. Beispiel: (im Exchange Admin Center oder mithilfe von PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Sitzung für ein bestimmtes Protokoll (z. B. ActiveSync) beenden  <br/> |Deaktivieren Sie das Protokoll. Beispiel: (im Exchange Admin Center oder mithilfe von PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

Die oben genannten Vorgänge können an drei Stellen durchgeführt werden:
  
|||
|:-----|:-----|
|**Ort zum Beenden der Sitzung** <br/> |**Dauer der Maßnahme** <br/> |
|Im Exchange Admin Center oder mithilfe von PowerShell  <br/> |Voraussichtliche Verzögerung = innerhalb von 30 Minuten  <br/> |
|Azure Active Directory Admin Center  <br/> |Voraussichtliche Verzögerung = 60 Minuten  <br/> |
|Lokale Umgebung  <br/> |Voraussichtliche Verzögerung = 3 Stunden oder mehr  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a>So erhalten Sie eine schnelle Reaktion auf die Kündigung eines Kontos

 **Schnellste Option**: Verwenden Sie das Exchange Admin Center (über PowerShell) oder das Azure Active Directory Admin Center. In einer lokalen Umgebung kann es mehrere Stunden dauern, bis die Änderung über das Azure Active Directory-Synchronisierungstool synchronisiert wurde.
  
 **Schnellste Option für einen Benutzer mit lokaler Präsenz und im Exchange-Rechenzentrum**: Beenden Sie die Sitzung über das Azure Active Directory Admin Center bzw. das Exchange Admin Center, UND führen Sie die Änderung auch in der lokalen Umgebung auch. Andernfalls wird die Änderung im Azure Active Directory Admin Center bzw. Exchange Admin Center durch DirSync überschrieben.
  
## <a name="related-articles"></a>Verwandte Artikel

[Wiederherstellen eines Benutzers](restore-user.md)

[Zurücksetzen von Kennwörtern](reset-passwords.md)
