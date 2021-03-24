---
title: DeviceFileCertificateInfo-Tabelle im schema der erweiterten Suche
description: Informationen zum Signieren von Dateien finden Sie in der DeviceFileCertificateInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 00e10c84c4bcb20f2e018bf05033b5b2235fd9ae
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063536"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="842ea-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="842ea-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="842ea-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="842ea-105">**Applies to:**</span></span>
- <span data-ttu-id="842ea-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="842ea-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="842ea-107">Die `DeviceFileCertificateInfo` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten.</span><span class="sxs-lookup"><span data-stu-id="842ea-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="842ea-108">In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="842ea-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="842ea-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="842ea-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="842ea-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="842ea-110">Column name</span></span> | <span data-ttu-id="842ea-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="842ea-111">Data type</span></span> | <span data-ttu-id="842ea-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="842ea-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="842ea-113">datetime</span><span class="sxs-lookup"><span data-stu-id="842ea-113">datetime</span></span> | <span data-ttu-id="842ea-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="842ea-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="842ea-115">string</span><span class="sxs-lookup"><span data-stu-id="842ea-115">string</span></span> | <span data-ttu-id="842ea-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="842ea-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="842ea-117">string</span><span class="sxs-lookup"><span data-stu-id="842ea-117">string</span></span> | <span data-ttu-id="842ea-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="842ea-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="842ea-119">string</span><span class="sxs-lookup"><span data-stu-id="842ea-119">string</span></span> | <span data-ttu-id="842ea-120">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="842ea-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="842ea-121">boolean</span><span class="sxs-lookup"><span data-stu-id="842ea-121">boolean</span></span> | <span data-ttu-id="842ea-122">Gibt an, ob die Datei signiert ist</span><span class="sxs-lookup"><span data-stu-id="842ea-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="842ea-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="842ea-123">string</span></span> | <span data-ttu-id="842ea-124">Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst gelesen oder aus einer externen Katalogdatei gelesen wurden</span><span class="sxs-lookup"><span data-stu-id="842ea-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="842ea-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="842ea-125">string</span></span> | <span data-ttu-id="842ea-126">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="842ea-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="842ea-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="842ea-127">string</span></span> | <span data-ttu-id="842ea-128">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="842ea-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="842ea-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="842ea-129">string</span></span> | <span data-ttu-id="842ea-130">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="842ea-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="842ea-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="842ea-131">string</span></span> | <span data-ttu-id="842ea-132">Eindeutiger Hashwert, der die ausstellende Zertifizierungsstelle (Ca) identifiziert</span><span class="sxs-lookup"><span data-stu-id="842ea-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="842ea-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="842ea-133">string</span></span> | <span data-ttu-id="842ea-134">Id für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="842ea-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="842ea-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="842ea-135">string</span></span> |  <span data-ttu-id="842ea-136">JSON-Array mit den URLs von Netzwerkfreigaben, die Zertifikate und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) enthalten</span><span class="sxs-lookup"><span data-stu-id="842ea-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="842ea-137">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="842ea-137">datetime</span></span> | <span data-ttu-id="842ea-138">Datum und Uhrzeit, zu der das Zertifikat erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="842ea-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="842ea-139">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="842ea-139">datetime</span></span> | <span data-ttu-id="842ea-140">Datum und Uhrzeit des Ablaufs des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="842ea-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="842ea-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="842ea-141">datetime</span></span> | <span data-ttu-id="842ea-142">Datum und Uhrzeit, zu der das Zertifikat gegensigniert wurde</span><span class="sxs-lookup"><span data-stu-id="842ea-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="842ea-143">boolean</span><span class="sxs-lookup"><span data-stu-id="842ea-143">boolean</span></span> | <span data-ttu-id="842ea-144">Gibt an, ob die Datei basierend auf den Ergebnissen der WinVerifyTrust-Funktion vertrauenswürdig ist, die nach unbekannten Stammzertifikatinformationen, ungültigen Signaturen, widerrufenen Zertifikaten und anderen fragwürdigen Attributen sucht.</span><span class="sxs-lookup"><span data-stu-id="842ea-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="842ea-145">boolean</span><span class="sxs-lookup"><span data-stu-id="842ea-145">boolean</span></span> | <span data-ttu-id="842ea-146">Gibt an, ob der Signier des Stammzertifikats Microsoft ist</span><span class="sxs-lookup"><span data-stu-id="842ea-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="842ea-147">long</span><span class="sxs-lookup"><span data-stu-id="842ea-147">long</span></span> | <span data-ttu-id="842ea-148">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="842ea-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="842ea-149">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="842ea-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="842ea-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="842ea-150">Related topics</span></span>
- [<span data-ttu-id="842ea-151">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="842ea-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="842ea-152">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="842ea-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="842ea-153">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="842ea-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="842ea-154">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="842ea-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="842ea-155">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="842ea-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="842ea-156">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="842ea-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
