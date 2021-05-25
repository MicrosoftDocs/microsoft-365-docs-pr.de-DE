---
title: Verwalten der Office 365-Nachrichtenverschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Nachdem Sie die Einrichtung von Office 365-Nachrichtenverschlüsselung (OME) abgeschlossen haben, erfahren Sie, wie Sie Ihre Bereitstellung auf verschiedene Weise anpassen.
ms.openlocfilehash: a2b3dde44ea541deb41eeb9d55d5ed745fa6c719
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52650984"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="28432-103">Verwalten der Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="28432-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="28432-104">Nachdem Sie die Einrichtung von Office 365-Nachrichtenverschlüsselung (OME) abgeschlossen haben, können Sie die Konfiguration Ihrer Bereitstellung auf verschiedene Weise anpassen.</span><span class="sxs-lookup"><span data-stu-id="28432-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="28432-105">Sie können z. B. konfigurieren, ob Einmalpasscodes aktiviert, die Schaltfläche Verschlüsseln in Outlook im Web angezeigt werden soll und vieles mehr. </span><span class="sxs-lookup"><span data-stu-id="28432-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="28432-106">Die Aufgaben in diesem Artikel beschreiben, wie.</span><span class="sxs-lookup"><span data-stu-id="28432-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="28432-107">Verwalten, ob Google-, Yahoo- und Microsoft-Kontoempfänger diese Konten verwenden können, um sich beim Office 365-Nachrichtenverschlüsselung anmelden</span><span class="sxs-lookup"><span data-stu-id="28432-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="28432-108">Wenn Sie die neuen Office 365-Nachrichtenverschlüsselung einrichten, können Benutzer in Ihrer Organisation Nachrichten an Empfänger senden, die sich außerhalb Ihrer Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="28432-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="28432-109">Wenn der Empfänger eine soziale *ID* wie ein Google-, Yahoo- oder Microsoft-Konto verwendet, kann sich der Empfänger mit einer sozialen ID beim OME-Portal anmelden.</span><span class="sxs-lookup"><span data-stu-id="28432-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="28432-110">Wenn Sie möchten, können Sie festlegen, dass Empfänger keine sozialen IDs für die Anmeldung beim OME-Portal verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="28432-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="28432-111">So verwalten Sie, ob Empfänger soziale IDs zum Anmelden beim OME-Portal verwenden können</span><span class="sxs-lookup"><span data-stu-id="28432-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="28432-112">[Verbinden, Exchange Online Remote PowerShell zu verwenden.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="28432-112">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="28432-113">Führen Sie Set-OMEConfiguration cmdlet mit dem Parameter SocialIdSignIn wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="28432-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="28432-114">So deaktivieren Sie beispielsweise soziale IDs:</span><span class="sxs-lookup"><span data-stu-id="28432-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="28432-115">So aktivieren Sie soziale IDs:</span><span class="sxs-lookup"><span data-stu-id="28432-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="28432-116">Verwalten der Verwendung von Einmalpasscodes für das Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="28432-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="28432-117">Wenn der Empfänger einer von OME verschlüsselten Nachricht Outlook nicht verwendet, empfängt der Empfänger unabhängig vom vom Empfänger verwendeten Konto einen zeitlich begrenzten Webansichtslink, über den er die Nachricht lesen kann.</span><span class="sxs-lookup"><span data-stu-id="28432-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="28432-118">Dieser Link enthält einen einmal übergebenen Code.</span><span class="sxs-lookup"><span data-stu-id="28432-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="28432-119">Als Administrator können Sie entscheiden, ob Empfänger Einmalpasscodes verwenden können, um sich beim OME-Portal zu anmelden.</span><span class="sxs-lookup"><span data-stu-id="28432-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="28432-120">So verwalten Sie, ob OME Einmalpasscodes generiert</span><span class="sxs-lookup"><span data-stu-id="28432-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="28432-121">Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28432-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="28432-122">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28432-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="28432-123">Führen Sie Set-OMEConfiguration cmdlet mit dem PARAMETER OTPEnabled aus:</span><span class="sxs-lookup"><span data-stu-id="28432-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="28432-124">So deaktivieren Sie beispielsweise einmal bestandene Codes:</span><span class="sxs-lookup"><span data-stu-id="28432-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="28432-125">So aktivieren Sie einmal bestandene Codes:</span><span class="sxs-lookup"><span data-stu-id="28432-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="28432-126">Verwalten der Anzeige der Schaltfläche Verschlüsseln in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="28432-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="28432-127">Als Administrator können Sie verwalten, ob diese Schaltfläche endbenutzern angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="28432-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="28432-128">So verwalten Sie, ob die Schaltfläche Verschlüsseln im Outlook im Web angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="28432-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="28432-129">Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28432-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="28432-130">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28432-130">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="28432-131">Führen Sie Set-IRMConfiguration cmdlet mit dem Parameter -SimplifiedClientAccessEnabled aus:</span><span class="sxs-lookup"><span data-stu-id="28432-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="28432-132">So deaktivieren Sie beispielsweise die Schaltfläche **Verschlüsseln:**</span><span class="sxs-lookup"><span data-stu-id="28432-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="28432-133">So aktivieren Sie die **Schaltfläche** Verschlüsseln:</span><span class="sxs-lookup"><span data-stu-id="28432-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="28432-134">Aktivieren der dienstseitigen Entschlüsselung von E-Mail-Nachrichten für iOS-E-Mail-App-Benutzer</span><span class="sxs-lookup"><span data-stu-id="28432-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="28432-135">Die iOS-E-Mail-App kann Nachrichten, die mit nachrichtengeschützt sind, nicht Office 365-Nachrichtenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="28432-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="28432-136">Als Microsoft 365 können Sie die dienstseitige Entschlüsselung für Nachrichten anwenden, die an die iOS-Mail-App übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="28432-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="28432-137">Wenn Sie die dienstseitige Entschlüsselung verwenden, sendet der Dienst eine entschlüsselte Kopie der Nachricht an das iOS-Gerät.</span><span class="sxs-lookup"><span data-stu-id="28432-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="28432-138">Das Clientgerät speichert eine entschlüsselte Kopie der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="28432-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="28432-139">Die Nachricht behält auch Informationen zu Nutzungsrechten bei, auch wenn die iOS-Mail-App keine clientseitigen Nutzungsrechte auf den Benutzer angewendet hat.</span><span class="sxs-lookup"><span data-stu-id="28432-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="28432-140">Der Benutzer kann die Nachricht auch dann kopieren oder drucken, wenn er ursprünglich nicht die Rechte dazu hatte.</span><span class="sxs-lookup"><span data-stu-id="28432-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="28432-141">Wenn der Benutzer jedoch versucht, eine Aktion zu vollenden, die den Microsoft 365-E-Mail-Server erfordert, z. B. das Weiterleiten der Nachricht, erlaubt der Server die Aktion nicht, wenn der Benutzer ursprünglich nicht das Nutzungsrecht dazu hatte.</span><span class="sxs-lookup"><span data-stu-id="28432-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="28432-142">Endbenutzer können die Verwendungseinschränkung "Do Not Forward" jedoch umgehen, indem sie die Nachricht von einem anderen Konto in der iOS-Mail-App weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="28432-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="28432-143">Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von E-Mails einrichten, können Anlagen für verschlüsselte und rechtegeschützte E-Mails nicht in der iOS-Mail-App angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="28432-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="28432-144">Wenn Sie das Senden entschlüsselter Nachrichten an iOS-E-Mail-App-Benutzer nicht zulassen möchten, erhalten Benutzer eine Meldung, die besagt, dass sie nicht über die Rechte zum Anzeigen der Nachricht verfügen.</span><span class="sxs-lookup"><span data-stu-id="28432-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="28432-145">Standardmäßig ist die dienstseitige Entschlüsselung von E-Mail-Nachrichten nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="28432-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="28432-146">Weitere Informationen und eine Ansicht der Clienterfahrung finden Sie unter Anzeigen verschlüsselter Nachrichten auf Ihrem iPhone [oder iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="28432-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="28432-147">So verwalten Sie, ob iOS-E-Mail-App-Benutzer Nachrichten anzeigen können, die durch Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="28432-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="28432-148">Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28432-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="28432-149">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28432-149">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="28432-150">Führen Sie Set-ActiveSyncOrganizations cmdlet mit dem Parameter AllowRMSSupportForUnenlightenedApps aus:</span><span class="sxs-lookup"><span data-stu-id="28432-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="28432-151">So konfigurieren Sie den Dienst beispielsweise so, dass Nachrichten entschlüsselt werden, bevor sie an nicht aufleuchtete Apps wie die iOS-Mail-App gesendet werden:</span><span class="sxs-lookup"><span data-stu-id="28432-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="28432-152">Oder, um den Dienst so zu konfigurieren, dass entschlüsselte Nachrichten nicht an nicht entschlüsselte Apps gesendet werden:</span><span class="sxs-lookup"><span data-stu-id="28432-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="28432-153">Einzelne Postfachrichtlinien (OWA/ActiveSync) überschreiben diese Einstellungen (d. h., wenn -IRMEnabled in der entsprechenden OWA-Postfachrichtlinie auf False festgelegt ist, oder ActiveSync-Postfachrichtlinie, dann würden diese Konfigurationen nicht angewendet werden).</span><span class="sxs-lookup"><span data-stu-id="28432-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="28432-154">Aktivieren der dienstseitigen Entschlüsselung von E-Mail-Anlagen für Webbrowser-E-Mail-Clients</span><span class="sxs-lookup"><span data-stu-id="28432-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="28432-155">Normalerweise werden Anlagen automatisch verschlüsselt, Office 365 nachrichtenverschlüsselung verwenden.</span><span class="sxs-lookup"><span data-stu-id="28432-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="28432-156">Als Administrator können Sie die dienstseitige Entschlüsselung für E-Mail-Anlagen anwenden, die Benutzer aus einem Webbrowser herunterladen.</span><span class="sxs-lookup"><span data-stu-id="28432-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="28432-157">Wenn Sie die dienstseitige Entschlüsselung verwenden, sendet der Dienst eine entschlüsselte Kopie der Datei an das Gerät.</span><span class="sxs-lookup"><span data-stu-id="28432-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="28432-158">Die Nachricht ist weiterhin verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="28432-158">The message is still encrypted.</span></span> <span data-ttu-id="28432-159">Die E-Mail-Anlage speichert auch Informationen zu Nutzungsrechten, auch wenn der Browser keine clientseitigen Nutzungsrechte auf den Benutzer angewendet hat.</span><span class="sxs-lookup"><span data-stu-id="28432-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="28432-160">Der Benutzer kann die E-Mail-Anlage auch dann kopieren oder drucken, wenn er ursprünglich nicht die Rechte dazu hatte.</span><span class="sxs-lookup"><span data-stu-id="28432-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="28432-161">Wenn der Benutzer jedoch versucht, eine Aktion zu vollenden, die den Microsoft 365-E-Mail-Server erfordert, z. B. das Weiterleiten der Anlage, erlaubt der Server die Aktion nicht, wenn der Benutzer ursprünglich nicht das Nutzungsrecht dazu hatte.</span><span class="sxs-lookup"><span data-stu-id="28432-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="28432-162">Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von Anlagen einrichten, können Benutzer keine Anlagen für verschlüsselte und rechtegeschützte E-Mails in der iOS-Mail-App anzeigen.</span><span class="sxs-lookup"><span data-stu-id="28432-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="28432-163">Wenn Sie entschlüsselte E-Mail-Anlagen nicht zulassen möchten, was die Standardeinstellung ist, erhalten Benutzer eine Meldung, die besagt, dass sie nicht über die Rechte zum Anzeigen der Anlage verfügen.</span><span class="sxs-lookup"><span data-stu-id="28432-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="28432-164">Weitere Informationen dazu, wie Microsoft 365 verschlüsselung für [E-Mails und E-Mail-Anlagen](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails) mit der Option Encrypt-Only implementieren, finden Sie unter Encrypt-Only option for emails.</span><span class="sxs-lookup"><span data-stu-id="28432-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="28432-165">So verwalten Sie, ob E-Mail-Anlagen beim Herunterladen aus einem Webbrowser entschlüsselt werden</span><span class="sxs-lookup"><span data-stu-id="28432-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="28432-166">Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28432-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="28432-167">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28432-167">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="28432-168">Führen Sie Set-IRMConfiguration cmdlet mit dem Parameter DecryptAttachmentForEncryptOnly aus:</span><span class="sxs-lookup"><span data-stu-id="28432-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="28432-169">So konfigurieren Sie den Dienst beispielsweise so, dass E-Mail-Anlagen entschlüsselt werden, wenn ein Benutzer sie aus einem Webbrowser herunterlädt:</span><span class="sxs-lookup"><span data-stu-id="28432-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="28432-170">So konfigurieren Sie den Dienst so, dass verschlüsselte E-Mail-Anlagen beim Download hinterlassen werden:</span><span class="sxs-lookup"><span data-stu-id="28432-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="28432-171">Sicherstellen, dass alle externen Empfänger das OME-Portal zum Lesen verschlüsselter E-Mails verwenden</span><span class="sxs-lookup"><span data-stu-id="28432-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="28432-172">Sie können benutzerdefinierte Brandingvorlagen verwenden, um empfängern den Empfang einer Wrapper-E-Mail zu erzwingen, die sie zum Lesen verschlüsselter E-Mails im OME-Portal anstatt Outlook oder Outlook im Web leitet.</span><span class="sxs-lookup"><span data-stu-id="28432-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="28432-173">Sie können dies tun, wenn Sie eine bessere Kontrolle darüber wünschen, wie Empfänger die empfangenen E-Mails verwenden.</span><span class="sxs-lookup"><span data-stu-id="28432-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="28432-174">Wenn externe Empfänger beispielsweise E-Mails im Webportal anzeigen, können Sie ein Ablaufdatum für die E-Mail festlegen und die E-Mail widerrufen.</span><span class="sxs-lookup"><span data-stu-id="28432-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="28432-175">Diese Features werden nur über das OME-Portal unterstützt.</span><span class="sxs-lookup"><span data-stu-id="28432-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="28432-176">Sie können die Option Verschlüsseln und die Option Nicht weiterleiten verwenden, wenn Sie die Nachrichtenflussregeln erstellen.</span><span class="sxs-lookup"><span data-stu-id="28432-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="28432-177">Verwenden einer benutzerdefinierten Vorlage, um alle externen Empfänger zur Verwendung des OME-Portals und für verschlüsselte E-Mails zu zwingen</span><span class="sxs-lookup"><span data-stu-id="28432-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="28432-178">Verwenden Sie ein Arbeits- oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28432-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="28432-179">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28432-179">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="28432-180">Führen Sie New-TransportRule cmdlet aus:</span><span class="sxs-lookup"><span data-stu-id="28432-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="28432-181">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="28432-181">where:</span></span>

   - <span data-ttu-id="28432-182">`mail flow rule name` ist der Name, den Sie für die neue Nachrichtenflussregel verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="28432-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="28432-183">`option name` ist entweder `Encrypt` oder `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="28432-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="28432-184">`template name` ist der Name, den Sie der benutzerdefinierten Brandingvorlage gegeben haben, z. B. `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="28432-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="28432-185">So verschlüsseln Sie alle externen E-Mails mit der Vorlage "OME-Konfiguration", und wenden Sie die Encrypt-Only an:</span><span class="sxs-lookup"><span data-stu-id="28432-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="28432-186">So verschlüsseln Sie alle externen E-Mails mit der Vorlage "OME-Konfiguration", und wenden Sie die Option Nicht weiterleiten an:</span><span class="sxs-lookup"><span data-stu-id="28432-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="28432-187">Anpassen der Darstellung von E-Mail-Nachrichten und des OME-Portals</span><span class="sxs-lookup"><span data-stu-id="28432-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="28432-188">Ausführliche Informationen dazu, wie Sie OME für Ihre Organisation anpassen können, finden Sie unter [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="28432-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="28432-189">Deaktivieren der neuen Funktionen für OME</span><span class="sxs-lookup"><span data-stu-id="28432-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="28432-190">We hope it doesn't come to it, but if you need, disabling the new capabilities for OME is very straightforward.</span><span class="sxs-lookup"><span data-stu-id="28432-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="28432-191">Zunächst müssen Sie alle von Ihnen erstellten Nachrichtenflussregeln entfernen, die die neuen OME-Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="28432-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="28432-192">Informationen zum Entfernen von Nachrichtenflussregeln finden Sie unter [Verwalten von Nachrichtenflussregeln](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span><span class="sxs-lookup"><span data-stu-id="28432-192">For information about removing mail flow rules, see [Manage mail flow rules](/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules).</span></span> <span data-ttu-id="28432-193">Führen Sie dann die folgenden Schritte in Exchange Online PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="28432-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="28432-194">So deaktivieren Sie die neuen Funktionen für OME</span><span class="sxs-lookup"><span data-stu-id="28432-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="28432-195">Starten Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell und stellen Sie eine Verbindung mit Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="28432-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="28432-196">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="28432-196">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="28432-197">Wenn Sie die Schaltfläche **Verschlüsseln** im Outlook aktiviert haben, deaktivieren Sie sie, indem Sie das cmdlet Set-IRMConfiguration mit dem Parameter SimplifiedClientAccessEnabled ausführen.</span><span class="sxs-lookup"><span data-stu-id="28432-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="28432-198">Überspringen Sie andernfalls diesen Schritt.</span><span class="sxs-lookup"><span data-stu-id="28432-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="28432-199">Deaktivieren Sie die neuen Funktionen für OME, indem Sie das cmdlet Set-IRMConfiguration ausführen, für das der Parameter AzureRMSLicensingEnabled auf false festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="28432-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
