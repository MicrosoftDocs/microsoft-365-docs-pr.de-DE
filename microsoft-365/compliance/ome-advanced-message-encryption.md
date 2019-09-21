---
title: Erweiterte Office 365-Nachrichtenverschlüsselung
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Erweiterte Nachrichtenverschlüsselung in Office 365 unterstützt Organisationen bei der Erfüllung Ihrer Compliance-Verpflichtungen, indem Administratoren das ablaufen und widerrufen des Zugriffs über ein Office 365-Webportal auf verschlüsselte e-Mails ermöglichen.
ms.openlocfilehash: dcef5f861711acffb8359063373cd90d4b122d88
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082247"
---
# <a name="office-365-advanced-message-encryption"></a>Erweiterte Office 365-Nachrichtenverschlüsselung

Office 365 erweiterte Nachrichtenverschlüsselung steht über Office 365 Nachrichtenverschlüsselung in bestimmten Abonnements zur Verfügung. Die erweiterte Nachrichtenverschlüsselung ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 und Office 365 Education A5 enthalten. Wenn Ihre Organisation über ein Office 365es Abonnement verfügt, das nicht Office 365 erweiterte Nachrichtenverschlüsselung enthält, können Sie erweiterte Nachrichtenverschlüsselung als Add-on mit E5-Kompatibilität der Advanced Compliance-SKU erwerben.

Die erweiterte Nachrichtenverschlüsselung in Office 365 unterstützt Kunden bei der Erfüllung von Compliance-Verpflichtungen, die flexiblere Kontrollen externer Empfänger und deren Zugriff auf verschlüsselte e-Mails erfordern. Mit erweiterter Nachrichtenverschlüsselung in Office 365 können Sie vertrauliche e-Mails, die außerhalb der Organisation freigegeben werden, mit automatischen Richtlinien steuern. Sie konfigurieren diese Richtlinien, um vertrauliche Informationstypen wie PII, Finanz-oder Integritäts-IDs zu identifizieren, oder Sie können Schlüsselwörter verwenden, um den Schutz zu verbessern. Nachdem Sie die Richtlinien konfiguriert haben, koppeln Sie Richtlinien mit benutzerdefinierten e-Mail-Vorlagen und fügen dann ein Ablaufdatum für die zusätzliche Kontrolle von e-Mails hinzu, die der Richtlinie entsprechen. Darüber hinaus können Administratoren verschlüsselte e-Mails, auf die extern über ein sicheres Webportal zugegriffen wird, weiter steuern, indem Sie den Zugriff auf die e-Mail jederzeit widerrufen.

Sie können ein Ablaufdatum für e-Mails, die an externe Empfänger gesendet werden, nur widerrufen und festlegen.

Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung verwenden, wendet Office 365 einen Wrapper immer dann auf e-Mails an, die der e-Mail-Fluss Regel entsprechen, auf die die Vorlage angewendet wird, wenn Sie eine benutzerdefinierte Branding-Vorlage anwenden. Sie können nur Nachrichten widerrufen und Ablaufdaten auf Nachrichten anwenden, die Benutzer über das Portal erhalten. Mit anderen Worten: e-Mail, auf die eine benutzerdefinierte Branding-Vorlage angewendet wurde.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Erste Schritte mit Office 365 erweiterte Nachrichtenverschlüsselung

In den folgenden Themen wird beschrieben, wie Sie die erweiterte Nachrichtenverschlüsselung einrichten und verwenden.

Ihre Organisation muss über ein Abonnement verfügen, das Office 365 erweiterte Nachrichtenverschlüsselung enthält. Ausführliche Informationen zu unterstützten Abonnements finden Sie in der [Beschreibung des Nachrichtenrichtlinien-und Kompatibilitätsdiensts](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Wenn Sie Office 365 Nachrichtenverschlüsselung nicht bereits eingerichtet haben, finden Sie weitere Informationen unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md).

[Legen Sie ein Ablaufdatum für e-Mails fest, die durch Office 365 erweiterte Nachrichtenverschlüsselung verschlüsselt werden](ome-advanced-expiration.md). Steuern Sie vertrauliche, außerhalb der Organisation freigegebene e-Mails mit automatischen Richtlinien, die den Schutz durch Ablauf des Zugriffs über ein sicheres Webportal auf verschlüsselte e-Mails verbessern.

[Durch Office 365 erweiterte Nachrichtenverschlüsselung verschlüsselte e-Mails widerrufen](revoke-ome-encrypted-mail.md). Steuern Sie vertrauliche e-Mails, die außerhalb der Organisation freigegeben wurden, und erhöhen Sie den Schutz, indem Sie den Zugriff über ein sicheres Webportal auf verschlüsselte e-Mails widerrufen.  