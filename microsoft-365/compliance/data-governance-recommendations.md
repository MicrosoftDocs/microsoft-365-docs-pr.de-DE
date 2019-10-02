---
title: 'Identifizieren von Inhalten für Empfehlungen im Hinblick auf die Datengovernance '
ms.author: brendonb
author: laurawi
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Das Office 365 Security & Compliance Center bietet Empfehlungen für Datengovernance basierend auf dem aktuellen Setup Ihrer Organisation; mit nur wenigen Klicks können Sie alles einrichten. Einige dieser Empfehlungen erkennen spezifische Inhalte in Ihrer Organisation und bieten dann empfohlene Schritte zum Verwalten dieser Inhalte an. Eine Empfehlung könnte beispielsweise Elemente mit unternehmenswichtigen Inhalten erkennen (z. B. Anwaltsgeheimnisse oder Geheimhaltungsvereinbarungen). Sie können dann automatisch eine Aufbewahrungbezeichnung auf diese Elemente anwenden, um sicherzustellen, dass sie bei Bedarf mit einer Geheimhaltungsklassifzierung versehen und aufbewahrt werden. In diesem Thema sind die Datengovernance-Empfehlungen aufgeführt, die möglicherweise angezeigt werden, und es wird beschrieben, welche Inhalte erkannt werden, damit die einzelnen Empfehlungen ausgelöst werden.
ms.openlocfilehash: 10752afb97fd0ae2993d88b4e3af9159d61de708
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342938"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="49e19-106">Identifizieren von Inhalten für Empfehlungen im Hinblick auf die Datengovernance </span><span class="sxs-lookup"><span data-stu-id="49e19-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="49e19-p102">Das Office 365 Security & Compliance Center bietet Empfehlungen für Datengovernance basierend auf dem aktuellen Setup Ihrer Organisation; mit nur wenigen Klicks können Sie alles einrichten. Einige dieser Empfehlungen erkennen spezifische Inhalte in Ihrer Organisation und bieten dann empfohlene Schritte zum Verwalten dieser Inhalte an. Eine Empfehlung könnte beispielsweise Elemente mit unternehmenswichtigen Inhalten erkennen (z. B. Anwaltsgeheimnisse oder Geheimhaltungsvereinbarungen). Sie können dann automatisch eine Aufbewahrungbezeichnung auf diese Elemente anwenden, um sicherzustellen, dass sie bei Bedarf mit einer Geheimhaltungsklassifzierung versehen und aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="49e19-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="49e19-110">In diesem Thema sind die Datengovernance-Empfehlungen aufgeführt, die möglicherweise angezeigt werden, und es wird beschrieben, welche Inhalte erkannt werden, damit die einzelnen Empfehlungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="49e19-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="49e19-111">Voicemail bereinigen</span><span class="sxs-lookup"><span data-stu-id="49e19-111">Clean up voicemail</span></span>

<span data-ttu-id="49e19-p103">Diese Empfehlung wird angezeigt, wenn E-Mail-Nachrichten, die mit dem Nachrichtentyp „Voicemail“ identifiziert wurden, in den Postfächern von Benutzern erkannt werden. Weitere Informationen zu [Nachrichteneigenschaften in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span><span class="sxs-lookup"><span data-stu-id="49e19-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="49e19-114">Inhalte mit Anwaltsgeheimnissen kennzeichnen</span><span class="sxs-lookup"><span data-stu-id="49e19-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="49e19-115">Diese Empfehlung wird angezeigt wird, wenn eine der folgenden Bedingungen erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="49e19-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="49e19-116">Eine beliebige Kombination der folgenden Schlüsselwörter wird im Textkörper einer E-Mail-Nachricht erkannt:</span><span class="sxs-lookup"><span data-stu-id="49e19-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="49e19-117">AG</span><span class="sxs-lookup"><span data-stu-id="49e19-117">ACP</span></span>
    - <span data-ttu-id="49e19-118">Anwaltsgeheimnis</span><span class="sxs-lookup"><span data-stu-id="49e19-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="49e19-119">Anwalts-Geheimnis</span><span class="sxs-lookup"><span data-stu-id="49e19-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="49e19-120">Anwaltsgeheimnisse</span><span class="sxs-lookup"><span data-stu-id="49e19-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="49e19-121">Eine beliebige Kombination der folgenden Schlüsselwörter wird in SharePoint- oder OneDrive-Dateien erkannt:</span><span class="sxs-lookup"><span data-stu-id="49e19-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="49e19-122">AG</span><span class="sxs-lookup"><span data-stu-id="49e19-122">ACP</span></span>
    - <span data-ttu-id="49e19-123">Anwaltsgeheimnis\*</span><span class="sxs-lookup"><span data-stu-id="49e19-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="49e19-124">Anwalts-Geheimnis</span><span class="sxs-lookup"><span data-stu-id="49e19-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="49e19-125">Audiodateien beibehalten</span><span class="sxs-lookup"><span data-stu-id="49e19-125">Retain audio files</span></span>

<span data-ttu-id="49e19-126">Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:</span><span class="sxs-lookup"><span data-stu-id="49e19-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="49e19-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="49e19-127">.MP3</span></span>
- <span data-ttu-id="49e19-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="49e19-128">.WMA</span></span>
- <span data-ttu-id="49e19-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="49e19-129">.WAV</span></span>
- <span data-ttu-id="49e19-130">.RA</span><span class="sxs-lookup"><span data-stu-id="49e19-130">.RA</span></span>
- <span data-ttu-id="49e19-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="49e19-131">.RAM</span></span>
- <span data-ttu-id="49e19-132">.RM</span><span class="sxs-lookup"><span data-stu-id="49e19-132">.RM</span></span>
- <span data-ttu-id="49e19-133">.MID</span><span class="sxs-lookup"><span data-stu-id="49e19-133">.MID</span></span>
- <span data-ttu-id="49e19-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="49e19-134">.OGG</span></span>
- <span data-ttu-id="49e19-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="49e19-135">.AIFF</span></span>
- <span data-ttu-id="49e19-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="49e19-136">.PCM</span></span>
- <span data-ttu-id="49e19-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="49e19-137">.AAC</span></span>
- <span data-ttu-id="49e19-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="49e19-138">.FLAC</span></span>
- <span data-ttu-id="49e19-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="49e19-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="49e19-140">CAD-Dateien beibehalten</span><span class="sxs-lookup"><span data-stu-id="49e19-140">Retain CAD files</span></span>

<span data-ttu-id="49e19-141">Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:</span><span class="sxs-lookup"><span data-stu-id="49e19-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="49e19-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="49e19-142">.3DXML</span></span>
- <span data-ttu-id="49e19-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="49e19-143">.ACIS</span></span>
- <span data-ttu-id="49e19-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="49e19-144">.ARC</span></span>
- <span data-ttu-id="49e19-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="49e19-145">.ASM</span></span>
- <span data-ttu-id="49e19-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="49e19-146">.CAT\*</span></span>
- <span data-ttu-id="49e19-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="49e19-147">.CGR</span></span>
- <span data-ttu-id="49e19-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="49e19-148">.DW\*</span></span>
- <span data-ttu-id="49e19-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="49e19-149">.DX\*</span></span>
- <span data-ttu-id="49e19-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="49e19-150">.EDRW</span></span>
- <span data-ttu-id="49e19-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="49e19-151">.IAM</span></span>
- <span data-ttu-id="49e19-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="49e19-152">.IGES</span></span>
- <span data-ttu-id="49e19-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="49e19-153">.IGS</span></span>
- <span data-ttu-id="49e19-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="49e19-154">.IPT</span></span>
- <span data-ttu-id="49e19-155">.JT</span><span class="sxs-lookup"><span data-stu-id="49e19-155">.JT</span></span>
- <span data-ttu-id="49e19-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="49e19-156">.MF1</span></span>
- <span data-ttu-id="49e19-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="49e19-157">.NEU</span></span>
- <span data-ttu-id="49e19-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="49e19-158">.PAR</span></span>
- <span data-ttu-id="49e19-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="49e19-159">.PKG</span></span>
- <span data-ttu-id="49e19-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="49e19-160">.PRC</span></span>
- <span data-ttu-id="49e19-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="49e19-161">.PRT</span></span>
- <span data-ttu-id="49e19-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="49e19-162">.PSM</span></span>
- <span data-ttu-id="49e19-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="49e19-163">.PWD</span></span>
- <span data-ttu-id="49e19-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="49e19-164">.SLD\*</span></span>
- <span data-ttu-id="49e19-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="49e19-165">.STEP</span></span>
- <span data-ttu-id="49e19-166">.STL</span><span class="sxs-lookup"><span data-stu-id="49e19-166">.STL</span></span>
- <span data-ttu-id="49e19-167">.STP</span><span class="sxs-lookup"><span data-stu-id="49e19-167">.STP</span></span>
- <span data-ttu-id="49e19-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="49e19-168">.U3D</span></span>
- <span data-ttu-id="49e19-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="49e19-169">.UNV</span></span>
- <span data-ttu-id="49e19-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="49e19-170">.VRML</span></span>
- <span data-ttu-id="49e19-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="49e19-171">.WRL</span></span>
- <span data-ttu-id="49e19-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="49e19-172">.X_\*</span></span>
- <span data-ttu-id="49e19-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="49e19-173">.XAS</span></span>
- <span data-ttu-id="49e19-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="49e19-174">.XMT\*</span></span>
- <span data-ttu-id="49e19-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="49e19-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="49e19-176">Bilddateien beibehalten</span><span class="sxs-lookup"><span data-stu-id="49e19-176">Retain image files</span></span>

<span data-ttu-id="49e19-177">Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:</span><span class="sxs-lookup"><span data-stu-id="49e19-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="49e19-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="49e19-178">.JPEG</span></span>
- <span data-ttu-id="49e19-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="49e19-179">.GIF</span></span>
- <span data-ttu-id="49e19-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="49e19-180">.TIF\*</span></span>
- <span data-ttu-id="49e19-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="49e19-181">.BMP</span></span>
- <span data-ttu-id="49e19-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="49e19-182">.PNG</span></span>
- <span data-ttu-id="49e19-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="49e19-183">.RAW</span></span>
- <span data-ttu-id="49e19-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="49e19-184">.PSD</span></span>
- <span data-ttu-id="49e19-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="49e19-185">.PSP</span></span>
- <span data-ttu-id="49e19-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="49e19-186">.JPG</span></span>
- <span data-ttu-id="49e19-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="49e19-187">.EXIF</span></span>
- <span data-ttu-id="49e19-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="49e19-188">.PPM</span></span>
- <span data-ttu-id="49e19-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="49e19-189">.PGM</span></span>
- <span data-ttu-id="49e19-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="49e19-190">.PBM</span></span>
- <span data-ttu-id="49e19-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="49e19-191">.PNM</span></span>
- <span data-ttu-id="49e19-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="49e19-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="49e19-193">Retain NDA content</span><span class="sxs-lookup"><span data-stu-id="49e19-193">Retain NDA content</span></span> 

<span data-ttu-id="49e19-194">Diese Empfehlung wird angezeigt wird, wenn eine der folgenden Bedingungen erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="49e19-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="49e19-195">Eine beliebige Kombination der folgenden Schlüsselwörter wird im Textkörper einer E-Mail-Nachricht erkannt:</span><span class="sxs-lookup"><span data-stu-id="49e19-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="49e19-196">NDA</span><span class="sxs-lookup"><span data-stu-id="49e19-196">NDA</span></span>
    - <span data-ttu-id="49e19-197">„Geheimhaltungsvereinbarung“</span><span class="sxs-lookup"><span data-stu-id="49e19-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="49e19-198">„Geheimhaltungs-Vereinbarung“</span><span class="sxs-lookup"><span data-stu-id="49e19-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="49e19-199">Eine beliebige Kombination der folgenden Schlüsselwörter wird in PDF- oder DOC-Dateien in SharePoint oder OneDrive erkannt:</span><span class="sxs-lookup"><span data-stu-id="49e19-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="49e19-200">NDA</span><span class="sxs-lookup"><span data-stu-id="49e19-200">NDA</span></span>
    - <span data-ttu-id="49e19-201">Geheimhaltungsvereinbarung</span><span class="sxs-lookup"><span data-stu-id="49e19-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="49e19-202">Softwaredateien beibehalten</span><span class="sxs-lookup"><span data-stu-id="49e19-202">Retain software development files</span></span>

<span data-ttu-id="49e19-203">Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:</span><span class="sxs-lookup"><span data-stu-id="49e19-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="49e19-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="49e19-204">.ASAX</span></span>
- <span data-ttu-id="49e19-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="49e19-205">.ASM</span></span>
- <span data-ttu-id="49e19-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="49e19-206">.ASP\*</span></span>
- <span data-ttu-id="49e19-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="49e19-207">.BAT</span></span>
- <span data-ttu-id="49e19-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="49e19-208">.CONFIG</span></span>
- <span data-ttu-id="49e19-209">.CS</span><span class="sxs-lookup"><span data-stu-id="49e19-209">.CS</span></span>
- <span data-ttu-id="49e19-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="49e19-210">.CSS</span></span>
- <span data-ttu-id="49e19-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="49e19-211">.DISCO</span></span>
- <span data-ttu-id="49e19-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="49e19-212">.HTM\*</span></span>
- <span data-ttu-id="49e19-213">.INC</span><span class="sxs-lookup"><span data-stu-id="49e19-213">.INC</span></span>
- <span data-ttu-id="49e19-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="49e19-214">.JAD</span></span>
- <span data-ttu-id="49e19-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="49e19-215">.JAVA</span></span>
- <span data-ttu-id="49e19-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="49e19-216">.JS\*</span></span>
- <span data-ttu-id="49e19-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="49e19-217">.LIB</span></span>
- <span data-ttu-id="49e19-218">.O</span><span class="sxs-lookup"><span data-stu-id="49e19-218">.O</span></span>
- <span data-ttu-id="49e19-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="49e19-219">.PHP</span></span>
- <span data-ttu-id="49e19-220">.RC</span><span class="sxs-lookup"><span data-stu-id="49e19-220">.RC</span></span>
- <span data-ttu-id="49e19-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="49e19-221">.RESX</span></span>
- <span data-ttu-id="49e19-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="49e19-222">.RPT</span></span>
- <span data-ttu-id="49e19-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="49e19-223">.RSS</span></span>
- <span data-ttu-id="49e19-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="49e19-224">.SCPT</span></span>
- <span data-ttu-id="49e19-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="49e19-225">.SRC</span></span>
- <span data-ttu-id="49e19-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="49e19-226">.VB\*</span></span>
- <span data-ttu-id="49e19-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="49e19-227">.WSF</span></span>
- <span data-ttu-id="49e19-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="49e19-228">.XCODEPROJ</span></span>
- <span data-ttu-id="49e19-229">.XML</span><span class="sxs-lookup"><span data-stu-id="49e19-229">.XML</span></span>
- <span data-ttu-id="49e19-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="49e19-230">.XSD</span></span>
- <span data-ttu-id="49e19-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="49e19-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="49e19-232">Videodateien beibehalten</span><span class="sxs-lookup"><span data-stu-id="49e19-232">Retain video files</span></span>

<span data-ttu-id="49e19-233">Diese Empfehlung wird angezeigt wird, wenn einer der folgenden Dateitypen in SharePoint oder OneDrive erkannt wird:</span><span class="sxs-lookup"><span data-stu-id="49e19-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="49e19-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="49e19-234">.AVCHD</span></span>
- <span data-ttu-id="49e19-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="49e19-235">.AVI</span></span>
- <span data-ttu-id="49e19-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="49e19-236">.FLV</span></span>
- <span data-ttu-id="49e19-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="49e19-237">.MOV</span></span>
- <span data-ttu-id="49e19-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="49e19-238">.MP2V</span></span>
- <span data-ttu-id="49e19-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="49e19-239">.MP4</span></span>
- <span data-ttu-id="49e19-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="49e19-240">.MP4V</span></span>
- <span data-ttu-id="49e19-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="49e19-241">.MPE</span></span>
- <span data-ttu-id="49e19-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="49e19-242">.MPEG</span></span>
- <span data-ttu-id="49e19-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="49e19-243">.MPEG1</span></span>
- <span data-ttu-id="49e19-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="49e19-244">.MPEG2</span></span>
- <span data-ttu-id="49e19-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="49e19-245">.MPEG4</span></span>
- <span data-ttu-id="49e19-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="49e19-246">.MPG</span></span>
- <span data-ttu-id="49e19-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="49e19-247">.MPG2</span></span>
- <span data-ttu-id="49e19-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="49e19-248">.MPG4</span></span>
- <span data-ttu-id="49e19-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="49e19-249">.WMV</span></span>
- <span data-ttu-id="49e19-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="49e19-250">.XMV</span></span>
