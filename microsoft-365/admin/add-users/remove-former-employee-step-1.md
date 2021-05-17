---
title: Schritt 1 – Beenden der Anmeldung eines Mitarbeiters bei Microsoft 365
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
description: Blockieren der Anmeldung eines ehemaligen Mitarbeiters und Sperren des Zugriffs auf Microsoft 365-Dienste.
ms.openlocfilehash: 60f4cf6b5c9a0b5dc2023b3ef7b6460685142d07
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244252"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a>Schritt 1 – Verhindern, dass sich ein ehemaliger Mitarbeiter an der Anmeldung einloggt und den Zugriff auf Microsoft 365-Dienste blockiert

Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, sollten Sie sein Kennwort zurücksetzen. Erzwingen Sie in diesem Schritt das Abmelden des Benutzers von Microsoft 365.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie das Feld neben dem Namen des Benutzers aus, und wählen Sie dann **Kennwort zurücksetzen aus.**
3. Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen aus.** (Senden Sie es nicht an sie.)
4. Wählen Sie den Namen des Benutzers aus, um  zum Eigenschaftenbereich zu wechseln, und wählen Sie auf der Registerkarte Konto die Option **Abmelden initiieren aus.**

Innerhalb einer Stunde – oder nachdem sie die aktuelle Microsoft 365-Seite verlassen haben, auf der sie sich befinden – werden sie aufgefordert, sich erneut zu registrieren. Ein Zugriffstoken ist für eine Stunde gut, daher hängt die Zeitachse davon ab, wie viel Zeit auf diesem Token noch bleibt und ob sie aus ihrer aktuellen Webseite navigieren.
  
> [!IMPORTANT]
> Wenn sich der Benutzer in Outlook im Web befindet und einfach in ihrem Postfach herumklickt, wird er möglicherweise nicht sofort angezeigt. Sobald sie eine andere Kachel auswählen, z. B. OneDrive, oder ihren Browser aktualisieren, wird die Abmeldeung initiiert.
  
Informationen zum sofortigen Abmelden eines Benutzers mithilfe von PowerShell finden Sie im [Cmdlet Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)
  
Weitere Informationen dazu, wie lange es dauert, für jemand die E-Mail-Nutzung zu beenden, finden Sie unter [Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a>Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf Microsoft 365-Dienste

> [!IMPORTANT]
 > Das Blockieren eines Kontos kann bis zu 24 Stunden in Kraft treten. Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, führen Sie die obigen Schritte aus, und setzen Sie ihr Kennwort zurück.

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie unter dem Namen des Benutzers das Symbol für **Diesen Benutzer blockieren aus.**
3. Wählen **Sie Anmelden des Benutzers blockieren** aus, und wählen Sie dann Speichern **aus.**

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf E-Mail (Exchange Online)

Wenn Sie über E-Mails im Rahmen Ihres Microsoft 365-Abonnements verfügen, melden Sie sich beim Exchange Admin Center an, und führen Sie die folgenden Schritte aus, um ihren ehemaligen Mitarbeiter am Zugriff auf seine E-Mails zu blockieren.
  
1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.
2. Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**.
3. Doppelklicken Sie auf den Benutzer, und wechseln Sie zur **Seite Postfachfeatures.** Wählen **Sie unter Mobile** Geräte die Option **Exchange ActiveSync** deaktivieren und OWA für Geräte deaktivieren **aus,** und **antworten** Sie bei Aufforderung mit Ja auf beide.
4. Wählen **Sie unter E-Mail-Konnektivität** **die Option Deaktivieren** aus, und antworten Sie **auf Ja,** wenn Sie dazu aufgefordert werden.
