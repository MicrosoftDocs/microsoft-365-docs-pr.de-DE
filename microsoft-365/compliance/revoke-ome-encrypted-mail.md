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
description: Als Administrator und Als Nachrichtensender können Sie bestimmte E-Mails widerrufen, die mit Office 365 Advanced Message Encryption.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051717"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="7d46d-103">Widerrufen von E-Mails, die durch erweiterte Nachrichtenverschlüsselung verschlüsselt wurden</span><span class="sxs-lookup"><span data-stu-id="7d46d-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="7d46d-104">Der E-Mail-Widerruf wird im Rahmen der Office 365 Advanced Message Encryption.</span><span class="sxs-lookup"><span data-stu-id="7d46d-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="7d46d-105">Office 365 Advanced Message Encryption ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Preis für gemeinnützige Mitarbeiter), Office 365 Enterprise E5 (Preis für gemeinnützige Mitarbeiter) und Office 365 Education A5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d46d-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="7d46d-106">Wenn Ihre Organisation über ein Abonnement verfügt, das Office 365 Advanced Message Encryption nicht enthält, können Sie es mit dem Microsoft 365 E5 Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder das Office 365 Advanced Compliance SKU-Add-On für Microsoft 365 E3, Microsoft 365 E3 (Preis für gemeinnützige Mitarbeiter) oder Office 365 SKUs erwerben.</span><span class="sxs-lookup"><span data-stu-id="7d46d-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="7d46d-107">Dieser Artikel ist Teil einer größeren Reihe von Artikeln über [Office 365-Nachrichtenverschlüsselung.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="7d46d-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="7d46d-108">Wenn eine Nachricht mithilfe von Office 365 Advanced Message Encryption verschlüsselt wurde und Sie ein Microsoft 365-Administrator sind oder der Absender der Nachricht sind, können Sie die Nachricht unter bestimmten Bedingungen widerrufen.</span><span class="sxs-lookup"><span data-stu-id="7d46d-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="7d46d-109">Administratoren widerrufen Nachrichten mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d46d-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="7d46d-110">Als Absender widerrufen Sie eine Nachricht, die Sie direkt aus Outlook im Web gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="7d46d-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="7d46d-111">In diesem Artikel werden die Umstände beschrieben, unter denen ein Widerruf möglich ist und wie dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="7d46d-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="7d46d-112">Verschlüsselte E-Mails, die Sie widerrufen können</span><span class="sxs-lookup"><span data-stu-id="7d46d-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="7d46d-113">Administratoren und Nachrichtensender können verschlüsselte E-Mails widerrufen, wenn der Empfänger eine linkbasierte verschlüsselte E-Mail mit Markennamen empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="7d46d-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="7d46d-114">Wenn der Empfänger in einem unterstützten Client eine systemeigene Inlineerfahrung Outlook hat, können Sie die Nachricht nicht widerrufen.</span><span class="sxs-lookup"><span data-stu-id="7d46d-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="7d46d-115">Ob ein Empfänger eine linkbasierte Oder eine Inlineerfahrung erhält, hängt vom Identitätstyp des Empfängers ab: Office 365- und Microsoft-Kontoempfänger (z. B. outlook.com Benutzer) erhalten eine Inlineerfahrung in unterstützten Outlook Clients.</span><span class="sxs-lookup"><span data-stu-id="7d46d-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="7d46d-116">Alle anderen Empfängertypen, z. B. Gmail- und Yahoo-Empfänger, erhalten eine linkbasierte Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="7d46d-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="7d46d-117">Administratoren und Nachrichtensender können Nachrichten widerrufen, die mithilfe der verschlüsselungsintegiert werden, die direkt von Outlook im Web angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7d46d-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="7d46d-118">Beispielsweise Nachrichten, die mit der Option Nur verschlüsseln verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="7d46d-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot der Option Nur verschlüsseln in Outlook im Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="7d46d-120">Empfängererfahrung für widerrufene verschlüsselte E-Mails</span><span class="sxs-lookup"><span data-stu-id="7d46d-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="7d46d-121">Nachdem eine E-Mail widerrufen wurde, erhält der Empfänger einen Fehler, wenn er über das Office 365-Nachrichtenverschlüsselung-Portal auf die verschlüsselte E-Mail zukommt: "Die Nachricht wurde vom Absender widerrufen".</span><span class="sxs-lookup"><span data-stu-id="7d46d-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Screenshot, der eine gesperrte verschlüsselte E-Mail zeigt.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="7d46d-123">Widerrufen einer von Ihnen gesendeten verschlüsselten Nachricht</span><span class="sxs-lookup"><span data-stu-id="7d46d-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="7d46d-124">Sie können eine E-Mail widerrufen, die Sie an einen einzelnen Empfänger gesendet haben, der ein Konto für soziale Netzwerke verwendet, z. B. gmail.com oder yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="7d46d-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="7d46d-125">Mit anderen Worten, Sie können eine E-Mail widerrufen, die an einen einzelnen Empfänger gesendet wurde, der die linkbasierte Erfahrung erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="7d46d-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="7d46d-126">Sie können eine E-Mail, die Sie an einen Empfänger gesendet haben, der ein Arbeits- oder Schulkonto verwendet, nicht von Office 365 oder Microsoft 365 oder einem Benutzer widerrufen, der ein Microsoft-Konto verwendet, z. B. ein outlook.com Konto.</span><span class="sxs-lookup"><span data-stu-id="7d46d-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="7d46d-127">Führen Sie die folgenden Schritte aus, um eine von Ihnen gesendete verschlüsselte Nachricht zu widerrufen</span><span class="sxs-lookup"><span data-stu-id="7d46d-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="7d46d-128">Navigieren Outlook im Web im Ordner  Gesendet zu der Nachricht, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d46d-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="7d46d-129">Wenn die E-Mail wieder aufrufbar ist, wird der Link "Externer Zugriff entfernen" oben in der Nachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7d46d-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot mit verschlüsselten E-Mails, die Sie in Outlook im Web widerrufen möchten.":::

2. <span data-ttu-id="7d46d-131">Klicken **Sie auf Externer Zugriff entfernen,** um die Nachricht zu widerrufen.</span><span class="sxs-lookup"><span data-stu-id="7d46d-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="7d46d-132">Die Meldung zeigt, dass ihr Status widerrufen wurde.</span><span class="sxs-lookup"><span data-stu-id="7d46d-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot der gesperrten verschlüsselten Nachricht in Outlook im Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="7d46d-134">So widerrufen Sie eine verschlüsselte Nachricht als Administrator</span><span class="sxs-lookup"><span data-stu-id="7d46d-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="7d46d-135">Microsoft 365 Administratoren führen die folgenden allgemeinen Schritte aus, um eine berechtigte verschlüsselte E-Mail zu widerrufen:</span><span class="sxs-lookup"><span data-stu-id="7d46d-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="7d46d-136">Hier erhalten Sie die Nachrichten-ID der E-Mail.</span><span class="sxs-lookup"><span data-stu-id="7d46d-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="7d46d-137">Stellen Sie sicher, dass Sie die Nachricht widerrufen können.</span><span class="sxs-lookup"><span data-stu-id="7d46d-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="7d46d-138">Widerrufen Sie die E-Mail.</span><span class="sxs-lookup"><span data-stu-id="7d46d-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="7d46d-139">Schritt 1.</span><span class="sxs-lookup"><span data-stu-id="7d46d-139">Step 1.</span></span> <span data-ttu-id="7d46d-140">Abrufen der Nachrichten-ID der E-Mail</span><span class="sxs-lookup"><span data-stu-id="7d46d-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="7d46d-141">Bevor Sie eine verschlüsselte E-Mail widerrufen können, erfassen Sie die Nachrichten-ID der E-Mail.</span><span class="sxs-lookup"><span data-stu-id="7d46d-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="7d46d-142">Die MessageId hat in der Regel das Format:</span><span class="sxs-lookup"><span data-stu-id="7d46d-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="7d46d-143">Es gibt mehrere Möglichkeiten, die Nachrichten-ID der E-Mail zu finden, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d46d-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="7d46d-144">In diesem Abschnitt werden einige Optionen beschrieben, Sie können jedoch eine beliebige Methode verwenden, die die ID enthält.</span><span class="sxs-lookup"><span data-stu-id="7d46d-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="7d46d-145">So identifizieren Sie die Nachrichten-ID der E-Mail, die Sie widerrufen möchten, mithilfe der Nachrichtenverfolgung im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7d46d-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="7d46d-146">Suchen Sie mithilfe von New Message Trace im Security & Compliance Center nach der E-Mail [nach Absender oder Empfänger.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="7d46d-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="7d46d-147">Nachdem Sie die E-Mail-Nachricht befindet, wählen Sie sie aus, um den Detailbereich **Nachrichtenverfolgung anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="7d46d-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="7d46d-148">Erweitern **Sie weitere Informationen,** um die Nachrichten-ID zu finden.</span><span class="sxs-lookup"><span data-stu-id="7d46d-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="7d46d-149">So identifizieren Sie die Nachrichten-ID der E-Mail, die Sie widerrufen möchten, mithilfe Office Nachrichtenverschlüsselungsberichte im Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="7d46d-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="7d46d-150">Navigieren Sie im Security &amp; Compliance Center zum **Nachrichtenverschlüsselungsbericht**.</span><span class="sxs-lookup"><span data-stu-id="7d46d-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="7d46d-151">Informationen zu diesem Bericht finden Sie unter [Anzeigen von E-Mail-Sicherheitsberichten im Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7d46d-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="7d46d-152">Wählen Sie die **Tabelle Details anzeigen** aus, und identifizieren Sie die Nachricht, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="7d46d-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="7d46d-153">Doppelklicken Sie auf die Nachricht, um Details anzuzeigen, die die Nachrichten-ID enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d46d-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="7d46d-154">Schritt 2.</span><span class="sxs-lookup"><span data-stu-id="7d46d-154">Step 2.</span></span> <span data-ttu-id="7d46d-155">Überprüfen, ob die E-Mail wieder aufrufbar ist</span><span class="sxs-lookup"><span data-stu-id="7d46d-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="7d46d-156">Um zu überprüfen, ob Sie eine Nachricht widerrufen können, überprüfen Sie in der Tabelle **Details** im Security Compliance Center, ob das Feld Sperrstatus im Verschlüsselungsbericht &amp; angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7d46d-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="7d46d-157">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob Sie eine bestimmte E-Mail-Nachricht mithilfe Windows PowerShell widerrufen können.</span><span class="sxs-lookup"><span data-stu-id="7d46d-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="7d46d-158">Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7d46d-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="7d46d-159">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d46d-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7d46d-160">Führen Sie Get-OMEMessageStatus cmdlet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7d46d-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="7d46d-161">Dieser Befehl gibt den Betreff der Nachricht zurück und gibt an, ob die Nachricht wieder aufrufbar ist.</span><span class="sxs-lookup"><span data-stu-id="7d46d-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="7d46d-162">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7d46d-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="7d46d-163">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="7d46d-163">Step 3.</span></span> <span data-ttu-id="7d46d-164">Widerrufen der E-Mail</span><span class="sxs-lookup"><span data-stu-id="7d46d-164">Revoke the mail</span></span>

<span data-ttu-id="7d46d-165">Sobald Sie die Nachrichten-ID der E-Mail kennen, die Sie widerrufen möchten, und sie überprüft haben, ob die Nachricht wieder aufrufbar ist, können Sie die E-Mail über das Security Compliance Center oder &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d46d-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="7d46d-166">So widerrufen Sie die Nachricht mithilfe des Security &amp; Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="7d46d-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="7d46d-167">Stellen Sie mithilfe eines Arbeits- oder Schulkontos mit globalen Administratorberechtigungen in Ihrer Organisation eine Verbindung mit dem Security & Compliance Center sicher.</span><span class="sxs-lookup"><span data-stu-id="7d46d-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="7d46d-168">Wählen Sie **im Verschlüsselungsbericht** in der **Tabelle Details** für die Nachricht die Option Nachricht **widerrufen aus.**</span><span class="sxs-lookup"><span data-stu-id="7d46d-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="7d46d-169">Verwenden Sie das cmdlet Set-OMEMessageRevocation, um eine E-Mail Windows PowerShell zu widerrufen.</span><span class="sxs-lookup"><span data-stu-id="7d46d-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="7d46d-170">Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [Verbinden, Exchange Online PowerShell zu verwenden.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="7d46d-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="7d46d-171">Führen Sie Set-OMEMessageRevocation cmdlet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="7d46d-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="7d46d-172">Führen Sie das cmdlet Get-OMEMessageStatus wie folgt aus, um zu überprüfen, ob die E-Mail widerrufen wurde:</span><span class="sxs-lookup"><span data-stu-id="7d46d-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="7d46d-173">Wenn der Widerruf erfolgreich war, gibt das Cmdlet das folgende Ergebnis zurück:</span><span class="sxs-lookup"><span data-stu-id="7d46d-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="7d46d-174">Weitere Informationen zu Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="7d46d-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="7d46d-175">Erweiterte Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="7d46d-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="7d46d-176">Office 365 Advanced Message Encryption – E-Mail-Ablauf</span><span class="sxs-lookup"><span data-stu-id="7d46d-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="7d46d-177">Beschreibung des Nachrichtenrichtlinien- und Compliancediensts</span><span class="sxs-lookup"><span data-stu-id="7d46d-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)