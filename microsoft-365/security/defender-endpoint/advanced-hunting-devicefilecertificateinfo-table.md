---
title: DeviceFileCertificateInfo-Tabelle im schema der erweiterten Suche
description: Informationen zum Signieren von Dateien finden Sie in der DeviceFileCertificateInfo-Tabelle des schemas für die erweiterte Suche.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Mdatp, microsoft defender atp, wdatp search, query, telemetry, schema reference, kusto, table, column, data type, description, digital signature, certificate, file signing, DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: b3b5af8093107925c6c12c901e8138960c5eeaf6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064383"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="57000-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="57000-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="57000-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="57000-105">**Applies to:**</span></span>
- [<span data-ttu-id="57000-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="57000-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="57000-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="57000-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="57000-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="57000-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="57000-109">Die `DeviceFileCertificateInfo` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten.</span><span class="sxs-lookup"><span data-stu-id="57000-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="57000-110">In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="57000-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="57000-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="57000-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="57000-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="57000-112">Column name</span></span> | <span data-ttu-id="57000-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="57000-113">Data type</span></span> | <span data-ttu-id="57000-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57000-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="57000-115">datetime</span><span class="sxs-lookup"><span data-stu-id="57000-115">datetime</span></span> | <span data-ttu-id="57000-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="57000-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="57000-117">string</span><span class="sxs-lookup"><span data-stu-id="57000-117">string</span></span> | <span data-ttu-id="57000-118">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="57000-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="57000-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-119">string</span></span> | <span data-ttu-id="57000-120">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="57000-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="57000-121">string</span><span class="sxs-lookup"><span data-stu-id="57000-121">string</span></span> | <span data-ttu-id="57000-122">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="57000-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="57000-123">boolean</span><span class="sxs-lookup"><span data-stu-id="57000-123">boolean</span></span> | <span data-ttu-id="57000-124">Gibt an, ob die Datei signiert ist</span><span class="sxs-lookup"><span data-stu-id="57000-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="57000-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-125">string</span></span> | <span data-ttu-id="57000-126">Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst gelesen oder aus einer externen Katalogdatei gelesen wurden</span><span class="sxs-lookup"><span data-stu-id="57000-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="57000-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-127">string</span></span> | <span data-ttu-id="57000-128">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="57000-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="57000-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-129">string</span></span> | <span data-ttu-id="57000-130">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="57000-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="57000-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-131">string</span></span> | <span data-ttu-id="57000-132">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="57000-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="57000-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-133">string</span></span> | <span data-ttu-id="57000-134">Eindeutiger Hashwert, der die ausstellende Zertifizierungsstelle (Ca) identifiziert</span><span class="sxs-lookup"><span data-stu-id="57000-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="57000-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-135">string</span></span> | <span data-ttu-id="57000-136">Id für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="57000-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="57000-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="57000-137">string</span></span> |  <span data-ttu-id="57000-138">JSON-Array mit den URLs von Netzwerkfreigaben, die Zertifikate und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) enthalten</span><span class="sxs-lookup"><span data-stu-id="57000-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="57000-139">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="57000-139">datetime</span></span> | <span data-ttu-id="57000-140">Datum und Uhrzeit, zu der das Zertifikat erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="57000-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="57000-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="57000-141">datetime</span></span> | <span data-ttu-id="57000-142">Datum und Uhrzeit des Ablaufs des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="57000-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="57000-143">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="57000-143">datetime</span></span> | <span data-ttu-id="57000-144">Datum und Uhrzeit, zu der das Zertifikat gegensigniert wurde</span><span class="sxs-lookup"><span data-stu-id="57000-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="57000-145">boolean</span><span class="sxs-lookup"><span data-stu-id="57000-145">boolean</span></span> | <span data-ttu-id="57000-146">Gibt an, ob die Datei basierend auf den Ergebnissen der WinVerifyTrust-Funktion vertrauenswürdig ist, die nach unbekannten Stammzertifikatinformationen, ungültigen Signaturen, widerrufenen Zertifikaten und anderen fragwürdigen Attributen sucht.</span><span class="sxs-lookup"><span data-stu-id="57000-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="57000-147">boolean</span><span class="sxs-lookup"><span data-stu-id="57000-147">boolean</span></span> | <span data-ttu-id="57000-148">Gibt an, ob der Signier des Stammzertifikats Microsoft ist</span><span class="sxs-lookup"><span data-stu-id="57000-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="57000-149">long</span><span class="sxs-lookup"><span data-stu-id="57000-149">long</span></span> | <span data-ttu-id="57000-150">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="57000-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="57000-151">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="57000-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="57000-152">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="57000-152">Related topics</span></span>
- [<span data-ttu-id="57000-153">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="57000-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="57000-154">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="57000-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="57000-155">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="57000-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
