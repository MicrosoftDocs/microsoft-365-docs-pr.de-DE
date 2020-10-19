---
title: Durch erweiterte Nachrichtenverschlüsselung verschlüsselte e-Mails widerrufen
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
description: Als Administrator und als Absender der Nachricht können Sie bestimmte e-Mails widerrufen, die mit Office 365 erweiterten Nachrichtenverschlüsselung verschlüsselt wurden.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868944"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="5f396-103">Durch erweiterte Nachrichtenverschlüsselung verschlüsselte e-Mails widerrufen</span><span class="sxs-lookup"><span data-stu-id="5f396-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="5f396-104">Die e-Mail-Sperrung wird im Rahmen Office 365 erweiterten Nachrichtenverschlüsselung angeboten.</span><span class="sxs-lookup"><span data-stu-id="5f396-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="5f396-105">Office 365 erweiterte Nachrichtenverschlüsselung ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Non-Profit-Mitarbeiter Preise), Office 365 Enterprise E5 (Nonprofit-Mitarbeiter Preise) und Office 365 Education A5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="5f396-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="5f396-106">Wenn Ihre Organisation über ein Abonnement verfügt, das Office 365 erweiterte Nachrichtenverschlüsselung nicht enthält, können Sie Sie mit dem Microsoft 365 E5 Compliance-SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Pricing) oder mit dem Office 365 Advanced Compliance SKU-Add-on für Microsoft 365 E3, Microsoft 365 E3 (Preise für gemeinnützige Mitarbeiter) oder Office 365-SKUs erwerben.</span><span class="sxs-lookup"><span data-stu-id="5f396-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="5f396-107">Dieser Artikel ist Teil einer größeren Reihe von Artikeln über [Office 365 Nachrichtenverschlüsselung](ome.md).</span><span class="sxs-lookup"><span data-stu-id="5f396-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="5f396-108">Wenn eine Nachricht mit Office 365 erweiterten Nachrichtenverschlüsselung verschlüsselt wurde und Sie ein Microsoft 365-Administrator sind oder Sie der Absender der Nachricht sind, können Sie die Nachricht unter bestimmten Bedingungen widerrufen.</span><span class="sxs-lookup"><span data-stu-id="5f396-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="5f396-109">Administratoren widerrufen Nachrichten mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f396-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="5f396-110">Als Absender widerrufen Sie eine Nachricht, die Sie direkt aus Outlook im Internet gesendet haben.</span><span class="sxs-lookup"><span data-stu-id="5f396-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="5f396-111">In diesem Artikel werden die Umstände beschrieben, unter denen die Sperrung möglich ist, und wie dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="5f396-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="5f396-112">Verschlüsselte e-Mails, die Sie widerrufen können</span><span class="sxs-lookup"><span data-stu-id="5f396-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="5f396-113">Administratoren und Nachrichtenabsender können verschlüsselte e-Mails widerrufen, wenn der Empfänger eine Linkbasierte, verschlüsselte e-Mail-Nachricht erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="5f396-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="5f396-114">Wenn der Empfänger eine systemeigene Inline Erfahrung in einem unterstützten Outlook-Client empfangen hat, können Sie die Nachricht nicht widerrufen.</span><span class="sxs-lookup"><span data-stu-id="5f396-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="5f396-115">Ob ein Empfänger eine Linkbasierte Erfahrung oder eine Inline-Erfahrung erhält, hängt vom Typ der Empfänger Identität ab: Office 365-und Microsoft-Konto Empfänger (beispielsweise Outlook.com-Benutzer) erhalten eine Inline-Erfahrung in unterstützten Outlook-Clients.</span><span class="sxs-lookup"><span data-stu-id="5f396-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="5f396-116">Alle anderen Empfängertypen, wie etwa Gmail-und Yahoo-Empfänger, erhalten eine Linkbasierte Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="5f396-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="5f396-117">Administratoren und Nachrichtenabsender können Nachrichten widerrufen, die mit der Verschlüsselung verschlüsselt werden, die direkt in Outlook im Internet angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="5f396-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="5f396-118">Beispielsweise werden Nachrichten mit der Option "nur verschlüsseln" verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="5f396-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot mit der Option &quot;nur verschlüsseln&quot; in Outlook im Internet.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="5f396-120">Empfänger Erfahrung für gesperrte verschlüsselte e-Mails</span><span class="sxs-lookup"><span data-stu-id="5f396-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="5f396-121">Sobald eine e-Mail widerrufen wurde, erhält der Empfänger eine Fehlermeldung, wenn er über das Office 365 Nachrichten Verschlüsselungs Portal auf die verschlüsselte e-Mail zugreift: "die Nachricht wurde vom Absender widerrufen".</span><span class="sxs-lookup"><span data-stu-id="5f396-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Screenshot, der eine widerrufene verschlüsselte e-Mail zeigt.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="5f396-123">Vorgehensweise widerrufen einer verschlüsselten Nachricht, die Sie gesendet haben</span><span class="sxs-lookup"><span data-stu-id="5f396-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="5f396-124">Zum Widerrufen einer verschlüsselten Nachricht, die Sie gesendet haben, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="5f396-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="5f396-125">Navigieren Sie in Outlook im Internet in Ihrem Ordner " **gesendet** " zu der Nachricht, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="5f396-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="5f396-126">Wenn die e-Mail widerruflich ist, wird der Link "externen Zugriff entfernen" oben in der Nachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5f396-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot mit verschlüsselten e-Mails, die Sie in Outlook im Internet widerrufen möchten.":::

2. <span data-ttu-id="5f396-128">Klicken Sie auf **externen Zugriff Entfernen** , um die Nachricht zu widerrufen.</span><span class="sxs-lookup"><span data-stu-id="5f396-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="5f396-129">Die Meldung zeigt, dass der Status widerrufen wurde.</span><span class="sxs-lookup"><span data-stu-id="5f396-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot mit Entsperrter verschlüsselter Nachricht in Outlook im Internet.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="5f396-131">Vorgehensweise widerrufen einer verschlüsselten Nachricht als Administrator</span><span class="sxs-lookup"><span data-stu-id="5f396-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="5f396-132">Microsoft 365-Administratoren befolgen diese allgemeinen Schritte zum Widerrufen einer berechtigten verschlüsselten e-Mail:</span><span class="sxs-lookup"><span data-stu-id="5f396-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="5f396-133">Rufen Sie die Nachrichten-ID der e-Mail ab.</span><span class="sxs-lookup"><span data-stu-id="5f396-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="5f396-134">Stellen Sie sicher, dass Sie die Nachricht widerrufen können.</span><span class="sxs-lookup"><span data-stu-id="5f396-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="5f396-135">Die e-Mail widerrufen.</span><span class="sxs-lookup"><span data-stu-id="5f396-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="5f396-136">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="5f396-136">Step 1.</span></span> <span data-ttu-id="5f396-137">Abrufen der Nachrichten-ID der e-Mail</span><span class="sxs-lookup"><span data-stu-id="5f396-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="5f396-138">Bevor Sie eine verschlüsselte e-Mail widerrufen können, müssen Sie die Nachrichten-ID der e-Mail erfassen.</span><span class="sxs-lookup"><span data-stu-id="5f396-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="5f396-139">Die MessageId weist normalerweise das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="5f396-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="5f396-140">Es gibt mehrere Möglichkeiten, die Nachrichten-ID der e-Mail zu finden, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="5f396-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="5f396-141">In diesem Abschnitt werden einige Optionen beschrieben, aber Sie können eine beliebige Methode verwenden, die die ID bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5f396-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="5f396-142">So identifizieren Sie die Nachrichten-ID der e-Mail, die Sie mithilfe der Nachrichtenablaufverfolgung im Security &amp; Compliance Center widerrufen möchten</span><span class="sxs-lookup"><span data-stu-id="5f396-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="5f396-143">Suchen Sie nach der e-Mail nach Absender oder Empfänger mithilfe der [neuen Nachrichtenablaufverfolgung im Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="5f396-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="5f396-144">Nachdem Sie die e-Mail-Adresse gefunden haben, wählen Sie Sie aus, um den Bereich **Nachrichtenablauf Verfolgungs Details** aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="5f396-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="5f396-145">Erweitern Sie **Weitere Informationen** , um nach der Nachrichten-ID zu suchen.</span><span class="sxs-lookup"><span data-stu-id="5f396-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="5f396-146">So identifizieren Sie die Nachrichten-ID der e-Mail, die Sie mithilfe von Office-Nachrichten Verschlüsselungs Berichten im Security Compliance Center widerrufen möchten &amp;</span><span class="sxs-lookup"><span data-stu-id="5f396-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="5f396-147">&amp;Navigieren Sie im Security Compliance Center zum **Nachrichten Verschlüsselungs Bericht**.</span><span class="sxs-lookup"><span data-stu-id="5f396-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="5f396-148">Informationen zu diesem Bericht finden Sie unter [Anzeigen von e-Mail-Sicherheitsberichten im Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="5f396-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="5f396-149">Wählen Sie die Tabelle **Details anzeigen** aus, und identifizieren Sie die Nachricht, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="5f396-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="5f396-150">Doppelklicken Sie auf die Nachricht, um Details anzuzeigen, die die Nachrichten-ID enthalten.</span><span class="sxs-lookup"><span data-stu-id="5f396-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="5f396-151">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="5f396-151">Step 2.</span></span> <span data-ttu-id="5f396-152">Sicherstellen, dass die e-Mail widerruflich ist</span><span class="sxs-lookup"><span data-stu-id="5f396-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="5f396-153">Um zu überprüfen, ob Sie eine Nachricht widerrufen können, überprüfen Sie, ob das Feld Sperr Status im Verschlüsselungs Bericht in der Tabelle **Details** im Security &amp; Compliance Center angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5f396-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="5f396-154">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob Sie eine bestimmte e-Mail-Nachricht mithilfe von Windows PowerShell widerrufen können.</span><span class="sxs-lookup"><span data-stu-id="5f396-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="5f396-155">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="5f396-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5f396-156">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5f396-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5f396-157">Führen Sie das Cmdlet Get-OMEMessageStatus wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5f396-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="5f396-158">Dieser Befehl gibt den Betreff der Nachricht zurück und gibt an, ob die Nachricht widerruflich ist.</span><span class="sxs-lookup"><span data-stu-id="5f396-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="5f396-159">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5f396-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="5f396-160">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="5f396-160">Step 3.</span></span> <span data-ttu-id="5f396-161">E-Mail widerrufen</span><span class="sxs-lookup"><span data-stu-id="5f396-161">Revoke the mail</span></span>

<span data-ttu-id="5f396-162">Wenn Sie die Nachrichten-ID der zu widerrufenden e-Mail kennen und sichergestellt haben, dass die Nachricht widerruflich ist, können Sie die e-Mail mit dem Security &amp; Compliance Center oder Windows PowerShell widerrufen.</span><span class="sxs-lookup"><span data-stu-id="5f396-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="5f396-163">So widerrufen Sie die Nachricht mit dem Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="5f396-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="5f396-164">Stellen Sie mithilfe eines Arbeits-oder Schul Kontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit dem Security & Compliance Center her.</span><span class="sxs-lookup"><span data-stu-id="5f396-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="5f396-165">Wählen Sie im **Verschlüsselungs Bericht**in der Tabelle **Details** für die Nachricht die Option **Nachricht widerrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="5f396-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="5f396-166">Verwenden Sie das Cmdlet "OMEMessageRevocation", um eine e-Mail mithilfe von Windows PowerShell zu widerrufen.</span><span class="sxs-lookup"><span data-stu-id="5f396-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="5f396-167">Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5f396-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5f396-168">Führen Sie das Cmdlet "OMEMessageRevocation" wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5f396-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="5f396-169">Um zu überprüfen, ob die e-Mail widerrufen wurde, führen Sie das Get-OMEMessageStatus-Cmdlet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="5f396-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="5f396-170">Wenn die Sperrung erfolgreich war, gibt das Cmdlet das folgende Ergebnis zurück:</span><span class="sxs-lookup"><span data-stu-id="5f396-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="5f396-171">Weitere Informationen zu Office 365 erweiterte Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="5f396-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="5f396-172">Erweiterte Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="5f396-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="5f396-173">Office 365 erweiterte Nachrichtenverschlüsselung – e-Mail-Ablauf</span><span class="sxs-lookup"><span data-stu-id="5f396-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="5f396-174">Beschreibung des Nachrichtenrichtlinien-und Kompatibilitätsdiensts</span><span class="sxs-lookup"><span data-stu-id="5f396-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
