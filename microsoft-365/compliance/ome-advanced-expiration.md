---
title: Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Verwenden Office 365 Advanced Message Encryption, um Ihre E-Mail-Sicherheit zu erhöhen, indem Sie ein Ablaufdatum für E-Mails über eine benutzerdefinierte Markenvorlage festlegen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927785"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.

Office 365 Advanced Message Encryption ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Preis für gemeinnützige Mitarbeiter), Office 365 Enterprise E5 (Preis für gemeinnützige Mitarbeiter) und Office 365 Education A5 enthalten. Wenn Ihre Organisation über ein Abonnement verfügt, das Office 365 Advanced Message Encryption nicht enthält, können Sie es mit dem Microsoft 365 E5 Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder das Office 365 Advanced Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder Office 365 SKUs erwerben.

Sie können den Nachrichtenablauf für E-Mails verwenden, die Ihre Benutzer an externe Empfänger senden, die das OME-Portal für den Zugriff auf verschlüsselte E-Mails verwenden. Sie erzwingen, dass Empfänger das OME-Portal verwenden, um verschlüsselte E-Mails, die von Ihrer Organisation gesendet werden, mithilfe einer benutzerdefinierten Markenvorlage anzeigen und beantworten zu können, die ein Ablaufdatum in Windows PowerShell.

Als globaler Office 365 können Sie auch einen Ablauf für diese E-Mail-Nachrichten angeben, wenn Sie Ihre Unternehmensmarke anwenden, um das Erscheinungsbild der E-Mail-Nachrichten Ihrer Organisation anzupassen. Mit Office 365 Advanced Message Encryption können Sie mehrere Vorlagen für verschlüsselte E-Mails erstellen, die aus Ihrer Organisation stammen. Mithilfe einer Vorlage können Sie steuern, wie lange Empfänger Zugriff auf von Ihren Benutzern gesendete E-Mails haben.

Wenn ein Endbenutzer E-Mails empfängt, für die ein Ablaufdatum festgelegt ist, wird dem Benutzer das Ablaufdatum in der Wrapper-E-Mail angezeigt. Wenn ein Benutzer versucht, eine abgelaufene E-Mail zu öffnen, wird im OME-Portal ein Fehler angezeigt.

Sie können nur Ablaufdaten für E-Mails an externe Empfänger festlegen.

Mit Office 365 Advanced Message Encryption wendet das Office 365 den Wrapper auf E-Mails an, die der Nachrichtenflussregel entspricht, auf die Sie die Vorlage anwenden. Darüber hinaus können Sie den Ablauf nur verwenden, wenn Sie benutzerdefiniertes Branding verwenden.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Erstellen einer benutzerdefinierten Brandingvorlage zum Erzwingen des Ablaufs von E-Mails mithilfe von PowerShell

1. [Verbinden, Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) mit einem Konto zu erstellen, das über globale Administratorberechtigungen in Ihrer Organisation verfügt.

2. Führen Sie New-OMEConfiguration cmdlet aus.

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

Dabei gilt:

- `Identity` ist der Name der benutzerdefinierten Vorlage.

- `ExternalMailExpiryInDays` gibt an, wie viele Tage Empfänger E-Mails behalten können, bevor sie ablaufen. Sie können einen beliebigen Wert zwischen 1 und 730 Tagen verwenden.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Weitere Informationen zu Office 365 Advanced Message Encryption

- [Erweiterte Office 365-Nachrichtenverschlüsselung](ome-advanced-message-encryption.md)

- [Widerrufen von E-Mails, die von der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden](revoke-ome-encrypted-mail.md)

- [Beschreibung des Nachrichtenrichtlinien- und Compliancediensts](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)