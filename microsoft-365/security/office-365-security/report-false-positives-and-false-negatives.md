---
title: Melden falsch positiver und falsch negativer Ergebnisse in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie falsch positive und falsch negative Ergebnisse in Outlook mithilfe der Funktion "Meldung melden" melden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 458e7d16e2614e7bac3a0aac5a4310e6353ab569
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082924"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Melden falsch positiver und falsch negativer Ergebnisse in Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Wenn Sie ein Administrator in einer Microsoft 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, die Seite **"Übermittlungen"** im Microsoft 365 Defender-Portal zu verwenden. Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie falsch positive Ergebnisse (gute E-Mails, die blockiert oder an Junk-Ordner gesendet wurden) und falsch negative Nachrichten (unerwünschte E-Mails oder Phishing-Nachrichten, die an den Posteingang übermittelt wurden) an Exchange Online Protection (EOP) senden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Verwenden Sie für eine optimale Benutzerübermittlung das Add-In "Nachricht melden" oder das Add-In "Phishing melden".

  > [!IMPORTANT]
  > Die integrierte Oberfläche zum Melden von Junk- oder Phishing in Outlook kann nicht die [Benutzerübermittlungsrichtlinie](./user-submission.md)verwenden. Es wird empfohlen, stattdessen das Add-In "Nachricht melden" oder das Add-In "Phishing melden" zu verwenden.

- Das Add-In "Nachricht melden" und das Add-In "Phishing melden" funktionieren für Outlook auf allen Plattformen (Outlook im Web, iOS, Android und Desktop).

- Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, verwenden Sie das Übermittlungsportal im Microsoft 365 Defender Portal. Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)

- Sie können das Senden von Nachrichten direkt an Microsoft, ein von Ihnen angegebenes Postfach oder beides konfigurieren. Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)

- Weitere Informationen zum Abrufen und Aktivieren der Berichtsnachricht oder der Berichtsphishing-Add-Ins finden Sie unter [Aktivieren der Berichtsnachricht oder der Berichtsphishing-Add-Ins.](enable-the-report-message-add-in.md)

- Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-report-message-feature"></a>Verwenden des Berichtsnachrichtenfeatures

### <a name="report-junk-and-phishing-messages"></a>Melden von Junk- und Phishingnachrichten

Verwenden Sie für Nachrichten im Posteingang oder einem anderen E-Mail-Ordner mit Ausnahme von Junk-E-Mails die folgende Methode, um Spam- und Phishingnachrichten zu melden:

1. Wählen Sie die Auslassungspunkte **"Weitere Aktionen"** in der oberen rechten Ecke der ausgewählten Nachricht aus, wählen Sie im Dropdownmenü die Option **"Nachricht** melden" aus, und wählen Sie dann **"Junk"** oder **"Phishing"** aus.

   ![Meldung melden – Weitere Aktionen](../../media/report-message-more-actions.png)

   ![Nachricht melden – Junk und Phishing](../../media/report-message-junk-phishing.png)

2. Die ausgewählten Nachrichten werden zur Analyse an Microsoft gesendet und:
   - In den Junk-E-Mail-Ordner verschoben, wenn sie als Spam gemeldet wurden.
   - Gelöscht, wenn sie als Phishing gemeldet wurden.

### <a name="report-messages-that-are-not-junk"></a>Melden von Nachrichten, die keine Junk-Nachrichten sind

1. Wählen Sie die Auslassungspunkte **"Weitere Aktionen"** in der oberen rechten Ecke der ausgewählten Nachricht aus, wählen Sie **"Nachricht** melden" aus dem Dropdownmenü aus, und wählen Sie dann **"Nicht Junk"** aus.

   ![Meldung melden – Weitere Aktionen](../../media/report-message-more-actions.png)

   ![Meldung melden – keine Junk-Nachricht](../../media/report-message-not-junk.png)

2. Die ausgewählte Nachricht wird zur Analyse an Microsoft gesendet und in den Posteingang oder einen anderen angegebenen Ordner verschoben.

## <a name="view-and-review-reported-messages"></a>Anzeigen und Überprüfen gemeldeter Nachrichten

Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:

- Verwenden Sie die Seite **"Übermittlungen"** im Microsoft 365 Defender Portal. Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)
- Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden. Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer An Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)
