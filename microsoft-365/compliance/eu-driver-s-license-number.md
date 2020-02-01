---
title: EU-Führerscheinnummer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592656"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="8977d-104">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-104">EU Driver's License Number</span></span>

<span data-ttu-id="8977d-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8977d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="8977d-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="8977d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8977d-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="8977d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8977d-108">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-108">Format</span></span>

<span data-ttu-id="8977d-109">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-110">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-110">Pattern</span></span>

<span data-ttu-id="8977d-111">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-112">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-112">Checksum</span></span>

<span data-ttu-id="8977d-113">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-114">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-114">Definition</span></span>

<span data-ttu-id="8977d-115">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-116">Der reguläre Ausdruck `Regex_austria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-117">Ein Schlüsselwort `Keywords_austria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="8977d-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-118">Keywords</span></span>

<span data-ttu-id="8977d-119">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-119">| |</span></span>
|<span data-ttu-id="8977d-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-121">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-121">dl#</span></span>  <br/> <span data-ttu-id="8977d-122">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-122">driver license</span></span>  <br/> <span data-ttu-id="8977d-123">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-123">driver license number</span></span>  <br/> <span data-ttu-id="8977d-124">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-124">driver licence</span></span>  <br/> <span data-ttu-id="8977d-125">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-125">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-126">drivers license</span></span>  <br/> <span data-ttu-id="8977d-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8977d-127">driver's licence</span></span>  <br/> <span data-ttu-id="8977d-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-128">driver's license</span></span>  <br/> <span data-ttu-id="8977d-129">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-129">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-130">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="8977d-131">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-131">driving license number</span></span>  <br/> <span data-ttu-id="8977d-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-132">dlno#</span></span>  <br/> <span data-ttu-id="8977d-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="8977d-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="8977d-134">Fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="8977d-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8977d-135">Belgien</span><span class="sxs-lookup"><span data-stu-id="8977d-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8977d-136">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-136">Format</span></span>

<span data-ttu-id="8977d-137">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-138">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-138">Pattern</span></span>

<span data-ttu-id="8977d-139">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-140">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-140">Checksum</span></span>

<span data-ttu-id="8977d-141">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-142">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-142">Definition</span></span>

<span data-ttu-id="8977d-143">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-144">Der reguläre Ausdruck `Regex_belgium_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-145">Ein Schlüsselwort `Keywords_belgium_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8977d-146">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-146">Keywords</span></span>

<span data-ttu-id="8977d-147">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-147">| |</span></span>
|<span data-ttu-id="8977d-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-149">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-149">dl#</span></span>  <br/> <span data-ttu-id="8977d-150">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-150">driver license</span></span>  <br/> <span data-ttu-id="8977d-151">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-151">driver license number</span></span>  <br/> <span data-ttu-id="8977d-152">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-152">driver licence</span></span>  <br/> <span data-ttu-id="8977d-153">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-153">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-154">drivers license</span></span>  <br/> <span data-ttu-id="8977d-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-155">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-156">driver's license</span></span>  <br/> <span data-ttu-id="8977d-157">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-157">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-158">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-158">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-159">dlno#</span></span>  <br/> <span data-ttu-id="8977d-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="8977d-160">rijbewijs</span></span>  <br/> <span data-ttu-id="8977d-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="8977d-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="8977d-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="8977d-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="8977d-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="8977d-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="8977d-166">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="8977d-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="8977d-167">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="8977d-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8977d-168">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="8977d-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8977d-169">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-169">Format</span></span>

<span data-ttu-id="8977d-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-171">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-171">Pattern</span></span>

<span data-ttu-id="8977d-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-173">Checksum</span></span>

<span data-ttu-id="8977d-174">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-175">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-175">Definition</span></span>

<span data-ttu-id="8977d-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-177">Der reguläre Ausdruck `Regex_bulgaria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-178">Ein Schlüsselwort `Keywords_bulgaria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="8977d-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-179">Keywords</span></span>

<span data-ttu-id="8977d-180">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-180">| |</span></span>
|<span data-ttu-id="8977d-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-182">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-182">dl#</span></span>  <br/> <span data-ttu-id="8977d-183">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-183">driver license</span></span>  <br/> <span data-ttu-id="8977d-184">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-184">driver license number</span></span>  <br/> <span data-ttu-id="8977d-185">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-185">driver licence</span></span>  <br/> <span data-ttu-id="8977d-186">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-186">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-187">drivers license</span></span>  <br/> <span data-ttu-id="8977d-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-188">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-189">driver's license</span></span>  <br/> <span data-ttu-id="8977d-190">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-190">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-191">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-191">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-192">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-192">driving license number</span></span>  <br/> <span data-ttu-id="8977d-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-193">dlno#</span></span>  <br/> <span data-ttu-id="8977d-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="8977d-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="8977d-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="8977d-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="8977d-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="8977d-196">сумпс</span></span>  <br/> <span data-ttu-id="8977d-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="8977d-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8977d-198">Kroatien</span><span class="sxs-lookup"><span data-stu-id="8977d-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8977d-199">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-199">Format</span></span>

<span data-ttu-id="8977d-200">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-201">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-201">Pattern</span></span>

<span data-ttu-id="8977d-202">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-203">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-203">Checksum</span></span>

<span data-ttu-id="8977d-204">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-205">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-205">Definition</span></span>

<span data-ttu-id="8977d-206">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-207">Der reguläre Ausdruck `Regex_croatia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-208">Ein Schlüsselwort `Keywords_croatia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8977d-209">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-209">Keywords</span></span>

<span data-ttu-id="8977d-210">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-210">| |</span></span>
|<span data-ttu-id="8977d-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-212">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-212">dl#</span></span>  <br/> <span data-ttu-id="8977d-213">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-213">driver license</span></span>  <br/> <span data-ttu-id="8977d-214">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-214">driver license number</span></span>  <br/> <span data-ttu-id="8977d-215">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-215">driver licence</span></span>  <br/> <span data-ttu-id="8977d-216">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-216">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-217">drivers license</span></span>  <br/> <span data-ttu-id="8977d-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-218">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-219">driver's license</span></span>  <br/> <span data-ttu-id="8977d-220">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-220">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-221">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-221">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-222">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-222">driving license number</span></span>  <br/> <span data-ttu-id="8977d-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-223">dlno#</span></span>  <br/> <span data-ttu-id="8977d-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="8977d-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8977d-225">Zypern</span><span class="sxs-lookup"><span data-stu-id="8977d-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8977d-226">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-226">Format</span></span>

<span data-ttu-id="8977d-227">12 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-228">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-228">Pattern</span></span>

<span data-ttu-id="8977d-229">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-230">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-230">Checksum</span></span>

<span data-ttu-id="8977d-231">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-232">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-232">Definition</span></span>

<span data-ttu-id="8977d-233">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-234">Der reguläre Ausdruck `Regex_cyprus_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-235">Ein Schlüsselwort `Keywords_cyprus_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-236">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-236">Keywords</span></span>

<span data-ttu-id="8977d-237">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-237">| |</span></span>
|<span data-ttu-id="8977d-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-239">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-239">dl#</span></span>  <br/> <span data-ttu-id="8977d-240">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-240">driver license</span></span>  <br/> <span data-ttu-id="8977d-241">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-241">driver license number</span></span>  <br/> <span data-ttu-id="8977d-242">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-242">driver licence</span></span>  <br/> <span data-ttu-id="8977d-243">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-243">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-244">drivers license</span></span>  <br/> <span data-ttu-id="8977d-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-245">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-246">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-246">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-247">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-247">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-248">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-248">driving license number</span></span>  <br/> <span data-ttu-id="8977d-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-249">dlno#</span></span>  <br/> <span data-ttu-id="8977d-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="8977d-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8977d-251">Tschechien</span><span class="sxs-lookup"><span data-stu-id="8977d-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8977d-252">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-252">Format</span></span>

<span data-ttu-id="8977d-253">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-254">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-254">Pattern</span></span>

<span data-ttu-id="8977d-255">Acht Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="8977d-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="8977d-256">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="8977d-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="8977d-257">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="8977d-257">A space (optional)</span></span>
    
- <span data-ttu-id="8977d-258">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-259">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-259">Checksum</span></span>

<span data-ttu-id="8977d-260">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-261">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-261">Definition</span></span>

<span data-ttu-id="8977d-262">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-263">Der reguläre Ausdruck `Regex_czech_republic_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-264">Ein Schlüsselwort `Keywords_czech_republic_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8977d-265">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-265">Keywords</span></span>

<span data-ttu-id="8977d-266">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-266">| |</span></span>
|<span data-ttu-id="8977d-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-268">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-268">dl#</span></span>  <br/> <span data-ttu-id="8977d-269">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-269">driver license</span></span>  <br/> <span data-ttu-id="8977d-270">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-270">driver license number</span></span>  <br/> <span data-ttu-id="8977d-271">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-271">driver licence</span></span>  <br/> <span data-ttu-id="8977d-272">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-272">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-273">drivers license</span></span>  <br/> <span data-ttu-id="8977d-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-274">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-275">driver's license</span></span>  <br/> <span data-ttu-id="8977d-276">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-276">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-277">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-277">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-278">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-278">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-279">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-279">driving license number</span></span>  <br/> <span data-ttu-id="8977d-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-280">dlno#</span></span>  <br/> <span data-ttu-id="8977d-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="8977d-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8977d-282">Dänemark</span><span class="sxs-lookup"><span data-stu-id="8977d-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8977d-283">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-283">Format</span></span>

<span data-ttu-id="8977d-284">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-285">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-285">Pattern</span></span>

<span data-ttu-id="8977d-286">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-287">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-287">Checksum</span></span>

<span data-ttu-id="8977d-288">Ja</span><span class="sxs-lookup"><span data-stu-id="8977d-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-289">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-289">Definition</span></span>

<span data-ttu-id="8977d-290">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-291">Der reguläre Ausdruck `Regex_denmark_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-292">Ein Schlüsselwort `Keywords_denmark_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="8977d-293">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-293">Keywords</span></span>

<span data-ttu-id="8977d-294">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-294">| |</span></span>
|<span data-ttu-id="8977d-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-296">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-296">dl#</span></span>  <br/> <span data-ttu-id="8977d-297">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-297">driver license</span></span>  <br/> <span data-ttu-id="8977d-298">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-298">driver license number</span></span>  <br/> <span data-ttu-id="8977d-299">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-299">driver licence</span></span>  <br/> <span data-ttu-id="8977d-300">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-300">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-301">drivers license</span></span>  <br/> <span data-ttu-id="8977d-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-302">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-303">driver's license</span></span>  <br/> <span data-ttu-id="8977d-304">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-304">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-305">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-305">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-306">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-306">driving license number</span></span>  <br/> <span data-ttu-id="8977d-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-307">dlno#</span></span>  <br/> <span data-ttu-id="8977d-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="8977d-308">kørekort</span></span>  <br/> <span data-ttu-id="8977d-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8977d-310">Estland</span><span class="sxs-lookup"><span data-stu-id="8977d-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8977d-311">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-311">Format</span></span>

<span data-ttu-id="8977d-312">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-313">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-313">Pattern</span></span>

<span data-ttu-id="8977d-314">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="8977d-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="8977d-315">Die Buchstaben "et" (unterscheidet nicht zwischen Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="8977d-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8977d-316">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-317">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-317">Checksum</span></span>

<span data-ttu-id="8977d-318">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-319">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-319">Definition</span></span>

<span data-ttu-id="8977d-320">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-321">Der reguläre Ausdruck `Regex_estonia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-322">Ein Schlüsselwort `Keywords_estonia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-323">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-323">Keywords</span></span>

<span data-ttu-id="8977d-324">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-324">| |</span></span>
|<span data-ttu-id="8977d-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-326">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-326">dl#</span></span>  <br/> <span data-ttu-id="8977d-327">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-327">driver license</span></span>  <br/> <span data-ttu-id="8977d-328">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-328">driver license number</span></span>  <br/> <span data-ttu-id="8977d-329">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-329">driver license number</span></span>  <br/> <span data-ttu-id="8977d-330">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-330">driver licence</span></span>  <br/> <span data-ttu-id="8977d-331">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-331">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-332">drivers license</span></span>  <br/> <span data-ttu-id="8977d-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-333">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-334">driver's license</span></span>  <br/> <span data-ttu-id="8977d-335">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-335">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-336">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-336">driving license number</span></span>  <br/> <span data-ttu-id="8977d-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-337">dlno#</span></span>  <br/> <span data-ttu-id="8977d-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8977d-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8977d-339">Finnland</span><span class="sxs-lookup"><span data-stu-id="8977d-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="8977d-340">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-340">Format</span></span>

<span data-ttu-id="8977d-341">10 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="8977d-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-342">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-342">Pattern</span></span>

<span data-ttu-id="8977d-343">10 Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="8977d-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="8977d-344">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-344">Six digits</span></span> 
    
- <span data-ttu-id="8977d-345">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="8977d-345">A hyphen</span></span>
    
-  <span data-ttu-id="8977d-346">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8977d-347">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-347">Checksum</span></span>

<span data-ttu-id="8977d-348">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-349">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-349">Definition</span></span>

<span data-ttu-id="8977d-350">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-351">Der reguläre Ausdruck `Regex_finland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-352">Ein Schlüsselwort `Keywords_finland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-353">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-353">Keywords</span></span>

<span data-ttu-id="8977d-354">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-354">| |</span></span>
|<span data-ttu-id="8977d-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-356">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-356">dl#</span></span>  <br/> <span data-ttu-id="8977d-357">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-357">driver license</span></span>  <br/> <span data-ttu-id="8977d-358">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-358">driver license number</span></span>  <br/> <span data-ttu-id="8977d-359">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-359">driver licence</span></span>  <br/> <span data-ttu-id="8977d-360">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-360">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-361">drivers license</span></span>  <br/> <span data-ttu-id="8977d-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-362">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-363">driver's license</span></span>  <br/> <span data-ttu-id="8977d-364">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-364">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-365">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-365">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-366">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-366">driving license number</span></span>  <br/> <span data-ttu-id="8977d-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-367">dlno#</span></span>  <br/> <span data-ttu-id="8977d-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="8977d-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="8977d-369">Frankreich</span><span class="sxs-lookup"><span data-stu-id="8977d-369">France</span></span>

<span data-ttu-id="8977d-370">Ausführliche Informationen finden Sie im Abschnitt "französische Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8977d-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8977d-371">Deutschland</span><span class="sxs-lookup"><span data-stu-id="8977d-371">Germany</span></span>

<span data-ttu-id="8977d-372">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8977d-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8977d-373">Griechenland</span><span class="sxs-lookup"><span data-stu-id="8977d-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8977d-374">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-374">Format</span></span>

<span data-ttu-id="8977d-375">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-376">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-376">Pattern</span></span>

 <span data-ttu-id="8977d-377">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8977d-378">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-378">Checksum</span></span>

<span data-ttu-id="8977d-379">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-380">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-380">Definition</span></span>

<span data-ttu-id="8977d-381">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-382">Der reguläre Ausdruck `Regex_greece_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-383">Ein Schlüsselwort `Keywords_greece_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-384">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-384">Keywords</span></span>

<span data-ttu-id="8977d-385">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-385">| |</span></span>
|<span data-ttu-id="8977d-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="8977d-387">dlL#</span></span>  <br/> <span data-ttu-id="8977d-388">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-388">driver license</span></span>  <br/> <span data-ttu-id="8977d-389">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-389">driver license number</span></span>  <br/> <span data-ttu-id="8977d-390">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-390">driver licence</span></span>  <br/> <span data-ttu-id="8977d-391">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-391">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-392">drivers license</span></span>  <br/> <span data-ttu-id="8977d-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-393">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-394">driver's license</span></span>  <br/> <span data-ttu-id="8977d-395">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-395">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-396">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-396">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-397">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-397">driving license number</span></span>  <br/> <span data-ttu-id="8977d-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-398">dlno#</span></span>  <br/> <span data-ttu-id="8977d-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="8977d-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="8977d-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="8977d-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8977d-401">Ungarn</span><span class="sxs-lookup"><span data-stu-id="8977d-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8977d-402">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-402">Format</span></span>

<span data-ttu-id="8977d-403">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-404">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-404">Pattern</span></span>

<span data-ttu-id="8977d-405">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="8977d-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="8977d-406">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="8977d-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8977d-407">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-408">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-408">Checksum</span></span>

<span data-ttu-id="8977d-409">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-410">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-410">Definition</span></span>

<span data-ttu-id="8977d-411">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-412">Der reguläre Ausdruck `Regex_hungary_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-413">Ein Schlüsselwort `Keywords_hungary_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-414">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-414">Keywords</span></span>

<span data-ttu-id="8977d-415">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-415">| |</span></span>
|<span data-ttu-id="8977d-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-417">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-417">dl#</span></span>  <br/> <span data-ttu-id="8977d-418">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-418">driver license</span></span>  <br/> <span data-ttu-id="8977d-419">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-419">driver license number</span></span>  <br/> <span data-ttu-id="8977d-420">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-420">driver licence</span></span>  <br/> <span data-ttu-id="8977d-421">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-421">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-422">drivers license</span></span>  <br/> <span data-ttu-id="8977d-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-423">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-424">driver's license</span></span>  <br/> <span data-ttu-id="8977d-425">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-425">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-426">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-426">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-427">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-427">driving license number</span></span>  <br/> <span data-ttu-id="8977d-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-428">dlno#</span></span>  <br/> <span data-ttu-id="8977d-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="8977d-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8977d-430">Irland</span><span class="sxs-lookup"><span data-stu-id="8977d-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8977d-431">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-431">Format</span></span>

<span data-ttu-id="8977d-432">Sechs Ziffern, gefolgt von vier Buchstaben</span><span class="sxs-lookup"><span data-stu-id="8977d-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-433">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-433">Pattern</span></span>

<span data-ttu-id="8977d-434">Sechs Ziffern und vier Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="8977d-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="8977d-435">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-435">Six digits</span></span>
    
- <span data-ttu-id="8977d-436">Vier Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="8977d-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-437">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-437">Checksum</span></span>

<span data-ttu-id="8977d-438">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-439">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-439">Definition</span></span>

<span data-ttu-id="8977d-440">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-441">Der reguläre Ausdruck `Regex_ireland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-442">Ein Schlüsselwort `Keywords_ireland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-443">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-443">Keywords</span></span>

<span data-ttu-id="8977d-444">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-444">| |</span></span>
|<span data-ttu-id="8977d-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-446">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-446">dl#</span></span>  <br/> <span data-ttu-id="8977d-447">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-447">driver license</span></span>  <br/> <span data-ttu-id="8977d-448">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-448">driver license number</span></span>  <br/> <span data-ttu-id="8977d-449">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-449">driver licence</span></span>  <br/> <span data-ttu-id="8977d-450">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-450">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-451">drivers license</span></span>  <br/> <span data-ttu-id="8977d-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-452">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-453">driver's license</span></span>  <br/> <span data-ttu-id="8977d-454">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-454">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-455">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-455">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-456">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-456">driving license number</span></span>  <br/> <span data-ttu-id="8977d-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-457">dlno#</span></span>  <br/> <span data-ttu-id="8977d-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="8977d-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8977d-459">Italien</span><span class="sxs-lookup"><span data-stu-id="8977d-459">Italy</span></span>

<span data-ttu-id="8977d-460">Ausführliche Informationen finden Sie im Abschnitt "Italien-Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8977d-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="8977d-461">Lettland</span><span class="sxs-lookup"><span data-stu-id="8977d-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8977d-462">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-462">Format</span></span>

<span data-ttu-id="8977d-463">Drei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-464">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-464">Pattern</span></span>

<span data-ttu-id="8977d-465">Drei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="8977d-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="8977d-466">Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="8977d-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8977d-467">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-468">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-468">Checksum</span></span>

<span data-ttu-id="8977d-469">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-470">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-470">Definition</span></span>

<span data-ttu-id="8977d-471">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-472">Der reguläre Ausdruck `Regex_latvia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-473">Ein Schlüsselwort `Keywords_latvia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-474">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-474">Keywords</span></span>

<span data-ttu-id="8977d-475">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-475">| |</span></span>
|<span data-ttu-id="8977d-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-477">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-477">dl#</span></span>  <br/> <span data-ttu-id="8977d-478">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-478">driver license</span></span>  <br/> <span data-ttu-id="8977d-479">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-479">driver license number</span></span>  <br/> <span data-ttu-id="8977d-480">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-480">driver licence</span></span>  <br/> <span data-ttu-id="8977d-481">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-481">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-482">drivers license</span></span>  <br/> <span data-ttu-id="8977d-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-483">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-484">driver's license</span></span>  <br/> <span data-ttu-id="8977d-485">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-485">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-486">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-486">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-487">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-487">driving license number</span></span>  <br/> <span data-ttu-id="8977d-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-488">dlno#</span></span>  <br/> <span data-ttu-id="8977d-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="8977d-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8977d-490">Litauen</span><span class="sxs-lookup"><span data-stu-id="8977d-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8977d-491">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-491">Format</span></span>

<span data-ttu-id="8977d-492">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-493">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-493">Pattern</span></span>

 <span data-ttu-id="8977d-494">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8977d-495">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-495">Checksum</span></span>

<span data-ttu-id="8977d-496">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-497">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-497">Definition</span></span>

<span data-ttu-id="8977d-498">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-499">Der reguläre Ausdruck `Regex_lithuania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-500">Ein Schlüsselwort `Keywords_lithuania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-501">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-501">Keywords</span></span>

<span data-ttu-id="8977d-502">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-502">| |</span></span>
|<span data-ttu-id="8977d-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-504">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-504">dl#</span></span>  <br/> <span data-ttu-id="8977d-505">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-505">driver license</span></span>  <br/> <span data-ttu-id="8977d-506">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-506">driver license number</span></span>  <br/> <span data-ttu-id="8977d-507">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-507">driver licence</span></span>  <br/> <span data-ttu-id="8977d-508">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-508">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-509">drivers license</span></span>  <br/> <span data-ttu-id="8977d-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-510">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-511">driver's license</span></span>  <br/> <span data-ttu-id="8977d-512">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-512">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-513">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-513">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-514">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-514">driving license number</span></span>  <br/> <span data-ttu-id="8977d-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-515">dlno#</span></span>  <br/> <span data-ttu-id="8977d-516">Vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="8977d-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8977d-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="8977d-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8977d-518">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-518">Format</span></span>

<span data-ttu-id="8977d-519">Sechs Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-520">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-520">Pattern</span></span>

 <span data-ttu-id="8977d-521">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8977d-522">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-522">Checksum</span></span>

<span data-ttu-id="8977d-523">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-524">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-524">Definition</span></span>

<span data-ttu-id="8977d-525">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-526">Der reguläre Ausdruck `Regex_luxemburg_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-527">Ein Schlüsselwort `Keywords_luxemburg_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-528">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-528">Keywords</span></span>

<span data-ttu-id="8977d-529">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-529">| |</span></span>
|<span data-ttu-id="8977d-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-531">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-531">dl#</span></span>  <br/> <span data-ttu-id="8977d-532">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-532">driver license</span></span>  <br/> <span data-ttu-id="8977d-533">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-533">driver license number</span></span>  <br/> <span data-ttu-id="8977d-534">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-534">driver licence</span></span>  <br/> <span data-ttu-id="8977d-535">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-535">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-536">drivers license</span></span>  <br/> <span data-ttu-id="8977d-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-537">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-538">driver's license</span></span>  <br/> <span data-ttu-id="8977d-539">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-539">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-540">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-540">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-541">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-541">driving license number</span></span>  <br/> <span data-ttu-id="8977d-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-542">dlno#</span></span>  <br/> <span data-ttu-id="8977d-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="8977d-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8977d-544">Malta</span><span class="sxs-lookup"><span data-stu-id="8977d-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8977d-545">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-545">Format</span></span>

<span data-ttu-id="8977d-546">Kombination aus zwei Zeichen und sechs Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-547">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-547">Pattern</span></span>

<span data-ttu-id="8977d-548">Kombination aus zwei Zeichen und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="8977d-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="8977d-549">Zwei Zeichen (Ziffern oder Buchstaben, bei denen die Groß-/Kleinschreibung nicht beachtet wird)</span><span class="sxs-lookup"><span data-stu-id="8977d-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="8977d-550">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="8977d-550">A space (optional)</span></span>
    
- <span data-ttu-id="8977d-551">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-551">Three digits</span></span>
    
- <span data-ttu-id="8977d-552">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="8977d-552">A space (optional)</span></span>
    
- <span data-ttu-id="8977d-553">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-554">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-554">Checksum</span></span>

<span data-ttu-id="8977d-555">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-556">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-556">Definition</span></span>

<span data-ttu-id="8977d-557">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-558">Der reguläre Ausdruck `Regex_malta_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-559">Ein Schlüsselwort `Keywords_malta_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-560">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-560">Keywords</span></span>

<span data-ttu-id="8977d-561">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-561">| |</span></span>
|<span data-ttu-id="8977d-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-563">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-563">dl#</span></span>  <br/> <span data-ttu-id="8977d-564">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-564">driver license</span></span>  <br/> <span data-ttu-id="8977d-565">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-565">driver license number</span></span>  <br/> <span data-ttu-id="8977d-566">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-566">driver licence</span></span>  <br/> <span data-ttu-id="8977d-567">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-567">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-568">drivers license</span></span>  <br/> <span data-ttu-id="8977d-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-569">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-570">driver's license</span></span>  <br/> <span data-ttu-id="8977d-571">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-571">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-572">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-572">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-573">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-573">driving license number</span></span>  <br/> <span data-ttu-id="8977d-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-574">dlno#</span></span>  <br/> <span data-ttu-id="8977d-575">Liċenzja TAS-Sewqan</span><span class="sxs-lookup"><span data-stu-id="8977d-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8977d-576">Niederlande</span><span class="sxs-lookup"><span data-stu-id="8977d-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8977d-577">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-577">Format</span></span>

<span data-ttu-id="8977d-578">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-579">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-579">Pattern</span></span>

<span data-ttu-id="8977d-580">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-581">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-581">Checksum</span></span>

<span data-ttu-id="8977d-582">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-583">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-583">Definition</span></span>

<span data-ttu-id="8977d-584">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-585">Der reguläre Ausdruck `Regex_netherlands_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-586">Ein Schlüsselwort `Keywords_netherlands_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-587">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-587">Keywords</span></span>

<span data-ttu-id="8977d-588">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-588">| |</span></span>
|<span data-ttu-id="8977d-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-590">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-590">dl#</span></span>  <br/> <span data-ttu-id="8977d-591">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-591">driver license</span></span>  <br/> <span data-ttu-id="8977d-592">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-592">driver license number</span></span>  <br/> <span data-ttu-id="8977d-593">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-593">driver licence</span></span>  <br/> <span data-ttu-id="8977d-594">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-594">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-595">drivers license</span></span>  <br/> <span data-ttu-id="8977d-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-596">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-597">driver's license</span></span>  <br/> <span data-ttu-id="8977d-598">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-598">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-599">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-599">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-600">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-600">driving license number</span></span>  <br/> <span data-ttu-id="8977d-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-601">dlno#</span></span>  <br/> <span data-ttu-id="8977d-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="8977d-602">permis de conduire</span></span>  <br/> <span data-ttu-id="8977d-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="8977d-603">rijbewijs</span></span>  <br/> <span data-ttu-id="8977d-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8977d-605">Polen</span><span class="sxs-lookup"><span data-stu-id="8977d-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="8977d-606">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-606">Format</span></span>

<span data-ttu-id="8977d-607">14 Ziffern mit 2 Schrägstrichen</span><span class="sxs-lookup"><span data-stu-id="8977d-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-608">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-608">Pattern</span></span>

<span data-ttu-id="8977d-609">14 Ziffern und 2 Schrägstriche:</span><span class="sxs-lookup"><span data-stu-id="8977d-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="8977d-610">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-610">Five digits</span></span> 
    
- <span data-ttu-id="8977d-611">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="8977d-611">A forward slash</span></span>
    
- <span data-ttu-id="8977d-612">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-612">Two digits</span></span>
    
- <span data-ttu-id="8977d-613">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="8977d-613">A forward slash</span></span>
    
- <span data-ttu-id="8977d-614">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-615">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-615">Checksum</span></span>

<span data-ttu-id="8977d-616">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-617">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-617">Definition</span></span>

<span data-ttu-id="8977d-618">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-619">Der reguläre Ausdruck `Regex_poland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-620">Ein Schlüsselwort `Keywords_poland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-621">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-621">Keywords</span></span>

<span data-ttu-id="8977d-622">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-622">| |</span></span>
|<span data-ttu-id="8977d-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-624">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-624">dl#</span></span>  <br/> <span data-ttu-id="8977d-625">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-625">driver license</span></span>  <br/> <span data-ttu-id="8977d-626">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-626">driver license number</span></span>  <br/> <span data-ttu-id="8977d-627">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-627">driver licence</span></span>  <br/> <span data-ttu-id="8977d-628">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-628">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-629">drivers license</span></span>  <br/> <span data-ttu-id="8977d-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-630">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-631">driver's license</span></span>  <br/> <span data-ttu-id="8977d-632">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-632">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-633">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-633">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-634">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-634">driving license number</span></span>  <br/> <span data-ttu-id="8977d-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-635">dlno#</span></span>  <br/> <span data-ttu-id="8977d-636">Prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="8977d-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="8977d-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="8977d-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8977d-638">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-638">Format</span></span>

<span data-ttu-id="8977d-639">Zwei Buchstaben, gefolgt von sieben Zahlen im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-640">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-640">Pattern</span></span>

<span data-ttu-id="8977d-641">Zwei Buchstaben, gefolgt von sieben Zahlen mit Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="8977d-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="8977d-642">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="8977d-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="8977d-643">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="8977d-643">A hyphen</span></span>
    
- <span data-ttu-id="8977d-644">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-644">Six digits</span></span>
    
- <span data-ttu-id="8977d-645">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-645">A space</span></span>
    
- <span data-ttu-id="8977d-646">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="8977d-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-647">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-647">Checksum</span></span>

<span data-ttu-id="8977d-648">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-649">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-649">Definition</span></span>

<span data-ttu-id="8977d-650">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-651">Der reguläre Ausdruck `Regex_portugal_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-652">Ein Schlüsselwort `Keywords_portugal_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-653">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-653">Keywords</span></span>

<span data-ttu-id="8977d-654">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-654">| |</span></span>
|<span data-ttu-id="8977d-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-656">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-656">dl#</span></span>  <br/> <span data-ttu-id="8977d-657">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-657">driver license</span></span>  <br/> <span data-ttu-id="8977d-658">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-658">driver license number</span></span>  <br/> <span data-ttu-id="8977d-659">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-659">driver licence</span></span>  <br/> <span data-ttu-id="8977d-660">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-660">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-661">drivers license</span></span>  <br/> <span data-ttu-id="8977d-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-662">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-663">driver's license</span></span>  <br/> <span data-ttu-id="8977d-664">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-664">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-665">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-665">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-666">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-666">driving license number</span></span>  <br/> <span data-ttu-id="8977d-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-667">dlno#</span></span>  <br/> <span data-ttu-id="8977d-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="8977d-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8977d-669">Rumänien</span><span class="sxs-lookup"><span data-stu-id="8977d-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8977d-670">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-670">Format</span></span>

<span data-ttu-id="8977d-671">Ein Zeichen gefolgt von acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-672">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-672">Pattern</span></span>

<span data-ttu-id="8977d-673">Ein Zeichen gefolgt von acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="8977d-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="8977d-674">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="8977d-675">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-676">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-676">Checksum</span></span>

<span data-ttu-id="8977d-677">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-678">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-678">Definition</span></span>

<span data-ttu-id="8977d-679">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-680">Der reguläre Ausdruck `Regex_romania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-681">Ein Schlüsselwort `Keywords_romania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-682">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-682">Keywords</span></span>

<span data-ttu-id="8977d-683">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-683">| |</span></span>
|<span data-ttu-id="8977d-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-685">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-685">dl#</span></span>  <br/> <span data-ttu-id="8977d-686">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-686">driver license</span></span>  <br/> <span data-ttu-id="8977d-687">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-687">driver license number</span></span>  <br/> <span data-ttu-id="8977d-688">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-688">driver licence</span></span>  <br/> <span data-ttu-id="8977d-689">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-689">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-690">drivers license</span></span>  <br/> <span data-ttu-id="8977d-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-691">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-692">driver's license</span></span>  <br/> <span data-ttu-id="8977d-693">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-693">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-694">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-694">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-695">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-695">driving license number</span></span>  <br/> <span data-ttu-id="8977d-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-696">dlno#</span></span>  <br/> <span data-ttu-id="8977d-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="8977d-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8977d-698">Slowakei</span><span class="sxs-lookup"><span data-stu-id="8977d-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8977d-699">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-699">Format</span></span>

<span data-ttu-id="8977d-700">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-701">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-701">Pattern</span></span>

<span data-ttu-id="8977d-702">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="8977d-703">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="8977d-704">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="8977d-705">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-705">Checksum</span></span>

<span data-ttu-id="8977d-706">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-707">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-707">Definition</span></span>

<span data-ttu-id="8977d-708">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-709">Der reguläre Ausdruck `Regex_slovakia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-710">Ein Schlüsselwort `Keywords_slovakia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-711">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-711">Keywords</span></span>

<span data-ttu-id="8977d-712">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-712">| |</span></span>
|<span data-ttu-id="8977d-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-714">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-714">dl#</span></span>  <br/> <span data-ttu-id="8977d-715">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-715">driver license</span></span>  <br/> <span data-ttu-id="8977d-716">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-716">driver license number</span></span>  <br/> <span data-ttu-id="8977d-717">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-717">driver licence</span></span>  <br/> <span data-ttu-id="8977d-718">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-718">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-719">drivers license</span></span>  <br/> <span data-ttu-id="8977d-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-720">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-721">driver's license</span></span>  <br/> <span data-ttu-id="8977d-722">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-722">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-723">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-723">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-724">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-724">driving license number</span></span>  <br/> <span data-ttu-id="8977d-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-725">dlno#</span></span>  <br/> <span data-ttu-id="8977d-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="8977d-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8977d-727">Slowenien</span><span class="sxs-lookup"><span data-stu-id="8977d-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8977d-728">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-728">Format</span></span>

<span data-ttu-id="8977d-729">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-730">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-730">Pattern</span></span>

<span data-ttu-id="8977d-731">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8977d-732">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-732">Checksum</span></span>

<span data-ttu-id="8977d-733">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-734">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-734">Definition</span></span>

<span data-ttu-id="8977d-735">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-736">Der reguläre Ausdruck `Regex_slovenia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-737">Ein Schlüsselwort `Keywords_slovenia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-738">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-738">Keywords</span></span>

<span data-ttu-id="8977d-739">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-739">| |</span></span>
|<span data-ttu-id="8977d-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-741">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-741">dl#</span></span>  <br/> <span data-ttu-id="8977d-742">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-742">driver license</span></span>  <br/> <span data-ttu-id="8977d-743">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-743">driver license number</span></span>  <br/> <span data-ttu-id="8977d-744">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-744">driver licence</span></span>  <br/> <span data-ttu-id="8977d-745">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-745">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-746">drivers license</span></span>  <br/> <span data-ttu-id="8977d-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-747">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-748">driver's license</span></span>  <br/> <span data-ttu-id="8977d-749">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-749">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-750">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-750">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-751">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-751">driving license number</span></span>  <br/> <span data-ttu-id="8977d-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-752">dlno#</span></span>  <br/> <span data-ttu-id="8977d-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="8977d-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8977d-754">Spanien</span><span class="sxs-lookup"><span data-stu-id="8977d-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8977d-755">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-755">Format</span></span>

<span data-ttu-id="8977d-756">Acht Ziffern, gefolgt von einem Zeichen</span><span class="sxs-lookup"><span data-stu-id="8977d-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-757">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-757">Pattern</span></span>

<span data-ttu-id="8977d-758">Acht Ziffern, gefolgt von einem Zeichen:</span><span class="sxs-lookup"><span data-stu-id="8977d-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="8977d-759">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-759">Eight digits</span></span> 
    
- <span data-ttu-id="8977d-760">Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="8977d-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-761">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-761">Checksum</span></span>

<span data-ttu-id="8977d-762">Ja</span><span class="sxs-lookup"><span data-stu-id="8977d-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-763">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-763">Definition</span></span>

<span data-ttu-id="8977d-764">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-765">Die- `Func_spain_eu_driver's_license_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-766">Ein Schlüsselwort `Keywords_spain_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8977d-767">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-767">Keywords</span></span>

<span data-ttu-id="8977d-768">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-768">| |</span></span>
|<span data-ttu-id="8977d-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-770">dlno#</span></span>  <br/> <span data-ttu-id="8977d-771">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-771">dl#</span></span>  <br/> <span data-ttu-id="8977d-772">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-772">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-773">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-773">driver licence</span></span>  <br/> <span data-ttu-id="8977d-774">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-774">driver license</span></span>  <br/> <span data-ttu-id="8977d-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-775">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-776">drivers license</span></span>  <br/> <span data-ttu-id="8977d-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="8977d-777">driver's licence</span></span>  <br/> <span data-ttu-id="8977d-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-778">driver's license</span></span>  <br/> <span data-ttu-id="8977d-779">Führerschein</span><span class="sxs-lookup"><span data-stu-id="8977d-779">driving licence</span></span>  <br/> <span data-ttu-id="8977d-780">driving license</span><span class="sxs-lookup"><span data-stu-id="8977d-780">driving license</span></span>  <br/> <span data-ttu-id="8977d-781">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-781">driver licence number</span></span>  <br/> <span data-ttu-id="8977d-782">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-782">driver license number</span></span>  <br/> <span data-ttu-id="8977d-783">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-783">drivers licence number</span></span>  <br/> <span data-ttu-id="8977d-784">Lizenznummer für Treiber</span><span class="sxs-lookup"><span data-stu-id="8977d-784">drivers license number</span></span>  <br/> <span data-ttu-id="8977d-785">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-785">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-786">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-786">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-787">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-787">driving licence number</span></span>  <br/> <span data-ttu-id="8977d-788">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-788">driving license number</span></span>  <br/> <span data-ttu-id="8977d-789">Führerschein</span><span class="sxs-lookup"><span data-stu-id="8977d-789">driving permit</span></span>  <br/> <span data-ttu-id="8977d-790">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-790">driving permit number</span></span>  <br/> <span data-ttu-id="8977d-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="8977d-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="8977d-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="8977d-792">permiso conducción</span></span>  <br/> <span data-ttu-id="8977d-793">número licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="8977d-794">número de carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="8977d-795">número Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="8977d-796">licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-796">licencia conducir</span></span>  <br/> <span data-ttu-id="8977d-797">número de Permiso de Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="8977d-798">número de Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="8977d-799">número Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="8977d-800">Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-800">permiso conducir</span></span>  <br/> <span data-ttu-id="8977d-801">licencia de Manejo</span><span class="sxs-lookup"><span data-stu-id="8977d-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="8977d-802">El Carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="8977d-803">Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="8977d-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8977d-804">Schweden</span><span class="sxs-lookup"><span data-stu-id="8977d-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="8977d-805">Format</span><span class="sxs-lookup"><span data-stu-id="8977d-805">Format</span></span>

<span data-ttu-id="8977d-806">Zehn Ziffern mit einem Bindestrich</span><span class="sxs-lookup"><span data-stu-id="8977d-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8977d-807">Muster</span><span class="sxs-lookup"><span data-stu-id="8977d-807">Pattern</span></span>

<span data-ttu-id="8977d-808">Zehn Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="8977d-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="8977d-809">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-809">Six digits</span></span> 
    
- <span data-ttu-id="8977d-810">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="8977d-810">A hyphen</span></span>
    
- <span data-ttu-id="8977d-811">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="8977d-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8977d-812">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="8977d-812">Checksum</span></span>

<span data-ttu-id="8977d-813">Nein</span><span class="sxs-lookup"><span data-stu-id="8977d-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8977d-814">Definition</span><span class="sxs-lookup"><span data-stu-id="8977d-814">Definition</span></span>

<span data-ttu-id="8977d-815">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="8977d-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8977d-816">Der reguläre Ausdruck `Regex_sweden_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="8977d-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8977d-817">Ein Schlüsselwort `Keywords_sweden_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="8977d-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="8977d-818">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="8977d-818">Keywords</span></span>

<span data-ttu-id="8977d-819">| |</span><span class="sxs-lookup"><span data-stu-id="8977d-819">| |</span></span>
|<span data-ttu-id="8977d-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="8977d-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="8977d-821">DL #</span><span class="sxs-lookup"><span data-stu-id="8977d-821">dl#</span></span>  <br/> <span data-ttu-id="8977d-822">driver license</span><span class="sxs-lookup"><span data-stu-id="8977d-822">driver license</span></span>  <br/> <span data-ttu-id="8977d-823">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="8977d-823">driver license number</span></span>  <br/> <span data-ttu-id="8977d-824">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="8977d-824">driver licence</span></span>  <br/> <span data-ttu-id="8977d-825">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="8977d-825">drivers lic.</span></span>  <br/> <span data-ttu-id="8977d-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="8977d-826">drivers license</span></span>  <br/> <span data-ttu-id="8977d-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="8977d-827">drivers licence</span></span>  <br/> <span data-ttu-id="8977d-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="8977d-828">driver's license</span></span>  <br/> <span data-ttu-id="8977d-829">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-829">driver's license number</span></span>  <br/> <span data-ttu-id="8977d-830">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-830">driver's licence number</span></span>  <br/> <span data-ttu-id="8977d-831">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="8977d-831">driving license number</span></span>  <br/> <span data-ttu-id="8977d-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="8977d-832">dlno#</span></span>  <br/> <span data-ttu-id="8977d-833">körkort</span><span class="sxs-lookup"><span data-stu-id="8977d-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="8977d-834">UK</span><span class="sxs-lookup"><span data-stu-id="8977d-834">UK</span></span>

<span data-ttu-id="8977d-835">Ausführliche Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="8977d-835">For details, see the section "U.K.</span></span> <span data-ttu-id="8977d-836">Nummer des Führerscheins "in [dem, wonach die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="8977d-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8977d-837">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8977d-837">See also</span></span>

[<span data-ttu-id="8977d-838">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="8977d-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

