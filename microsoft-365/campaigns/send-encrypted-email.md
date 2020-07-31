---
title: Senden verschlüsselter E-Mail-Nachrichten
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Erfahren Sie, wie Sie verschlüsselte e-Mails mit Outlook senden.
ms.openlocfilehash: f5184de55ce07d5e669e98afb6e627833071c4ba
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526876"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Verschlüsseln oder beschriften Sie Ihre vertraulichen E-Mails

Ihre Daten und Kampagneninformationen sind wichtig und werden häufig vertraulich behandelt. Schützen Sie diese vertraulichen Informationen mithilfe von Verschlüsselungs-und Sensitivitäts Bezeichnungen, damit Sie und Ihre e-Mail-Empfänger die Informationen mit der für Sie erforderlichen Empfindlichkeit behandeln können.


## <a name="best-practices"></a>Bewährte Methoden

Bevor Sie e-Mails mit vertraulichen oder vertraulichen Informationen senden, sollten Sie Folgendes einschalten:

- **Verschlüsselung:** Sie können Ihre e-Mails verschlüsseln, um die Vertraulichkeit der Informationen in der e-Mail zu schützen. Wenn Sie eine e-Mail-Nachricht verschlüsseln, wird Sie von lesbarem Nur-Text in verschlüsselten Cypher-Text konvertiert. Nur der Empfänger mit dem privaten Schlüssel, der mit dem zum Verschlüsseln der Nachricht verwendeten öffentlichen Schlüssel übereinstimmt, kann die Nachricht zum Lesen entziffern. Jeder Empfänger ohne den entsprechenden privaten Schlüssel sieht jedoch unlesbaren Text. Ihr Administrator kann Regeln definieren, um Nachrichten automatisch zu verschlüsseln, die bestimmte Kriterien erfüllen. Beispielsweise kann Ihr Administrator eine Regel erstellen, die alle Nachrichten verschlüsselt, die außerhalb Ihrer Organisation gesendet werden, oder alle Nachrichten, die bestimmte Wörter oder Phrasen erwähnen. Alle Verschlüsselungsregeln werden automatisch angewendet.
- **Vertraulichkeits Bezeichnungen:** Ihre Kampagne kann auch Sensitivitäts Bezeichnungen einrichten, die Sie auf Ihre Dateien und e-Mails anwenden können, damit Sie mit den Informationsschutz Richtlinien Ihrer Kampagne konform bleiben. Wenn Sie eine Bezeichnung festlegen, bleibt die Bezeichnung mit Ihrer e-Mail erhalten, auch wenn Sie gesendet wird, beispielsweise indem Sie als Kopfzeile für Ihre Nachricht angezeigt wird.

![Diagramm einer e-Mail mit Beschriftungen für Bezeichnungen und Verschlüsselung](../media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Einrichtung

Wenn Sie eine Nachricht verschlüsseln möchten, die keine vordefinierte Regel erfüllt oder Ihr Administrator keine Regeln eingerichtet hat, können Sie vor dem Senden einer Nachricht eine Vielzahl unterschiedlicher Verschlüsselungsregeln anwenden. Wenn Sie eine verschlüsselte Nachricht von Outlook 2013 oder 2016 oder Outlook 2016 für Mac senden möchten, wählen Sie **Optionen > Berechtigungen**aus, und wählen Sie dann die benötigte Schutzoption aus. Sie können eine verschlüsselte Nachricht auch senden, indem Sie die Schaltfläche **schützen** in Outlook im Internet auswählen. Weitere Informationen finden Sie unter [senden, anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Administratoreinstellungen

Weitere Informationen zum Einrichten der e-Mail-Verschlüsselung finden Sie unter [e-Mail-Verschlüsselung in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).

### <a name="automatically-encrypt-email-messages"></a>E-Mail-Nachrichten automatisch verschlüsseln

Administratoren können e-Mail-Flussregeln erstellen, um automatisch e-Mail-Nachrichten zu schützen, die von Ihrer Kampagne gesendet und empfangen werden. Richten Sie Regeln zum Verschlüsseln von ausgehenden e-Mail-Nachrichten ein, und entfernen Sie die Verschlüsselung aus verschlüsselten Nachrichten, die innerhalb Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten von Ihrer Organisation gesendet 

Sie erstellen Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten mit den neuen Funktionen für die Office 365 Nachrichtenverschlüsselung (OM). Definieren Sie Nachrichtenfluss Regeln für die Auslösung der Nachrichtenverschlüsselung mit den neuen OM-Funktionen mithilfe des Exchange Admin Centers (EAC). 

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden. 
2. Wählen Sie die Kachel admin aus. 
3. Wählen Sie im Admin Center die Option admin Centers **> Exchange**aus. 

Weitere Informationen finden Sie unter [Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).

### <a name="brand-your-encryption-messages"></a>Branding Ihrer Verschlüsselungs Nachrichten

Sie können auch Ihr Kampagnen Branding anwenden, um das Aussehen und den Text in den e-Mail-Nachrichten anzupassen. Weitere Informationen finden Sie unter [Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).

