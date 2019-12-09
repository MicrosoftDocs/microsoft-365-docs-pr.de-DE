---
title: ISO/IEC 27017:2015-Verhaltenskodex für Informationssicherheitskontrollen
description: Microsoft-Clouddienste haben diesen Verhaltenskodex für Informationssicherheitskontrollen implementiert.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: f58322fe915c811ba2613bef98116f910abc03d1
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859685"
---
# <a name="isoiec-270172015-code-of-practice-for-information-security-controls"></a><span data-ttu-id="70bab-104">ISO/IEC 27017:2015 Verhaltenskodex für Informationssicherheitskontrollen</span><span class="sxs-lookup"><span data-stu-id="70bab-104">ISO/IEC 27017:2015 Code of Practice for Information Security Controls</span></span>

## <a name="iso-iec-27017-overview"></a><span data-ttu-id="70bab-105">Übersicht über ISO-IEC 27017</span><span class="sxs-lookup"><span data-stu-id="70bab-105">ISO-IEC 27017 Overview</span></span>

<span data-ttu-id="70bab-106">Der ISO/IEC 27017:2015-Verhaltenskodex ist als Referenz für Organisationen vorgesehen, um sie während der Implementierung eines Systems für die Verwaltung der Cloud Computing-Informationssicherheit gemäß ISO/IEC 27002:2013 bei der Auswahl von Informationssicherheitskontrollen für Clouddienste zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="70bab-106">The ISO/IEC 27017:2015 code of practice is designed for organizations to use as a reference for selecting cloud services information security controls when implementing a cloud computing information security management system based on ISO/IEC 27002:2013.</span></span> <span data-ttu-id="70bab-107">Er kann auch von Cloud Service-Anbietern als Leitfaden zum Implementieren von allgemein anerkannten Schutzkontrollen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="70bab-107">It can also be used by cloud service providers as a guidance document for implementing commonly accepted protection controls.</span></span>

<span data-ttu-id="70bab-108">Dieser internationale Standard stellt zusätzliche cloudspezifische Implementierungsanweisungen gemäß ISO/IEC 27002 zur Verfügung und bietet weitere Kontrollen, um cloudspezifische Bedrohungen der Informationssicherheit und Risiken in Bezug auf die Abschnitte 5 bis 18 in ISO/IEC 27002: 2013 für Kontrollen, Implementierungsrichtlinien und andere Informationen zu mindern.</span><span class="sxs-lookup"><span data-stu-id="70bab-108">This international standard provides additional cloud-specific implementation guidance based on ISO/IEC 27002, and provides additional controls to address cloud-specific information security threats and risks referring to clauses 5–18 in ISO/IEC 27002: 2013 for controls, implementation guidance, and other information.</span></span> <span data-ttu-id="70bab-109">Insbesondere stellt dieser Standard Anleitungen zu 37 Kontrollen in ISO/IEC 27002 zur Verfügung und enthält außerdem sieben neue Kontrollen, die nicht in ISO/IEC 27002 dupliziert sind.</span><span class="sxs-lookup"><span data-stu-id="70bab-109">Specifically, this standard provides guidance on 37 controls in ISO/IEC 27002, and it also features seven new controls that are not duplicated in ISO/IEC 27002.</span></span> <span data-ttu-id="70bab-110">Diese neuen Kontrollen beziehen sich auf die folgenden wichtigen Bereiche:</span><span class="sxs-lookup"><span data-stu-id="70bab-110">These new controls address the following important areas:</span></span>

- <span data-ttu-id="70bab-111">Gemeinsame Rollen und Pflichten innerhalb einer Cloud Computing-Umgebung</span><span class="sxs-lookup"><span data-stu-id="70bab-111">Shared roles and responsibilities within a cloud computing environment</span></span>
- <span data-ttu-id="70bab-112">Entfernen und Rückgabe von Kundenressourcen in Cloud Services nach Vertragsende</span><span class="sxs-lookup"><span data-stu-id="70bab-112">Removal and return of cloud service customer assets upon contract termination</span></span>
- <span data-ttu-id="70bab-113">Schutz und Trennung der virtuellen Umgebung eines Kunden von der Umgebung anderer Kunden</span><span class="sxs-lookup"><span data-stu-id="70bab-113">Protection and separation of a customer’s virtual environment from that of other customers</span></span>
- <span data-ttu-id="70bab-114">Erfordernisse zur Stärkung virtueller Maschinen um Geschäftsanforderungen zu erfüllen</span><span class="sxs-lookup"><span data-stu-id="70bab-114">Virtual machine hardening requirements to meet business needs</span></span>
- <span data-ttu-id="70bab-115">Verfahren für administrative Abläufe einer Cloud Computing-Umgebung</span><span class="sxs-lookup"><span data-stu-id="70bab-115">Procedures for administrative operations of a cloud computing environment</span></span>
- <span data-ttu-id="70bab-116">Überwachung relevanter Aktivitäten innerhalb einer Cloud Computing-Umgebung durch den Kunden</span><span class="sxs-lookup"><span data-stu-id="70bab-116">Enabling customers to monitor relevant activities within a cloud computing environment</span></span>
- <span data-ttu-id="70bab-117">Ausrichtung der Sicherheitsverwaltung für virtuelle und physische Netzwerke</span><span class="sxs-lookup"><span data-stu-id="70bab-117">Alignment of security management for virtual and physical networks</span></span>

## <a name="microsoft-and-isoiec-27017"></a><span data-ttu-id="70bab-118">Microsoft und ISO/IEC 27017</span><span class="sxs-lookup"><span data-stu-id="70bab-118">Microsoft and ISO/IEC 27017</span></span>

<span data-ttu-id="70bab-119">ISO/IEC 27017 ist einzigartig, da es Anleitungen für Anbieter und Kunden von Clouddiensten bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="70bab-119">ISO/IEC 27017 is unique in providing guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="70bab-120">Der Standard stellt außerdem Cloud Service-Kunden praktische Informationen im Hinblick auf ihre Erwartungen an Cloud Service-Anbieter zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="70bab-120">It also provides cloud service customers with practical information on what they should expect from cloud service providers.</span></span> <span data-ttu-id="70bab-121">Kunden können die Vorteile von ISO/IEC 27017 direkt nutzen, indem sie sich der gemeinsamen Verantwortung in der Cloud bewusst sind.</span><span class="sxs-lookup"><span data-stu-id="70bab-121">Customers can benefit directly from ISO/IEC 27017 by ensuring they understand the shared responsibilities in the cloud.</span></span>

<span data-ttu-id="70bab-122">Erfahren Sie mehr über die Vorteile von ISO/IEC-27017 für die Microsoft Cloud: [ISO/IEC 27017: Verhaltenskodex für Informationssicherheitskontrollen herunterladen](https://aka.ms/iso27017-backgrounder)</span><span class="sxs-lookup"><span data-stu-id="70bab-122">Learn about the benefits of ISO/IEC 27017 on the Microsoft Cloud: [Download the ISO/IEC 27017: Code of Practice for Information Security Controls](https://aka.ms/iso27017-backgrounder)</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="70bab-123">In-Scope-Cloud-Dienste von Microsoft</span><span class="sxs-lookup"><span data-stu-id="70bab-123">Microsoft in-scope cloud services</span></span>

- [<span data-ttu-id="70bab-124">Azure und Azure Government und Azure Deutschland</span><span class="sxs-lookup"><span data-stu-id="70bab-124">Azure, Azure Government, and Azure Germany</span></span>](https://aka.ms/AzureCompliance)
- <span data-ttu-id="70bab-125">Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="70bab-125">Cloud App Security</span></span>
- [<span data-ttu-id="70bab-126">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="70bab-126">Dynamics 365</span></span>](https://aka.ms/d365-compliance-list)
- <span data-ttu-id="70bab-127">Genomics</span><span class="sxs-lookup"><span data-stu-id="70bab-127">Genomics</span></span>
- <span data-ttu-id="70bab-128">Graph</span><span class="sxs-lookup"><span data-stu-id="70bab-128">Graph</span></span>
- <span data-ttu-id="70bab-129">Intune</span><span class="sxs-lookup"><span data-stu-id="70bab-129">Intune</span></span>
- <span data-ttu-id="70bab-130">Microsoft Flow-Clouddienst als eigenständiger Dienst oder in einem firmenspezifischen Office 365- oder Dynamics 365-Plan bzw. einer -Anwendungssuite enthalten</span><span class="sxs-lookup"><span data-stu-id="70bab-130">Microsoft Flow cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="70bab-131">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense und Office 365 Deutschland</span><span class="sxs-lookup"><span data-stu-id="70bab-131">Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense, and Office 365 Germany</span></span>
- <span data-ttu-id="70bab-132">PowerApps-Clouddienst als eigenständiger Dienst oder in einem firmenspezifischen Office 365- oder Dynamics 365-Plan bzw. einer -Anwendungssuite enthalten</span><span class="sxs-lookup"><span data-stu-id="70bab-132">PowerApps cloud service either as a standalone service or as included in an Office 365 or Dynamics 365 branded plan or suite</span></span>
- <span data-ttu-id="70bab-133">Power BI-Clouddienst entweder als eigenständiger Dienst oder als Bestandteil eines Office 365 Markenplans oder einer Office 365 Suite</span><span class="sxs-lookup"><span data-stu-id="70bab-133">Power BI cloud service either as a standalone service or as included in an Office 365 branded plan or suite</span></span>
- <span data-ttu-id="70bab-134">Sehen Sie sich eine [detaillierten Liste](https://go.microsoft.com/fwlink/p/?linkid=2077751) der abgedeckten Dienste in Office 365 an</span><span class="sxs-lookup"><span data-stu-id="70bab-134">See a [detailed list](https://go.microsoft.com/fwlink/p/?linkid=2077751) of covered services in Office 365</span></span>

## <a name="audits-reports-and-certificates"></a><span data-ttu-id="70bab-135">Prüfungen, Berichte und Zertifikate</span><span class="sxs-lookup"><span data-stu-id="70bab-135">Audits, reports, and certificates</span></span>

<span data-ttu-id="70bab-136">Microsoft-Clouddienste werden einmal jährlich im Rahmen des Zertifizierungsprozesses nach ISO/IEC 27001:2013 hinsichtlich des ISO/IEC 27017:2015-Verhaltenskodex überprüft.</span><span class="sxs-lookup"><span data-stu-id="70bab-136">Microsoft cloud services are audited once a year for the ISO/IEC 27017:2015 code of practice as part of the certification process for ISO/IEC 27001:2013.</span></span>

- [<span data-ttu-id="70bab-137">Azure ISO 27017-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="70bab-137">Azure ISO 27017 Certificate</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078005)
- [<span data-ttu-id="70bab-138">Azure ISO 27017-Bewertungsbericht</span><span class="sxs-lookup"><span data-stu-id="70bab-138">Azure ISO 27017 Assessment report</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2078010)
- [<span data-ttu-id="70bab-139">Azure ISO 27017-Erklärung zur Anwendbarkeit</span><span class="sxs-lookup"><span data-stu-id="70bab-139">Azure ISO 27017 Statement of Applicability</span></span>](https://aka.ms/azureiso27017StatementofApplicability)
- [<span data-ttu-id="70bab-140">Office 365 ISO 27001, 27018- und 27017-Prüfbericht</span><span class="sxs-lookup"><span data-stu-id="70bab-140">Office 365 ISO 27001, 27018, and 27017 Audit Assessment Report</span></span>](https://aka.ms/o365isoreport)

## <a name="frequently-asked-questions"></a><span data-ttu-id="70bab-141">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="70bab-141">Frequently asked questions</span></span>

<span data-ttu-id="70bab-142">Für wen gilt der Standard?</span><span class="sxs-lookup"><span data-stu-id="70bab-142">To whom does the standard apply?</span></span>

<span data-ttu-id="70bab-143">Dieser Verhaltenskodex stellt Kontrollen und Implementierungsanleitungen für Anbieter und Kunden von Clouddiensten bereit.</span><span class="sxs-lookup"><span data-stu-id="70bab-143">This code of practice provides controls and implementation guidance for both cloud service providers and cloud service customers.</span></span> <span data-ttu-id="70bab-144">Er ist ähnlich strukturiert wie ISO/IEC 27002:2013.</span><span class="sxs-lookup"><span data-stu-id="70bab-144">It is structured in a format similar to ISO/IEC 27002:2013.</span></span>

<span data-ttu-id="70bab-145">**Wo kann ich die Complianceinformationen von Microsoft für ISO/IEC 27017:2015 anzeigen?**</span><span class="sxs-lookup"><span data-stu-id="70bab-145">**Where can I view Microsoft’s compliance information for ISO/IEC 27017:2015?**</span></span>

<span data-ttu-id="70bab-146">Sie können das [ISO/IEC 27017:2015-Zertifikat](https://aka.ms/azureiso27017) für Azure, Intune und Power BI herunterladen.</span><span class="sxs-lookup"><span data-stu-id="70bab-146">You can download the [ISO/IEC 27017:2015 certificate](https://aka.ms/azureiso27017) for Azure, Intune, and Power BI.</span></span>

<span data-ttu-id="70bab-147">**Kann ich die ISO/IEC 27017-Compliance von Microsoft-Diensten für den Zertifizierungsprozess meiner Organisation verwenden?**</span><span class="sxs-lookup"><span data-stu-id="70bab-147">**Can I use the ISO/IEC 27017 compliance of Microsoft services in my organization’s certification process?**</span></span>

<span data-ttu-id="70bab-148">Ja.</span><span class="sxs-lookup"><span data-stu-id="70bab-148">Yes.</span></span> <span data-ttu-id="70bab-149">Wenn Ihr Unternehmen eine Zertifizierung für Installationen anstrebt, die in einem der im Umfang enthaltenen Microsoft Enterprise Cloud Services bereitgestellt werden, können Sie die entsprechenden Zertifizierungen von Microsoft für Ihre Compliancebewertung verwenden.</span><span class="sxs-lookup"><span data-stu-id="70bab-149">If your business is seeking certification for implementations deployed on any Microsoft in-scope enterprise cloud services, you can use Microsoft’s relevant certifications in your compliance assessment.</span></span> <span data-ttu-id="70bab-150">Sie sind jedoch dafür verantwortlich, einen Auditor mit der Prüfung Ihrer Implementierung unter Wahrung der Compliance zu beauftragen. Außerdem sind Sie für die Kontrollen und Prozesse in Ihrer eigenen Organisation zuständig.</span><span class="sxs-lookup"><span data-stu-id="70bab-150">However, you are responsible for engaging an assessor to evaluate your implementation for compliance, and for the controls and processes within your own organization.</span></span>

<span data-ttu-id="70bab-151">**Wie erhalte ich Kopien der entsprechenden Prüfberichte?**</span><span class="sxs-lookup"><span data-stu-id="70bab-151">**How can I get copies of the applicable audit reports?**</span></span>

<span data-ttu-id="70bab-152">Im [Service Trust Portal](https://aka.ms/stphelp) erhalten Sie unabhängige Prüfberichte von Dritten und weitere zugehörige Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="70bab-152">The [Service Trust Portal](https://aka.ms/stphelp) provides independent, third-party audit reports and other related documentation.</span></span> <span data-ttu-id="70bab-153">Sie können diese Dokumentation aus dem Portal herunterladen und prüfen, um Unterstützung bei der Erfüllung Ihrer eigenen gesetzlichen Anforderungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="70bab-153">You can use the portal to download and review this documentation for assistance with your own regulatory requirements.</span></span>

## <a name="resources"></a><span data-ttu-id="70bab-154">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="70bab-154">Resources</span></span>

- [<span data-ttu-id="70bab-155">ISO/IEC 27017:2015-Verhaltenskodex</span><span class="sxs-lookup"><span data-stu-id="70bab-155">ISO/IEC 27017:2015 code of practice</span></span>](https://www.iso.org/iso/iso_catalogue/catalogue_tc/catalogue_detail.htm?csnumber=43757)
- [<span data-ttu-id="70bab-156">Nutzungsbedingungen für Microsoft-Onlinedienste</span><span class="sxs-lookup"><span data-stu-id="70bab-156">Microsoft Online Services Terms</span></span>](https://aka.ms/Online-Services-Terms)
- [<span data-ttu-id="70bab-157">Compliance im Microsoft Trust Center</span><span class="sxs-lookup"><span data-stu-id="70bab-157">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="70bab-158">Hintergrundinformationen zum Angebot herunterladen</span><span class="sxs-lookup"><span data-stu-id="70bab-158">Download the offering backgrounder</span></span>

<span data-ttu-id="70bab-159">Benötigen Sie das Dokument mit Hintergrundwissen für dieses Angebot?</span><span class="sxs-lookup"><span data-stu-id="70bab-159">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="70bab-160">Laden Sie die [PDF-Datei](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf) herunter.</span><span class="sxs-lookup"><span data-stu-id="70bab-160">Download the [PDF](https://download.microsoft.com/download/7/7/9/7799D02B-A97A-48E0-A057-C19DD543BB24/ISO-IEC-27017_backgrounder.pdf).</span></span>
