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
description: Nachdem Sie die Einrichtung Office 365 Nachrichtenverschlüsselung (OM) abgeschlossen haben, erfahren Sie, wie Sie Ihre Bereitstellung auf verschiedene Arten anpassen.
ms.openlocfilehash: 83fa620852ea9b2e0cd50d50b6715742658b7239
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815432"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="8cbfc-103">Verwalten der Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="8cbfc-103">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="8cbfc-104">Nachdem Sie die Einrichtung Office 365 Nachrichtenverschlüsselung (OM) abgeschlossen haben, können Sie die Konfiguration Ihrer Bereitstellung auf verschiedene Weise anpassen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-104">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="8cbfc-105">Beispielsweise können Sie konfigurieren, ob Sie einmalige Pass Codes aktivieren möchten, die Schaltfläche **verschlüsseln** in Outlook im Internet anzeigen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-105">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="8cbfc-106">In den Aufgaben in diesem Artikel wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-106">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="8cbfc-107">Verwalten, ob sich Google-, Yahoo-und Microsoft-Konto Empfänger mit diesen Konten beim Office 365 Nachrichten Verschlüsselungs Portal anmelden können</span><span class="sxs-lookup"><span data-stu-id="8cbfc-107">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="8cbfc-108">Wenn Sie die neuen Office 365 Nachrichten Verschlüsselungsfunktionen einrichten, können Benutzer in Ihrer Organisation Nachrichten an Empfänger außerhalb Ihrer Organisation senden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-108">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your organization.</span></span> <span data-ttu-id="8cbfc-109">Wenn der Empfänger eine *soziale ID* wie ein Google-Konto, ein Yahoo-Konto oder ein Microsoft-Konto verwendet, kann sich der Empfänger beim OM-Portal mit einer sozialen ID anmelden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-109">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="8cbfc-110">Wenn Sie möchten, können Sie festlegen, dass Empfänger keine sozialen IDs für die Anmeldung beim OM-Portal verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-110">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="8cbfc-111">So verwalten Sie, ob Empfänger soziale IDs verwenden können, um sich beim OM-Portal anzumelden</span><span class="sxs-lookup"><span data-stu-id="8cbfc-111">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="8cbfc-112">Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-112">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="8cbfc-113">Führen Sie das Cmdlet "OMEConfiguration" mit dem Parameter "SocialIdSignIn" wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-113">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="8cbfc-114">Um beispielsweise soziale IDs zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-114">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="8cbfc-115">So aktivieren Sie soziale IDs:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-115">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="8cbfc-116">Verwalten der Verwendung von einmaligen Pass Codes für das Office 365 Nachrichten Verschlüsselungs Portal</span><span class="sxs-lookup"><span data-stu-id="8cbfc-116">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="8cbfc-117">Wenn der Empfänger einer Nachricht, die von OM verschlüsselt wurde, Outlook nicht verwendet, unabhängig vom vom Empfänger verwendeten Konto, erhält der Empfänger einen Link zur zeitlich begrenzten Webansicht, mit dem Sie die Nachricht lesen können.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-117">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="8cbfc-118">Dieser Link enthält einen One-Time-Pass-Code.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-118">This link includes a one-time pass code.</span></span> <span data-ttu-id="8cbfc-119">Als Administrator können Sie entscheiden, ob Empfänger die einmaligen Pass Codes verwenden können, um sich beim OM-Portal anzumelden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-119">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="8cbfc-120">So verwalten Sie, ob OM einen einmal Durchlaufcode generiert</span><span class="sxs-lookup"><span data-stu-id="8cbfc-120">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="8cbfc-121">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-121">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="8cbfc-122">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-122">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8cbfc-123">Führen Sie das Cmdlet "OMEConfiguration" mit dem Parameter "OTPEnabled" aus:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-123">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="8cbfc-124">Beispielsweise zum Deaktivieren von einmaligen Pass Codes:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-124">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="8cbfc-125">So aktivieren Sie einmalige Pass Codes:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-125">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="8cbfc-126">Verwalten der Anzeige der Schaltfläche "verschlüsseln" in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="8cbfc-126">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="8cbfc-127">Als Administrator können Sie steuern, ob diese Schaltfläche Endbenutzern angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-127">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="8cbfc-128">So verwalten Sie, ob die Schaltfläche Verschlüsseln in Outlook im Internet angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="8cbfc-128">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="8cbfc-129">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-129">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="8cbfc-130">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-130">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8cbfc-131">Führen Sie das Cmdlet "IRMConfiguration" mit dem-SimplifiedClientAccessEnabled-Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-131">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="8cbfc-132">Um beispielsweise die Schaltfläche **verschlüsseln** zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-132">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="8cbfc-133">So aktivieren Sie die Schaltfläche **verschlüsseln** :</span><span class="sxs-lookup"><span data-stu-id="8cbfc-133">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="8cbfc-134">Aktivieren der dienstseitigen Entschlüsselung von e-Mail-Nachrichten für Benutzer von IOS Mail App</span><span class="sxs-lookup"><span data-stu-id="8cbfc-134">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="8cbfc-135">Die IOS Mail-App kann Nachrichten, die mit Office 365 Nachrichtenverschlüsselung geschützt sind, nicht entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-135">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="8cbfc-136">Als Microsoft 365-Administrator können Sie dienstseitige Entschlüsselung für Nachrichten anwenden, die an die IOS-Mail-App übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-136">As a Microsoft 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="8cbfc-137">Wenn Sie sich für die Verwendung der dienstseitigen Entschlüsselung entscheiden, sendet der Dienst eine entschlüsselte Kopie der Nachricht an das IOS-Gerät.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-137">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="8cbfc-138">Das Clientgerät speichert eine entschlüsselte Kopie der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-138">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="8cbfc-139">Die Nachricht behält auch Informationen zu Nutzungsrechten bei, obwohl die IOS-Mail-App keine clientseitigen Nutzungsrechte für den Benutzer anwendet.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-139">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="8cbfc-140">Der Benutzer kann die Nachricht auch dann kopieren oder ausdrucken, wenn er ursprünglich nicht über die Rechte dazu verfügt.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-140">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="8cbfc-141">Wenn der Benutzer jedoch versucht, eine Aktion abzuschließen, bei der der Microsoft 365-e-Mail-Server erforderlich ist, beispielsweise das Weiterleiten der Nachricht, wird die Aktion vom Server nicht zugelassen, wenn der Benutzer ursprünglich nicht über das Recht zum Verwenden der Anwendung verfügt.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-141">However, if the user attempts to complete an action that requires the Microsoft 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="8cbfc-142">Endbenutzer können jedoch die Verwendungseinschränkung "nicht weiterleiten" umgehen, indem Sie die Nachricht von einem anderen Konto innerhalb der IOS-Mail-App weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-142">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="8cbfc-143">Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von e-Mails einrichten, können Anlagen für verschlüsselte und Rechte geschützte Nachrichten nicht in der IOS-Mail-App angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-143">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="8cbfc-144">Wenn Sie nicht zulassen, dass entschlüsselte Nachrichten an Benutzer von IOS-Mail-apps gesendet werden, erhalten Benutzer eine Nachricht, die besagt, dass Sie nicht über die Berechtigung zum Anzeigen der Nachricht verfügen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-144">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="8cbfc-145">Standardmäßig ist die dienstseitige Entschlüsselung von e-Mail-Nachrichten nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-145">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="8cbfc-146">Weitere Informationen und eine Übersicht über die Clientumgebung finden Sie unter Anzeigen von [verschlüsselten Nachrichten auf Ihrem iPhone oder iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-146">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="8cbfc-147">So verwalten Sie, ob Benutzer von IOS-Mail-apps Nachrichten anzeigen können, die durch Office 365 Nachrichtenverschlüsselung geschützt sind</span><span class="sxs-lookup"><span data-stu-id="8cbfc-147">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="8cbfc-148">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-148">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="8cbfc-149">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-149">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8cbfc-150">Führen Sie das Cmdlet "ActiveSyncOrganizations" mit dem Parameter "AllowRMSSupportForUnenlightenedApps" aus:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-150">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="8cbfc-151">Beispielsweise zum Konfigurieren des Diensts zum Entschlüsseln von Nachrichten, bevor Sie an nicht aufgeklärte apps wie die IOS-Mail-App gesendet werden:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-151">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="8cbfc-152">Oder, um den Dienst so zu konfigurieren, dass entschlüsselte Nachrichten nicht an nicht aufgeklärte apps gesendet werden:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-152">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="8cbfc-153">Einzelne Postfachrichtlinien (OWA/ActiveSync) setzen diese Einstellungen außer Kraft (d. h., wenn-den IRMEnabled in der jeweiligen OWA-Postfachrichtlinie oder in der ActiveSync-Postfachrichtlinie auf false festgelegt ist, werden diese Konfigurationen nicht angewendet).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-153">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="8cbfc-154">Aktivieren der dienstseitigen Entschlüsselung von e-Mail-Anlagen für Webbrowser-e-Mail-Clients</span><span class="sxs-lookup"><span data-stu-id="8cbfc-154">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="8cbfc-155">Normalerweise werden Anlagen automatisch verschlüsselt, wenn Sie Office 365 Nachrichtenverschlüsselung verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-155">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="8cbfc-156">Als Administrator können Sie dienstseitige Entschlüsselung für e-Mail-Anlagen anwenden, die von Benutzern aus einem Webbrowser heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-156">As an administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="8cbfc-157">Wenn Sie die dienstseitige Entschlüsselung verwenden, sendet der Dienst eine entschlüsselte Kopie der Datei an das Gerät.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-157">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="8cbfc-158">Die Nachricht ist weiterhin verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-158">The message is still encrypted.</span></span> <span data-ttu-id="8cbfc-159">Die e-Mail-Anlage behält auch Informationen zu Nutzungsrechten, obwohl der Browser keine clientseitigen Nutzungsrechte für den Benutzer anwendet.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-159">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="8cbfc-160">Der Benutzer kann die e-Mail-Anlage auch dann kopieren oder ausdrucken, wenn er ursprünglich nicht über die Rechte dazu verfügt.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-160">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="8cbfc-161">Wenn der Benutzer jedoch versucht, eine Aktion abzuschließen, bei der der Microsoft 365-e-Mail-Server erforderlich ist, beispielsweise das Weiterleiten der Anlage, wird die Aktion vom Server nicht zugelassen, wenn der Benutzer ursprünglich nicht über das Recht zum Verwenden der Anwendung verfügt.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-161">However, if the user tries to complete an action that requires the Microsoft 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="8cbfc-162">Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von Anlagen einrichten, können Benutzer keine Anlagen in verschlüsselter und mit rechten geschützter e-Mail in der IOS Mail-App anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-162">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="8cbfc-163">Wenn Sie entschlüsselte e-Mail-Anlagen nicht zulassen (Standardeinstellung), erhalten Benutzer eine Meldung, die besagt, dass Sie nicht über die Berechtigung zum Anzeigen der Anlage verfügen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-163">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="8cbfc-164">Weitere Informationen dazu, wie Microsoft 365 die Verschlüsselung von e-Mails und e-Mail-Anlagen mit der Option "nur verschlüsseln" implementiert, finden Sie unter [verschlüsseln-only-Option für e-Mails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="8cbfc-164">For more information about how Microsoft 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="8cbfc-165">So verwalten Sie, ob e-Mail-Anlagen beim Herunterladen aus einem Webbrowser entschlüsselt werden</span><span class="sxs-lookup"><span data-stu-id="8cbfc-165">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="8cbfc-166">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-166">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="8cbfc-167">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-167">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8cbfc-168">Führen Sie das Cmdlet "IRMConfiguration" mit dem Parameter "DecryptAttachmentForEncryptOnly" aus:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-168">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="8cbfc-169">Um beispielsweise den Dienst so zu konfigurieren, dass e-Mail-Anlagen entschlüsselt werden, wenn ein Benutzer Sie von einem Webbrowser herunterlädt:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-169">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="8cbfc-170">So konfigurieren Sie den Dienst so, dass verschlüsselte e-Mail-Anlagen beim Herunterladen verlassen werden:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-170">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="8cbfc-171">Sicherstellen, dass alle externen Empfänger das OM-Portal zum Lesen verschlüsselter e-Mails verwenden</span><span class="sxs-lookup"><span data-stu-id="8cbfc-171">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="8cbfc-172">Sie können benutzerdefinierte Branding-Vorlagen verwenden, um zu erzwingen, dass Empfänger eine Wrapper-e-Mail erhalten, die Sie dazu leitet, verschlüsselte e-Mails im OM-Portal zu lesen, anstatt Outlook oder Outlook im Web zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-172">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="8cbfc-173">Dies empfiehlt sich, wenn Sie mehr Kontrolle über die Verwendung von e-Mails erhalten möchten, die von Empfängern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-173">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="8cbfc-174">Wenn beispielsweise externe Empfänger e-Mails im Webportal anzeigen, können Sie ein Ablaufdatum für die e-Mail festlegen, und Sie können die e-Mail widerrufen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-174">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="8cbfc-175">Diese Features werden nur über das OM-Portal unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-175">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="8cbfc-176">Sie können die Option Verschlüsseln und die Option nicht weiterleiten beim Erstellen der Nachrichtenfluss Regeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-176">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="8cbfc-177">Verwenden einer benutzerdefinierten Vorlage, um zu erzwingen, dass alle externen Empfänger das OM-Portal und für verschlüsselte e-Mails verwenden</span><span class="sxs-lookup"><span data-stu-id="8cbfc-177">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="8cbfc-178">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-178">Use a work or school account that has global administrator permissions in your organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="8cbfc-179">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-179">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8cbfc-180">Führen Sie das Cmdlet New-TransportRule aus:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-180">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="8cbfc-181">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-181">where:</span></span>

   - <span data-ttu-id="8cbfc-182">`mail flow rule name`ist der Name, den Sie für die neue Nachrichtenfluss Regel verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-182">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="8cbfc-183">`option name`ist entweder `Encrypt` oder `Do Not Forward` .</span><span class="sxs-lookup"><span data-stu-id="8cbfc-183">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="8cbfc-184">`template name`ist der Name, den Sie beispielsweise der benutzerdefinierten Branding-Vorlage gegeben haben `OME Configuration` .</span><span class="sxs-lookup"><span data-stu-id="8cbfc-184">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="8cbfc-185">So verschlüsseln Sie alle externen e-Mails mit der Vorlage "OM-Konfiguration" und wenden die Option "nur verschlüsseln" an:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-185">To encrypt all external email with the "OME Configuration" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

   <span data-ttu-id="8cbfc-186">So verschlüsseln Sie alle externen e-Mails mit der Vorlage "OM-Konfiguration" und wenden die Option "nicht weiterleiten" an:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-186">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "OME Configuration"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="8cbfc-187">Anpassen der Darstellung von e-Mail-Nachrichten und des OM-Portals</span><span class="sxs-lookup"><span data-stu-id="8cbfc-187">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="8cbfc-188">Ausführliche Informationen dazu, wie Sie OM für Ihre Organisation anpassen können, finden Sie unter [Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-188">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="8cbfc-189">Deaktivieren der neuen Funktionen für OM</span><span class="sxs-lookup"><span data-stu-id="8cbfc-189">Disable the new capabilities for OME</span></span>

<span data-ttu-id="8cbfc-190">Wir hoffen, dass es nicht dazu kommt, aber wenn Sie dies benötigen, ist die Deaktivierung der neuen Funktionen für OM sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-190">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="8cbfc-191">Zunächst müssen Sie alle e-Mail-Flussregeln, die Sie erstellt haben, mit den neuen OM-Funktionen entfernen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-191">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="8cbfc-192">Informationen zum Entfernen von Nachrichtenfluss Regeln finden Sie unter [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-192">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="8cbfc-193">Führen Sie dann die folgenden Schritte in Exchange Online PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-193">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="8cbfc-194">So deaktivieren Sie die neuen Funktionen für OM</span><span class="sxs-lookup"><span data-stu-id="8cbfc-194">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="8cbfc-195">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-195">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="8cbfc-196">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="8cbfc-196">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="8cbfc-197">Wenn Sie die Schaltfläche **verschlüsseln** in Outlook im Internet aktiviert haben, deaktivieren Sie Sie, indem Sie das CmdletSet-IRMConfiguration mit dem Parameter SimplifiedClientAccessEnabled ausführen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-197">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="8cbfc-198">Andernfalls können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="8cbfc-198">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="8cbfc-199">Deaktivieren Sie die neuen Funktionen für OM, indem Sie das Cmdlet "IRMConfiguration" ausführen, wobei der Parameter "AzureRMSLicensingEnabled" auf "false" festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="8cbfc-199">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
