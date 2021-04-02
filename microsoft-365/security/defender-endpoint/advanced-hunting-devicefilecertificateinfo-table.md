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
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499180"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="d0983-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="d0983-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0983-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d0983-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0983-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d0983-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="d0983-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="d0983-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0983-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d0983-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="d0983-109">Die `DeviceFileCertificateInfo` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu Dateisignaturzertifikaten.</span><span class="sxs-lookup"><span data-stu-id="d0983-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="d0983-110">In dieser Tabelle werden Daten aus Zertifikatüberprüfungsaktivitäten verwendet, die regelmäßig für Dateien auf Endpunkten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d0983-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="d0983-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="d0983-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="d0983-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d0983-112">Column name</span></span> | <span data-ttu-id="d0983-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d0983-113">Data type</span></span> | <span data-ttu-id="d0983-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0983-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d0983-115">datetime</span><span class="sxs-lookup"><span data-stu-id="d0983-115">datetime</span></span> | <span data-ttu-id="d0983-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="d0983-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d0983-117">string</span><span class="sxs-lookup"><span data-stu-id="d0983-117">string</span></span> | <span data-ttu-id="d0983-118">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="d0983-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d0983-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-119">string</span></span> | <span data-ttu-id="d0983-120">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="d0983-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="d0983-121">string</span><span class="sxs-lookup"><span data-stu-id="d0983-121">string</span></span> | <span data-ttu-id="d0983-122">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="d0983-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="d0983-123">boolean</span><span class="sxs-lookup"><span data-stu-id="d0983-123">boolean</span></span> | <span data-ttu-id="d0983-124">Gibt an, ob die Datei signiert ist</span><span class="sxs-lookup"><span data-stu-id="d0983-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="d0983-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-125">string</span></span> | <span data-ttu-id="d0983-126">Gibt an, ob Signaturinformationen als eingebetteter Inhalt in der Datei selbst gelesen oder aus einer externen Katalogdatei gelesen wurden</span><span class="sxs-lookup"><span data-stu-id="d0983-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="d0983-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-127">string</span></span> | <span data-ttu-id="d0983-128">Informationen zum Signier der Datei</span><span class="sxs-lookup"><span data-stu-id="d0983-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="d0983-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-129">string</span></span> | <span data-ttu-id="d0983-130">Eindeutiger Hashwert, der den Signier identifiziert</span><span class="sxs-lookup"><span data-stu-id="d0983-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="d0983-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-131">string</span></span> | <span data-ttu-id="d0983-132">Informationen zur ausstellenden Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="d0983-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="d0983-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-133">string</span></span> | <span data-ttu-id="d0983-134">Eindeutiger Hashwert, der die ausstellende Zertifizierungsstelle (Ca) identifiziert</span><span class="sxs-lookup"><span data-stu-id="d0983-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="d0983-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-135">string</span></span> | <span data-ttu-id="d0983-136">Id für das Zertifikat, das für die ausstellende Zertifizierungsstelle eindeutig ist</span><span class="sxs-lookup"><span data-stu-id="d0983-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="d0983-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="d0983-137">string</span></span> |  <span data-ttu-id="d0983-138">JSON-Array mit den URLs von Netzwerkfreigaben, die Zertifikate und Zertifikatsperrlisten (Certificate Revocation Lists, CRLs) enthalten</span><span class="sxs-lookup"><span data-stu-id="d0983-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="d0983-139">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d0983-139">datetime</span></span> | <span data-ttu-id="d0983-140">Datum und Uhrzeit, zu der das Zertifikat erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="d0983-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="d0983-141">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d0983-141">datetime</span></span> | <span data-ttu-id="d0983-142">Datum und Uhrzeit des Ablaufs des Zertifikats</span><span class="sxs-lookup"><span data-stu-id="d0983-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="d0983-143">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="d0983-143">datetime</span></span> | <span data-ttu-id="d0983-144">Datum und Uhrzeit, zu der das Zertifikat gegensigniert wurde</span><span class="sxs-lookup"><span data-stu-id="d0983-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="d0983-145">boolean</span><span class="sxs-lookup"><span data-stu-id="d0983-145">boolean</span></span> | <span data-ttu-id="d0983-146">Gibt an, ob die Datei basierend auf den Ergebnissen der WinVerifyTrust-Funktion vertrauenswürdig ist, die nach unbekannten Stammzertifikatinformationen, ungültigen Signaturen, widerrufenen Zertifikaten und anderen fragwürdigen Attributen sucht.</span><span class="sxs-lookup"><span data-stu-id="d0983-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="d0983-147">boolean</span><span class="sxs-lookup"><span data-stu-id="d0983-147">boolean</span></span> | <span data-ttu-id="d0983-148">Gibt an, ob der Signier des Stammzertifikats Microsoft ist</span><span class="sxs-lookup"><span data-stu-id="d0983-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="d0983-149">long</span><span class="sxs-lookup"><span data-stu-id="d0983-149">long</span></span> | <span data-ttu-id="d0983-150">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="d0983-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d0983-151">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0983-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="d0983-152">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d0983-152">Related topics</span></span>
- [<span data-ttu-id="d0983-153">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="d0983-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d0983-154">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d0983-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d0983-155">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="d0983-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
