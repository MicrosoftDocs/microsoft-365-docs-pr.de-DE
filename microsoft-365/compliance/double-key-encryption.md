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
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201729"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="e8111-103">Doppelschlüssel Verschlüsselung (DKE)</span><span class="sxs-lookup"><span data-stu-id="e8111-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="e8111-104">*Gilt für: [Microsoft 365-Konformität](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="e8111-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="e8111-105">*Anweisungen für: [Azure Information Protection Unified Labeling-Client für Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="e8111-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="e8111-106">*Dienstbeschreibung für: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="e8111-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="e8111-107">Mit dieser Public Preview-Version von Double Key Encryption (DKE) können Sie den Azure Information Protection Unified Labelling-Client verwenden, um hochsensible Inhalte zu schützen und gleichzeitig die vollständige Kontrolle über Ihren Schlüssel beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="e8111-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="e8111-108">Für den Zugriff auf geschützte Inhalte sind zwei Schlüssel erforderlich, die zusammen verwendet werden, um eine Doppelschlüssel Verschlüsselung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e8111-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="e8111-109">Sie speichern einen Schlüssel in Microsoft Azure und halten die andere Taste.</span><span class="sxs-lookup"><span data-stu-id="e8111-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="e8111-110">Die Doppelschlüssel Verschlüsselung unterstützt sowohl Cloud-als auch lokale Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="e8111-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="e8111-111">Mithilfe dieser Bereitstellungen kann sichergestellt werden, dass verschlüsselte Daten immer deckend bleiben, wenn Sie die geschützten Daten speichern.</span><span class="sxs-lookup"><span data-stu-id="e8111-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="e8111-112">Weitere Informationen zu den standardmäßigen cloudbasierten Mandantenstamm Schlüsseln finden Sie unter [Planning and Implementing your Azure Information Protection Mandant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="e8111-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="e8111-113">Die Verschlüsselung mit doppeltem Schlüssel ähnelt einem Schließfach, das sowohl einen Bankschlüssel als auch einen Kundenschlüssel benötigt, um Zugriff zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e8111-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="e8111-114">Zum Entschlüsseln geschützter Inhalte müssen Sie sowohl den Microsoft Managed Key als auch den Kundenschlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8111-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="e8111-115">Im folgenden Video wird gezeigt, wie die doppelte Schlüssel Verschlüsselung funktioniert, um Ihre Inhalte zu schützen.</span><span class="sxs-lookup"><span data-stu-id="e8111-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="e8111-116">Wenn Ihre Organisationen eine der folgenden Anforderungen haben, können Sie DKE verwenden, um Ihre Inhalte zu schützen:</span><span class="sxs-lookup"><span data-stu-id="e8111-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="e8111-117">Sie möchten sicherstellen, dass *nur Sie* geschützte Inhalte immer entschlüsseln können, unter allen Umständen.</span><span class="sxs-lookup"><span data-stu-id="e8111-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="e8111-118">Sie möchten nicht, dass Microsoft selbst Zugriff auf geschützte Daten hat.</span><span class="sxs-lookup"><span data-stu-id="e8111-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="e8111-119">Sie haben regulatorische Anforderungen, um Schlüssel innerhalb einer geografischen Grenze zu halten.</span><span class="sxs-lookup"><span data-stu-id="e8111-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="e8111-120">Alle Kundenschlüssel für die Datenverschlüsselung und-Entschlüsselung werden in Ihrem Rechenzentrum verwaltet.</span><span class="sxs-lookup"><span data-stu-id="e8111-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="e8111-121">System-und Lizenzierungsanforderungen für DKE</span><span class="sxs-lookup"><span data-stu-id="e8111-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="e8111-122">Diese Public Preview-Version der Doppelschlüssel Verschlüsselung für Microsoft 365 ist als Teil von Microsoft 365 E5 und Office 365 E5 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e8111-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="e8111-123">Wenn Sie nicht über eine Microsoft 365 E5-Lizenz verfügen, können Sie sich für eine [Testversion](https://aka.ms/M365E5ComplianceTrial)registrieren.</span><span class="sxs-lookup"><span data-stu-id="e8111-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="e8111-124">Weitere Informationen zu diesen Lizenzen finden Sie unter [Microsoft 365 Licensing Guidance for Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="e8111-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="e8111-125">**Office-Insider** Um die öffentliche Vorschau verwenden zu können, müssen Sie Mitglied des Office-Insider Programms sein.</span><span class="sxs-lookup"><span data-stu-id="e8111-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="e8111-126">Um an Office Insider teilzunehmen, wechseln Sie zu [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="e8111-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="e8111-127">Nachdem Sie Mitglied sind, bereiten Sie Ihre Umgebung für die Bereitstellung von Office Insider-Builds vor, indem Sie die richtige Bereitstellungsmethode für Ihre Organisation auswählen.</span><span class="sxs-lookup"><span data-stu-id="e8111-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="e8111-128">Anweisungen finden Sie unter [Erste Schritte bei der Bereitstellung von Office-Insider-Builds](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="e8111-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="e8111-129">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="e8111-129">**Azure Information Protection**.</span></span> <span data-ttu-id="e8111-130">DKE arbeitet mit Sensitivitäts Bezeichnungen und benötigt Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="e8111-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="e8111-131">Unterstützte Umgebungen zum Speichern und anzeigen DKE geschützter Inhalte</span><span class="sxs-lookup"><span data-stu-id="e8111-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="e8111-132">**Unterstützte Anwendungen**.</span><span class="sxs-lookup"><span data-stu-id="e8111-132">**Supported applications**.</span></span> <span data-ttu-id="e8111-133">[Microsoft 365-Apps für Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) -Clients unter Windows, einschließlich Word, Excel und PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="e8111-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="e8111-134">**Online-Inhalts Unterstützung**.</span><span class="sxs-lookup"><span data-stu-id="e8111-134">**Online content support**.</span></span> <span data-ttu-id="e8111-135">Dokumente und Dateien, die Online in Microsoft SharePoint und OneDrive für Unternehmen gespeichert werden, werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e8111-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="e8111-136">Sie können verschlüsselte Inhalte per e-Mail freigeben, aber keine verschlüsselten Dokumente und Dateien online anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e8111-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="e8111-137">Stattdessen müssen Sie geschützte Inhalte mithilfe der Desktop-Apps auf dem lokalen Computer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e8111-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="e8111-138">Informationen zu diesem öffentlichen Vorschau-Artikel</span><span class="sxs-lookup"><span data-stu-id="e8111-138">About this public preview article</span></span>

<span data-ttu-id="e8111-139">Sie können einige der Schritte zum Bereitstellen der doppelten Schlüssel Verschlüsselung auf verschiedene Weise ausführen.</span><span class="sxs-lookup"><span data-stu-id="e8111-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="e8111-140">In diesem Artikel werden ausführliche Anweisungen bereitgestellt, damit erfahrene Administratoren den Dienst erfolgreich bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e8111-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="e8111-141">Wenn Sie mit den gängigen Technologien wie git vertraut sind, die von den in diesem Artikel beschriebenen Bereitstellungsmethoden gemeinsam verwendet werden, können Sie Ihre eigenen Methoden auswählen.</span><span class="sxs-lookup"><span data-stu-id="e8111-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="e8111-142">Für die öffentliche Vorschau wurden detaillierte Anweisungen zum Bereitstellen des doppelten Schlüssel Verschlüsselungs Diensts in Azure aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8111-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="e8111-143">Dieses Szenario ist nicht das, was Sie wahrscheinlich in der Produktion tun würden.</span><span class="sxs-lookup"><span data-stu-id="e8111-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="e8111-144">Für die öffentliche Vorschau mithilfe von Azure ist eine schnelle Möglichkeit zur Bereitstellung, mit der Sie sofort mit der doppelten Schlüssel Verschlüsselung beginnen können.</span><span class="sxs-lookup"><span data-stu-id="e8111-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="e8111-145">Sie können den Dienst an beliebiger Stelle bereitstellen, unabhängig davon, ob er lokal in Ihrem Netzwerk oder mit einem anderen Anbieter vorliegt.</span><span class="sxs-lookup"><span data-stu-id="e8111-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="e8111-146">Sie müssen den Schlüsselspeicher mit den für diesen Speicherort geeigneten Methoden veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e8111-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="e8111-147">Bereitstellen der doppelten Schlüssel Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e8111-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="e8111-148">Sie führen die folgenden allgemeinen Schritte aus, um die doppelte Schlüssel Verschlüsselung für Ihre Organisation einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e8111-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="e8111-149">Im Beispiel in diesem Artikel wird Azure als Bereitstellungsziel für den DKE-Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8111-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="e8111-150">Wenn Sie an einem anderen Speicherort bereitstellen, müssen Sie Ihre eigenen Werte angeben.</span><span class="sxs-lookup"><span data-stu-id="e8111-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="e8111-151">Installieren der erforderlichen Softwarekomponenten</span><span class="sxs-lookup"><span data-stu-id="e8111-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="e8111-152">Klonen des GitHub-Repositorys mit doppelten Schlüssel Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="e8111-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="e8111-153">Ändern von Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e8111-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="e8111-154">Generieren von Test Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="e8111-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="e8111-155">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="e8111-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="e8111-156">Veröffentlichen des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="e8111-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="e8111-157">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="e8111-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="e8111-158">Registrieren des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="e8111-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="e8111-159">Erstellen von Vertraulichkeitsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="e8111-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="e8111-160">Wenn Sie fertig sind, können Sie Dokumente und Dateien mit DKE verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="e8111-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="e8111-161">Weitere Informationen finden Sie unter [Anwenden von Sensitivitäts Bezeichnungen auf Ihre Dateien und e-Mails in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="e8111-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="e8111-162">Installieren der erforderlichen Softwarekomponenten</span><span class="sxs-lookup"><span data-stu-id="e8111-162">Install software prerequisites</span></span>

<span data-ttu-id="e8111-163">Es gibt zwei Arten von Softwarevoraussetzungen für die Doppelschlüssel Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="e8111-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="e8111-164">Voraussetzungen für den doppelten Schlüssel Verschlüsselungsdienst</span><span class="sxs-lookup"><span data-stu-id="e8111-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="e8111-165">Zwei wichtige Verschlüsselungs Voraussetzungen für Clientcomputer</span><span class="sxs-lookup"><span data-stu-id="e8111-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="e8111-166">Voraussetzungen für den doppelten Schlüssel Verschlüsselungsdienst</span><span class="sxs-lookup"><span data-stu-id="e8111-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="e8111-167">Installieren Sie diese Voraussetzungen auf dem Computer, auf dem Sie den DKE-Dienst installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e8111-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="e8111-168">**.Net Core 3,1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="e8111-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="e8111-169">Laden Sie das SDK herunter, und installieren Sie es aus dem [Download .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="e8111-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="e8111-170">**Visual Studio Code**.</span><span class="sxs-lookup"><span data-stu-id="e8111-170">**Visual Studio Code**.</span></span> <span data-ttu-id="e8111-171">Laden Sie Visual Studio Code aus herunter [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="e8111-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="e8111-172">Nachdem Sie installiert haben, führen Sie Visual Studio Code aus, und wählen Sie **View** \> **Extensions**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="e8111-173">Installieren Sie diese Erweiterungen.</span><span class="sxs-lookup"><span data-stu-id="e8111-173">Install these extensions.</span></span>

- <span data-ttu-id="e8111-174">C# für Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e8111-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="e8111-175">NuGet-Paket-Manager</span><span class="sxs-lookup"><span data-stu-id="e8111-175">NuGet Package Manager</span></span>

<span data-ttu-id="e8111-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="e8111-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="e8111-177">Richten Sie mindestens eine [Bereitstellungsmethode](https://insider.office.com/business/deploy)ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="e8111-178">**Git-Ressourcen**.</span><span class="sxs-lookup"><span data-stu-id="e8111-178">**Git resources**.</span></span> <span data-ttu-id="e8111-179">Laden Sie eine der folgenden Optionen herunter, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="e8111-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="e8111-180">Git</span><span class="sxs-lookup"><span data-stu-id="e8111-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="e8111-181">GitHub-Desktop</span><span class="sxs-lookup"><span data-stu-id="e8111-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="e8111-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="e8111-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="e8111-183">**OpenSSL** Sie müssen [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installiert haben, um [Testschlüssel zu generieren](#generate-test-keys) , nachdem Sie DKE bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="e8111-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="e8111-184">Stellen Sie sicher, dass Sie sie ordnungsgemäß aus dem Pfad der Umgebungsvariablen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e8111-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="e8111-185">Weitere Informationen finden Sie beispielsweise unter "Add the Installation Directory to Path" unter https://www.osradar.com/install-openssl-windows/ .</span><span class="sxs-lookup"><span data-stu-id="e8111-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="e8111-186">Zwei wichtige Verschlüsselungs Voraussetzungen für Clientcomputer</span><span class="sxs-lookup"><span data-stu-id="e8111-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="e8111-187">Installieren Sie diese Voraussetzungen auf jedem Clientcomputer, auf dem geschützte Dokumente geschützt und verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e8111-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="e8111-188">**Microsoft Office** Version \*. 12711 oder höher.</span><span class="sxs-lookup"><span data-stu-id="e8111-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="e8111-189">**Azure Information Protection Unified Labelling-Client** Versionen 2.7.93.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="e8111-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="e8111-190">Laden Sie den Unified Labeling-Client von [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)herunter, und installieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="e8111-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="e8111-191">Klonen des DKE GitHub-Repositorys</span><span class="sxs-lookup"><span data-stu-id="e8111-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="e8111-192">Microsoft stellt die DKE-Quelldateien in einem GitHub-Repository bereit.</span><span class="sxs-lookup"><span data-stu-id="e8111-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="e8111-193">Sie klonen das Repository, um das Projekt für die Verwendung in Ihrer Organisation lokal zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8111-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="e8111-194">Das DKE GitHub-Repository befindet sich unter [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="e8111-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="e8111-195">Die folgenden Anweisungen sind für Benutzer mit unerfahrenem git oder Visual Studio Code gedacht:</span><span class="sxs-lookup"><span data-stu-id="e8111-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="e8111-196">Wechseln Sie in Ihrem Browser zu:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="e8111-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="e8111-197">Klicken Sie auf der rechten Seite des Bildschirms auf **Code**.</span><span class="sxs-lookup"><span data-stu-id="e8111-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="e8111-198">Ihre Version der Benutzeroberfläche zeigt möglicherweise eine Schaltfläche " **Klonen" oder "herunterladen** ".</span><span class="sxs-lookup"><span data-stu-id="e8111-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="e8111-199">Wählen Sie dann in der Dropdownliste, die angezeigt wird, das Symbol Kopieren aus, um die URL in Ihre Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="e8111-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="e8111-200">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Klonen des Double Key-Verschlüsselungsdienst-Repositorys von GitHub":::

3. <span data-ttu-id="e8111-202">Wählen Sie in Visual Studio Code **View** die Option \> **Befehls Palette** anzeigen aus, und wählen Sie **git: Clone**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="e8111-203">Um zur Option in der Liste zu wechseln, beginnen Sie mit der Eingabe, `git: clone` um die Einträge zu filtern, und wählen Sie Sie dann im Dropdown aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="e8111-204">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code git: Clone Option":::

4. <span data-ttu-id="e8111-206">Fügen Sie in das Textfeld die URL ein, die Sie aus git kopiert haben, und wählen Sie **aus GitHub Klonen aus**.</span><span class="sxs-lookup"><span data-stu-id="e8111-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="e8111-207">Navigieren Sie im angezeigten Dialogfeld **Ordner auswählen** zu einem Speicherort, und wählen Sie ihn aus, um das Repository zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e8111-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="e8111-208">Wählen Sie an der Eingabeaufforderung **Öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="e8111-209">Das Repository wird in Visual Studio Code geöffnet und zeigt den aktuellen git-Zweig unten links an.</span><span class="sxs-lookup"><span data-stu-id="e8111-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="e8111-210">Der aktuelle Zweig sollte " **Master**" sein.</span><span class="sxs-lookup"><span data-stu-id="e8111-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="e8111-211">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Visual Studio Code Master Verzweigung":::

6. <span data-ttu-id="e8111-213">Wählen Sie das Wort **Master aus,** und wählen Sie dann in der Liste der Verzweigungen **public_preview** aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="e8111-214">Wenn Sie die public_preview Verzweigung auswählen, stellen Sie sicher, dass Sie über die richtigen Dateien zum Erstellen des Projekts verfügen.</span><span class="sxs-lookup"><span data-stu-id="e8111-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="e8111-215">Wenn Sie nicht die richtige Verzweigung auswählen, wird die Bereitstellung nicht erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e8111-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="e8111-216">Sie haben Ihr DKE-Quell-Repository jetzt lokal eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="e8111-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="e8111-217">Ändern Sie als nächstes die [Anwendungseinstellungen](#modify-application-settings) für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="e8111-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="e8111-218">Ändern von Anwendungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e8111-218">Modify application settings</span></span>

<span data-ttu-id="e8111-219">Um den DKE-Dienst bereitzustellen, müssen Sie die folgenden Arten von Anwendungseinstellungen ändern:</span><span class="sxs-lookup"><span data-stu-id="e8111-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="e8111-220">Wichtige Zugriffseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e8111-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="e8111-221">Mandanten-und Schlüsseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="e8111-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="e8111-222">Sie ändern Anwendungseinstellungen in der Datei appsettings.js.</span><span class="sxs-lookup"><span data-stu-id="e8111-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="e8111-223">Diese Datei befindet sich im DoubleKeyEncryptionService Repo, das Sie lokal unter DoubleKeyEncryptionService\src\customer-Key-Store. geklont haben.</span><span class="sxs-lookup"><span data-stu-id="e8111-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="e8111-224">Beispielsweise können Sie in Visual Studio Code die Datei wie in der folgenden Abbildung gezeigt durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="e8111-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Suchen der appsettings.jsDatei für DKE.":::

#### <a name="key-access-settings"></a><span data-ttu-id="e8111-226">Wichtige Zugriffseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e8111-226">Key access settings</span></span>

<span data-ttu-id="e8111-227">Wählen Sie aus, ob e-Mail-oder Rollenautorisierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8111-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="e8111-228">DKE unterstützt immer nur eine dieser Authentifizierungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="e8111-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="e8111-229">**E-Mail-Autorisierung**.</span><span class="sxs-lookup"><span data-stu-id="e8111-229">**Email authorization**.</span></span> <span data-ttu-id="e8111-230">Ermöglicht Ihrer Organisation die Autorisierung des Zugriffs auf Schlüssel nur basierend auf e-Mail-Adressen.</span><span class="sxs-lookup"><span data-stu-id="e8111-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="e8111-231">**Rollenautorisierung**.</span><span class="sxs-lookup"><span data-stu-id="e8111-231">**Role authorization**.</span></span> <span data-ttu-id="e8111-232">Ermöglicht Ihrer Organisation das Autorisieren des Zugriffs auf Schlüssel basierend auf Active Directory Gruppen und erfordert, dass der Webdienst LDAP Abfragen kann.</span><span class="sxs-lookup"><span data-stu-id="e8111-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="e8111-233">So legen Sie die wichtigsten Zugriffseinstellungen für DKE fest:</span><span class="sxs-lookup"><span data-stu-id="e8111-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="e8111-234">Definieren Sie in der Datei **appsettings.jsauf** nur eine der folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e8111-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="e8111-235">Für die e-Mail-Autorisierung suchen Sie die **AuthorizedEmailAddresses** -Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e8111-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="e8111-236">Fügen Sie die e-Mail-Adresse hinzu, die Sie autorisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e8111-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="e8111-237">Trennen Sie mehrere e-Mail-Adressen mit doppelten Anführungszeichen und Kommas.</span><span class="sxs-lookup"><span data-stu-id="e8111-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="e8111-238">Beispiel: **"' AuthorizedEmailAddresses '": ["Email1@Company.com", "Email2@Company.com", email3@Company.com]**</span><span class="sxs-lookup"><span data-stu-id="e8111-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="appsettings.jsauf Datei mit e-Mail-Autorisierungsmethode":::

   - <span data-ttu-id="e8111-240">Für die Rollenautorisierung suchen Sie die **AuthorizedRoles** -Einstellung.</span><span class="sxs-lookup"><span data-stu-id="e8111-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="e8111-241">Definieren Sie mit den ActiveDirectory-Gruppennamen, die Sie autorisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e8111-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="e8111-242">Beispiel: **"AuthorizedRoles": ["group1", "group2", "Gruppe3"]**</span><span class="sxs-lookup"><span data-stu-id="e8111-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsfür die Datei mit der Rollen Autorisierungsmethode":::

2. <span data-ttu-id="e8111-244">Entfernen Sie die Einstellung, die für die ausgewählte Autorisierungsmethode nicht relevant ist.</span><span class="sxs-lookup"><span data-stu-id="e8111-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="e8111-245">Mandanten-und Schlüsseleinstellungen</span><span class="sxs-lookup"><span data-stu-id="e8111-245">Tenant and key settings</span></span>

<span data-ttu-id="e8111-246">DKE-Mandanten-und Key-Einstellungen befinden sich in der Datei **appsettings.js** und der **Startup.cs** -Datei.</span><span class="sxs-lookup"><span data-stu-id="e8111-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="e8111-247">Ändern Sie in der Datei **appsettings.jsauf** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="e8111-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="e8111-248">**ValidIssuers**.</span><span class="sxs-lookup"><span data-stu-id="e8111-248">**ValidIssuers**.</span></span> <span data-ttu-id="e8111-249">Ersetzen `<tenantid>` Sie durch ihre Mandanten-GUID.</span><span class="sxs-lookup"><span data-stu-id="e8111-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="e8111-250">**JwtAudience**.</span><span class="sxs-lookup"><span data-stu-id="e8111-250">**JwtAudience**.</span></span> <span data-ttu-id="e8111-251">Ersetzen Sie `<yourhostname>` durch den Hostnamen des Computers, auf dem der DKE-Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8111-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="e8111-252">Der Wert für JwtAudience muss *exakt*mit dem Namen des Hosts übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="e8111-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="e8111-253">Sie können **localhost: 5000** beim Debuggen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8111-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="e8111-254">Wenn Sie das Debuggen abgeschlossen haben, sollten Sie diesen Wert jedoch auf den Hostnamen des Servers aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e8111-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="e8111-255">**LDAPPath**.</span><span class="sxs-lookup"><span data-stu-id="e8111-255">**LDAPPath**.</span></span> <span data-ttu-id="e8111-256">Legen Sie den Wert wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="e8111-256">Set the value as follows:</span></span>

  - <span data-ttu-id="e8111-257">Wenn Sie die Rollenautorisierung verwenden, geben Sie die LDAP-Domäne ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="e8111-258">Wenn Sie e-Mail-Autorisierung verwenden, lassen Sie diesen Wert leer.</span><span class="sxs-lookup"><span data-stu-id="e8111-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="e8111-259">Weitere Informationen finden Sie unter [Key Access Settings](#key-access-settings).</span><span class="sxs-lookup"><span data-stu-id="e8111-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="e8111-260">**TestKeys: Name**.</span><span class="sxs-lookup"><span data-stu-id="e8111-260">**TestKeys:Name**.</span></span> <span data-ttu-id="e8111-261">Geben Sie einen Namen für den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-261">Enter a name for your key.</span></span> <span data-ttu-id="e8111-262">Beispiel: **TestKey1**</span><span class="sxs-lookup"><span data-stu-id="e8111-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="e8111-263">**TestKeys: ID**. Erstellen Sie eine GUID, und geben Sie Sie als **TestKeys: ID-** Wert ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="e8111-264">Beispiel: **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span><span class="sxs-lookup"><span data-stu-id="e8111-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="e8111-265">Sie können eine Website wie den [Online-GUID-Generator](https://guidgenerator.com/) verwenden, um eine GUID nach dem Zufallsprinzip zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e8111-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="e8111-266">Generieren von Test Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="e8111-266">Generate test keys</span></span>

<span data-ttu-id="e8111-267">Sobald Ihre Anwendungseinstellungen definiert sind, können Sie öffentliche und private Testschlüssel generieren.</span><span class="sxs-lookup"><span data-stu-id="e8111-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="e8111-268">So generieren Sie Schlüssel:</span><span class="sxs-lookup"><span data-stu-id="e8111-268">To generate keys:</span></span>

1. <span data-ttu-id="e8111-269">Führen Sie im Windows-Startmenü die OpenSSL-Eingabeaufforderung aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="e8111-270">Wechseln Sie zu dem Ordner, in dem Sie die Testschlüssel speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="e8111-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="e8111-271">Die Dateien, die Sie erstellen, indem Sie die Schritte in dieser Aufgabe ausführen, werden im gleichen Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8111-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="e8111-272">Generieren Sie den neuen Testschlüssel.</span><span class="sxs-lookup"><span data-stu-id="e8111-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="e8111-273">Generiert den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="e8111-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="e8111-274">Generieren Sie den öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="e8111-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="e8111-275">Öffnen Sie in einem Text-Editor **pubkeyonly. PEM**.</span><span class="sxs-lookup"><span data-stu-id="e8111-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="e8111-276">Kopieren Sie den gesamten Inhalt der Datei **pubkeyonly. PEM** , mit Ausnahme der ersten und der letzten Zeile, in den **PublicPem** -Abschnitt der Datei **appsettings.js** .</span><span class="sxs-lookup"><span data-stu-id="e8111-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="e8111-277">Öffnen Sie in einem Text-Editor **privkeynopass. PEM**.</span><span class="sxs-lookup"><span data-stu-id="e8111-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="e8111-278">Kopieren Sie den gesamten Inhalt der Datei **privkeynopass. PEM** , mit Ausnahme der ersten und der letzten Zeile, in den **PrivatePem** -Abschnitt der Datei **appsettings.js** .</span><span class="sxs-lookup"><span data-stu-id="e8111-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="e8111-279">Entfernen Sie alle Leerzeichen und Zeilen Umrisse sowohl im **PublicPem** -als auch im **PrivatePem** -Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="e8111-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e8111-280">Wenn Sie diesen Inhalt kopieren, löschen Sie keine PEM-Daten.</span><span class="sxs-lookup"><span data-stu-id="e8111-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="e8111-281">Öffnen Sie die Datei **Startup.cs** , und suchen Sie nach den folgenden Zeilen:</span><span class="sxs-lookup"><span data-stu-id="e8111-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="e8111-282">Ersetzen Sie diese Zeilen durch den folgenden Text:</span><span class="sxs-lookup"><span data-stu-id="e8111-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="e8111-283">Die Endergebnisse sollten ähnlich wie in der folgenden Abbildung aussehen.</span><span class="sxs-lookup"><span data-stu-id="e8111-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="Startup.cs-Datei für die öffentliche Vorschau":::

<span data-ttu-id="e8111-285">Jetzt sind Sie fertig, um [Ihr DKE-Projekt zu erstellen](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="e8111-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="e8111-286">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="e8111-286">Build the project</span></span>

<span data-ttu-id="e8111-287">Verwenden Sie die folgenden Anweisungen, um das DKE-Projekt lokal zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="e8111-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="e8111-288">Wählen Sie in Visual Studio Code im DKE-Dienst-Repository **View** die Option \> **Befehls Palette** anzeigen aus, und geben Sie dann an der Eingabeaufforderung **Erstellen** ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="e8111-289">Wählen Sie in der Liste **Aufgaben: Build-Task ausführen**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="e8111-290">Wenn keine Build-Tasks gefunden werden, wählen Sie Create **Task konfigurieren** aus, und erstellen Sie wie folgt einen für .net Core.</span><span class="sxs-lookup"><span data-stu-id="e8111-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Konfigurieren fehlender Build-Aufgabe für .net":::

   1. <span data-ttu-id="e8111-292">Wählen Sie **tasks.jsaus Vorlage erstellen aus**.</span><span class="sxs-lookup"><span data-stu-id="e8111-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Erstellen tasks.jsDatei aus der Vorlage für DKE":::

   2. <span data-ttu-id="e8111-294">Wählen Sie in der Liste der Vorlagentypen **.net Core**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Erstellen tasks.jsDatei aus der Vorlage für DKE":::

   3. <span data-ttu-id="e8111-296">Suchen Sie im Abschnitt erstellen nach dem Pfad zur Datei **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="e8111-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="e8111-297">Wenn er nicht vorhanden ist, fügen Sie die folgende Reihe hinzu:</span><span class="sxs-lookup"><span data-stu-id="e8111-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="e8111-298">Führen Sie den Build erneut aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-298">Run the build again.</span></span>

1. <span data-ttu-id="e8111-299">Stellen Sie sicher, dass im Ausgabefenster keine roten Fehler vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e8111-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="e8111-300">Wenn rote Fehler vorliegen, überprüfen Sie die Konsolenausgabe.</span><span class="sxs-lookup"><span data-stu-id="e8111-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="e8111-301">Stellen Sie sicher, dass Sie alle vorherigen Schritte ordnungsgemäß abgeschlossen haben und die richtigen Build-Versionen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="e8111-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="e8111-302">**Ausführen** \> **Starten** Sie das Debuggen, um den Prozess zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="e8111-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="e8111-303">Wenn Sie zur Auswahl einer Umgebung aufgefordert werden, wählen Sie **.net Core**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="e8111-304">Der .net Core-Debugger wird in der Regel in gestartet **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="e8111-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="e8111-305">Um den Testschlüssel anzuzeigen, wechseln Sie zu **https://localhost:5001** , und fügen Sie einen Schrägstrich (/) und den Namen Ihres Schlüssels an.</span><span class="sxs-lookup"><span data-stu-id="e8111-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="e8111-306">Zum Beispiel:**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="e8111-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="e8111-307">Der Schlüssel sollte im JSON-Format angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e8111-307">The key should display in JSON format.</span></span>

<span data-ttu-id="e8111-308">Ihr Setup ist nun abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e8111-308">Your setup is now complete.</span></span> <span data-ttu-id="e8111-309">Stellen Sie vor dem Veröffentlichen des Keystores in appsettings.jsauf für die JwtAudience-Einstellung sicher, dass der Wert für Hostname genau mit dem Namen des App-Diensthosts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e8111-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="e8111-310">Möglicherweise haben Sie es zu localhost geändert, um die Problembehandlung für den Build auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e8111-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="e8111-311">Veröffentlichen des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="e8111-311">Publish the key store</span></span>

<span data-ttu-id="e8111-312">In den folgenden Schritten wird beschrieben, wie Sie eine Azure-App-Dienstinstanz erstellen, die ihre DKE-Bereitstellung hostet, und wie Sie die generierten Schlüssel in Azure veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="e8111-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="e8111-313">So erstellen Sie eine Azure-Webanwendungs Instanz zum Hosten Ihrer DKE-Bereitstellung:</span><span class="sxs-lookup"><span data-stu-id="e8111-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="e8111-314">Melden Sie sich in Ihrem Browser beim [Microsoft Azure-Portal](https://ms.portal.azure.com)an, und wechseln Sie zu **App-Dienste**  >  **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e8111-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="e8111-315">Wählen Sie Ihre Abonnement-und Ressourcengruppe aus, und definieren Sie die Details der Instanz.</span><span class="sxs-lookup"><span data-stu-id="e8111-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="e8111-316">Geben Sie den Hostnamen des Computers ein, auf dem Sie den DKE-Dienst installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e8111-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="e8111-317">Stellen Sie sicher, dass der Name dem Namen entspricht, der für die JwtAudience-Einstellung in der Datei [**appsettings.js**](#tenant-and-key-settings) für festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8111-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="e8111-318">Der Wert, den Sie für den Namen angeben, ist auch der WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="e8111-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="e8111-319">Wählen Sie für **veröffentlichen**den **Code**aus, und wählen Sie für **Laufzeitstapel** **.net Core 3,1**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="e8111-320">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Hinzufügen des App-Diensts":::

1. <span data-ttu-id="e8111-322">Wählen Sie unten auf der Seite **überprüfen + erstellen**aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="e8111-323">Führen Sie einen der folgenden Schritte aus, um die generierten Schlüssel in Azure zu veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="e8111-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="e8111-324">Veröffentlichen über ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e8111-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="e8111-325">Veröffentlichen über FTP</span><span class="sxs-lookup"><span data-stu-id="e8111-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="e8111-326">Veröffentlichen über Visual Studio 2019 oder höher</span><span class="sxs-lookup"><span data-stu-id="e8111-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="e8111-327">Veröffentlichen in einem lokalen System</span><span class="sxs-lookup"><span data-stu-id="e8111-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="e8111-328">Möglicherweise bevorzugen Sie andere Methoden zum Bereitstellen der Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="e8111-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="e8111-329">Wählen Sie die Methode aus, die für Ihre Organisation am besten geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="e8111-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="e8111-330">Die [Veröffentlichung über Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) und an ein [Lokales System](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) wird in der [ASP .NET-Dokumentation](https://docs.microsoft.com/aspnet/core/)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8111-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="e8111-331">Wenn Sie eine dieser Methoden verwenden, öffnen Sie die Anweisungen in einer separaten Registerkarte, damit Sie nach Abschluss des Verfahrens problemlos zurückkehren können.</span><span class="sxs-lookup"><span data-stu-id="e8111-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="e8111-332">Veröffentlichen über ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e8111-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="e8111-333">Navigieren Sie in das Verzeichnis `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="e8111-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="e8111-334">Beispiel: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e8111-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="e8111-335">Wechseln Sie in der CodeBase für den Schlüsselspeicher zum Ordner **Customer-Key-store\src\customer-Key-Store** , und vergewissern Sie sich, dass dieser Ordner die Datei **customerkeystore. csproj** enthält.</span><span class="sxs-lookup"><span data-stu-id="e8111-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="e8111-336">Ausführen: **dotnet veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="e8111-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="e8111-337">Das Ausgabefenster zeigt das Verzeichnis an, in dem die Veröffentlichung bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8111-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="e8111-338">Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="e8111-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="e8111-339">Senden Sie alle Dateien im Veröffentlichungsverzeichnis an eine ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="e8111-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="e8111-340">Stellen Sie beim Erstellen der ZIP-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der ZIP-Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="e8111-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="e8111-341">Ziehen Sie die ZIP-Datei, die Sie erstellen, auf die ZipDeployUI-Website, die Sie oben geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="e8111-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="e8111-342">Beispiel: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="e8111-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="e8111-343">DKE wird bereitgestellt, und Sie können zu den Test Schlüsseln navigieren, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e8111-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="e8111-344">Über [prüfen Sie Ihre Bereitstellung](#validate-your-deployment) weiter unten.</span><span class="sxs-lookup"><span data-stu-id="e8111-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="e8111-345">Veröffentlichen über FTP</span><span class="sxs-lookup"><span data-stu-id="e8111-345">Publish via FTP</span></span>

1. <span data-ttu-id="e8111-346">Stellen Sie eine Verbindung mit dem [oben](#publish-the-key-store)erstellten App-Dienst her.</span><span class="sxs-lookup"><span data-stu-id="e8111-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="e8111-347">Wechseln Sie in Ihrem Browser zu: **Azure Portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="e8111-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="e8111-348">Kopieren Sie die angezeigten Verbindungszeichenfolgen in eine lokale Datei.</span><span class="sxs-lookup"><span data-stu-id="e8111-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="e8111-349">Sie verwenden diese Zeichenfolgen, um eine Verbindung zum Webdienst des Webanwendungs herzustellen und Dateien über FTP hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="e8111-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="e8111-350">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Kopieren von Verbindungszeichenfolgen aus dem FTP-Dashboard":::

1. <span data-ttu-id="e8111-352">Wechseln Sie in der CodeBase für den Schlüsselspeicher zum **Verzeichnis Customer-Key-store\src\customer-Key-Store**.</span><span class="sxs-lookup"><span data-stu-id="e8111-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="e8111-353">Stellen Sie sicher, dass dieses Verzeichnis die Datei **customerkeystore. csproj** enthält.</span><span class="sxs-lookup"><span data-stu-id="e8111-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="e8111-354">Ausführen: **dotnet veröffentlichen**</span><span class="sxs-lookup"><span data-stu-id="e8111-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="e8111-355">Die Ausgabe enthält das Verzeichnis, in dem die Veröffentlichung bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e8111-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="e8111-356">Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="e8111-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="e8111-357">Senden Sie alle Dateien im Veröffentlichungsverzeichnis in eine ZIP-Datei.</span><span class="sxs-lookup"><span data-stu-id="e8111-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="e8111-358">Stellen Sie beim Erstellen der ZIP-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der ZIP-Datei befinden.</span><span class="sxs-lookup"><span data-stu-id="e8111-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="e8111-359">Verwenden Sie von Ihrem FTP-Client die Verbindungsinformationen, die Sie zum Herstellen einer Verbindung mit Ihrem App-Dienst kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="e8111-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="e8111-360">Laden Sie die ZIP-Datei, die Sie im vorherigen Schritt erstellt haben, in das Stammverzeichnis Ihrer Webanwendung hoch.</span><span class="sxs-lookup"><span data-stu-id="e8111-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="e8111-361">DKE wird bereitgestellt, und Sie können zu den Test Schlüsseln navigieren, die Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e8111-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="e8111-362">Als nächstes [validieren Sie Ihre Bereitstellung](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="e8111-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="e8111-363">Überprüfen der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="e8111-363">Validate your deployment</span></span>

<span data-ttu-id="e8111-364">Nachdem Sie DKE mit einer der oben beschriebenen Methoden bereitgestellt haben, überprüfen Sie die Bereitstellung und die Schlüsselspeicher Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e8111-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="e8111-365">Ausführen</span><span class="sxs-lookup"><span data-stu-id="e8111-365">Run:</span></span>

<span data-ttu-id="e8111-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="e8111-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="e8111-367">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-367">For example:</span></span>

<span data-ttu-id="e8111-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="e8111-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="e8111-369">Stellen Sie sicher, dass in der Ausgabe keine Fehler angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e8111-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="e8111-370">Wenn Sie fertig sind, [registrieren Sie Ihren Schlüsselspeicher](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="e8111-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="e8111-371">Registrieren des Schlüsselspeichers</span><span class="sxs-lookup"><span data-stu-id="e8111-371">Register your key store</span></span>

<span data-ttu-id="e8111-372">Mit den folgenden Schritten können Sie den Schlüsselspeicher registrieren.</span><span class="sxs-lookup"><span data-stu-id="e8111-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="e8111-373">Das Registrieren des Schlüsselspeichers ist der letzte Schritt bei der Bereitstellung von DKE, bevor Sie mit dem Erstellen von Beschriftungen beginnen können.</span><span class="sxs-lookup"><span data-stu-id="e8111-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="e8111-374">So registrieren Sie Ihren Schlüsselspeicher:</span><span class="sxs-lookup"><span data-stu-id="e8111-374">To register your key store:</span></span>

1. <span data-ttu-id="e8111-375">Öffnen Sie in Ihrem Browser das [Microsoft Azure-Portal](https://ms.portal.azure.com/), und wechseln Sie zu **alle Services** - \> **Identitäts** - \> **App-Registrierungen**.</span><span class="sxs-lookup"><span data-stu-id="e8111-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="e8111-376">Wählen Sie **neue Registrierung**aus, und geben Sie einen aussagekräftigen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="e8111-377">Wählen Sie in den angezeigten Optionen einen Kontotyp aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="e8111-378">Wenn Sie Microsoft Azure mit einer nicht benutzerdefinierten Domäne wie **onmicrosoft.com**verwenden, wählen Sie **Konten nur in diesem Organisations Verzeichnis aus (nur Microsoft – einzelner Mandant).**</span><span class="sxs-lookup"><span data-stu-id="e8111-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="e8111-379">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Neue APP-Registrierung":::

4. <span data-ttu-id="e8111-381">Wählen Sie unten auf der Seite **registrieren** aus, um die neue APP-Registrierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8111-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="e8111-382">Wählen Sie in der neuen App-Registrierung im linken Bereich unter **Verwalten**die Option **Authentifizierung**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="e8111-383">Wählen Sie **Plattform hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="e8111-384">Klicken Sie im Popup " **configure Platforms** " auf " **Internet**".</span><span class="sxs-lookup"><span data-stu-id="e8111-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="e8111-385">Geben Sie unter **Umleitungs-URIs** den URI des doppelten Schlüssel Verschlüsselungs Diensts ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="e8111-386">Geben Sie die APP-Dienst-URL ein, einschließlich des Hostnamens und der Domäne.</span><span class="sxs-lookup"><span data-stu-id="e8111-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="e8111-387">Beispiel: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="e8111-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="e8111-388">Die eingegebene URL muss mit dem Hostnamen übereinstimmen, in dem der Schlüsselspeicher bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e8111-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="e8111-389">Wenn Sie lokal mit Visual Studio testen, verwenden Sie **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="e8111-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="e8111-390">In allen Fällen muss das Schema **https**sein.</span><span class="sxs-lookup"><span data-stu-id="e8111-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="e8111-391">Stellen Sie sicher, dass der Hostname genau mit dem Hostnamen des App-Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e8111-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="e8111-392">Möglicherweise haben Sie es zu localhost geändert, um die Problembehandlung für den Build auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e8111-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="e8111-393">In appsettings.jsauf ist dies der Hostname, den Sie als Wert für die Einstellung JwtAudience identifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="e8111-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="e8111-394">Aktivieren Sie unter **implizite Gewährung**das Kontrollkästchen **ID-Token** .</span><span class="sxs-lookup"><span data-stu-id="e8111-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="e8111-395">Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e8111-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="e8111-396">Wählen Sie im linken Bereich **eine API verfügbar machen**aus, und wählen Sie dann neben Anwendungs-ID-URI die Option **festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="e8111-397">Wählen Sie auf der Seite **eine API verfügbar machen** im Bereich **durch diese API definierte Bereiche** die Option **Bereich hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="e8111-398">Im neuen Bereich:</span><span class="sxs-lookup"><span data-stu-id="e8111-398">In the new scope:</span></span>

    1. <span data-ttu-id="e8111-399">Definieren Sie den Bereichsnamen als **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="e8111-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="e8111-400">Wählen Sie die Administratoren und Benutzer, die zustimmen können.</span><span class="sxs-lookup"><span data-stu-id="e8111-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="e8111-401">Definieren Sie alle verbleibenden erforderlichen Werte.</span><span class="sxs-lookup"><span data-stu-id="e8111-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="e8111-402">Wählen Sie **Bereich hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="e8111-402">Select **Add scope.**</span></span>

    <span data-ttu-id="e8111-403">Wählen Sie oben **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e8111-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="e8111-404">Wählen Sie weiterhin auf der Seite **eine API verfügbar machen** im Bereich **autorisierte Clientanwendungen** die Option **Clientanwendung hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="e8111-405">In der neuen Clientanwendung:</span><span class="sxs-lookup"><span data-stu-id="e8111-405">In the new client application:</span></span>

    1. <span data-ttu-id="e8111-406">Definieren Sie die Client-ID als **d3590ed6-52b3-4102-Aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="e8111-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="e8111-407">Dieser Wert ist die Microsoft Office-Client-ID und ermöglicht Office das Abrufen eines Zugriffstokens für den Schlüsselspeicher.</span><span class="sxs-lookup"><span data-stu-id="e8111-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="e8111-408">Wählen Sie unter **autorisierte Bereiche**den **user_impersonation** Bereich aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="e8111-409">Wählen Sie **Anwendung hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e8111-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="e8111-410">Wählen Sie oben **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e8111-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="e8111-411">Ihr DKE-Schlüsselspeicher ist jetzt registriert.</span><span class="sxs-lookup"><span data-stu-id="e8111-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="e8111-412">Fahren Sie mit dem [Erstellen von Beschriftungen mithilfe von DKE](#create-labels-using-dke)fort.</span><span class="sxs-lookup"><span data-stu-id="e8111-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="e8111-413">Erstellen von Beschriftungen mithilfe von DKE</span><span class="sxs-lookup"><span data-stu-id="e8111-413">Create labels using DKE</span></span>

<span data-ttu-id="e8111-414">Nachdem Sie den Schlüsselspeicher registriert haben, richten Sie die Sensitivitäts Bezeichnungen im Microsoft 365 Compliance Center ein, und wenden Sie diese Bezeichnungen auf die doppelte Schlüssel Verschlüsselung an.</span><span class="sxs-lookup"><span data-stu-id="e8111-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="e8111-415">Wählen Sie auf der Benutzeroberfläche für die Bezeichnungs Erstellung die Option **Doppelschlüssel Verschlüsselung verwenden** aus, und geben Sie die Endpunkt-URL für den Schlüssel ein.</span><span class="sxs-lookup"><span data-stu-id="e8111-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="e8111-416">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e8111-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Wählen Sie Doppelschlüssel Verschlüsselung im Microsoft 365 Compliance Center verwenden aus.":::

<span data-ttu-id="e8111-418">Alle DKE-Bezeichnungen, die Sie hinzufügen, werden für Benutzer in den neuesten Versionen von Microsoft 365 apps for Enterprise angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e8111-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="e8111-419">Es kann bis zu 24 Stunden dauern, bis die Clients mit den neuen Bezeichnungen aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e8111-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="e8111-420">Aktivieren von DKE in Ihrem Client</span><span class="sxs-lookup"><span data-stu-id="e8111-420">Enable DKE in your client</span></span>

<span data-ttu-id="e8111-421">Wenn Ihre DKE-Beschriftungen nicht unter dem Menüband für die Vertraulichkeit in Microsoft Office angezeigt werden, ist der Client möglicherweise nicht DKE aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8111-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="e8111-422">Aktivieren Sie DKE für Ihren Client, indem Sie die folgenden Registrierungsschlüssel hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e8111-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
