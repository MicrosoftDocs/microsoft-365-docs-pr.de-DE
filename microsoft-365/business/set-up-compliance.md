---
title: Erhöhter Bedrohungsschutz für Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Richten Sie Office 365 Advanced Threat Protection ein, und schützen Sie vertrauliche Daten.
ms.openlocfilehash: 53741a7726222bb32329a401953be72257df95cc
ms.sourcegitcommit: 7ac06563c6ff034358e8fd3f9298fc426187ade2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668387"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="51eb9-103">Einrichten von Kompatibilitätsfeatures</span><span class="sxs-lookup"><span data-stu-id="51eb9-103">Set up compliance features</span></span>

<span data-ttu-id="51eb9-104">Ihr Microsoft 365 Business verfügt über Features zum Schutz Ihrer Daten und Geräte und hilft Ihnen dabei, die vertraulichen Informationen Ihrer Kunden sicher zu halten.</span><span class="sxs-lookup"><span data-stu-id="51eb9-104">Your Microsoft 365 Business comes with features to protect your data and devices, and help you keep yours and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="51eb9-105">Einrichten von DLP-Features</span><span class="sxs-lookup"><span data-stu-id="51eb9-105">Set up DLP features</span></span>

<span data-ttu-id="51eb9-106">Ein Beispiel zum Einrichten einer Richtlinie zum Schutz gegen personenbezogene Informationen (PII) finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) .</span><span class="sxs-lookup"><span data-stu-id="51eb9-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="51eb9-107">DLP verfügt über viele vorgefertigte Richtlinienvorlagen für viele unterschiedliche Gebietsschemas.</span><span class="sxs-lookup"><span data-stu-id="51eb9-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="51eb9-108">Zum Beispiel: Australien Financial Data, Canada Personal Information Act, US Financial Data, etc. Eine vollständige Liste finden Sie unter [was die DLP-Richtlinienvorlagen enthalten](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) .</span><span class="sxs-lookup"><span data-stu-id="51eb9-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, etc. See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="51eb9-109">Alle diese Vorlagen können ähnlich wie beim PII-Vorlagenbeispiel aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="51eb9-109">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="51eb9-110">Einrichten der e-Mail-Aufbewahrung mit Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="51eb9-110">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="51eb9-111">**Exchange Online Archivierungs** Lizenz Funktionen unterstützen die Einhaltung von Vorschriften und behördlichen Vorgaben durch die Beibehaltung von e-Mail-Inhalten für eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="51eb9-111">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="51eb9-112">Es hilft auch, das Risiko im Fall eines Rechtsstreits zu verringern, und bietet eine Möglichkeit, Daten nach einer Sicherheitsverletzung wiederherzustellen, oder wenn Sie gelöschte Elemente wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-112">It also helps reduce your risk in the event of a lawsuit and provides a way to recover data after a security breach, or when you need to recover deleted items.</span></span> <span data-ttu-id="51eb9-113">Sie können das Beweissicherungsverfahren verwenden, um alle Inhalte eines Benutzers beizubehalten, oder Sie verwenden Aufbewahrungsrichtlinien, um die beizubehaltenden Elemente anzupassen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-113">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="51eb9-114">**Beweissicherungsverfahren:** Sie können alle Postfachinhalte einschließlich gelöschter Elemente beibehalten, indem Sie das gesamte Postfach eines Benutzers in das Beweissicherungsverfahren versetzen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-114">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="51eb9-115">So legen Sie ein Postfach für das Beweissicherungsverfahren im Admin Center ab:</span><span class="sxs-lookup"><span data-stu-id="51eb9-115">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="51eb9-116">Navigieren Sie im linken Navigationsbereich zu **Benutzer** \> **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="51eb9-116">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="51eb9-117">Wählen Sie einen Benutzer aus, dessen Postfach Sie in das Beweissicherungsverfahren einfügen möchten, und klicken Sie im Benutzerbereich auf **e-Mail-Einstellungen** erweitern, und wählen Sie neben **Weitere Einstellungen** die Option **Exchange-Eigenschaften bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="51eb9-117">Select a user whose mailbox you want to place on litigation hold and in the user pane expand **Mail settings** and next to **More settings** choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="51eb9-118">Wählen Sie auf der Seite Postfachbenutzer im linken Navigationsbereich die Option \* \* Postfachfeatures \* \* aus, und wählen Sie dann den Link **aktivieren** unter **Beweissicherungsverfahren**aus.</span><span class="sxs-lookup"><span data-stu-id="51eb9-118">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="51eb9-119">Im Dialogfeld **Beweissicherungsverfahren** können Sie die Dauer des beweissicherungsverfahrens im Feld **Dauer des Beweis** Sicherungsverfahrens angeben, das Feld leer lassen, wenn Sie einen unbegrenzten Haltebereich platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="51eb9-119">In the **litigation hold** dialog box you can specify the litigation hold duration in the **Litigation hold duration** field, leave field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="51eb9-120">Sie können auch Notizen hinzufügen und den Postfachbesitzer an eine Website weiterleiten, die möglicherweise mehr über das \> \*\*\*\* Beweissicherungsverfahren zu erklären ist.</span><span class="sxs-lookup"><span data-stu-id="51eb9-120">You can also add notes and direct the mail box owner to a website you might have to explain more about the litigation hold \> **Save**.</span></span>
    
<span data-ttu-id="51eb9-121">**Aufbewahrung:** Sie können benutzerdefinierte Aufbewahrungsrichtlinien aktivieren, beispielsweise um eine bestimmte Zeitspanne beizubehalten oder Inhalte dauerhaft am Ende des Aufbewahrungszeitraums zu löschen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-121">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="51eb9-122">Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="51eb9-122">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-azure-information-protection-features"></a><span data-ttu-id="51eb9-123">Einrichten von Azure Information Protection-Features</span><span class="sxs-lookup"><span data-stu-id="51eb9-123">Set up Azure Information Protection features</span></span>

<span data-ttu-id="51eb9-124">Azure Information Protection (AIP) hilft Ihnen, Ihre Dokumente und e-Mails zu klassifizieren und optional zu schützen, indem Sie Bezeichnungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="51eb9-124">Azure Information Protection (AIP) helps you classify and optionally, protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="51eb9-125">Bezeichnungen können automatisch von Administratoren angewendet werden, die Regeln und Bedingungen manuell von Benutzern definieren, oder indem Sie eine Kombination verwenden, in der Benutzern Empfehlungen gegeben werden.</span><span class="sxs-lookup"><span data-stu-id="51eb9-125">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="51eb9-126">In Outlook im Internet können Sie die folgenden integrierten Bezeichnungen und Einschränkungen auf Ihre e-Mails anwenden:</span><span class="sxs-lookup"><span data-stu-id="51eb9-126">In Outlook on the web you can apply the following built-in labels and restrictions to your emails:</span></span>
  
- <span data-ttu-id="51eb9-127">**Nicht weiterleiten**: Empfänger können die Nachricht lesen, aber keine Inhalte weiterleiten, drucken oder kopieren</span><span class="sxs-lookup"><span data-stu-id="51eb9-127">**Do Not Forward**: Recipients can read the message, but they can't forward, print, or copy content</span></span>
    
- <span data-ttu-id="51eb9-128">\*\*\*\* Verschlüsseln: die gesamte Nachricht ist verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="51eb9-128">**Encrypt**: The entire message is encrypted.</span></span> <span data-ttu-id="51eb9-129">Empfänger müssen Ihre Identität vor dem Zugriff auf verschlüsselte Inhalte bestätigen und die Verschlüsselung nicht entfernen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-129">Recipients must confirm their identity before accessing encrypted content and can't remove encryption.</span></span>
    
- <span data-ttu-id="51eb9-130">**Vertraulich**: gibt den Mitarbeitern in Ihrer Organisation vollständige Berechtigungen für e-Mail-Inhalte und-Anlagen, jedoch nicht für Personen außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="51eb9-130">**Confidential**: Gives the employees in your organization full permissions to the email content and attachments, but not to people outside your organization.</span></span> <span data-ttu-id="51eb9-131">Datenbesitzer können Inhalte an beliebiger Position nachverfolgen und widerrufen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-131">Data owners can track and revoke content at any point.</span></span>
    
- <span data-ttu-id="51eb9-132">**Streng vertraulich**: Diese Einschränkung kann auf streng vertrauliche Daten angewendet werden, sodass Mitarbeiter die Daten anzeigen, bearbeiten und beantworten, aber nicht weiterleiten, drucken oder kopieren können.</span><span class="sxs-lookup"><span data-stu-id="51eb9-132">**Highly Confidential**: This restriction can be applied to highly confidential data, allowing employees to view, edit, and reply, but not forward, print, or copy the data.</span></span> <span data-ttu-id="51eb9-133">Datenbesitzer können Inhalte an beliebiger Position nachverfolgen und widerrufen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-133">Data owners can track and revoke content at any point.</span></span>

### <a name="make-sure-azure-information-protection-is-activated"></a><span data-ttu-id="51eb9-134">Stellen Sie sicher, dass Azure Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="51eb9-134">Make sure Azure Information Protection is activated</span></span>

<span data-ttu-id="51eb9-135">So stellen Sie sicher, dass AIP aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="51eb9-135">To verify that AIP is activated :</span></span>

1. <span data-ttu-id="51eb9-136">Melden Sie sich beim [Azure-Portal](https://portal.azure.com/)an.</span><span class="sxs-lookup"><span data-stu-id="51eb9-136">Sign into [Azure portal](https://portal.azure.com/).</span></span>

2. <span data-ttu-id="51eb9-137">Wählen Sie **alle Dienste** aus, und geben Sie in das **Suchfeld** *Azure Information Protection* ein.</span><span class="sxs-lookup"><span data-stu-id="51eb9-137">Select **All services** and type in *Azure Information Protection* in the **Search Box**.</span></span>

3. <span data-ttu-id="51eb9-138">Nachdem die Ergebnisse angezeigt wurden, klicken Sie auf den Start neben **Azure Information Protection** , um ihn zu einem bevorzugten und leicht zu findenden späteren Zeitpunkt zu machen.</span><span class="sxs-lookup"><span data-stu-id="51eb9-138">Once the results display, click the start next to **Azure Information Protection** to make it a favorite and easy to find later.</span></span>

4. <span data-ttu-id="51eb9-139">Wählen Sie **Azure Information Protection** \> **Protection-Aktivierung** aus, und stellen Sie sicher, dass der Status auf Aktiviert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="51eb9-139">Select **Azure Information Protection** \> **Protection activation** and make sure the status is set to activated.</span></span> 

### <a name="view-the-azure-information-protection-policy-and-default-labels"></a><span data-ttu-id="51eb9-140">Anzeigen der Azure Information Protection-Richtlinie und der Standardbeschriftungen</span><span class="sxs-lookup"><span data-stu-id="51eb9-140">View the Azure Information Protection policy and default labels</span></span> 

<span data-ttu-id="51eb9-141">So zeigen Sie die vorhandenen Bezeichnungen an und ändern Sie:</span><span class="sxs-lookup"><span data-stu-id="51eb9-141">To view, and modify, the existing labels:</span></span>

1. <span data-ttu-id="51eb9-142">Wählen Sie im Azure Information Protection-Dashboard **Klassifikations** \> **Bezeichnungen**aus.</span><span class="sxs-lookup"><span data-stu-id="51eb9-142">On the Azure Information Protection dashboard, select **Classifications** \> **Labels**.</span></span> <br/><span data-ttu-id="51eb9-143">![Standard Beschriftungen für Azure Information Protection.](media/AIPLabels.png)</span><span class="sxs-lookup"><span data-stu-id="51eb9-143">![Standard labels for Azure Information Protection.](media/AIPLabels.png)</span></span>

2. <span data-ttu-id="51eb9-144">Sie können eine beliebige Beschriftung auswählen, um Optionen anzuzeigen, Sie können den Anzeigenamen, die Farben usw. ändern.</span><span class="sxs-lookup"><span data-stu-id="51eb9-144">You can choose any label to view options, you can change the display name, colors, etc.</span></span>
 
3. <span data-ttu-id="51eb9-145">Weitere Informationen finden Sie unter [ändern und Erstellen neuer Bezeichnungen](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) , wenn Sie eigene erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="51eb9-145">See  [Modify and create new labels](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step2) if you want to create your own.</span></span> 

### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="51eb9-146">Manuelles Installieren des Azure Information Protection-Clients</span><span class="sxs-lookup"><span data-stu-id="51eb9-146">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="51eb9-147">So installieren Sie den AIP-Client manuell:</span><span class="sxs-lookup"><span data-stu-id="51eb9-147">To manually install the AIP client:</span></span>

1. <span data-ttu-id="51eb9-148">Laden Sie **AzInfoProtection. exe** aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018)herunter.</span><span class="sxs-lookup"><span data-stu-id="51eb9-148">Download **AzInfoProtection.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="51eb9-149">Sie können überprüfen, ob die Installation erfolgreich war, indem Sie ein Word-Dokument anzeigen und sicherstellen, dass die Option **schützen** auf der Registerkarte **Start** zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="51eb9-149">You can verify that the installation worked by viewing a Word document and making sure that the **Protect** option is available on the **Home** tab.</span></span> <br/><span data-ttu-id="51eb9-150">![Dropdown-Registerkarte Schutz in einem Word-Dokument.](media/Word_Protect.png)</span><span class="sxs-lookup"><span data-stu-id="51eb9-150">![Protection tab drop-down in a Word document.](media/Word_Protect.png)</span></span>

<span data-ttu-id="51eb9-151">Weitere Informationen finden Sie unter [Installieren des Clients](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="51eb9-151">For more information see, [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
