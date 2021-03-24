---
title: Widerrufen von E-Mails, die durch erweiterte Nachrichtenverschlüsselung verschlüsselt wurden
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Als Administrator und Nachrichtensender können Sie bestimmte E-Mails widerrufen, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051717"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a>Widerrufen von E-Mails, die durch erweiterte Nachrichtenverschlüsselung verschlüsselt wurden

Die E-Mail-Sperrung wird im Rahmen der erweiterten Office 365-Nachrichtenverschlüsselung angeboten. Office 365 Advanced Message Encryption ist in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Preis für gemeinnützige Mitarbeiter), Office 365 Enterprise E5 (Gemeinnützige Mitarbeiterpreise) und Office 365 Education A5 enthalten. Wenn Ihre Organisation über ein Abonnement verfügt, das keine erweiterte Office 365-Nachrichtenverschlüsselung umfasst, können Sie es mit dem Microsoft 365 E5 Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder dem Office 365 Advanced Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preise für gemeinnützige Mitarbeiter) oder Office 365 SKUs erwerben.

Dieser Artikel ist Teil einer größeren Reihe von Artikeln zur [Office 365-Nachrichtenverschlüsselung.](ome.md)

Wenn eine Nachricht mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurde und Sie ein Microsoft 365-Administrator sind oder der Absender der Nachricht sind, können Sie die Nachricht unter bestimmten Bedingungen widerrufen. Administratoren widerrufen Nachrichten mithilfe von PowerShell. Als Absender widerrufen Sie eine Nachricht, die Sie direkt aus Outlook im Web gesendet haben. In diesem Artikel werden die Umstände beschrieben, unter denen ein Widerruf möglich ist und wie dies möglich ist.
  
## <a name="encrypted-emails-that-you-can-revoke"></a>Verschlüsselte E-Mails, die Sie widerrufen können

Administratoren und Nachrichtensender können verschlüsselte E-Mails widerrufen, wenn der Empfänger eine linkbasierte verschlüsselte E-Mail mit Markennamen empfangen hat. Wenn der Empfänger eine systemeigene Inlineerfahrung in einem unterstützten Outlook-Client erhalten hat, können Sie die Nachricht nicht widerrufen.

Ob ein Empfänger eine linkbasierte oder eine Inlineerfahrung erhält, hängt vom Identitätstyp des Empfängers ab: Office 365- und Microsoft-Kontoempfänger (z. B. outlook.com-Benutzer) erhalten eine Inlineerfahrung in unterstützten Outlook-Clients. Alle anderen Empfängertypen, z. B. Gmail- und Yahoo-Empfänger, erhalten eine linkbasierte Erfahrung.

Administratoren und Nachrichtensender können Nachrichten, die verschlüsselt sind, mithilfe der Verschlüsselung widerrufen, die direkt aus Outlook im Web angewendet wird. Beispielsweise Nachrichten, die mit der Option Nur verschlüsseln verschlüsselt werden.

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot der Option Nur verschlüsseln in Outlook im Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a>Empfängererfahrung für widerrufene verschlüsselte E-Mails

Nachdem eine E-Mail widerrufen wurde, erhält der Empfänger einen Fehler, wenn er über das Office 365-Nachrichtenverschlüsselungsportal auf die verschlüsselte E-Mail zukommt: "Die Nachricht wurde vom Absender widerrufen".

![Screenshot, der eine gesperrte verschlüsselte E-Mail zeigt.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a>Widerrufen einer von Ihnen gesendeten verschlüsselten Nachricht

Sie können eine E-Mail widerrufen, die Sie an einen einzelnen Empfänger gesendet haben, der ein Konto für soziale Netzwerke verwendet, z. B. gmail.com oder yahoo.com. Mit anderen Worten, Sie können eine E-Mail widerrufen, die an einen einzelnen Empfänger gesendet wurde, der die linkbasierte Erfahrung erhalten hat.

Sie können keine E-Mails widerrufen, die Sie an einen Empfänger gesendet haben, der ein Geschäfts- oder Schulkonto von Office 365 oder Microsoft 365 oder einem Benutzer verwendet, der ein Microsoft-Konto verwendet, z. B. ein outlook.com Konto. 

Führen Sie die folgenden Schritte aus, um eine von Ihnen gesendete verschlüsselte Nachricht zu widerrufen

1. Navigieren Sie in Outlook  im Web im Ordner Gesendet zu der Nachricht, die Sie widerrufen möchten.

   Wenn die E-Mail wieder aufrufbar ist, wird der Link "Externer Zugriff entfernen" oben in der Nachricht angezeigt.

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot mit verschlüsselten E-Mails, die Sie in Outlook im Web widerrufen möchten.":::

2. Klicken **Sie auf Externer Zugriff entfernen,** um die Nachricht zu widerrufen.

   Die Meldung zeigt, dass ihr Status widerrufen wurde.

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot mit widerrufener verschlüsselter Nachricht in Outlook im Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a>So widerrufen Sie eine verschlüsselte Nachricht als Administrator

Microsoft 365-Administratoren führen die folgenden allgemeinen Schritte aus, um eine berechtigte verschlüsselte E-Mail zu widerrufen:

- Hier erhalten Sie die Nachrichten-ID der E-Mail.
- Stellen Sie sicher, dass Sie die Nachricht widerrufen können.
- Widerrufen Sie die E-Mail.

### <a name="step-1-obtain-the-message-id-of-the-email"></a>Schritt 1. Abrufen der Nachrichten-ID der E-Mail

Bevor Sie eine verschlüsselte E-Mail widerrufen können, erfassen Sie die Nachrichten-ID der E-Mail. Die MessageId hat in der Regel das Format:

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

Es gibt mehrere Möglichkeiten, die Nachrichten-ID der E-Mail zu finden, die Sie widerrufen möchten. In diesem Abschnitt werden einige Optionen beschrieben, Sie können jedoch eine beliebige Methode verwenden, die die ID enthält.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a>So identifizieren Sie die Nachrichten-ID der E-Mail, die Sie widerrufen möchten, mithilfe der Nachrichtenverfolgung im Security &amp; Compliance Center

1. Suchen Sie mithilfe von New Message Trace im Security & Compliance Center nach der E-Mail [nach Absender oder Empfänger.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)

2. Nachdem Sie die E-Mail-Nachricht befindet, wählen Sie sie aus, um den Detailbereich **Nachrichtenverfolgung anzuzeigen.** Erweitern **Sie weitere Informationen,** um die Nachrichten-ID zu finden.

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a>So identifizieren Sie die Nachrichten-ID der E-Mail, die Sie widerrufen möchten, mithilfe von Berichten zur Office-Nachrichtenverschlüsselung im Security &amp; Compliance Center

1. Navigieren Sie im Security &amp; Compliance Center zum **Nachrichtenverschlüsselungsbericht**. Informationen zu diesem Bericht finden Sie unter [Anzeigen von E-Mail-Sicherheitsberichten im Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).

2. Wählen Sie die **Tabelle Details anzeigen** aus, und identifizieren Sie die Nachricht, die Sie widerrufen möchten.

3. Doppelklicken Sie auf die Nachricht, um Details anzuzeigen, die die Nachrichten-ID enthalten.

### <a name="step-2-verify-that-the-mail-is-revocable"></a>Schritt 2. Überprüfen, ob die E-Mail wieder aufrufbar ist

Um zu überprüfen, ob Sie eine Nachricht widerrufen können, überprüfen Sie in der Tabelle **Details** im Security Compliance Center, ob das Feld Sperrstatus im Verschlüsselungsbericht &amp; angezeigt wird.

Führen Sie die folgenden Schritte aus, um zu überprüfen, ob Sie eine bestimmte E-Mail-Nachricht mithilfe von Windows PowerShell widerrufen können.

1. Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online ein. Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie Get-OMEMessageStatus cmdlet wie folgt aus:

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   Dieser Befehl gibt den Betreff der Nachricht zurück und gibt an, ob die Nachricht wieder aufrufbar ist. Beispiel:

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a>Schritt 3. Widerrufen der E-Mail

Sobald Sie die Nachrichten-ID der E-Mail kennen, die Sie widerrufen möchten, und sie überprüft haben, ob die Nachricht wieder aufrufbar ist, können Sie die E-Mail über das Security Compliance Center oder über &amp; Windows PowerShell.

So widerrufen Sie die Nachricht mithilfe des Security &amp; Compliance Centers

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos mit globalen Administratorberechtigungen in Ihrer Organisation eine Verbindung mit dem Security & Compliance Center sicher.

2. Wählen Sie **im Verschlüsselungsbericht** in der **Tabelle Details** für die Nachricht die Option Nachricht **widerrufen aus.**

Verwenden Sie das Cmdlet Set-OMEMessageRevocation, um eine E-Mail Windows PowerShell widerrufen.

1. Mit einem Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [verbinden Sie sich mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

2. Führen Sie Set-OMEMessageRevocation cmdlet wie folgt aus:

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. Führen Sie das cmdlet Get-OMEMessageStatus wie folgt aus, um zu überprüfen, ob die E-Mail widerrufen wurde:

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    Wenn der Widerruf erfolgreich war, gibt das Cmdlet das folgende Ergebnis zurück:  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a>Weitere Informationen zur erweiterten Office 365-Nachrichtenverschlüsselung

- [Erweiterte Office 365-Nachrichtenverschlüsselung](ome-advanced-message-encryption.md)

- [Office 365 Advanced Message Encryption – E-Mail-Ablauf](ome-advanced-expiration.md)

- [Beschreibung des Nachrichtenrichtlinien- und Compliancediensts](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)