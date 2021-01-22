---
title: Tabelle "DeviceFileCertificateInfo" im Schema "Erweiterte Suche"
description: Informationen zum Signieren von Dateien in der Tabelle "DeviceFileCertificateInfo" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, digitale Signatur, Zertifikat, Dateisignierung, DeviceFileCertificateInfo
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e35e8e86f6814a5f90a7921f71ccab7247fcc1bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931314"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="04536-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="04536-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="04536-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="04536-105">**Applies to:**</span></span>
- <span data-ttu-id="04536-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04536-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="04536-107">Die Tabelle im Schema für die erweiterte `DeviceFileCertificateInfo` [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten.</span><span class="sxs-lookup"><span data-stu-id="04536-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="04536-108">In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="04536-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="04536-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="04536-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="04536-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="04536-110">Column name</span></span> | <span data-ttu-id="04536-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="04536-111">Data type</span></span> | <span data-ttu-id="04536-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="04536-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="04536-113">datetime</span><span class="sxs-lookup"><span data-stu-id="04536-113">datetime</span></span> | <span data-ttu-id="04536-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="04536-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="04536-115">string</span><span class="sxs-lookup"><span data-stu-id="04536-115">string</span></span> | <span data-ttu-id="04536-116">Eindeutiger Bezeichner für den Computer im Dienst</span><span class="sxs-lookup"><span data-stu-id="04536-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="04536-117">string</span><span class="sxs-lookup"><span data-stu-id="04536-117">string</span></span> | <span data-ttu-id="04536-118">Vollqualifizierter Domänenname (FQDN) des Computers</span><span class="sxs-lookup"><span data-stu-id="04536-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="04536-119">string</span><span class="sxs-lookup"><span data-stu-id="04536-119">string</span></span> | <span data-ttu-id="04536-120">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="04536-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="04536-121">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="04536-121">boolean</span></span> | <span data-ttu-id="04536-122">Gibt an, ob die Datei signiert ist</span><span class="sxs-lookup"><span data-stu-id="04536-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="04536-123">string</span><span class="sxs-lookup"><span data-stu-id="04536-123">string</span></span> | <span data-ttu-id="04536-124">Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst oder aus einer externen Katalogdatei gelesen wurden.</span><span class="sxs-lookup"><span data-stu-id="04536-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="04536-125">string</span><span class="sxs-lookup"><span data-stu-id="04536-125">string</span></span> | <span data-ttu-id="04536-126">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="04536-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="04536-127">string</span><span class="sxs-lookup"><span data-stu-id="04536-127">string</span></span> | <span data-ttu-id="04536-128">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="04536-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="04536-129">string</span><span class="sxs-lookup"><span data-stu-id="04536-129">string</span></span> | <span data-ttu-id="04536-130">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="04536-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="04536-131">string</span><span class="sxs-lookup"><span data-stu-id="04536-131">string</span></span> | <span data-ttu-id="04536-132">Eindeutiger Hashwert, der die ausstellende Zertifizierungsstelle identifiziert</span><span class="sxs-lookup"><span data-stu-id="04536-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="04536-133">string</span><span class="sxs-lookup"><span data-stu-id="04536-133">string</span></span> | <span data-ttu-id="04536-134">Bezeichner für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="04536-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="04536-135">string</span><span class="sxs-lookup"><span data-stu-id="04536-135">string</span></span> |  <span data-ttu-id="04536-136">JSON-Array, das die URLs von Netzwerkfreigaben auflistet, die Zertifikate und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) enthalten</span><span class="sxs-lookup"><span data-stu-id="04536-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="04536-137">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="04536-137">datetime</span></span> | <span data-ttu-id="04536-138">Datum und Uhrzeit der Zertifikatserg nkung</span><span class="sxs-lookup"><span data-stu-id="04536-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="04536-139">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="04536-139">datetime</span></span> | <span data-ttu-id="04536-140">Datum und Uhrzeit des Ablaufs des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="04536-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="04536-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="04536-141">datetime</span></span> | <span data-ttu-id="04536-142">Datum und Uhrzeit, an dem und zu der das Zertifikat gegensigniert wurde</span><span class="sxs-lookup"><span data-stu-id="04536-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="04536-143">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="04536-143">boolean</span></span> | <span data-ttu-id="04536-144">Gibt an, ob die Datei basierend auf den Ergebnissen der WinVerifyTrust -Funktion vertrauenswürdig ist, die auf unbekannte Stammzertifikatinformationen, ungültige Signaturen, gesperrte Zertifikate und andere fragwürdige Attribute überprüft.</span><span class="sxs-lookup"><span data-stu-id="04536-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="04536-145">Boolescher Wert</span><span class="sxs-lookup"><span data-stu-id="04536-145">boolean</span></span> | <span data-ttu-id="04536-146">Gibt an, ob der Signer des Stammzertifikats Microsoft ist.</span><span class="sxs-lookup"><span data-stu-id="04536-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="04536-147">long</span><span class="sxs-lookup"><span data-stu-id="04536-147">long</span></span> | <span data-ttu-id="04536-148">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="04536-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="04536-149">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten "DeviceName" und "Timestamp" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="04536-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="04536-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="04536-150">Related topics</span></span>
- [<span data-ttu-id="04536-151">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="04536-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="04536-152">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="04536-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="04536-153">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="04536-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="04536-154">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="04536-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="04536-155">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="04536-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="04536-156">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="04536-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
