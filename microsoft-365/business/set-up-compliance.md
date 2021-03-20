---
title: Erhöhen des Bedrohungsschutzes für Microsoft 365 Business Premium
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Richten Sie Compliancefeatures ein, um Datenverluste zu verhindern und die vertraulichen Informationen Ihrer und Ihrer Kunden zu schützen.
ms.openlocfilehash: e210787718025c5df29af8d4a2283291dcecc2a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912528"
---
# <a name="set-up-compliance-features"></a><span data-ttu-id="953de-103">Einrichten von Compliancefeatures</span><span class="sxs-lookup"><span data-stu-id="953de-103">Set up compliance features</span></span>

<span data-ttu-id="953de-104">Ihr Microsoft 365 Business Premium verfügt über Features zum Schutz Ihrer Daten und Geräte und hilft Ihnen, die vertraulichen Informationen Ihrer Kunden und Ihrer Kunden zu schützen.</span><span class="sxs-lookup"><span data-stu-id="953de-104">Your Microsoft 365 Business Premium comes with features to protect your data and devices, and help you keep your and your customers' sensitive information secure.</span></span>

## <a name="set-up-dlp-features"></a><span data-ttu-id="953de-105">Einrichten von DLP-Features</span><span class="sxs-lookup"><span data-stu-id="953de-105">Set up DLP features</span></span>

<span data-ttu-id="953de-106">Ein Beispiel zum Einrichten einer Richtlinie zum Schutz vor Verlust personenbezogener Daten finden Sie unter Erstellen einer [DLP-Richtlinie](../compliance/create-a-dlp-policy-from-a-template.md) aus einer Vorlage.</span><span class="sxs-lookup"><span data-stu-id="953de-106">See [Create a DLP policy from a template](../compliance/create-a-dlp-policy-from-a-template.md) for an example on how to set up a policy to protect against protect loss of personal data.</span></span> 
  
<span data-ttu-id="953de-107">DLP enthält viele einsatzbereite Richtlinienvorlagen für viele verschiedene Locales.</span><span class="sxs-lookup"><span data-stu-id="953de-107">DLP comes with many ready-to-use policy templates for many different locales.</span></span> <span data-ttu-id="953de-108">Beispiel: Australische Finanzdaten, Canada Personal Information Act, U.S. Financial Data und so weiter.</span><span class="sxs-lookup"><span data-stu-id="953de-108">For example, Australia Financial Data, Canada Personal Information Act, U.S. Financial Data, and so on.</span></span> <span data-ttu-id="953de-109">Eine vollständige Liste finden Sie unter Was [die DLP-Richtlinienvorlagen](../compliance/what-the-dlp-policy-templates-include.md) enthalten.</span><span class="sxs-lookup"><span data-stu-id="953de-109">See [What the DLP policy templates include](../compliance/what-the-dlp-policy-templates-include.md) for a full list.</span></span> <span data-ttu-id="953de-110">Alle diese Vorlagen können ähnlich wie im Beispiel für piI-Vorlagen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="953de-110">All of these templates can be enabled similar to the PII template example.</span></span> 
  
## <a name="set-up-email-retention-with-exchange-online-archiving"></a><span data-ttu-id="953de-111">Einrichten der E-Mail-Aufbewahrung mit Exchange Online-Archivierung</span><span class="sxs-lookup"><span data-stu-id="953de-111">Set up email retention with Exchange Online Archiving</span></span>

 <span data-ttu-id="953de-112">**Exchange Online-Archivierung** Lizenzfeatures helfen bei der Aufrechterhaltung von Compliance- und behördlichen Standards, indem E-Mail-Inhalte für eDiscovery beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="953de-112">**Exchange Online Archiving** license features help maintain compliance and regulatory standards by preserving email content for eDiscovery.</span></span> <span data-ttu-id="953de-113">Es hilft auch, Ihr Risiko zu reduzieren, wenn eine Klage vorlag, und bietet eine Möglichkeit, Daten nach einer Sicherheitsverletzung oder wenn Sie gelöschte Elemente wiederherstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="953de-113">It also helps reduce your risk if there is a lawsuit, and provides a way to recover data after a security breach or when you need to recover deleted items.</span></span> <span data-ttu-id="953de-114">Sie können das Verfahrensverfahren verwenden, um alle Inhalte eines Benutzers zu erhalten, oder Aufbewahrungsrichtlinien verwenden, um die Aufbewahrungsrichtlinien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="953de-114">You can use litigation hold to preserve all of a user's content, or use retention policies to customize what you want to preserve.</span></span>
  
<span data-ttu-id="953de-115">**Halterecht für Rechtsstreitigkeiten:** Sie können alle Postfachinhalte, einschließlich gelöschter Elemente, beibehalten, indem Sie das gesamte Postfach eines Benutzers in einem Rechtsstreit zurückhalten.</span><span class="sxs-lookup"><span data-stu-id="953de-115">**Litigation hold:** You can preserve all mailbox content including deleted items by putting a user's entire mailbox on litigation hold.</span></span> 
    
<span data-ttu-id="953de-116">So platzieren Sie ein Postfach in einem Rechtsstreit im Admin Center:</span><span class="sxs-lookup"><span data-stu-id="953de-116">To place a mailbox on litigation hold, in the Admin center:</span></span>
    
1. <span data-ttu-id="953de-117">Wechseln Sie im linken Navigations navi zu **Benutzer** \> **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="953de-117">In the left nav, go to **Users** \> **Active users**.</span></span>
    
2. <span data-ttu-id="953de-118">Wählen Sie einen Benutzer aus, dessen Postfach Sie in einem Prozesssicherungsverfahren platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="953de-118">Select a user whose mailbox you want to place on litigation hold.</span></span> <span data-ttu-id="953de-119">Erweitern Sie im Benutzerbereich **E-Mail-Einstellungen,** und wählen Sie neben **Weitere Einstellungen** die Option **Exchange-Eigenschaften bearbeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="953de-119">In the user pane, expand **Mail settings**, and next to **More settings**, choose **Edit Exchange properties**.</span></span>
    
3. <span data-ttu-id="953de-120">Wählen Sie auf der Postfachseite für den Benutzer \*\* Postfachfunktionen \*\* im linken Navigationsgerät aus, und wählen Sie dann den Link Aktivieren **unter** **Rechtsstreitigkeiten aus.**</span><span class="sxs-lookup"><span data-stu-id="953de-120">On the mailbox page for the user, choose \*\* mailbox features \*\* on the left nav, and then choose the **Enable** link under **Litigation hold**.</span></span>
    
4. <span data-ttu-id="953de-121">Im Dialogfeld **Prozesssicherungsverfahren** können Sie die Dauer des Prozesssicherungsverfahren im Feld Dauer des **Rechtsstreitigkeiten-Haltebereichs** angeben.</span><span class="sxs-lookup"><span data-stu-id="953de-121">In the **litigation hold** dialog box, you can specify the litigation hold duration in the **Litigation hold duration** field.</span></span> <span data-ttu-id="953de-122">Lassen Sie das Feld leer, wenn Sie einen unendlichen Haltebereich platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="953de-122">Leave the field empty if you want to place an infinite hold.</span></span> <span data-ttu-id="953de-123">Sie können auch Notizen hinzufügen und den Postfachbesitzer zu einer Website führen, auf der Sie möglicherweise weitere Informationen zum Prozesssicherungsverfahren erläutern müssen.</span><span class="sxs-lookup"><span data-stu-id="953de-123">You can also add notes and direct the mailbox owner to a website you might have to explain more about the litigation hold.</span></span> <span data-ttu-id="953de-124">\>**Speichern** Sie .</span><span class="sxs-lookup"><span data-stu-id="953de-124">\> **Save**.</span></span>
    
<span data-ttu-id="953de-125">**Aufbewahrung:** Sie können beispielsweise angepasste Aufbewahrungsrichtlinien aktivieren, um inhalte für einen bestimmten Zeitraum zu erhalten oder Inhalte am Ende des Aufbewahrungszeitraums dauerhaft zu löschen.</span><span class="sxs-lookup"><span data-stu-id="953de-125">**Retention:** You can enable customized retention policies, for example, to preserve for a specific amount of time or delete content permanently at the end of the retention period.</span></span> <span data-ttu-id="953de-126">Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](../compliance/retention.md).</span><span class="sxs-lookup"><span data-stu-id="953de-126">To learn more, see [Overview of retention policies](../compliance/retention.md).</span></span>

## <a name="set-up-sensitivity-labels"></a><span data-ttu-id="953de-127">Einrichten von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="953de-127">Set up Sensitivity labels</span></span>

<span data-ttu-id="953de-128">Vertraulichkeitsbezeichnungen sind in Azure Information Protection (AIP) Plan 1 enthalten und helfen Ihnen, Ihre Dokumente und E-Mails durch Anwenden von Bezeichnungen zu klassifizieren und optional zu schützen.</span><span class="sxs-lookup"><span data-stu-id="953de-128">Sensitivity labels come with Azure Information Protection (AIP) Plan 1, and help you classify, and optionally protect your documents and emails, by applying labels.</span></span> <span data-ttu-id="953de-129">Bezeichnungen können automatisch von Administratoren angewendet werden, die Regeln und Bedingungen definieren, manuell von Benutzern oder mithilfe einer Kombination, in der Benutzern Empfehlungen gegeben werden.</span><span class="sxs-lookup"><span data-stu-id="953de-129">Labels can be applied automatically by administrators who define rules and conditions, manually by users, or by using a combination where users are given recommendations.</span></span>

<span data-ttu-id="953de-130">Zum Einrichten von Vertraulichkeitsbezeichnungen zeigen Sie video [zum Erstellen und Verwalten von Vertraulichkeitsbezeichnungen](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) an.</span><span class="sxs-lookup"><span data-stu-id="953de-130">To set up Sensitivity labels, view [create and manage sensitivity labels](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) video.</span></span>



### <a name="install-the-azure-information-protection-client-manually"></a><span data-ttu-id="953de-131">Manuelles Installieren des Azure Information Protection-Clients</span><span class="sxs-lookup"><span data-stu-id="953de-131">Install the Azure Information Protection client manually</span></span>

<span data-ttu-id="953de-132">So installieren Sie den AIP-Client manuell:</span><span class="sxs-lookup"><span data-stu-id="953de-132">To manually install the AIP client:</span></span>

1. <span data-ttu-id="953de-133">Laden **AzinfoProtection_UL.exe** von [Microsoft Download Center herunter.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="953de-133">Download **AzinfoProtection_UL.exe** from [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>
 
2. <span data-ttu-id="953de-134">Sie können überprüfen, ob die Installation funktioniert hat,  indem Sie ein Word-Dokument anzeigen und sicherstellen, dass die Option Vertraulichkeit auf der Registerkarte **Start verfügbar** ist.</span><span class="sxs-lookup"><span data-stu-id="953de-134">You can verify that the installation worked by viewing a Word document and making sure that the **Sensitivity** option is available on the **Home** tab.</span></span>
<br/><span data-ttu-id="953de-135">![Dropdownliste "Registerkarte Schutz" in einem Word-Dokument.](../media/word-sensitivity.png)</span><span class="sxs-lookup"><span data-stu-id="953de-135">![Protection tab drop-down in a Word document.](../media/word-sensitivity.png)</span></span>

<span data-ttu-id="953de-136">Weitere Informationen finden Sie unter [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span><span class="sxs-lookup"><span data-stu-id="953de-136">For more information, see [Install the client](/azure/information-protection/infoprotect-tutorial-step3).</span></span>