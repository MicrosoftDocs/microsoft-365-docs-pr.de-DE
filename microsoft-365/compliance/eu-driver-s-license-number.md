---
title: EU-Führerscheinnummer
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081483"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="5e10a-104">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-104">EU Driver's License Number</span></span>

<span data-ttu-id="5e10a-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="5e10a-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="5e10a-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="5e10a-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5e10a-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="5e10a-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-108">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-108">Format</span></span>

<span data-ttu-id="5e10a-109">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-110">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-110">Pattern</span></span>

<span data-ttu-id="5e10a-111">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-112">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-112">Checksum</span></span>

<span data-ttu-id="5e10a-113">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-114">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-114">Definition</span></span>

<span data-ttu-id="5e10a-115">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-116">Der reguläre Ausdruck `Regex_austria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-117">Ein Schlüsselwort `Keywords_austria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="5e10a-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-118">Keywords</span></span>

<span data-ttu-id="5e10a-119">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-119"></span></span>
|<span data-ttu-id="5e10a-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-121">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-121">dl#</span></span>  <br/> <span data-ttu-id="5e10a-122">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-122">driver license</span></span>  <br/> <span data-ttu-id="5e10a-123">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-123">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-124">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-124">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-125">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-125">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-126">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-127">driver's licence</span></span>  <br/> <span data-ttu-id="5e10a-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-128">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-129">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-129">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-130">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="5e10a-131">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-131">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-132">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="5e10a-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="5e10a-134">Fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="5e10a-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="5e10a-135">Belgien</span><span class="sxs-lookup"><span data-stu-id="5e10a-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-136">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-136">Format</span></span>

<span data-ttu-id="5e10a-137">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-138">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-138">Pattern</span></span>

<span data-ttu-id="5e10a-139">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-140">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-140">Checksum</span></span>

<span data-ttu-id="5e10a-141">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-142">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-142">Definition</span></span>

<span data-ttu-id="5e10a-143">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-144">Der reguläre Ausdruck `Regex_belgium_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-145">Ein Schlüsselwort `Keywords_belgium_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5e10a-146">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-146">Keywords</span></span>

<span data-ttu-id="5e10a-147">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-147"></span></span>
|<span data-ttu-id="5e10a-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-149">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-149">dl#</span></span>  <br/> <span data-ttu-id="5e10a-150">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-150">driver license</span></span>  <br/> <span data-ttu-id="5e10a-151">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-151">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-152">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-152">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-153">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-153">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-154">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-155">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-156">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-157">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-157">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-158">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-158">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-159">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5e10a-160">rijbewijs</span></span>  <br/> <span data-ttu-id="5e10a-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="5e10a-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="5e10a-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="5e10a-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="5e10a-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="5e10a-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="5e10a-166">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="5e10a-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="5e10a-167">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="5e10a-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="5e10a-168">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="5e10a-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-169">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-169">Format</span></span>

<span data-ttu-id="5e10a-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-171">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-171">Pattern</span></span>

<span data-ttu-id="5e10a-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-173">Checksum</span></span>

<span data-ttu-id="5e10a-174">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-175">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-175">Definition</span></span>

<span data-ttu-id="5e10a-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-177">Der reguläre Ausdruck `Regex_bulgaria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-178">Ein Schlüsselwort `Keywords_bulgaria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="5e10a-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-179">Keywords</span></span>

<span data-ttu-id="5e10a-180">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-180"></span></span>
|<span data-ttu-id="5e10a-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-182">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-182">dl#</span></span>  <br/> <span data-ttu-id="5e10a-183">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-183">driver license</span></span>  <br/> <span data-ttu-id="5e10a-184">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-184">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-185">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-185">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-186">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-186">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-187">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-188">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-189">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-190">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-190">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-191">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-191">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-192">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-192">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-193">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="5e10a-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="5e10a-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="5e10a-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="5e10a-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="5e10a-196">сумпс</span></span>  <br/> <span data-ttu-id="5e10a-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="5e10a-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="5e10a-198">Kroatien</span><span class="sxs-lookup"><span data-stu-id="5e10a-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-199">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-199">Format</span></span>

<span data-ttu-id="5e10a-200">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-201">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-201">Pattern</span></span>

<span data-ttu-id="5e10a-202">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-203">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-203">Checksum</span></span>

<span data-ttu-id="5e10a-204">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-205">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-205">Definition</span></span>

<span data-ttu-id="5e10a-206">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-207">Der reguläre Ausdruck `Regex_croatia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-208">Ein Schlüsselwort `Keywords_croatia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5e10a-209">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-209">Keywords</span></span>

<span data-ttu-id="5e10a-210">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-210"></span></span>
|<span data-ttu-id="5e10a-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-212">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-212">dl#</span></span>  <br/> <span data-ttu-id="5e10a-213">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-213">driver license</span></span>  <br/> <span data-ttu-id="5e10a-214">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-214">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-215">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-215">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-216">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-216">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-217">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-218">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-219">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-220">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-220">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-221">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-221">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-222">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-222">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-223">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="5e10a-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="5e10a-225">Zypern</span><span class="sxs-lookup"><span data-stu-id="5e10a-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-226">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-226">Format</span></span>

<span data-ttu-id="5e10a-227">12 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-228">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-228">Pattern</span></span>

<span data-ttu-id="5e10a-229">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-230">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-230">Checksum</span></span>

<span data-ttu-id="5e10a-231">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-232">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-232">Definition</span></span>

<span data-ttu-id="5e10a-233">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-234">Der reguläre Ausdruck `Regex_cyprus_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-235">Ein Schlüsselwort `Keywords_cyprus_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-236">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-236">Keywords</span></span>

<span data-ttu-id="5e10a-237">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-237"></span></span>
|<span data-ttu-id="5e10a-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-239">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-239">dl#</span></span>  <br/> <span data-ttu-id="5e10a-240">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-240">driver license</span></span>  <br/> <span data-ttu-id="5e10a-241">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-241">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-242">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-242">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-243">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-243">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-244">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-245">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-246">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-246">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-247">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-247">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-248">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-248">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-249">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5e10a-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="5e10a-251">Tschechien</span><span class="sxs-lookup"><span data-stu-id="5e10a-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-252">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-252">Format</span></span>

<span data-ttu-id="5e10a-253">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-254">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-254">Pattern</span></span>

<span data-ttu-id="5e10a-255">Acht Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="5e10a-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="5e10a-256">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="5e10a-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="5e10a-257">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="5e10a-257">A space (optional)</span></span>
    
- <span data-ttu-id="5e10a-258">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-259">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-259">Checksum</span></span>

<span data-ttu-id="5e10a-260">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-261">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-261">Definition</span></span>

<span data-ttu-id="5e10a-262">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-263">Der reguläre Ausdruck `Regex_czech_republic_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-264">Ein Schlüsselwort `Keywords_czech_republic_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5e10a-265">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-265">Keywords</span></span>

<span data-ttu-id="5e10a-266">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-266"></span></span>
|<span data-ttu-id="5e10a-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-268">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-268">dl#</span></span>  <br/> <span data-ttu-id="5e10a-269">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-269">driver license</span></span>  <br/> <span data-ttu-id="5e10a-270">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-270">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-271">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-271">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-272">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-272">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-273">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-274">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-275">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-276">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-276">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-277">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-277">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-278">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-278">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-279">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-279">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-280">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="5e10a-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="5e10a-282">Dänemark</span><span class="sxs-lookup"><span data-stu-id="5e10a-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-283">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-283">Format</span></span>

<span data-ttu-id="5e10a-284">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-285">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-285">Pattern</span></span>

<span data-ttu-id="5e10a-286">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-287">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-287">Checksum</span></span>

<span data-ttu-id="5e10a-288">Ja</span><span class="sxs-lookup"><span data-stu-id="5e10a-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-289">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-289">Definition</span></span>

<span data-ttu-id="5e10a-290">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-291">Der reguläre Ausdruck `Regex_denmark_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-292">Ein Schlüsselwort `Keywords_denmark_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="5e10a-293">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-293">Keywords</span></span>

<span data-ttu-id="5e10a-294">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-294"></span></span>
|<span data-ttu-id="5e10a-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-296">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-296">dl#</span></span>  <br/> <span data-ttu-id="5e10a-297">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-297">driver license</span></span>  <br/> <span data-ttu-id="5e10a-298">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-298">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-299">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-299">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-300">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-300">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-301">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-302">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-303">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-304">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-304">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-305">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-305">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-306">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-306">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-307">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="5e10a-308">kørekort</span></span>  <br/> <span data-ttu-id="5e10a-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="5e10a-310">Estland</span><span class="sxs-lookup"><span data-stu-id="5e10a-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-311">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-311">Format</span></span>

<span data-ttu-id="5e10a-312">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-313">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-313">Pattern</span></span>

<span data-ttu-id="5e10a-314">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="5e10a-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5e10a-315">Die Buchstaben "et" (unterscheidet nicht zwischen Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="5e10a-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5e10a-316">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-317">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-317">Checksum</span></span>

<span data-ttu-id="5e10a-318">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-319">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-319">Definition</span></span>

<span data-ttu-id="5e10a-320">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-321">Der reguläre Ausdruck `Regex_estonia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-322">Ein Schlüsselwort `Keywords_estonia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-323">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-323">Keywords</span></span>

<span data-ttu-id="5e10a-324">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-324"></span></span>
|<span data-ttu-id="5e10a-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-326">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-326">dl#</span></span>  <br/> <span data-ttu-id="5e10a-327">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-327">driver license</span></span>  <br/> <span data-ttu-id="5e10a-328">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-328">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-329">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-329">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-330">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-330">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-331">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-331">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-332">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-333">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-334">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-335">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-335">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-336">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-336">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-337">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5e10a-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="5e10a-339">Finnland</span><span class="sxs-lookup"><span data-stu-id="5e10a-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-340">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-340">Format</span></span>

<span data-ttu-id="5e10a-341">10 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="5e10a-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-342">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-342">Pattern</span></span>

<span data-ttu-id="5e10a-343">10 Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="5e10a-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5e10a-344">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-344">Six digits</span></span> 
    
- <span data-ttu-id="5e10a-345">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="5e10a-345">A hyphen</span></span>
    
-  <span data-ttu-id="5e10a-346">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5e10a-347">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-347">Checksum</span></span>

<span data-ttu-id="5e10a-348">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-349">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-349">Definition</span></span>

<span data-ttu-id="5e10a-350">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-351">Der reguläre Ausdruck `Regex_finland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-352">Ein Schlüsselwort `Keywords_finland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-353">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-353">Keywords</span></span>

<span data-ttu-id="5e10a-354">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-354"></span></span>
|<span data-ttu-id="5e10a-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-356">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-356">dl#</span></span>  <br/> <span data-ttu-id="5e10a-357">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-357">driver license</span></span>  <br/> <span data-ttu-id="5e10a-358">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-358">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-359">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-359">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-360">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-360">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-361">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-362">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-363">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-364">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-364">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-365">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-365">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-366">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-366">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-367">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="5e10a-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="5e10a-369">Frankreich</span><span class="sxs-lookup"><span data-stu-id="5e10a-369">France</span></span>

<span data-ttu-id="5e10a-370">Ausführliche Informationen finden Sie im Abschnitt "französische Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5e10a-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="5e10a-371">Deutschland</span><span class="sxs-lookup"><span data-stu-id="5e10a-371">Germany</span></span>

<span data-ttu-id="5e10a-372">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5e10a-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="5e10a-373">Griechenland</span><span class="sxs-lookup"><span data-stu-id="5e10a-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-374">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-374">Format</span></span>

<span data-ttu-id="5e10a-375">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-376">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-376">Pattern</span></span>

 <span data-ttu-id="5e10a-377">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5e10a-378">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-378">Checksum</span></span>

<span data-ttu-id="5e10a-379">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-380">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-380">Definition</span></span>

<span data-ttu-id="5e10a-381">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-382">Der reguläre Ausdruck `Regex_greece_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-383">Ein Schlüsselwort `Keywords_greece_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-384">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-384">Keywords</span></span>

<span data-ttu-id="5e10a-385">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-385"></span></span>
|<span data-ttu-id="5e10a-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-387">dlL#</span></span>  <br/> <span data-ttu-id="5e10a-388">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-388">driver license</span></span>  <br/> <span data-ttu-id="5e10a-389">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-389">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-390">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-390">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-391">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-391">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-392">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-393">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-394">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-395">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-395">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-396">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-396">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-397">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-397">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-398">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="5e10a-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="5e10a-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="5e10a-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="5e10a-401">Ungarn</span><span class="sxs-lookup"><span data-stu-id="5e10a-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-402">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-402">Format</span></span>

<span data-ttu-id="5e10a-403">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-404">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-404">Pattern</span></span>

<span data-ttu-id="5e10a-405">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="5e10a-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="5e10a-406">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="5e10a-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5e10a-407">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-408">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-408">Checksum</span></span>

<span data-ttu-id="5e10a-409">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-410">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-410">Definition</span></span>

<span data-ttu-id="5e10a-411">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-412">Der reguläre Ausdruck `Regex_hungary_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-413">Ein Schlüsselwort `Keywords_hungary_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-414">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-414">Keywords</span></span>

<span data-ttu-id="5e10a-415">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-415"></span></span>
|<span data-ttu-id="5e10a-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-417">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-417">dl#</span></span>  <br/> <span data-ttu-id="5e10a-418">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-418">driver license</span></span>  <br/> <span data-ttu-id="5e10a-419">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-419">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-420">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-420">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-421">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-421">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-422">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-423">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-424">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-425">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-425">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-426">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-426">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-427">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-427">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-428">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="5e10a-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="5e10a-430">Irland</span><span class="sxs-lookup"><span data-stu-id="5e10a-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-431">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-431">Format</span></span>

<span data-ttu-id="5e10a-432">Sechs Ziffern, gefolgt von vier Buchstaben</span><span class="sxs-lookup"><span data-stu-id="5e10a-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-433">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-433">Pattern</span></span>

<span data-ttu-id="5e10a-434">Sechs Ziffern und vier Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="5e10a-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="5e10a-435">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-435">Six digits</span></span>
    
- <span data-ttu-id="5e10a-436">Vier Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="5e10a-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-437">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-437">Checksum</span></span>

<span data-ttu-id="5e10a-438">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-439">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-439">Definition</span></span>

<span data-ttu-id="5e10a-440">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-441">Der reguläre Ausdruck `Regex_ireland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-442">Ein Schlüsselwort `Keywords_ireland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-443">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-443">Keywords</span></span>

<span data-ttu-id="5e10a-444">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-444"></span></span>
|<span data-ttu-id="5e10a-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-446">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-446">dl#</span></span>  <br/> <span data-ttu-id="5e10a-447">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-447">driver license</span></span>  <br/> <span data-ttu-id="5e10a-448">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-448">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-449">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-449">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-450">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-450">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-451">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-452">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-453">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-454">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-454">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-455">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-455">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-456">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-456">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-457">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="5e10a-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="5e10a-459">Italien</span><span class="sxs-lookup"><span data-stu-id="5e10a-459">Italy</span></span>

<span data-ttu-id="5e10a-460">Ausführliche Informationen finden Sie im Abschnitt "Italien-Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5e10a-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="5e10a-461">Lettland</span><span class="sxs-lookup"><span data-stu-id="5e10a-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-462">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-462">Format</span></span>

<span data-ttu-id="5e10a-463">Drei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-464">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-464">Pattern</span></span>

<span data-ttu-id="5e10a-465">Drei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="5e10a-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="5e10a-466">Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="5e10a-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5e10a-467">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-468">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-468">Checksum</span></span>

<span data-ttu-id="5e10a-469">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-470">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-470">Definition</span></span>

<span data-ttu-id="5e10a-471">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-472">Der reguläre Ausdruck `Regex_latvia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-473">Ein Schlüsselwort `Keywords_latvia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-474">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-474">Keywords</span></span>

<span data-ttu-id="5e10a-475">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-475"></span></span>
|<span data-ttu-id="5e10a-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-477">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-477">dl#</span></span>  <br/> <span data-ttu-id="5e10a-478">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-478">driver license</span></span>  <br/> <span data-ttu-id="5e10a-479">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-479">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-480">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-480">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-481">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-481">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-482">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-483">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-484">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-485">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-485">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-486">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-486">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-487">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-487">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-488">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="5e10a-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="5e10a-490">Litauen</span><span class="sxs-lookup"><span data-stu-id="5e10a-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-491">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-491">Format</span></span>

<span data-ttu-id="5e10a-492">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-493">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-493">Pattern</span></span>

 <span data-ttu-id="5e10a-494">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5e10a-495">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-495">Checksum</span></span>

<span data-ttu-id="5e10a-496">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-497">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-497">Definition</span></span>

<span data-ttu-id="5e10a-498">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-499">Der reguläre Ausdruck `Regex_lithuania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-500">Ein Schlüsselwort `Keywords_lithuania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-501">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-501">Keywords</span></span>

<span data-ttu-id="5e10a-502">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-502"></span></span>
|<span data-ttu-id="5e10a-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-504">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-504">dl#</span></span>  <br/> <span data-ttu-id="5e10a-505">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-505">driver license</span></span>  <br/> <span data-ttu-id="5e10a-506">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-506">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-507">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-507">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-508">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-508">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-509">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-510">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-511">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-512">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-512">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-513">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-513">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-514">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-514">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-515">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-516">Vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="5e10a-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="5e10a-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="5e10a-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-518">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-518">Format</span></span>

<span data-ttu-id="5e10a-519">Sechs Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-520">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-520">Pattern</span></span>

 <span data-ttu-id="5e10a-521">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5e10a-522">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-522">Checksum</span></span>

<span data-ttu-id="5e10a-523">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-524">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-524">Definition</span></span>

<span data-ttu-id="5e10a-525">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-526">Der reguläre Ausdruck `Regex_luxemburg_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-527">Ein Schlüsselwort `Keywords_luxemburg_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-528">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-528">Keywords</span></span>

<span data-ttu-id="5e10a-529">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-529"></span></span>
|<span data-ttu-id="5e10a-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-531">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-531">dl#</span></span>  <br/> <span data-ttu-id="5e10a-532">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-532">driver license</span></span>  <br/> <span data-ttu-id="5e10a-533">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-533">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-534">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-534">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-535">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-535">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-536">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-537">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-538">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-539">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-539">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-540">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-540">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-541">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-541">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-542">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="5e10a-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="5e10a-544">Malta</span><span class="sxs-lookup"><span data-stu-id="5e10a-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-545">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-545">Format</span></span>

<span data-ttu-id="5e10a-546">Kombination aus zwei Zeichen und sechs Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-547">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-547">Pattern</span></span>

<span data-ttu-id="5e10a-548">Kombination aus zwei Zeichen und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="5e10a-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="5e10a-549">Zwei Zeichen (Ziffern oder Buchstaben, bei denen die Groß-/Kleinschreibung nicht beachtet wird)</span><span class="sxs-lookup"><span data-stu-id="5e10a-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="5e10a-550">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="5e10a-550">A space (optional)</span></span>
    
- <span data-ttu-id="5e10a-551">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-551">Three digits</span></span>
    
- <span data-ttu-id="5e10a-552">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="5e10a-552">A space (optional)</span></span>
    
- <span data-ttu-id="5e10a-553">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-554">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-554">Checksum</span></span>

<span data-ttu-id="5e10a-555">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-556">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-556">Definition</span></span>

<span data-ttu-id="5e10a-557">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-558">Der reguläre Ausdruck `Regex_malta_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-559">Ein Schlüsselwort `Keywords_malta_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-560">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-560">Keywords</span></span>

<span data-ttu-id="5e10a-561">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-561"></span></span>
|<span data-ttu-id="5e10a-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-563">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-563">dl#</span></span>  <br/> <span data-ttu-id="5e10a-564">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-564">driver license</span></span>  <br/> <span data-ttu-id="5e10a-565">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-565">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-566">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-566">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-567">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-567">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-568">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-569">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-570">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-571">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-571">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-572">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-572">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-573">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-573">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-574">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-575">Liċenzja TAS-Sewqan</span><span class="sxs-lookup"><span data-stu-id="5e10a-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="5e10a-576">Niederlande</span><span class="sxs-lookup"><span data-stu-id="5e10a-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-577">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-577">Format</span></span>

<span data-ttu-id="5e10a-578">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-579">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-579">Pattern</span></span>

<span data-ttu-id="5e10a-580">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-581">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-581">Checksum</span></span>

<span data-ttu-id="5e10a-582">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-583">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-583">Definition</span></span>

<span data-ttu-id="5e10a-584">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-585">Der reguläre Ausdruck `Regex_netherlands_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-586">Ein Schlüsselwort `Keywords_netherlands_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-587">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-587">Keywords</span></span>

<span data-ttu-id="5e10a-588">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-588"></span></span>
|<span data-ttu-id="5e10a-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-590">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-590">dl#</span></span>  <br/> <span data-ttu-id="5e10a-591">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-591">driver license</span></span>  <br/> <span data-ttu-id="5e10a-592">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-592">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-593">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-593">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-594">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-594">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-595">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-596">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-597">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-598">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-598">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-599">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-599">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-600">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-600">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-601">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="5e10a-602">permis de conduire</span></span>  <br/> <span data-ttu-id="5e10a-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="5e10a-603">rijbewijs</span></span>  <br/> <span data-ttu-id="5e10a-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="5e10a-605">Polen</span><span class="sxs-lookup"><span data-stu-id="5e10a-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-606">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-606">Format</span></span>

<span data-ttu-id="5e10a-607">14 Ziffern mit 2 Schrägstrichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-608">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-608">Pattern</span></span>

<span data-ttu-id="5e10a-609">14 Ziffern und 2 Schrägstriche:</span><span class="sxs-lookup"><span data-stu-id="5e10a-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="5e10a-610">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-610">Five digits</span></span> 
    
- <span data-ttu-id="5e10a-611">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="5e10a-611">A forward slash</span></span>
    
- <span data-ttu-id="5e10a-612">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-612">Two digits</span></span>
    
- <span data-ttu-id="5e10a-613">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="5e10a-613">A forward slash</span></span>
    
- <span data-ttu-id="5e10a-614">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-615">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-615">Checksum</span></span>

<span data-ttu-id="5e10a-616">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-617">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-617">Definition</span></span>

<span data-ttu-id="5e10a-618">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-619">Der reguläre Ausdruck `Regex_poland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-620">Ein Schlüsselwort `Keywords_poland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-621">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-621">Keywords</span></span>

<span data-ttu-id="5e10a-622">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-622"></span></span>
|<span data-ttu-id="5e10a-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-624">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-624">dl#</span></span>  <br/> <span data-ttu-id="5e10a-625">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-625">driver license</span></span>  <br/> <span data-ttu-id="5e10a-626">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-626">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-627">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-627">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-628">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-628">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-629">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-630">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-631">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-632">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-632">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-633">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-633">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-634">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-634">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-635">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-636">Prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="5e10a-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="5e10a-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="5e10a-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-638">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-638">Format</span></span>

<span data-ttu-id="5e10a-639">Zwei Buchstaben, gefolgt von sieben Zahlen im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-640">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-640">Pattern</span></span>

<span data-ttu-id="5e10a-641">Zwei Buchstaben, gefolgt von sieben Zahlen mit Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="5e10a-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="5e10a-642">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="5e10a-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="5e10a-643">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="5e10a-643">A hyphen</span></span>
    
- <span data-ttu-id="5e10a-644">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-644">Six digits</span></span>
    
- <span data-ttu-id="5e10a-645">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-645">A space</span></span>
    
- <span data-ttu-id="5e10a-646">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="5e10a-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-647">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-647">Checksum</span></span>

<span data-ttu-id="5e10a-648">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-649">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-649">Definition</span></span>

<span data-ttu-id="5e10a-650">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-651">Der reguläre Ausdruck `Regex_portugal_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-652">Ein Schlüsselwort `Keywords_portugal_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-653">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-653">Keywords</span></span>

<span data-ttu-id="5e10a-654">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-654"></span></span>
|<span data-ttu-id="5e10a-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-656">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-656">dl#</span></span>  <br/> <span data-ttu-id="5e10a-657">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-657">driver license</span></span>  <br/> <span data-ttu-id="5e10a-658">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-658">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-659">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-659">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-660">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-660">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-661">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-662">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-663">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-664">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-664">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-665">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-665">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-666">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-666">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-667">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="5e10a-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="5e10a-669">Rumänien</span><span class="sxs-lookup"><span data-stu-id="5e10a-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-670">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-670">Format</span></span>

<span data-ttu-id="5e10a-671">Ein Zeichen gefolgt von acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-672">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-672">Pattern</span></span>

<span data-ttu-id="5e10a-673">Ein Zeichen gefolgt von acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="5e10a-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="5e10a-674">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="5e10a-675">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-676">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-676">Checksum</span></span>

<span data-ttu-id="5e10a-677">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-678">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-678">Definition</span></span>

<span data-ttu-id="5e10a-679">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-680">Der reguläre Ausdruck `Regex_romania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-681">Ein Schlüsselwort `Keywords_romania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-682">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-682">Keywords</span></span>

<span data-ttu-id="5e10a-683">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-683"></span></span>
|<span data-ttu-id="5e10a-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-685">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-685">dl#</span></span>  <br/> <span data-ttu-id="5e10a-686">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-686">driver license</span></span>  <br/> <span data-ttu-id="5e10a-687">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-687">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-688">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-688">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-689">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-689">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-690">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-691">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-692">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-693">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-693">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-694">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-694">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-695">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-695">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-696">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="5e10a-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="5e10a-698">Slowakei</span><span class="sxs-lookup"><span data-stu-id="5e10a-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-699">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-699">Format</span></span>

<span data-ttu-id="5e10a-700">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-701">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-701">Pattern</span></span>

<span data-ttu-id="5e10a-702">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="5e10a-703">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="5e10a-704">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5e10a-705">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-705">Checksum</span></span>

<span data-ttu-id="5e10a-706">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-707">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-707">Definition</span></span>

<span data-ttu-id="5e10a-708">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-709">Der reguläre Ausdruck `Regex_slovakia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-710">Ein Schlüsselwort `Keywords_slovakia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-711">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-711">Keywords</span></span>

<span data-ttu-id="5e10a-712">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-712"></span></span>
|<span data-ttu-id="5e10a-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-714">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-714">dl#</span></span>  <br/> <span data-ttu-id="5e10a-715">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-715">driver license</span></span>  <br/> <span data-ttu-id="5e10a-716">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-716">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-717">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-717">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-718">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-718">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-719">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-720">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-721">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-722">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-722">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-723">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-723">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-724">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-724">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-725">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="5e10a-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="5e10a-727">Slowenien</span><span class="sxs-lookup"><span data-stu-id="5e10a-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-728">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-728">Format</span></span>

<span data-ttu-id="5e10a-729">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-730">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-730">Pattern</span></span>

<span data-ttu-id="5e10a-731">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5e10a-732">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-732">Checksum</span></span>

<span data-ttu-id="5e10a-733">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-734">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-734">Definition</span></span>

<span data-ttu-id="5e10a-735">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-736">Der reguläre Ausdruck `Regex_slovenia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-737">Ein Schlüsselwort `Keywords_slovenia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-738">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-738">Keywords</span></span>

<span data-ttu-id="5e10a-739">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-739"></span></span>
|<span data-ttu-id="5e10a-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-741">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-741">dl#</span></span>  <br/> <span data-ttu-id="5e10a-742">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-742">driver license</span></span>  <br/> <span data-ttu-id="5e10a-743">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-743">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-744">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-744">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-745">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-745">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-746">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-747">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-748">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-749">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-749">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-750">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-750">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-751">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-751">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-752">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="5e10a-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="5e10a-754">Spanien</span><span class="sxs-lookup"><span data-stu-id="5e10a-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-755">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-755">Format</span></span>

<span data-ttu-id="5e10a-756">Acht Ziffern, gefolgt von einem Zeichen</span><span class="sxs-lookup"><span data-stu-id="5e10a-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-757">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-757">Pattern</span></span>

<span data-ttu-id="5e10a-758">Acht Ziffern, gefolgt von einem Zeichen:</span><span class="sxs-lookup"><span data-stu-id="5e10a-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="5e10a-759">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-759">Eight digits</span></span> 
    
- <span data-ttu-id="5e10a-760">Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="5e10a-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-761">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-761">Checksum</span></span>

<span data-ttu-id="5e10a-762">Ja</span><span class="sxs-lookup"><span data-stu-id="5e10a-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-763">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-763">Definition</span></span>

<span data-ttu-id="5e10a-764">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-765">Die- `Func_spain_eu_driver's_license_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-766">Ein Schlüsselwort `Keywords_spain_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5e10a-767">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-767">Keywords</span></span>

<span data-ttu-id="5e10a-768">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-768"></span></span>
|<span data-ttu-id="5e10a-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-770">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-771">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-771">dl#</span></span>  <br/> <span data-ttu-id="5e10a-772">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-772">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-773">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-773">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-774">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-774">driver license</span></span>  <br/> <span data-ttu-id="5e10a-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-775">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-776">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-777">driver's licence</span></span>  <br/> <span data-ttu-id="5e10a-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-778">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-779">Führerschein</span><span class="sxs-lookup"><span data-stu-id="5e10a-779">driving licence</span></span>  <br/> <span data-ttu-id="5e10a-780">driving license</span><span class="sxs-lookup"><span data-stu-id="5e10a-780">driving license</span></span>  <br/> <span data-ttu-id="5e10a-781">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-781">driver licence number</span></span>  <br/> <span data-ttu-id="5e10a-782">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-782">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-783">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-783">drivers licence number</span></span>  <br/> <span data-ttu-id="5e10a-784">Lizenznummer für Treiber</span><span class="sxs-lookup"><span data-stu-id="5e10a-784">drivers license number</span></span>  <br/> <span data-ttu-id="5e10a-785">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-785">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-786">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-786">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-787">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-787">driving licence number</span></span>  <br/> <span data-ttu-id="5e10a-788">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-788">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-789">Führerschein</span><span class="sxs-lookup"><span data-stu-id="5e10a-789">driving permit</span></span>  <br/> <span data-ttu-id="5e10a-790">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-790">driving permit number</span></span>  <br/> <span data-ttu-id="5e10a-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="5e10a-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="5e10a-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="5e10a-792">permiso conducción</span></span>  <br/> <span data-ttu-id="5e10a-793">número licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="5e10a-794">número de carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="5e10a-795">número Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="5e10a-796">licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-796">licencia conducir</span></span>  <br/> <span data-ttu-id="5e10a-797">número de Permiso de Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="5e10a-798">número de Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="5e10a-799">número Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="5e10a-800">Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-800">permiso conducir</span></span>  <br/> <span data-ttu-id="5e10a-801">licencia de Manejo</span><span class="sxs-lookup"><span data-stu-id="5e10a-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="5e10a-802">El Carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="5e10a-803">Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="5e10a-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="5e10a-804">Schweden</span><span class="sxs-lookup"><span data-stu-id="5e10a-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="5e10a-805">Format</span><span class="sxs-lookup"><span data-stu-id="5e10a-805">Format</span></span>

<span data-ttu-id="5e10a-806">Zehn Ziffern mit einem Bindestrich</span><span class="sxs-lookup"><span data-stu-id="5e10a-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5e10a-807">Muster</span><span class="sxs-lookup"><span data-stu-id="5e10a-807">Pattern</span></span>

<span data-ttu-id="5e10a-808">Zehn Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="5e10a-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="5e10a-809">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-809">Six digits</span></span> 
    
- <span data-ttu-id="5e10a-810">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="5e10a-810">A hyphen</span></span>
    
- <span data-ttu-id="5e10a-811">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="5e10a-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5e10a-812">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="5e10a-812">Checksum</span></span>

<span data-ttu-id="5e10a-813">No</span><span class="sxs-lookup"><span data-stu-id="5e10a-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="5e10a-814">Definition</span><span class="sxs-lookup"><span data-stu-id="5e10a-814">Definition</span></span>

<span data-ttu-id="5e10a-815">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="5e10a-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5e10a-816">Der reguläre Ausdruck `Regex_sweden_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="5e10a-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5e10a-817">Ein Schlüsselwort `Keywords_sweden_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="5e10a-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="5e10a-818">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5e10a-818">Keywords</span></span>

<span data-ttu-id="5e10a-819">| |</span><span class="sxs-lookup"><span data-stu-id="5e10a-819"></span></span>
|<span data-ttu-id="5e10a-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="5e10a-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="5e10a-821">DL #</span><span class="sxs-lookup"><span data-stu-id="5e10a-821">dl#</span></span>  <br/> <span data-ttu-id="5e10a-822">driver license</span><span class="sxs-lookup"><span data-stu-id="5e10a-822">driver license</span></span>  <br/> <span data-ttu-id="5e10a-823">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-823">driver license number</span></span>  <br/> <span data-ttu-id="5e10a-824">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="5e10a-824">driver licence</span></span>  <br/> <span data-ttu-id="5e10a-825">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="5e10a-825">drivers lic.</span></span>  <br/> <span data-ttu-id="5e10a-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="5e10a-826">drivers license</span></span>  <br/> <span data-ttu-id="5e10a-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="5e10a-827">drivers licence</span></span>  <br/> <span data-ttu-id="5e10a-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="5e10a-828">driver's license</span></span>  <br/> <span data-ttu-id="5e10a-829">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-829">driver's license number</span></span>  <br/> <span data-ttu-id="5e10a-830">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-830">driver's licence number</span></span>  <br/> <span data-ttu-id="5e10a-831">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="5e10a-831">driving license number</span></span>  <br/> <span data-ttu-id="5e10a-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="5e10a-832">dlno#</span></span>  <br/> <span data-ttu-id="5e10a-833">körkort</span><span class="sxs-lookup"><span data-stu-id="5e10a-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="5e10a-834">UK</span><span class="sxs-lookup"><span data-stu-id="5e10a-834">UK</span></span>

<span data-ttu-id="5e10a-835">Ausführliche Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="5e10a-835">For details, see the section "U.K.</span></span> <span data-ttu-id="5e10a-836">Nummer des Führerscheins "in [dem, wonach die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="5e10a-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5e10a-837">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e10a-837">See also</span></span>

[<span data-ttu-id="5e10a-838">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="5e10a-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

