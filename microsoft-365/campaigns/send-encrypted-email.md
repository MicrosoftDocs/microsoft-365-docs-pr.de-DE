---
title: Verschlüsselte e-Mail senden
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
ms.openlocfilehash: 16e6a6977d7cd8ec4d6bf59adbcd196b14995752
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183299"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Verschlüsseln oder bezeichnen von vertraulichen e-Mails

Ihre Daten und Kampagneninformationen sind wichtig und werden häufig vertraulich behandelt. Schützen Sie diese vertraulichen Informationen mithilfe von Verschlüsselungs-und Sensitivitäts Bezeichnungen, damit Sie und Ihre e-Mail-Empfänger die Informationen mit der für Sie erforderlichen Empfindlichkeit behandeln können.


## <a name="best-practices"></a>Bewährte Methoden

Bevor Sie e-Mails mit vertraulichen oder vertraulichen Informationen senden, sollten Sie Folgendes einschalten:

- **Verschlüsselung:** Sie können Ihre e-Mails verschlüsseln, um die Vertraulichkeit der Informationen in der e-Mail zu schützen. Wenn Sie eine e-Mail-Nachricht verschlüsseln, wird Sie von lesbarem Nur-Text in verschlüsselten Cypher-Text konvertiert. Nur der Empfänger mit dem privaten Schlüssel, der mit dem zum Verschlüsseln der Nachricht verwendeten öffentlichen Schlüssel übereinstimmt, kann die Nachricht zum Lesen entziffern. Jeder Empfänger ohne den entsprechenden privaten Schlüssel sieht jedoch unlesbaren Text. Ihr Administrator kann Regeln definieren, um Nachrichten automatisch zu verschlüsseln, die bestimmte Kriterien erfüllen. Beispielsweise kann Ihr Administrator eine Regel erstellen, die alle Nachrichten verschlüsselt, die außerhalb Ihrer Organisation gesendet werden, oder alle Nachrichten, die bestimmte Wörter oder Phrasen erwähnen. Alle Verschlüsselungsregeln werden automatisch angewendet.
- **Vertraulichkeits Bezeichnungen:** Ihre Kampagne kann auch Sensitivitäts Bezeichnungen einrichten, die Sie auf Ihre Dateien und e-Mails anwenden können, damit Sie mit den Informationsschutz Richtlinien Ihrer Kampagne konform bleiben. Wenn Sie eine Bezeichnung festlegen, bleibt die Bezeichnung mit Ihrer e-Mail erhalten, auch wenn Sie gesendet wird, beispielsweise indem Sie als Kopfzeile für Ihre Nachricht angezeigt wird.

![Diagramm einer e-Mail mit Beschriftungen für Bezeichnungen und Verschlüsselung](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a>Einrichtung

Wenn Sie eine Nachricht verschlüsseln möchten, die keine vordefinierte Regel erfüllt oder Ihr Administrator keine Regeln eingerichtet hat, können Sie vor dem Senden einer Nachricht eine Vielzahl unterschiedlicher Verschlüsselungsregeln anwenden. Wenn Sie eine verschlüsselte Nachricht von Outlook 2013 oder 2016 oder Outlook 2016 für Mac senden möchten, wählen Sie **Optionen #a0 Berechtigungen**aus, und wählen Sie dann die benötigte Schutzoption aus. Sie können eine verschlüsselte Nachricht auch senden, indem Sie die Schaltfläche **schützen** in Outlook im Internet auswählen. Weitere Informationen finden Sie unter [senden, anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PC](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).

## <a name="admin-settings"></a>Administratoreinstellungen

Weitere Informationen zum Einrichten der e-Mail-Verschlüsselung finden Sie unter [e-Mail-Verschlüsselung in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).

### <a name="automatically-encrypt-email-messages"></a>E-Mail-Nachrichten automatisch verschlüsseln

Administratoren können e-Mail-Flussregeln erstellen, um automatisch e-Mail-Nachrichten zu schützen, die von Ihrer Kampagne gesendet und empfangen werden. Einrichten von Regeln zum Verschlüsseln von ausgehenden e-Mail-Nachrichten und zum Entfernen der Verschlüsselung von verschlüsselten Nachrichten, die innerhalb Ihrer Organisation oder von Antworten auf verschlüsselte Nachrichten von Ihrer Organisation gesendet 

Sie erstellen Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten mit den neuen Funktionen für die Office 365 Nachrichtenverschlüsselung (OM). Definieren Sie Nachrichtenfluss Regeln für die Auslösung der Nachrichtenverschlüsselung mit den neuen OM-Funktionen mithilfe des Exchange Admin Centers (EAC). 

1. Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei Office 365 an. 
2. Wählen Sie die Kachel admin aus. 
3. Wählen Sie im Office 365 Admin Center die Option admin Centers **#a0 Exchange**aus. 

Weitere Informationen finden Sie unter [Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).

### <a name="brand-your-encryption-messages"></a>Branding Ihrer Verschlüsselungs Nachrichten

Sie können auch Ihr Kampagnen Branding anwenden, um das Aussehen und den Text in den e-Mail-Nachrichten anzupassen. Weitere Informationen finden Sie unter [Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).

