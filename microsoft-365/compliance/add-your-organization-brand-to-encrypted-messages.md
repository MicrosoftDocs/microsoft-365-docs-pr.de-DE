---
title: Hinzufügen ihrer Unternehmensmarke zu Ihren verschlüsselten Nachrichten
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
description: Erfahren Sie, wie Office 365 globalen Administratoren das Branding Ihrer Organisation auf verschlüsselte E-Mail-Nachrichten & Inhalte des Verschlüsselungsportals anwenden können.
ms.openlocfilehash: 95320e9f268f19cedd993efe4fa0e68fd75af125
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430732"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="b33d1-103">Hinzufügen der Marke Ihrer Organisation zu Ihren Microsoft 365 für verschlüsselte Nachrichtenverschlüsselung für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="b33d1-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="b33d1-104">Sie können Ihr Unternehmensbranding anwenden, um das Erscheinungsbild der E-Mail-Nachrichten Ihrer Organisation und des Verschlüsselungsportals anzupassen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="b33d1-105">Sie müssen globale Administratorberechtigungen auf Ihr Geschäfts-, Schul- oder Unikonto anwenden, bevor Sie loslegen können.</span><span class="sxs-lookup"><span data-stu-id="b33d1-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="b33d1-106">Sobald Sie über diese Berechtigungen verfügen, verwenden Sie die Cmdlets Get-OMEConfiguration und Set-OMEConfiguration Windows PowerShell, um diese Teile verschlüsselter E-Mail-Nachrichten anzupassen:</span><span class="sxs-lookup"><span data-stu-id="b33d1-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="b33d1-107">Einführungstext</span><span class="sxs-lookup"><span data-stu-id="b33d1-107">Introductory text</span></span>

- <span data-ttu-id="b33d1-108">Disclaimer text</span><span class="sxs-lookup"><span data-stu-id="b33d1-108">Disclaimer text</span></span>

- <span data-ttu-id="b33d1-109">URL für die Datenschutzbestimmungen Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="b33d1-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="b33d1-110">Text im OME-Portal</span><span class="sxs-lookup"><span data-stu-id="b33d1-110">Text in the OME portal</span></span>

- <span data-ttu-id="b33d1-111">Logo, das in der E-Mail-Nachricht und im OME-Portal angezeigt wird oder ob überhaupt ein Logo verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="b33d1-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="b33d1-112">Hintergrundfarbe im E-Mail-Nachrichten- und OME-Portal</span><span class="sxs-lookup"><span data-stu-id="b33d1-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="b33d1-113">Sie können auch jederzeit zum Standardaussehen und -verhalten zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="b33d1-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="b33d1-114">Wenn Sie mehr Kontrolle wünschen, verwenden Sie Office 365 Advanced Message Encryption, um mehrere Vorlagen für verschlüsselte E-Mails aus Ihrer Organisation zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="b33d1-115">Verwenden Sie diese Vorlagen, um Teile der Endbenutzerumgebung zu steuern.</span><span class="sxs-lookup"><span data-stu-id="b33d1-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="b33d1-116">Geben Sie beispielsweise an, ob Empfänger Google-, Yahoo- und Microsoft-Konten verwenden können, um sich beim Verschlüsselungsportal anzumelden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="b33d1-117">Verwenden Sie Vorlagen, um mehrere Anwendungsfälle zu erfüllen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="b33d1-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="b33d1-118">Einzelne Abteilungen, z. B. Finanzen, Vertrieb usw.</span><span class="sxs-lookup"><span data-stu-id="b33d1-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="b33d1-119">Verschiedene Produkte</span><span class="sxs-lookup"><span data-stu-id="b33d1-119">Different products</span></span>

- <span data-ttu-id="b33d1-120">Unterschiedliche geografische Regionen oder Länder</span><span class="sxs-lookup"><span data-stu-id="b33d1-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="b33d1-121">Gibt an, ob Sie zulassen möchten, dass E-Mails widerrufen werden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="b33d1-122">Gibt an, ob E-Mails, die an externe Empfänger gesendet werden, nach einer bestimmten Anzahl von Tagen ablaufen sollen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="b33d1-123">Nachdem Sie die Vorlagen erstellt haben, können Sie sie mithilfe Exchange Nachrichtenflussregeln auf verschlüsselte E-Mails anwenden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="b33d1-124">Wenn Sie über Office 365 Advanced Message Encryption verfügen, können Sie mithilfe dieser Vorlagen alle E-Mails widerrufen, die Sie mit einem Branding versehen haben.</span><span class="sxs-lookup"><span data-stu-id="b33d1-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="b33d1-125">Arbeiten mit OME-Brandingvorlagen</span><span class="sxs-lookup"><span data-stu-id="b33d1-125">Work with OME branding templates</span></span>

<span data-ttu-id="b33d1-126">Sie können mehrere Features in einer Brandingvorlage ändern.</span><span class="sxs-lookup"><span data-stu-id="b33d1-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="b33d1-127">Sie können die Standardvorlage ändern, aber nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="b33d1-128">Wenn Sie über die erweiterte Nachrichtenverschlüsselung verfügen, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="b33d1-129">Verwenden Sie Windows PowerShell, um jeweils mit einer Brandingvorlage zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="b33d1-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="b33d1-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) – Ändern der standardmäßigen Brandingvorlage oder einer benutzerdefinierten Brandingvorlage, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b33d1-130">[Set-OMEConfiguration](/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="b33d1-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) – Erstellen Sie eine neue Brandingvorlage, nur erweiterte Nachrichtenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="b33d1-131">[New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="b33d1-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) – Entfernen Sie eine benutzerdefinierte Brandingvorlage, nur erweiterte Nachrichtenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="b33d1-132">[Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="b33d1-133">Sie können die Standardbrandingvorlage nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="b33d1-134">Ändern einer OME-Brandingvorlage</span><span class="sxs-lookup"><span data-stu-id="b33d1-134">Modify an OME branding template</span></span>

<span data-ttu-id="b33d1-135">Verwenden Sie Windows PowerShell, um jeweils eine Brandingvorlage zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b33d1-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="b33d1-136">Wenn Sie über die erweiterte Nachrichtenverschlüsselung verfügen, können Sie auch benutzerdefinierte Vorlagen erstellen, ändern und entfernen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="b33d1-137">Starten Sie mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="b33d1-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b33d1-138">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b33d1-138">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b33d1-139">Verwenden Sie das Cmdlet Set-OMEConfiguration, wie in ["Set-OMEConfiguration"](/powershell/module/exchange/Set-OMEConfiguration) beschrieben, oder verwenden Sie die folgende Grafik und Tabelle als Anleitung.</span><span class="sxs-lookup"><span data-stu-id="b33d1-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Anpassbare E-Mail-Komponenten](../media/ome-template-breakout.png)

|<span data-ttu-id="b33d1-141">**So passen Sie dieses Verschlüsselungsfeature an**</span><span class="sxs-lookup"><span data-stu-id="b33d1-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="b33d1-142">**Verwenden Sie diese Befehle**</span><span class="sxs-lookup"><span data-stu-id="b33d1-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b33d1-143">Hintergrundfarbe</span><span class="sxs-lookup"><span data-stu-id="b33d1-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="b33d1-144">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="b33d1-145">Weitere Informationen zu Hintergrundfarben finden Sie im Abschnitt ["Hintergrundfarben"](#background-color-reference) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="b33d1-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="b33d1-146">Logo</span><span class="sxs-lookup"><span data-stu-id="b33d1-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="b33d1-147">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="b33d1-148">Unterstützte Dateiformate: .png, .jpg, .bmp oder .tiff</span><span class="sxs-lookup"><span data-stu-id="b33d1-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="b33d1-149">Optimale Größe der Logodatei: weniger als 40 KB</span><span class="sxs-lookup"><span data-stu-id="b33d1-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="b33d1-150">Optimale Größe des Logobilds: 170 x 70 Pixel.</span><span class="sxs-lookup"><span data-stu-id="b33d1-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="b33d1-151">Wenn Ihr Bild diese Dimensionen überschreitet, ändert der Dienst die Größe Ihres Logos für die Anzeige im Portal.</span><span class="sxs-lookup"><span data-stu-id="b33d1-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="b33d1-152">Der Dienst ändert die Grafikdatei selbst nicht.</span><span class="sxs-lookup"><span data-stu-id="b33d1-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="b33d1-153">Um optimale Ergebnisse zu erzielen, verwenden Sie die optimale Größe.</span><span class="sxs-lookup"><span data-stu-id="b33d1-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="b33d1-154">Text neben dem Namen und der E-Mail-Adresse des Absenders</span><span class="sxs-lookup"><span data-stu-id="b33d1-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b33d1-155">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="b33d1-156">Text, der auf der Schaltfläche "Nachricht lesen" angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="b33d1-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b33d1-157">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="b33d1-158">Text, der unter der Schaltfläche "Nachricht lesen" angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="b33d1-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="b33d1-159">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="b33d1-160">URL für den Link "Datenschutzbestimmungen"</span><span class="sxs-lookup"><span data-stu-id="b33d1-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="b33d1-161">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="b33d1-162">Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält</span><span class="sxs-lookup"><span data-stu-id="b33d1-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="b33d1-163">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="b33d1-164">Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt</span><span class="sxs-lookup"><span data-stu-id="b33d1-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="b33d1-165">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="b33d1-166">So aktivieren oder deaktivieren Sie die Authentifizierung mit einem einmaligen Passcode für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="b33d1-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="b33d1-167">**Beispiele:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-167">**Examples:**</span></span> <br/><span data-ttu-id="b33d1-168">So aktivieren Sie einmalige Passcodes für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="b33d1-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="b33d1-169">So deaktivieren Sie einmalige Passcodes für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="b33d1-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="b33d1-170">So aktivieren oder deaktivieren Sie die Authentifizierung mit Microsoft-, Google- oder Yahoo-Identitäten für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="b33d1-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="b33d1-171">**Beispiele:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-171">**Examples:**</span></span> <br/><span data-ttu-id="b33d1-172">So aktivieren Sie IDs für soziale Netzwerke für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="b33d1-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="b33d1-173">So deaktivieren Sie IDs für soziale Netzwerke für diese benutzerdefinierte Vorlage</span><span class="sxs-lookup"><span data-stu-id="b33d1-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="b33d1-174">Erstellen einer OME-Brandingvorlage (Erweiterte Nachrichtenverschlüsselung)</span><span class="sxs-lookup"><span data-stu-id="b33d1-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="b33d1-175">Wenn Sie über Office 365 Advanced Message Encryption verfügen, können Sie benutzerdefinierte Brandingvorlagen für Ihre Organisation mithilfe des [Cmdlets "New-OMEConfiguration"](/powershell/module/exchange/new-omeconfiguration) erstellen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="b33d1-176">Nachdem Sie die Vorlage erstellt haben, ändern Sie die Vorlage mithilfe des Cmdlets Set-OMEConfiguration, wie unter [Ändern einer OME-Brandingvorlage](#modify-an-ome-branding-template)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b33d1-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="b33d1-177">Sie können mehrere Vorlagen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-177">You can create multiple templates.</span></span>

<span data-ttu-id="b33d1-178">So erstellen Sie eine neue benutzerdefinierte Brandingvorlage:</span><span class="sxs-lookup"><span data-stu-id="b33d1-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="b33d1-179">Starten Sie mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="b33d1-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b33d1-180">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b33d1-180">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b33d1-181">Verwenden Sie das Cmdlet ["New-OMEConfiguration",](/powershell/module/exchange/new-omeconfiguration) um eine neue Vorlage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-181">Use the [New-OMEConfiguration](/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="b33d1-182">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b33d1-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="b33d1-183">Zurückgeben der Standardbrandingvorlage an die ursprünglichen Werte</span><span class="sxs-lookup"><span data-stu-id="b33d1-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="b33d1-184">Führen Sie die folgenden Schritte aus, um alle Änderungen aus der Standardvorlage zu entfernen, einschließlich Markenanpassungen usw.:</span><span class="sxs-lookup"><span data-stu-id="b33d1-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="b33d1-185">Starten Sie mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="b33d1-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b33d1-186">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b33d1-186">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b33d1-187">Verwenden Sie das Cmdlet **"Set-OMEConfiguration",** wie in ["Set-OMEConfiguration"](/powershell/module/exchange/Set-OMEConfiguration)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b33d1-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="b33d1-188">Um die Brandinganpassungen Ihrer Organisation aus den Werten "DisclaimerText", "EmailText" und "PortalText" zu entfernen, legen Sie den Wert auf eine leere Zeichenfolge `""` fest.</span><span class="sxs-lookup"><span data-stu-id="b33d1-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="b33d1-189">Legen Sie für alle Bildwerte, z. B. Logo, den Wert auf  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="b33d1-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="b33d1-190">In der folgenden Tabelle werden die Standardeinstellungen für die Verschlüsselungsanpassung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b33d1-190">The following table describes the encryption customization option defaults.</span></span>

   |<span data-ttu-id="b33d1-191">Dieses Feature der Verschlüsselungserfahrung zu Standardtext und -bild zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="b33d1-191">To revert this feature of the encryption experience back to the default text and image</span></span>|<span data-ttu-id="b33d1-192">Verwenden Sie diese Befehle</span><span class="sxs-lookup"><span data-stu-id="b33d1-192">Use these commands</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="b33d1-193">Standardtext, der in verschlüsselten E-Mail-Nachrichten enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="b33d1-193">Default text that comes with encrypted email messages.</span></span>  <span data-ttu-id="b33d1-194">Der Standardtext wird über den Anweisungen zum Betrachten von verschlüsselten Nachrichten angezeigt</span><span class="sxs-lookup"><span data-stu-id="b33d1-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="b33d1-195">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="b33d1-196">Haftungsausschluss in der E-Mail, die die verschlüsselte Nachricht enthält</span><span class="sxs-lookup"><span data-stu-id="b33d1-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="b33d1-197">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="b33d1-198">Der Text wird oben im Anzeigeportal für verschlüsselte E-Mails angezeigt</span><span class="sxs-lookup"><span data-stu-id="b33d1-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="b33d1-199">**Beispiel für die zurückgesetzte Standardeinstellung:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="b33d1-200">Logo</span><span class="sxs-lookup"><span data-stu-id="b33d1-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="b33d1-201">**Beispiel für die zurückgesetzte Standardeinstellung:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="b33d1-202">Hintergrundfarbe</span><span class="sxs-lookup"><span data-stu-id="b33d1-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="b33d1-203">**Beispiel für die zurückgesetzte Standardeinstellung:**</span><span class="sxs-lookup"><span data-stu-id="b33d1-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="b33d1-204">Entfernen einer benutzerdefinierten Brandingvorlage (Erweiterte Nachrichtenverschlüsselung)</span><span class="sxs-lookup"><span data-stu-id="b33d1-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="b33d1-205">Brandingvorlagen, die Sie erstellt haben, können nur entfernt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="b33d1-206">Sie können die Standardbrandingvorlage nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="b33d1-207">So entfernen Sie eine benutzerdefinierte Brandingvorlage:</span><span class="sxs-lookup"><span data-stu-id="b33d1-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="b33d1-208">Starten Sie mithilfe eines Geschäfts-, Schul- oder Unikontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Windows PowerShell Sitzung, und stellen Sie eine Verbindung mit Exchange Online her.</span><span class="sxs-lookup"><span data-stu-id="b33d1-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b33d1-209">Anleitungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="b33d1-209">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="b33d1-210">Verwenden Sie das Cmdlet **"Remove-OMEConfiguration"** wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b33d1-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="b33d1-211">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b33d1-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="b33d1-212">Weitere Informationen finden Sie unter [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span><span class="sxs-lookup"><span data-stu-id="b33d1-212">For more information, see [Remove-OMEConfiguration](/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="b33d1-213">Erstellen einer Exchange Nachrichtenflussregel, die Ihr benutzerdefiniertes Branding auf verschlüsselte E-Mails anwendet</span><span class="sxs-lookup"><span data-stu-id="b33d1-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b33d1-214">Drittanbieteranwendungen, die E-Mails scannen und ändern, können verhindern, dass das OME-Branding korrekt angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b33d1-214">Third-party applications that scan and modify mail can prevent OME branding from being applied correctly.</span></span>

<span data-ttu-id="b33d1-215">Nachdem Sie die Standardvorlage geändert oder neue Brandingvorlagen erstellt haben, können Sie Exchange Nachrichtenflussregeln erstellen, um Ihr benutzerdefiniertes Branding basierend auf bestimmten Bedingungen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-215">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="b33d1-216">Eine solche Regel wendet benutzerdefiniertes Branding in den folgenden Szenarien an:</span><span class="sxs-lookup"><span data-stu-id="b33d1-216">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="b33d1-217">Wenn die E-Mail manuell vom Endbenutzer mit Outlook oder Outlook im Web verschlüsselt wurde, früher Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="b33d1-217">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="b33d1-218">Wenn die E-Mail automatisch durch eine Exchange Nachrichtenflussregel oder Richtlinie zur Verhinderung von Datenverlust verschlüsselt wurde</span><span class="sxs-lookup"><span data-stu-id="b33d1-218">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="b33d1-219">Informationen zum Erstellen einer Exchange Nachrichtenflussregel, die Verschlüsselung anwendet, finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten in Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="b33d1-219">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="b33d1-220">Melden Sie sich in einem Webbrowser unter Verwendung eines Geschäfts-, Schul- oder Unikontos, dem globale Administratorberechtigungen gewährt wurden, [bei Office 365 an.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="b33d1-220">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="b33d1-221">Wählen Sie die **Kachel "Administrator"** aus.</span><span class="sxs-lookup"><span data-stu-id="b33d1-221">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="b33d1-222">Wählen Sie im Microsoft 365 Admin Center **Admin Centers** \> **Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="b33d1-222">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="b33d1-223">Wechseln Sie im **Exchange-Verwaltungskonsole** zu \> **Nachrichtenflussregeln,** und wählen Sie **das** Symbol ![ "Neu ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Neu" aus, um eine neue Regel zu erstellen.**</span><span class="sxs-lookup"><span data-stu-id="b33d1-223">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="b33d1-224">Weitere Informationen zur Verwendung des EAC finden Sie im [Exchange Admin Center in Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="b33d1-224">For more information about using the EAC, see [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="b33d1-225">Geben Sie unter **"Name"** einen Namen für die Regel ein, z. B. Branding für die Vertriebsabteilung.</span><span class="sxs-lookup"><span data-stu-id="b33d1-225">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="b33d1-226">Wählen Sie unter **"Diese Regel anwenden, wenn"** die Bedingung **"Der Absender befindet sich innerhalb der Organisation"** und andere gewünschte Bedingungen aus der Liste der verfügbaren Bedingungen aus.</span><span class="sxs-lookup"><span data-stu-id="b33d1-226">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="b33d1-227">Sie können z. B. eine bestimmte Brandingvorlage auf Folgendes anwenden:</span><span class="sxs-lookup"><span data-stu-id="b33d1-227">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="b33d1-228">Alle verschlüsselten E-Mails, die von Mitgliedern der Finanzabteilung gesendet werden</span><span class="sxs-lookup"><span data-stu-id="b33d1-228">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="b33d1-229">Verschlüsselte E-Mails, die mit einem bestimmten Schlüsselwort wie "Extern" oder "Partner" gesendet werden</span><span class="sxs-lookup"><span data-stu-id="b33d1-229">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="b33d1-230">Verschlüsselte E-Mails, die an eine bestimmte Domäne gesendet werden</span><span class="sxs-lookup"><span data-stu-id="b33d1-230">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="b33d1-231">Wählen Sie **unter "Folgendes"** die Option **"Nachrichtensicherheit** \> **anwenden benutzerdefiniertes Branding auf OME-Nachrichten** anwenden" aus.</span><span class="sxs-lookup"><span data-stu-id="b33d1-231">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="b33d1-232">Wählen Sie als Nächstes in der Dropdownliste eine Brandingvorlage aus.</span><span class="sxs-lookup"><span data-stu-id="b33d1-232">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="b33d1-233">(Optional) Sie können die Nachrichtenflussregel so konfigurieren, dass Verschlüsselung und benutzerdefiniertes Branding angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-233">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="b33d1-234">Wählen Sie unter **"Do the following"** die Option **"Nachrichtensicherheit ändern"** und dann **"Anwenden Office 365-Nachrichtenverschlüsselung und Rechteschutz"** aus.</span><span class="sxs-lookup"><span data-stu-id="b33d1-234">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="b33d1-235">Wählen Sie eine RMS-Vorlage aus der Liste aus, klicken Sie auf **"Speichern"** und dann auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="b33d1-235">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="b33d1-236">Die Liste der Vorlagen enthält Standardvorlagen und -optionen sowie alle benutzerdefinierten Vorlagen, die Sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="b33d1-236">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="b33d1-237">Wenn die Liste leer ist, stellen Sie sicher, dass Sie Office 365-Nachrichtenverschlüsselung mit den neuen Funktionen eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="b33d1-237">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="b33d1-238">Anweisungen finden Sie unter [Einrichten neuer Office 365-Nachrichtenverschlüsselung Funktionen.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="b33d1-238">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="b33d1-239">Informationen zu den Standardvorlagen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection.](/information-protection/deploy-use/configure-policy-templates)</span><span class="sxs-lookup"><span data-stu-id="b33d1-239">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="b33d1-240">Informationen zur Option **"Nicht weiterleiten"** finden Sie unter ["Nicht weiterleiten"-Option für E-Mails.](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="b33d1-240">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="b33d1-241">Informationen zur Option **"Nur verschlüsseln"** finden Sie unter ["Nur verschlüsseln" für E-Mails.](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="b33d1-241">For information about the **encrypt only** option, see [Encrypt Only option for emails](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="b33d1-242">Wählen Sie **"Aktion hinzufügen"** aus, wenn Sie eine andere Aktion angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="b33d1-242">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="b33d1-243">Hintergrundfarbreferenz</span><span class="sxs-lookup"><span data-stu-id="b33d1-243">Background color reference</span></span>

<span data-ttu-id="b33d1-244">Die Farbnamen, die Sie für die Hintergrundfarbe verwenden können, sind begrenzt.</span><span class="sxs-lookup"><span data-stu-id="b33d1-244">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="b33d1-245">Anstelle eines Farbnamens können Sie einen Hexadezimalcodewert (#RRGGBB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-245">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="b33d1-246">Sie können einen Hexadezimalcodewert verwenden, der einem Farbnamen entspricht, oder sie können einen benutzerdefinierten Hexadezimalcodewert verwenden.</span><span class="sxs-lookup"><span data-stu-id="b33d1-246">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="b33d1-247">Achten Sie darauf, den Hexadezimalcodewert in Anführungszeichen (z. B. ) einzuschließen. `"#f0f8ff"`</span><span class="sxs-lookup"><span data-stu-id="b33d1-247">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="b33d1-248">Die verfügbaren Hintergrundfarbennamen und die entsprechenden Hexadezimalcodewerte werden in der folgenden Tabelle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b33d1-248">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="b33d1-249">**Farbname**</span><span class="sxs-lookup"><span data-stu-id="b33d1-249">**Color name**</span></span>|<span data-ttu-id="b33d1-250">**Farbcode**</span><span class="sxs-lookup"><span data-stu-id="b33d1-250">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="b33d1-251">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="b33d1-251">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="b33d1-252">#faebd7</span><span class="sxs-lookup"><span data-stu-id="b33d1-252">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="b33d1-253">#00ffff</span><span class="sxs-lookup"><span data-stu-id="b33d1-253">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="b33d1-254">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="b33d1-254">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="b33d1-255">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="b33d1-255">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="b33d1-256">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="b33d1-256">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="b33d1-257">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="b33d1-257">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="b33d1-258">#000000</span><span class="sxs-lookup"><span data-stu-id="b33d1-258">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="b33d1-259">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="b33d1-259">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="b33d1-260">#0000ff</span><span class="sxs-lookup"><span data-stu-id="b33d1-260">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="b33d1-261">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="b33d1-261">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="b33d1-262">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="b33d1-262">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="b33d1-263">#deb887</span><span class="sxs-lookup"><span data-stu-id="b33d1-263">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="b33d1-264">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="b33d1-264">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="b33d1-265">#7fff00</span><span class="sxs-lookup"><span data-stu-id="b33d1-265">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="b33d1-266">#d2691e</span><span class="sxs-lookup"><span data-stu-id="b33d1-266">#d2691e</span></span>|
|`coral`|<span data-ttu-id="b33d1-267">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="b33d1-267">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="b33d1-268">#6495ed</span><span class="sxs-lookup"><span data-stu-id="b33d1-268">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="b33d1-269">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="b33d1-269">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="b33d1-270">#dc143c</span><span class="sxs-lookup"><span data-stu-id="b33d1-270">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="b33d1-271">#00ffff</span><span class="sxs-lookup"><span data-stu-id="b33d1-271">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="b33d1-272">#00008b</span><span class="sxs-lookup"><span data-stu-id="b33d1-272">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="b33d1-273">#008b8b</span><span class="sxs-lookup"><span data-stu-id="b33d1-273">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="b33d1-274">#b8860b</span><span class="sxs-lookup"><span data-stu-id="b33d1-274">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="b33d1-275">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="b33d1-275">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="b33d1-276">#006400</span><span class="sxs-lookup"><span data-stu-id="b33d1-276">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="b33d1-277">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="b33d1-277">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="b33d1-278">#8b008b</span><span class="sxs-lookup"><span data-stu-id="b33d1-278">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="b33d1-279">#556b2f</span><span class="sxs-lookup"><span data-stu-id="b33d1-279">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="b33d1-280">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="b33d1-280">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="b33d1-281">#9932cc</span><span class="sxs-lookup"><span data-stu-id="b33d1-281">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="b33d1-282">#8b0000</span><span class="sxs-lookup"><span data-stu-id="b33d1-282">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="b33d1-283">#e9967a</span><span class="sxs-lookup"><span data-stu-id="b33d1-283">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="b33d1-284">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="b33d1-284">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="b33d1-285">#483d8b</span><span class="sxs-lookup"><span data-stu-id="b33d1-285">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="b33d1-286">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="b33d1-286">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="b33d1-287">#00ced1</span><span class="sxs-lookup"><span data-stu-id="b33d1-287">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="b33d1-288">#9400d3</span><span class="sxs-lookup"><span data-stu-id="b33d1-288">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="b33d1-289">#ff1493</span><span class="sxs-lookup"><span data-stu-id="b33d1-289">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="b33d1-290">#00bfff</span><span class="sxs-lookup"><span data-stu-id="b33d1-290">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="b33d1-291">#696969</span><span class="sxs-lookup"><span data-stu-id="b33d1-291">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="b33d1-292">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="b33d1-292">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="b33d1-293">#b22222</span><span class="sxs-lookup"><span data-stu-id="b33d1-293">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="b33d1-294">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="b33d1-294">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="b33d1-295">#228b22</span><span class="sxs-lookup"><span data-stu-id="b33d1-295">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="b33d1-296">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="b33d1-296">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="b33d1-297">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="b33d1-297">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="b33d1-298">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="b33d1-298">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="b33d1-299">#ffd700</span><span class="sxs-lookup"><span data-stu-id="b33d1-299">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="b33d1-300">#daa520</span><span class="sxs-lookup"><span data-stu-id="b33d1-300">#daa520</span></span>|
|`gray`|<span data-ttu-id="b33d1-301">#808080</span><span class="sxs-lookup"><span data-stu-id="b33d1-301">#808080</span></span>|
|`green`|<span data-ttu-id="b33d1-302">#008000</span><span class="sxs-lookup"><span data-stu-id="b33d1-302">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="b33d1-303">#adff2f</span><span class="sxs-lookup"><span data-stu-id="b33d1-303">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="b33d1-304">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="b33d1-304">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="b33d1-305">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="b33d1-305">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="b33d1-306">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="b33d1-306">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="b33d1-307">#4b0082</span><span class="sxs-lookup"><span data-stu-id="b33d1-307">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="b33d1-308">#fffff0</span><span class="sxs-lookup"><span data-stu-id="b33d1-308">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="b33d1-309">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="b33d1-309">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="b33d1-310">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="b33d1-310">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="b33d1-311">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="b33d1-311">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="b33d1-312">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="b33d1-312">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="b33d1-313">#fffacd</span><span class="sxs-lookup"><span data-stu-id="b33d1-313">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="b33d1-314">#add8e6</span><span class="sxs-lookup"><span data-stu-id="b33d1-314">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="b33d1-315">#f08080</span><span class="sxs-lookup"><span data-stu-id="b33d1-315">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="b33d1-316">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="b33d1-316">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="b33d1-317">#fafad2</span><span class="sxs-lookup"><span data-stu-id="b33d1-317">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="b33d1-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="b33d1-318">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="b33d1-319">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="b33d1-319">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="b33d1-320">#90ee90</span><span class="sxs-lookup"><span data-stu-id="b33d1-320">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="b33d1-321">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="b33d1-321">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="b33d1-322">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="b33d1-322">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="b33d1-323">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="b33d1-323">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="b33d1-324">#87cefa</span><span class="sxs-lookup"><span data-stu-id="b33d1-324">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="b33d1-325">#778899</span><span class="sxs-lookup"><span data-stu-id="b33d1-325">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="b33d1-326">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="b33d1-326">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="b33d1-327">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="b33d1-327">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="b33d1-328">#00ff00</span><span class="sxs-lookup"><span data-stu-id="b33d1-328">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="b33d1-329">#32cd32</span><span class="sxs-lookup"><span data-stu-id="b33d1-329">#32cd32</span></span>|
|`linen`|<span data-ttu-id="b33d1-330">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="b33d1-330">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="b33d1-331">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="b33d1-331">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="b33d1-332">#800000</span><span class="sxs-lookup"><span data-stu-id="b33d1-332">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="b33d1-333">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="b33d1-333">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="b33d1-334">#0000cd</span><span class="sxs-lookup"><span data-stu-id="b33d1-334">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="b33d1-335">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="b33d1-335">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="b33d1-336">#9370db</span><span class="sxs-lookup"><span data-stu-id="b33d1-336">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="b33d1-337">#3cb371</span><span class="sxs-lookup"><span data-stu-id="b33d1-337">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="b33d1-338">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="b33d1-338">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="b33d1-339">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="b33d1-339">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="b33d1-340">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="b33d1-340">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="b33d1-341">#c71585</span><span class="sxs-lookup"><span data-stu-id="b33d1-341">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="b33d1-342">#191970</span><span class="sxs-lookup"><span data-stu-id="b33d1-342">#191970</span></span>|
|`mintcream`|<span data-ttu-id="b33d1-343">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="b33d1-343">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="b33d1-344">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="b33d1-344">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="b33d1-345">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="b33d1-345">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="b33d1-346">#ffdead</span><span class="sxs-lookup"><span data-stu-id="b33d1-346">#ffdead</span></span>|
|`navy`|<span data-ttu-id="b33d1-347">#000080</span><span class="sxs-lookup"><span data-stu-id="b33d1-347">#000080</span></span>|
|`oldlace`|<span data-ttu-id="b33d1-348">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="b33d1-348">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="b33d1-349">#808000</span><span class="sxs-lookup"><span data-stu-id="b33d1-349">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="b33d1-350">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="b33d1-350">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="b33d1-351">#ffa500</span><span class="sxs-lookup"><span data-stu-id="b33d1-351">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="b33d1-352">#ff4500</span><span class="sxs-lookup"><span data-stu-id="b33d1-352">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="b33d1-353">#da70d6</span><span class="sxs-lookup"><span data-stu-id="b33d1-353">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="b33d1-354">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="b33d1-354">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="b33d1-355">#98fb98</span><span class="sxs-lookup"><span data-stu-id="b33d1-355">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="b33d1-356">#afeeee</span><span class="sxs-lookup"><span data-stu-id="b33d1-356">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="b33d1-357">#db7093</span><span class="sxs-lookup"><span data-stu-id="b33d1-357">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="b33d1-358">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="b33d1-358">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="b33d1-359">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="b33d1-359">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="b33d1-360">#cd853f</span><span class="sxs-lookup"><span data-stu-id="b33d1-360">#cd853f</span></span>|
|`pink`|<span data-ttu-id="b33d1-361">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="b33d1-361">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="b33d1-362">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="b33d1-362">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="b33d1-363">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="b33d1-363">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="b33d1-364">#800080</span><span class="sxs-lookup"><span data-stu-id="b33d1-364">#800080</span></span>|
|`red`|<span data-ttu-id="b33d1-365">#ff0000</span><span class="sxs-lookup"><span data-stu-id="b33d1-365">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="b33d1-366">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="b33d1-366">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="b33d1-367">#4169e1</span><span class="sxs-lookup"><span data-stu-id="b33d1-367">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="b33d1-368">#8b4513</span><span class="sxs-lookup"><span data-stu-id="b33d1-368">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="b33d1-369">#fa8072</span><span class="sxs-lookup"><span data-stu-id="b33d1-369">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="b33d1-370">#f4a460</span><span class="sxs-lookup"><span data-stu-id="b33d1-370">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="b33d1-371">#00ff00</span><span class="sxs-lookup"><span data-stu-id="b33d1-371">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="b33d1-372">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="b33d1-372">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="b33d1-373">#a0522d</span><span class="sxs-lookup"><span data-stu-id="b33d1-373">#a0522d</span></span>|
|`silver`|<span data-ttu-id="b33d1-374">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="b33d1-374">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="b33d1-375">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="b33d1-375">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="b33d1-376">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="b33d1-376">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="b33d1-377">#708090</span><span class="sxs-lookup"><span data-stu-id="b33d1-377">#708090</span></span>|
|`snow`|<span data-ttu-id="b33d1-378">#fffafa</span><span class="sxs-lookup"><span data-stu-id="b33d1-378">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="b33d1-379">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="b33d1-379">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="b33d1-380">#4682b4</span><span class="sxs-lookup"><span data-stu-id="b33d1-380">#4682b4</span></span>|
|`tan`|<span data-ttu-id="b33d1-381">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="b33d1-381">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="b33d1-382">#008080</span><span class="sxs-lookup"><span data-stu-id="b33d1-382">#008080</span></span>|
|`thistle`|<span data-ttu-id="b33d1-383">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="b33d1-383">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="b33d1-384">#ff6347</span><span class="sxs-lookup"><span data-stu-id="b33d1-384">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="b33d1-385">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="b33d1-385">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="b33d1-386">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="b33d1-386">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="b33d1-387">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="b33d1-387">#f5deb3</span></span>|
|`white`|<span data-ttu-id="b33d1-388">#ffffff</span><span class="sxs-lookup"><span data-stu-id="b33d1-388">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="b33d1-389">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="b33d1-389">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="b33d1-390">#ffff00</span><span class="sxs-lookup"><span data-stu-id="b33d1-390">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="b33d1-391">#9acd32</span><span class="sxs-lookup"><span data-stu-id="b33d1-391">#9acd32</span></span>|
