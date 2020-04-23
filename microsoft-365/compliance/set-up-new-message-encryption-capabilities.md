---
title: Einrichten neuer Nachrichtenverschlüsselungsfunktionen
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Mit den neuen Office 365-Nachrichtenverschlüsselungsfunktionen (Office 365 Message Encryption, OME), die auf Azure Information Protection aufbauen, kann Ihre Organisation geschützte E-Mail-Kommunikation mit Personen innerhalb und außerhalb der Organisation nutzen. Die neuen OME-Funktionen arbeiten mit anderen Organisationen, Outlook.com, Gmail und anderen E-Mail-Diensten zusammen.
ms.openlocfilehash: 95ac1528c59dc3f59e0d0e923d78ffb7138456d5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635467"
---
# <a name="set-up-new-message-encryption-capabilities"></a><span data-ttu-id="3830b-104">Einrichten neuer Nachrichtenverschlüsselungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="3830b-104">Set up new Message Encryption capabilities</span></span>

<span data-ttu-id="3830b-105">Die neuen Funktionen der Office 365-Nachrichtenverschlüsselung (OME) ermöglichen es Organisationen, geschützte E-Mails mit anderen Personen auf jedem Gerät freizugeben.</span><span class="sxs-lookup"><span data-stu-id="3830b-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="3830b-106">Benutzer können geschützte Nachrichten mit anderen Microsoft 365-Organisationen sowie Nicht-Kunden austauschen, die Outlook.com, Gmail und andere E-Mail-Dienste verwenden.</span><span class="sxs-lookup"><span data-stu-id="3830b-106">Users can exchange protected messages with other Microsoft 365 organizations, as well as non-customers using Outlook.com, Gmail, and other email services.</span></span>

<span data-ttu-id="3830b-107">Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die neuen OME-Funktionen in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="3830b-107">Follow the steps below to ensure that the new OME capabilities are available in your organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="3830b-108">Überprüfen Sie, dass Azure Rights Management aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="3830b-108">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="3830b-109">Die neuen OME-Funktionen nutzen die Schutzfeatures in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), der Technologie, die von [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) zum Schützen von E-Mails und Dokumenten mithilfe von Verschlüsselung und Zugriffssteuerelementen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3830b-109">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="3830b-110">Die einzige Voraussetzung für die Verwendung der neuen OME-Funktionen besteht darin, dass [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) im Mandanten Ihrer Organisation aktiviert sein muss.</span><span class="sxs-lookup"><span data-stu-id="3830b-110">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="3830b-111">Wenn dies zutrifft, werden die neuen OME-Funktionen von Microsoft 365 automatisch aktiviert, und Sie müssen nichts unternehmen.</span><span class="sxs-lookup"><span data-stu-id="3830b-111">If it is, Microsoft 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="3830b-112">Azure RMS wird auch bei den meisten berechtigenden Plänen automatisch aktiviert, daher müssen Sie in dieser Hinsicht wahrscheinlich auch keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="3830b-112">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="3830b-113">Weitere Informationen hierzu finden Sie unter [Aktivieren von Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="3830b-113">See [Activating Azure Rights Management](https://docs.microsoft.com/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3830b-114">Wenn Sie Active Directory Rights Management Services (AD RMS) mit Exchange Online verwenden, müssen Sie zu [Azure Information Protection migrieren](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms), bevor Sie die neuen OME-Funktionen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3830b-114">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="3830b-115">OME ist nicht kompatibel mit AD RMS.</span><span class="sxs-lookup"><span data-stu-id="3830b-115">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="3830b-116">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="3830b-116">For more information, see:</span></span>

- <span data-ttu-id="3830b-117">Lesen Sie [Welche Abonnements benötige ich, um die neuen OME-Funktionen nutzen zu können?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities), um zu überprüfen, ob Ihr Abonnementplan Azure Information Protection umfasst (das Azure RMS-Funktionen beinhaltet).</span><span class="sxs-lookup"><span data-stu-id="3830b-117">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="3830b-118">Informationen zum Kauf eines berechtigenden Abonnements finden Sie unter [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="3830b-118">[Azure Information Protection](https://azure.microsoft.com/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="3830b-119">Manuelles Aktivieren von Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="3830b-119">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="3830b-120">Wenn Sie Azure RMS deaktiviert haben oder wenn es aus irgendeinem Grund nicht automatisch aktiviert wurde, können Sie es hier manuell im aktivieren:</span><span class="sxs-lookup"><span data-stu-id="3830b-120">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="3830b-121">**Microsoft 365 Admin Center**: Anweisungen hierzu finden Sie unter [Aktivieren von Azure Rights Management im Admin Center](https://docs.microsoft.com/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="3830b-121">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="3830b-122">**Azure-Portal**: Anweisungen hierzu finden Sie unter [Aktivieren von Azure Rights Management im Azure-Portal](https://docs.microsoft.com/azure/information-protection/activate-azure).</span><span class="sxs-lookup"><span data-stu-id="3830b-122">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="3830b-123">Konfigurieren der Verwaltung Ihres Azure Information Protection-Mandantenschlüssels</span><span class="sxs-lookup"><span data-stu-id="3830b-123">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="3830b-124">Dies ist ein optionaler Schritt.</span><span class="sxs-lookup"><span data-stu-id="3830b-124">This is an optional step.</span></span> <span data-ttu-id="3830b-125">Microsoft das Verwalten des Hauptschlüssels für Azure Information Protection zu gestatten, ist die Standardeinstellung und wird als bewährte Methode für die meisten Organisationen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3830b-125">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most organizations.</span></span> <span data-ttu-id="3830b-126">In diesem Fall brauchen Sie nichts zu unternehmen.</span><span class="sxs-lookup"><span data-stu-id="3830b-126">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="3830b-127">Es gibt viele Gründe, beispielsweise Complianceanforderungen, aus denen Sie Ihren eigenen Hauptschlüssel generieren und verwalten müssen – auch als "Bring Your Own Key" (BYOK) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3830b-127">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="3830b-128">In diesem Fall empfehlen wir Ihnen, vor dem Einrichten der neuen OME-Funktionen die erforderlichen Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="3830b-128">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="3830b-129">Weitere Informationen finden Sie unter [Planen und Implementieren Ihres Azure Information Protection-Mandantenschlüssels](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="3830b-129">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="3830b-130">Überprüfen der neuen OME-Konfiguration in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3830b-130">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="3830b-131">Sie können überprüfen, ob Ihr Microsoft 365-Mandant für die Verwendung der neuen OME-Funktionen in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) ordnungsgemäß konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="3830b-131">You can verify that your Microsoft 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="3830b-132">[Stellen Sie eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell), und verwenden Sie dafür ein Konto mit globalen Administratorberechtigungen in Ihrem Microsoft 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="3830b-132">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Microsoft 365 tenant.</span></span>

2. <span data-ttu-id="3830b-133">Führen Sie das Cmdlet "Get-IRMConfiguration" aus.</span><span class="sxs-lookup"><span data-stu-id="3830b-133">Run the Get-IRMConfiguration cmdlet.</span></span>

     <span data-ttu-id="3830b-134">Für den Parameter AzureRMSLicensingEnabled sollte der Wert "$True" angezeigt werden, der angibt, dass OME auf Ihrem-Mandanten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="3830b-134">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="3830b-135">Ist das nicht der Fall, verwenden Sie "Set-IRMConfiguration", um den Wert von "AzureRMSLicensingEnabled" auf "$True" festzulegen, um OME zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3830b-135">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="3830b-136">Führen Sie das Cmdlet "Test-IRMConfiguration" unter Verwendung der folgenden Syntax aus:</span><span class="sxs-lookup"><span data-stu-id="3830b-136">Run the Test-IRMConfiguration cmdlet using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="3830b-137">**Beispiel**:</span><span class="sxs-lookup"><span data-stu-id="3830b-137">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="3830b-138">Die Angabe der E-Mail-Adresse eines Absenders ist optional, aber durch diesen Wert wird das System gezwungen, zusätzliche Prüfungen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="3830b-138">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="3830b-139">Verwenden Sie die E-Mail-Adresse eines beliebigen Benutzers in Ihrem Microsoft 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="3830b-139">Use the email address of any user in your Microsoft 365 tenant.</span></span>

     <span data-ttu-id="3830b-140">Die Ergebnisse sollten in etwa folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="3830b-140">Your results should be similar to:</span></span>

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - <span data-ttu-id="3830b-141">Der Name Ihrer Organisation ersetzt *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="3830b-141">Your organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="3830b-142">Die Standardvorlagennamen unterscheiden sich möglicherweise von den vorstehenden.</span><span class="sxs-lookup"><span data-stu-id="3830b-142">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="3830b-143">Weitere Informationen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="3830b-143">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="3830b-144">Führen Sie das Cmdlet "Remove-PSSession" aus, um die Verbindung mit dem Rights Management-Dienst zu trennen.</span><span class="sxs-lookup"><span data-stu-id="3830b-144">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="3830b-145">Nächste Schritte: Definieren von Nachrichtenflussregeln, um neue OME-Funktionen zu verwenden</span><span class="sxs-lookup"><span data-stu-id="3830b-145">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="3830b-146">Wenn zuvor konfigurierte Nachrichtenflussregeln zum Verschlüsseln von E-Mails in Ihrer Organisation konfiguriert wurden, müssen Sie die vorhandenen Regeln zur Verwendung der neuen OME-Funktionen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3830b-146">If there are previously configured mail flow rules to encrypt email in your organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="3830b-147">Für neue Bereitstellungen müssen Sie neue Nachrichtenflussregeln erstellen.</span><span class="sxs-lookup"><span data-stu-id="3830b-147">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="3830b-148">Wenn Sie vorhandene Nachrichtenflussregeln nicht aktualisieren, werden Ihre Benutzer weiterhin verschlüsselte E-Mails empfangen, bei denen das vorherige HTML-Anlagenformat statt der neuen, nahtlosen OME-Erfahrung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3830b-148">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="3830b-149">Nachrichtenflussregeln bestimmen, unter welchen Bedingungen E-Mail-Nachrichten verschlüsselt werden sollten, sowie Bedingungen zum Entfernen dieser Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="3830b-149">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="3830b-150">Wenn Sie eine Aktion für eine Regel festlegen, werden alle Nachrichten, die den Regelbedingungen entsprechen, beim Senden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="3830b-150">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="3830b-151">Schritte zum Erstellen von Nachrichtenflussregeln für OME finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="3830b-151">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="3830b-152">So aktualisieren Sie vorhandene Regeln so, dass die neuen OME-Funktionen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3830b-152">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="3830b-153">Wechseln Sie im Microsoft 365 Admin Center zu **Admin Center > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="3830b-153">In the Microsoft 365 admin center, go to **Admin centers > Exchange**.</span></span>
2. <span data-ttu-id="3830b-154">Wechseln Sie im Exchange Admin Center zu **Nachrichtenfluss > Regeln**.</span><span class="sxs-lookup"><span data-stu-id="3830b-154">In the Exchange admin center, go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="3830b-155">**Gehen Sie für jede Regel wie folgt vor**:</span><span class="sxs-lookup"><span data-stu-id="3830b-155">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="3830b-156">Wählen Sie **Nachrichtensicherheit ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="3830b-156">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="3830b-157">Wählen Sie **Office 365-Nachrichtenverschlüsselung und Rechteschutz anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="3830b-157">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="3830b-158">Wählen Sie eine RMS-Vorlage aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="3830b-158">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="3830b-159">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3830b-159">Select **Save**.</span></span>
    - <span data-ttu-id="3830b-160">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="3830b-160">Select **OK**.</span></span>
