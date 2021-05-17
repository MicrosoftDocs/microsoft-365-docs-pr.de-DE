---
title: DeviceFileCertificateInfo-Tabelle im schema der erweiterten Suche
description: Informationen zum Signieren von Dateien finden Sie in der DeviceFileCertificateInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023213"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="07d5a-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="07d5a-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="07d5a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="07d5a-105">**Applies to:**</span></span>
- <span data-ttu-id="07d5a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07d5a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="07d5a-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="07d5a-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="07d5a-108">Die `DeviceFileCertificateInfo` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten.</span><span class="sxs-lookup"><span data-stu-id="07d5a-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="07d5a-109">In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="07d5a-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="07d5a-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="07d5a-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="07d5a-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="07d5a-111">Column name</span></span> | <span data-ttu-id="07d5a-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="07d5a-112">Data type</span></span> | <span data-ttu-id="07d5a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07d5a-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="07d5a-114">datetime</span><span class="sxs-lookup"><span data-stu-id="07d5a-114">datetime</span></span> | <span data-ttu-id="07d5a-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="07d5a-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="07d5a-116">string</span><span class="sxs-lookup"><span data-stu-id="07d5a-116">string</span></span> | <span data-ttu-id="07d5a-117">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="07d5a-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="07d5a-118">string</span><span class="sxs-lookup"><span data-stu-id="07d5a-118">string</span></span> | <span data-ttu-id="07d5a-119">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="07d5a-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="07d5a-120">string</span><span class="sxs-lookup"><span data-stu-id="07d5a-120">string</span></span> | <span data-ttu-id="07d5a-121">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="07d5a-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="07d5a-122">boolean</span><span class="sxs-lookup"><span data-stu-id="07d5a-122">boolean</span></span> | <span data-ttu-id="07d5a-123">Gibt an, ob die Datei signiert ist</span><span class="sxs-lookup"><span data-stu-id="07d5a-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="07d5a-124">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07d5a-124">string</span></span> | <span data-ttu-id="07d5a-125">Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst gelesen oder aus einer externen Katalogdatei gelesen wurden</span><span class="sxs-lookup"><span data-stu-id="07d5a-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="07d5a-126">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07d5a-126">string</span></span> | <span data-ttu-id="07d5a-127">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="07d5a-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="07d5a-128">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07d5a-128">string</span></span> | <span data-ttu-id="07d5a-129">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="07d5a-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="07d5a-130">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07d5a-130">string</span></span> | <span data-ttu-id="07d5a-131">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="07d5a-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="07d5a-132">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07d5a-132">string</span></span> | <span data-ttu-id="07d5a-133">Eindeutiger Hashwert, der die ausstellende Zertifizierungsstelle (Ca) identifiziert</span><span class="sxs-lookup"><span data-stu-id="07d5a-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="07d5a-134">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07d5a-134">string</span></span> | <span data-ttu-id="07d5a-135">Id für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="07d5a-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="07d5a-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07d5a-136">string</span></span> |  <span data-ttu-id="07d5a-137">JSON-Array mit den URLs von Netzwerkfreigaben, die Zertifikate und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) enthalten</span><span class="sxs-lookup"><span data-stu-id="07d5a-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="07d5a-138">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="07d5a-138">datetime</span></span> | <span data-ttu-id="07d5a-139">Datum und Uhrzeit, zu der das Zertifikat erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="07d5a-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="07d5a-140">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="07d5a-140">datetime</span></span> | <span data-ttu-id="07d5a-141">Datum und Uhrzeit des Ablaufs des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="07d5a-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="07d5a-142">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="07d5a-142">datetime</span></span> | <span data-ttu-id="07d5a-143">Datum und Uhrzeit, zu der das Zertifikat gegensigniert wurde</span><span class="sxs-lookup"><span data-stu-id="07d5a-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="07d5a-144">boolean</span><span class="sxs-lookup"><span data-stu-id="07d5a-144">boolean</span></span> | <span data-ttu-id="07d5a-145">Gibt an, ob die Datei basierend auf den Ergebnissen der WinVerifyTrust-Funktion vertrauenswürdig ist, die nach unbekannten Stammzertifikatinformationen, ungültigen Signaturen, widerrufenen Zertifikaten und anderen fragwürdigen Attributen sucht.</span><span class="sxs-lookup"><span data-stu-id="07d5a-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="07d5a-146">boolean</span><span class="sxs-lookup"><span data-stu-id="07d5a-146">boolean</span></span> | <span data-ttu-id="07d5a-147">Gibt an, ob der Signier des Stammzertifikats Microsoft ist</span><span class="sxs-lookup"><span data-stu-id="07d5a-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="07d5a-148">long</span><span class="sxs-lookup"><span data-stu-id="07d5a-148">long</span></span> | <span data-ttu-id="07d5a-149">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="07d5a-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="07d5a-150">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="07d5a-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="07d5a-151">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="07d5a-151">Related topics</span></span>
- [<span data-ttu-id="07d5a-152">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="07d5a-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="07d5a-153">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="07d5a-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="07d5a-154">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="07d5a-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="07d5a-155">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="07d5a-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="07d5a-156">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="07d5a-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="07d5a-157">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="07d5a-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
