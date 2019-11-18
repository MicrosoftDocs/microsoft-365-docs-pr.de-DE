---
title: Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.
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
description: Mit Office 365 erweiterten Nachrichten Verschlüsselungsfunktionen über Office 365-Nachrichtenverschlüsselung (OM) können Sie Ihre e-Mail-Sicherheit erweitern, indem Sie ein Ablaufdatum für e-Mails über eine benutzerdefinierte Marken Vorlage festlegen.
ms.openlocfilehash: 6790cc7103ad098419bde96b93738424626cd0cc
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38686109"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a>Festlegen eines Ablaufdatums für E-Mails, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.

Office 365 erweiterte Nachrichtenverschlüsselung ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Non-Profit-Mitarbeiter Preise), Office 365 Enterprise E5 (Nonprofit-Mitarbeiter Preise) und Office 365 Education A5 enthalten. Wenn Ihre Organisation über ein Abonnement verfügt, das Office 365 erweiterte Nachrichtenverschlüsselung nicht enthält, können Sie es mit dem Microsoft 365 E5 Compliance-SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Preise für gemeinnützige Mitarbeiter) oder mit dem Office 365 Advanced erwerben. Compliance-SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Preise für gemeinnützige Mitarbeiter) oder Office 365 SKUs.

Sie können Nachrichtenablauf bei e-Mails verwenden, die Ihre Benutzer an externe Empfänger senden, die das OM-Portal zum Zugriff auf verschlüsselte e-Mails verwenden. Sie erzwingen, dass Empfänger das OM-Portal verwenden, um verschlüsselte e-Mails anzuzeigen und zu beantworten, die von Ihrer Organisation gesendet werden, indem Sie eine benutzerdefinierte Marken Vorlage verwenden, die ein Ablaufdatum in Windows PowerShell angibt.

Wenn Sie als globaler O365-Administrator Ihre Unternehmensmarke anwenden, um das Aussehen der e-Mail-Nachrichten Ihrer Office 365 Organisation anzupassen, können Sie auch einen Ablauf für diese e-Mail-Nachrichten angeben. Mit Office 365 erweiterten Nachrichtenverschlüsselung können Sie mehrere Vorlagen für verschlüsselte e-Mails erstellen, die aus Ihrer Organisation stammen. Mithilfe einer Vorlage können Sie steuern, wie lange Empfänger Zugriff auf von Ihren Benutzern gesendete e-Mails haben.

Wenn ein Endbenutzer e-Mails erhält, für die ein Ablaufdatum festgelegt wurde, sieht der Benutzer das Ablaufdatum in der Wrapper-e-Mail. Wenn ein Benutzer versucht, eine abgelaufene e-Mail zu öffnen, wird im OM-Portal ein Fehler angezeigt.

Sie können nur Ablaufdaten für e-Mails an externe Empfänger festlegen.

Bei Office 365 erweiterten Nachrichtenverschlüsselung wendet der Office 365 den Wrapper bei jeder Anwendung des benutzerdefinierten Branding auf e-Mail an, die der Nachrichtenfluss Regel entspricht, auf die die Vorlage angewendet wird. Außerdem können Sie die Ablaufzeit nur verwenden, wenn Sie benutzerdefiniertes Branding verwenden.

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a>Erstellen einer benutzerdefinierten Branding-Vorlage zum Erzwingen des e-Mail-Ablaufs mithilfe von PowerShell

1. Stellen Sie eine [Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) mit einem Konto her, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt.

2. Führen Sie das Cmdlet New-OMEConfiguration aus.

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

Dabei gilt:

- `Identity`ist der Name der benutzerdefinierten Vorlage.

- `ExternalMailExpiryInDays`Gibt an, wie viele Tage e-Mails von Empfängern aufbewahrt werden können, bevor Sie ablaufen. Sie können einen beliebigen Wert zwischen 1 bis 730 Tagen verwenden.

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Weitere Informationen zu Office 365 erweiterte Nachrichtenverschlüsselung

- [Erweiterte Office 365-Nachrichtenverschlüsselung](ome-advanced-message-encryption.md)

- [Widerrufen von E-Mails, die von der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden](revoke-ome-encrypted-mail.md)

- [Beschreibung des Nachrichtenrichtlinien-und Kompatibilitätsdiensts](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
