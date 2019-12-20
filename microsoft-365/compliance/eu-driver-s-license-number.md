---
title: EU-Führerscheinnummer
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
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805958"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="29ec0-104">EU-Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-104">EU Driver's License Number</span></span>

<span data-ttu-id="29ec0-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp des EU-Führerscheins für die Lizenznummer erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="29ec0-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="29ec0-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="29ec0-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="29ec0-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="29ec0-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-108">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-108">Format</span></span>

<span data-ttu-id="29ec0-109">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-110">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-110">Pattern</span></span>

<span data-ttu-id="29ec0-111">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-112">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-112">Checksum</span></span>

<span data-ttu-id="29ec0-113">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-114">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-114">Definition</span></span>

<span data-ttu-id="29ec0-115">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-116">Der reguläre Ausdruck `Regex_austria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-117">Ein Schlüsselwort `Keywords_austria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="29ec0-118">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-118">Keywords</span></span>

<span data-ttu-id="29ec0-119">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-119"></span></span>
|<span data-ttu-id="29ec0-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-121">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-121">dl#</span></span>  <br/> <span data-ttu-id="29ec0-122">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-122">driver license</span></span>  <br/> <span data-ttu-id="29ec0-123">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-123">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-124">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-124">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-125">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-125">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-126">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-127">driver's licence</span></span>  <br/> <span data-ttu-id="29ec0-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-128">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-129">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-129">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-130">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="29ec0-131">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-131">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-132">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="29ec0-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="29ec0-134">Fuhrerschein Republik Osterreich</span><span class="sxs-lookup"><span data-stu-id="29ec0-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="29ec0-135">Belgien</span><span class="sxs-lookup"><span data-stu-id="29ec0-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-136">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-136">Format</span></span>

<span data-ttu-id="29ec0-137">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-138">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-138">Pattern</span></span>

<span data-ttu-id="29ec0-139">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-140">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-140">Checksum</span></span>

<span data-ttu-id="29ec0-141">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-142">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-142">Definition</span></span>

<span data-ttu-id="29ec0-143">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-144">Der reguläre Ausdruck `Regex_belgium_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-145">Ein Schlüsselwort `Keywords_belgium_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="29ec0-146">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-146">Keywords</span></span>

<span data-ttu-id="29ec0-147">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-147"></span></span>
|<span data-ttu-id="29ec0-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-149">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-149">dl#</span></span>  <br/> <span data-ttu-id="29ec0-150">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-150">driver license</span></span>  <br/> <span data-ttu-id="29ec0-151">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-151">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-152">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-152">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-153">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-153">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-154">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-155">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-156">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-157">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-157">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-158">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-158">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-159">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="29ec0-160">rijbewijs</span></span>  <br/> <span data-ttu-id="29ec0-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="29ec0-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="29ec0-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="29ec0-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="29ec0-165">Führerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="29ec0-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="29ec0-166">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="29ec0-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="29ec0-167">Fuehrerschein-Nr</span><span class="sxs-lookup"><span data-stu-id="29ec0-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="29ec0-168">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="29ec0-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-169">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-169">Format</span></span>

<span data-ttu-id="29ec0-170">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-171">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-171">Pattern</span></span>

<span data-ttu-id="29ec0-172">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-173">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-173">Checksum</span></span>

<span data-ttu-id="29ec0-174">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-175">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-175">Definition</span></span>

<span data-ttu-id="29ec0-176">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-177">Der reguläre Ausdruck `Regex_bulgaria_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-178">Ein Schlüsselwort `Keywords_bulgaria_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="29ec0-179">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-179">Keywords</span></span>

<span data-ttu-id="29ec0-180">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-180"></span></span>
|<span data-ttu-id="29ec0-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-182">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-182">dl#</span></span>  <br/> <span data-ttu-id="29ec0-183">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-183">driver license</span></span>  <br/> <span data-ttu-id="29ec0-184">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-184">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-185">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-185">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-186">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-186">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-187">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-188">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-189">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-190">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-190">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-191">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-191">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-192">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-192">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-193">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="29ec0-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="29ec0-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="29ec0-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="29ec0-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="29ec0-196">сумпс</span></span>  <br/> <span data-ttu-id="29ec0-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="29ec0-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="29ec0-198">Kroatien</span><span class="sxs-lookup"><span data-stu-id="29ec0-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-199">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-199">Format</span></span>

<span data-ttu-id="29ec0-200">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-201">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-201">Pattern</span></span>

<span data-ttu-id="29ec0-202">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-203">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-203">Checksum</span></span>

<span data-ttu-id="29ec0-204">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-205">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-205">Definition</span></span>

<span data-ttu-id="29ec0-206">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-207">Der reguläre Ausdruck `Regex_croatia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-208">Ein Schlüsselwort `Keywords_croatia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="29ec0-209">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-209">Keywords</span></span>

<span data-ttu-id="29ec0-210">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-210"></span></span>
|<span data-ttu-id="29ec0-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-212">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-212">dl#</span></span>  <br/> <span data-ttu-id="29ec0-213">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-213">driver license</span></span>  <br/> <span data-ttu-id="29ec0-214">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-214">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-215">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-215">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-216">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-216">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-217">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-218">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-219">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-220">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-220">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-221">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-221">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-222">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-222">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-223">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="29ec0-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="29ec0-225">Zypern</span><span class="sxs-lookup"><span data-stu-id="29ec0-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-226">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-226">Format</span></span>

<span data-ttu-id="29ec0-227">12 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-228">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-228">Pattern</span></span>

<span data-ttu-id="29ec0-229">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-230">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-230">Checksum</span></span>

<span data-ttu-id="29ec0-231">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-232">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-232">Definition</span></span>

<span data-ttu-id="29ec0-233">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-234">Der reguläre Ausdruck `Regex_cyprus_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-235">Ein Schlüsselwort `Keywords_cyprus_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-236">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-236">Keywords</span></span>

<span data-ttu-id="29ec0-237">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-237"></span></span>
|<span data-ttu-id="29ec0-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-239">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-239">dl#</span></span>  <br/> <span data-ttu-id="29ec0-240">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-240">driver license</span></span>  <br/> <span data-ttu-id="29ec0-241">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-241">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-242">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-242">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-243">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-243">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-244">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-245">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-246">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-246">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-247">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-247">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-248">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-248">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-249">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="29ec0-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="29ec0-251">Tschechien</span><span class="sxs-lookup"><span data-stu-id="29ec0-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-252">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-252">Format</span></span>

<span data-ttu-id="29ec0-253">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-254">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-254">Pattern</span></span>

<span data-ttu-id="29ec0-255">Acht Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="29ec0-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="29ec0-256">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="29ec0-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="29ec0-257">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="29ec0-257">A space (optional)</span></span>
    
- <span data-ttu-id="29ec0-258">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-259">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-259">Checksum</span></span>

<span data-ttu-id="29ec0-260">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-261">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-261">Definition</span></span>

<span data-ttu-id="29ec0-262">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-263">Der reguläre Ausdruck `Regex_czech_republic_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-264">Ein Schlüsselwort `Keywords_czech_republic_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="29ec0-265">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-265">Keywords</span></span>

<span data-ttu-id="29ec0-266">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-266"></span></span>
|<span data-ttu-id="29ec0-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-268">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-268">dl#</span></span>  <br/> <span data-ttu-id="29ec0-269">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-269">driver license</span></span>  <br/> <span data-ttu-id="29ec0-270">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-270">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-271">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-271">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-272">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-272">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-273">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-274">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-275">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-276">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-276">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-277">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-277">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-278">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-278">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-279">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-279">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-280">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="29ec0-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="29ec0-282">Dänemark</span><span class="sxs-lookup"><span data-stu-id="29ec0-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-283">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-283">Format</span></span>

<span data-ttu-id="29ec0-284">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-285">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-285">Pattern</span></span>

<span data-ttu-id="29ec0-286">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-287">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-287">Checksum</span></span>

<span data-ttu-id="29ec0-288">Ja</span><span class="sxs-lookup"><span data-stu-id="29ec0-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-289">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-289">Definition</span></span>

<span data-ttu-id="29ec0-290">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-291">Der reguläre Ausdruck `Regex_denmark_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-292">Ein Schlüsselwort `Keywords_denmark_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="29ec0-293">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-293">Keywords</span></span>

<span data-ttu-id="29ec0-294">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-294"></span></span>
|<span data-ttu-id="29ec0-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-296">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-296">dl#</span></span>  <br/> <span data-ttu-id="29ec0-297">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-297">driver license</span></span>  <br/> <span data-ttu-id="29ec0-298">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-298">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-299">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-299">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-300">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-300">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-301">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-302">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-303">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-304">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-304">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-305">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-305">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-306">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-306">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-307">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="29ec0-308">kørekort</span></span>  <br/> <span data-ttu-id="29ec0-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="29ec0-310">Estland</span><span class="sxs-lookup"><span data-stu-id="29ec0-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-311">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-311">Format</span></span>

<span data-ttu-id="29ec0-312">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-313">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-313">Pattern</span></span>

<span data-ttu-id="29ec0-314">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="29ec0-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="29ec0-315">Die Buchstaben "et" (unterscheidet nicht zwischen Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="29ec0-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="29ec0-316">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-317">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-317">Checksum</span></span>

<span data-ttu-id="29ec0-318">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-319">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-319">Definition</span></span>

<span data-ttu-id="29ec0-320">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-321">Der reguläre Ausdruck `Regex_estonia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-322">Ein Schlüsselwort `Keywords_estonia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-323">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-323">Keywords</span></span>

<span data-ttu-id="29ec0-324">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-324"></span></span>
|<span data-ttu-id="29ec0-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-326">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-326">dl#</span></span>  <br/> <span data-ttu-id="29ec0-327">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-327">driver license</span></span>  <br/> <span data-ttu-id="29ec0-328">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-328">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-329">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-329">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-330">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-330">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-331">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-331">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-332">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-333">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-334">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-335">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-335">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-336">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-336">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-337">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="29ec0-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="29ec0-339">Finnland</span><span class="sxs-lookup"><span data-stu-id="29ec0-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-340">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-340">Format</span></span>

<span data-ttu-id="29ec0-341">10 Ziffern, die einen Bindestrich enthalten</span><span class="sxs-lookup"><span data-stu-id="29ec0-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-342">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-342">Pattern</span></span>

<span data-ttu-id="29ec0-343">10 Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="29ec0-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="29ec0-344">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-344">Six digits</span></span> 
    
- <span data-ttu-id="29ec0-345">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="29ec0-345">A hyphen</span></span>
    
-  <span data-ttu-id="29ec0-346">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="29ec0-347">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-347">Checksum</span></span>

<span data-ttu-id="29ec0-348">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-349">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-349">Definition</span></span>

<span data-ttu-id="29ec0-350">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-351">Der reguläre Ausdruck `Regex_finland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-352">Ein Schlüsselwort `Keywords_finland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-353">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-353">Keywords</span></span>

<span data-ttu-id="29ec0-354">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-354"></span></span>
|<span data-ttu-id="29ec0-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-356">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-356">dl#</span></span>  <br/> <span data-ttu-id="29ec0-357">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-357">driver license</span></span>  <br/> <span data-ttu-id="29ec0-358">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-358">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-359">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-359">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-360">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-360">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-361">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-362">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-363">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-364">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-364">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-365">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-365">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-366">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-366">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-367">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="29ec0-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="29ec0-369">Frankreich</span><span class="sxs-lookup"><span data-stu-id="29ec0-369">France</span></span>

<span data-ttu-id="29ec0-370">Ausführliche Informationen finden Sie im Abschnitt "französische Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="29ec0-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="29ec0-371">Deutschland</span><span class="sxs-lookup"><span data-stu-id="29ec0-371">Germany</span></span>

<span data-ttu-id="29ec0-372">Ausführliche Informationen finden Sie im Abschnitt "Deutsche Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="29ec0-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="29ec0-373">Griechenland</span><span class="sxs-lookup"><span data-stu-id="29ec0-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-374">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-374">Format</span></span>

<span data-ttu-id="29ec0-375">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-376">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-376">Pattern</span></span>

 <span data-ttu-id="29ec0-377">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="29ec0-378">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-378">Checksum</span></span>

<span data-ttu-id="29ec0-379">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-380">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-380">Definition</span></span>

<span data-ttu-id="29ec0-381">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-382">Der reguläre Ausdruck `Regex_greece_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-383">Ein Schlüsselwort `Keywords_greece_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-384">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-384">Keywords</span></span>

<span data-ttu-id="29ec0-385">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-385"></span></span>
|<span data-ttu-id="29ec0-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-387">dlL#</span></span>  <br/> <span data-ttu-id="29ec0-388">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-388">driver license</span></span>  <br/> <span data-ttu-id="29ec0-389">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-389">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-390">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-390">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-391">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-391">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-392">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-393">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-394">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-395">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-395">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-396">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-396">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-397">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-397">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-398">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="29ec0-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="29ec0-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="29ec0-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="29ec0-401">Ungarn</span><span class="sxs-lookup"><span data-stu-id="29ec0-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-402">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-402">Format</span></span>

<span data-ttu-id="29ec0-403">Zwei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-404">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-404">Pattern</span></span>

<span data-ttu-id="29ec0-405">Zwei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="29ec0-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="29ec0-406">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="29ec0-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="29ec0-407">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-408">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-408">Checksum</span></span>

<span data-ttu-id="29ec0-409">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-410">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-410">Definition</span></span>

<span data-ttu-id="29ec0-411">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-412">Der reguläre Ausdruck `Regex_hungary_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-413">Ein Schlüsselwort `Keywords_hungary_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-414">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-414">Keywords</span></span>

<span data-ttu-id="29ec0-415">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-415"></span></span>
|<span data-ttu-id="29ec0-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-417">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-417">dl#</span></span>  <br/> <span data-ttu-id="29ec0-418">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-418">driver license</span></span>  <br/> <span data-ttu-id="29ec0-419">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-419">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-420">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-420">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-421">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-421">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-422">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-423">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-424">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-425">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-425">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-426">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-426">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-427">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-427">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-428">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="29ec0-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="29ec0-430">Irland</span><span class="sxs-lookup"><span data-stu-id="29ec0-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-431">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-431">Format</span></span>

<span data-ttu-id="29ec0-432">Sechs Ziffern, gefolgt von vier Buchstaben</span><span class="sxs-lookup"><span data-stu-id="29ec0-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-433">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-433">Pattern</span></span>

<span data-ttu-id="29ec0-434">Sechs Ziffern und vier Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="29ec0-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="29ec0-435">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-435">Six digits</span></span>
    
- <span data-ttu-id="29ec0-436">Vier Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="29ec0-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-437">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-437">Checksum</span></span>

<span data-ttu-id="29ec0-438">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-439">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-439">Definition</span></span>

<span data-ttu-id="29ec0-440">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-441">Der reguläre Ausdruck `Regex_ireland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-442">Ein Schlüsselwort `Keywords_ireland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-443">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-443">Keywords</span></span>

<span data-ttu-id="29ec0-444">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-444"></span></span>
|<span data-ttu-id="29ec0-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-446">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-446">dl#</span></span>  <br/> <span data-ttu-id="29ec0-447">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-447">driver license</span></span>  <br/> <span data-ttu-id="29ec0-448">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-448">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-449">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-449">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-450">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-450">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-451">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-452">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-453">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-454">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-454">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-455">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-455">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-456">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-456">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-457">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="29ec0-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="29ec0-459">Italien</span><span class="sxs-lookup"><span data-stu-id="29ec0-459">Italy</span></span>

<span data-ttu-id="29ec0-460">Ausführliche Informationen finden Sie im Abschnitt "Italien-Führerscheinnummer" unter [was die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="29ec0-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="29ec0-461">Lettland</span><span class="sxs-lookup"><span data-stu-id="29ec0-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-462">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-462">Format</span></span>

<span data-ttu-id="29ec0-463">Drei Buchstaben, gefolgt von sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-464">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-464">Pattern</span></span>

<span data-ttu-id="29ec0-465">Drei Buchstaben und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="29ec0-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="29ec0-466">Drei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="29ec0-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="29ec0-467">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-468">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-468">Checksum</span></span>

<span data-ttu-id="29ec0-469">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-470">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-470">Definition</span></span>

<span data-ttu-id="29ec0-471">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-472">Der reguläre Ausdruck `Regex_latvia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-473">Ein Schlüsselwort `Keywords_latvia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-474">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-474">Keywords</span></span>

<span data-ttu-id="29ec0-475">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-475"></span></span>
|<span data-ttu-id="29ec0-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-477">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-477">dl#</span></span>  <br/> <span data-ttu-id="29ec0-478">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-478">driver license</span></span>  <br/> <span data-ttu-id="29ec0-479">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-479">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-480">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-480">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-481">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-481">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-482">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-483">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-484">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-485">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-485">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-486">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-486">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-487">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-487">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-488">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="29ec0-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="29ec0-490">Litauen</span><span class="sxs-lookup"><span data-stu-id="29ec0-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-491">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-491">Format</span></span>

<span data-ttu-id="29ec0-492">Acht Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-493">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-493">Pattern</span></span>

 <span data-ttu-id="29ec0-494">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="29ec0-495">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-495">Checksum</span></span>

<span data-ttu-id="29ec0-496">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-497">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-497">Definition</span></span>

<span data-ttu-id="29ec0-498">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-499">Der reguläre Ausdruck `Regex_lithuania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-500">Ein Schlüsselwort `Keywords_lithuania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-501">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-501">Keywords</span></span>

<span data-ttu-id="29ec0-502">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-502"></span></span>
|<span data-ttu-id="29ec0-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-504">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-504">dl#</span></span>  <br/> <span data-ttu-id="29ec0-505">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-505">driver license</span></span>  <br/> <span data-ttu-id="29ec0-506">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-506">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-507">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-507">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-508">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-508">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-509">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-510">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-511">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-512">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-512">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-513">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-513">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-514">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-514">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-515">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-516">Vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="29ec0-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="29ec0-517">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="29ec0-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-518">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-518">Format</span></span>

<span data-ttu-id="29ec0-519">Sechs Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-520">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-520">Pattern</span></span>

 <span data-ttu-id="29ec0-521">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="29ec0-522">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-522">Checksum</span></span>

<span data-ttu-id="29ec0-523">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-524">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-524">Definition</span></span>

<span data-ttu-id="29ec0-525">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-526">Der reguläre Ausdruck `Regex_luxemburg_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-527">Ein Schlüsselwort `Keywords_luxemburg_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-528">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-528">Keywords</span></span>

<span data-ttu-id="29ec0-529">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-529"></span></span>
|<span data-ttu-id="29ec0-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-531">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-531">dl#</span></span>  <br/> <span data-ttu-id="29ec0-532">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-532">driver license</span></span>  <br/> <span data-ttu-id="29ec0-533">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-533">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-534">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-534">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-535">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-535">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-536">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-537">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-538">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-539">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-539">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-540">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-540">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-541">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-541">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-542">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="29ec0-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="29ec0-544">Malta</span><span class="sxs-lookup"><span data-stu-id="29ec0-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-545">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-545">Format</span></span>

<span data-ttu-id="29ec0-546">Kombination aus zwei Zeichen und sechs Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-547">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-547">Pattern</span></span>

<span data-ttu-id="29ec0-548">Kombination aus zwei Zeichen und sechs Ziffern:</span><span class="sxs-lookup"><span data-stu-id="29ec0-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="29ec0-549">Zwei Zeichen (Ziffern oder Buchstaben, bei denen die Groß-/Kleinschreibung nicht beachtet wird)</span><span class="sxs-lookup"><span data-stu-id="29ec0-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="29ec0-550">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="29ec0-550">A space (optional)</span></span>
    
- <span data-ttu-id="29ec0-551">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-551">Three digits</span></span>
    
- <span data-ttu-id="29ec0-552">Ein Leerzeichen (optional) </span><span class="sxs-lookup"><span data-stu-id="29ec0-552">A space (optional)</span></span>
    
- <span data-ttu-id="29ec0-553">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-554">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-554">Checksum</span></span>

<span data-ttu-id="29ec0-555">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-556">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-556">Definition</span></span>

<span data-ttu-id="29ec0-557">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-558">Der reguläre Ausdruck `Regex_malta_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-559">Ein Schlüsselwort `Keywords_malta_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-560">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-560">Keywords</span></span>

<span data-ttu-id="29ec0-561">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-561"></span></span>
|<span data-ttu-id="29ec0-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-563">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-563">dl#</span></span>  <br/> <span data-ttu-id="29ec0-564">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-564">driver license</span></span>  <br/> <span data-ttu-id="29ec0-565">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-565">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-566">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-566">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-567">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-567">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-568">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-569">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-570">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-571">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-571">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-572">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-572">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-573">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-573">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-574">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-575">Liċenzja TAS-Sewqan</span><span class="sxs-lookup"><span data-stu-id="29ec0-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="29ec0-576">Niederlande</span><span class="sxs-lookup"><span data-stu-id="29ec0-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-577">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-577">Format</span></span>

<span data-ttu-id="29ec0-578">10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-579">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-579">Pattern</span></span>

<span data-ttu-id="29ec0-580">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-581">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-581">Checksum</span></span>

<span data-ttu-id="29ec0-582">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-583">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-583">Definition</span></span>

<span data-ttu-id="29ec0-584">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-585">Der reguläre Ausdruck `Regex_netherlands_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-586">Ein Schlüsselwort `Keywords_netherlands_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-587">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-587">Keywords</span></span>

<span data-ttu-id="29ec0-588">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-588"></span></span>
|<span data-ttu-id="29ec0-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-590">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-590">dl#</span></span>  <br/> <span data-ttu-id="29ec0-591">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-591">driver license</span></span>  <br/> <span data-ttu-id="29ec0-592">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-592">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-593">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-593">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-594">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-594">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-595">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-596">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-597">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-598">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-598">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-599">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-599">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-600">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-600">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-601">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="29ec0-602">permis de conduire</span></span>  <br/> <span data-ttu-id="29ec0-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="29ec0-603">rijbewijs</span></span>  <br/> <span data-ttu-id="29ec0-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="29ec0-605">Polen</span><span class="sxs-lookup"><span data-stu-id="29ec0-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-606">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-606">Format</span></span>

<span data-ttu-id="29ec0-607">14 Ziffern mit 2 Schrägstrichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-608">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-608">Pattern</span></span>

<span data-ttu-id="29ec0-609">14 Ziffern und 2 Schrägstriche:</span><span class="sxs-lookup"><span data-stu-id="29ec0-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="29ec0-610">Fünf Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-610">Five digits</span></span> 
    
- <span data-ttu-id="29ec0-611">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="29ec0-611">A forward slash</span></span>
    
- <span data-ttu-id="29ec0-612">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-612">Two digits</span></span>
    
- <span data-ttu-id="29ec0-613">Ein Schrägstrich </span><span class="sxs-lookup"><span data-stu-id="29ec0-613">A forward slash</span></span>
    
- <span data-ttu-id="29ec0-614">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-615">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-615">Checksum</span></span>

<span data-ttu-id="29ec0-616">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-617">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-617">Definition</span></span>

<span data-ttu-id="29ec0-618">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-619">Der reguläre Ausdruck `Regex_poland_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-620">Ein Schlüsselwort `Keywords_poland_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-621">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-621">Keywords</span></span>

<span data-ttu-id="29ec0-622">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-622"></span></span>
|<span data-ttu-id="29ec0-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-624">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-624">dl#</span></span>  <br/> <span data-ttu-id="29ec0-625">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-625">driver license</span></span>  <br/> <span data-ttu-id="29ec0-626">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-626">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-627">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-627">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-628">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-628">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-629">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-630">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-631">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-632">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-632">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-633">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-633">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-634">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-634">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-635">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-636">Prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="29ec0-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="29ec0-637">Portugal</span><span class="sxs-lookup"><span data-stu-id="29ec0-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-638">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-638">Format</span></span>

<span data-ttu-id="29ec0-639">Zwei Buchstaben, gefolgt von sieben Zahlen im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-640">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-640">Pattern</span></span>

<span data-ttu-id="29ec0-641">Zwei Buchstaben, gefolgt von sieben Zahlen mit Sonderzeichen:</span><span class="sxs-lookup"><span data-stu-id="29ec0-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="29ec0-642">Zwei Buchstaben (Groß-/Kleinschreibung nicht beachtet)</span><span class="sxs-lookup"><span data-stu-id="29ec0-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="29ec0-643">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="29ec0-643">A hyphen</span></span>
    
- <span data-ttu-id="29ec0-644">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-644">Six digits</span></span>
    
- <span data-ttu-id="29ec0-645">Ein Leerzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-645">A space</span></span>
    
- <span data-ttu-id="29ec0-646">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="29ec0-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-647">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-647">Checksum</span></span>

<span data-ttu-id="29ec0-648">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-649">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-649">Definition</span></span>

<span data-ttu-id="29ec0-650">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-651">Der reguläre Ausdruck `Regex_portugal_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-652">Ein Schlüsselwort `Keywords_portugal_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-653">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-653">Keywords</span></span>

<span data-ttu-id="29ec0-654">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-654"></span></span>
|<span data-ttu-id="29ec0-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-656">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-656">dl#</span></span>  <br/> <span data-ttu-id="29ec0-657">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-657">driver license</span></span>  <br/> <span data-ttu-id="29ec0-658">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-658">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-659">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-659">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-660">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-660">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-661">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-662">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-663">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-664">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-664">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-665">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-665">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-666">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-666">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-667">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-668">Carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="29ec0-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="29ec0-669">Rumänien</span><span class="sxs-lookup"><span data-stu-id="29ec0-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-670">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-670">Format</span></span>

<span data-ttu-id="29ec0-671">Ein Zeichen gefolgt von acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-672">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-672">Pattern</span></span>

<span data-ttu-id="29ec0-673">Ein Zeichen gefolgt von acht Ziffern:</span><span class="sxs-lookup"><span data-stu-id="29ec0-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="29ec0-674">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="29ec0-675">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-676">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-676">Checksum</span></span>

<span data-ttu-id="29ec0-677">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-678">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-678">Definition</span></span>

<span data-ttu-id="29ec0-679">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-680">Der reguläre Ausdruck `Regex_romania_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-681">Ein Schlüsselwort `Keywords_romania_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-682">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-682">Keywords</span></span>

<span data-ttu-id="29ec0-683">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-683"></span></span>
|<span data-ttu-id="29ec0-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-685">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-685">dl#</span></span>  <br/> <span data-ttu-id="29ec0-686">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-686">driver license</span></span>  <br/> <span data-ttu-id="29ec0-687">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-687">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-688">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-688">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-689">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-689">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-690">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-691">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-692">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-693">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-693">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-694">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-694">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-695">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-695">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-696">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="29ec0-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="29ec0-698">Slowakei</span><span class="sxs-lookup"><span data-stu-id="29ec0-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-699">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-699">Format</span></span>

<span data-ttu-id="29ec0-700">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-701">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-701">Pattern</span></span>

<span data-ttu-id="29ec0-702">Ein Zeichen gefolgt von sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="29ec0-703">Ein Buchstabe (ohne Unterscheidung nach Groß-/Kleinschreibung) oder Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="29ec0-704">Sieben Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="29ec0-705">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-705">Checksum</span></span>

<span data-ttu-id="29ec0-706">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-707">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-707">Definition</span></span>

<span data-ttu-id="29ec0-708">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-709">Der reguläre Ausdruck `Regex_slovakia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-710">Ein Schlüsselwort `Keywords_slovakia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-711">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-711">Keywords</span></span>

<span data-ttu-id="29ec0-712">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-712"></span></span>
|<span data-ttu-id="29ec0-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-714">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-714">dl#</span></span>  <br/> <span data-ttu-id="29ec0-715">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-715">driver license</span></span>  <br/> <span data-ttu-id="29ec0-716">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-716">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-717">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-717">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-718">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-718">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-719">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-720">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-721">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-722">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-722">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-723">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-723">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-724">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-724">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-725">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="29ec0-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="29ec0-727">Slowenien</span><span class="sxs-lookup"><span data-stu-id="29ec0-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-728">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-728">Format</span></span>

<span data-ttu-id="29ec0-729">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-730">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-730">Pattern</span></span>

<span data-ttu-id="29ec0-731">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="29ec0-732">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-732">Checksum</span></span>

<span data-ttu-id="29ec0-733">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-734">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-734">Definition</span></span>

<span data-ttu-id="29ec0-735">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-736">Der reguläre Ausdruck `Regex_slovenia_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-737">Ein Schlüsselwort `Keywords_slovenia_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-738">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-738">Keywords</span></span>

<span data-ttu-id="29ec0-739">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-739"></span></span>
|<span data-ttu-id="29ec0-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-741">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-741">dl#</span></span>  <br/> <span data-ttu-id="29ec0-742">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-742">driver license</span></span>  <br/> <span data-ttu-id="29ec0-743">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-743">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-744">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-744">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-745">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-745">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-746">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-747">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-748">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-749">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-749">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-750">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-750">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-751">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-751">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-752">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="29ec0-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="29ec0-754">Spanien</span><span class="sxs-lookup"><span data-stu-id="29ec0-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-755">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-755">Format</span></span>

<span data-ttu-id="29ec0-756">Acht Ziffern, gefolgt von einem Zeichen</span><span class="sxs-lookup"><span data-stu-id="29ec0-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-757">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-757">Pattern</span></span>

<span data-ttu-id="29ec0-758">Acht Ziffern, gefolgt von einem Zeichen:</span><span class="sxs-lookup"><span data-stu-id="29ec0-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="29ec0-759">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-759">Eight digits</span></span> 
    
- <span data-ttu-id="29ec0-760">Eine Ziffer oder ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="29ec0-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-761">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-761">Checksum</span></span>

<span data-ttu-id="29ec0-762">Ja</span><span class="sxs-lookup"><span data-stu-id="29ec0-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-763">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-763">Definition</span></span>

<span data-ttu-id="29ec0-764">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-765">Die- `Func_spain_eu_driver's_license_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-766">Ein Schlüsselwort `Keywords_spain_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="29ec0-767">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-767">Keywords</span></span>

<span data-ttu-id="29ec0-768">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-768"></span></span>
|<span data-ttu-id="29ec0-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-770">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-771">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-771">dl#</span></span>  <br/> <span data-ttu-id="29ec0-772">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-772">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-773">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-773">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-774">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-774">driver license</span></span>  <br/> <span data-ttu-id="29ec0-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-775">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-776">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-777">driver's licence</span></span>  <br/> <span data-ttu-id="29ec0-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-778">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-779">Führerschein</span><span class="sxs-lookup"><span data-stu-id="29ec0-779">driving licence</span></span>  <br/> <span data-ttu-id="29ec0-780">driving license</span><span class="sxs-lookup"><span data-stu-id="29ec0-780">driving license</span></span>  <br/> <span data-ttu-id="29ec0-781">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-781">driver licence number</span></span>  <br/> <span data-ttu-id="29ec0-782">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-782">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-783">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-783">drivers licence number</span></span>  <br/> <span data-ttu-id="29ec0-784">Lizenznummer für Treiber</span><span class="sxs-lookup"><span data-stu-id="29ec0-784">drivers license number</span></span>  <br/> <span data-ttu-id="29ec0-785">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-785">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-786">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-786">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-787">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-787">driving licence number</span></span>  <br/> <span data-ttu-id="29ec0-788">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-788">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-789">Führerschein</span><span class="sxs-lookup"><span data-stu-id="29ec0-789">driving permit</span></span>  <br/> <span data-ttu-id="29ec0-790">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-790">driving permit number</span></span>  <br/> <span data-ttu-id="29ec0-791">Permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="29ec0-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="29ec0-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="29ec0-792">permiso conducción</span></span>  <br/> <span data-ttu-id="29ec0-793">número licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="29ec0-794">número de carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="29ec0-795">número Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="29ec0-796">licencia Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-796">licencia conducir</span></span>  <br/> <span data-ttu-id="29ec0-797">número de Permiso de Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="29ec0-798">número de Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="29ec0-799">número Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="29ec0-800">Permiso Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-800">permiso conducir</span></span>  <br/> <span data-ttu-id="29ec0-801">licencia de Manejo</span><span class="sxs-lookup"><span data-stu-id="29ec0-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="29ec0-802">El Carnet de Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="29ec0-803">Carnet Conducir</span><span class="sxs-lookup"><span data-stu-id="29ec0-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="29ec0-804">Schweden</span><span class="sxs-lookup"><span data-stu-id="29ec0-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="29ec0-805">Format</span><span class="sxs-lookup"><span data-stu-id="29ec0-805">Format</span></span>

<span data-ttu-id="29ec0-806">Zehn Ziffern mit einem Bindestrich</span><span class="sxs-lookup"><span data-stu-id="29ec0-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="29ec0-807">Muster</span><span class="sxs-lookup"><span data-stu-id="29ec0-807">Pattern</span></span>

<span data-ttu-id="29ec0-808">Zehn Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="29ec0-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="29ec0-809">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-809">Six digits</span></span> 
    
- <span data-ttu-id="29ec0-810">Ein Bindestrich</span><span class="sxs-lookup"><span data-stu-id="29ec0-810">A hyphen</span></span>
    
- <span data-ttu-id="29ec0-811">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="29ec0-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="29ec0-812">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="29ec0-812">Checksum</span></span>

<span data-ttu-id="29ec0-813">Nein</span><span class="sxs-lookup"><span data-stu-id="29ec0-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="29ec0-814">Definition</span><span class="sxs-lookup"><span data-stu-id="29ec0-814">Definition</span></span>

<span data-ttu-id="29ec0-815">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="29ec0-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="29ec0-816">Der reguläre Ausdruck `Regex_sweden_eu_driver's_license_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="29ec0-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="29ec0-817">Ein Schlüsselwort `Keywords_sweden_eu_driver's_license_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="29ec0-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="29ec0-818">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="29ec0-818">Keywords</span></span>

<span data-ttu-id="29ec0-819">| |</span><span class="sxs-lookup"><span data-stu-id="29ec0-819"></span></span>
|<span data-ttu-id="29ec0-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="29ec0-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="29ec0-821">DL #</span><span class="sxs-lookup"><span data-stu-id="29ec0-821">dl#</span></span>  <br/> <span data-ttu-id="29ec0-822">driver license</span><span class="sxs-lookup"><span data-stu-id="29ec0-822">driver license</span></span>  <br/> <span data-ttu-id="29ec0-823">Treiber Lizenznummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-823">driver license number</span></span>  <br/> <span data-ttu-id="29ec0-824">Treiber Lizenz</span><span class="sxs-lookup"><span data-stu-id="29ec0-824">driver licence</span></span>  <br/> <span data-ttu-id="29ec0-825">Treiber lic.</span><span class="sxs-lookup"><span data-stu-id="29ec0-825">drivers lic.</span></span>  <br/> <span data-ttu-id="29ec0-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="29ec0-826">drivers license</span></span>  <br/> <span data-ttu-id="29ec0-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="29ec0-827">drivers licence</span></span>  <br/> <span data-ttu-id="29ec0-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="29ec0-828">driver's license</span></span>  <br/> <span data-ttu-id="29ec0-829">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-829">driver's license number</span></span>  <br/> <span data-ttu-id="29ec0-830">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-830">driver's licence number</span></span>  <br/> <span data-ttu-id="29ec0-831">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="29ec0-831">driving license number</span></span>  <br/> <span data-ttu-id="29ec0-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="29ec0-832">dlno#</span></span>  <br/> <span data-ttu-id="29ec0-833">körkort</span><span class="sxs-lookup"><span data-stu-id="29ec0-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="29ec0-834">UK</span><span class="sxs-lookup"><span data-stu-id="29ec0-834">UK</span></span>

<span data-ttu-id="29ec0-835">Ausführliche Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="29ec0-835">For details, see the section "U.K.</span></span> <span data-ttu-id="29ec0-836">Nummer des Führerscheins "in [dem, wonach die Typen für vertrauliche Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="29ec0-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="29ec0-837">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29ec0-837">See also</span></span>

[<span data-ttu-id="29ec0-838">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="29ec0-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

