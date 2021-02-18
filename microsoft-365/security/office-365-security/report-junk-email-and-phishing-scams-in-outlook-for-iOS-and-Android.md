---
title: Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die integrierten Junk-E-Mail-, nicht Junk- und Phishing-E-Mail-Berichtsoptionen in Outlook für iOS und Android informieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e3a2d77c978649e7496d09f78301add397fb9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289173"
---
# <a name="report-junk-and-phishing-email-in-outlook-for-ios-and-android-in-exchange-online"></a>Melden von Junk- und Phishing-E-Mails in Outlook für iOS und Android in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern, die moderne Hybridauthentifizierung [verwenden,](../../enterprise/hybrid-modern-auth-overview.md)können Sie die integrierten Berichtsoptionen in Outlook für iOS und Android verwenden, um falsch positive Ergebnisse (gute E-Mails, die als Spam gekennzeichnet sind), falsch negative Ergebnisse (ungültige E-Mails sind zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) zu übermitteln.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was müssen Sie wissen, bevor Sie beginnen

- Für eine optimale Benutzerübermittlung empfehlen wir die Verwendung der Add-Ins "Nachricht melden" und "Phishing melden". Weitere Informationen finden Sie unter "Aktivieren [des Berichtsnachrichten-Add-Ins"](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) und ["Aktivieren des Phishing-Add-Ins".](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-phish-add-in)

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center. Weitere Informationen finden Sie unter ["Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft ".](admin-submission.md)

- Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter ["Melden von Nachrichten und Dateien an Microsoft".](report-junk-email-messages-to-microsoft.md)

  > [!NOTE]
  > Wenn die Junk-E-Mail-Berichterstellung für Outlook in der Benutzerübermittlungsrichtlinie deaktiviert ist, werden Junk- oder Phishingnachrichten in den Junk-E-Mail-Ordner verschoben und nicht an Ihren Administrator oder Microsoft gemeldet.