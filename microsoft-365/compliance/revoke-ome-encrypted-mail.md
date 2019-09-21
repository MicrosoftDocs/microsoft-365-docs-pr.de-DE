---
title: Widerrufen von E-Mails, die von der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden
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
description: Als Office 365 Administrator können Sie bestimmte e-Mails widerrufen, die mit Office 365 erweiterter Nachrichtenverschlüsselung verschlüsselt wurden.
ms.openlocfilehash: e55129f68c7add589bd973b36f069d7cdbf631cf
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081983"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="ee1c0-103">Widerrufen von E-Mails, die von der erweiterten Office 365-Nachrichtenverschlüsselung verschlüsselt wurden</span><span class="sxs-lookup"><span data-stu-id="ee1c0-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="ee1c0-104">Die e-Mail-Sperrung wird im Rahmen Office 365 erweiterten Nachrichtenverschlüsselung angeboten.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="ee1c0-105">Office 365 erweiterte Nachrichtenverschlüsselung steht über Office 365 Nachrichtenverschlüsselung in bestimmten Abonnements zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-105">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="ee1c0-106">Die erweiterte Nachrichtenverschlüsselung ist in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 und Office 365 Education A5 enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-106">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="ee1c0-107">Wenn Ihre Organisation über ein Office 365es Abonnement verfügt, das nicht Office 365 erweiterte Nachrichtenverschlüsselung enthält, können Sie erweiterte Nachrichtenverschlüsselung als Add-on mit E5-Kompatibilität der Advanced Compliance-SKU erwerben.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-107">If your organization has an Office 365 subscription that does not include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="ee1c0-108">Dieser Artikel ist Teil einer größeren Reihe von Artikeln über [Office 365 Nachrichtenverschlüsselung](ome.md).</span><span class="sxs-lookup"><span data-stu-id="ee1c0-108">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="ee1c0-109">Wenn eine Nachricht mit Office 365 erweiterten Nachrichtenverschlüsselung verschlüsselt wurde und Sie ein Office 365 Administrator sind, können Sie die Nachricht unter bestimmten Bedingungen widerrufen.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-109">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="ee1c0-110">In diesem Artikel werden die Umstände beschrieben, unter denen die Sperrung möglich ist, und wie dies geschieht.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-110">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="ee1c0-111">Verschlüsselte e-Mails, die Sie widerrufen können</span><span class="sxs-lookup"><span data-stu-id="ee1c0-111">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="ee1c0-112">Sie können verschlüsselte e-Mails widerrufen, wenn der Empfänger eine Linkbasierte, eingebrannte verschlüsselte e-Mail erhalten hat.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-112">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="ee1c0-113">Wenn der Empfänger eine systemeigene Inline Erfahrung in einem unterstützten Outlook-Client empfangen hat, können diese e-Mails nicht widerrufen werden.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-113">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="ee1c0-114">Ob ein Empfänger eine Linkbasierte Erfahrung oder eine Inline-Erfahrung erhält, hängt vom Typ der Empfänger Identität ab: Office 365-und Microsoft-Konto Empfänger (beispielsweise Outlook.com-Benutzer) erhalten eine Inline-Erfahrung in unterstützten Outlook-Clients.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-114">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="ee1c0-115">Alle anderen Empfängertypen, wie etwa Gmail-Empfänger, erhalten eine Linkbasierte Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-115">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="ee1c0-116">Empfänger Erfahrung für gesperrte verschlüsselte e-Mails</span><span class="sxs-lookup"><span data-stu-id="ee1c0-116">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="ee1c0-117">Sobald eine e-Mail widerrufen wurde, erhält der Empfänger eine Fehlermeldung, wenn er über das Office 365 Nachrichten Verschlüsselungs Portal auf die verschlüsselte e-Mail zugreift: "die Nachricht wurde vom Absender widerrufen".</span><span class="sxs-lookup"><span data-stu-id="ee1c0-117">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Screenshot, der eine widerrufene verschlüsselte e-Mail zeigt.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="ee1c0-119">Vorgehensweise widerrufen einer verschlüsselten e-Mail</span><span class="sxs-lookup"><span data-stu-id="ee1c0-119">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="ee1c0-120">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-120">Step 1.</span></span> <span data-ttu-id="ee1c0-121">Abrufen der Nachrichten-ID der e-Mail</span><span class="sxs-lookup"><span data-stu-id="ee1c0-121">Obtain the Message ID of the email</span></span>

<span data-ttu-id="ee1c0-122">Bevor Sie eine verschlüsselte e-Mail widerrufen können, erfassen Sie die Nachrichten-ID der e-Mail.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-122">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="ee1c0-123">Die MessageId weist normalerweise das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-123">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="ee1c0-124">Es gibt mehrere Möglichkeiten, die Nachrichten-ID der e-Mail zu finden, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-124">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="ee1c0-125">In diesem Abschnitt werden einige Optionen beschrieben, aber Sie können eine beliebige Methode verwenden, die die ID bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-125">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="ee1c0-126">So identifizieren Sie die Nachrichten-ID der e-Mail, die Sie mithilfe der Nachrichtenablaufverfolgung im Security &amp; Compliance Center widerrufen möchten</span><span class="sxs-lookup"><span data-stu-id="ee1c0-126">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="ee1c0-127">Suchen Sie nach der e-Mail nach Absender oder Empfänger mithilfe der [neuen Nachrichtenablaufverfolgung in Office 365 Security #a0 Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="ee1c0-127">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="ee1c0-128">Nachdem Sie die e-Mail-Adresse gefunden haben, wählen Sie Sie aus, um den Bereich **Nachrichtenablauf Verfolgungs Details** aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-128">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="ee1c0-129">Erweitern Sie **Weitere Informationen** , um nach der Nachrichten-ID zu suchen.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-129">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="ee1c0-130">So identifizieren Sie die Nachrichten-ID der e-Mail, die Sie mithilfe von Office-Nachrichten Verschlüsselungs Berichten im &amp; Security Compliance Center widerrufen möchten</span><span class="sxs-lookup"><span data-stu-id="ee1c0-130">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="ee1c0-131">Navigieren Sie im &amp; Security Compliance Center zum **Nachrichten Verschlüsselungs Bericht**.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-131">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="ee1c0-132">Informationen zu diesem Bericht finden Sie unter [Anzeigen von e-Mail-Sicherheits &amp; Berichten im Security Compliance Center](view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="ee1c0-132">For information on this report, see [View email security reports in the Security &amp; Compliance Center](view-email-security-reports.md).</span></span>

2. <span data-ttu-id="ee1c0-133">Wählen Sie die Tabelle **Details anzeigen** aus, und identifizieren Sie die Nachricht, die Sie widerrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-133">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="ee1c0-134">Doppelklicken Sie auf die Nachricht, um Details anzuzeigen, die die Nachrichten-ID enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-134">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="ee1c0-135">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-135">Step 2.</span></span> <span data-ttu-id="ee1c0-136">Sicherstellen, dass die e-Mail widerruflich ist</span><span class="sxs-lookup"><span data-stu-id="ee1c0-136">Verify that the mail is revocable</span></span>

<span data-ttu-id="ee1c0-137">Um zu überprüfen, ob Sie eine Nachricht widerrufen können, überprüfen Sie, ob das Feld Sperr Status im Verschlüsselungs \*\*\*\* Bericht in der Tabelle Details &amp; im Security Compliance Center angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-137">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="ee1c0-138">Führen Sie die folgenden Schritte aus, um zu überprüfen, ob Sie eine bestimmte e-Mail-Nachricht mithilfe von Windows PowerShell widerrufen können.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-138">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="ee1c0-139">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-139">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="ee1c0-140">Anweisungen finden Sie unter [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="ee1c0-140">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ee1c0-141">Führen Sie das Cmdlet Get-OMEMessageStatus wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-141">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="ee1c0-142">Gibt den Betreff der Nachricht zurück und gibt an, ob die Nachricht widerruflich ist.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-142">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="ee1c0-143">For example,</span><span class="sxs-lookup"><span data-stu-id="ee1c0-143">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="ee1c0-144">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-144">Step 3.</span></span> <span data-ttu-id="ee1c0-145">E-Mail widerrufen</span><span class="sxs-lookup"><span data-stu-id="ee1c0-145">Revoke the mail</span></span>

<span data-ttu-id="ee1c0-146">Wenn Sie die Nachrichten-ID der zu widerrufenden e-Mail kennen und sichergestellt haben, dass die Nachricht widerruflich ist, können Sie die e-Mail mithilfe des Security &amp; Compliance Centers oder von Windows PowerShell widerrufen.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-146">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="ee1c0-147">So widerrufen Sie die Nachricht mit &amp; dem Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="ee1c0-147">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="ee1c0-148">Wenn Sie die e-Mail im Security &amp; Compliance Center widerrufen möchten, wählen Sie im Verschlüsselungs Bericht in der Tabelle **Details** für die Nachricht die Option **Nachricht widerrufen**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-148">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="ee1c0-149">Sie können eine e-Mail mithilfe von Windows PowerShell widerrufen, indem Sie das Cmdlet "OMEMessageRevocation" verwenden.</span><span class="sxs-lookup"><span data-stu-id="ee1c0-149">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="ee1c0-150">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="ee1c0-150">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="ee1c0-151">Führen Sie das Cmdlet "OMEMessageRevocation" wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-151">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="ee1c0-152">Um zu überprüfen, ob die e-Mail widerrufen wurde, führen Sie das Get-OMEMessageStatus-Cmdlet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-152">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="ee1c0-153">Wenn die Sperrung erfolgreich war, gibt das Cmdlet das folgende Ergebnis zurück:</span><span class="sxs-lookup"><span data-stu-id="ee1c0-153">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="ee1c0-154">Weitere Informationen zu Office 365 erweiterte Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ee1c0-154">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="ee1c0-155">Erweiterte Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ee1c0-155">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="ee1c0-156">Office 365 erweiterte Nachrichtenverschlüsselung – e-Mail-Ablauf</span><span class="sxs-lookup"><span data-stu-id="ee1c0-156">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="ee1c0-157">Beschreibung des Nachrichtenrichtlinien-und Kompatibilitätsdiensts</span><span class="sxs-lookup"><span data-stu-id="ee1c0-157">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
