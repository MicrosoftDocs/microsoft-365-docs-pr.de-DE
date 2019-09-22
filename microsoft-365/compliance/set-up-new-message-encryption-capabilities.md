---
title: Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen
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
description: Mit den neuen Office 365-Nachrichtenverschlüsselungsfunktionen (Office 365 Message Encryption, OME), die auf Azure Information Protection aufbauen, kann Ihre Organisation geschützte E-Mail-Kommunikation mit Personen innerhalb und außerhalb der Organisation nutzen. Die neuen OME-Funktionen arbeiten mit anderen Office 365-Organisationen, Outlook.com, Gmail und anderen E-Mail-Diensten zusammen.
ms.openlocfilehash: 835b1d6f40868684536dbea8f75dab0665950210
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081917"
---
# <a name="set-up-new-office-365-message-encryption-capabilities"></a><span data-ttu-id="a776c-104">Einrichten neuer Office 365-Nachrichtenverschlüsselungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="a776c-104">Set up new Office 365 Message Encryption capabilities</span></span>

<span data-ttu-id="a776c-105">Die neuen Funktionen der Office 365-Nachrichtenverschlüsselung (OME) ermöglichen es Organisationen, geschützte E-Mails mit anderen Personen auf jedem Gerät freizugeben.</span><span class="sxs-lookup"><span data-stu-id="a776c-105">The new Office 365 Message Encryption (OME) capabilities allow organizations to share protected email with anyone on any device.</span></span> <span data-ttu-id="a776c-106">Benutzer können geschützte Nachrichten mit anderen Office 365-Organisationen sowie Nicht-Office 365-Kunden, die Outlook.com, Gmail und andere E-Mail-Dienste verwenden, austauschen.</span><span class="sxs-lookup"><span data-stu-id="a776c-106">Users can exchange protected messages with other Office 365 organizations, as well as non-Office 365 customers using Outlook.com, Gmail, and other email services.</span></span>

||
|:-----|
|<span data-ttu-id="a776c-107">Dieser Artikel ist Teil einer größeren Reihe von Artikeln zur Office 365-Nachrichtenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="a776c-107">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="a776c-108">Dieser Artikel ist für Administratoren und IT-Experten bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a776c-108">This article is intended for  IT Pros.</span></span> <span data-ttu-id="a776c-109">Wenn Sie nur nach Informationen zum Senden oder Empfangen einer verschlüsselten Nachricht suchen, suchen Sie in der [Office 365-Nachrichtenverschlüsselung (OME)](ome.md) in der Artikelliste den Artikel, der Ihren Anforderungen am besten entspricht.</span><span class="sxs-lookup"><span data-stu-id="a776c-109">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

<span data-ttu-id="a776c-110">Führen Sie die folgenden Schritte aus, um sicherzustellen, dass die neuen OME-Funktionen in Ihrer Office 365-Organisation verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a776c-110">Follow the steps below to ensure that the New OME capabilities are available in your Office 365 organization.</span></span>

## <a name="verify-that-azure-rights-management-is-active"></a><span data-ttu-id="a776c-111">Überprüfen Sie, dass Azure Rights Management aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="a776c-111">Verify that Azure Rights Management is active</span></span>

<span data-ttu-id="a776c-112">Die neuen OME-Funktionen nutzen die Schutzfeatures in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/de-DE/azure/information-protection/what-is-information-protection), der Technologie, die von [Azure Information Protection](https://docs.microsoft.com/de-DE/azure/information-protection/what-is-azure-rms) zum Schützen von E-Mails und Dokumenten mithilfe von Verschlüsselung und Zugriffssteuerelementen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a776c-112">The new OME capabilities leverage the protection features in [Azure Rights Management Services (Azure RMS)](https://docs.microsoft.com/de-DE/azure/information-protection/what-is-information-protection), the technology used by [Azure Information Protection](https://docs.microsoft.com/de-DE/azure/information-protection/what-is-azure-rms) to protect emails and documents via encryption and access controls.</span></span>

<span data-ttu-id="a776c-113">Die einzige Voraussetzung für die Verwendung der neuen OME-Funktionen besteht darin, dass [Azure Rights Management](https://docs.microsoft.com/de-DE/azure/information-protection/what-is-azure-rms) im Mandanten Ihrer Organisation aktiviert sein muss.</span><span class="sxs-lookup"><span data-stu-id="a776c-113">The only prerequisite for using the new OME capabilities is that [Azure Rights Management](https://docs.microsoft.com/de-DE/azure/information-protection/what-is-azure-rms) must be activated in your organization's tenant.</span></span> <span data-ttu-id="a776c-114">Ist dies der Fall, werden die neuen OME-Funktionen von Office 365 automatisch aktiviert, und Sie müssen nichts unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a776c-114">If it is, Office 365 activates the new OME capabilities automatically and you don't need to do anything.</span></span>

<span data-ttu-id="a776c-115">Azure RMS wird auch bei den meisten berechtigenden Plänen automatisch aktiviert, daher müssen Sie in dieser Hinsicht wahrscheinlich auch keine Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="a776c-115">Azure RMS is also activated automatically for most eligible plans, so you probably don't have to do anything in this regard either.</span></span> <span data-ttu-id="a776c-116">Weitere Informationen hierzu finden Sie unter [Aktivieren von Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service).</span><span class="sxs-lookup"><span data-stu-id="a776c-116">See [Activating Azure Rights Management](https://docs.microsoft.com/en-gb/azure/information-protection/activate-service) for more information.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a776c-117">Wenn Sie Active Directory Rights Management Services (AD RMS) mit Exchange Online verwenden, müssen Sie zu [Azure Information Protection migrieren](https://docs.microsoft.com/de-DE/azure/information-protection/migrate-from-ad-rms-to-azure-rms), bevor Sie die neuen OME-Funktionen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a776c-117">If you use Active Directory Rights Management service (AD RMS) with Exchange Online, you need to [migrate to Azure Information Protection](https://docs.microsoft.com/de-DE/azure/information-protection/migrate-from-ad-rms-to-azure-rms) before you can use the new OME capabilities.</span></span> <span data-ttu-id="a776c-118">OME ist nicht kompatibel mit AD RMS.</span><span class="sxs-lookup"><span data-stu-id="a776c-118">OME is not compatible with AD RMS.</span></span>  

<span data-ttu-id="a776c-119">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="a776c-119">For more information, see:</span></span>

- <span data-ttu-id="a776c-120">Lesen Sie [Welche Abonnements benötige ich, um die neuen OME-Funktionen nutzen zu können?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities), um zu überprüfen, ob Ihr Abonnementplan Azure Information Protection umfasst (das Azure RMS-Funktionen beinhaltet).</span><span class="sxs-lookup"><span data-stu-id="a776c-120">[What subscriptions do I need to use the new OME capabilities?](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) to check whether your subscription plan includes Azure Information Protection (which includes Azure RMS functionality).</span></span>
- <span data-ttu-id="a776c-121">Informationen zum Kauf eines berechtigenden Abonnements finden Sie unter [Azure Information Protection](https://azure.microsoft.com/de-DE/services/information-protection/).</span><span class="sxs-lookup"><span data-stu-id="a776c-121">[Azure Information Protection](https://azure.microsoft.com/de-DE/services/information-protection/) for information about purchasing an eligible subscription.</span></span>  

### <a name="manually-activating-azure-rights-management"></a><span data-ttu-id="a776c-122">Manuelles Aktivieren von Azure Rights Management</span><span class="sxs-lookup"><span data-stu-id="a776c-122">Manually activating Azure Rights Management</span></span>

<span data-ttu-id="a776c-123">Wenn Sie Azure RMS deaktiviert haben oder wenn es aus irgendeinem Grund nicht automatisch aktiviert wurde, können Sie es hier manuell im aktivieren:</span><span class="sxs-lookup"><span data-stu-id="a776c-123">If you disabled Azure RMS, or if it was not automatically activated for any reason, you can activate it manually in the:</span></span>

- <span data-ttu-id="a776c-124">**Microsoft 365 Admin Center**: Anweisungen hierzu finden Sie unter [Aktivieren von Azure Rights Management im Admin Center](https://docs.microsoft.com/de-DE/azure/information-protection/activate-office365).</span><span class="sxs-lookup"><span data-stu-id="a776c-124">**Microsoft 365 admin center**: See [How to activate Azure Rights Management from the admin center](https://docs.microsoft.com/de-DE/azure/information-protection/activate-office365) for instructions.</span></span>
- <span data-ttu-id="a776c-125">**Azure-Portal**: Anweisungen hierzu finden Sie unter [Aktivieren von Azure Rights Management im Azure-Portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure).</span><span class="sxs-lookup"><span data-stu-id="a776c-125">**Azure portal**: See [How to activate Azure Rights Management from the Azure portal](https://docs.microsoft.com/en-gb/azure/information-protection/activate-azure) for instructions.</span></span>

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a><span data-ttu-id="a776c-126">Konfigurieren der Verwaltung Ihres Azure Information Protection-Mandantenschlüssels</span><span class="sxs-lookup"><span data-stu-id="a776c-126">Configure management of your Azure Information Protection tenant key</span></span>

<span data-ttu-id="a776c-127">Dies ist ein optionaler Schritt.</span><span class="sxs-lookup"><span data-stu-id="a776c-127">This is an optional step.</span></span> <span data-ttu-id="a776c-128">Microsoft das Verwalten des Hauptschlüssels für Azure Information Protection zu gestatten, ist die Standardeinstellungen und wird als bewährte Methoden für die meisten Office 365-Mandanten empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a776c-128">Allowing Microsoft to manage the root key for Azure Information Protection is the default setting and recommended best practice for most Office 365 tenants.</span></span> <span data-ttu-id="a776c-129">In diesem Fall brauchen Sie nichts zu unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a776c-129">If this is the case, you don't need to do anything.</span></span>

<span data-ttu-id="a776c-130">Es gibt viele Gründe, beispielsweise Complianceanforderungen, aus denen Sie Ihren eigenen Hauptschlüssel generieren und verwalten müssen – auch als "Bring Your Own Key" (BYOK) bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="a776c-130">There are many reasons, for example compliance requirements, that may necessitate you generating and managing your own root key (also known as bring your own key (BYOK)).</span></span> <span data-ttu-id="a776c-131">In diesem Fall empfehlen wir Ihnen, vor dem Einrichten der neuen OME-Funktionen die erforderlichen Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a776c-131">If this is the case, we recommend that you complete the required steps before setting up the new OME capabilities.</span></span> <span data-ttu-id="a776c-132">Weitere Informationen finden Sie unter [Planen und Implementieren Ihres Azure Information Protection-Mandantenschlüssels](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="a776c-132">See [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key) for more.</span></span>

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a><span data-ttu-id="a776c-133">Überprüfen der neuen OME-Konfiguration in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a776c-133">Verify new OME configuration in Exchange Online PowerShell</span></span>

<span data-ttu-id="a776c-134">Sie können überprüfen, ob Ihr Office 365-Mandant für die Verwendung der neuen OME-Funktionen in [Exchange Online PowerShell](https://docs.microsoft.com/de-DE/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps) ordnungsgemäß konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a776c-134">You can verify that your Office 365 tenant is properly configured to use the new OME capabilities in [Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps).</span></span>
  
1. <span data-ttu-id="a776c-135">Stellen Sie eine [Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/de-DE/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) unter Verwendung eines Kontos mit globalen Administratorberechtigungen in Ihrem Office 365-Mandanten her.</span><span class="sxs-lookup"><span data-stu-id="a776c-135">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/de-DE/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) using an account with global administrator permissions in your Office 365 tenant.</span></span>

2. <span data-ttu-id="a776c-136">Führen Sie das Cmdlet "Get-IRMConfiguration" aus.</span><span class="sxs-lookup"><span data-stu-id="a776c-136">Run the Get-SPOHubSite cmdlet.</span></span>

     <span data-ttu-id="a776c-137">Für den Parameter AzureRMSLicensingEnabled sollte der Wert "$True" angezeigt werden, der angibt, dass OME auf Ihrem-Mandanten konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a776c-137">You should see a value of $True for the AzureRMSLicensingEnabled parameter, which indicates that OME is configured in your tenant.</span></span> <span data-ttu-id="a776c-138">Ist das nicht der Fall, verwenden Sie "Set-IRMConfiguration", um den Wert von "AzureRMSLicensingEnabled" auf "$True" festzulegen, um OME zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a776c-138">If it is not, use Set-IRMConfiguration to set the value of AzureRMSLicensingEnabled to $True to enable OME.</span></span>

3. <span data-ttu-id="a776c-139">Führen Sie das Cmdlet "Test-IRMConfiguration" unter Verwendung der folgenden Syntax aus:</span><span class="sxs-lookup"><span data-stu-id="a776c-139">Run the script by using the following syntax:</span></span>

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   <span data-ttu-id="a776c-140">**Beispiel**:</span><span class="sxs-lookup"><span data-stu-id="a776c-140">**Example**:</span></span>

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - <span data-ttu-id="a776c-141">Die Angabe der E-Mail-Adresse eines Absenders ist optional, aber durch diesen Wert wird das System gezwungen, zusätzliche Prüfungen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="a776c-141">Providing a sender email is optional, but forces the system to perform additional checks.</span></span> <span data-ttu-id="a776c-142">Verwenden Sie die E-Mail-Adresse eines beliebigen Benutzers auf Ihrem Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="a776c-142">Use the email address of any user in your Office 365 tenant.</span></span>

     <span data-ttu-id="a776c-143">Die Ergebnisse sollten in etwa folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="a776c-143">Your results should be similar to:</span></span>

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

   - <span data-ttu-id="a776c-144">Der Name Ihrer Office 365-Organisation ersetzt *Contoso*.</span><span class="sxs-lookup"><span data-stu-id="a776c-144">Your Office 365 organization name will replace *Contoso*.</span></span>

   - <span data-ttu-id="a776c-145">Die Standardvorlagennamen unterscheiden sich möglicherweise von den vorstehenden.</span><span class="sxs-lookup"><span data-stu-id="a776c-145">The default template names may be different from those displayed above.</span></span> <span data-ttu-id="a776c-146">Weitere Informationen finden Sie unter [Konfigurieren und Verwalten von Vorlagen für Azure Information Protection](https://docs.microsoft.com/de-DE/azure/information-protection/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="a776c-146">See [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/de-DE/azure/information-protection/configure-policy-templates) for more.</span></span>

4. <span data-ttu-id="a776c-147">Führen Sie das Cmdlet "Remove-PSSession" aus, um die Verbindung mit dem Rights Management-Dienst zu trennen.</span><span class="sxs-lookup"><span data-stu-id="a776c-147">Run the Remove-PSSession cmdlet to disconnect from the Rights Management service.</span></span>

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a><span data-ttu-id="a776c-148">Nächste Schritte: Definieren von Nachrichtenflussregeln, um neue OME-Funktionen zu verwenden</span><span class="sxs-lookup"><span data-stu-id="a776c-148">Next steps: Define mail flow rules to use new OME capabilities</span></span>

<span data-ttu-id="a776c-149">Wenn zuvor konfigurierte Nachrichtenflussregeln zum Verschlüsseln von E-Mails in Ihrer Office 365-Organisation konfiguriert wurden, müssen Sie die vorhandenen Regeln zur Verwendung der neuen OME-Funktionen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a776c-149">If there are previously configured mail flow rules to encrypt email in your Office 365 organization, you need to update the existing rules to use the new OME capabilities.</span></span> <span data-ttu-id="a776c-150">Für neue Bereitstellungen müssen Sie neue Nachrichtenflussregeln erstellen.</span><span class="sxs-lookup"><span data-stu-id="a776c-150">For new deployments, you need to create new mail flow rules.</span></span>

>[!IMPORTANT]
><span data-ttu-id="a776c-151">Wenn Sie vorhandene Nachrichtenflussregeln nicht aktualisieren, werden Ihre Benutzer weiterhin verschlüsselte E-Mails empfangen, bei denen das vorherige HTML-Anlagenformat statt der neuen, nahtlosen OME-Erfahrung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a776c-151">If you do not update existing mail flow rules, your users will continue to receive encrypted mail that uses the previous HTML attachment format, instead of the new seamless OME experience.</span></span>

<span data-ttu-id="a776c-152">Nachrichtenflussregeln bestimmen, unter welchen Bedingungen E-Mail-Nachrichten verschlüsselt werden sollten, sowie Bedingungen zum Entfernen dieser Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="a776c-152">Mail flow rules determine under what conditions email messages should be encrypted, as well as conditions for removing that encryption.</span></span> <span data-ttu-id="a776c-153">Wenn Sie eine Aktion für eine Regel festlegen, werden alle Nachrichten, die den Regelbedingungen entsprechen, beim Senden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="a776c-153">When you set an action for a rule, any messages that match the rule conditions are encrypted when they're sent.</span></span>
  
<span data-ttu-id="a776c-154">Schritte zum Erstellen von Nachrichtenflussregeln für OME finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="a776c-154">For steps on creating mail flow rules for OME, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

<span data-ttu-id="a776c-155">So aktualisieren Sie vorhandene Regeln so, dass die neuen OME-Funktionen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a776c-155">To update existing rules to use the new OME capabilities:</span></span>

1. <span data-ttu-id="a776c-156">Wechseln Sie im Microsoft 365 Admin Center zu **Admin Center > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a776c-156">In the Microsoft 365 admin center, in the left pane, go to **Admin centersMicrosoft Search**</span></span>
2. <span data-ttu-id="a776c-157">Wechseln Sie im Exchange Admin Center zu **Nachrichtenfluss > Regeln**.</span><span class="sxs-lookup"><span data-stu-id="a776c-157">In the Exchange admin center (EAC), go to **Mail flow > Rules**.</span></span>
3. <span data-ttu-id="a776c-158">**Gehen Sie für jede Regel wie folgt vor**:</span><span class="sxs-lookup"><span data-stu-id="a776c-158">For each rule, in **Do the following**:</span></span>
    - <span data-ttu-id="a776c-159">Wählen Sie **Nachrichtensicherheit ändern** aus.</span><span class="sxs-lookup"><span data-stu-id="a776c-159">Select **Modify the message security**.</span></span>
    - <span data-ttu-id="a776c-160">Wählen Sie **Office 365-Nachrichtenverschlüsselung und Rechteschutz anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="a776c-160">Select **Apply Office 365 Message Encryption and rights protection**.</span></span>
    - <span data-ttu-id="a776c-161">Wählen Sie eine RMS-Vorlage aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a776c-161">Select an RMS template from the list.</span></span>
    - <span data-ttu-id="a776c-162">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a776c-162">Select **Save**.</span></span>
    - <span data-ttu-id="a776c-163">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="a776c-163">Select **OK**.</span></span>
