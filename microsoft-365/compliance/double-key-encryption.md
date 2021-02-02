---
title: Double Key Encryption (DKE)
description: DKE ermöglicht es Ihnen, hochgradig vertrauliche Daten zu schützen und gleichzeitig die vollständige Kontrolle über Ihren Schlüssel zu erhalten.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c10a10a5922755db2c901137c3dff8acee5b8445
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066858"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="ba098-103">Verschlüsselung mit Doppelschlüsseln für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ba098-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="ba098-104">*Gilt für: Verschlüsselung mit Doppelschlüsseln für Microsoft 365, [Microsoft 365 Compliance,](https://www.microsoft.com/microsoft-365/business/compliance-management) [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="ba098-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="ba098-105">*Anweisungen für: [Azure Information Protection Unified Labeling Client für Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="ba098-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="ba098-106">*Dienstbeschreibung für: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="ba098-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="ba098-107">Die Doppelschlüsselverschlüsselung (Double Key Encryption, DKE) verwendet zwei Schlüssel für den Zugriff auf geschützte Inhalte.</span><span class="sxs-lookup"><span data-stu-id="ba098-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="ba098-108">Microsoft speichert einen Schlüssel in Microsoft Azure, und Sie halten den anderen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ba098-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="ba098-109">Sie behalten die vollständige Kontrolle über einen Ihrer Schlüssel mithilfe des Diensts für die Verschlüsselung von Doppelschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ba098-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="ba098-110">Sie wenden Den Schutz mithilfe des Azure Information Protection einheitlichen Bezeichnungsclients auf Ihre hochgradig vertraulichen Inhalte an.</span><span class="sxs-lookup"><span data-stu-id="ba098-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="ba098-111">Die Verschlüsselung mit Doppelschlüssel unterstützt sowohl Cloud- als auch lokale Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="ba098-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="ba098-112">Diese Bereitstellungen tragen dazu bei, dass verschlüsselte Daten undurchsichtig bleiben, unabhängig davon, wo Sie die geschützten Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="ba098-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="ba098-113">Weitere Informationen zu den standardmäßigen, cloudbasierten Mandantenstammschlüsseln finden Sie unter Planung und Implementierung Ihres [Azure Information Protection-Mandantenschlüssels.](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)</span><span class="sxs-lookup"><span data-stu-id="ba098-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="ba098-114">Wann Ihre Organisation DKE übernehmen soll</span><span class="sxs-lookup"><span data-stu-id="ba098-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="ba098-115">Die Verschlüsselung mit doppelschlüsseligem Schlüssel ist für Ihre vertraulichsten Daten vorgesehen, die den strengsten Schutzanforderungen unterliegen.</span><span class="sxs-lookup"><span data-stu-id="ba098-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="ba098-116">DKE ist nicht für alle Daten vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ba098-116">DKE is not intended for all data.</span></span> <span data-ttu-id="ba098-117">Im Allgemeinen verwenden Sie die Doppelschlüsselverschlüsselung, um nur einen kleinen Teil der Gesamtdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="ba098-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="ba098-118">Sie sollten sorgfältig daran gehen, die richtigen Daten zu identifizieren, die mit dieser Lösung vor der Bereitstellung zu abdecken sind.</span><span class="sxs-lookup"><span data-stu-id="ba098-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="ba098-119">In einigen Fällen müssen Sie möglicherweise Ihren Umfang einengt und andere Lösungen für die meisten Daten verwenden, z. B. Microsoft Information Protection mit von Microsoft verwalteten Schlüsseln oder BYOK.</span><span class="sxs-lookup"><span data-stu-id="ba098-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="ba098-120">Diese Lösungen sind ausreichend für Dokumente, die nicht erweiterten Schutz- und behördlichen Anforderungen unterliegen.</span><span class="sxs-lookup"><span data-stu-id="ba098-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="ba098-121">Darüber hinaus können Sie mit diesen Lösungen die leistungsstärksten Office 365-Dienste verwenden. Dienste, die Sie nicht mit DKE-verschlüsselten Inhalten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ba098-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="ba098-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-122">For example:</span></span>

- <span data-ttu-id="ba098-123">Transportregeln, einschließlich Ansoftware und Spam, die einen Einblick in die Anlage erfordern</span><span class="sxs-lookup"><span data-stu-id="ba098-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="ba098-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="ba098-124">Microsoft Delve</span></span>
- <span data-ttu-id="ba098-125">eDiscovery</span><span class="sxs-lookup"><span data-stu-id="ba098-125">eDiscovery</span></span>
- <span data-ttu-id="ba098-126">Inhaltssuche und -indizierung</span><span class="sxs-lookup"><span data-stu-id="ba098-126">Content search and indexing</span></span>
- <span data-ttu-id="ba098-127">Office Web Apps einschließlich der Funktion für die gemeinsamen Dokumentierung</span><span class="sxs-lookup"><span data-stu-id="ba098-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="ba098-128">Alle externen Anwendungen oder Dienste, die nicht über das MIP SDK in DKE integriert sind, können keine Aktionen für die verschlüsselten Daten ausführen.</span><span class="sxs-lookup"><span data-stu-id="ba098-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="ba098-129">Das Microsoft Information Protection SDK 1.7+ unterstützt die Verschlüsselung mit Doppelschlüsseln. Anwendungen, die in unser SDK integriert sind, können mit ausreichenden Berechtigungen und Integrationen über diese Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="ba098-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="ba098-130">Es wird empfohlen, dass Organisationen die Microsoft Information Protection-Funktionen (Klassifizierung und Bezeichnung) verwenden, um die meisten ihrer vertraulichen Daten zu schützen, und DKE nur für ihre unternehmenskritischen Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba098-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="ba098-131">Die Verschlüsselung von Doppelschlüsseln ist für vertrauliche Daten in stark regulierten Branchen wie Finanzdienstleistungen und Gesundheitswesen relevant.</span><span class="sxs-lookup"><span data-stu-id="ba098-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="ba098-132">Wenn für Ihre Organisationen eine der folgenden Anforderungen erfüllt ist, können Sie DKE verwenden, um Ihre Inhalte zu schützen:</span><span class="sxs-lookup"><span data-stu-id="ba098-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="ba098-133">Sie möchten sicherstellen, *dass unter* allen Umständen nur Sie geschützte Inhalte entschlüsseln können.</span><span class="sxs-lookup"><span data-stu-id="ba098-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="ba098-134">Sie möchten nicht, dass Microsoft selbst Zugriff auf geschützte Daten hat.</span><span class="sxs-lookup"><span data-stu-id="ba098-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="ba098-135">Sie haben gesetzliche Vorschriften, um Schlüssel innerhalb einer geografischen Grenze zu halten.</span><span class="sxs-lookup"><span data-stu-id="ba098-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="ba098-136">Alle Schlüssel, die Sie für die Datenverschlüsselung und -entschlüsselung beibehalten, werden in Ihrem Rechenzentrum verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ba098-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="ba098-137">System- und Lizenzierungsanforderungen für DKE</span><span class="sxs-lookup"><span data-stu-id="ba098-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="ba098-138">**Die Verschlüsselung mit Doppelschlüsseln für Microsoft 365** ist in Microsoft 365 E5 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba098-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="ba098-139">Wenn Sie keine Microsoft 365 E5-Lizenz haben, können Sie sich für eine Testversion [registrieren.](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="ba098-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="ba098-140">Weitere Informationen zu diesen Lizenzen finden Sie unter [Microsoft 365-Lizenzierungsanleitungen für](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)& Compliance.</span><span class="sxs-lookup"><span data-stu-id="ba098-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="ba098-141">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="ba098-141">**Azure Information Protection**.</span></span> <span data-ttu-id="ba098-142">DKE arbeitet mit Vertraulichkeitsbezeichnungen und erfordert Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="ba098-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="ba098-143">DkE-Vertraulichkeitsbezeichnungen werden Endbenutzern über das Menüband für Vertraulichkeit in Office Desktop Apps zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="ba098-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="ba098-144">Installieren Sie diese erforderlichen Komponenten auf jedem Clientcomputer, auf dem Sie geschützte Dokumente schützen und verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ba098-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="ba098-145">**Microsoft Office Apps für Unternehmen** Version \*.12711 oder höher (Desktopversionen von Word, PowerPoint und Excel) unter Windows.</span><span class="sxs-lookup"><span data-stu-id="ba098-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="ba098-146">**Azure Information Protection Unified Labeling Client,** Version 2.7.93.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="ba098-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="ba098-147">Laden Sie den Unified Labeling-Client aus dem Microsoft Download Center herunter, und [installieren Sie den Client.](https://www.microsoft.com/download/details.aspx?id=53018)</span><span class="sxs-lookup"><span data-stu-id="ba098-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="ba098-148">Unterstützte Umgebungen zum Speichern und Anzeigen von DKE-geschützten Inhalten</span><span class="sxs-lookup"><span data-stu-id="ba098-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="ba098-149">**Unterstützte Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="ba098-149">**Supported applications**.</span></span> <span data-ttu-id="ba098-150">[Microsoft 365 Apps for Enterprise Clients](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) unter Windows, einschließlich Word, Excel und PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="ba098-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="ba098-151">**Onlineinhaltsunterstützung**.</span><span class="sxs-lookup"><span data-stu-id="ba098-151">**Online content support**.</span></span> <span data-ttu-id="ba098-152">Online gespeicherte Dokumente und Dateien in Microsoft SharePoint und OneDrive for Business werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ba098-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="ba098-153">Sie können verschlüsselte Inhalte per E-Mail freigeben, verschlüsselte Dokumente und Dateien können jedoch nicht online angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ba098-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="ba098-154">Stattdessen müssen Sie geschützte Inhalte mithilfe der Desktop-Apps auf Dem lokalen Computer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ba098-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="ba098-155">Übersicht über die Bereitstellung von DKE</span><span class="sxs-lookup"><span data-stu-id="ba098-155">Overview of deploying DKE</span></span>

<span data-ttu-id="ba098-156">Führen Sie die folgenden allgemeinen Schritte zum Einrichten von DKE aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="ba098-157">Nachdem Sie diese Schritte abgeschlossen haben, können Ihre Endbenutzer Ihre hochgradig vertraulichen Daten mit der Verschlüsselung mit doppelschlüsseligem Schlüssel schützen.</span><span class="sxs-lookup"><span data-stu-id="ba098-157">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="ba098-158">Bereitstellen des DKE-Diensts, wie in diesem Artikel beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ba098-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="ba098-159">Erstellen Sie eine Bezeichnung mit doppelter Schlüsselverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="ba098-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="ba098-160">Navigieren Sie zum Informationsschutz im [Microsoft 365 Compliance Center,](https://compliance.microsoft.com) und erstellen Sie eine neue Bezeichnung mit doppelter Schlüsselverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="ba098-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="ba098-161">Weitere Informationen finden Sie unter Einschränken [des Zugriffs auf Inhalte mithilfe von Vertraulichkeitsbezeichnungen zum Anwenden von Verschlüsselung.](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)</span><span class="sxs-lookup"><span data-stu-id="ba098-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="ba098-162">Verwenden Sie Doppelschlüsselverschlüsselungsbezeichnungen.</span><span class="sxs-lookup"><span data-stu-id="ba098-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="ba098-163">Schützen Sie Daten, indem Sie die Bezeichnung "Verschlüsselte Doppelschlüssel" im Menüband "Vertraulichkeit" in Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="ba098-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="ba098-164">Es gibt mehrere Möglichkeiten, einige der Schritte zum Bereitstellen der Doppelschlüsselverschlüsselung zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="ba098-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="ba098-165">Dieser Artikel enthält ausführliche Anweisungen, damit weniger erfahrene Administratoren den Dienst erfolgreich bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="ba098-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="ba098-166">Wenn Sie damit gut zu tun haben, können Sie ihre eigenen Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba098-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="ba098-167">Bereitstellen von DKE</span><span class="sxs-lookup"><span data-stu-id="ba098-167">Deploy DKE</span></span>

<span data-ttu-id="ba098-168">Dieser Artikel und das Bereitstellungsvideo verwenden Azure als Bereitstellungsziel für den DKE-Dienst.</span><span class="sxs-lookup"><span data-stu-id="ba098-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="ba098-169">Wenn Sie an einem anderen Speicherort bereitstellen, müssen Sie Ihre eigenen Werte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ba098-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="ba098-170">Sehen Sie [sich das Video zur Bereitstellung der](https://youtu.be/vDWfHN_kygg) Doppelschlüsselverschlüsselung an, um eine schrittweise Übersicht über die Konzepte in diesem Artikel zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ba098-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="ba098-171">Das Video dauert etwa 18 Minuten.</span><span class="sxs-lookup"><span data-stu-id="ba098-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="ba098-172">Führen Sie die folgenden allgemeinen Schritte aus, um die Doppelschlüsselverschlüsselung für Ihre Organisation zu einrichten.</span><span class="sxs-lookup"><span data-stu-id="ba098-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="ba098-173">Installieren der erforderlichen Software für den DKE-Dienst</span><span class="sxs-lookup"><span data-stu-id="ba098-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="ba098-174">Klonen des GitHub-Repositorys für die Doppelschlüsselverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ba098-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="ba098-175">Ändern von Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ba098-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="ba098-176">Generieren von Testschlüsseln</span><span class="sxs-lookup"><span data-stu-id="ba098-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="ba098-177">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ba098-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="ba098-178">Bereitstellen des DKE-Diensts und Veröffentlichen des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="ba098-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="ba098-179">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ba098-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="ba098-180">Registrieren des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="ba098-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="ba098-181">Erstellen von Vertraulichkeitsbezeichnungen mithilfe von DKE</span><span class="sxs-lookup"><span data-stu-id="ba098-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="ba098-182">Aktivieren von DKE in Ihrem Client</span><span class="sxs-lookup"><span data-stu-id="ba098-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="ba098-183">Migrieren geschützter Dateien von den Bezeichnungen HYOK zu den DKE-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ba098-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="ba098-184">Wenn Sie fertig sind, können Sie Dokumente und Dateien mithilfe von DKE verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ba098-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="ba098-185">Weitere Informationen finden Sie unter [Anwenden von Vertraulichkeitsbezeichnungen auf Ihre Dateien und E-Mails in Office.](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)</span><span class="sxs-lookup"><span data-stu-id="ba098-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="ba098-186">Installieren der erforderlichen Software für den DKE-Dienst</span><span class="sxs-lookup"><span data-stu-id="ba098-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="ba098-187">Installieren Sie diese erforderlichen Komponenten auf dem Computer, auf dem Sie den DKE-Dienst installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ba098-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="ba098-188">**.NET Core 3.1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="ba098-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="ba098-189">Laden Sie das SDK von [Download .NET Core 3.1 herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="ba098-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="ba098-190">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="ba098-190">**Visual Studio Code**.</span></span> <span data-ttu-id="ba098-191">Laden Visual Studio Code von [https://code.visualstudio.com/](https://code.visualstudio.com) herunter.</span><span class="sxs-lookup"><span data-stu-id="ba098-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="ba098-192">Führen Sie nach der Installation Visual Studio Code aus, und wählen Sie **"Ansichtserweiterungen"** \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="ba098-193">Installieren Sie diese Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="ba098-193">Install these extensions.</span></span>

- <span data-ttu-id="ba098-194">C# für Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ba098-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="ba098-195">NuGet Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="ba098-195">NuGet Package Manager</span></span>

<span data-ttu-id="ba098-196">**Git-Ressourcen**.</span><span class="sxs-lookup"><span data-stu-id="ba098-196">**Git resources**.</span></span> <span data-ttu-id="ba098-197">Laden Sie eine der folgenden Komponenten herunter, und installieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="ba098-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="ba098-198">Git</span><span class="sxs-lookup"><span data-stu-id="ba098-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="ba098-199">GitHub Desktop</span><span class="sxs-lookup"><span data-stu-id="ba098-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="ba098-200">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="ba098-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="ba098-201">**OpenSSL** Sie müssen [OpenSSL installiert haben,](https://slproweb.com/products/Win32OpenSSL.html) um [Testschlüssel zu generieren,](#generate-test-keys) nachdem Sie DKE bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ba098-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="ba098-202">Stellen Sie sicher, dass Sie es korrekt über den Pfad der Umgebungsvariablen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ba098-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="ba098-203">Weitere Informationen finden Sie unter "Hinzufügen des Installationsverzeichnisses zu [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) PATH".</span><span class="sxs-lookup"><span data-stu-id="ba098-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="ba098-204">Klonen des DKE-GitHub-Repositorys</span><span class="sxs-lookup"><span data-stu-id="ba098-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="ba098-205">Microsoft stellt die DKE-Quelldateien in einem GitHub-Repository bereit.</span><span class="sxs-lookup"><span data-stu-id="ba098-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="ba098-206">Sie klonen das Repository, um das Projekt zur Verwendung in Ihrer Organisation lokal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba098-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="ba098-207">Das DKE-GitHub-Repository befindet sich unter [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="ba098-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="ba098-208">Die folgenden Anweisungen sind für unerfahrene Git- oder Visual Studio Codebenutzer vorgesehen:</span><span class="sxs-lookup"><span data-stu-id="ba098-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="ba098-209">Wechseln Sie in Ihrem Browser zu: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="ba098-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="ba098-210">Wählen Sie auf der rechten Seite des Bildschirms **Code aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="ba098-211">In Ihrer Version der Benutzeroberfläche wird möglicherweise eine **Klon- oder Downloadschaltfläche** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba098-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="ba098-212">Wählen Sie dann in der angezeigten Dropdownliste das Kopiersymbol aus, um die URL in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="ba098-213">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-213">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba098-214">![Klonen des Dienstrepositorys für die Verschlüsselung mit Doppelschlüsseln von GitHub](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="ba098-214">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="ba098-215">Wählen Visual Studio Code "Befehlspalette  \> **anzeigen" und** dann **"Git: Klonen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="ba098-216">Um zu der Option in der Liste zu springen, beginnen Sie mit der Eingabe, um die Einträge zu filtern, und wählen Sie sie dann aus der `git: clone` Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="ba098-217">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-217">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba098-218">![Visual Studio Code GIT:Clone-Option](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="ba098-218">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="ba098-219">Fügen Sie in das Textfeld die URL ein, die Sie aus Git kopiert haben, und wählen Sie **"Clone" aus GitHub aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="ba098-220">Navigieren Sie **im angezeigten** Dialogfeld "Ordner auswählen" zu einem Speicherort, und wählen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="ba098-221">Wählen Sie an der Eingabeaufforderung **"Öffnen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="ba098-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span><span class="sxs-lookup"><span data-stu-id="ba098-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="ba098-223">Die Verzweigung sollte z. B. haupt **sein.**</span><span class="sxs-lookup"><span data-stu-id="ba098-223">For example,  The branch should be **main**.</span></span> <span data-ttu-id="ba098-224">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-224">For example:</span></span>

   ![Screenshot of the DKE repo in Visual Studio Code displaying the main branch](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="ba098-226">Wenn Sie nicht in der Hauptverzweigung sind, müssen Sie sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="ba098-226">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="ba098-227">Wählen Visual Studio Code die Verzweigung und die Hauptauswahl **aus** der Liste der angezeigten Zweigstellen aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-227">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="ba098-228">Durch Auswählen der Hauptverzweigung wird sichergestellt, dass Sie über die richtigen Dateien zum Erstellen des Projekts verfügen.</span><span class="sxs-lookup"><span data-stu-id="ba098-228">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="ba098-229">Wenn Sie nicht die richtige Verzweigung auswählen, kann ihre Bereitstellung nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba098-229">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="ba098-230">Sie haben nun Ihr DKE-Quellrepository lokal eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="ba098-230">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="ba098-231">Ändern Sie [als Nächstes die Anwendungseinstellungen](#modify-application-settings) für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="ba098-231">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="ba098-232">Ändern von Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ba098-232">Modify application settings</span></span>

<span data-ttu-id="ba098-233">Zum Bereitstellen des DKE-Diensts müssen Sie die folgenden Arten von Anwendungseinstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="ba098-233">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="ba098-234">Zugriffseinstellungen für Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ba098-234">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="ba098-235">Mandanten- und Schlüsseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="ba098-235">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="ba098-236">Sie ändern anwendungseinstellungen in der appsettings.jsdatei.</span><span class="sxs-lookup"><span data-stu-id="ba098-236">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="ba098-237">Diese Datei befindet sich im DoubleKeyEncryptionService-Repository, das Sie lokal unter "DoubleKeyEncryptionService\src\customer-key-store" geklont haben.</span><span class="sxs-lookup"><span data-stu-id="ba098-237">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="ba098-238">Beispielsweise können Sie in Visual Studio Code zu der Datei navigieren, wie in der folgenden Abbildung dargestellt.</span><span class="sxs-lookup"><span data-stu-id="ba098-238">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Suchen des appsettings.jsdatei für DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="ba098-240">Zugriffseinstellungen für Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ba098-240">Key access settings</span></span>

<span data-ttu-id="ba098-241">Wählen Sie aus, ob die E-Mail- oder Rollenautorisierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ba098-241">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="ba098-242">DKE unterstützt immer nur eine dieser Authentifizierungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="ba098-242">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="ba098-243">**E-Mail-Autorisierung**.</span><span class="sxs-lookup"><span data-stu-id="ba098-243">**Email authorization**.</span></span> <span data-ttu-id="ba098-244">Ermöglicht Ihrer Organisation, den Zugriff auf Schlüssel nur basierend auf E-Mail-Adressen zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-244">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="ba098-245">**Rollenautorisierung**.</span><span class="sxs-lookup"><span data-stu-id="ba098-245">**Role authorization**.</span></span> <span data-ttu-id="ba098-246">Ermöglicht Ihrer Organisation, den Zugriff auf Schlüssel basierend auf Active Directory-Gruppen zu autorisieren, und erfordert, dass der Webdienst LDAP abfragen kann.</span><span class="sxs-lookup"><span data-stu-id="ba098-246">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="ba098-247">**So legen Sie Schlüsselzugriffseinstellungen für DKE mithilfe der E-Mail-Autorisierung**</span><span class="sxs-lookup"><span data-stu-id="ba098-247">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="ba098-248">Öffnen Sie **dieappsettings.jsdatei,** und suchen Sie die `AuthorizedEmailAddress` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ba098-248">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="ba098-249">Fügen Sie die E-Mail-Adressen hinzu, die Sie autorisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ba098-249">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="ba098-250">Trennen Sie mehrere E-Mail-Adressen durch doppelte Anführungszeichen und Kommas.</span><span class="sxs-lookup"><span data-stu-id="ba098-250">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="ba098-251">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-251">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="ba098-252">Suchen Sie die `LDAPPath` Einstellung, und entfernen Sie den Text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` zwischen den doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="ba098-252">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="ba098-253">Lassen Sie die doppelten Anführungszeichen stehen.</span><span class="sxs-lookup"><span data-stu-id="ba098-253">Leave the double quotes in place.</span></span> <span data-ttu-id="ba098-254">Wenn Sie fertig sind, sollte die Einstellung wie hier aussehen.</span><span class="sxs-lookup"><span data-stu-id="ba098-254">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="ba098-255">Suchen Sie die `AuthorizedRoles` Einstellung, und löschen Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="ba098-255">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="ba098-256">Diese Abbildung zeigt die **appsettings.jsdatei,** die ordnungsgemäß für die E-Mail-Autorisierung formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="ba098-256">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![The appsettings.json file showing email authorization method](../media/dke-email-accesssetting.png)

<span data-ttu-id="ba098-258">**So legen Sie schlüsselzugriffseinstellungen für DKE mithilfe der Rollenautorisierung**</span><span class="sxs-lookup"><span data-stu-id="ba098-258">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="ba098-259">Öffnen Sie **appsettings.jsdatei,** und suchen Sie die `AuthorizedRoles` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="ba098-259">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="ba098-260">Fügen Sie die Active Directory-Gruppennamen hinzu, die Sie autorisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ba098-260">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="ba098-261">Trennen Sie mehrere Gruppennamen durch doppelte Anführungszeichen und Kommas.</span><span class="sxs-lookup"><span data-stu-id="ba098-261">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="ba098-262">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-262">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="ba098-263">Suchen Sie die `LDAPPath` Einstellung, und fügen Sie die Active Directory-Domäne hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba098-263">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="ba098-264">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-264">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="ba098-265">Suchen Sie die `AuthorizedEmailAddress` Einstellung, und löschen Sie die gesamte Zeile.</span><span class="sxs-lookup"><span data-stu-id="ba098-265">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="ba098-266">Diese Abbildung zeigt die **appsettings.jsdatei,** die ordnungsgemäß für die Rollenautorisierung formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="ba098-266">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jseiner Datei mit der Rollenautorisierungsmethode](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="ba098-268">Mandanten- und Schlüsseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="ba098-268">Tenant and key settings</span></span>

<span data-ttu-id="ba098-269">Die Einstellungen für den Mandanten und die Schlüssel von DKE befinden sich inappsettings.js **Datei.**</span><span class="sxs-lookup"><span data-stu-id="ba098-269">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="ba098-270">**So konfigurieren Sie Mandanten- und Schlüsseleinstellungen für DKE**</span><span class="sxs-lookup"><span data-stu-id="ba098-270">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="ba098-271">Öffnen Sie **dieappsettings.jsOn-Datei.**</span><span class="sxs-lookup"><span data-stu-id="ba098-271">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="ba098-272">Suchen Sie die `ValidIssuers` Einstellung, und ersetzen `<tenantid>` Sie sie durch Ihre Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="ba098-272">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="ba098-273">Sie können Ihre Mandanten-ID finden, indem Sie zum Azure-Portal gehen und die [Mandanteneigenschaften anzeigen.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="ba098-273">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="ba098-274">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-274">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="ba098-275">Suchen Sie die `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="ba098-275">Locate the `JwtAudience`.</span></span> <span data-ttu-id="ba098-276">Ersetzen `<yourhostname>` Sie den Hostnamen des Computers, auf dem der DKE-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ba098-276">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="ba098-277">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-277">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ba098-278">Der Wert für `JwtAudience` muss exakt mit dem Namen Ihres Hosts *übereinstimmen.*</span><span class="sxs-lookup"><span data-stu-id="ba098-278">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="ba098-279">Sie können **localhost:5001 beim Debuggen** verwenden.</span><span class="sxs-lookup"><span data-stu-id="ba098-279">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="ba098-280">Wenn Sie jedoch mit dem Debuggen fertig sind, müssen Sie diesen Wert auf den Hostnamen des Servers aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-280">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="ba098-281">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="ba098-281">`TestKeys:Name`.</span></span> <span data-ttu-id="ba098-282">Geben Sie einen Namen für Ihren Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="ba098-282">Enter a name for your key.</span></span> <span data-ttu-id="ba098-283">Beispiel: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="ba098-283">For example: `TestKey1`</span></span>
- <span data-ttu-id="ba098-284">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="ba098-284">`TestKeys:Id`.</span></span> <span data-ttu-id="ba098-285">Erstellen Sie eine GUID, und geben Sie sie als Wert `TestKeys:ID` ein.</span><span class="sxs-lookup"><span data-stu-id="ba098-285">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="ba098-286">Beispiel: `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="ba098-286">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="ba098-287">Sie können eine Website wie [den Online-GUID-Generator](https://guidgenerator.com/) verwenden, um eine GUID nach dem Zufallsprinzip zu generieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-287">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="ba098-288">Diese Abbildung zeigt das richtige Format für Mandanten- und Schlüsseleinstellungen in **appsettings.json .**</span><span class="sxs-lookup"><span data-stu-id="ba098-288">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="ba098-289">`LDAPPath` ist für die Rollenautorisierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ba098-289">`LDAPPath` is configured for role authorization.</span></span>

![Zeigt die richtigen Mandanten- und Schlüsseleinstellungen für DKE in der datei appsettings.jsan.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="ba098-291">Generieren von Testschlüsseln</span><span class="sxs-lookup"><span data-stu-id="ba098-291">Generate test keys</span></span>

<span data-ttu-id="ba098-292">Nachdem Sie Ihre Anwendungseinstellungen definiert haben, können Sie öffentliche und private Testschlüssel generieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-292">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="ba098-293">So generieren Sie Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="ba098-293">To generate keys:</span></span>

1. <span data-ttu-id="ba098-294">Führen Sie im Startmenü von Windows die OpenSSL-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-294">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="ba098-295">Wechseln Sie zu dem Ordner, in dem Sie die Testschlüssel speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="ba098-295">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="ba098-296">Die Dateien, die Sie durch Ausführen der Schritte in dieser Aufgabe erstellen, werden im gleichen Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ba098-296">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="ba098-297">Generieren Sie den neuen Testschlüssel.</span><span class="sxs-lookup"><span data-stu-id="ba098-297">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="ba098-298">Generieren Sie den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ba098-298">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="ba098-299">Generieren Sie den öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ba098-299">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="ba098-300">Öffnen Sie in einem Texteditor **pubkeyonly.pem**.</span><span class="sxs-lookup"><span data-stu-id="ba098-300">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="ba098-301">Kopieren Sie den inhalt in der Datei **pubkeyonly.pem** mit Ausnahme der ersten und letzten Zeilen in den Abschnittappsettings.js`PublicPem` **On-Datei.**</span><span class="sxs-lookup"><span data-stu-id="ba098-301">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="ba098-302">Öffnen Sie in einem Texteditor **"privkeynopass.pem".**</span><span class="sxs-lookup"><span data-stu-id="ba098-302">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="ba098-303">Kopieren Sie den inhalt in der **Datei "privkeynopass.pem"** mit Ausnahme der ersten und letzten Zeilen in den Abschnittappsettings.js`PrivatePem` **Datei.**</span><span class="sxs-lookup"><span data-stu-id="ba098-303">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="ba098-304">Entfernen Sie alle Leerzeichen und Zeilenlinien in der `PublicPem` und in den `PrivatePem` Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="ba098-304">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="ba098-305">Wenn Sie diesen Inhalt kopieren, löschen Sie keine der PEM-Daten.</span><span class="sxs-lookup"><span data-stu-id="ba098-305">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="ba098-306">Navigieren Visual Studio Code zur **Startup.cs** Datei.</span><span class="sxs-lookup"><span data-stu-id="ba098-306">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="ba098-307">Diese Datei befindet sich im DoubleKeyEncryptionService-Repository, das Sie lokal unter "DoubleKeyEncryptionService\src\customer-key-store\" geklont haben.</span><span class="sxs-lookup"><span data-stu-id="ba098-307">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="ba098-308">Suchen Sie die folgenden Zeilen:</span><span class="sxs-lookup"><span data-stu-id="ba098-308">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="ba098-309">Ersetzen Sie diese Zeilen durch den folgenden Text:</span><span class="sxs-lookup"><span data-stu-id="ba098-309">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="ba098-310">Die Endergebnisse sollten in etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="ba098-310">The end results should look similar to the following.</span></span>

    ![startup.cs datei für die öffentliche Vorschau](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="ba098-312">Jetzt können Sie Ihr [DKE-Projekt erstellen.](#build-the-project)</span><span class="sxs-lookup"><span data-stu-id="ba098-312">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="ba098-313">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="ba098-313">Build the project</span></span>

<span data-ttu-id="ba098-314">Verwenden Sie die folgenden Anweisungen zum lokalen Erstellen des DKE-Projekts:</span><span class="sxs-lookup"><span data-stu-id="ba098-314">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="ba098-315">Wählen Visual Studio Code im REPOSITORY des DKE-Diensts die Option "Befehlspalette  anzeigen" aus, und geben Sie dann \>  **build** an der Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="ba098-315">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="ba098-316">Wählen Sie in der Liste **"Tasks: Run build task" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-316">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="ba098-317">Wenn keine Buildaufgaben gefunden wurden, wählen Sie **"Buildaufgabe** konfigurieren" aus, und erstellen Sie eine für .NET Core wie folgt.</span><span class="sxs-lookup"><span data-stu-id="ba098-317">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Konfigurieren fehlender Buildaufgabe für .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="ba098-319">Choose **Create tasks.json from template**.</span><span class="sxs-lookup"><span data-stu-id="ba098-319">Choose **Create tasks.json from template**.</span></span>

      ![Erstellen tasks.jsDatei aus der Vorlage für DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="ba098-321">Wählen Sie in der Liste der Vorlagentypen **.NET Core aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-321">From the list of template types, select **.NET Core**.</span></span>

      ![Auswählen der richtigen Vorlage für DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="ba098-323">Suchen Sie im Buildabschnitt den Pfad zur **Datei "customerkeystore.csproj".**</span><span class="sxs-lookup"><span data-stu-id="ba098-323">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="ba098-324">Wenn sie nicht da ist, fügen Sie die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="ba098-324">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="ba098-325">Führen Sie den Build erneut aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-325">Run the build again.</span></span>

3. <span data-ttu-id="ba098-326">Stellen Sie sicher, dass im Ausgabefenster keine roten Fehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ba098-326">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="ba098-327">Wenn rote Fehler auftreten, überprüfen Sie die Konsolenausgabe.</span><span class="sxs-lookup"><span data-stu-id="ba098-327">If there are red errors, check the console output.</span></span> <span data-ttu-id="ba098-328">Stellen Sie sicher, dass Sie alle vorherigen Schritte ordnungsgemäß ausgeführt haben und die richtigen Buildversionen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="ba098-328">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="ba098-329">Wählen **Sie** \> **"Debuggen ausführen"** aus, um den Prozess zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="ba098-329">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="ba098-330">Wenn Sie aufgefordert werden, eine Umgebung auszuwählen, wählen Sie **.NET Core aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-330">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="ba098-331">Der .NET Core-Debugger wird in der Regel mit `https://localhost:5001` gestartet.</span><span class="sxs-lookup"><span data-stu-id="ba098-331">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="ba098-332">Zum Anzeigen des Testschlüssels wechseln Sie zu und fügen einen Schrägstrich (/) und den Namen `https://localhost:5001` Ihres Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="ba098-332">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="ba098-333">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-333">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="ba098-334">Der Schlüssel sollte im JSON-Format angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ba098-334">The key should display in JSON format.</span></span>

<span data-ttu-id="ba098-335">Das Setup ist nun abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ba098-335">Your setup is now complete.</span></span> <span data-ttu-id="ba098-336">Bevor Sie den Keystore in appsettings.json für die Einstellung JwtAudience veröffentlichen, stellen Sie sicher, dass der Wert für hostname genau mit Ihrem App-Dienst-Hostnamen entspricht.</span><span class="sxs-lookup"><span data-stu-id="ba098-336">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="ba098-337">Möglicherweise haben Sie es in "localhost" geändert, um probleme mit dem Build zu beheben.</span><span class="sxs-lookup"><span data-stu-id="ba098-337">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="ba098-338">Bereitstellen des DKE-Diensts und Veröffentlichen des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="ba098-338">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="ba098-339">Stellen Sie den Dienst für Produktionsbereitstellungen entweder in einer Drittanbieter-Cloud oder in einem lokalen [System zur Veröffentlichung zur Verfügung.](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)</span><span class="sxs-lookup"><span data-stu-id="ba098-339">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="ba098-340">Möglicherweise bevorzugen Sie andere Methoden zum Bereitstellen ihrer Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ba098-340">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="ba098-341">Wählen Sie die Methode aus, die für Ihre Organisation am besten funktioniert.</span><span class="sxs-lookup"><span data-stu-id="ba098-341">Select the method that works best for your organization.</span></span>

<span data-ttu-id="ba098-342">Für Pilotbereitstellungen können Sie in Azure bereitstellen und sofort los damit beginnen.</span><span class="sxs-lookup"><span data-stu-id="ba098-342">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="ba098-343">**So erstellen Sie eine Azure Web App-Instanz zum Hosten Ihrer DKE-Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="ba098-343">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="ba098-344">Um den Schlüsselspeicher zu veröffentlichen, erstellen Sie eine Azure App Service-Instanz als Host für Ihre DKE-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="ba098-344">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="ba098-345">Als Nächstes veröffentlichen Sie Ihre generierten Schlüssel in Azure.</span><span class="sxs-lookup"><span data-stu-id="ba098-345">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="ba098-346">Melden Sie sich in Ihrem Browser beim [Microsoft Azure-Portal](https://ms.portal.azure.com)an, und wechseln Sie zu **"App Services**  >  **Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="ba098-346">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="ba098-347">Wählen Sie Ihr Abonnement und Ihre Ressourcengruppe aus, und definieren Sie Ihre Instanzdetails.</span><span class="sxs-lookup"><span data-stu-id="ba098-347">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="ba098-348">Geben Sie den Hostnamen des Computers ein, auf dem Sie den DkE-Dienst installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ba098-348">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="ba098-349">Stellen Sie sicher, dass der Name mit dem Namen identisch ist, der für die Einstellung "JwtAudience" in der Datei [**appsettings.jsist.**](#tenant-and-key-settings)</span><span class="sxs-lookup"><span data-stu-id="ba098-349">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="ba098-350">Der Wert, den Sie für den Namen bereitstellen, ist auch der WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="ba098-350">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="ba098-351">Wählen **Sie für "Veröffentlichen",** **"Code"** und für den **Laufzeitstapel** **.NET Core 3.1 aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-351">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="ba098-352">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-352">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba098-353">![Hinzufügen ihres App-Diensts](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="ba098-353">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="ba098-354">At the bottom of the page, select **Review + create**, and then select **Add**.</span><span class="sxs-lookup"><span data-stu-id="ba098-354">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="ba098-355">Gehen Sie wie folgt vor, um die generierten Schlüssel zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="ba098-355">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="ba098-356">Veröffentlichen über ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="ba098-356">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="ba098-357">Veröffentlichen per FTP</span><span class="sxs-lookup"><span data-stu-id="ba098-357">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="ba098-358">Veröffentlichen über Visual Studio 2019 oder höher</span><span class="sxs-lookup"><span data-stu-id="ba098-358">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="ba098-359">Veröffentlichen über ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="ba098-359">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="ba098-360">Wechseln Sie zu `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="ba098-360">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="ba098-361">Beispiel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="ba098-361">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="ba098-362">Wechseln Sie in der Codebasis für den Schlüsselspeicher zum Ordner **"customer-key-store\src\customer-key-store",** und stellen Sie sicher, dass dieser Ordner die Datei **"customerkeystore.csproj"** enthält.</span><span class="sxs-lookup"><span data-stu-id="ba098-362">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="ba098-363">Ausführen: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="ba098-363">Run: **dotnet publish**</span></span>

   <span data-ttu-id="ba098-364">Im Ausgabefenster wird das Verzeichnis angezeigt, in dem die Veröffentlichung bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ba098-364">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="ba098-365">Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="ba098-365">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="ba098-366">Senden Sie alle Dateien im Veröffentlichungsverzeichnis an eine ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="ba098-366">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="ba098-367">Stellen Sie beim Erstellen der ZIP-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der ZIP-Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="ba098-367">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="ba098-368">Ziehen Und ablegen Sie die ZIP-Datei, die Sie erstellen, auf die ZipDeployUI-Website, die Sie oben geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="ba098-368">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="ba098-369">Beispiel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="ba098-369">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="ba098-370">DKE wird bereitgestellt, und Sie können zu den von Ihnen erstellten Testschlüsseln navigieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-370">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="ba098-371">Fahren Sie mit [der Überprüfung Ihrer Bereitstellung weiter](#validate-your-deployment) unten fort.</span><span class="sxs-lookup"><span data-stu-id="ba098-371">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="ba098-372">Veröffentlichen per FTP</span><span class="sxs-lookup"><span data-stu-id="ba098-372">Publish via FTP</span></span>

1. <span data-ttu-id="ba098-373">Stellen Sie eine Verbindung mit dem app-Dienst, den Sie oben [erstellt.](#deploy-the-dke-service-and-publish-the-key-store)</span><span class="sxs-lookup"><span data-stu-id="ba098-373">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="ba098-374">Wechseln Sie in Ihrem Browser zu: **Azure portal**  >  **App Service** Deployment  >  **Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="ba098-374">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="ba098-375">Kopieren Sie die angezeigten Verbindungszeichenfolgen in eine lokale Datei.</span><span class="sxs-lookup"><span data-stu-id="ba098-375">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="ba098-376">Sie verwenden diese Zeichenfolgen, um eine Verbindung mit dem Web -App-Dienst herzustellen und Dateien per FTP hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="ba098-376">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="ba098-377">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-377">For example:</span></span>

   ![Kopieren von Verbindungszeichenfolgen aus dem FTP-Dashboard](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="ba098-379">Wechseln Sie in der Codebasis für den Schlüsselspeicher zum Verzeichnis **"customer-key-store\src\customer-key-store".**</span><span class="sxs-lookup"><span data-stu-id="ba098-379">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="ba098-380">Stellen Sie sicher, dass dieses Verzeichnis die **Datei "customerkeystore.csproj"** enthält.</span><span class="sxs-lookup"><span data-stu-id="ba098-380">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="ba098-381">Ausführen: **dotnet publish**</span><span class="sxs-lookup"><span data-stu-id="ba098-381">Run: **dotnet publish**</span></span>

   <span data-ttu-id="ba098-382">Die Ausgabe enthält das Verzeichnis, in dem die Veröffentlichung bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ba098-382">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="ba098-383">Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="ba098-383">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="ba098-384">Senden Sie alle Dateien im Veröffentlichungsverzeichnis an eine ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="ba098-384">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="ba098-385">Stellen Sie beim Erstellen der ZIP-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der ZIP-Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="ba098-385">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="ba098-386">Verwenden Sie von Ihrem FTP-Client die Verbindungsinformationen, die Sie kopiert haben, um eine Verbindung mit Ihrem App-Dienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ba098-386">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="ba098-387">Laden Sie die ZIP-Datei, die Sie im vorherigen Schritt erstellt haben, in das Stammverzeichnis Ihrer Web App hoch.</span><span class="sxs-lookup"><span data-stu-id="ba098-387">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="ba098-388">DKE wird bereitgestellt, und Sie können zu den von Ihnen erstellten Testschlüsseln navigieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-388">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="ba098-389">Überprüfen Sie [als Nächstes Ihre Bereitstellung.](#validate-your-deployment)</span><span class="sxs-lookup"><span data-stu-id="ba098-389">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="ba098-390">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ba098-390">Validate your deployment</span></span>

<span data-ttu-id="ba098-391">Überprüfen Sie nach der Bereitstellung von DKE mithilfe einer der oben beschriebenen Methoden die Bereitstellung und die wichtigsten Speichereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="ba098-391">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="ba098-392">Führen Sie dies aus:</span><span class="sxs-lookup"><span data-stu-id="ba098-392">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="ba098-393">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-393">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="ba098-394">Stellen Sie sicher, dass in der Ausgabe keine Fehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ba098-394">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="ba098-395">Wenn Sie bereit sind, registrieren [Sie Ihren Schlüsselspeicher.](#register-your-key-store)</span><span class="sxs-lookup"><span data-stu-id="ba098-395">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="ba098-396">Bei dem Schlüsselnamen wird die Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="ba098-396">The key name is case sensitive.</span></span> <span data-ttu-id="ba098-397">Geben Sie den Schlüsselnamen so ein, wie er in der Datei appsettings.jswird.</span><span class="sxs-lookup"><span data-stu-id="ba098-397">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="ba098-398">Registrieren des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="ba098-398">Register your key store</span></span>

<span data-ttu-id="ba098-399">Mit den folgenden Schritten können Sie Ihren DKE-Dienst registrieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-399">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="ba098-400">Die Registrierung Ihres DKE-Diensts ist der letzte Schritt bei der Bereitstellung von DKE, bevor Sie mit dem Erstellen von Bezeichnungen beginnen können.</span><span class="sxs-lookup"><span data-stu-id="ba098-400">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="ba098-401">So registrieren Sie den DKE-Dienst:</span><span class="sxs-lookup"><span data-stu-id="ba098-401">To register the DKE service:</span></span>

1. <span data-ttu-id="ba098-402">Öffnen Sie in Ihrem Browser das [Microsoft Azure-Portal,](https://ms.portal.azure.com/)und wechseln Sie zu **"All Services** \> **Identity** \> **App Registrations".**</span><span class="sxs-lookup"><span data-stu-id="ba098-402">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="ba098-403">Wählen **Sie "Neue Registrierung"** aus, und geben Sie einen aussagekräftigen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="ba098-403">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="ba098-404">Wählen Sie einen Kontotyp aus den angezeigten Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-404">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="ba098-405">Wenn Sie Microsoft Azure mit einer nicht benutzerdefinierten Domäne wie **onmicrosoft.com** verwenden, wählen Sie nur Konten in diesem Organisationsverzeichnis **aus (nur Microsoft – einzelner Mandant).**</span><span class="sxs-lookup"><span data-stu-id="ba098-405">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="ba098-406">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-406">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ba098-407">![Neue App-Registrierung](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="ba098-407">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="ba098-408">Wählen Sie unten auf der Seite **"Registrieren"** aus, um die neue App-Registrierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba098-408">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="ba098-409">Wählen Sie in Der neuen App-Registrierung im linken Bereich unter **"Verwalten"** die Option **"Authentifizierung" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-409">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="ba098-410">Wählen Sie **"Plattform hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-410">Select **Add a platform**.</span></span>

7. <span data-ttu-id="ba098-411">Wählen Sie **im Popup "Plattformen** konfigurieren" die **Option "Web" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-411">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="ba098-412">Geben **Sie unter "Umleitungs-URIs"** den URI Des Verschlüsselungsdiensts mit Doppelschlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="ba098-412">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="ba098-413">Geben Sie die App-Dienst-URL ein, einschließlich hostname und domäne.</span><span class="sxs-lookup"><span data-stu-id="ba098-413">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="ba098-414">Beispiel: https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="ba098-414">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="ba098-415">Die von Ihnen eingegebene URL muss mit dem Hostnamen übereinstimmen, unter dem Ihr DKE-Dienst bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ba098-415">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="ba098-416">Wenn Sie lokal mit einem Visual Studio testen, verwenden Sie **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="ba098-416">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="ba098-417">In allen Fällen muss das Schema **https sein.**</span><span class="sxs-lookup"><span data-stu-id="ba098-417">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="ba098-418">Stellen Sie sicher, dass der Hostname exakt dem Hostnamen des App-Diensts entspricht.</span><span class="sxs-lookup"><span data-stu-id="ba098-418">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="ba098-419">Möglicherweise haben Sie es geändert, `localhost` um eine Problembehandlung für den Build zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ba098-419">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="ba098-420">In **appsettings.json** ist dieser Wert der Hostname, den Sie für festgelegt `JwtAudience` haben.</span><span class="sxs-lookup"><span data-stu-id="ba098-420">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="ba098-421">Aktivieren **Sie unter Implizite** Gewährung das Kontrollkästchen **"ID-Token".**</span><span class="sxs-lookup"><span data-stu-id="ba098-421">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="ba098-422">Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ba098-422">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="ba098-423">Wählen Sie im linken Bereich **"API verfügbar** machen" und dann neben "Anwendungs-ID-URI" die Option **"Festlegen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-423">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="ba098-424">Wählen Sie auf der Seite  **"API verfügbar** machen" in den von diesem API-Bereich definierten Bereich die Option **"Bereich hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-424">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="ba098-425">Im neuen Bereich:</span><span class="sxs-lookup"><span data-stu-id="ba098-425">In the new scope:</span></span>

    1. <span data-ttu-id="ba098-426">Definieren Sie den Bereichsnamen **als user_impersonation.**</span><span class="sxs-lookup"><span data-stu-id="ba098-426">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="ba098-427">Wählen Sie die Administratoren und Benutzer aus, die zustimmen können.</span><span class="sxs-lookup"><span data-stu-id="ba098-427">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="ba098-428">Definieren Sie alle verbleibenden erforderlichen Werte.</span><span class="sxs-lookup"><span data-stu-id="ba098-428">Define any remaining values required.</span></span>

    4. <span data-ttu-id="ba098-429">Klicken Sie auf **Bereich hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ba098-429">Select **Add scope**.</span></span>

    5. <span data-ttu-id="ba098-430">Wählen **Sie oben** "Speichern" aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ba098-430">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="ba098-431">Wählen Sie auf der **Seite "API verfügbar** machen" im Bereich **"Autorisierte Clientanwendungen"** die Option **"Clientanwendung hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="ba098-431">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="ba098-432">In der neuen Clientanwendung:</span><span class="sxs-lookup"><span data-stu-id="ba098-432">In the new client application:</span></span>

    1. <span data-ttu-id="ba098-433">Definieren Sie die Client-ID als **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="ba098-433">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="ba098-434">Dieser Wert ist die Microsoft Office Client-ID und ermöglicht Es Office, ein Zugriffstoken für Ihren Schlüsselspeicher abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ba098-434">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="ba098-435">Wählen **Sie unter "Autorisierte Bereiche"** den **user_impersonation** aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-435">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="ba098-436">Wählen Sie **Anwendung hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ba098-436">Select **Add application**.</span></span>

    4. <span data-ttu-id="ba098-437">Wählen **Sie oben** "Speichern" aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ba098-437">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="ba098-438">Ihr DKE-Dienst ist jetzt registriert.</span><span class="sxs-lookup"><span data-stu-id="ba098-438">Your DKE service is now registered.</span></span> <span data-ttu-id="ba098-439">Fahren Sie fort, [indem Sie Bezeichnungen mithilfe von DKE erstellen.](#create-sensitivity-labels-using-dke)</span><span class="sxs-lookup"><span data-stu-id="ba098-439">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="ba098-440">Erstellen von Vertraulichkeitsbezeichnungen mithilfe von DKE</span><span class="sxs-lookup"><span data-stu-id="ba098-440">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="ba098-441">Erstellen Sie im Microsoft 365 Compliance Center eine neue Vertraulichkeitsbezeichnung, und wenden Sie die Verschlüsselung wie andernfalls an.</span><span class="sxs-lookup"><span data-stu-id="ba098-441">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="ba098-442">Wählen **Sie "Doppelschlüsselverschlüsselung verwenden"** aus, und geben Sie die Endpunkt-URL für Ihren Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="ba098-442">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="ba098-443">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ba098-443">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ba098-444">![Auswählen der Verschlüsselung mit Doppelschlüsseln im Microsoft 365 Compliance Center](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="ba098-444">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="ba098-445">Alle hinzugefügten DKE-Bezeichnungen werden benutzern in den neuesten Versionen von Microsoft 365 Apps for Enterprise angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba098-445">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="ba098-446">Es kann bis zu 24 Stunden dauern, bis die Clients mit den neuen Bezeichnungen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ba098-446">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="ba098-447">Aktivieren von DKE in Ihrem Client</span><span class="sxs-lookup"><span data-stu-id="ba098-447">Enable DKE in your client</span></span>

<span data-ttu-id="ba098-448">Wenn Sie ein Office-Insider sind, ist DKE für Sie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ba098-448">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="ba098-449">Aktivieren Sie andernfalls DKE für Ihren Client, indem Sie die folgenden Registrierungsschlüssel hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ba098-449">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="ba098-450">Migrieren geschützter Dateien von den Bezeichnungen HYOK zu den DKE-Bezeichnungen</span><span class="sxs-lookup"><span data-stu-id="ba098-450">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="ba098-451">Wenn Sie möchten, können Sie nach Abschluss der Einrichtung von DKE Inhalte, die Sie mithilfe von "HYOK"-Bezeichnungen geschützt haben, zu den DKE-Bezeichnungen migrieren.</span><span class="sxs-lookup"><span data-stu-id="ba098-451">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="ba098-452">Zum Migrieren verwenden Sie den AIP-Scanner.</span><span class="sxs-lookup"><span data-stu-id="ba098-452">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="ba098-453">Informationen zu den ersten Schritte mit dem Scanner finden Sie unter [Was ist der Azure Information Protection-Scanner für einheitliche Bezeichnungen?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)</span><span class="sxs-lookup"><span data-stu-id="ba098-453">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="ba098-454">Wenn Sie keine Inhalte migrieren, bleiben Ihre durch HYOK geschützten Inhalte davon unberührt.</span><span class="sxs-lookup"><span data-stu-id="ba098-454">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
