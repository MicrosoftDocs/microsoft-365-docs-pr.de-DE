---
title: Schritt 7 – Löschen des Benutzerkontos eines ehemaligen Mitarbeiters
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
ms.openlocfilehash: e2e1b234eaee3818321761af8f737bad8d131b62
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286321"
---
# <a name="step-7---delete-a-former-employees-user-account"></a>Schritt 7 – Löschen des Benutzerkontos eines ehemaligen Mitarbeiters

Nachdem Sie auf alle Benutzerdaten des ehemaligen Mitarbeiters zugegriffen und diese gespeichert haben, können Sie das Konto des ehemaligen Mitarbeiters löschen.

> [!IMPORTANT]
> Löschen Sie das Konto nicht, wenn Sie eine E-Mail-Weiterleitung eingerichtet oder das Konto in ein freigegebenes Postfach konvertiert haben. Für beide Funktionen wird das Konto benötigt, damit die Weiterleitung oder Postfachfreigabe funktioniert.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Namen des Mitarbeiters aus, den Sie löschen möchten.
3. Wählen Sie unter dem Namen des Benutzers **"Benutzer löschen"** aus. Wählen Sie die gewünschten Optionen für diesen Benutzer aus, und wählen Sie dann **Benutzer löschen** aus. Wenn Sie bereits einem anderen Benutzer Zugriff auf die E-Mails und OneDrive dieses Benutzers gewährt haben, müssen Sie dies hier nicht erneut tun.

Wenn Sie einen Benutzer löschen, wird das Konto ungefähr 30 Tage lang deaktiviert (inaktiv). Sie haben in dieser Zeit noch die Möglichkeit, das Konto wiederherzustellen, bevor es endgültig gelöscht wird.

## <a name="watch-delete-a-former-employees-user-account"></a>Überwachung: Löschen des Benutzerkontos eines ehemaligen Mitarbeiters

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR]

Wenn Sie dieses Video hilfreich fanden, schauen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](../../business-video/index.yml), an.

## <a name="does-your-organization-use-active-directory"></a>Verwendet Ihre Organisation Active Directory?

Wenn Ihre Organisation Benutzerkonten mit Microsoft 365 aus einer lokalen Active Directory-Umgebung synchronisiert, müssen Sie diese Benutzerkonten in Ihrem lokalen Active Directory-Dienst löschen und wiederherstellen. Sie können sie nicht in Office 365 löschen und wiederherstellen.

Informationen zum Löschen und Wiederherstellen eines Benutzerkontos in Active Directory finden Sie unter [Löschen eines Benutzerkontos.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))
  
Wenn Sie Azure Active Directory verwenden, lesen Sie das [PowerShell-Cmdlet "Remove-MsolUser".](/powershell/module/msonline/remove-msoluser)
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters

Hier finden Sie Informationen dazu, wie Sie die E-Mail-Nutzung für einen Mitarbeiter beenden können (Exchange).

<br>

****

|Mögliche Aktionen|Wie geht das?|
|:-----|:-----|
|Sitzung beenden (z. B. Outlook im Web, Outlook, Exchange Active Sync usw.) und Öffnen einer neuen Sitzung erzwingen|Kennwort zurücksetzen|
|Sitzung beenden und Zugriff auf zukünftige Sitzungen (für alle Protokolle) sperren|Deaktivieren Sie das Konto. Beispiel: (im Exchange Admin Center oder mithilfe von PowerShell): <p>  `Set-Mailbox user@contoso.com -AccountDisabled:$true`|
|Sitzung für ein bestimmtes Protokoll (z. B. ActiveSync) beenden|Deaktivieren Sie das Protokoll. Beispiel: (im Exchange Admin Center oder mithilfe von PowerShell): <p>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false`|
|

Die oben genannten Vorgänge können an drei Stellen ausgeführt werden:
  
<br>

****

|Ort zum Beenden der Sitzung|Dauer der Maßnahme|
|---|---|
|Im Exchange Admin Center oder mithilfe von PowerShell|Voraussichtliche Verzögerung = innerhalb von 30 Minuten|
|Azure Active Directory Admin Center|Voraussichtliche Verzögerung = 60 Minuten|
|Lokale Umgebung|Voraussichtliche Verzögerung = 3 Stunden oder mehr|
|

### <a name="how-to-get-fastest-response-for-account-termination"></a>So erhalten Sie eine schnelle Reaktion auf die Kündigung eines Kontos

**Schnellste Option**: Verwenden Sie das Exchange Admin Center (über PowerShell) oder das Azure Active Directory Admin Center. In einer lokalen Umgebung kann es mehrere Stunden dauern, bis die Änderung über das Azure Active Directory-Synchronisierungstool synchronisiert wurde.
  
**Schnellste Option für einen Benutzer mit lokaler Präsenz und im Exchange-Rechenzentrum**: Beenden Sie die Sitzung über das Azure Active Directory Admin Center bzw. das Exchange Admin Center, UND führen Sie die Änderung auch in der lokalen Umgebung auch. Andernfalls wird die Änderung im Azure Active Directory Admin Center bzw. Exchange Admin Center durch DirSync überschrieben.
  
## <a name="related-content"></a>Verwandte Inhalte

[Wiederherstellen eines Benutzers](restore-user.md) (Artikel)/Zurücksetzen [von Kennwörtern](reset-passwords.md) (Artikel)
