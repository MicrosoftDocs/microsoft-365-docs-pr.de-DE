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
description: Erfahren Sie, wie Sie verschlüsselte E-Mails mithilfe von Outlook senden.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044216"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Verschlüsseln oder beschriften Sie Ihre vertraulichen E-Mails

Ihre Daten und Kampagneninformationen sind wichtig und häufig vertraulich. Schützen Sie diese vertraulichen Informationen mithilfe von Verschlüsselungs- und Vertraulichkeitsbezeichnungen, damit Sie und Ihre E-Mail-Empfänger die Informationen mit der benötigten Vertraulichkeit behandeln.

## <a name="best-practices"></a>Bewährte Methoden

Bevor Sie E-Mails mit vertraulichen oder vertraulichen Informationen senden, sollten Sie dies aktivieren:

- **Verschlüsselung:** Sie können Ihre E-Mails verschlüsseln, um den Datenschutz der Informationen in der E-Mail zu schützen. Wenn Sie eine E-Mail-Nachricht verschlüsseln, wird sie von lesbarem nur-Text in scrambled -Text konvertiert. Nur der Empfänger, der über den privaten Schlüssel verfügt, der dem zum Verschlüsseln der Nachricht verwendeten öffentlichen Schlüssel entspricht, kann die Nachricht zum Lesen entschlüsseln. Jeder Empfänger ohne den entsprechenden privaten Schlüssel sieht jedoch unentschlüsselten Text. Ihr Administrator kann Regeln definieren, um Nachrichten, die bestimmte Kriterien erfüllen, automatisch zu verschlüsseln. Beispielsweise kann Ihr Administrator eine Regel erstellen, die alle nachrichten verschlüsselt, die außerhalb Ihrer Organisation gesendet werden, oder alle Nachrichten, die bestimmte Wörter oder Ausdrücke erwähnen. Verschlüsselungsregeln werden automatisch angewendet.
- **Vertraulichkeitsbezeichnungen:** Ihre Kampagne kann auch Vertraulichkeitsbezeichnungen einrichten, die Sie auf Ihre Dateien und E-Mails anwenden können, um sie mit den Informationsschutzrichtlinien Ihrer Kampagne kompatibel zu halten. Wenn Sie eine Bezeichnung festlegen, bleibt die Bezeichnung auch dann bei Ihrer E-Mail erhalten, wenn sie gesendet wird, z. B. indem sie als Kopfzeile ihrer Nachricht angezeigt wird.

![Diagramm einer E-Mail mit Beschriftungen und Verschlüsselung](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Einrichtung

Wenn Sie eine Nachricht verschlüsseln möchten, die keine vordefinierte Regel erfüllt, oder Wenn Ihr Administrator keine Regeln eingerichtet hat, können Sie eine Vielzahl verschiedener Verschlüsselungsregeln anwenden, bevor Sie die Nachricht senden. Wenn Sie eine verschlüsselte Nachricht aus Outlook 2013 oder 2016 oder Outlook 2016 für Mac senden möchten, wählen Sie Optionen **>** Berechtigungen aus, und wählen Sie dann die schutzoption aus, die Sie benötigen. Sie können auch eine verschlüsselte  Nachricht senden, indem Sie in Outlook im Web auf die Schaltfläche "Schützen" klicken. Weitere Informationen finden Sie unter Senden, Anzeigen und Antworten auf verschlüsselte [Nachrichten in Outlook für PC.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)

## <a name="admin-settings"></a>Administratoreinstellungen

Weitere Informationen zum Einrichten der E-Mail-Verschlüsselung finden Sie bei [der E-Mail-Verschlüsselung in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)

### <a name="automatically-encrypt-email-messages"></a>Automatisches Verschlüsseln von E-Mail-Nachrichten

Administratoren können Nachrichtenflussregeln erstellen, um automatisch E-Mail-Nachrichten zu schützen, die von Ihrer Kampagne gesendet und empfangen werden. Richten Sie Regeln ein, um alle ausgehenden E-Mail-Nachrichten zu verschlüsseln und die Verschlüsselung von verschlüsselten Nachrichten zu entfernen, die von innerhalb Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten von Ihrer Organisation gesendet werden.

Sie erstellen Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten mit den neuen Funktionen der Office 365-Nachrichtenverschlüsselung (Office 365 Message Encryption, OME). Definieren von Nachrichtenflussregeln zum Auslösen der Nachrichtenverschlüsselung mit den neuen OME-Funktionen mithilfe der Exchange Admin Center (EAC). 

1. Melden Sie sich in einem Webbrowser mit einem Arbeits- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden.
2. Wählen Sie die Kachel "Admin" aus.
3. Wählen Sie im Admin Center admin **center > Exchange aus.**

Weitere Informationen finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)

### <a name="brand-your-encryption-messages"></a>Ihre Verschlüsselungsnachrichten mit einem Markenbranding bebranden

Sie können Ihr Kampagnenbranding auch anwenden, um das Aussehen und den Text in den E-Mail-Nachrichten anzupassen. Weitere Informationen finden Sie unter "Hinzufügen der Marke Ihrer [Organisation zu Ihren verschlüsselten Nachrichten".](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)
