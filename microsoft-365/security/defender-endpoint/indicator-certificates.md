---
title: Erstellen von Indikatoren basierend auf Zertifikaten
ms.reviewer: ''
description: Erstellen Sie Indikatoren basierend auf Zertifikaten, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: ioc, Zertifikat, Zertifikate, verwalten, zulässig, blockiert, blockieren, sauber, schadhaft, Dateihash, IP-Adresse, URLs, Domäne
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8cf611e38bc781c2302f70f6491bb827410235b0
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164681"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="fc7eb-104">Erstellen von Indikatoren basierend auf Zertifikaten</span><span class="sxs-lookup"><span data-stu-id="fc7eb-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="fc7eb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fc7eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="fc7eb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="fc7eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="fc7eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc7eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fc7eb-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="fc7eb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fc7eb-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="fc7eb-110">Sie können Indikatoren für Zertifikate erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-110">You can create indicators for certificates.</span></span> <span data-ttu-id="fc7eb-111">Einige häufige Verwendungsfälle sind:</span><span class="sxs-lookup"><span data-stu-id="fc7eb-111">Some common use cases include:</span></span>

- <span data-ttu-id="fc7eb-112">Szenarien, in denen Sie Blockierungstechnologien bereitstellen müssen, z. B. Regeln zur Reduzierung der Angriffsfläche und kontrollierten Ordnerzugriff, jedoch Verhalten von signierten Anwendungen zulassen müssen, indem Sie das Zertifikat in der Liste der zulässigen Anwendungen hinzufügen. [](attack-surface-reduction.md) [](controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="fc7eb-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="fc7eb-113">Blockieren der Verwendung einer bestimmten signierten Anwendung in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="fc7eb-114">Durch das Erstellen eines Indikators zum Blockieren des Zertifikats der Anwendung verhindert Windows Defender AV Dateiausführungen (Blockieren und Bereinigung), und die automatische Untersuchung und Korrektur verhält sich gleich.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="fc7eb-115">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="fc7eb-115">Before you begin</span></span>

<span data-ttu-id="fc7eb-116">Es ist wichtig, die folgenden Anforderungen zu verstehen, bevor Sie Indikatoren für Zertifikate erstellen:</span><span class="sxs-lookup"><span data-stu-id="fc7eb-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="fc7eb-117">Dieses Feature ist verfügbar, wenn Ihre Organisation Windows Defender Antivirus und cloudbasierter Schutz aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="fc7eb-118">Weitere Informationen finden Sie unter [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="fc7eb-118">For more information, see [Manage cloud-based protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="fc7eb-119">Die Antischalwareclientversion muss 4.18.1901.x oder höher sein.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="fc7eb-120">Unterstützt auf Computern unter Windows 10, Version 1703 oder höher, Windows Server 2016 und 2019.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="fc7eb-121">Die Viren- und Bedrohungsschutzdefinitionen müssen auf dem neuesten Stand sein.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="fc7eb-122">Dieses Feature unterstützt derzeit die Eingabe von . CER oder . PEM-Dateierweiterungen.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="fc7eb-123">Ein gültiges Blattzertifikat ist ein Signaturzertifikat, das über einen gültigen Zertifizierungspfad verfügt und an die von Microsoft vertrauenswürdige Stammzertifizierungsstelle (Root Certificate Authority, CA) verkettet werden muss.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="fc7eb-124">Alternativ kann ein benutzerdefiniertes (selbst signiertes) Zertifikat verwendet werden, solange es vom Client als vertrauenswürdig eingestuft wird (Das Zertifikat der Stammzertifizierungsstelle wird unter dem lokalen Computer "Vertrauenswürdige Stammzertifizierungsstellen" installiert).</span><span class="sxs-lookup"><span data-stu-id="fc7eb-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="fc7eb-125">Die untergeordneten Oder übergeordneten der IoCs für das Zulassen/Blockieren von Zertifikaten sind nicht in der Allow/Block-IoC-Funktionalität enthalten, sondern nur Blattzertifikate werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="fc7eb-126">Von Microsoft signierte Zertifikate können nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="fc7eb-127">Erstellen Sie auf der Einstellungsseite einen Indikator für Zertifikate:</span><span class="sxs-lookup"><span data-stu-id="fc7eb-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="fc7eb-128">Es kann bis zu 3 Stunden dauern, bis ein Zertifikat ioC erstellt und entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="fc7eb-129">Wählen Sie im Navigationsbereich **Einstellungsindikatoren**  >  **aus.**</span><span class="sxs-lookup"><span data-stu-id="fc7eb-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="fc7eb-130">Wählen Sie die **Registerkarte Zertifikat** aus.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="fc7eb-131">Wählen **Sie Indikator hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="fc7eb-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="fc7eb-132">Geben Sie die folgenden Details an:</span><span class="sxs-lookup"><span data-stu-id="fc7eb-132">Specify the following details:</span></span>
   - <span data-ttu-id="fc7eb-133">Indikator – Geben Sie die Entitätsdetails an, und definieren Sie den Ablauf des Indikators.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="fc7eb-134">Aktion – Geben Sie die zu ergreifende Aktion an, und geben Sie eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="fc7eb-135">Bereich : Definieren Sie den Bereich der Computergruppe.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="fc7eb-136">Überprüfen Sie die Details auf der Registerkarte Zusammenfassung, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="fc7eb-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fc7eb-137">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fc7eb-137">Related topics</span></span>
- [<span data-ttu-id="fc7eb-138">Erstellen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="fc7eb-138">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="fc7eb-139">Erstellen von Indikatoren für Dateien</span><span class="sxs-lookup"><span data-stu-id="fc7eb-139">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="fc7eb-140">Erstellen von Indikatoren für IPs und URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="fc7eb-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="fc7eb-141">Verwalten von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="fc7eb-141">Manage indicators</span></span>](indicator-manage.md)
