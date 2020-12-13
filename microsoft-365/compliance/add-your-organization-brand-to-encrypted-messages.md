---
title: Hinzufügen Ihrer Unternehmensmarke zu verschlüsselten Nachrichten
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Erfahren Sie, wie Office 365 globale Administratoren das Branding Ihrer Organisation auf verschlüsselte e-Mail-Nachrichten & Inhalt des Verschlüsselungs Portals anwenden können.
ms.openlocfilehash: 77fd5e08afa1a4d8ae5f6386fa65b88b6ea2be4d
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663232"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="65946-103">Hinzufügen der Marke Ihrer Organisation zu ihren verschlüsselten Nachrichten in Microsoft 365 for Business-Nachrichtenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="65946-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="65946-104">Sie können das Branding Ihres Unternehmens anwenden, um das Aussehen der e-Mail-Nachrichten Ihrer Organisation und des Verschlüsselungs Portals anzupassen.</span><span class="sxs-lookup"><span data-stu-id="65946-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="65946-105">Sie müssen globale Administratorberechtigungen auf Ihr Arbeits-oder Schulkonto anwenden, bevor Sie mit dem ersten Einstieg beginnen können.</span><span class="sxs-lookup"><span data-stu-id="65946-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="65946-106">Nachdem Sie über diese Berechtigungen verfügen, verwenden Sie die Cmdlets Get-OMEConfiguration und Set-OMEConfiguration Windows PowerShell, um diese Teile von verschlüsselten e-Mail-Nachrichten anzupassen:</span><span class="sxs-lookup"><span data-stu-id="65946-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="65946-107">Einführungstext</span><span class="sxs-lookup"><span data-stu-id="65946-107">Introductory text</span></span>

- <span data-ttu-id="65946-108">Disclaimer text</span><span class="sxs-lookup"><span data-stu-id="65946-108">Disclaimer text</span></span>

- <span data-ttu-id="65946-109">URL für die Datenschutzerklärung Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="65946-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="65946-110">Text im OM-Portal</span><span class="sxs-lookup"><span data-stu-id="65946-110">Text in the OME portal</span></span>

- <span data-ttu-id="65946-111">Logo, das in der e-Mail-Nachricht und im OM-Portal angezeigt wird, oder ob ein Logo überhaupt verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="65946-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="65946-112">Hintergrundfarbe in der e-Mail-Nachricht und im OM-Portal</span><span class="sxs-lookup"><span data-stu-id="65946-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="65946-113">Sie können auch jederzeit zum Standardaussehen und -verhalten zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="65946-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="65946-114">Wenn Sie mehr Kontrolle wünschen, verwenden Sie Office 365 erweiterte Nachrichtenverschlüsselung, um mehrere Vorlagen für verschlüsselte e-Mails zu erstellen, die von Ihrer Organisation stammen.</span><span class="sxs-lookup"><span data-stu-id="65946-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="65946-115">Verwenden Sie diese Vorlagen, um Teile der Benutzeroberfläche zu steuern.</span><span class="sxs-lookup"><span data-stu-id="65946-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="65946-116">Geben Sie beispielsweise an, ob Empfänger Google-, Yahoo-und Microsoft-Konten verwenden können, um sich beim Verschlüsselungs Portal anzumelden.</span><span class="sxs-lookup"><span data-stu-id="65946-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="65946-117">Verwenden Sie Vorlagen, um mehrere Anwendungsfälle zu erfüllen, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="65946-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="65946-118">Einzelne Abteilungen wie Finanzen, Vertrieb usw.</span><span class="sxs-lookup"><span data-stu-id="65946-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="65946-119">Verschiedene Produkte</span><span class="sxs-lookup"><span data-stu-id="65946-119">Different products</span></span>

- <span data-ttu-id="65946-120">Unterschiedliche geographische Regionen oder Länder</span><span class="sxs-lookup"><span data-stu-id="65946-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="65946-121">Ob Sie das Widerrufen von e-Mails zulassen möchten</span><span class="sxs-lookup"><span data-stu-id="65946-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="65946-122">Ob e-Mail-Nachrichten, die an externe Empfänger gesendet werden sollen, nach einer festgelegten Anzahl von Tagen ablaufen.</span><span class="sxs-lookup"><span data-stu-id="65946-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="65946-123">Nachdem Sie die Vorlagen erstellt haben, können Sie Sie mithilfe von Exchange-Nachrichtenfluss Regeln auf verschlüsselte e-Mail-Nachrichten anwenden.</span><span class="sxs-lookup"><span data-stu-id="65946-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="65946-124">Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung haben, können Sie jede e-Mail-Nachricht widerrufen, die Sie mit diesen Vorlagen gebrandmarkt haben.</span><span class="sxs-lookup"><span data-stu-id="65946-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="65946-125">Arbeiten mit Branding-Vorlagen für OM</span><span class="sxs-lookup"><span data-stu-id="65946-125">Work with OME branding templates</span></span>

<span data-ttu-id="65946-126">Sie können mehrere Features in einer Branding-Vorlage ändern.</span><span class="sxs-lookup"><span data-stu-id="65946-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="65946-127">Sie können die Standardvorlage ändern, aber nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="65946-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="65946-128">Wenn Sie erweiterte Nachrichtenverschlüsselung haben, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen.</span><span class="sxs-lookup"><span data-stu-id="65946-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="65946-129">Verwenden Sie Windows PowerShell, um gleichzeitig mit einer Branding-Vorlage zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="65946-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="65946-130">[Festlegen-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) -ändern Sie die standardmäßige Branding-Vorlage oder eine benutzerdefinierte Branding-Vorlage, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="65946-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="65946-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -erstellen Sie eine neue Branding-Vorlage, nur erweiterte Nachrichtenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="65946-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="65946-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) – Entfernen einer benutzerdefinierten Branding-Vorlage, nur erweiterte Nachrichtenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="65946-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="65946-133">Die standardmäßige Branding-Vorlage kann nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="65946-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="65946-134">Ändern einer OM-Branding-Vorlage</span><span class="sxs-lookup"><span data-stu-id="65946-134">Modify an OME branding template</span></span>

<span data-ttu-id="65946-135">Verwenden Sie Windows PowerShell, um eine Branding-Vorlage gleichzeitig zu ändern.</span><span class="sxs-lookup"><span data-stu-id="65946-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="65946-136">Wenn Sie erweiterte Nachrichtenverschlüsselung haben, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen.</span><span class="sxs-lookup"><span data-stu-id="65946-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="65946-137">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="65946-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="65946-138">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="65946-138">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="65946-139">Verwenden Sie das Set-OMEConfiguration-Cmdlet wie in "OMEConfiguration" beschrieben, oder verwenden Sie die folgende Grafik und Tabelle, um Anleitungen zu [geben](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="65946-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Anpassbare e-Mail-Teile](../media/ome-template-breakout.png)

|<span data-ttu-id="65946-141">**So passen Sie dieses Verschlüsselungsfeature an**</span><span class="sxs-lookup"><span data-stu-id="65946-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="65946-142">**Verwenden Sie diese Befehle**</span><span class="sxs-lookup"><span data-stu-id="65946-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65946-143">Hintergrundfarbe</span><span class="sxs-lookup"><span data-stu-id="65946-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="65946-144">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="65946-145">Weitere Informationen zu Hintergrundfarben finden Sie im Abschnitt [Hintergrundfarben](#background-color-reference) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="65946-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="65946-146">Logo</span><span class="sxs-lookup"><span data-stu-id="65946-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="65946-147">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="65946-148">Unterstützte Dateiformate: .png, .jpg, .bmp oder .tiff</span><span class="sxs-lookup"><span data-stu-id="65946-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="65946-149">Optimale Größe der Logodatei: weniger als 40 KB</span><span class="sxs-lookup"><span data-stu-id="65946-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="65946-150">Optimale Größe des Logo Bilds: 170 Pixel.</span><span class="sxs-lookup"><span data-stu-id="65946-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="65946-151">Wenn Ihr Bild diese Dimensionen überschreitet, ändert der Dienst Ihr Logo so, dass es im Portal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="65946-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="65946-152">Der Dienst ändert die Grafikdatei selbst nicht.</span><span class="sxs-lookup"><span data-stu-id="65946-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="65946-153">Um optimale Ergebnisse zu erzielen, verwenden Sie die optimale Größe.</span><span class="sxs-lookup"><span data-stu-id="65946-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="65946-154">Text neben dem Namen und der e-Mail-Adresse des Absenders</span><span class="sxs-lookup"><span data-stu-id="65946-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="65946-155">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="65946-156">Text, der auf der Schaltfläche "Nachricht lesen" angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="65946-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="65946-157">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="65946-158">Text, der unter der Schaltfläche "Nachricht lesen" angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="65946-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="65946-159">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="65946-160">URL für den Link zur Datenschutzerklärung</span><span class="sxs-lookup"><span data-stu-id="65946-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="65946-161">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="65946-162">Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält</span><span class="sxs-lookup"><span data-stu-id="65946-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="65946-163">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="65946-164">Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt</span><span class="sxs-lookup"><span data-stu-id="65946-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="65946-165">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="65946-166">So aktivieren oder deaktivieren Sie die Authentifizierung mithilfe eines einmaligen Pass Codes für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="65946-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="65946-167">**Beispiele:**</span><span class="sxs-lookup"><span data-stu-id="65946-167">**Examples:**</span></span> <br/><span data-ttu-id="65946-168">So aktivieren Sie einmalige Kennwörter für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="65946-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="65946-169">So deaktivieren Sie einmalige Kennwörter für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="65946-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="65946-170">So aktivieren oder deaktivieren Sie die Authentifizierung mit Microsoft-, Google-oder Yahoo-Identitäten für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="65946-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="65946-171">**Beispiele:**</span><span class="sxs-lookup"><span data-stu-id="65946-171">**Examples:**</span></span> <br/><span data-ttu-id="65946-172">So aktivieren Sie soziale IDs für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="65946-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="65946-173">So deaktivieren Sie soziale IDs für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="65946-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="65946-174">Erstellen einer OM-Branding-Vorlage (Erweiterte Nachrichtenverschlüsselung)</span><span class="sxs-lookup"><span data-stu-id="65946-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="65946-175">Wenn Sie Office 365 erweiterte Nachrichtenverschlüsselung haben, können Sie mithilfe des Cmdlets [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) benutzerdefinierte Branding-Vorlagen für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="65946-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="65946-176">Nachdem Sie die Vorlage erstellt haben, ändern Sie die Vorlage mithilfe des Set-OMEConfiguration-Cmdlets wie unter [Modify a OM Branding Template](#modify-an-ome-branding-template)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65946-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="65946-177">Sie können mehrere Vorlagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="65946-177">You can create multiple templates.</span></span>

<span data-ttu-id="65946-178">So erstellen Sie eine neue benutzerdefinierte Branding-Vorlage:</span><span class="sxs-lookup"><span data-stu-id="65946-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="65946-179">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="65946-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="65946-180">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="65946-180">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="65946-181">Verwenden Sie das Cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) , um eine neue Vorlage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="65946-181">Use the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="65946-182">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65946-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="65946-183">Zurückgeben der standardmäßigen Branding-Vorlage auf die ursprünglichen Werte</span><span class="sxs-lookup"><span data-stu-id="65946-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="65946-184">Führen Sie die folgenden Schritte aus, um alle Änderungen aus der Standardvorlage, einschließlich Marken Anpassungen usw., zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="65946-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="65946-185">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="65946-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="65946-186">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="65946-186">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="65946-187">Verwenden Sie das Cmdlet " **OMEConfiguration** " wie unter " [festlegen-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)" beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65946-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="65946-188">Wenn Sie die Marken Anpassungen ihrer Organisation aus den DisclaimerText-, EmailText-und Portal Text-Werten entfernen möchten, legen Sie den Wert auf eine leere Zeichenfolge fest `""` .</span><span class="sxs-lookup"><span data-stu-id="65946-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="65946-189">Legen Sie für alle Bild Werte wie Logo den Wert auf fest  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="65946-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="65946-190">In der folgenden Tabelle werden die Standardeinstellungen für die Verschlüsselungs Anpassungsoption beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65946-190">The following table describes the encryption customization option defaults.</span></span>

   <span data-ttu-id="65946-191">**Dieses Feature der Verschlüsselungserfahrung zu Standardtext und -bild zurücksetzen**</span><span class="sxs-lookup"><span data-stu-id="65946-191">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="65946-192">**Verwenden Sie diese Befehle**</span><span class="sxs-lookup"><span data-stu-id="65946-192">**Use these commands**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="65946-193">Standardtext im Lieferumfang von verschlüsselten e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="65946-193">Default text that comes with encrypted email messages</span></span>  <br/> <span data-ttu-id="65946-194">Der Standardtext wird über den Anweisungen zum Betrachten von verschlüsselten Nachrichten angezeigt</span><span class="sxs-lookup"><span data-stu-id="65946-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="65946-195">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="65946-196">Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält</span><span class="sxs-lookup"><span data-stu-id="65946-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="65946-197">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="65946-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="65946-198">Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt</span><span class="sxs-lookup"><span data-stu-id="65946-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="65946-199">**Beispiel Zurücksetzen auf Standard:**</span><span class="sxs-lookup"><span data-stu-id="65946-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="65946-200">Logo</span><span class="sxs-lookup"><span data-stu-id="65946-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="65946-201">**Beispiel Zurücksetzen auf Standard:**</span><span class="sxs-lookup"><span data-stu-id="65946-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="65946-202">Hintergrundfarbe</span><span class="sxs-lookup"><span data-stu-id="65946-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="65946-203">**Beispiel Zurücksetzen auf Standard:**</span><span class="sxs-lookup"><span data-stu-id="65946-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="65946-204">Entfernen einer benutzerdefinierten Branding-Vorlage (Erweiterte Nachrichtenverschlüsselung)</span><span class="sxs-lookup"><span data-stu-id="65946-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="65946-205">Sie können nur Branding-Vorlagen entfernen oder löschen, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="65946-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="65946-206">Sie können die standardmäßige Branding-Vorlage nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="65946-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="65946-207">So entfernen Sie eine benutzerdefinierte Branding-Vorlage:</span><span class="sxs-lookup"><span data-stu-id="65946-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="65946-208">Verwenden Sie ein Arbeits-oder Schulkonto, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, starten Sie eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="65946-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="65946-209">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="65946-209">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="65946-210">Verwenden Sie das Cmdlet **Remove-OMEConfiguration** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="65946-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="65946-211">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65946-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="65946-212">Weitere Informationen finden Sie unter [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span><span class="sxs-lookup"><span data-stu-id="65946-212">For more information, see [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="65946-213">Erstellen einer Exchange-Nachrichtenfluss Regel, die Ihr benutzerdefiniertes Branding auf verschlüsselte e-Mails anwendet</span><span class="sxs-lookup"><span data-stu-id="65946-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="65946-214">Nachdem Sie entweder die Standardvorlage geändert oder neue Branding-Vorlagen erstellt haben, können Sie Exchange-Nachrichtenfluss Regeln erstellen, um Ihr benutzerdefiniertes Branding basierend auf bestimmten Bedingungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="65946-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="65946-215">In den folgenden Szenarien wird eine solche Regel benutzerdefiniertes Branding anwenden:</span><span class="sxs-lookup"><span data-stu-id="65946-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="65946-216">Wenn die e-Mail manuell vom Endbenutzer mit Outlook oder Outlook im Internet verschlüsselt wurde, früher Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="65946-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="65946-217">Wenn die e-Mail von einer Exchange-Nachrichtenfluss Regel oder einer Richtlinie zur Verhinderung von Datenverlusten automatisch verschlüsselt wurde</span><span class="sxs-lookup"><span data-stu-id="65946-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="65946-218">Informationen zum Erstellen einer Exchange-Nachrichtenfluss Regel, die Verschlüsselung zutrifft, finden Sie unter [define Mail Flow Rules to encrypt Email Messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="65946-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="65946-219">Melden Sie sich in einem Webbrowser mit einem Arbeits-oder Schulkonto, dem globale Administratorberechtigungen erteilt wurden, bei [Office 365 an](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span><span class="sxs-lookup"><span data-stu-id="65946-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="65946-220">Wählen Sie die Kachel **Admin** aus.</span><span class="sxs-lookup"><span data-stu-id="65946-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="65946-221">Wählen Sie im Microsoft 365 Admin Center **Admin** Center \> **Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="65946-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="65946-222">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** , und wählen Sie **Neues** ![ Neues Symbol neue ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="65946-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="65946-223">Weitere Informationen zur Verwendung der Exchange-Verwaltungskonsole finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="65946-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="65946-224">Geben Sie unter **Name** einen Namen für die Regel ein, beispielsweise Branding für die Vertriebsabteilung.</span><span class="sxs-lookup"><span data-stu-id="65946-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="65946-225">Wählen Sie unter **diese Regel anwenden, wenn** aus der Liste der verfügbaren Bedingungen die Bedingung aus, in der sich **der Absender innerhalb der Organisation befindet** , und andere Bedingungen aus.</span><span class="sxs-lookup"><span data-stu-id="65946-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="65946-226">Beispielsweise können Sie eine bestimmte Branding-Vorlage auf Folgendes anwenden:</span><span class="sxs-lookup"><span data-stu-id="65946-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="65946-227">Alle verschlüsselten e-Mails, die von Mitgliedern der Finanzabteilung gesendet wurden</span><span class="sxs-lookup"><span data-stu-id="65946-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="65946-228">Verschlüsselte e-Mails, die mit einem bestimmten Schlüsselwort wie "extern" oder "Partner" gesendet werden</span><span class="sxs-lookup"><span data-stu-id="65946-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="65946-229">Verschlüsselte e-Mails, die an eine bestimmte Domäne gesendet werden</span><span class="sxs-lookup"><span data-stu-id="65946-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="65946-230">Wählen Sie unter **gehen Sie wie folgt** vor die Option **Nachrichtensicherheit** \> **anwenden benutzerdefiniertes Branding auf OM-Nachrichten** ändern aus.</span><span class="sxs-lookup"><span data-stu-id="65946-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="65946-231">Wählen Sie dann in der Dropdownliste eine Branding-Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="65946-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="65946-232">Optional Sie können die Nachrichtenfluss Regel so konfigurieren, dass Verschlüsselung und benutzerdefiniertes Branding angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="65946-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="65946-233">Wählen Sie unter **Folgendes ausführen die** Option **Nachrichtensicherheit ändern** aus, und wählen Sie dann **Office 365 Nachrichtenverschlüsselung und Rechte Schutz anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="65946-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="65946-234">Wählen Sie in der Liste eine RMS-Vorlage aus, wählen Sie **Speichern** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="65946-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="65946-235">Die Liste der Vorlagen enthält Standardvorlagen und-Optionen sowie benutzerdefinierte Vorlagen, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="65946-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="65946-236">Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365 Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="65946-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="65946-237">Anweisungen finden Sie unter [Einrichten neuer Office 365 Nachrichten Verschlüsselungsfunktionen](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="65946-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="65946-238">Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="65946-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="65946-239">Informationen zur Option " **nicht weiterleiten** " finden Sie unter [do not Forward Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span><span class="sxs-lookup"><span data-stu-id="65946-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="65946-240">Informationen zur Option **nur verschlüsseln** finden Sie unter [verschlüsseln nur Option for Emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span><span class="sxs-lookup"><span data-stu-id="65946-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="65946-241">Wählen Sie **Aktion hinzufügen** aus, wenn Sie eine andere Aktion angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="65946-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="65946-242">Hintergrund Farbreferenz</span><span class="sxs-lookup"><span data-stu-id="65946-242">Background color reference</span></span>

<span data-ttu-id="65946-243">Die Farb Namen, die Sie für die Hintergrundfarbe verwenden können, sind limitiert.</span><span class="sxs-lookup"><span data-stu-id="65946-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="65946-244">Anstelle eines Farbnamens können Sie einen Hex-Codewert (#RRGGBB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="65946-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="65946-245">Sie können einen Hex-Codewert verwenden, der einem Farb Namen entspricht, oder einen benutzerdefinierten HEX-Codewert verwenden.</span><span class="sxs-lookup"><span data-stu-id="65946-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="65946-246">Achten Sie darauf, den Hex-Codewert in Anführungszeichen (beispielsweise) einzuschließen `"#f0f8ff"` .</span><span class="sxs-lookup"><span data-stu-id="65946-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="65946-247">In der folgenden Tabelle werden die verfügbaren Namen der Hintergrundfarbe und die zugehörigen Hex-Codewerte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="65946-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|||
|---|---|
|<span data-ttu-id="65946-248">**Farbname**</span><span class="sxs-lookup"><span data-stu-id="65946-248">**Color name**</span></span>|<span data-ttu-id="65946-249">**Farb Code**</span><span class="sxs-lookup"><span data-stu-id="65946-249">**Color code**</span></span>|
|`aliceblue`|<span data-ttu-id="65946-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="65946-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="65946-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="65946-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="65946-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="65946-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="65946-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="65946-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="65946-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="65946-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="65946-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="65946-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="65946-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="65946-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="65946-257">#000000</span><span class="sxs-lookup"><span data-stu-id="65946-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="65946-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="65946-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="65946-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="65946-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="65946-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="65946-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="65946-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="65946-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="65946-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="65946-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="65946-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="65946-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="65946-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="65946-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="65946-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="65946-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="65946-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="65946-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="65946-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="65946-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="65946-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="65946-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="65946-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="65946-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="65946-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="65946-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="65946-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="65946-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="65946-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="65946-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="65946-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="65946-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="65946-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="65946-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="65946-275">#006400</span><span class="sxs-lookup"><span data-stu-id="65946-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="65946-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="65946-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="65946-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="65946-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="65946-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="65946-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="65946-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="65946-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="65946-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="65946-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="65946-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="65946-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="65946-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="65946-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="65946-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="65946-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="65946-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="65946-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="65946-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="65946-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="65946-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="65946-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="65946-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="65946-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="65946-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="65946-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="65946-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="65946-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="65946-290">#696969</span><span class="sxs-lookup"><span data-stu-id="65946-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="65946-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="65946-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="65946-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="65946-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="65946-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="65946-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="65946-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="65946-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="65946-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="65946-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="65946-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="65946-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="65946-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="65946-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="65946-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="65946-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="65946-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="65946-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="65946-300">#808080</span><span class="sxs-lookup"><span data-stu-id="65946-300">#808080</span></span>|
|`green`|<span data-ttu-id="65946-301">#008000</span><span class="sxs-lookup"><span data-stu-id="65946-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="65946-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="65946-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="65946-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="65946-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="65946-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="65946-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="65946-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="65946-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="65946-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="65946-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="65946-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="65946-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="65946-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="65946-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="65946-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="65946-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="65946-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="65946-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="65946-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="65946-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="65946-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="65946-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="65946-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="65946-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="65946-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="65946-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="65946-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="65946-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="65946-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="65946-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="65946-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="65946-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="65946-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="65946-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="65946-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="65946-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="65946-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="65946-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="65946-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="65946-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="65946-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="65946-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="65946-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="65946-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="65946-324">#778899</span><span class="sxs-lookup"><span data-stu-id="65946-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="65946-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="65946-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="65946-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="65946-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="65946-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="65946-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="65946-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="65946-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="65946-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="65946-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="65946-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="65946-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="65946-331">#800000</span><span class="sxs-lookup"><span data-stu-id="65946-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="65946-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="65946-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="65946-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="65946-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="65946-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="65946-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="65946-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="65946-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="65946-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="65946-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="65946-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="65946-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="65946-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="65946-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="65946-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="65946-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="65946-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="65946-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="65946-341">#191970</span><span class="sxs-lookup"><span data-stu-id="65946-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="65946-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="65946-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="65946-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="65946-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="65946-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="65946-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="65946-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="65946-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="65946-346">#000080</span><span class="sxs-lookup"><span data-stu-id="65946-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="65946-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="65946-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="65946-348">#808000</span><span class="sxs-lookup"><span data-stu-id="65946-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="65946-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="65946-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="65946-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="65946-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="65946-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="65946-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="65946-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="65946-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="65946-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="65946-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="65946-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="65946-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="65946-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="65946-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="65946-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="65946-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="65946-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="65946-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="65946-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="65946-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="65946-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="65946-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="65946-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="65946-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="65946-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="65946-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="65946-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="65946-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="65946-363">#800080</span><span class="sxs-lookup"><span data-stu-id="65946-363">#800080</span></span>|
|`red`|<span data-ttu-id="65946-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="65946-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="65946-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="65946-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="65946-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="65946-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="65946-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="65946-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="65946-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="65946-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="65946-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="65946-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="65946-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="65946-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="65946-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="65946-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="65946-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="65946-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="65946-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="65946-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="65946-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="65946-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="65946-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="65946-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="65946-376">#708090</span><span class="sxs-lookup"><span data-stu-id="65946-376">#708090</span></span>|
|`snow`|<span data-ttu-id="65946-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="65946-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="65946-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="65946-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="65946-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="65946-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="65946-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="65946-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="65946-381">#008080</span><span class="sxs-lookup"><span data-stu-id="65946-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="65946-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="65946-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="65946-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="65946-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="65946-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="65946-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="65946-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="65946-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="65946-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="65946-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="65946-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="65946-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="65946-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="65946-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="65946-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="65946-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="65946-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="65946-390">#9acd32</span></span>|
