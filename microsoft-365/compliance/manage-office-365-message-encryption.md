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
description: Nachdem Sie die Einrichtung Office 365 Nachrichtenverschlüsselung (OM) abgeschlossen haben, können Sie die Konfiguration Ihrer Bereitstellung auf verschiedene Weise anpassen. Beispielsweise können Sie konfigurieren, ob Sie einmalige Pass Codes aktivieren möchten, die Schaltfläche Protect in Outlook im Internet anzeigen und vieles mehr. In den Aufgaben in diesem Artikel wird beschrieben, wie.
ms.openlocfilehash: 102d57681e049bf803b377fea97cc0fdb11affb2
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2020
ms.locfileid: "42562002"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="f14e7-105">Verwalten der Office 365-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="f14e7-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="f14e7-106">Nachdem Sie die Einrichtung Office 365 Nachrichtenverschlüsselung (OM) abgeschlossen haben, können Sie die Konfiguration Ihrer Bereitstellung auf verschiedene Weise anpassen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-106">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in several ways.</span></span> <span data-ttu-id="f14e7-107">Beispielsweise können Sie konfigurieren, ob Sie einmalige Pass Codes aktivieren möchten, die Schaltfläche **verschlüsseln** in Outlook im Internet anzeigen und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="f14e7-107">For example, you can configure whether to enable one-time pass codes, display the **Encrypt** button in Outlook on the web, and more.</span></span> <span data-ttu-id="f14e7-108">In den Aufgaben in diesem Artikel wird beschrieben, wie.</span><span class="sxs-lookup"><span data-stu-id="f14e7-108">The tasks in this article describe how.</span></span>

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="f14e7-109">Verwalten, ob sich Google-, Yahoo-und Microsoft-Konto Empfänger mit diesen Konten beim Office 365 Nachrichten Verschlüsselungs Portal anmelden können</span><span class="sxs-lookup"><span data-stu-id="f14e7-109">Manage whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="f14e7-110">Wenn Sie die neuen Office 365 Nachrichten Verschlüsselungsfunktionen einrichten, können Benutzer in Ihrer Organisation Nachrichten an Empfänger senden, die sich außerhalb Ihrer Office 365 Organisation befinden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-110">When you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization.</span></span> <span data-ttu-id="f14e7-111">Wenn der Empfänger eine *soziale ID* wie ein Google-Konto, ein Yahoo-Konto oder ein Microsoft-Konto verwendet, kann sich der Empfänger beim OM-Portal mit einer sozialen ID anmelden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-111">If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal with a social ID.</span></span> <span data-ttu-id="f14e7-112">Wenn Sie möchten, können Sie festlegen, dass Empfänger keine sozialen IDs für die Anmeldung beim OM-Portal verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-112">If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="f14e7-113">So verwalten Sie, ob Empfänger soziale IDs verwenden können, um sich beim OM-Portal anzumelden</span><span class="sxs-lookup"><span data-stu-id="f14e7-113">To manage whether recipients can use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="f14e7-114">Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f14e7-114">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="f14e7-115">Führen Sie das Cmdlet "OMEConfiguration" mit dem Parameter "SocialIdSignIn" wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f14e7-115">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   <span data-ttu-id="f14e7-116">Um beispielsweise soziale IDs zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f14e7-116">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="f14e7-117">So aktivieren Sie soziale IDs:</span><span class="sxs-lookup"><span data-stu-id="f14e7-117">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a><span data-ttu-id="f14e7-118">Verwalten der Verwendung von einmaligen Pass Codes für das Office 365 Nachrichten Verschlüsselungs Portal</span><span class="sxs-lookup"><span data-stu-id="f14e7-118">Manage the use of one-time pass codes for the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="f14e7-119">Wenn der Empfänger einer Nachricht, die von OM verschlüsselt wurde, Outlook nicht verwendet, unabhängig vom vom Empfänger verwendeten Konto, erhält der Empfänger einen Link zur zeitlich begrenzten Webansicht, mit dem Sie die Nachricht lesen können.</span><span class="sxs-lookup"><span data-stu-id="f14e7-119">If the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message.</span></span> <span data-ttu-id="f14e7-120">Dieser Link enthält einen One-Time-Pass-Code.</span><span class="sxs-lookup"><span data-stu-id="f14e7-120">This link includes a one-time pass code.</span></span> <span data-ttu-id="f14e7-121">Als Administrator können Sie entscheiden, ob Empfänger die einmaligen Pass Codes verwenden können, um sich beim OM-Portal anzumelden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-121">As an administrator, you can decide if recipients can use one-time pass codes to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a><span data-ttu-id="f14e7-122">So verwalten Sie, ob OM einen einmal Durchlaufcode generiert</span><span class="sxs-lookup"><span data-stu-id="f14e7-122">To manage whether OME generates one-time pass codes</span></span>
  
1. <span data-ttu-id="f14e7-123">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="f14e7-123">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f14e7-124">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f14e7-124">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f14e7-125">Führen Sie das Cmdlet "OMEConfiguration" mit dem Parameter "OTPEnabled" aus:</span><span class="sxs-lookup"><span data-stu-id="f14e7-125">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="f14e7-126">Beispielsweise zum Deaktivieren von einmaligen Pass Codes:</span><span class="sxs-lookup"><span data-stu-id="f14e7-126">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="f14e7-127">So aktivieren Sie einmalige Pass Codes:</span><span class="sxs-lookup"><span data-stu-id="f14e7-127">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-encrypt-button-in-outlook-on-the-web"></a><span data-ttu-id="f14e7-128">Verwalten der Anzeige der Schaltfläche "verschlüsseln" in Outlook im Internet</span><span class="sxs-lookup"><span data-stu-id="f14e7-128">Manage the display of the Encrypt button in Outlook on the web</span></span>

<span data-ttu-id="f14e7-129">Als Administrator können Sie steuern, ob diese Schaltfläche Endbenutzern angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f14e7-129">As an administrator, you can manage whether to display this button to end users.</span></span>
  
### <a name="to-manage-whether-the-encrypt-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="f14e7-130">So verwalten Sie, ob die Schaltfläche Verschlüsseln in Outlook im Internet angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="f14e7-130">To manage whether the Encrypt button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="f14e7-131">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="f14e7-131">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f14e7-132">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f14e7-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f14e7-133">Führen Sie das Cmdlet "IRMConfiguration" mit dem-SimplifiedClientAccessEnabled-Parameter aus:</span><span class="sxs-lookup"><span data-stu-id="f14e7-133">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="f14e7-134">Um beispielsweise die Schaltfläche **verschlüsseln** zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="f14e7-134">For example, to disable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="f14e7-135">So aktivieren Sie die Schaltfläche **verschlüsseln** :</span><span class="sxs-lookup"><span data-stu-id="f14e7-135">To enable the **Encrypt** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="f14e7-136">Aktivieren der dienstseitigen Entschlüsselung von e-Mail-Nachrichten für Benutzer von IOS Mail App</span><span class="sxs-lookup"><span data-stu-id="f14e7-136">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="f14e7-137">Die IOS Mail-App kann Nachrichten, die mit Office 365 Nachrichtenverschlüsselung geschützt sind, nicht entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="f14e7-137">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption.</span></span> <span data-ttu-id="f14e7-138">Als Office 365 Administrator können Sie die dienstseitige Entschlüsselung für Nachrichten anwenden, die an die IOS-Mail-App übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-138">As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app.</span></span> <span data-ttu-id="f14e7-139">Wenn Sie sich für die Verwendung der dienstseitigen Entschlüsselung entscheiden, sendet der Dienst eine entschlüsselte Kopie der Nachricht an das IOS-Gerät.</span><span class="sxs-lookup"><span data-stu-id="f14e7-139">When you choose to do use service-side decryption, the service sends a decrypted copy of the message to the iOS device.</span></span> <span data-ttu-id="f14e7-140">Das Clientgerät speichert eine entschlüsselte Kopie der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f14e7-140">The client device stores a decrypted copy of the message.</span></span> <span data-ttu-id="f14e7-141">Die Nachricht behält auch Informationen zu Nutzungsrechten bei, obwohl die IOS-Mail-App keine clientseitigen Nutzungsrechte für den Benutzer anwendet.</span><span class="sxs-lookup"><span data-stu-id="f14e7-141">The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="f14e7-142">Der Benutzer kann die Nachricht auch dann kopieren oder ausdrucken, wenn er ursprünglich nicht über die Rechte dazu verfügt.</span><span class="sxs-lookup"><span data-stu-id="f14e7-142">The user can copy or print the message even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="f14e7-143">Wenn der Benutzer jedoch versucht, eine Aktion abzuschließen, für die der Office 365-e-Mail-Server erforderlich ist, beispielsweise das Weiterleiten der Nachricht, wird die Aktion vom Server nicht zugelassen, wenn der Benutzer ursprünglich nicht über das Recht zum Verwenden des Benutzers verfügt.</span><span class="sxs-lookup"><span data-stu-id="f14e7-143">However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span> <span data-ttu-id="f14e7-144">Endbenutzer können jedoch die Verwendungseinschränkung "nicht weiterleiten" umgehen, indem Sie die Nachricht von einem anderen Konto innerhalb der IOS-Mail-App weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="f14e7-144">However, end users can work around "Do Not Forward" usage restriction by forwarding the message from a different account within the iOS mail app.</span></span> <span data-ttu-id="f14e7-145">Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von e-Mails einrichten, können Anlagen für verschlüsselte und Rechte geschützte Nachrichten nicht in der IOS-Mail-App angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-145">Regardless of whether you set up service-side decryption of mail, attachments to encrypted and rights protected mail can't be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="f14e7-146">Wenn Sie nicht zulassen, dass entschlüsselte Nachrichten an Benutzer von IOS-Mail-apps gesendet werden, erhalten Benutzer eine Nachricht, die besagt, dass Sie nicht über die Berechtigung zum Anzeigen der Nachricht verfügen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-146">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message.</span></span> <span data-ttu-id="f14e7-147">Standardmäßig ist die dienstseitige Entschlüsselung von e-Mail-Nachrichten nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f14e7-147">By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="f14e7-148">Weitere Informationen und eine Übersicht über die Clientumgebung finden Sie unter Anzeigen von [verschlüsselten Nachrichten auf Ihrem iPhone oder iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span><span class="sxs-lookup"><span data-stu-id="f14e7-148">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="f14e7-149">So verwalten Sie, ob Benutzer von IOS-Mail-apps Nachrichten anzeigen können, die durch Office 365 Nachrichtenverschlüsselung geschützt sind</span><span class="sxs-lookup"><span data-stu-id="f14e7-149">To manage whether iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="f14e7-150">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="f14e7-150">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f14e7-151">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f14e7-151">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f14e7-152">Führen Sie das Cmdlet "ActiveSyncOrganizations" mit dem Parameter "AllowRMSSupportForUnenlightenedApps" aus:</span><span class="sxs-lookup"><span data-stu-id="f14e7-152">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="f14e7-153">Beispielsweise zum Konfigurieren des Diensts zum Entschlüsseln von Nachrichten, bevor Sie an nicht aufgeklärte apps wie die IOS-Mail-App gesendet werden:</span><span class="sxs-lookup"><span data-stu-id="f14e7-153">For example, to configure the service to decrypt messages before they're sent to unenlightened apps like the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="f14e7-154">Oder, um den Dienst so zu konfigurieren, dass entschlüsselte Nachrichten nicht an nicht aufgeklärte apps gesendet werden:</span><span class="sxs-lookup"><span data-stu-id="f14e7-154">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

> [!NOTE]
> <span data-ttu-id="f14e7-155">Einzelne Postfachrichtlinien (OWA/ActiveSync) setzen diese Einstellungen außer Kraft (d. h., wenn-den IRMEnabled in der jeweiligen OWA-Postfachrichtlinie oder in der ActiveSync-Postfachrichtlinie auf false festgelegt ist, werden diese Konfigurationen nicht angewendet).</span><span class="sxs-lookup"><span data-stu-id="f14e7-155">Individual mailbox policies (OWA/ActiveSync) override these settings (i.e. if -IRMEnabled is set to False within the respective OWA Mailbox policy, or ActiveSync Mailbox policy, then these configurations would not apply).</span></span>

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="f14e7-156">Aktivieren der dienstseitigen Entschlüsselung von e-Mail-Anlagen für Webbrowser-e-Mail-Clients</span><span class="sxs-lookup"><span data-stu-id="f14e7-156">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="f14e7-157">Normalerweise werden Anlagen automatisch verschlüsselt, wenn Sie Office 365 Nachrichtenverschlüsselung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-157">Normally, when you use Office 365 message encryption, attachments are automatically encrypted.</span></span> <span data-ttu-id="f14e7-158">Als Office 365 Administrator können Sie die dienstseitige Entschlüsselung für e-Mail-Anlagen anwenden, die von Benutzern aus einem Webbrowser heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-158">As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="f14e7-159">Wenn Sie die dienstseitige Entschlüsselung verwenden, sendet der Dienst eine entschlüsselte Kopie der Datei an das Gerät.</span><span class="sxs-lookup"><span data-stu-id="f14e7-159">When you use service-side decryption, the service sends a decrypted copy of the file to the device.</span></span> <span data-ttu-id="f14e7-160">Die Nachricht ist weiterhin verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="f14e7-160">The message is still encrypted.</span></span> <span data-ttu-id="f14e7-161">Die e-Mail-Anlage behält auch Informationen zu Nutzungsrechten, obwohl der Browser keine clientseitigen Nutzungsrechte für den Benutzer anwendet.</span><span class="sxs-lookup"><span data-stu-id="f14e7-161">The email attachment also keeps information about usage rights even though the browser doesn't apply client-side usage rights to the user.</span></span> <span data-ttu-id="f14e7-162">Der Benutzer kann die e-Mail-Anlage auch dann kopieren oder ausdrucken, wenn er ursprünglich nicht über die Rechte dazu verfügt.</span><span class="sxs-lookup"><span data-stu-id="f14e7-162">The user can copy or print the email attachment even if they didn't originally have the rights to do so.</span></span> <span data-ttu-id="f14e7-163">Wenn der Benutzer jedoch versucht, eine Aktion abzuschließen, für die der Office 365-e-Mail-Server erforderlich ist, beispielsweise das Weiterleiten der Anlage, wird die Aktion vom Server nicht zugelassen, wenn der Benutzer ursprünglich nicht über das Recht zum Verwenden verfügt.</span><span class="sxs-lookup"><span data-stu-id="f14e7-163">However, if the user tries to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server won't permit the action if the user didn't originally have the usage right to do so.</span></span>
  
<span data-ttu-id="f14e7-164">Unabhängig davon, ob Sie die dienstseitige Entschlüsselung von Anlagen einrichten, können Benutzer keine Anlagen in verschlüsselter und mit rechten geschützter e-Mail in der IOS Mail-App anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-164">Regardless of whether you set up service-side decryption of attachments, users can't view any attachments to encrypted and rights protected mail in the iOS mail app.</span></span>
  
<span data-ttu-id="f14e7-165">Wenn Sie entschlüsselte e-Mail-Anlagen nicht zulassen (Standardeinstellung), erhalten Benutzer eine Meldung, die besagt, dass Sie nicht über die Berechtigung zum Anzeigen der Anlage verfügen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-165">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="f14e7-166">Weitere Informationen dazu, wie Office 365 die Verschlüsselung für e-Mails und e-Mail-Anlagen mit der Option "nur verschlüsseln" implementiert, finden Sie unter [verschlüsseln-only-Option für e-Mails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="f14e7-166">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="f14e7-167">So verwalten Sie, ob e-Mail-Anlagen beim Herunterladen aus einem Webbrowser entschlüsselt werden</span><span class="sxs-lookup"><span data-stu-id="f14e7-167">To manage whether email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="f14e7-168">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="f14e7-168">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f14e7-169">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f14e7-169">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f14e7-170">Führen Sie das Cmdlet "IRMConfiguration" mit dem Parameter "DecryptAttachmentForEncryptOnly" aus:</span><span class="sxs-lookup"><span data-stu-id="f14e7-170">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentForEncryptOnly parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly <$true|$false>
   ```

   <span data-ttu-id="f14e7-171">Um beispielsweise den Dienst so zu konfigurieren, dass e-Mail-Anlagen entschlüsselt werden, wenn ein Benutzer Sie von einem Webbrowser herunterlädt:</span><span class="sxs-lookup"><span data-stu-id="f14e7-171">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
   ```

   <span data-ttu-id="f14e7-172">So konfigurieren Sie den Dienst so, dass verschlüsselte e-Mail-Anlagen beim Herunterladen verlassen werden:</span><span class="sxs-lookup"><span data-stu-id="f14e7-172">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail"></a><span data-ttu-id="f14e7-173">Sicherstellen, dass alle externen Empfänger das OM-Portal zum Lesen verschlüsselter e-Mails verwenden</span><span class="sxs-lookup"><span data-stu-id="f14e7-173">Ensure all external recipients use the OME Portal to read encrypted mail</span></span>

<span data-ttu-id="f14e7-174">Sie können benutzerdefinierte Branding-Vorlagen verwenden, um zu erzwingen, dass Empfänger eine Wrapper-e-Mail erhalten, die Sie dazu leitet, verschlüsselte e-Mails im OM-Portal zu lesen, anstatt Outlook oder Outlook im Web zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-174">You can use custom branding templates to force recipients to receive a wrapper mail that directs them to read encrypted email in the OME Portal instead of using Outlook or Outlook on the web.</span></span> <span data-ttu-id="f14e7-175">Dies empfiehlt sich, wenn Sie mehr Kontrolle über die Verwendung von e-Mails erhalten möchten, die von Empfängern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-175">You might want to do this if you use want greater control over how recipients use the mail they receive.</span></span> <span data-ttu-id="f14e7-176">Wenn beispielsweise externe Empfänger e-Mails im Webportal anzeigen, können Sie ein Ablaufdatum für die e-Mail festlegen, und Sie können die e-Mail widerrufen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-176">For example, if external recipients view email in the web portal, you can set an expiration date for the email, and you can revoke the email.</span></span> <span data-ttu-id="f14e7-177">Diese Features werden nur über das OM-Portal unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f14e7-177">These features are only supported through the OME Portal.</span></span> <span data-ttu-id="f14e7-178">Sie können die Option Verschlüsseln und die Option nicht weiterleiten beim Erstellen der Nachrichtenfluss Regeln verwenden.</span><span class="sxs-lookup"><span data-stu-id="f14e7-178">You can use the Encrypt option and the Do Not Forward option when creating the mail flow rules.</span></span>

### <a name="use-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email"></a><span data-ttu-id="f14e7-179">Verwenden einer benutzerdefinierten Vorlage, um zu erzwingen, dass alle externen Empfänger das OM-Portal und für verschlüsselte e-Mails verwenden</span><span class="sxs-lookup"><span data-stu-id="f14e7-179">Use a custom template to force all external recipients to use the OME Portal and for encrypted email</span></span>

1. <span data-ttu-id="f14e7-180">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, und starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="f14e7-180">Use a work or school account that has global administrator permissions in your Office 365 organization and start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f14e7-181">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f14e7-181">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f14e7-182">Führen Sie das Cmdlet New-TransportRule aus:</span><span class="sxs-lookup"><span data-stu-id="f14e7-182">Run the New-TransportRule cmdlet:</span></span>

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    <span data-ttu-id="f14e7-183">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="f14e7-183">where:</span></span>

   - <span data-ttu-id="f14e7-184">`mail flow rule name`ist der Name, den Sie für die neue Nachrichtenfluss Regel verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="f14e7-184">`mail flow rule name` is the name you want to use for the new mail flow rule.</span></span>

   - <span data-ttu-id="f14e7-185">`option name`ist entweder `Encrypt` oder `Do Not Forward`.</span><span class="sxs-lookup"><span data-stu-id="f14e7-185">`option name` is either `Encrypt` or `Do Not Forward`.</span></span>

   - <span data-ttu-id="f14e7-186">`template name`ist der Name, den Sie beispielsweise `OME Configuration`der benutzerdefinierten Branding-Vorlage gegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f14e7-186">`template name` is the name you gave the custom branding template, for example `OME Configuration`.</span></span>

   <span data-ttu-id="f14e7-187">So verschlüsseln Sie alle externen e-Mails mit der Vorlage "1 Woche Sale" und wenden die Option "nur verschlüsseln" an:</span><span class="sxs-lookup"><span data-stu-id="f14e7-187">To encrypt all external email with the "One week sale" template and apply the Encrypt-Only option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<OME Configuration>"
   ```

   <span data-ttu-id="f14e7-188">So verschlüsseln Sie alle externen e-Mails mit der Vorlage "OM-Konfiguration" und wenden die Option "nicht weiterleiten" an:</span><span class="sxs-lookup"><span data-stu-id="f14e7-188">To encrypt all external email with the "OME Configuration" template and apply the Do Not Forward option:</span></span>

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<OME Configuration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="f14e7-189">Anpassen der Darstellung von e-Mail-Nachrichten und des OM-Portals</span><span class="sxs-lookup"><span data-stu-id="f14e7-189">Customize the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="f14e7-190">Ausführliche Informationen dazu, wie Sie OM für Ihre Organisation anpassen können, finden Sie unter [Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten](add-your-organization-brand-to-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="f14e7-190">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disable-the-new-capabilities-for-ome"></a><span data-ttu-id="f14e7-191">Deaktivieren der neuen Funktionen für OM</span><span class="sxs-lookup"><span data-stu-id="f14e7-191">Disable the new capabilities for OME</span></span>

<span data-ttu-id="f14e7-192">Wir hoffen, dass es nicht dazu kommt, aber wenn Sie dies benötigen, ist die Deaktivierung der neuen Funktionen für OM sehr einfach.</span><span class="sxs-lookup"><span data-stu-id="f14e7-192">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward.</span></span> <span data-ttu-id="f14e7-193">Zunächst müssen Sie alle e-Mail-Flussregeln, die Sie erstellt haben, mit den neuen OM-Funktionen entfernen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-193">First, you'll need to remove any mail flow rules you've created that use the new OME capabilities.</span></span> <span data-ttu-id="f14e7-194">Informationen zum Entfernen von Nachrichtenfluss Regeln finden Sie unter [Manage Mail Flow Rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="f14e7-194">For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx).</span></span> <span data-ttu-id="f14e7-195">Führen Sie dann die folgenden Schritte in Exchange Online PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="f14e7-195">Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="f14e7-196">So deaktivieren Sie die neuen Funktionen für OM</span><span class="sxs-lookup"><span data-stu-id="f14e7-196">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="f14e7-197">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Office 365 Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="f14e7-197">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="f14e7-198">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="f14e7-198">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="f14e7-199">Wenn Sie die Schaltfläche **verschlüsseln** in Outlook im Internet aktiviert haben, deaktivieren Sie Sie, indem Sie das CmdletSet-IRMConfiguration mit dem Parameter SimplifiedClientAccessEnabled ausführen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-199">If you enabled the **Encrypt** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter.</span></span> <span data-ttu-id="f14e7-200">Andernfalls können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="f14e7-200">Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="f14e7-201">Deaktivieren Sie die neuen Funktionen für OM, indem Sie das Cmdlet "IRMConfiguration" ausführen, wobei der Parameter "AzureRMSLicensingEnabled" auf "false" festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="f14e7-201">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
