---
title: DeviceFileCertificateInfoBeta-Tabelle im Advanced Hunting-Schema
description: Erfahren Sie mehr über Datei Signierungsinformationen in der DeviceFileCertificateInfoBeta-Tabelle des Advanced Hunting-Schemas.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, digitale Signatur, Zertifikat, Dateisignierung, DeviceFileCertificateInfoBeta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4d5769088f3904bf62d2889f35f236c9410628db
ms.sourcegitcommit: 7705fdbcee4f8714ce044c9e120a431023f7a367
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "41230203"
---
# <a name="devicefilecertificateinfobeta"></a><span data-ttu-id="d86dc-104">DeviceFileCertificateInfoBeta</span><span class="sxs-lookup"><span data-stu-id="d86dc-104">DeviceFileCertificateInfoBeta</span></span>

<span data-ttu-id="d86dc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d86dc-105">**Applies to:**</span></span>
- <span data-ttu-id="d86dc-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d86dc-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="d86dc-107">Die `DeviceFileCertificateInfoBeta` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Dateisignatur Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="d86dc-107">The `DeviceFileCertificateInfoBeta` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="d86dc-108">In dieser Tabelle werden Daten verwendet, die aus Zertifikat Überprüfungsaktivitäten regelmäßig für Dateien auf Endpunkten ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="d86dc-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="d86dc-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d86dc-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d86dc-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d86dc-110">Column name</span></span> | <span data-ttu-id="d86dc-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d86dc-111">Data type</span></span> | <span data-ttu-id="d86dc-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d86dc-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d86dc-113">datetime</span><span class="sxs-lookup"><span data-stu-id="d86dc-113">datetime</span></span> | <span data-ttu-id="d86dc-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="d86dc-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d86dc-115">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-115">string</span></span> | <span data-ttu-id="d86dc-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="d86dc-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d86dc-117">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-117">string</span></span> | <span data-ttu-id="d86dc-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="d86dc-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="d86dc-119">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-119">string</span></span> | <span data-ttu-id="d86dc-120">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="d86dc-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="d86dc-121">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d86dc-121">boolean</span></span> | <span data-ttu-id="d86dc-122">Gibt an, ob die Datei signiert ist</span><span class="sxs-lookup"><span data-stu-id="d86dc-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="d86dc-123">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-123">string</span></span> | <span data-ttu-id="d86dc-124">Gibt an, ob Signaturinformationen als eingebettet gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="d86dc-124">Indicates whether signature information was read as embedded</span></span> | <span data-ttu-id="d86dc-125">Inhalte in der Datei selbst oder aus einer externen Katalogdatei lesen</span><span class="sxs-lookup"><span data-stu-id="d86dc-125">content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="d86dc-126">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-126">string</span></span> | <span data-ttu-id="d86dc-127">Informationen über den unterschreibenden der Datei</span><span class="sxs-lookup"><span data-stu-id="d86dc-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="d86dc-128">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-128">string</span></span> | <span data-ttu-id="d86dc-129">Eindeutiger Hashwert zur Identifizierung der signierenden</span><span class="sxs-lookup"><span data-stu-id="d86dc-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="d86dc-130">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-130">string</span></span> | <span data-ttu-id="d86dc-131">Informationen zur ausstellenden Zertifizierungsstelle (Certification Authority, ca)</span><span class="sxs-lookup"><span data-stu-id="d86dc-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="d86dc-132">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-132">string</span></span> | <span data-ttu-id="d86dc-133">Eindeutiger Hashwert zur Identifizierung der ausstellenden Zertifizierungsstelle (Certification Authority, ca)</span><span class="sxs-lookup"><span data-stu-id="d86dc-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="d86dc-134">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-134">string</span></span> | <span data-ttu-id="d86dc-135">Bezeichner für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="d86dc-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="d86dc-136">string</span><span class="sxs-lookup"><span data-stu-id="d86dc-136">string</span></span> |  <span data-ttu-id="d86dc-137">JSON-Array, das die URLs von Netzwerkfreigaben auflistet, die Zertifikate und Zertifikatsperrlisten enthalten</span><span class="sxs-lookup"><span data-stu-id="d86dc-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="d86dc-138">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d86dc-138">datetime</span></span> | <span data-ttu-id="d86dc-139">Datum und Uhrzeit der Erstellung des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="d86dc-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="d86dc-140">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d86dc-140">datetime</span></span> | <span data-ttu-id="d86dc-141">Datum und Uhrzeit des Ablaufs des Zertifikats festgelegt</span><span class="sxs-lookup"><span data-stu-id="d86dc-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="d86dc-142">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d86dc-142">datetime</span></span> | <span data-ttu-id="d86dc-143">Datum und Uhrzeit der Gegenzeichnung des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="d86dc-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="d86dc-144">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d86dc-144">boolean</span></span> | <span data-ttu-id="d86dc-145">Gibt an, ob die Datei vertrauenswürdig ist, basierend auf den Ergebnissen der WinVerifyTrust-Funktion, die nach unbekannten Stammzertifikat Informationen, ungültigen Signaturen, gesperrten Zertifikaten und anderen fragwürdigen Attributen sucht.</span><span class="sxs-lookup"><span data-stu-id="d86dc-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="d86dc-146">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="d86dc-146">boolean</span></span> | <span data-ttu-id="d86dc-147">Gibt an, ob die Signatur des Stammzertifikats Microsoft lautet.</span><span class="sxs-lookup"><span data-stu-id="d86dc-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="d86dc-148">long</span><span class="sxs-lookup"><span data-stu-id="d86dc-148">long</span></span> | <span data-ttu-id="d86dc-149">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="d86dc-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d86dc-150">Zum Identifizieren eindeutiger Ereignisse muss diese Spalte zusammen mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d86dc-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="d86dc-151">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d86dc-151">Related topics</span></span>
- [<span data-ttu-id="d86dc-152">Vorbeugende Suche nach Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="d86dc-152">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d86dc-153">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d86dc-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d86dc-154">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="d86dc-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d86dc-155">Suche nach Bedrohungen auf Geräten und in E-Mails</span><span class="sxs-lookup"><span data-stu-id="d86dc-155">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d86dc-156">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="d86dc-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d86dc-157">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="d86dc-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)