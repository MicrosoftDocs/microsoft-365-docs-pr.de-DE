---
title: Lokalisieren der Benutzererfahrung
description: So lokalisieren Sie Geräte für Benutzer
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 354f61284bbd95c1c7ca4cd50459a1644a89d090
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023261"
---
# <a name="localize-the-user-experience"></a><span data-ttu-id="f20c9-104">Lokalisieren der Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="f20c9-104">Localize the user experience</span></span>

<span data-ttu-id="f20c9-105">Benutzer von Microsoft Managed Desktop können die Sprache ihrer Wahl entweder während des Setupvorgangs (die "out-of-box"-Erfahrung) oder danach auswählen.</span><span class="sxs-lookup"><span data-stu-id="f20c9-105">Users of Microsoft Managed Desktop devices can select the language of their choice either during the setup process (the "out of box experience") or afterwards.</span></span>

## <a name="during-setup-the-out-of-box-experience"></a><span data-ttu-id="f20c9-106">Während des Setups (die "out-of-box"-Erfahrung)</span><span class="sxs-lookup"><span data-stu-id="f20c9-106">During setup (the "out of box experience")</span></span>

<span data-ttu-id="f20c9-107">Während des Abschlusses des Setups können Benutzer die Sprache ihrer Wahl auswählen.</span><span class="sxs-lookup"><span data-stu-id="f20c9-107">During the process of completing setup, users can select the language of their choice.</span></span> <span data-ttu-id="f20c9-108">Diese Auswahl wirkt sich auf die folgenden Attribute aus:</span><span class="sxs-lookup"><span data-stu-id="f20c9-108">This selection affects these attributes:</span></span>

- <span data-ttu-id="f20c9-109">Windows 10 sprachfeatures:</span><span class="sxs-lookup"><span data-stu-id="f20c9-109">Windows 10 language features:</span></span>
    - <span data-ttu-id="f20c9-110">Anzeigesprache</span><span class="sxs-lookup"><span data-stu-id="f20c9-110">Display language</span></span>
    - <span data-ttu-id="f20c9-111">Tastatursprache</span><span class="sxs-lookup"><span data-stu-id="f20c9-111">Keyboard language</span></span>
    - <span data-ttu-id="f20c9-112">Sprachbezogene Features bei Bedarf</span><span class="sxs-lookup"><span data-stu-id="f20c9-112">Language-related Features on Demand</span></span>

- <span data-ttu-id="f20c9-113">Microsoft 365 Apps für Enterprise Sprachfeatures:</span><span class="sxs-lookup"><span data-stu-id="f20c9-113">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="f20c9-114">Anzeigesprache</span><span class="sxs-lookup"><span data-stu-id="f20c9-114">Display language</span></span>
    - <span data-ttu-id="f20c9-115">Korrekturhilfen und Erstellungstools</span><span class="sxs-lookup"><span data-stu-id="f20c9-115">Proofing and authoring tools</span></span>

> [!NOTE]
> <span data-ttu-id="f20c9-116">Benutzer können nur sprachbezogene Features bei Bedarf erhalten, indem sie die Sprache während des Setupvorgangs auswählen.</span><span class="sxs-lookup"><span data-stu-id="f20c9-116">Users can only get language-related Features On Demand by selecting the language during the setup process.</span></span>

## <a name="after-completing-setup"></a><span data-ttu-id="f20c9-117">Nach Abschluss des Setups</span><span class="sxs-lookup"><span data-stu-id="f20c9-117">After completing setup</span></span>

<span data-ttu-id="f20c9-118">Benutzer können die Sprache ihrer Wahl für Windows 10 und Microsoft 365 Apps für Enterprise nach Abschluss des Setupprozesses auswählen.</span><span class="sxs-lookup"><span data-stu-id="f20c9-118">Users can select the language of their choice for Windows 10 and Microsoft 365 Apps for Enterprise anytime after the setup process is complete.</span></span> <span data-ttu-id="f20c9-119">Insbesondere gilt:</span><span class="sxs-lookup"><span data-stu-id="f20c9-119">Specifically:</span></span>

- <span data-ttu-id="f20c9-120">Windows 10 sprachfeatures:</span><span class="sxs-lookup"><span data-stu-id="f20c9-120">Windows 10 language features:</span></span>
    - <span data-ttu-id="f20c9-121">Anzeigesprache</span><span class="sxs-lookup"><span data-stu-id="f20c9-121">Display language</span></span>
    - <span data-ttu-id="f20c9-122">Tastatursprache</span><span class="sxs-lookup"><span data-stu-id="f20c9-122">Keyboard language</span></span>

- <span data-ttu-id="f20c9-123">Microsoft 365 Apps für Enterprise Sprachfeatures:</span><span class="sxs-lookup"><span data-stu-id="f20c9-123">Microsoft 365 Apps for Enterprise language features:</span></span>
    - <span data-ttu-id="f20c9-124">Anzeigesprache</span><span class="sxs-lookup"><span data-stu-id="f20c9-124">Display language</span></span>
    - <span data-ttu-id="f20c9-125">Korrekturhilfen und Erstellungstools</span><span class="sxs-lookup"><span data-stu-id="f20c9-125">Proofing and authoring tools</span></span>

<span data-ttu-id="f20c9-126">Fügen Sie [die](#supported-languages) Benutzer der Gruppe Modern **Workplace-Office-Language_Packs** hinzu, um die unterstützten Sprachen für Microsoft 365 Apps für Enterprise zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f20c9-126">To make the [Supported languages](#supported-languages) for Microsoft 365 Apps for Enterprise available for your users to install, add the users to the **Modern Workplace-Office-Language_Packs** group.</span></span> <span data-ttu-id="f20c9-127">Die Sprachen sind in der Intune-Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="f20c9-127">The languages will be available in the Intune Company Portal.</span></span>


## <a name="supported-languages"></a><span data-ttu-id="f20c9-128">Unterstützte Sprachen</span><span class="sxs-lookup"><span data-stu-id="f20c9-128">Supported languages</span></span>

<span data-ttu-id="f20c9-129">Für neue Geräte muss Ihr Hersteller Gerätebilder bereitstellen, die die von Ihnen benötigten Sprachen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f20c9-129">For new devices, your manufacturer must provide device images that include the languages you require.</span></span> <span data-ttu-id="f20c9-130">Wenn das Image Ihres Herstellers andere Als die in der Liste der unterstützten Sprachen bereitgestellten Sprachen enthält, wird es weiterhin vom Dienst unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f20c9-130">If your manufacturer's image includes languages other than those provided in the supported languages list it is still supported by the service.</span></span>

<span data-ttu-id="f20c9-131">Wenn Sie vorhandene Geräte erneut verwenden, müssen Sie möglicherweise mit Ihrem Microsoft-Kontomitarbeiter zusammenarbeiten, um geeignete Bilder zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f20c9-131">If you are reusing existing devices, you might need to work with your Microsoft account representative to obtain appropriate images.</span></span> <span data-ttu-id="f20c9-132">Weitere Informationen finden Sie unter [Gerätebilder](../service-description/device-images.md).</span><span class="sxs-lookup"><span data-stu-id="f20c9-132">For more information, see [Device images](../service-description/device-images.md).</span></span>

<span data-ttu-id="f20c9-133">Das [von Microsoft Managed Desktop](../service-description/device-images.md#universal-image) bereitgestellte universelle Bild enthält die folgenden Sprachen und für Windows 10:</span><span class="sxs-lookup"><span data-stu-id="f20c9-133">The [universal image](../service-description/device-images.md#universal-image) provided by Microsoft Managed Desktop includes these languages and for Windows 10:</span></span>

- <span data-ttu-id="f20c9-134">Arabisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-134">Arabic</span></span>
- <span data-ttu-id="f20c9-135">Bulgarisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-135">Bulgarian</span></span>
- <span data-ttu-id="f20c9-136">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="f20c9-136">Chinese Simplified</span></span>
- <span data-ttu-id="f20c9-137">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="f20c9-137">Chinese Traditional</span></span>
- <span data-ttu-id="f20c9-138">Kroatisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-138">Croatian</span></span>
- <span data-ttu-id="f20c9-139">Tschechisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-139">Czech</span></span>
- <span data-ttu-id="f20c9-140">Dänisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-140">Danish</span></span>  
- <span data-ttu-id="f20c9-141">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-141">Dutch</span></span>  
- <span data-ttu-id="f20c9-142">Englisch (US, GB, AU, CA, IN)</span><span class="sxs-lookup"><span data-stu-id="f20c9-142">English (US, GB, AU, CA, IN)</span></span>
- <span data-ttu-id="f20c9-143">Estnisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-143">Estonian</span></span>
- <span data-ttu-id="f20c9-144">Finnisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-144">Finnish</span></span> 
- <span data-ttu-id="f20c9-145">Französisch (Frankreich, Kanada)</span><span class="sxs-lookup"><span data-stu-id="f20c9-145">French (France, Canada)</span></span>
- <span data-ttu-id="f20c9-146">Deutsch</span><span class="sxs-lookup"><span data-stu-id="f20c9-146">German</span></span>
- <span data-ttu-id="f20c9-147">Griechisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-147">Greek</span></span>
- <span data-ttu-id="f20c9-148">Hebräisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-148">Hebrew</span></span>
- <span data-ttu-id="f20c9-149">Ungarisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-149">Hungarian</span></span>
- <span data-ttu-id="f20c9-150">Indonesisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-150">Indonesian</span></span>
- <span data-ttu-id="f20c9-151">Italienisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-151">Italian</span></span>
- <span data-ttu-id="f20c9-152">Japanisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-152">Japanese</span></span>
- <span data-ttu-id="f20c9-153">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-153">Korean</span></span>
- <span data-ttu-id="f20c9-154">Lettisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-154">Latvian</span></span>
- <span data-ttu-id="f20c9-155">Litauisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-155">Lithuanian</span></span>
- <span data-ttu-id="f20c9-156">Norwegisch (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="f20c9-156">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="f20c9-157">Polnisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-157">Polish</span></span>
- <span data-ttu-id="f20c9-158">Portugiesisch (Brasilien)</span><span class="sxs-lookup"><span data-stu-id="f20c9-158">Portuguese (Brazil)</span></span>
- <span data-ttu-id="f20c9-159">Portugiesisch (Portugal)</span><span class="sxs-lookup"><span data-stu-id="f20c9-159">Portuguese (Portugal)</span></span>
- <span data-ttu-id="f20c9-160">Rumänisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-160">Romanian</span></span>
- <span data-ttu-id="f20c9-161">Russisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-161">Russian</span></span> 
- <span data-ttu-id="f20c9-162">Serbisch (lateinisches Alphabet)</span><span class="sxs-lookup"><span data-stu-id="f20c9-162">Serbian (Latin alphabet)</span></span>
- <span data-ttu-id="f20c9-163">Slowakisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-163">Slovak</span></span>
- <span data-ttu-id="f20c9-164">Slowenisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-164">Slovenian</span></span>
- <span data-ttu-id="f20c9-165">Spanisch (Spanien, Mexiko)</span><span class="sxs-lookup"><span data-stu-id="f20c9-165">Spanish (Spain, Mexico)</span></span>
- <span data-ttu-id="f20c9-166">Schwedisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-166">Swedish</span></span>
- <span data-ttu-id="f20c9-167">Thailändisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-167">Thai</span></span>
- <span data-ttu-id="f20c9-168">Türkisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-168">Turkish</span></span>
- <span data-ttu-id="f20c9-169">Ukrainisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-169">Ukrainian</span></span>
- <span data-ttu-id="f20c9-170">Vietnamesisch</span><span class="sxs-lookup"><span data-stu-id="f20c9-170">Vietnamese</span></span>

<span data-ttu-id="f20c9-171">Microsoft 365 Apps für Enterprise kann eine etwas andere Liste unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f20c9-171">Microsoft 365 Apps for Enterprise might support a slightly different list.</span></span>

<span data-ttu-id="f20c9-172">Wenn Ihre Benutzer eine andere Sprache als die [](../working-with-managed-desktop/admin-support.md) hier aufgeführten benötigen, stellen Sie eine Supportanfrage mithilfe des [Admin-Portals.](access-admin-portal.md)</span><span class="sxs-lookup"><span data-stu-id="f20c9-172">If your users need a language other than the ones listed here, file a [support request](../working-with-managed-desktop/admin-support.md) by using the [Admin portal](access-admin-portal.md).</span></span>

## <a name="languages-for-support-and-operations"></a><span data-ttu-id="f20c9-173">Sprachen für Support und Vorgänge</span><span class="sxs-lookup"><span data-stu-id="f20c9-173">Languages for support and operations</span></span>

### <a name="user-support"></a><span data-ttu-id="f20c9-174">Benutzerunterstützung</span><span class="sxs-lookup"><span data-stu-id="f20c9-174">User support</span></span>
<span data-ttu-id="f20c9-175">Microsoft Managed Desktop bietet Unterstützung nur in Englisch.</span><span class="sxs-lookup"><span data-stu-id="f20c9-175">Microsoft Managed Desktop provides support only in English.</span></span> <span data-ttu-id="f20c9-176">Wenn Benutzer eine andere Sprache in der Hilfe-App auswählen, erhalten sie Unterstützung von den allgemeinen Microsoft-Supportkanälen und nicht direkt von Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f20c9-176">If users choose another language in the Get Help app, they will get support from the general Microsoft support channels, rather than support directly from Microsoft Managed Desktop.</span></span> <span data-ttu-id="f20c9-177">Weitere Informationen finden Sie unter [Abrufen von Hilfe für Benutzer](../working-with-managed-desktop/end-user-support.md).</span><span class="sxs-lookup"><span data-stu-id="f20c9-177">For more information, see [Getting help for users](../working-with-managed-desktop/end-user-support.md).</span></span>

<span data-ttu-id="f20c9-178">Wenn Ihre Benutzer Unterstützung in anderen Sprachen benötigen, müssen Sie dies über Nicht-Microsoft-Supportquellen oder aus Ihrer eigenen Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f20c9-178">If your users need support in other languages, you'll have to provide that through non-Microsoft support sources or from your own organization.</span></span>

### <a name="admin-support-and-operations"></a><span data-ttu-id="f20c9-179">Administratorunterstützung und -vorgänge</span><span class="sxs-lookup"><span data-stu-id="f20c9-179">Admin support and operations</span></span>
<span data-ttu-id="f20c9-180">Microsoft Managed Desktop bietet Administratorunterstützung nur in Englisch.</span><span class="sxs-lookup"><span data-stu-id="f20c9-180">Microsoft Managed Desktop provides admin support only in English.</span></span> <span data-ttu-id="f20c9-181">Dies umfasst das Administratorportal und die gesamte Kommunikation mit Microsoft Managed Desktop Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="f20c9-181">This includes the Admin portal and all communications with Microsoft Managed Desktop Operations.</span></span> <span data-ttu-id="f20c9-182">Sie sollten davon ausgehen, dass alle administratorbezogenen Interaktionen und Schnittstellen in Englisch sind, sofern nicht anders angegeben.</span><span class="sxs-lookup"><span data-stu-id="f20c9-182">You should assume that all admin-related interactions and interfaces will be in English, unless specified otherwise.</span></span>


