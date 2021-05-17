---
title: Erweiterte Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Die erweiterte Nachrichtenverschlüsselung unterstützt Organisationen bei der Erfüllung ihrer Complianceverpflichtungen, indem Administratoren noch mehr mit geschützten Nachrichten tun können.
ms.openlocfilehash: 8c650c47c1853102e4e2d142040e49724ef707e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923955"
---
# <a name="advanced-message-encryption"></a>Erweiterte Nachrichtenverschlüsselung

Office 365 Advanced Message Encryption ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Preis für gemeinnützige Mitarbeiter), Office 365 Enterprise E5 (Preis für gemeinnützige Mitarbeiter) und Office 365 Education A5 enthalten. Wenn Ihre Organisation über ein Abonnement verfügt, das keine Office 365 Advanced Message Encryption, Sie können es mit dem Microsoft 365 E5 Compliance-SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder das Office 365 Advanced Compliance-SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter), Office 365 SKUs oder das Microsoft 365 E5/A5 Information Protection and Governance SKU-Add-On für Microsoft 365 A3/E3 erwerben.

Die erweiterte Nachrichtenverschlüsselung unterstützt Kunden bei der Erfüllung von Complianceverpflichtungen, die flexiblere Kontrollen über externe Empfänger und ihren Zugriff auf verschlüsselte E-Mails erfordern. Mit der erweiterten Nachrichtenverschlüsselung in Office 365 können Sie vertrauliche E-Mails steuern, die außerhalb der Organisation freigegeben wurden, mit automatischen Richtlinien. Sie konfigurieren diese Richtlinien, um vertrauliche Informationstypen wie PII-, Finanz- oder Integritäts-IDs zu identifizieren, oder Sie können Schlüsselwörter verwenden, um den Schutz zu verbessern. Nachdem Sie die Richtlinien konfiguriert haben, koppeln Sie Richtlinien mit benutzerdefinierten E-Mail-Vorlagen mit Markennamen und fügen dann ein Ablaufdatum für die zusätzliche Kontrolle von E-Mails hinzu, die zur Richtlinie passen. Außerdem können Administratoren verschlüsselte E-Mails, auf die extern über ein sicheres Webportal zugegriffen wird, weiter steuern, indem sie den Zugriff auf die E-Mails jederzeit wieder ensprechen.

Sie können nur ein Ablaufdatum für E-Mails widerrufen und festlegen, die an externe Empfänger gesendet werden.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Erste Schritte mit Office 365 Advanced Message Encryption

In den folgenden Artikeln wird beschrieben, wie Sie die erweiterte Nachrichtenverschlüsselung einrichten und verwenden.

Ihre Organisation muss über ein Abonnement verfügen, das Office 365 Advanced Message Encryption. Ausführliche Informationen zu unterstützten Abonnements finden Sie in der [Beschreibung des Nachrichtenrichtlinien- und Compliancediensts](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Wenn Sie noch keine Office 365-Nachrichtenverschlüsselung eingerichtet haben, lesen Sie [Einrichten neuer Office 365-Nachrichtenverschlüsselung Funktionen](set-up-new-message-encryption-capabilities.md).

Mit der erweiterten Nachrichtenverschlüsselung sind Sie nicht auf eine einzelne Brandingvorlage beschränkt. Stattdessen können Sie mehrere Brandingvorlagen erstellen und verwenden. Weitere Informationen finden Sie unter [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).

[Legen Sie ein Ablaufdatum für E-Mails, die von Office 365 Advanced Message Encryption.](ome-advanced-expiration.md) Steuern Sie vertrauliche E-Mails, die außerhalb der Organisation freigegeben werden, mit automatischen Richtlinien, die den Schutz verbessern, indem Sie den Zugriff über ein sicheres Webportal auf verschlüsselte E-Mails ablaufen.

[Widerrufen von E-Mails, die Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md). Steuern Sie vertrauliche E-Mails, die außerhalb der Organisation freigegeben wurden, und verbessern Sie den Schutz, indem Sie den Zugriff über ein sicheres Webportal auf verschlüsselte E-Mails enkeln.  

Mit Office 365 Advanced Message Encryption, wendet Microsoft bei jeder Anwendung einer benutzerdefinierten Brandingvorlage einen Wrapper auf E-Mails an, der der Nachrichtenflussregel entspricht, auf die Sie die Vorlage anwenden. Sie können Nur Nachrichten widerrufen und Ablaufdaten auf Nachrichten anwenden, die Benutzer über das Portal erhalten. Anders ausgedrückt: E-Mails, auf die eine benutzerdefinierte Brandingvorlage angewendet wurde. Weitere Informationen und ein Beispiel finden Sie in der Anleitung unter Sicherstellen, dass alle externen Empfänger das [OME-Portal](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail)zum Lesen verschlüsselter E-Mails verwenden.