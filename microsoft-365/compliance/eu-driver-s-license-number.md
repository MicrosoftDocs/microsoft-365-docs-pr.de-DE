---
title: EU-Führerscheinnummer
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 2e75a8724dc91ef2d895c977fdd5fcc21e7a1da4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938829"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="73419-104">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-104">EU Driver's License Number</span></span>

<span data-ttu-id="73419-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="73419-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="73419-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="73419-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="73419-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="73419-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="73419-108">Format</span><span class="sxs-lookup"><span data-stu-id="73419-108">Format</span></span>

<span data-ttu-id="73419-109">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-110">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-110">Pattern</span></span>

<span data-ttu-id="73419-111">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-112">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-112">Checksum</span></span>

<span data-ttu-id="73419-113">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-114">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-114">Definition</span></span>

<span data-ttu-id="73419-115">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-116">Der reguläre Ausdruck `Regex_austria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-117">Ein Schlüsselwort `Keywords_austria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="73419-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-118">Keywords</span></span>

<span data-ttu-id="73419-119">| |</span><span class="sxs-lookup"><span data-stu-id="73419-119">| |</span></span>
|<span data-ttu-id="73419-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-121">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-121">dl#</span></span>  <br/> <span data-ttu-id="73419-122">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-122">driver license</span></span>  <br/> <span data-ttu-id="73419-123">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-123">driver license number</span></span>  <br/> <span data-ttu-id="73419-124">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-124">driver licence</span></span>  <br/> <span data-ttu-id="73419-125">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-125">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-126">drivers license</span></span>  <br/> <span data-ttu-id="73419-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="73419-127">driver's licence</span></span>  <br/> <span data-ttu-id="73419-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-128">driver's license</span></span>  <br/> <span data-ttu-id="73419-129">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-129">driver's license number</span></span>  <br/> <span data-ttu-id="73419-130">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="73419-131">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-131">driving license number</span></span>  <br/> <span data-ttu-id="73419-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-132">dlno#</span></span>  <br/> <span data-ttu-id="73419-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="73419-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="73419-134">Fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="73419-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="73419-135">Belgien</span><span class="sxs-lookup"><span data-stu-id="73419-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="73419-136">Format</span><span class="sxs-lookup"><span data-stu-id="73419-136">Format</span></span>

<span data-ttu-id="73419-137">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-138">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-138">Pattern</span></span>

<span data-ttu-id="73419-139">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-140">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-140">Checksum</span></span>

<span data-ttu-id="73419-141">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-142">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-142">Definition</span></span>

<span data-ttu-id="73419-143">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-144">Der reguläre Ausdruck `Regex_belgium_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-145">Ein Schlüsselwort `Keywords_belgium_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="73419-146">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-146">Keywords</span></span>

<span data-ttu-id="73419-147">| |</span><span class="sxs-lookup"><span data-stu-id="73419-147">| |</span></span>
|<span data-ttu-id="73419-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-149">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-149">dl#</span></span>  <br/> <span data-ttu-id="73419-150">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-150">driver license</span></span>  <br/> <span data-ttu-id="73419-151">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-151">driver license number</span></span>  <br/> <span data-ttu-id="73419-152">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-152">driver licence</span></span>  <br/> <span data-ttu-id="73419-153">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-153">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-154">drivers license</span></span>  <br/> <span data-ttu-id="73419-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-155">drivers licence</span></span>  <br/> <span data-ttu-id="73419-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-156">driver's license</span></span>  <br/> <span data-ttu-id="73419-157">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-157">driver's license number</span></span>  <br/> <span data-ttu-id="73419-158">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-158">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-159">dlno#</span></span>  <br/> <span data-ttu-id="73419-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="73419-160">rijbewijs</span></span>  <br/> <span data-ttu-id="73419-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="73419-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="73419-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="73419-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="73419-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="73419-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="73419-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="73419-166">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="73419-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="73419-167">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="73419-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="73419-168">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="73419-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="73419-169">Format</span><span class="sxs-lookup"><span data-stu-id="73419-169">Format</span></span>

<span data-ttu-id="73419-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-171">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-171">Pattern</span></span>

<span data-ttu-id="73419-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-173">Checksum</span></span>

<span data-ttu-id="73419-174">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-175">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-175">Definition</span></span>

<span data-ttu-id="73419-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-177">Der reguläre Ausdruck `Regex_bulgaria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-178">Ein Schlüsselwort `Keywords_bulgaria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="73419-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-179">Keywords</span></span>

<span data-ttu-id="73419-180">| |</span><span class="sxs-lookup"><span data-stu-id="73419-180">| |</span></span>
|<span data-ttu-id="73419-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-182">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-182">dl#</span></span>  <br/> <span data-ttu-id="73419-183">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-183">driver license</span></span>  <br/> <span data-ttu-id="73419-184">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-184">driver license number</span></span>  <br/> <span data-ttu-id="73419-185">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-185">driver licence</span></span>  <br/> <span data-ttu-id="73419-186">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-186">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-187">drivers license</span></span>  <br/> <span data-ttu-id="73419-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-188">drivers licence</span></span>  <br/> <span data-ttu-id="73419-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-189">driver's license</span></span>  <br/> <span data-ttu-id="73419-190">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-190">driver's license number</span></span>  <br/> <span data-ttu-id="73419-191">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-191">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-192">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-192">driving license number</span></span>  <br/> <span data-ttu-id="73419-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-193">dlno#</span></span>  <br/> <span data-ttu-id="73419-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="73419-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="73419-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="73419-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="73419-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="73419-196">сумпс</span></span>  <br/> <span data-ttu-id="73419-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="73419-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="73419-198">Kroatien</span><span class="sxs-lookup"><span data-stu-id="73419-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="73419-199">Format</span><span class="sxs-lookup"><span data-stu-id="73419-199">Format</span></span>

<span data-ttu-id="73419-200">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-201">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-201">Pattern</span></span>

<span data-ttu-id="73419-202">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-203">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-203">Checksum</span></span>

<span data-ttu-id="73419-204">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-205">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-205">Definition</span></span>

<span data-ttu-id="73419-206">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-207">Der reguläre Ausdruck `Regex_croatia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-208">Ein Schlüsselwort `Keywords_croatia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="73419-209">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-209">Keywords</span></span>

<span data-ttu-id="73419-210">| |</span><span class="sxs-lookup"><span data-stu-id="73419-210">| |</span></span>
|<span data-ttu-id="73419-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-212">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-212">dl#</span></span>  <br/> <span data-ttu-id="73419-213">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-213">driver license</span></span>  <br/> <span data-ttu-id="73419-214">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-214">driver license number</span></span>  <br/> <span data-ttu-id="73419-215">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-215">driver licence</span></span>  <br/> <span data-ttu-id="73419-216">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-216">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-217">drivers license</span></span>  <br/> <span data-ttu-id="73419-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-218">drivers licence</span></span>  <br/> <span data-ttu-id="73419-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-219">driver's license</span></span>  <br/> <span data-ttu-id="73419-220">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-220">driver's license number</span></span>  <br/> <span data-ttu-id="73419-221">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-221">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-222">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-222">driving license number</span></span>  <br/> <span data-ttu-id="73419-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-223">dlno#</span></span>  <br/> <span data-ttu-id="73419-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="73419-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="73419-225">Zypern</span><span class="sxs-lookup"><span data-stu-id="73419-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="73419-226">Format</span><span class="sxs-lookup"><span data-stu-id="73419-226">Format</span></span>

<span data-ttu-id="73419-227">12 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-228">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-228">Pattern</span></span>

<span data-ttu-id="73419-229">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-230">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-230">Checksum</span></span>

<span data-ttu-id="73419-231">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-232">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-232">Definition</span></span>

<span data-ttu-id="73419-233">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-234">Der reguläre Ausdruck `Regex_cyprus_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-235">Ein Schlüsselwort `Keywords_cyprus_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-236">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-236">Keywords</span></span>

<span data-ttu-id="73419-237">| |</span><span class="sxs-lookup"><span data-stu-id="73419-237">| |</span></span>
|<span data-ttu-id="73419-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-239">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-239">dl#</span></span>  <br/> <span data-ttu-id="73419-240">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-240">driver license</span></span>  <br/> <span data-ttu-id="73419-241">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-241">driver license number</span></span>  <br/> <span data-ttu-id="73419-242">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-242">driver licence</span></span>  <br/> <span data-ttu-id="73419-243">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-243">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-244">drivers license</span></span>  <br/> <span data-ttu-id="73419-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-245">drivers licence</span></span>  <br/> <span data-ttu-id="73419-246">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-246">driver's license number</span></span>  <br/> <span data-ttu-id="73419-247">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-247">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-248">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-248">driving license number</span></span>  <br/> <span data-ttu-id="73419-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-249">dlno#</span></span>  <br/> <span data-ttu-id="73419-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="73419-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="73419-251">Tschechien</span><span class="sxs-lookup"><span data-stu-id="73419-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="73419-252">Format</span><span class="sxs-lookup"><span data-stu-id="73419-252">Format</span></span>

<span data-ttu-id="73419-253">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-254">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-254">Pattern</span></span>

<span data-ttu-id="73419-255">Acht Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="73419-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="73419-256">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="73419-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="73419-257">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="73419-257">A space (optional)</span></span>
    
- <span data-ttu-id="73419-258">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-259">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-259">Checksum</span></span>

<span data-ttu-id="73419-260">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-261">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-261">Definition</span></span>

<span data-ttu-id="73419-262">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-263">Der reguläre Ausdruck `Regex_czech_republic_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-264">Ein Schlüsselwort `Keywords_czech_republic_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="73419-265">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-265">Keywords</span></span>

<span data-ttu-id="73419-266">| |</span><span class="sxs-lookup"><span data-stu-id="73419-266">| |</span></span>
|<span data-ttu-id="73419-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-268">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-268">dl#</span></span>  <br/> <span data-ttu-id="73419-269">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-269">driver license</span></span>  <br/> <span data-ttu-id="73419-270">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-270">driver license number</span></span>  <br/> <span data-ttu-id="73419-271">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-271">driver licence</span></span>  <br/> <span data-ttu-id="73419-272">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-272">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-273">drivers license</span></span>  <br/> <span data-ttu-id="73419-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-274">drivers licence</span></span>  <br/> <span data-ttu-id="73419-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-275">driver's license</span></span>  <br/> <span data-ttu-id="73419-276">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-276">driver's license number</span></span>  <br/> <span data-ttu-id="73419-277">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-277">driver's license number</span></span>  <br/> <span data-ttu-id="73419-278">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-278">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-279">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-279">driving license number</span></span>  <br/> <span data-ttu-id="73419-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-280">dlno#</span></span>  <br/> <span data-ttu-id="73419-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="73419-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="73419-282">Dänemark</span><span class="sxs-lookup"><span data-stu-id="73419-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="73419-283">Format</span><span class="sxs-lookup"><span data-stu-id="73419-283">Format</span></span>

<span data-ttu-id="73419-284">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-285">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-285">Pattern</span></span>

<span data-ttu-id="73419-286">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-287">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-287">Checksum</span></span>

<span data-ttu-id="73419-288">Ja</span><span class="sxs-lookup"><span data-stu-id="73419-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-289">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-289">Definition</span></span>

<span data-ttu-id="73419-290">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-291">Der reguläre Ausdruck `Regex_denmark_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-292">Ein Schlüsselwort `Keywords_denmark_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="73419-293">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-293">Keywords</span></span>

<span data-ttu-id="73419-294">| |</span><span class="sxs-lookup"><span data-stu-id="73419-294">| |</span></span>
|<span data-ttu-id="73419-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-296">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-296">dl#</span></span>  <br/> <span data-ttu-id="73419-297">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-297">driver license</span></span>  <br/> <span data-ttu-id="73419-298">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-298">driver license number</span></span>  <br/> <span data-ttu-id="73419-299">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-299">driver licence</span></span>  <br/> <span data-ttu-id="73419-300">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-300">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-301">drivers license</span></span>  <br/> <span data-ttu-id="73419-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-302">drivers licence</span></span>  <br/> <span data-ttu-id="73419-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-303">driver's license</span></span>  <br/> <span data-ttu-id="73419-304">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-304">driver's license number</span></span>  <br/> <span data-ttu-id="73419-305">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-305">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-306">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-306">driving license number</span></span>  <br/> <span data-ttu-id="73419-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-307">dlno#</span></span>  <br/> <span data-ttu-id="73419-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="73419-308">kørekort</span></span>  <br/> <span data-ttu-id="73419-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="73419-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="73419-310">Estland</span><span class="sxs-lookup"><span data-stu-id="73419-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="73419-311">Format</span><span class="sxs-lookup"><span data-stu-id="73419-311">Format</span></span>

<span data-ttu-id="73419-312">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-313">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-313">Pattern</span></span>

<span data-ttu-id="73419-314">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="73419-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="73419-315">Die Buchstaben "et" (unterscheidet nicht zwischen Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="73419-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="73419-316">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-317">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-317">Checksum</span></span>

<span data-ttu-id="73419-318">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-319">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-319">Definition</span></span>

<span data-ttu-id="73419-320">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-321">Der reguläre Ausdruck `Regex_estonia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-322">Ein Schlüsselwort `Keywords_estonia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-323">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-323">Keywords</span></span>

<span data-ttu-id="73419-324">| |</span><span class="sxs-lookup"><span data-stu-id="73419-324">| |</span></span>
|<span data-ttu-id="73419-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-326">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-326">dl#</span></span>  <br/> <span data-ttu-id="73419-327">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-327">driver license</span></span>  <br/> <span data-ttu-id="73419-328">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-328">driver license number</span></span>  <br/> <span data-ttu-id="73419-329">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-329">driver license number</span></span>  <br/> <span data-ttu-id="73419-330">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-330">driver licence</span></span>  <br/> <span data-ttu-id="73419-331">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-331">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-332">drivers license</span></span>  <br/> <span data-ttu-id="73419-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-333">drivers licence</span></span>  <br/> <span data-ttu-id="73419-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-334">driver's license</span></span>  <br/> <span data-ttu-id="73419-335">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-335">driver's license number</span></span>  <br/> <span data-ttu-id="73419-336">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-336">driving license number</span></span>  <br/> <span data-ttu-id="73419-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-337">dlno#</span></span>  <br/> <span data-ttu-id="73419-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="73419-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="73419-339">Finnland</span><span class="sxs-lookup"><span data-stu-id="73419-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="73419-340">Format</span><span class="sxs-lookup"><span data-stu-id="73419-340">Format</span></span>

<span data-ttu-id="73419-341">10 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="73419-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-342">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-342">Pattern</span></span>

<span data-ttu-id="73419-343">10 Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="73419-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="73419-344">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-344">Six digits</span></span> 
    
- <span data-ttu-id="73419-345">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="73419-345">A hyphen</span></span>
    
-  <span data-ttu-id="73419-346">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="73419-347">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-347">Checksum</span></span>

<span data-ttu-id="73419-348">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-349">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-349">Definition</span></span>

<span data-ttu-id="73419-350">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-351">Der reguläre Ausdruck `Regex_finland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-352">Ein Schlüsselwort `Keywords_finland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-353">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-353">Keywords</span></span>

<span data-ttu-id="73419-354">| |</span><span class="sxs-lookup"><span data-stu-id="73419-354">| |</span></span>
|<span data-ttu-id="73419-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-356">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-356">dl#</span></span>  <br/> <span data-ttu-id="73419-357">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-357">driver license</span></span>  <br/> <span data-ttu-id="73419-358">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-358">driver license number</span></span>  <br/> <span data-ttu-id="73419-359">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-359">driver licence</span></span>  <br/> <span data-ttu-id="73419-360">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-360">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-361">drivers license</span></span>  <br/> <span data-ttu-id="73419-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-362">drivers licence</span></span>  <br/> <span data-ttu-id="73419-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-363">driver's license</span></span>  <br/> <span data-ttu-id="73419-364">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-364">driver's license number</span></span>  <br/> <span data-ttu-id="73419-365">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-365">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-366">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-366">driving license number</span></span>  <br/> <span data-ttu-id="73419-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-367">dlno#</span></span>  <br/> <span data-ttu-id="73419-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="73419-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="73419-369">Frankreich</span><span class="sxs-lookup"><span data-stu-id="73419-369">France</span></span>

<span data-ttu-id="73419-370">Ausführliche Informationen finden Sie im Abschnitt "französische Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="73419-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="73419-371">Deutschland</span><span class="sxs-lookup"><span data-stu-id="73419-371">Germany</span></span>

<span data-ttu-id="73419-372">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="73419-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="73419-373">Griechenland</span><span class="sxs-lookup"><span data-stu-id="73419-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="73419-374">Format</span><span class="sxs-lookup"><span data-stu-id="73419-374">Format</span></span>

<span data-ttu-id="73419-375">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-376">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-376">Pattern</span></span>

 <span data-ttu-id="73419-377">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="73419-378">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-378">Checksum</span></span>

<span data-ttu-id="73419-379">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-380">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-380">Definition</span></span>

<span data-ttu-id="73419-381">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-382">Der reguläre Ausdruck `Regex_greece_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-383">Ein Schlüsselwort `Keywords_greece_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-384">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-384">Keywords</span></span>

<span data-ttu-id="73419-385">| |</span><span class="sxs-lookup"><span data-stu-id="73419-385">| |</span></span>
|<span data-ttu-id="73419-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="73419-387">dlL#</span></span>  <br/> <span data-ttu-id="73419-388">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-388">driver license</span></span>  <br/> <span data-ttu-id="73419-389">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-389">driver license number</span></span>  <br/> <span data-ttu-id="73419-390">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-390">driver licence</span></span>  <br/> <span data-ttu-id="73419-391">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-391">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-392">drivers license</span></span>  <br/> <span data-ttu-id="73419-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-393">drivers licence</span></span>  <br/> <span data-ttu-id="73419-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-394">driver's license</span></span>  <br/> <span data-ttu-id="73419-395">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-395">driver's license number</span></span>  <br/> <span data-ttu-id="73419-396">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-396">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-397">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-397">driving license number</span></span>  <br/> <span data-ttu-id="73419-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-398">dlno#</span></span>  <br/> <span data-ttu-id="73419-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="73419-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="73419-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="73419-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="73419-401">Ungarn</span><span class="sxs-lookup"><span data-stu-id="73419-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="73419-402">Format</span><span class="sxs-lookup"><span data-stu-id="73419-402">Format</span></span>

<span data-ttu-id="73419-403">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-404">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-404">Pattern</span></span>

<span data-ttu-id="73419-405">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="73419-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="73419-406">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="73419-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="73419-407">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-408">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-408">Checksum</span></span>

<span data-ttu-id="73419-409">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-410">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-410">Definition</span></span>

<span data-ttu-id="73419-411">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-412">Der reguläre Ausdruck `Regex_hungary_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-413">Ein Schlüsselwort `Keywords_hungary_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-414">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-414">Keywords</span></span>

<span data-ttu-id="73419-415">| |</span><span class="sxs-lookup"><span data-stu-id="73419-415">| |</span></span>
|<span data-ttu-id="73419-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-417">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-417">dl#</span></span>  <br/> <span data-ttu-id="73419-418">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-418">driver license</span></span>  <br/> <span data-ttu-id="73419-419">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-419">driver license number</span></span>  <br/> <span data-ttu-id="73419-420">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-420">driver licence</span></span>  <br/> <span data-ttu-id="73419-421">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-421">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-422">drivers license</span></span>  <br/> <span data-ttu-id="73419-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-423">drivers licence</span></span>  <br/> <span data-ttu-id="73419-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-424">driver's license</span></span>  <br/> <span data-ttu-id="73419-425">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-425">driver's license number</span></span>  <br/> <span data-ttu-id="73419-426">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-426">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-427">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-427">driving license number</span></span>  <br/> <span data-ttu-id="73419-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-428">dlno#</span></span>  <br/> <span data-ttu-id="73419-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="73419-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="73419-430">Irland</span><span class="sxs-lookup"><span data-stu-id="73419-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="73419-431">Format</span><span class="sxs-lookup"><span data-stu-id="73419-431">Format</span></span>

<span data-ttu-id="73419-432">Sechs Ziffern, gefolgt von vier Buchstaben</span><span class="sxs-lookup"><span data-stu-id="73419-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-433">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-433">Pattern</span></span>

<span data-ttu-id="73419-434">Sechs Ziffern und vier Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="73419-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="73419-435">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-435">Six digits</span></span>
    
- <span data-ttu-id="73419-436">Vier Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="73419-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-437">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-437">Checksum</span></span>

<span data-ttu-id="73419-438">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-439">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-439">Definition</span></span>

<span data-ttu-id="73419-440">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-441">Der reguläre Ausdruck `Regex_ireland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-442">Ein Schlüsselwort `Keywords_ireland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-443">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-443">Keywords</span></span>

<span data-ttu-id="73419-444">| |</span><span class="sxs-lookup"><span data-stu-id="73419-444">| |</span></span>
|<span data-ttu-id="73419-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-446">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-446">dl#</span></span>  <br/> <span data-ttu-id="73419-447">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-447">driver license</span></span>  <br/> <span data-ttu-id="73419-448">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-448">driver license number</span></span>  <br/> <span data-ttu-id="73419-449">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-449">driver licence</span></span>  <br/> <span data-ttu-id="73419-450">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-450">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-451">drivers license</span></span>  <br/> <span data-ttu-id="73419-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-452">drivers licence</span></span>  <br/> <span data-ttu-id="73419-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-453">driver's license</span></span>  <br/> <span data-ttu-id="73419-454">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-454">driver's license number</span></span>  <br/> <span data-ttu-id="73419-455">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-455">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-456">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-456">driving license number</span></span>  <br/> <span data-ttu-id="73419-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-457">dlno#</span></span>  <br/> <span data-ttu-id="73419-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="73419-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="73419-459">Italien</span><span class="sxs-lookup"><span data-stu-id="73419-459">Italy</span></span>

<span data-ttu-id="73419-460">Ausführliche Informationen finden Sie im Abschnitt "Italien-Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="73419-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="73419-461">Lettland</span><span class="sxs-lookup"><span data-stu-id="73419-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="73419-462">Format</span><span class="sxs-lookup"><span data-stu-id="73419-462">Format</span></span>

<span data-ttu-id="73419-463">Drei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-464">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-464">Pattern</span></span>

<span data-ttu-id="73419-465">Drei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="73419-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="73419-466">Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="73419-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="73419-467">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-468">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-468">Checksum</span></span>

<span data-ttu-id="73419-469">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-470">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-470">Definition</span></span>

<span data-ttu-id="73419-471">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-472">Der reguläre Ausdruck `Regex_latvia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-473">Ein Schlüsselwort `Keywords_latvia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-474">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-474">Keywords</span></span>

<span data-ttu-id="73419-475">| |</span><span class="sxs-lookup"><span data-stu-id="73419-475">| |</span></span>
|<span data-ttu-id="73419-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-477">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-477">dl#</span></span>  <br/> <span data-ttu-id="73419-478">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-478">driver license</span></span>  <br/> <span data-ttu-id="73419-479">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-479">driver license number</span></span>  <br/> <span data-ttu-id="73419-480">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-480">driver licence</span></span>  <br/> <span data-ttu-id="73419-481">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-481">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-482">drivers license</span></span>  <br/> <span data-ttu-id="73419-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-483">drivers licence</span></span>  <br/> <span data-ttu-id="73419-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-484">driver's license</span></span>  <br/> <span data-ttu-id="73419-485">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-485">driver's license number</span></span>  <br/> <span data-ttu-id="73419-486">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-486">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-487">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-487">driving license number</span></span>  <br/> <span data-ttu-id="73419-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-488">dlno#</span></span>  <br/> <span data-ttu-id="73419-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="73419-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="73419-490">Litauen</span><span class="sxs-lookup"><span data-stu-id="73419-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="73419-491">Format</span><span class="sxs-lookup"><span data-stu-id="73419-491">Format</span></span>

<span data-ttu-id="73419-492">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-493">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-493">Pattern</span></span>

 <span data-ttu-id="73419-494">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="73419-495">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-495">Checksum</span></span>

<span data-ttu-id="73419-496">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-497">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-497">Definition</span></span>

<span data-ttu-id="73419-498">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-499">Der reguläre Ausdruck `Regex_lithuania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-500">Ein Schlüsselwort `Keywords_lithuania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-501">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-501">Keywords</span></span>

<span data-ttu-id="73419-502">| |</span><span class="sxs-lookup"><span data-stu-id="73419-502">| |</span></span>
|<span data-ttu-id="73419-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-504">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-504">dl#</span></span>  <br/> <span data-ttu-id="73419-505">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-505">driver license</span></span>  <br/> <span data-ttu-id="73419-506">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-506">driver license number</span></span>  <br/> <span data-ttu-id="73419-507">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-507">driver licence</span></span>  <br/> <span data-ttu-id="73419-508">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-508">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-509">drivers license</span></span>  <br/> <span data-ttu-id="73419-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-510">drivers licence</span></span>  <br/> <span data-ttu-id="73419-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-511">driver's license</span></span>  <br/> <span data-ttu-id="73419-512">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-512">driver's license number</span></span>  <br/> <span data-ttu-id="73419-513">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-513">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-514">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-514">driving license number</span></span>  <br/> <span data-ttu-id="73419-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-515">dlno#</span></span>  <br/> <span data-ttu-id="73419-516">Vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="73419-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="73419-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="73419-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="73419-518">Format</span><span class="sxs-lookup"><span data-stu-id="73419-518">Format</span></span>

<span data-ttu-id="73419-519">Sechs Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-520">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-520">Pattern</span></span>

 <span data-ttu-id="73419-521">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="73419-522">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-522">Checksum</span></span>

<span data-ttu-id="73419-523">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-524">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-524">Definition</span></span>

<span data-ttu-id="73419-525">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-526">Der reguläre Ausdruck `Regex_luxemburg_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-527">Ein Schlüsselwort `Keywords_luxemburg_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-528">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-528">Keywords</span></span>

<span data-ttu-id="73419-529">| |</span><span class="sxs-lookup"><span data-stu-id="73419-529">| |</span></span>
|<span data-ttu-id="73419-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-531">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-531">dl#</span></span>  <br/> <span data-ttu-id="73419-532">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-532">driver license</span></span>  <br/> <span data-ttu-id="73419-533">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-533">driver license number</span></span>  <br/> <span data-ttu-id="73419-534">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-534">driver licence</span></span>  <br/> <span data-ttu-id="73419-535">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-535">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-536">drivers license</span></span>  <br/> <span data-ttu-id="73419-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-537">drivers licence</span></span>  <br/> <span data-ttu-id="73419-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-538">driver's license</span></span>  <br/> <span data-ttu-id="73419-539">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-539">driver's license number</span></span>  <br/> <span data-ttu-id="73419-540">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-540">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-541">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-541">driving license number</span></span>  <br/> <span data-ttu-id="73419-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-542">dlno#</span></span>  <br/> <span data-ttu-id="73419-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="73419-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="73419-544">Malta</span><span class="sxs-lookup"><span data-stu-id="73419-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="73419-545">Format</span><span class="sxs-lookup"><span data-stu-id="73419-545">Format</span></span>

<span data-ttu-id="73419-546">Kombination aus zwei Zeichen und sechs Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="73419-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-547">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-547">Pattern</span></span>

<span data-ttu-id="73419-548">Kombination aus zwei Zeichen und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="73419-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="73419-549">Zwei Zeichen (Ziffern oder Buchstaben, bei denen die Groß-/Kleinschreibung nicht beachtet wird)</span><span class="sxs-lookup"><span data-stu-id="73419-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="73419-550">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="73419-550">A space (optional)</span></span>
    
- <span data-ttu-id="73419-551">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-551">Three digits</span></span>
    
- <span data-ttu-id="73419-552">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="73419-552">A space (optional)</span></span>
    
- <span data-ttu-id="73419-553">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-554">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-554">Checksum</span></span>

<span data-ttu-id="73419-555">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-556">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-556">Definition</span></span>

<span data-ttu-id="73419-557">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-558">Der reguläre Ausdruck `Regex_malta_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-559">Ein Schlüsselwort `Keywords_malta_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-560">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-560">Keywords</span></span>

<span data-ttu-id="73419-561">| |</span><span class="sxs-lookup"><span data-stu-id="73419-561">| |</span></span>
|<span data-ttu-id="73419-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-563">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-563">dl#</span></span>  <br/> <span data-ttu-id="73419-564">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-564">driver license</span></span>  <br/> <span data-ttu-id="73419-565">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-565">driver license number</span></span>  <br/> <span data-ttu-id="73419-566">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-566">driver licence</span></span>  <br/> <span data-ttu-id="73419-567">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-567">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-568">drivers license</span></span>  <br/> <span data-ttu-id="73419-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-569">drivers licence</span></span>  <br/> <span data-ttu-id="73419-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-570">driver's license</span></span>  <br/> <span data-ttu-id="73419-571">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-571">driver's license number</span></span>  <br/> <span data-ttu-id="73419-572">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-572">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-573">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-573">driving license number</span></span>  <br/> <span data-ttu-id="73419-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-574">dlno#</span></span>  <br/> <span data-ttu-id="73419-575">Liċenzja TAS-Sewqan</span><span class="sxs-lookup"><span data-stu-id="73419-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="73419-576">Niederlande</span><span class="sxs-lookup"><span data-stu-id="73419-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="73419-577">Format</span><span class="sxs-lookup"><span data-stu-id="73419-577">Format</span></span>

<span data-ttu-id="73419-578">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-579">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-579">Pattern</span></span>

<span data-ttu-id="73419-580">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-581">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-581">Checksum</span></span>

<span data-ttu-id="73419-582">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-583">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-583">Definition</span></span>

<span data-ttu-id="73419-584">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-585">Der reguläre Ausdruck `Regex_netherlands_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-586">Ein Schlüsselwort `Keywords_netherlands_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-587">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-587">Keywords</span></span>

<span data-ttu-id="73419-588">| |</span><span class="sxs-lookup"><span data-stu-id="73419-588">| |</span></span>
|<span data-ttu-id="73419-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-590">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-590">dl#</span></span>  <br/> <span data-ttu-id="73419-591">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-591">driver license</span></span>  <br/> <span data-ttu-id="73419-592">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-592">driver license number</span></span>  <br/> <span data-ttu-id="73419-593">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-593">driver licence</span></span>  <br/> <span data-ttu-id="73419-594">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-594">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-595">drivers license</span></span>  <br/> <span data-ttu-id="73419-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-596">drivers licence</span></span>  <br/> <span data-ttu-id="73419-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-597">driver's license</span></span>  <br/> <span data-ttu-id="73419-598">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-598">driver's license number</span></span>  <br/> <span data-ttu-id="73419-599">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-599">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-600">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-600">driving license number</span></span>  <br/> <span data-ttu-id="73419-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-601">dlno#</span></span>  <br/> <span data-ttu-id="73419-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="73419-602">permis de conduire</span></span>  <br/> <span data-ttu-id="73419-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="73419-603">rijbewijs</span></span>  <br/> <span data-ttu-id="73419-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="73419-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="73419-605">Polen</span><span class="sxs-lookup"><span data-stu-id="73419-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="73419-606">Format</span><span class="sxs-lookup"><span data-stu-id="73419-606">Format</span></span>

<span data-ttu-id="73419-607">14 Ziffern mit 2 Schrägstrichen</span><span class="sxs-lookup"><span data-stu-id="73419-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-608">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-608">Pattern</span></span>

<span data-ttu-id="73419-609">14 Ziffern und 2 Schrägstriche:</span><span class="sxs-lookup"><span data-stu-id="73419-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="73419-610">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-610">Five digits</span></span> 
    
- <span data-ttu-id="73419-611">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="73419-611">A forward slash</span></span>
    
- <span data-ttu-id="73419-612">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-612">Two digits</span></span>
    
- <span data-ttu-id="73419-613">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="73419-613">A forward slash</span></span>
    
- <span data-ttu-id="73419-614">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-615">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-615">Checksum</span></span>

<span data-ttu-id="73419-616">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-617">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-617">Definition</span></span>

<span data-ttu-id="73419-618">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-619">Der reguläre Ausdruck `Regex_poland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-620">Ein Schlüsselwort `Keywords_poland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-621">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-621">Keywords</span></span>

<span data-ttu-id="73419-622">| |</span><span class="sxs-lookup"><span data-stu-id="73419-622">| |</span></span>
|<span data-ttu-id="73419-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-624">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-624">dl#</span></span>  <br/> <span data-ttu-id="73419-625">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-625">driver license</span></span>  <br/> <span data-ttu-id="73419-626">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-626">driver license number</span></span>  <br/> <span data-ttu-id="73419-627">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-627">driver licence</span></span>  <br/> <span data-ttu-id="73419-628">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-628">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-629">drivers license</span></span>  <br/> <span data-ttu-id="73419-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-630">drivers licence</span></span>  <br/> <span data-ttu-id="73419-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-631">driver's license</span></span>  <br/> <span data-ttu-id="73419-632">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-632">driver's license number</span></span>  <br/> <span data-ttu-id="73419-633">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-633">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-634">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-634">driving license number</span></span>  <br/> <span data-ttu-id="73419-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-635">dlno#</span></span>  <br/> <span data-ttu-id="73419-636">Prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="73419-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="73419-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="73419-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="73419-638">Format</span><span class="sxs-lookup"><span data-stu-id="73419-638">Format</span></span>

<span data-ttu-id="73419-639">Zwei Buchstaben, gefolgt von sieben Zahlen im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="73419-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-640">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-640">Pattern</span></span>

<span data-ttu-id="73419-641">Zwei Buchstaben, gefolgt von sieben Zahlen mit Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="73419-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="73419-642">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="73419-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="73419-643">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="73419-643">A hyphen</span></span>
    
- <span data-ttu-id="73419-644">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-644">Six digits</span></span>
    
- <span data-ttu-id="73419-645">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-645">A space</span></span>
    
- <span data-ttu-id="73419-646">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="73419-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-647">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-647">Checksum</span></span>

<span data-ttu-id="73419-648">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-649">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-649">Definition</span></span>

<span data-ttu-id="73419-650">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-651">Der reguläre Ausdruck `Regex_portugal_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-652">Ein Schlüsselwort `Keywords_portugal_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-653">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-653">Keywords</span></span>

<span data-ttu-id="73419-654">| |</span><span class="sxs-lookup"><span data-stu-id="73419-654">| |</span></span>
|<span data-ttu-id="73419-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-656">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-656">dl#</span></span>  <br/> <span data-ttu-id="73419-657">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-657">driver license</span></span>  <br/> <span data-ttu-id="73419-658">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-658">driver license number</span></span>  <br/> <span data-ttu-id="73419-659">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-659">driver licence</span></span>  <br/> <span data-ttu-id="73419-660">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-660">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-661">drivers license</span></span>  <br/> <span data-ttu-id="73419-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-662">drivers licence</span></span>  <br/> <span data-ttu-id="73419-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-663">driver's license</span></span>  <br/> <span data-ttu-id="73419-664">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-664">driver's license number</span></span>  <br/> <span data-ttu-id="73419-665">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-665">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-666">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-666">driving license number</span></span>  <br/> <span data-ttu-id="73419-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-667">dlno#</span></span>  <br/> <span data-ttu-id="73419-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="73419-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="73419-669">Rumänien</span><span class="sxs-lookup"><span data-stu-id="73419-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="73419-670">Format</span><span class="sxs-lookup"><span data-stu-id="73419-670">Format</span></span>

<span data-ttu-id="73419-671">Ein Zeichen gefolgt von acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-672">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-672">Pattern</span></span>

<span data-ttu-id="73419-673">Ein Zeichen gefolgt von acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="73419-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="73419-674">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="73419-675">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-676">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-676">Checksum</span></span>

<span data-ttu-id="73419-677">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-678">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-678">Definition</span></span>

<span data-ttu-id="73419-679">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-680">Der reguläre Ausdruck `Regex_romania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-681">Ein Schlüsselwort `Keywords_romania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-682">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-682">Keywords</span></span>

<span data-ttu-id="73419-683">| |</span><span class="sxs-lookup"><span data-stu-id="73419-683">| |</span></span>
|<span data-ttu-id="73419-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-685">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-685">dl#</span></span>  <br/> <span data-ttu-id="73419-686">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-686">driver license</span></span>  <br/> <span data-ttu-id="73419-687">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-687">driver license number</span></span>  <br/> <span data-ttu-id="73419-688">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-688">driver licence</span></span>  <br/> <span data-ttu-id="73419-689">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-689">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-690">drivers license</span></span>  <br/> <span data-ttu-id="73419-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-691">drivers licence</span></span>  <br/> <span data-ttu-id="73419-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-692">driver's license</span></span>  <br/> <span data-ttu-id="73419-693">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-693">driver's license number</span></span>  <br/> <span data-ttu-id="73419-694">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-694">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-695">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-695">driving license number</span></span>  <br/> <span data-ttu-id="73419-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-696">dlno#</span></span>  <br/> <span data-ttu-id="73419-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="73419-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="73419-698">Slowakei</span><span class="sxs-lookup"><span data-stu-id="73419-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="73419-699">Format</span><span class="sxs-lookup"><span data-stu-id="73419-699">Format</span></span>

<span data-ttu-id="73419-700">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-701">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-701">Pattern</span></span>

<span data-ttu-id="73419-702">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="73419-703">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="73419-704">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="73419-705">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-705">Checksum</span></span>

<span data-ttu-id="73419-706">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-707">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-707">Definition</span></span>

<span data-ttu-id="73419-708">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-709">Der reguläre Ausdruck `Regex_slovakia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-710">Ein Schlüsselwort `Keywords_slovakia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-711">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-711">Keywords</span></span>

<span data-ttu-id="73419-712">| |</span><span class="sxs-lookup"><span data-stu-id="73419-712">| |</span></span>
|<span data-ttu-id="73419-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-714">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-714">dl#</span></span>  <br/> <span data-ttu-id="73419-715">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-715">driver license</span></span>  <br/> <span data-ttu-id="73419-716">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-716">driver license number</span></span>  <br/> <span data-ttu-id="73419-717">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-717">driver licence</span></span>  <br/> <span data-ttu-id="73419-718">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-718">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-719">drivers license</span></span>  <br/> <span data-ttu-id="73419-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-720">drivers licence</span></span>  <br/> <span data-ttu-id="73419-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-721">driver's license</span></span>  <br/> <span data-ttu-id="73419-722">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-722">driver's license number</span></span>  <br/> <span data-ttu-id="73419-723">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-723">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-724">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-724">driving license number</span></span>  <br/> <span data-ttu-id="73419-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-725">dlno#</span></span>  <br/> <span data-ttu-id="73419-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="73419-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="73419-727">Slowenien</span><span class="sxs-lookup"><span data-stu-id="73419-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="73419-728">Format</span><span class="sxs-lookup"><span data-stu-id="73419-728">Format</span></span>

<span data-ttu-id="73419-729">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="73419-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-730">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-730">Pattern</span></span>

<span data-ttu-id="73419-731">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="73419-732">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-732">Checksum</span></span>

<span data-ttu-id="73419-733">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-734">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-734">Definition</span></span>

<span data-ttu-id="73419-735">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-736">Der reguläre Ausdruck `Regex_slovenia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-737">Ein Schlüsselwort `Keywords_slovenia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-738">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-738">Keywords</span></span>

<span data-ttu-id="73419-739">| |</span><span class="sxs-lookup"><span data-stu-id="73419-739">| |</span></span>
|<span data-ttu-id="73419-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-741">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-741">dl#</span></span>  <br/> <span data-ttu-id="73419-742">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-742">driver license</span></span>  <br/> <span data-ttu-id="73419-743">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-743">driver license number</span></span>  <br/> <span data-ttu-id="73419-744">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-744">driver licence</span></span>  <br/> <span data-ttu-id="73419-745">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-745">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-746">drivers license</span></span>  <br/> <span data-ttu-id="73419-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-747">drivers licence</span></span>  <br/> <span data-ttu-id="73419-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-748">driver's license</span></span>  <br/> <span data-ttu-id="73419-749">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-749">driver's license number</span></span>  <br/> <span data-ttu-id="73419-750">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-750">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-751">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-751">driving license number</span></span>  <br/> <span data-ttu-id="73419-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-752">dlno#</span></span>  <br/> <span data-ttu-id="73419-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="73419-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="73419-754">Spanien</span><span class="sxs-lookup"><span data-stu-id="73419-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="73419-755">Format</span><span class="sxs-lookup"><span data-stu-id="73419-755">Format</span></span>

<span data-ttu-id="73419-756">Acht Ziffern, gefolgt von einem Zeichen</span><span class="sxs-lookup"><span data-stu-id="73419-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-757">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-757">Pattern</span></span>

<span data-ttu-id="73419-758">Acht Ziffern, gefolgt von einem Zeichen:</span><span class="sxs-lookup"><span data-stu-id="73419-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="73419-759">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-759">Eight digits</span></span> 
    
- <span data-ttu-id="73419-760">Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="73419-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-761">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-761">Checksum</span></span>

<span data-ttu-id="73419-762">Ja</span><span class="sxs-lookup"><span data-stu-id="73419-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-763">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-763">Definition</span></span>

<span data-ttu-id="73419-764">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-765">Die- `Func_spain_eu_driver's_license_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-766">Ein Schlüsselwort `Keywords_spain_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="73419-767">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-767">Keywords</span></span>

<span data-ttu-id="73419-768">| |</span><span class="sxs-lookup"><span data-stu-id="73419-768">| |</span></span>
|<span data-ttu-id="73419-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-770">dlno#</span></span>  <br/> <span data-ttu-id="73419-771">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-771">dl#</span></span>  <br/> <span data-ttu-id="73419-772">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-772">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-773">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-773">driver licence</span></span>  <br/> <span data-ttu-id="73419-774">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-774">driver license</span></span>  <br/> <span data-ttu-id="73419-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-775">drivers licence</span></span>  <br/> <span data-ttu-id="73419-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-776">drivers license</span></span>  <br/> <span data-ttu-id="73419-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="73419-777">driver's licence</span></span>  <br/> <span data-ttu-id="73419-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-778">driver's license</span></span>  <br/> <span data-ttu-id="73419-779">Führerschein</span><span class="sxs-lookup"><span data-stu-id="73419-779">driving licence</span></span>  <br/> <span data-ttu-id="73419-780">driving license</span><span class="sxs-lookup"><span data-stu-id="73419-780">driving license</span></span>  <br/> <span data-ttu-id="73419-781">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-781">driver licence number</span></span>  <br/> <span data-ttu-id="73419-782">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-782">driver license number</span></span>  <br/> <span data-ttu-id="73419-783">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-783">drivers licence number</span></span>  <br/> <span data-ttu-id="73419-784">Lizenznummer für Treiber</span><span class="sxs-lookup"><span data-stu-id="73419-784">drivers license number</span></span>  <br/> <span data-ttu-id="73419-785">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-785">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-786">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-786">driver's license number</span></span>  <br/> <span data-ttu-id="73419-787">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-787">driving licence number</span></span>  <br/> <span data-ttu-id="73419-788">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-788">driving license number</span></span>  <br/> <span data-ttu-id="73419-789">Führerschein</span><span class="sxs-lookup"><span data-stu-id="73419-789">driving permit</span></span>  <br/> <span data-ttu-id="73419-790">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-790">driving permit number</span></span>  <br/> <span data-ttu-id="73419-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="73419-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="73419-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="73419-792">permiso conducción</span></span>  <br/> <span data-ttu-id="73419-793">número licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="73419-794">número de carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="73419-795">número Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="73419-796">licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-796">licencia conducir</span></span>  <br/> <span data-ttu-id="73419-797">número de Permiso de Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="73419-798">número de Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="73419-799">número Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="73419-800">Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-800">permiso conducir</span></span>  <br/> <span data-ttu-id="73419-801">licencia de Manejo</span><span class="sxs-lookup"><span data-stu-id="73419-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="73419-802">El Carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="73419-803">Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="73419-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="73419-804">Schweden</span><span class="sxs-lookup"><span data-stu-id="73419-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="73419-805">Format</span><span class="sxs-lookup"><span data-stu-id="73419-805">Format</span></span>

<span data-ttu-id="73419-806">Zehn Ziffern mit einem Bindestrich</span><span class="sxs-lookup"><span data-stu-id="73419-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="73419-807">Muster</span><span class="sxs-lookup"><span data-stu-id="73419-807">Pattern</span></span>

<span data-ttu-id="73419-808">Zehn Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="73419-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="73419-809">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-809">Six digits</span></span> 
    
- <span data-ttu-id="73419-810">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="73419-810">A hyphen</span></span>
    
- <span data-ttu-id="73419-811">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="73419-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="73419-812">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="73419-812">Checksum</span></span>

<span data-ttu-id="73419-813">Nein</span><span class="sxs-lookup"><span data-stu-id="73419-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="73419-814">Definition</span><span class="sxs-lookup"><span data-stu-id="73419-814">Definition</span></span>

<span data-ttu-id="73419-815">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="73419-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="73419-816">Der reguläre Ausdruck `Regex_sweden_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="73419-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="73419-817">Ein Schlüsselwort `Keywords_sweden_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="73419-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="73419-818">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="73419-818">Keywords</span></span>

<span data-ttu-id="73419-819">| |</span><span class="sxs-lookup"><span data-stu-id="73419-819">| |</span></span>
|<span data-ttu-id="73419-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="73419-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="73419-821">DL #</span><span class="sxs-lookup"><span data-stu-id="73419-821">dl#</span></span>  <br/> <span data-ttu-id="73419-822">driver license</span><span class="sxs-lookup"><span data-stu-id="73419-822">driver license</span></span>  <br/> <span data-ttu-id="73419-823">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="73419-823">driver license number</span></span>  <br/> <span data-ttu-id="73419-824">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="73419-824">driver licence</span></span>  <br/> <span data-ttu-id="73419-825">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="73419-825">drivers lic.</span></span>  <br/> <span data-ttu-id="73419-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="73419-826">drivers license</span></span>  <br/> <span data-ttu-id="73419-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="73419-827">drivers licence</span></span>  <br/> <span data-ttu-id="73419-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="73419-828">driver's license</span></span>  <br/> <span data-ttu-id="73419-829">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-829">driver's license number</span></span>  <br/> <span data-ttu-id="73419-830">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-830">driver's licence number</span></span>  <br/> <span data-ttu-id="73419-831">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="73419-831">driving license number</span></span>  <br/> <span data-ttu-id="73419-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="73419-832">dlno#</span></span>  <br/> <span data-ttu-id="73419-833">körkort</span><span class="sxs-lookup"><span data-stu-id="73419-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="73419-834">UK</span><span class="sxs-lookup"><span data-stu-id="73419-834">UK</span></span>

<span data-ttu-id="73419-835">Ausführliche Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="73419-835">For details, see the section "U.K.</span></span> <span data-ttu-id="73419-836">Nummer des Führerscheins "in [dem, wonach die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="73419-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="73419-837">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73419-837">See also</span></span>

[<span data-ttu-id="73419-838">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="73419-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

