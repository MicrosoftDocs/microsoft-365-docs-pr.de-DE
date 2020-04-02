---
title: Erweiterte Office 365-Nachrichtenverschlüsselung
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
description: Die erweiterte Nachrichtenverschlüsselung in Office 365 unterstützt Organisationen bei der Erfüllung Ihrer Compliance-Verpflichtungen, indem Administratoren die Möglichkeit erhalten, noch mehr mit geschützten Nachrichten zu tun.
ms.openlocfilehash: 3b7f4d595b8c3592530b107dd7f71aeb8d0dc57e
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106173"
---
# <a name="office-365-advanced-message-encryption"></a>Erweiterte Office 365-Nachrichtenverschlüsselung

Office 365 erweiterte Nachrichtenverschlüsselung ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Non-Profit-Mitarbeiter Preise), Office 365 Enterprise E5 (Nonprofit-Mitarbeiter Preise) und Office 365 Education A5 enthalten. Wenn Ihre Organisation über ein Abonnement verfügt, das Office 365 erweiterte Nachrichtenverschlüsselung nicht enthält, Sie können es mit dem Microsoft 365 E5 Compliance SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Non-Profit-Mitarbeiter) oder mit dem Office 365 Advanced Compliance SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Non-Profit-Mitarbeiter Preise), Office 365 SKUs oder dem Microsoft 365 E5/A5 Information Protection and Governance-SKU-Add-on für Microsoft 365 a3

Die erweiterte Nachrichtenverschlüsselung in Office 365 unterstützt Kunden bei der Erfüllung von Compliance-Verpflichtungen, die flexiblere Kontrollen externer Empfänger und deren Zugriff auf verschlüsselte e-Mails erfordern. Mit erweiterter Nachrichtenverschlüsselung in Office 365 können Sie vertrauliche e-Mails, die außerhalb der Organisation freigegeben werden, mit automatischen Richtlinien steuern. Sie konfigurieren diese Richtlinien, um vertrauliche Informationstypen wie PII, Finanz-oder Integritäts-IDs zu identifizieren, oder Sie können Schlüsselwörter verwenden, um den Schutz zu verbessern. Nachdem Sie die Richtlinien konfiguriert haben, koppeln Sie Richtlinien mit benutzerdefinierten e-Mail-Vorlagen und fügen dann ein Ablaufdatum für die zusätzliche Kontrolle von e-Mails hinzu, die der Richtlinie entsprechen. Darüber hinaus können Administratoren verschlüsselte e-Mails, auf die extern über ein sicheres Webportal zugegriffen wird, weiter steuern, indem Sie den Zugriff auf die e-Mail jederzeit widerrufen.

Sie können ein Ablaufdatum für e-Mails, die an externe Empfänger gesendet werden, nur widerrufen und festlegen.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Erste Schritte mit Office 365 erweiterte Nachrichtenverschlüsselung

In den folgenden Artikeln wird beschrieben, wie Sie die erweiterte Nachrichtenverschlüsselung einrichten und verwenden.

Ihre Organisation muss über ein Abonnement verfügen, das Office 365 erweiterte Nachrichtenverschlüsselung enthält. Ausführliche Informationen zu unterstützten Abonnements finden Sie in der [Beschreibung des Nachrichtenrichtlinien-und Kompatibilitätsdiensts](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Wenn Sie Office 365 Nachrichtenverschlüsselung nicht bereits eingerichtet haben, finden Sie weitere Informationen unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md).

Mit der erweiterten Nachrichtenverschlüsselung sind Sie nicht auf eine einzelne Branding-Vorlage limitiert. Stattdessen können Sie mehrere Branding-Vorlagen erstellen und verwenden. Weitere Informationen finden Sie unter [Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten](add-your-organization-brand-to-encrypted-messages.md).

[Legen Sie ein Ablaufdatum für e-Mails fest, die durch Office 365 erweiterte Nachrichtenverschlüsselung verschlüsselt werden](ome-advanced-expiration.md). Steuern Sie vertrauliche, außerhalb der Organisation freigegebene e-Mails mit automatischen Richtlinien, die den Schutz durch Ablauf des Zugriffs über ein sicheres Webportal auf verschlüsselte e-Mails verbessern.

[Durch Office 365 erweiterte Nachrichtenverschlüsselung verschlüsselte e-Mails widerrufen](revoke-ome-encrypted-mail.md). Steuern Sie vertrauliche e-Mails, die außerhalb der Organisation freigegeben wurden, und erhöhen Sie den Schutz, indem Sie den Zugriff über ein sicheres Webportal auf verschlüsselte e-Mails widerrufen.  

Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung verwenden, wendet Office 365 einen Wrapper immer dann auf e-Mails an, die der e-Mail-Fluss Regel entsprechen, auf die die Vorlage angewendet wird, wenn Sie eine benutzerdefinierte Branding-Vorlage anwenden. Sie können nur Nachrichten widerrufen und Ablaufdaten auf Nachrichten anwenden, die Benutzer über das Portal erhalten. Mit anderen Worten: e-Mail, auf die eine benutzerdefinierte Branding-Vorlage angewendet wurde. Weitere Informationen und ein Beispiel finden Sie im Leitfaden unter [sicherstellen, dass alle externen Empfänger das OM-Portal zum Lesen verschlüsselter e-Mails verwenden](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).
