---
title: 'Schritt 1: Beenden der Anmeldung eines Mitarbeiters bei Microsoft 365'
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
description: Blockieren der Anmeldung eines ehemaligen Mitarbeiters und Blockieren des Zugriffs auf Microsoft 365 Dienste.
ms.openlocfilehash: 58b65a0a886460e8be01635c857433773cfc9059
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177117"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Schritt 1: Verhindern, dass sich ein ehemaliger Mitarbeiter anmeldet und den Zugriff auf Microsoft 365 Dienste blockiert

Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, sollten Sie sein Kennwort zurücksetzen. Erzwingen Sie in diesem Schritt, dass sich der Benutzer von Microsoft 365 abmeldet.

> [!NOTE]
> Sie müssen ein globaler Administrator sein, um die Abmeldung für andere Administratoren zu initiieren. Für Benutzer, die keine Administratoren sind, können Sie einen Benutzeradministrator oder einen Helpdesk-Administratorbenutzer verwenden, um diese Aktion auszuführen. [Weitere Informationen zu den Administratorrollen](about-admin-roles.md)

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie das Kontrollkästchen neben dem Benutzernamen aus, und wählen Sie dann **Kennwort zurücksetzen** aus.
3. Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen** aus. (Senden Sie es nicht an sie.)
4. Wählen Sie den Namen des Benutzers aus, um zum Eigenschaftenbereich zu wechseln, und wählen Sie auf der Registerkarte **"Konto"** die Option **"Aus allen Sitzungen abmelden" aus.**

Innerhalb einer Stunde – oder nachdem sie die aktuelle Microsoft 365 Seite verlassen haben, auf der sie sich befinden – werden sie aufgefordert, sich erneut anzumelden. Ein Zugriffstoken ist eine Stunde lang gut, daher hängt die Zeitachse davon ab, wie viel Zeit für dieses Token verbleibt und ob er aus seiner aktuellen Webseite navigiert.
  
> [!IMPORTANT]
> Wenn sich der Benutzer in Outlook im Web befindet und einfach nur in sein Postfach klickt, wird er möglicherweise nicht sofort gestartet. Sobald sie eine andere Kachel auswählen, z. B. OneDrive, oder ihren Browser aktualisieren, wird die Abmeldung initiiert.
  
Informationen zum sofortigen Abmelden eines Benutzers mitHilfe von PowerShell finden Sie im Cmdlet ["Revoke-AzureADUserAllRefreshToken".](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)
  
Weitere Informationen dazu, wie lange es dauert, für jemand die E-Mail-Nutzung zu beenden, finden Sie unter [Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf Microsoft 365 Dienste

> [!IMPORTANT]
 > Das Blockieren eines Kontos kann bis zu 24 Stunden dauern, bis es wirksam wird. Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, führen Sie die oben beschriebenen Schritte aus, und setzen Sie das Kennwort zurück.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie unter dem Namen des Benutzers das Symbol für **"Diesen Benutzer blockieren"** aus.
3. Wählen Sie **"Benutzeranmeldung blockieren" und** dann **"Speichern"** aus.

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf E-Mail (Exchange Online)

Wenn Sie E-Mails als Teil Ihres Microsoft 365-Abonnements haben, melden Sie sich beim Exchange Admin Center an, und führen Sie die folgenden Schritte aus, um zu verhindern, dass Ihr ehemaliger Mitarbeiter auf seine E-Mails zugreift.
  
1. Wechseln Sie zum <a href="https://admin.exchange.microsoft.com/" target="_blank">Exchange Admin Center</a>.
2. Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**.
3. Doppelklicken Sie auf den Benutzer, und wechseln Sie zu **"Einstellungen für E-Mail-Apps verwalten"** unter **"E-Mail-Apps".** **Deaktivieren** Sie den Schieberegler für alle Optionen. **Mobile (Exchange ActiveSync)**, **Outlook im Web**, **Outlook Desktop (MAPI)**, **Exchange Webdienste,** **POP3** und **IMAP**.
4. Wählen Sie **Speichern**.
