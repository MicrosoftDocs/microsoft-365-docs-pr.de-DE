---
title: Widerrufen von E-Mails, die mit der erweiterten Nachrichtenverschlüsselung verschlüsselt wurden
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
description: Als Administrator und als Absender von Nachrichten können Sie bestimmte E-Mails widerrufen, die mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden.
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105140"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="d2ea3-103">Widerrufen von E-Mails, die mit der erweiterten Nachrichtenverschlüsselung verschlüsselt wurden</span><span class="sxs-lookup"><span data-stu-id="d2ea3-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="d2ea3-104">Die E-Mail-Sperrung wird als Teil der erweiterten Office 365-Nachrichtenverschlüsselung angeboten.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="d2ea3-105">Die erweiterte Nachrichtenverschlüsselung für Office [365 ist in Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Preise für gemeinnützige Mitarbeiter), Office 365 Enterprise E5 (Preise für gemeinnützige Mitarbeiter) und Office 365 Education A5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="d2ea3-106">Wenn Ihre Organisation über ein Abonnement verfügt, das nicht die erweiterte Nachrichtenverschlüsselung von Office 365 umfasst, können Sie es mit dem Microsoft 365 E5 Compliance-SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preise für gemeinnützige Mitarbeiter) oder dem Office 365 Advanced Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preise für gemeinnützige Mitarbeiter) oder Office 365 SKUs erwerben.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="d2ea3-107">Dieser Artikel ist Teil einer größeren Reihe von Artikeln zur [Office 365-Nachrichtenverschlüsselung.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="d2ea3-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="d2ea3-108">Wenn eine Nachricht mit der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurde und Sie ein Microsoft 365-Administrator sind oder der Absender der Nachricht sind, können Sie die Nachricht unter bestimmten Bedingungen widerrufen.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="d2ea3-109">Administratoren widerrufen Nachrichten mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="d2ea3-110">Als Absender widerrufen Sie eine Nachricht, die Sie direkt aus Outlook im Web gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="d2ea3-111">In diesem Artikel werden die Umstände beschrieben, unter denen eine Sperrung möglich ist und wie Sie dies tun.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="d2ea3-112">Verschlüsselte E-Mails, die Sie widerrufen können</span><span class="sxs-lookup"><span data-stu-id="d2ea3-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="d2ea3-113">Administratoren und Nachrichtensender können verschlüsselte E-Mails widerrufen, wenn der Empfänger eine linkbasierte, mit einem Markennamen verschlüsselte E-Mail erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="d2ea3-114">Wenn der Empfänger eine systemeigene Inlineerfahrung in einem unterstützten Outlook-Client erhalten hat, können Sie die Nachricht nicht widerrufen.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="d2ea3-115">Ob ein Empfänger eine linkbasierte Oder eine Inlineerfahrung erhält, hängt vom Identitätstyp des Empfängers ab: Office 365- und Microsoft-Kontoempfänger (z. B. outlook.com-Benutzer) erhalten eine Inlineerfahrung in unterstützten Outlook-Clients.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="d2ea3-116">Alle anderen Empfängertypen, z. B. Gmail- und Yahoo-Empfänger, erhalten eine linkbasierte Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="d2ea3-117">Administratoren und Nachrichtensender können verschlüsselte Nachrichten mithilfe einer Verschlüsselung widerrufen, die direkt aus Outlook im Web angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="d2ea3-118">Beispielsweise Nachrichten, die mit der Option "Nur verschlüsseln" verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot showing Encrypt Only option in Outlook on the web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="d2ea3-120">Empfängererfahrung für gesperrte verschlüsselte E-Mails</span><span class="sxs-lookup"><span data-stu-id="d2ea3-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="d2ea3-121">Nachdem eine E-Mail widerrufen wurde, erhält der Empfänger beim Zugriff auf die verschlüsselte E-Mail über das Office 365-Nachrichtenverschlüsselungsportal eine Fehlermeldung: "Die Nachricht wurde vom Absender widerrufen".</span><span class="sxs-lookup"><span data-stu-id="d2ea3-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Screenshot, der eine gesperrte verschlüsselte E-Mail zeigt.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="d2ea3-123">So widerrufen Sie eine von Ihnen gesendete verschlüsselte Nachricht</span><span class="sxs-lookup"><span data-stu-id="d2ea3-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="d2ea3-124">Sie können eine E-Mail widerrufen, die Sie an einen einzelnen Empfänger gesendet haben, der ein soziales Konto verwendet, z. B. gmail.com oder yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="d2ea3-125">Mit anderen Worten, Sie können eine E-Mail widerrufen, die an einen einzelnen Empfänger gesendet wurde, der die linkbasierte Erfahrung erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="d2ea3-126">Sie können keine E-Mails widerrufen, die Sie an einen Empfänger gesendet haben, der ein Geschäfts-, Schul- oder Geschäftskonto von Office 365 oder Microsoft 365 oder einen Benutzer verwendet, der ein Microsoft-Konto verwendet, z. B. ein outlook.com Konto.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="d2ea3-127">Führen Sie die folgenden Schritte aus, um eine von Ihnen gesendete verschlüsselte Nachricht zu widerrufen</span><span class="sxs-lookup"><span data-stu-id="d2ea3-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="d2ea3-128">Navigieren Sie in Outlook im Web im Ordner **"Gesendet"** zu der Nachricht, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="d2ea3-129">Wenn die E-Mail wiederaufrufbar ist, wird oben in der Nachricht der Link "Externer Zugriff entfernen" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot mit verschlüsselten E-Mails, die Sie in Outlook im Web widerrufen möchten.":::

2. <span data-ttu-id="d2ea3-131">Klicken **Sie auf "Externer Zugriff entfernen",** um die Nachricht zu widerrufen.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="d2ea3-132">Die Meldung zeigt an, dass der Status widerrufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot der gesperrten verschlüsselten Nachricht in Outlook im Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="d2ea3-134">So widerrufen Sie eine verschlüsselte Nachricht als Administrator</span><span class="sxs-lookup"><span data-stu-id="d2ea3-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="d2ea3-135">Microsoft 365-Administratoren führen diese allgemeinen Schritte aus, um eine berechtigte verschlüsselte E-Mail zu widerrufen:</span><span class="sxs-lookup"><span data-stu-id="d2ea3-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="d2ea3-136">Erhalten Sie die Nachrichten-ID der E-Mail.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="d2ea3-137">Stellen Sie sicher, dass Sie die Nachricht widerrufen können.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="d2ea3-138">Widerrufen sie die E-Mail.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="d2ea3-139">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-139">Step 1.</span></span> <span data-ttu-id="d2ea3-140">Abrufen der Nachrichten-ID der E-Mail</span><span class="sxs-lookup"><span data-stu-id="d2ea3-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="d2ea3-141">Bevor Sie eine verschlüsselte E-Mail widerrufen können, sammeln Sie die Nachrichten-ID der E-Mail.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="d2ea3-142">Die MessageId hat in der Regel das format:</span><span class="sxs-lookup"><span data-stu-id="d2ea3-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="d2ea3-143">Es gibt mehrere Möglichkeiten, die Nachrichten-ID der E-Mail zu finden, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="d2ea3-144">In diesem Abschnitt werden einige Optionen beschrieben, Sie können jedoch eine beliebige Methode verwenden, die die ID enthält.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="d2ea3-145">So identifizieren Sie die Nachrichten-ID der E-Mail, die Sie widerrufen möchten, mithilfe der Nachrichtenverfolgung im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d2ea3-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d2ea3-146">Suchen Sie im Security & Compliance Center nach der E-Mail [nach Absender oder Empfänger.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="d2ea3-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="d2ea3-147">Sobald Sie die E-Mail-Nachricht finden, wählen Sie sie aus, um den Detailbereich für die **Nachrichtenverfolgung anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="d2ea3-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="d2ea3-148">Erweitern **Sie weitere Informationen,** um die Nachrichten-ID zu finden.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="d2ea3-149">So identifizieren Sie die Nachrichten-ID der E-Mail, die Sie widerrufen möchten, mithilfe von Berichten zur Office-Nachrichtenverschlüsselung im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d2ea3-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d2ea3-150">Navigieren Sie im Security &amp; Compliance Center zum **Nachrichtenverschlüsselungsbericht.**</span><span class="sxs-lookup"><span data-stu-id="d2ea3-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="d2ea3-151">Informationen zu diesem Bericht finden Sie unter [Anzeigen von E-Mail-Sicherheitsberichten im Security &amp; Compliance Center.](../security/office-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="d2ea3-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="d2ea3-152">Wählen Sie die **Tabelle "Details anzeigen"** aus, und identifizieren Sie die Nachricht, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="d2ea3-153">Doppelklicken Sie auf die Nachricht, um Details anzuzeigen, die die Nachrichten-ID enthalten.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="d2ea3-154">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-154">Step 2.</span></span> <span data-ttu-id="d2ea3-155">Überprüfen, ob die E-Mail wiederaufrufbar ist</span><span class="sxs-lookup"><span data-stu-id="d2ea3-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="d2ea3-156">Um zu überprüfen, ob Sie eine Nachricht widerrufen können, überprüfen Sie in der Tabelle **"Details"** im Security Compliance Center, ob das Feld "Sperrstatus" im Verschlüsselungsbericht &amp; angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="d2ea3-157">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob Sie eine bestimmte E-Mail-Nachricht mithilfe Windows PowerShell können.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="d2ea3-158">Starten Sie unter Verwendung eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="d2ea3-159">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="d2ea3-159">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d2ea3-160">Führen Sie Get-OMEMessageStatus cmdlet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d2ea3-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="d2ea3-161">Dieser Befehl gibt den Betreff der Nachricht zurück und gibt an, ob die Nachricht aufrufbar ist.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="d2ea3-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d2ea3-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="d2ea3-163">Schritt 3.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-163">Step 3.</span></span> <span data-ttu-id="d2ea3-164">Widerrufen der E-Mail</span><span class="sxs-lookup"><span data-stu-id="d2ea3-164">Revoke the mail</span></span>

<span data-ttu-id="d2ea3-165">Sobald Sie die Nachrichten-ID der E-Mail kennen, die Sie widerrufen möchten, und sie überprüft haben, ob die Nachricht wiederaufrufbar ist, können Sie die E-Mail über das Security Compliance Center oder die &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="d2ea3-166">So widerrufen Sie die Nachricht mithilfe des Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d2ea3-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="d2ea3-167">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit dem Security & Compliance Center herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="d2ea3-168">Wählen Sie **im Verschlüsselungsbericht** in der **Tabelle "Details"** für die Nachricht die Option **"Nachricht widerrufen" aus.**</span><span class="sxs-lookup"><span data-stu-id="d2ea3-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="d2ea3-169">Verwenden Sie das cmdlet Windows PowerShell, um eine E-Mail Set-OMEMessageRevocation widerrufen.</span><span class="sxs-lookup"><span data-stu-id="d2ea3-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="d2ea3-170">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](https://aka.ms/exopowershell)</span><span class="sxs-lookup"><span data-stu-id="d2ea3-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="d2ea3-171">Führen Sie Set-OMEMessageRevocation cmdlet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d2ea3-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="d2ea3-172">Führen Sie zum Überprüfen, ob die E-Mail widerrufen wurde, das cmdlet Get-OMEMessageStatus wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d2ea3-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="d2ea3-173">Wenn die Sperrung erfolgreich war, gibt das Cmdlet das folgende Ergebnis zurück:</span><span class="sxs-lookup"><span data-stu-id="d2ea3-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="d2ea3-174">Weitere Informationen zur erweiterten Nachrichtenverschlüsselung in Office 365</span><span class="sxs-lookup"><span data-stu-id="d2ea3-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="d2ea3-175">Erweiterte Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="d2ea3-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="d2ea3-176">Office 365 Advanced Message Encryption – E-Mail-Ablauf</span><span class="sxs-lookup"><span data-stu-id="d2ea3-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="d2ea3-177">Beschreibung des Nachrichtenrichtlinien- und Kompatibilitätsdiensts</span><span class="sxs-lookup"><span data-stu-id="d2ea3-177">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
