---
title: Erhöhter Bedrohungsschutz für Microsoft 365 Business Premium
f1.keywords:
- NOCSH
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
- OKR_SMB_M365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
description: Richten Sie Compliance-Features ein, um Datenverlust zu verhindern und um sicherzustellen, dass die vertraulichen Informationen Ihrer Kunden geschützt sind.
ms.openlocfilehash: e0d853223c7e6f455cba6e68ad173b137992d863
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635122"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="df6be-103">Einrichten von Compliancefeatures</span><span class="sxs-lookup"><span data-stu-id="df6be-103">Set up compliance features</span></span>

<span data-ttu-id="df6be-104">Ihr Microsoft 365 Business Premium verfügt über Features zum Schutz Ihrer Daten und Geräte und hilft Ihnen dabei, die vertraulichen Informationen Ihrer Kunden sicher zu halten.</span><span class="sxs-lookup"><span data-stu-id="df6be-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="df6be-105">Einrichten von DLP-Features</span><span class="sxs-lookup"><span data-stu-id="df6be-105">Set up DLP features</span></span>

<span data-ttu-id="df6be-106">Ein Beispiel zum Einrichten einer Richtlinie zum Schutz gegen personenbezogene Informationen (PII) finden Sie unter [Erstellen einer DLP-Richtlinie aus einer Vorlage](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) .</span><span class="sxs-lookup"><span data-stu-id="df6be-106">See [Create a DLP policy from a template](https://support.office.com/article/59414438-99f5-488b-975c-5023f2254369) for an example on how to set up a policy to protect against personally identifiable information (PII).</span></span> 
  
<span data-ttu-id="df6be-107">DLP verfügt über viele vorgefertigte Richtlinienvorlagen für viele unterschiedliche Gebietsschemas.</span><span class="sxs-lookup"><span data-stu-id="df6be-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="df6be-108">Beispiel: Australien Financial Data, Canada Personal Information Act, US Financial Data, etc.</span><span class="sxs-lookup"><span data-stu-id="df6be-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="df6be-109">Eine vollständige Liste finden Sie unter [was die DLP-Richtlinienvorlagen enthalten](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) .</span><span class="sxs-lookup"><span data-stu-id="df6be-109">See [What the DLP policy templates include](https://support.office.com/article/c2e588d3-8f4f-4937-a286-8c399f28953a) for a full list.</span></span> <span data-ttu-id="df6be-110">Alle diese Vorlagen können ähnlich wie beim PII-Vorlagenbeispiel aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="df6be-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="df6be-111">Einrichten der e-Mail-Aufbewahrung mit Exchange Online Archivierung</span><span class="sxs-lookup"><span data-stu-id="df6be-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="df6be-112">**Exchange Online Archivierungs** Lizenz Funktionen unterstützen die Einhaltung von Vorschriften und behördlichen Vorgaben durch die Beibehaltung von e-Mail-Inhalten für eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="df6be-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="df6be-113">Es hilft auch, das Risiko zu verringern, wenn es einen Prozess gibt, und bietet eine Möglichkeit zum Wiederherstellen von Daten nach einer Sicherheitsverletzung oder wenn Sie gelöschte Elemente wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="df6be-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="df6be-114">Sie können das Beweissicherungsverfahren verwenden, um alle Inhalte eines Benutzers beizubehalten, oder Sie verwenden Aufbewahrungsrichtlinien, um die beizubehaltenden Elemente anzupassen.</span><span class="sxs-lookup"><span data-stu-id="df6be-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="df6be-115">**Beweissicherungsverfahren:** Sie können alle Postfachinhalte einschließlich gelöschter Elemente beibehalten, indem Sie das gesamte Postfach eines Benutzers in das Beweissicherungsverfahren versetzen.</span><span class="sxs-lookup"><span data-stu-id="df6be-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="df6be-116">So legen Sie ein Postfach für das Beweissicherungsverfahren im Admin Center ab:</span><span class="sxs-lookup"><span data-stu-id="df6be-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="df6be-117">Navigieren Sie im linken Navigationsbereich zu **Benutzer** \> **aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="df6be-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="df6be-118">Wählen Sie einen Benutzer aus, dessen Postfach Sie in das Beweissicherungsverfahren einordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="df6be-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="df6be-119">Erweitern Sie im Bereich Benutzer den Eintrag **e-Mail-Einstellungen**, und klicken Sie neben **Weitere Einstellungen**auf **Exchange-Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="df6be-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="df6be-120">Wählen Sie auf der Seite Postfachbenutzer im linken Navigationsbereich die Option \* \* Postfachfeatures \* \* aus, und wählen Sie dann den Link **aktivieren** unter **Beweissicherungsverfahren**aus.</span><span class="sxs-lookup"><span data-stu-id="df6be-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="df6be-121">Im Dialogfeld **Beweissicherungsverfahren** können Sie die Dauer des beweissicherungsverfahrens im Feld **Dauer** des beweissicherungsverfahrens angeben.</span><span class="sxs-lookup"><span data-stu-id="df6be-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="df6be-122">Lassen Sie das Feld leer, wenn Sie einen unbegrenzten Haltebereich platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="df6be-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="df6be-123">Sie können auch Notizen hinzufügen und den Postfachbesitzer zu einer Website weiterleiten, auf der Sie möglicherweise mehr über das Beweissicherungsverfahren erklären müssen.</span><span class="sxs-lookup"><span data-stu-id="df6be-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="df6be-124">\>**Save**.</span><span class="sxs-lookup"><span data-stu-id="df6be-124">\> **Save**.</span></span>
    
<span data-ttu-id="df6be-125">**Aufbewahrung:** Sie können benutzerdefinierte Aufbewahrungsrichtlinien aktivieren, beispielsweise um eine bestimmte Zeitspanne beizubehalten oder Inhalte dauerhaft am Ende des Aufbewahrungszeitraums zu löschen.</span><span class="sxs-lookup"><span data-stu-id="df6be-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="df6be-126">Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span><span class="sxs-lookup"><span data-stu-id="df6be-126">To learn more, see [Overview of retention policies](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="df6be-127">Einrichten von Sensitivitäts Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="df6be-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="df6be-128">Die Sensitivitäts Bezeichnungen werden mit dem Azure Information Protection (AIP)-Plan 1 geliefert und helfen Ihnen, Ihre Dokumente und e-Mails zu klassifizieren und optional zu schützen, indem Sie Bezeichnungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="df6be-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="df6be-129">Bezeichnungen können automatisch von Administratoren angewendet werden, die Regeln und Bedingungen manuell von Benutzern definieren, oder indem Sie eine Kombination verwenden, in der Benutzern Empfehlungen gegeben werden.</span><span class="sxs-lookup"><span data-stu-id="df6be-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="df6be-130">Um Sensitivitäts Bezeichnungen einzurichten, zeigen Sie Video zu [Erstellen und Verwalten von Sensitivitäts Bezeichnungen](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) an.</span><span class="sxs-lookup"><span data-stu-id="df6be-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="df6be-131">Manuelles Installieren des Azure Information Protection-Clients</span><span class="sxs-lookup"><span data-stu-id="df6be-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="df6be-132">So installieren Sie den AIP-Client manuell:</span><span class="sxs-lookup"><span data-stu-id="df6be-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="df6be-133">Laden Sie **AzinfoProtection_UL. exe** aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018)herunter.</span><span class="sxs-lookup"><span data-stu-id="df6be-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="df6be-134">Sie können überprüfen, ob die Installation erfolgreich war, indem Sie ein Word-Dokument anzeigen und sicherstellen, dass die Option **Vertraulichkeit** auf der Registerkarte **Start** verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="df6be-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="df6be-135">![Dropdown-Registerkarte Schutz in einem Word-Dokument.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="df6be-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="df6be-136">Weitere Informationen finden Sie unter [Installieren des Clients](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="df6be-136">For more information, see [Install the client](https://docs.microsoft.com/azure/information-protection/infoprotect-tutorial-step3).</span></span>
