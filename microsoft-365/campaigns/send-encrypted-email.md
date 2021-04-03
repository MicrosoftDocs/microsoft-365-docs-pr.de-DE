---
title: Senden verschlüsselter E-Mail-Nachrichten
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Erfahren Sie, wie Sie verschlüsselte E-Mails mit Outlook senden.
ms.openlocfilehash: 209734bd52d1d97278d5632f035723758fe2e016
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576973"
---
# <a name="encrypt-or-label-your-sensitive-email"></a>Verschlüsseln oder beschriften Sie Ihre vertraulichen E-Mails

Ihre Daten und Kampagneninformationen sind wichtig und oft vertraulich. Schützen Sie diese vertraulichen Informationen mithilfe von Verschlüsselungs- und Vertraulichkeitsbezeichnungen, damit Sie und Ihre E-Mail-Empfänger die Informationen mit der benötigten Vertraulichkeit behandeln.

## <a name="best-practices"></a>Bewährte Methoden

Bevor Sie E-Mails mit vertraulichen oder vertraulichen Informationen senden, sollten Sie dies aktivieren:

- **Verschlüsselung:** Sie können Ihre E-Mails verschlüsseln, um den Datenschutz der Informationen in der E-Mail zu schützen. Wenn Sie eine E-Mail-Nachricht verschlüsseln, wird sie aus lesbarem Nur-Text in einen verkorkst-zyperlichen Text konvertiert. Nur der Empfänger, der über den privaten Schlüssel verfügt, der dem öffentlichen Schlüssel entspricht, der zum Verschlüsseln der Nachricht verwendet wird, kann die Nachricht zum Lesen entschlüsseln. Jeder Empfänger ohne den entsprechenden privaten Schlüssel wird jedoch unentschlüsselbarer Text angezeigt. Ihr Administrator kann Regeln definieren, um Nachrichten, die bestimmte Kriterien erfüllen, automatisch zu verschlüsseln. Beispielsweise kann Ihr Administrator eine Regel erstellen, die alle nachrichten verschlüsselt, die außerhalb Ihrer Organisation gesendet werden, oder alle Nachrichten, die bestimmte Wörter oder Ausdrücke erwähnen. Alle Verschlüsselungsregeln werden automatisch angewendet.
- **Vertraulichkeitsbezeichnungen:** Ihre Kampagne kann auch Vertraulichkeitsbezeichnungen einrichten, die Sie auf Ihre Dateien und E-Mails anwenden können, um sie mit den Informationsschutzrichtlinien Ihrer Kampagne kompatibel zu halten. Wenn Sie eine Bezeichnung festlegen, bleibt die Bezeichnung bei Ihrer E-Mail erhalten, auch wenn sie gesendet wird , z. B. indem sie als Kopfzeile für Ihre Nachricht angezeigt wird.

![Diagramm einer E-Mail mit Beschriftungen und Verschlüsselung](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a>Einrichtung

Wenn Sie eine Nachricht verschlüsseln möchten, die einer vordefinierten Regel nicht gerecht wird oder Ihr Administrator keine Regeln eingerichtet hat, können Sie eine Vielzahl von verschiedenen Verschlüsselungsregeln anwenden, bevor Sie die Nachricht senden. Wenn Sie eine verschlüsselte Nachricht von Outlook 2013 oder 2016 oder Outlook 2016 für Mac senden möchten, wählen Sie **Optionen > Berechtigungen** aus, und wählen Sie dann die von Ihnen benötigten Schutzoption aus. Sie können auch eine verschlüsselte Nachricht senden, indem Sie die **Schaltfläche** Schützen in Outlook im Web auswählen. Weitere Informationen finden Sie unter [Senden, Anzeigen und Antworten auf verschlüsselte Nachrichten in Outlook für PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).

## <a name="admin-settings"></a>Administratoreinstellungen

Weitere Informationen zum Einrichten der E-Mail-Verschlüsselung finden Sie unter [E-Mail-Verschlüsselung in Microsoft 365](../compliance/email-encryption.md).

### <a name="automatically-encrypt-email-messages"></a>Automatisches Verschlüsseln von E-Mail-Nachrichten

Administratoren können Nachrichtenflussregeln erstellen, um E-Mail-Nachrichten, die von Ihrer Kampagne gesendet und empfangen werden, automatisch zu schützen. Richten Sie Regeln ein, um ausgehende E-Mail-Nachrichten zu verschlüsseln und die Verschlüsselung aus verschlüsselten Nachrichten zu entfernen, die aus Ihrer Organisation oder aus Antworten auf verschlüsselte Nachrichten, die von Ihrer Organisation gesendet werden, kommen.

Sie erstellen Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten mit den neuen Office 365 Message Encryption (OME)-Funktionen. Definieren Von Nachrichtenflussregeln zum Auslösen der Nachrichtenverschlüsselung mit den neuen OME-Funktionen mithilfe des Exchange Admin Center (EAC). 

1. Melden Sie sich in einem Webbrowser mit einem Arbeits- oder Schulkonto an, dem globale Administratorberechtigungen erteilt wurden.
2. Wählen Sie die Kachel Admin aus.
3. Wählen Sie im Admin Center **admin center > Exchange aus.**

Weitere Informationen finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten.](../compliance/define-mail-flow-rules-to-encrypt-email.md)

### <a name="brand-your-encryption-messages"></a>Ihre Verschlüsselungsnachrichten brandmarken

Sie können auch Ihr Kampagnenbranding anwenden, um das Erscheinungsbild und den Text in den E-Mail-Nachrichten anzupassen. Weitere Informationen finden Sie unter [Add your organization's brand to your encrypted messages](../compliance/email-encryption.md).