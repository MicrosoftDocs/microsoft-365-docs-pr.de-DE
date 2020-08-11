---
title: Doppelschlüssel Verschlüsselung (DKE)
description: Mit DKE können Sie hoch vertrauliche Daten schützen und gleichzeitig die vollständige Kontrolle über Ihren Schlüssel behalten.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 0c66afa22c8712455a875bc8ca4ddcad1678e2e7
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/10/2020
ms.locfileid: "46601998"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="80b6f-103">Doppelschlüssel Verschlüsselung (DKE)</span><span class="sxs-lookup"><span data-stu-id="80b6f-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="80b6f-104">*Gilt für: Doppelschlüssel Verschlüsselung für Microsoft 365 Public Preview, [Microsoft 365-Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="80b6f-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="80b6f-105">*Anweisungen für: [Azure Information Protection Unified Labeling-Client für Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="80b6f-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="80b6f-106">*Dienstbeschreibung für: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="80b6f-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="80b6f-107">Bei der Doppelschlüssel Verschlüsselung (Double Key Encryption, DKE) werden zwei Schlüssel zusammen verwendet, um auf geschützte Inhalte zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="80b6f-108">Sie speichern einen Schlüssel in Microsoft Azure und halten die andere Taste.</span><span class="sxs-lookup"><span data-stu-id="80b6f-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="80b6f-109">Der Azure Information Protection Unified Labeling-Client schützt hochsensible Inhalte, während Sie den Vollzugriff auf einen Ihrer Schlüssel beibehalten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="80b6f-110">Die Doppelschlüssel Verschlüsselung unterstützt sowohl Cloud-als auch lokale Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="80b6f-111">Mithilfe dieser Bereitstellungen kann sichergestellt werden, dass verschlüsselte Daten immer deckend bleiben, wenn Sie die geschützten Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="80b6f-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="80b6f-112">Weitere Informationen zu den standardmäßigen cloudbasierten Mandantenstamm Schlüsseln finden Sie unter [Planning and Implementing your Azure Information Protection Mandant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="80b6f-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="80b6f-113">Wenn Ihre Organisationen eine der folgenden Anforderungen haben, können Sie DKE verwenden, um Ihre Inhalte zu schützen:</span><span class="sxs-lookup"><span data-stu-id="80b6f-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="80b6f-114">Sie möchten sicherstellen, dass *nur Sie* geschützte Inhalte immer entschlüsseln können, unter allen Umständen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="80b6f-115">Sie möchten nicht, dass Microsoft selbst Zugriff auf geschützte Daten hat.</span><span class="sxs-lookup"><span data-stu-id="80b6f-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="80b6f-116">Sie haben regulatorische Anforderungen, um Schlüssel innerhalb einer geografischen Grenze zu halten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="80b6f-117">Alle Schlüssel, die Sie für die Datenverschlüsselung und-Entschlüsselung speichern, werden in Ihrem Rechenzentrum verwaltet.</span><span class="sxs-lookup"><span data-stu-id="80b6f-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="80b6f-118">System-und Lizenzierungsanforderungen für DKE</span><span class="sxs-lookup"><span data-stu-id="80b6f-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="80b6f-119">Die Doppelschlüssel Verschlüsselung für Microsoft 365 wird mit Microsoft 365 E5 und Office 365 E5 ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="80b6f-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="80b6f-120">Wenn Sie nicht über eine Microsoft 365 E5-Lizenz verfügen, können Sie sich für eine [Testversion](https://aka.ms/M365E5ComplianceTrial)registrieren.</span><span class="sxs-lookup"><span data-stu-id="80b6f-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="80b6f-121">Weitere Informationen zu diesen Lizenzen finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="80b6f-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="80b6f-122">**Office-Insider** Um die öffentliche Vorschau verwenden zu können, müssen Sie Mitglied des Office-Insider Programms sein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="80b6f-123">Um an Office Insider teilzunehmen, wechseln Sie zu [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="80b6f-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="80b6f-124">Nachdem Sie Mitglied sind, bereiten Sie Ihre Umgebung für die Bereitstellung von Office Insider-Builds vor, indem Sie die richtige Bereitstellungsmethode für Ihre Organisation auswählen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="80b6f-125">Anweisungen finden Sie unter [Erste Schritte bei der Bereitstellung von Office-Insider-Builds](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="80b6f-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="80b6f-126">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-126">**Azure Information Protection**.</span></span> <span data-ttu-id="80b6f-127">DKE arbeitet mit Sensitivitäts Bezeichnungen und benötigt Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="80b6f-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="80b6f-128">Unterstützte Umgebungen zum Speichern und anzeigen DKE geschützter Inhalte</span><span class="sxs-lookup"><span data-stu-id="80b6f-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="80b6f-129">**Unterstützte Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-129">**Supported applications**.</span></span> <span data-ttu-id="80b6f-130">[Microsoft 365-Apps für Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) -Clients unter Windows, einschließlich Word, Excel und PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="80b6f-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="80b6f-131">**Online-Inhalts Unterstützung**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-131">**Online content support**.</span></span> <span data-ttu-id="80b6f-132">Dokumente und Dateien, die Online in Microsoft SharePoint und OneDrive für Unternehmen gespeichert werden, werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="80b6f-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="80b6f-133">Sie können verschlüsselte Inhalte per e-Mail freigeben, aber keine verschlüsselten Dokumente und Dateien online anzeigen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="80b6f-134">Stattdessen müssen Sie geschützte Inhalte mithilfe der Desktop-Apps auf dem lokalen Computer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="80b6f-135">Informationen zu diesem öffentlichen Vorschau-Artikel</span><span class="sxs-lookup"><span data-stu-id="80b6f-135">About this public preview article</span></span>

<span data-ttu-id="80b6f-136">Sie können einige der Schritte zum Bereitstellen der doppelten Schlüssel Verschlüsselung auf verschiedene Weise ausführen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="80b6f-137">In diesem Artikel werden ausführliche Anweisungen bereitgestellt, damit erfahrene Administratoren den Dienst erfolgreich bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="80b6f-138">Wenn Sie sich dafür entscheiden, können Sie Ihre eigenen Methoden verwenden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="80b6f-139">Dieser Artikel enthält schrittweise Anweisungen zum Bereitstellen des doppelten Schlüssel Verschlüsselungs Diensts in Azure.</span><span class="sxs-lookup"><span data-stu-id="80b6f-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="80b6f-140">Dieses Szenario ist nicht das, was Sie wahrscheinlich in der Produktion tun würden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="80b6f-141">Für die öffentliche Vorschau ist die Verwendung von Azure ein schneller Weg zur Bereitstellung von DKE.</span><span class="sxs-lookup"><span data-stu-id="80b6f-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="80b6f-142">Durch die Bereitstellung in Azure können Sie sofort mit der doppelten Schlüssel Verschlüsselung beginnen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="80b6f-143">Sie können den Dienst lokal in Ihrem Netzwerk oder mit einem anderen Anbieter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="80b6f-144">Sie müssen den Schlüsselspeicher mit Methoden veröffentlichen, die für diesen Speicherort geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="80b6f-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="80b6f-145">Bereitstellen der doppelten Schlüssel Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="80b6f-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="80b6f-146">In diesem Artikel und dem Bereitstellungs Video wird Azure als Bereitstellungsziel für den DKE-Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="80b6f-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="80b6f-147">Wenn Sie an einem anderen Speicherort bereitstellen, müssen Sie Ihre eigenen Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="80b6f-148">Sehen Sie sich das [Video zur Bereitstellung der doppelten Schlüssel Verschlüsselung](https://youtu.be/vDWfHN_kygg) an, um eine Schritt-für-Schritt-Übersicht der Konzepte im Artikel zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="80b6f-149">Das Video dauert etwa 18 Minuten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="80b6f-150">Sie führen die folgenden allgemeinen Schritte aus, um die doppelte Schlüssel Verschlüsselung für Ihre Organisation einzurichten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="80b6f-151">Installieren der erforderlichen Softwarekomponenten</span><span class="sxs-lookup"><span data-stu-id="80b6f-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="80b6f-152">Klonen des GitHub-Repositorys mit doppelten Schlüssel Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="80b6f-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="80b6f-153">Ändern von Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="80b6f-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="80b6f-154">Generieren von Test Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="80b6f-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="80b6f-155">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="80b6f-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="80b6f-156">Veröffentlichen des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="80b6f-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="80b6f-157">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="80b6f-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="80b6f-158">Registrieren des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="80b6f-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="80b6f-159">Erstellen von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="80b6f-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="80b6f-160">Wenn Sie fertig sind, können Sie Dokumente und Dateien mit DKE verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="80b6f-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="80b6f-161">Weitere Informationen finden Sie unter [Anwenden von Sensitivitäts Bezeichnungen auf Ihre Dateien und e-Mails in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="80b6f-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="80b6f-162">Installieren der erforderlichen Softwarekomponenten</span><span class="sxs-lookup"><span data-stu-id="80b6f-162">Install software prerequisites</span></span>

<span data-ttu-id="80b6f-163">Es gibt zwei Arten von Softwarevoraussetzungen für die Doppelschlüssel Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="80b6f-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="80b6f-164">Voraussetzungen für den doppelten Schlüssel Verschlüsselungsdienst</span><span class="sxs-lookup"><span data-stu-id="80b6f-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="80b6f-165">Zwei wichtige Verschlüsselungs Voraussetzungen für Clientcomputer</span><span class="sxs-lookup"><span data-stu-id="80b6f-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="80b6f-166">Voraussetzungen für den doppelten Schlüssel Verschlüsselungsdienst</span><span class="sxs-lookup"><span data-stu-id="80b6f-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="80b6f-167">Installieren Sie diese Voraussetzungen auf dem Computer, auf dem Sie den DKE-Dienst installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="80b6f-168">**.Net Core 3,1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="80b6f-169">Laden Sie das SDK herunter, und installieren Sie es aus dem [Download .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="80b6f-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="80b6f-170">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-170">**Visual Studio Code**.</span></span> <span data-ttu-id="80b6f-171">Laden Sie Visual Studio Code aus herunter [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="80b6f-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="80b6f-172">Nachdem Sie installiert haben, führen Sie Visual Studio Code aus, und wählen Sie **View** \> **Extensions**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="80b6f-173">Installieren Sie diese Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-173">Install these extensions.</span></span>

- <span data-ttu-id="80b6f-174">C# für Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="80b6f-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="80b6f-175">NuGet-Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="80b6f-175">NuGet Package Manager</span></span>

<span data-ttu-id="80b6f-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="80b6f-177">Richten Sie mindestens eine [Bereitstellungsmethode](https://insider.office.com/business/deploy)ein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="80b6f-178">**Git-Ressourcen**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-178">**Git resources**.</span></span> <span data-ttu-id="80b6f-179">Laden Sie eine der folgenden Optionen herunter, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="80b6f-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="80b6f-180">Git</span><span class="sxs-lookup"><span data-stu-id="80b6f-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="80b6f-181">GitHub-Desktop</span><span class="sxs-lookup"><span data-stu-id="80b6f-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="80b6f-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="80b6f-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="80b6f-183">**OpenSSL** Sie müssen [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installiert haben, um [Testschlüssel zu generieren](#generate-test-keys) , nachdem Sie DKE bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="80b6f-184">Stellen Sie sicher, dass Sie sie ordnungsgemäß aus dem Pfad der Umgebungsvariablen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="80b6f-185">Weitere Informationen finden Sie beispielsweise unter "Add the Installation Directory to Path" unter https://www.osradar.com/install-openssl-windows/ .</span><span class="sxs-lookup"><span data-stu-id="80b6f-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="80b6f-186">Zwei wichtige Verschlüsselungs Voraussetzungen für Clientcomputer</span><span class="sxs-lookup"><span data-stu-id="80b6f-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="80b6f-187">Installieren Sie diese Voraussetzungen auf jedem Clientcomputer, auf dem geschützte Dokumente geschützt und verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="80b6f-188">**Microsoft Office** Version \*. 12711 oder höher.</span><span class="sxs-lookup"><span data-stu-id="80b6f-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="80b6f-189">**Azure Information Protection Unified Labelling-Client** Versionen 2.7.93.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="80b6f-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="80b6f-190">Laden Sie den Unified Labeling-Client von [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)herunter, und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="80b6f-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="80b6f-191">Klonen des DKE GitHub-Repositorys</span><span class="sxs-lookup"><span data-stu-id="80b6f-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="80b6f-192">Microsoft stellt die DKE-Quelldateien in einem GitHub-Repository bereit.</span><span class="sxs-lookup"><span data-stu-id="80b6f-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="80b6f-193">Sie klonen das Repository, um das Projekt für die Verwendung in Ihrer Organisation lokal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="80b6f-194">Das DKE GitHub-Repository befindet sich unter [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="80b6f-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="80b6f-195">Die folgenden Anweisungen sind für Benutzer mit unerfahrenem git oder Visual Studio Code gedacht:</span><span class="sxs-lookup"><span data-stu-id="80b6f-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="80b6f-196">Wechseln Sie in Ihrem Browser zu:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="80b6f-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="80b6f-197">Klicken Sie auf der rechten Seite des Bildschirms auf **Code**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="80b6f-198">Ihre Version der Benutzeroberfläche zeigt möglicherweise eine Schaltfläche " **Klonen" oder "herunterladen** ".</span><span class="sxs-lookup"><span data-stu-id="80b6f-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="80b6f-199">Wählen Sie dann in der Dropdownliste, die angezeigt wird, das Symbol Kopieren aus, um die URL in Ihre Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="80b6f-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="80b6f-200">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-200">For example:</span></span>

   ![Klonen des Double Key-Verschlüsselungsdienst-Repositorys von GitHub](../media/dke-clone.png)

3. <span data-ttu-id="80b6f-202">Wählen Sie in Visual Studio Code **View** die Option \> **Befehls Palette** anzeigen aus, und wählen Sie **git: Clone**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="80b6f-203">Um zur Option in der Liste zu wechseln, beginnen Sie mit der Eingabe, `git: clone` um die Einträge zu filtern, und wählen Sie Sie dann im Dropdown aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="80b6f-204">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-204">For example:</span></span>

   ![Visual Studio Code git: Clone Option](../media/dke-vscode-clone.png)

4. <span data-ttu-id="80b6f-206">Fügen Sie in das Textfeld die URL ein, die Sie aus git kopiert haben, und wählen Sie **aus GitHub Klonen aus**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="80b6f-207">Navigieren Sie im angezeigten Dialogfeld **Ordner auswählen** zu einem Speicherort, und wählen Sie ihn aus, um das Repository zu speichern.</span><span class="sxs-lookup"><span data-stu-id="80b6f-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="80b6f-208">Wählen Sie an der Eingabeaufforderung **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="80b6f-209">Das Repository wird in Visual Studio Code geöffnet und zeigt den aktuellen git-Zweig unten links an.</span><span class="sxs-lookup"><span data-stu-id="80b6f-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="80b6f-210">Die Verzweigung sollte " **Master**" sein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-210">The branch should be **master**.</span></span>

    <span data-ttu-id="80b6f-211">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-211">For example:</span></span>

   ![Visual Studio Code Master Verzweigung](../media/dke-vscode-master.png)

6. <span data-ttu-id="80b6f-213">Wählen Sie das Wort **Master aus,** und wählen Sie dann in der Liste der Verzweigungen **public_preview** aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="80b6f-214">Wenn Sie die public_preview Verzweigung auswählen, stellen Sie sicher, dass Sie über die richtigen Dateien zum Erstellen des Projekts verfügen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="80b6f-215">Wenn Sie nicht die richtige Verzweigung auswählen, wird die Bereitstellung nicht erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="80b6f-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="80b6f-216">Sie haben Ihr DKE-Quell-Repository jetzt lokal eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="80b6f-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="80b6f-217">Ändern Sie als nächstes die [Anwendungseinstellungen](#modify-application-settings) für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="80b6f-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="80b6f-218">Ändern von Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="80b6f-218">Modify application settings</span></span>

<span data-ttu-id="80b6f-219">Um den DKE-Dienst bereitzustellen, müssen Sie die folgenden Arten von Anwendungseinstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="80b6f-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="80b6f-220">Wichtige Zugriffseinstellungen</span><span class="sxs-lookup"><span data-stu-id="80b6f-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="80b6f-221">Mandanten-und Schlüsseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="80b6f-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="80b6f-222">Sie ändern Anwendungseinstellungen in der Datei appsettings.js.</span><span class="sxs-lookup"><span data-stu-id="80b6f-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="80b6f-223">Diese Datei befindet sich im DoubleKeyEncryptionService Repo, das Sie lokal unter DoubleKeyEncryptionService\src\customer-Key-Store. geklont haben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="80b6f-224">Beispielsweise können Sie in Visual Studio Code die Datei wie in der folgenden Abbildung gezeigt durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Suchen der appsettings.jsDatei für DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="80b6f-226">Wichtige Zugriffseinstellungen</span><span class="sxs-lookup"><span data-stu-id="80b6f-226">Key access settings</span></span>

<span data-ttu-id="80b6f-227">Wählen Sie aus, ob e-Mail-oder Rollenautorisierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="80b6f-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="80b6f-228">DKE unterstützt immer nur eine dieser Authentifizierungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="80b6f-229">**E-Mail-Autorisierung**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-229">**Email authorization**.</span></span> <span data-ttu-id="80b6f-230">Ermöglicht Ihrer Organisation die Autorisierung des Zugriffs auf Schlüssel nur basierend auf e-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="80b6f-231">**Rollenautorisierung**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-231">**Role authorization**.</span></span> <span data-ttu-id="80b6f-232">Ermöglicht Ihrer Organisation das Autorisieren des Zugriffs auf Schlüssel basierend auf Active Directory Gruppen und erfordert, dass der Webdienst LDAP Abfragen kann.</span><span class="sxs-lookup"><span data-stu-id="80b6f-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="80b6f-233">**So legen Sie die wichtigsten Zugriffseinstellungen für DKE mithilfe der e-Mail-Autorisierung fest**</span><span class="sxs-lookup"><span data-stu-id="80b6f-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="80b6f-234">Öffnen Sie die Datei **appsettings.jsauf** , und suchen Sie die `AuthorizedEmailAddress` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="80b6f-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="80b6f-235">Fügen Sie die e-Mail-Adressen hinzu, die Sie autorisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="80b6f-236">Trennen Sie mehrere e-Mail-Adressen mit doppelten Anführungszeichen und Kommas.</span><span class="sxs-lookup"><span data-stu-id="80b6f-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="80b6f-237">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="80b6f-238">Suchen `LDAPPath` Sie die Einstellung, und entfernen Sie den Text `If role authorization is used then this is the LDAP path` zwischen den doppelten Anführungszeichen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="80b6f-239">Lassen Sie die doppelten Anführungszeichen an der richtigen Stelle.</span><span class="sxs-lookup"><span data-stu-id="80b6f-239">Leave the double quotes in place.</span></span> <span data-ttu-id="80b6f-240">Wenn Sie fertig sind, sollte die Einstellung wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="80b6f-241">Suchen Sie die `AuthorizedRoles` Einstellung, und löschen Sie die gesamte-Reihe.</span><span class="sxs-lookup"><span data-stu-id="80b6f-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="80b6f-242">Dieses Bild zeigt die **appsettings.jsauf** Datei, die für die e-Mail-Autorisierung ordnungsgemäß formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="80b6f-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![Die appsettings.jsder Datei mit e-Mail-Autorisierungsmethode](../media/dke-email-accesssetting.png)

<span data-ttu-id="80b6f-244">**So legen Sie wichtige Zugriffseinstellungen für DKE mithilfe der Rollenautorisierung fest**</span><span class="sxs-lookup"><span data-stu-id="80b6f-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="80b6f-245">Öffnen Sie die Datei **appsettings.jsauf** , und suchen Sie die `AuthorizedRoles` Einstellung.</span><span class="sxs-lookup"><span data-stu-id="80b6f-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="80b6f-246">Fügen Sie die Active Directory Gruppennamen hinzu, die Sie autorisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="80b6f-247">Trennen Sie mehrere Gruppennamen mit doppelten Anführungszeichen und Kommas.</span><span class="sxs-lookup"><span data-stu-id="80b6f-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="80b6f-248">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="80b6f-249">Suchen `LDAPPath` Sie die Einstellung, und fügen Sie die Active Directory Domäne hinzu.</span><span class="sxs-lookup"><span data-stu-id="80b6f-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="80b6f-250">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="80b6f-251">Suchen Sie die `AuthorizedEmailAddress` Einstellung, und löschen Sie die gesamte-Reihe.</span><span class="sxs-lookup"><span data-stu-id="80b6f-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="80b6f-252">Dieses Bild zeigt die **appsettings.jsauf** Datei, die für die Rollenautorisierung ordnungsgemäß formatiert ist.</span><span class="sxs-lookup"><span data-stu-id="80b6f-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsfür die Datei mit der Rollen Autorisierungsmethode](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="80b6f-254">Mandanten-und Schlüsseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="80b6f-254">Tenant and key settings</span></span>

<span data-ttu-id="80b6f-255">DKE-Mandanten-und Key-Einstellungen befinden sich in der Datei **appsettings.js** .</span><span class="sxs-lookup"><span data-stu-id="80b6f-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="80b6f-256">**So konfigurieren Sie die Mandanten-und Schlüsseleinstellungen für DKE**</span><span class="sxs-lookup"><span data-stu-id="80b6f-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="80b6f-257">Öffnen Sie die Datei **appsettings.js** .</span><span class="sxs-lookup"><span data-stu-id="80b6f-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="80b6f-258">Suchen `ValidIssuers` Sie die Einstellung, und ersetzen `<tenantid>` Sie Sie durch ihre Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="80b6f-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="80b6f-259">Sie können die Mandanten-ID ermitteln, indem Sie zum Azure-Portal wechseln und die [Mandanten Eigenschaften](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)anzeigen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="80b6f-260">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="80b6f-261">Suchen Sie nach der `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="80b6f-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="80b6f-262">Ersetzen Sie `<yourhostname>` durch den Hostnamen des Computers, auf dem der DKE-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="80b6f-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="80b6f-263">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="80b6f-264">Der Wert für `JwtAudience` muss mit dem Namen des Hosts *genau*übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="80b6f-265">Sie können **localhost: 5001** beim Debuggen verwenden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="80b6f-266">Wenn Sie das Debuggen abgeschlossen haben, sollten Sie diesen Wert jedoch auf den Hostnamen des Servers aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="80b6f-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="80b6f-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="80b6f-267">`TestKeys:Name`.</span></span> <span data-ttu-id="80b6f-268">Geben Sie einen Namen für den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-268">Enter a name for your key.</span></span> <span data-ttu-id="80b6f-269">Beispiel: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="80b6f-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="80b6f-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="80b6f-270">`TestKeys:Id`.</span></span> <span data-ttu-id="80b6f-271">Erstellen Sie eine GUID, und geben Sie Sie als `TestKeys:ID` Wert ein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="80b6f-272">Beispiel: `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="80b6f-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="80b6f-273">Sie können eine Website wie den [Online-GUID-Generator](https://guidgenerator.com/) verwenden, um eine GUID nach dem Zufallsprinzip zu generieren.</span><span class="sxs-lookup"><span data-stu-id="80b6f-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="80b6f-274">Dieses Bild zeigt das richtige Format für Mandanten-und Tasteneinstellungen in **appsettings.jsauf**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="80b6f-275">`LDAPPath`ist für die Rollenautorisierung konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="80b6f-275">`LDAPPath` is configured for role authorization.</span></span>

![Zeigt die richtigen Mandanten-und Schlüsseleinstellungen für DKE in der Datei appsettings.js.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="80b6f-277">Generieren von Test Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="80b6f-277">Generate test keys</span></span>

<span data-ttu-id="80b6f-278">Sobald Ihre Anwendungseinstellungen definiert sind, können Sie öffentliche und private Testschlüssel generieren.</span><span class="sxs-lookup"><span data-stu-id="80b6f-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="80b6f-279">So generieren Sie Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-279">To generate keys:</span></span>

1. <span data-ttu-id="80b6f-280">Führen Sie im Windows-Startmenü die OpenSSL-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="80b6f-281">Wechseln Sie zu dem Ordner, in dem Sie die Testschlüssel speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="80b6f-282">Die Dateien, die Sie erstellen, indem Sie die Schritte in dieser Aufgabe ausführen, werden im gleichen Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="80b6f-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="80b6f-283">Generieren Sie den neuen Testschlüssel.</span><span class="sxs-lookup"><span data-stu-id="80b6f-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="80b6f-284">Generiert den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="80b6f-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="80b6f-285">Generieren Sie den öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="80b6f-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="80b6f-286">Öffnen Sie in einem Text-Editor **pubkeyonly. PEM**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="80b6f-287">Kopieren Sie den gesamten Inhalt der Datei **pubkeyonly. PEM** , mit Ausnahme der ersten und der letzten Zeile, in den `PublicPem` Abschnitt der Datei **appsettings.js** .</span><span class="sxs-lookup"><span data-stu-id="80b6f-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="80b6f-288">Öffnen Sie in einem Text-Editor **privkeynopass. PEM**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="80b6f-289">Kopieren Sie den gesamten Inhalt der Datei **privkeynopass. PEM** , mit Ausnahme der ersten und der letzten Zeile, in den `PrivatePem` Abschnitt der Datei **appsettings.js** .</span><span class="sxs-lookup"><span data-stu-id="80b6f-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="80b6f-290">Entfernen Sie alle Leerzeichen und Zeilen Umrisse in `PublicPem` den `PrivatePem` Abschnitten und.</span><span class="sxs-lookup"><span data-stu-id="80b6f-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="80b6f-291">Wenn Sie diesen Inhalt kopieren, löschen Sie keine PEM-Daten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="80b6f-292">Navigieren Sie in Visual Studio Code zur **Startup.cs** -Datei.</span><span class="sxs-lookup"><span data-stu-id="80b6f-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="80b6f-293">Diese Datei befindet sich im DoubleKeyEncryptionService Repo, das Sie lokal unter DoubleKeyEncryptionService\src\customer-Key-store\. geklont haben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="80b6f-294">Suchen Sie die folgenden Zeilen:</span><span class="sxs-lookup"><span data-stu-id="80b6f-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="80b6f-295">Ersetzen Sie diese Zeilen durch den folgenden Text:</span><span class="sxs-lookup"><span data-stu-id="80b6f-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="80b6f-296">Die Endergebnisse sollten etwa wie folgt aussehen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-296">The end results should look similar to the following.</span></span>

   ![Startup.cs-Datei für die öffentliche Vorschau](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="80b6f-298">Jetzt sind Sie fertig, um [Ihr DKE-Projekt zu erstellen](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="80b6f-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="80b6f-299">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="80b6f-299">Build the project</span></span>

<span data-ttu-id="80b6f-300">Verwenden Sie die folgenden Anweisungen, um das DKE-Projekt lokal zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="80b6f-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="80b6f-301">Wählen Sie in Visual Studio Code im DKE-Dienst-Repository **View** die Option \> **Befehls Palette** anzeigen aus, und geben Sie dann an der Eingabeaufforderung **Erstellen** ein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="80b6f-302">Wählen Sie in der Liste **Aufgaben: Build-Task ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="80b6f-303">Wenn keine Build-Tasks gefunden werden, wählen Sie Create **Task konfigurieren** aus, und erstellen Sie wie folgt einen für .net Core.</span><span class="sxs-lookup"><span data-stu-id="80b6f-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Konfigurieren fehlender Build-Aufgabe für .net](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="80b6f-305">Wählen Sie **tasks.jsaus Vorlage erstellen aus**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-305">Choose **Create tasks.json from template**.</span></span>

   ![Erstellen tasks.jsDatei aus der Vorlage für DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="80b6f-307">Wählen Sie in der Liste der Vorlagentypen **.net Core**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-307">From the list of template types, select **.NET Core**.</span></span>

   ![Erstellen tasks.jsDatei aus der Vorlage für DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="80b6f-309">Suchen Sie im Abschnitt erstellen nach dem Pfad zur Datei **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="80b6f-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="80b6f-310">Wenn er nicht vorhanden ist, fügen Sie die folgende Reihe hinzu:</span><span class="sxs-lookup"><span data-stu-id="80b6f-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="80b6f-311">Führen Sie den Build erneut aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-311">Run the build again.</span></span>

1. <span data-ttu-id="80b6f-312">Stellen Sie sicher, dass im Ausgabefenster keine roten Fehler vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="80b6f-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="80b6f-313">Wenn rote Fehler vorliegen, überprüfen Sie die Konsolenausgabe.</span><span class="sxs-lookup"><span data-stu-id="80b6f-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="80b6f-314">Stellen Sie sicher, dass Sie alle vorherigen Schritte ordnungsgemäß abgeschlossen haben und die richtigen Build-Versionen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="80b6f-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="80b6f-315">Wählen **Run** Sie \> **Start Debuggen** ausführen aus, um den Prozess zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="80b6f-316">Wenn Sie zur Auswahl einer Umgebung aufgefordert werden, wählen Sie **.net Core**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="80b6f-317">Der .net Core-Debugger wird normalerweise in "'" gestartet https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 und ein Schrägstrich (/) und der Name des Schlüssels angefügt.</span><span class="sxs-lookup"><span data-stu-id="80b6f-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="80b6f-318">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="80b6f-319">Der Schlüssel sollte im JSON-Format angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-319">The key should display in JSON format.</span></span>

<span data-ttu-id="80b6f-320">Ihr Setup ist nun abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-320">Your setup is now complete.</span></span> <span data-ttu-id="80b6f-321">Stellen Sie vor dem Veröffentlichen des Keystores in appsettings.jsauf für die JwtAudience-Einstellung sicher, dass der Wert für Hostname genau mit dem Namen des App-Diensthosts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="80b6f-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="80b6f-322">Möglicherweise haben Sie es zu localhost geändert, um die Problembehandlung für den Build auszuführen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="80b6f-323">Veröffentlichen des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="80b6f-323">Publish the key store</span></span>

<span data-ttu-id="80b6f-324">Zum Veröffentlichen des Schlüsselspeichers erstellen Sie eine Azure-App-Dienstinstanz, die ihre DKE-Bereitstellung hostet.</span><span class="sxs-lookup"><span data-stu-id="80b6f-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="80b6f-325">Als Nächstes veröffentlichen Sie die generierten Schlüssel in Azure.</span><span class="sxs-lookup"><span data-stu-id="80b6f-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="80b6f-326">**So erstellen Sie eine Azure-Webanwendung-Instanz zum Hosten Ihrer DKE-Bereitstellung**</span><span class="sxs-lookup"><span data-stu-id="80b6f-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="80b6f-327">Melden Sie sich in Ihrem Browser beim [Microsoft Azure-Portal](https://ms.portal.azure.com)an, und wechseln Sie zu **App-Dienste**  >  **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="80b6f-328">Wählen Sie Ihre Abonnement-und Ressourcengruppe aus, und definieren Sie die Details der Instanz.</span><span class="sxs-lookup"><span data-stu-id="80b6f-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="80b6f-329">Geben Sie den Hostnamen des Computers ein, auf dem Sie den DKE-Dienst installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="80b6f-330">Stellen Sie sicher, dass der Name dem Namen entspricht, der für die JwtAudience-Einstellung in der Datei [**appsettings.js**](#tenant-and-key-settings) für festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="80b6f-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="80b6f-331">Der Wert, den Sie für den Namen angeben, ist auch der WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="80b6f-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="80b6f-332">Wählen Sie für **veröffentlichen**den **Code**aus, und wählen Sie für **Laufzeitstapel** **.net Core 3,1**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="80b6f-333">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-333">For example:</span></span>

   ![Hinzufügen des App-Diensts](../media/dke-azure-add-app-service.png)

1. <span data-ttu-id="80b6f-335">Wählen Sie unten auf der Seite **überprüfen + erstellen**aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="80b6f-336">Führen Sie einen der folgenden Schritte aus, um die generierten Schlüssel in Azure zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="80b6f-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="80b6f-337">Veröffentlichen über ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="80b6f-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="80b6f-338">Veröffentlichen über FTP</span><span class="sxs-lookup"><span data-stu-id="80b6f-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="80b6f-339">Veröffentlichen über Visual Studio 2019 oder höher</span><span class="sxs-lookup"><span data-stu-id="80b6f-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="80b6f-340">Veröffentlichen in einem lokalen System</span><span class="sxs-lookup"><span data-stu-id="80b6f-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="80b6f-341">Möglicherweise bevorzugen Sie andere Methoden zum Bereitstellen der Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="80b6f-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="80b6f-342">Wählen Sie die Methode aus, die für Ihre Organisation am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="80b6f-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="80b6f-343">Die [Veröffentlichung über Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) und an ein [Lokales System](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) wird in der [ASP .NET-Dokumentation](https://docs.microsoft.com/aspnet/core/)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="80b6f-344">Wenn Sie eine dieser Methoden verwenden, öffnen Sie die Anweisungen in einer separaten Registerkarte, damit Sie nach Abschluss des Verfahrens problemlos zurückkehren können.</span><span class="sxs-lookup"><span data-stu-id="80b6f-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="80b6f-345">Veröffentlichen über ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="80b6f-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="80b6f-346">Navigieren Sie in das Verzeichnis `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="80b6f-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="80b6f-347">Beispiel: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="80b6f-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="80b6f-348">Wechseln Sie in der CodeBase für den Schlüsselspeicher zum Ordner **Customer-Key-store\src\customer-Key-Store** , und vergewissern Sie sich, dass dieser Ordner die Datei **customerkeystore. csproj** enthält.</span><span class="sxs-lookup"><span data-stu-id="80b6f-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="80b6f-349">Ausführen: **dotnet veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="80b6f-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="80b6f-350">Das Ausgabefenster zeigt das Verzeichnis an, in dem die Veröffentlichung bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="80b6f-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="80b6f-351">Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="80b6f-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="80b6f-352">Senden Sie alle Dateien im Veröffentlichungsverzeichnis an eine ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="80b6f-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="80b6f-353">Stellen Sie beim Erstellen der ZIP-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der ZIP-Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="80b6f-354">Ziehen Sie die ZIP-Datei, die Sie erstellen, auf die ZipDeployUI-Website, die Sie oben geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="80b6f-355">Beispiel: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="80b6f-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="80b6f-356">DKE wird bereitgestellt, und Sie können zu den Test Schlüsseln navigieren, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="80b6f-357">Über [prüfen Sie Ihre Bereitstellung](#validate-your-deployment) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="80b6f-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="80b6f-358">Veröffentlichen über FTP</span><span class="sxs-lookup"><span data-stu-id="80b6f-358">Publish via FTP</span></span>

1. <span data-ttu-id="80b6f-359">Stellen Sie eine Verbindung mit dem [oben](#publish-the-key-store)erstellten App-Dienst her.</span><span class="sxs-lookup"><span data-stu-id="80b6f-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="80b6f-360">Wechseln Sie in Ihrem Browser zu: **Azure Portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="80b6f-361">Kopieren Sie die angezeigten Verbindungszeichenfolgen in eine lokale Datei.</span><span class="sxs-lookup"><span data-stu-id="80b6f-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="80b6f-362">Sie verwenden diese Zeichenfolgen, um eine Verbindung zum Webdienst des Webanwendungs herzustellen und Dateien über FTP hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="80b6f-363">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-363">For example:</span></span>

   ![Kopieren von Verbindungszeichenfolgen aus dem FTP-Dashboard](../media/dke-ftp-dashboard.png)

1. <span data-ttu-id="80b6f-365">Wechseln Sie in der CodeBase für den Schlüsselspeicher zum **Verzeichnis Customer-Key-store\src\customer-Key-Store**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="80b6f-366">Stellen Sie sicher, dass dieses Verzeichnis die Datei **customerkeystore. csproj** enthält.</span><span class="sxs-lookup"><span data-stu-id="80b6f-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="80b6f-367">Ausführen: **dotnet veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="80b6f-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="80b6f-368">Die Ausgabe enthält das Verzeichnis, in dem die Veröffentlichung bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="80b6f-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="80b6f-369">Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="80b6f-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="80b6f-370">Senden Sie alle Dateien im Veröffentlichungsverzeichnis in eine ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="80b6f-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="80b6f-371">Stellen Sie beim Erstellen der ZIP-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der ZIP-Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="80b6f-372">Verwenden Sie von Ihrem FTP-Client die Verbindungsinformationen, die Sie zum Herstellen einer Verbindung mit Ihrem App-Dienst kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="80b6f-373">Laden Sie die ZIP-Datei, die Sie im vorherigen Schritt erstellt haben, in das Stammverzeichnis Ihrer Webanwendung hoch.</span><span class="sxs-lookup"><span data-stu-id="80b6f-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="80b6f-374">DKE wird bereitgestellt, und Sie können zu den Test Schlüsseln navigieren, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="80b6f-375">Als nächstes [validieren Sie Ihre Bereitstellung](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="80b6f-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="80b6f-376">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="80b6f-376">Validate your deployment</span></span>

<span data-ttu-id="80b6f-377">Nachdem Sie DKE mit einer der oben beschriebenen Methoden bereitgestellt haben, überprüfen Sie die Bereitstellung und die Schlüsselspeicher Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="80b6f-378">Führen Sie  aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-378">Run:</span></span>

<span data-ttu-id="80b6f-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="80b6f-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="80b6f-380">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-380">For example:</span></span>

<span data-ttu-id="80b6f-381">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="80b6f-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="80b6f-382">Stellen Sie sicher, dass in der Ausgabe keine Fehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="80b6f-383">Wenn Sie fertig sind, [registrieren Sie Ihren Schlüsselspeicher](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="80b6f-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="80b6f-384">Registrieren des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="80b6f-384">Register your key store</span></span>

<span data-ttu-id="80b6f-385">Mit den folgenden Schritten können Sie den Schlüsselspeicher registrieren.</span><span class="sxs-lookup"><span data-stu-id="80b6f-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="80b6f-386">Das Registrieren des Schlüsselspeichers ist der letzte Schritt bei der Bereitstellung von DKE, bevor Sie mit dem Erstellen von Beschriftungen beginnen können.</span><span class="sxs-lookup"><span data-stu-id="80b6f-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="80b6f-387">So registrieren Sie Ihren Schlüsselspeicher:</span><span class="sxs-lookup"><span data-stu-id="80b6f-387">To register your key store:</span></span>

1. <span data-ttu-id="80b6f-388">Öffnen Sie in Ihrem Browser das [Microsoft Azure-Portal](https://ms.portal.azure.com/), und wechseln Sie zu **alle Services** - \> **Identitäts** - \> **App-Registrierungen**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="80b6f-389">Wählen Sie **neue Registrierung**aus, und geben Sie einen aussagekräftigen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="80b6f-390">Wählen Sie in den angezeigten Optionen einen Kontotyp aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="80b6f-391">Wenn Sie Microsoft Azure mit einer nicht benutzerdefinierten Domäne wie **onmicrosoft.com**verwenden, wählen Sie **Konten nur in diesem Organisations Verzeichnis aus (nur Microsoft – einzelner Mandant).**</span><span class="sxs-lookup"><span data-stu-id="80b6f-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="80b6f-392">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-392">For example:</span></span>

   ![Neue APP-Registrierung](../media/dke-app-registration.png)

4. <span data-ttu-id="80b6f-394">Wählen Sie unten auf der Seite **registrieren** aus, um die neue APP-Registrierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="80b6f-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="80b6f-395">Wählen Sie in der neuen App-Registrierung im linken Bereich unter **Verwalten**die Option **Authentifizierung**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="80b6f-396">Wählen Sie **Plattform hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="80b6f-397">Wählen Sie im Popup **Konfigurieren von Plattformen** die Option **Internet**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="80b6f-398">Geben Sie unter **Umleitungs-URIs**den URI des doppelten Schlüssel Verschlüsselungs Diensts ein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="80b6f-399">Geben Sie die APP-Dienst-URL ein, einschließlich des Hostnamens und der Domäne.</span><span class="sxs-lookup"><span data-stu-id="80b6f-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="80b6f-400">Beispiel: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="80b6f-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="80b6f-401">Die eingegebene URL muss mit dem Hostnamen übereinstimmen, in dem der Schlüsselspeicher bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="80b6f-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="80b6f-402">Wenn Sie lokal mit Visual Studio testen, verwenden Sie **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="80b6f-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="80b6f-403">In allen Fällen muss das Schema **https**sein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="80b6f-404">Stellen Sie sicher, dass der Hostname genau mit dem Hostnamen des App-Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="80b6f-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="80b6f-405">Möglicherweise haben Sie es geändert, um `localhost` die Problembehandlung beim Build zu beheben.</span><span class="sxs-lookup"><span data-stu-id="80b6f-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="80b6f-406">In **appsettings.json**ist dieser Wert der Hostname, für den Sie festgelegt haben `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="80b6f-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="80b6f-407">Aktivieren Sie unter **implizite Gewährung**das Kontrollkästchen **ID-Token** .</span><span class="sxs-lookup"><span data-stu-id="80b6f-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="80b6f-408">Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="80b6f-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="80b6f-409">Wählen Sie im linken Bereich **eine API verfügbar machen**aus, und wählen Sie dann neben Anwendungs-ID-URI die Option **festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="80b6f-410">Wählen Sie auf der Seite **eine API verfügbar machen** im Bereich **durch diese API definierte Bereiche** die Option **Bereich hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="80b6f-411">Im neuen Bereich:</span><span class="sxs-lookup"><span data-stu-id="80b6f-411">In the new scope:</span></span>

    1. <span data-ttu-id="80b6f-412">Definieren Sie den Bereichsnamen als **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="80b6f-413">Wählen Sie die Administratoren und Benutzer, die zustimmen können.</span><span class="sxs-lookup"><span data-stu-id="80b6f-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="80b6f-414">Definieren Sie alle verbleibenden erforderlichen Werte.</span><span class="sxs-lookup"><span data-stu-id="80b6f-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="80b6f-415">Wählen Sie **Bereich hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="80b6f-415">Select **Add scope.**</span></span>

    <span data-ttu-id="80b6f-416">Wählen Sie oben **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="80b6f-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="80b6f-417">Wählen Sie weiterhin auf der Seite **eine API verfügbar machen** im Bereich **autorisierte Clientanwendungen** die Option **Clientanwendung hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="80b6f-418">In der neuen Clientanwendung:</span><span class="sxs-lookup"><span data-stu-id="80b6f-418">In the new client application:</span></span>

    1. <span data-ttu-id="80b6f-419">Definieren Sie die Client-ID als **d3590ed6-52b3-4102-Aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="80b6f-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="80b6f-420">Dieser Wert ist die Microsoft Office-Client-ID und ermöglicht Office das Abrufen eines Zugriffstokens für den Schlüsselspeicher.</span><span class="sxs-lookup"><span data-stu-id="80b6f-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="80b6f-421">Wählen Sie unter **autorisierte Bereiche**den **user_impersonation** Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="80b6f-422">Wählen Sie **Anwendung hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="80b6f-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="80b6f-423">Wählen Sie oben **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="80b6f-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="80b6f-424">Ihr DKE-Schlüsselspeicher ist jetzt registriert.</span><span class="sxs-lookup"><span data-stu-id="80b6f-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="80b6f-425">Fahren Sie mit dem [Erstellen von Beschriftungen mithilfe von DKE](#create-labels-using-dke)fort.</span><span class="sxs-lookup"><span data-stu-id="80b6f-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="80b6f-426">Erstellen von Beschriftungen mithilfe von DKE</span><span class="sxs-lookup"><span data-stu-id="80b6f-426">Create labels using DKE</span></span>

<span data-ttu-id="80b6f-427">Erstellen Sie im Microsoft 365 Compliance Center eine neue Sensitivitäts Bezeichnung, und wenden Sie die Verschlüsselung wie sonst an.</span><span class="sxs-lookup"><span data-stu-id="80b6f-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="80b6f-428">Wählen Sie **Doppelschlüssel Verschlüsselung verwenden** aus, und geben Sie die Endpunkt-URL für Ihren Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="80b6f-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="80b6f-429">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="80b6f-429">For example:</span></span>

![Wählen Sie Doppelschlüssel Verschlüsselung im Microsoft 365 Compliance Center verwenden aus.](../media/dke-use-dke.png)

<span data-ttu-id="80b6f-431">Alle DKE-Bezeichnungen, die Sie hinzufügen, werden für Benutzer in den neuesten Versionen von Microsoft 365 apps for Enterprise angezeigt.</span><span class="sxs-lookup"><span data-stu-id="80b6f-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="80b6f-432">Es kann bis zu 24 Stunden dauern, bis die Clients mit den neuen Bezeichnungen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="80b6f-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="80b6f-433">Aktivieren von DKE in Ihrem Client</span><span class="sxs-lookup"><span data-stu-id="80b6f-433">Enable DKE in your client</span></span>

<span data-ttu-id="80b6f-434">Aktivieren Sie DKE für Ihren Client, indem Sie die folgenden Registrierungsschlüssel hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="80b6f-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
