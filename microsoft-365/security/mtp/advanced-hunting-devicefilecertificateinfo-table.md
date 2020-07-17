---
title: DeviceFileCertificateInfo-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Datei Signierungsinformationen in der DeviceFileCertificateInfo-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, digitale Signatur, Zertifikat, Dateisignierung, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cba27b5b43141c8c90f9a8bc7f70c55aabc1979d
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899315"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="37e15-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="37e15-104">DeviceFileCertificateInfo</span></span>

<span data-ttu-id="37e15-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="37e15-105">**Applies to:**</span></span>
- <span data-ttu-id="37e15-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="37e15-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="37e15-107">Die `DeviceFileCertificateInfo` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Dateisignatur Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="37e15-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="37e15-108">In dieser Tabelle werden Daten verwendet, die aus Zertifikat Überprüfungsaktivitäten regelmäßig für Dateien auf Endpunkten ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="37e15-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="37e15-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="37e15-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="37e15-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="37e15-110">Column name</span></span> | <span data-ttu-id="37e15-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="37e15-111">Data type</span></span> | <span data-ttu-id="37e15-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="37e15-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="37e15-113">datetime</span><span class="sxs-lookup"><span data-stu-id="37e15-113">datetime</span></span> | <span data-ttu-id="37e15-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="37e15-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="37e15-115">string</span><span class="sxs-lookup"><span data-stu-id="37e15-115">string</span></span> | <span data-ttu-id="37e15-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="37e15-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="37e15-117">string</span><span class="sxs-lookup"><span data-stu-id="37e15-117">string</span></span> | <span data-ttu-id="37e15-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="37e15-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="37e15-119">string</span><span class="sxs-lookup"><span data-stu-id="37e15-119">string</span></span> | <span data-ttu-id="37e15-120">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="37e15-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="37e15-121">boolean</span><span class="sxs-lookup"><span data-stu-id="37e15-121">boolean</span></span> | <span data-ttu-id="37e15-122">Gibt an, ob die Datei signiert ist</span><span class="sxs-lookup"><span data-stu-id="37e15-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="37e15-123">string</span><span class="sxs-lookup"><span data-stu-id="37e15-123">string</span></span> | <span data-ttu-id="37e15-124">Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst gelesen oder aus einer externen Katalogdatei gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="37e15-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="37e15-125">string</span><span class="sxs-lookup"><span data-stu-id="37e15-125">string</span></span> | <span data-ttu-id="37e15-126">Informationen über den unterschreibenden der Datei</span><span class="sxs-lookup"><span data-stu-id="37e15-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="37e15-127">string</span><span class="sxs-lookup"><span data-stu-id="37e15-127">string</span></span> | <span data-ttu-id="37e15-128">Eindeutiger Hashwert zur Identifizierung der signierenden</span><span class="sxs-lookup"><span data-stu-id="37e15-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="37e15-129">string</span><span class="sxs-lookup"><span data-stu-id="37e15-129">string</span></span> | <span data-ttu-id="37e15-130">Informationen zur ausstellenden Zertifizierungsstelle (Certification Authority, ca)</span><span class="sxs-lookup"><span data-stu-id="37e15-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="37e15-131">string</span><span class="sxs-lookup"><span data-stu-id="37e15-131">string</span></span> | <span data-ttu-id="37e15-132">Eindeutiger Hashwert zur Identifizierung der ausstellenden Zertifizierungsstelle (Certification Authority, ca)</span><span class="sxs-lookup"><span data-stu-id="37e15-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="37e15-133">string</span><span class="sxs-lookup"><span data-stu-id="37e15-133">string</span></span> | <span data-ttu-id="37e15-134">Bezeichner für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="37e15-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="37e15-135">string</span><span class="sxs-lookup"><span data-stu-id="37e15-135">string</span></span> |  <span data-ttu-id="37e15-136">JSON-Array, das die URLs von Netzwerkfreigaben auflistet, die Zertifikate und Zertifikatsperrlisten enthalten</span><span class="sxs-lookup"><span data-stu-id="37e15-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="37e15-137">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="37e15-137">datetime</span></span> | <span data-ttu-id="37e15-138">Datum und Uhrzeit der Erstellung des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="37e15-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="37e15-139">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="37e15-139">datetime</span></span> | <span data-ttu-id="37e15-140">Datum und Uhrzeit des Ablaufs des Zertifikats festgelegt</span><span class="sxs-lookup"><span data-stu-id="37e15-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="37e15-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="37e15-141">datetime</span></span> | <span data-ttu-id="37e15-142">Datum und Uhrzeit der Gegenzeichnung des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="37e15-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="37e15-143">boolean</span><span class="sxs-lookup"><span data-stu-id="37e15-143">boolean</span></span> | <span data-ttu-id="37e15-144">Gibt an, ob die Datei vertrauenswürdig ist, basierend auf den Ergebnissen der WinVerifyTrust-Funktion, die nach unbekannten Stammzertifikat Informationen, ungültigen Signaturen, gesperrten Zertifikaten und anderen fragwürdigen Attributen sucht.</span><span class="sxs-lookup"><span data-stu-id="37e15-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="37e15-145">boolean</span><span class="sxs-lookup"><span data-stu-id="37e15-145">boolean</span></span> | <span data-ttu-id="37e15-146">Gibt an, ob die Signatur des Stammzertifikats Microsoft lautet.</span><span class="sxs-lookup"><span data-stu-id="37e15-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="37e15-147">long</span><span class="sxs-lookup"><span data-stu-id="37e15-147">long</span></span> | <span data-ttu-id="37e15-148">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="37e15-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="37e15-149">Zum Identifizieren eindeutiger Ereignisse muss diese Spalte zusammen mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="37e15-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="37e15-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="37e15-150">Related topics</span></span>
- [<span data-ttu-id="37e15-151">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="37e15-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="37e15-152">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="37e15-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="37e15-153">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="37e15-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="37e15-154">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="37e15-154">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="37e15-155">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="37e15-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="37e15-156">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="37e15-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
