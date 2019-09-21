---
title: EU-Steueridentifikationsnummer
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-Steueridentifikationsnummer" erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081463"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="270c3-104">EU-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-104">EU Tax Identification Number</span></span>

<span data-ttu-id="270c3-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der vertraulichen Informationen für die EU-Steueridentifikationsnummer (TIN) erkennt.</span><span class="sxs-lookup"><span data-stu-id="270c3-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="270c3-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="270c3-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="270c3-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="270c3-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="270c3-108">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-108">Format</span></span>

<span data-ttu-id="270c3-109">Neun Ziffern mit optionalem Bindestrich und Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="270c3-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-110">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-110">Pattern</span></span>

<span data-ttu-id="270c3-111">Neun Ziffern mit optionalem Bindestrich und Schrägstrich:</span><span class="sxs-lookup"><span data-stu-id="270c3-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="270c3-112">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-112">Two digits</span></span> 
    
- <span data-ttu-id="270c3-113">Ein Bindestrich (optional)</span><span class="sxs-lookup"><span data-stu-id="270c3-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="270c3-114">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-114">Three digits</span></span>
    
- <span data-ttu-id="270c3-115">Ein Schrägstrich (optional)</span><span class="sxs-lookup"><span data-stu-id="270c3-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="270c3-116">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-117">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-117">Checksum</span></span>

<span data-ttu-id="270c3-118">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-119">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-119">Definition</span></span>

<span data-ttu-id="270c3-120">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-121">Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-122">Ein Schlüsselwort `Keywords_austria_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-123">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-124">Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-125">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="270c3-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-127">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-127">tax number</span></span>
  
<span data-ttu-id="270c3-128">number</span><span class="sxs-lookup"><span data-stu-id="270c3-128">number</span></span>
  
<span data-ttu-id="270c3-129">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-129">tax registration number</span></span>
  
<span data-ttu-id="270c3-130">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-130">tax id</span></span>
  
<span data-ttu-id="270c3-131">St.Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-131">st.nr.</span></span>
  
<span data-ttu-id="270c3-132">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="270c3-133">Belgien</span><span class="sxs-lookup"><span data-stu-id="270c3-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="270c3-134">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-134">Format</span></span>

<span data-ttu-id="270c3-135">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-136">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-136">Pattern</span></span>

<span data-ttu-id="270c3-137">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="270c3-137">11 digits:</span></span>
  
- <span data-ttu-id="270c3-138">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-138">Two digits</span></span>
    
- <span data-ttu-id="270c3-139">A "0" oder "1"</span><span class="sxs-lookup"><span data-stu-id="270c3-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="270c3-140">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="270c3-140">One digit</span></span>
    
- <span data-ttu-id="270c3-141">A "0" oder "1" oder "2" oder "3"</span><span class="sxs-lookup"><span data-stu-id="270c3-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="270c3-142">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-143">Checksum</span></span>

<span data-ttu-id="270c3-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-145">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-145">Definition</span></span>

<span data-ttu-id="270c3-146">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-147">Der reguläre Ausdruck `Regex_belgium_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-148">Ein Schlüsselwort `Keywords_belgium_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-149">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="270c3-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-151">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-151">tax number</span></span>
  
<span data-ttu-id="270c3-152">nationale Registrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-152">national registration number</span></span>
  
<span data-ttu-id="270c3-153">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-153">tax registration number</span></span>
  
<span data-ttu-id="270c3-154">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-154">tax id</span></span>
  
<span data-ttu-id="270c3-155">NIF</span><span class="sxs-lookup"><span data-stu-id="270c3-155">nif</span></span>
  
<span data-ttu-id="270c3-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="270c3-156">nif#</span></span>
  
<span data-ttu-id="270c3-157">Numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="270c3-157">numéro de registre national</span></span>
  
<span data-ttu-id="270c3-158">Numéro d'identification Fiscale</span><span class="sxs-lookup"><span data-stu-id="270c3-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="270c3-159">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="270c3-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="270c3-160">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-160">Format</span></span>

<span data-ttu-id="270c3-161">Zehn Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-162">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-162">Pattern</span></span>

<span data-ttu-id="270c3-163">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-164">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-164">Checksum</span></span>

<span data-ttu-id="270c3-165">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-166">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-166">Definition</span></span>

<span data-ttu-id="270c3-167">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-168">Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-169">Ein Schlüsselwort `Keywords_bulgaria_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-170">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-171">Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-172">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="270c3-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-174">BUCN</span><span class="sxs-lookup"><span data-stu-id="270c3-174">bucn</span></span>
  
<span data-ttu-id="270c3-175">einheitliche Zivil Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-175">uniform civil number</span></span>
  
<span data-ttu-id="270c3-176">BUCN #</span><span class="sxs-lookup"><span data-stu-id="270c3-176">bucn#</span></span>
  
<span data-ttu-id="270c3-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="270c3-178">Uniform Civil ID</span><span class="sxs-lookup"><span data-stu-id="270c3-178">uniform civil id</span></span>
  
<span data-ttu-id="270c3-179">Uniform Civil Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-179">uniform civil no</span></span>
  
<span data-ttu-id="270c3-180">EGN</span><span class="sxs-lookup"><span data-stu-id="270c3-180">egn</span></span>
  
<span data-ttu-id="270c3-181">Bulgarische Uniform Civil Number</span><span class="sxs-lookup"><span data-stu-id="270c3-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="270c3-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="270c3-182">uniformcivilno#</span></span>
  
<span data-ttu-id="270c3-183">EGN #</span><span class="sxs-lookup"><span data-stu-id="270c3-183">egn#</span></span>
  
<span data-ttu-id="270c3-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="270c3-184">униформ граждански номер</span></span>
  
<span data-ttu-id="270c3-185">униформ-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-185">униформ id</span></span>
  
<span data-ttu-id="270c3-186">униформ-граждански-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-186">униформ граждански id</span></span>
  
<span data-ttu-id="270c3-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="270c3-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="270c3-188">Kroatien</span><span class="sxs-lookup"><span data-stu-id="270c3-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="270c3-189">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-189">Format</span></span>

<span data-ttu-id="270c3-190">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-191">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-191">Pattern</span></span>

<span data-ttu-id="270c3-192">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="270c3-192">11 digits:</span></span>
  
- <span data-ttu-id="270c3-193">Zehn Ziffern, nach dem Zufallsprinzip ausgewählt</span><span class="sxs-lookup"><span data-stu-id="270c3-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="270c3-194">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="270c3-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-195">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-195">Checksum</span></span>

<span data-ttu-id="270c3-196">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-197">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-197">Definition</span></span>

<span data-ttu-id="270c3-198">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-199">Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-200">Ein Schlüsselwort `Keywords_croatia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-201">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-202">Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-203">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="270c3-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-205">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-205">tax number</span></span>
  
<span data-ttu-id="270c3-206">Steuer</span><span class="sxs-lookup"><span data-stu-id="270c3-206">tax</span></span>
  
<span data-ttu-id="270c3-207">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-207">tax id</span></span>
  
<span data-ttu-id="270c3-208">oid</span><span class="sxs-lookup"><span data-stu-id="270c3-208">oid</span></span>
  
<span data-ttu-id="270c3-209">OID #</span><span class="sxs-lookup"><span data-stu-id="270c3-209">oid#</span></span>
  
<span data-ttu-id="270c3-210">porezni Broj</span><span class="sxs-lookup"><span data-stu-id="270c3-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="270c3-211">Zypern</span><span class="sxs-lookup"><span data-stu-id="270c3-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="270c3-212">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-212">Format</span></span>

<span data-ttu-id="270c3-213">Acht Ziffern und ein Buchstabe im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-214">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-214">Pattern</span></span>

<span data-ttu-id="270c3-215">Acht Ziffern und ein Buchstabe:</span><span class="sxs-lookup"><span data-stu-id="270c3-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="270c3-216">A "0"</span><span class="sxs-lookup"><span data-stu-id="270c3-216">A "0"</span></span> 
    
- <span data-ttu-id="270c3-217">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="270c3-217">Seven digits</span></span>
    
- <span data-ttu-id="270c3-218">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-219">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-219">Checksum</span></span>

<span data-ttu-id="270c3-220">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-221">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-221">Definition</span></span>

<span data-ttu-id="270c3-222">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-223">Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-224">Ein Schlüsselwort `Keywords_cyprus_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-225">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-226">Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-227">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="270c3-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-229">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-229">tax number</span></span>
  
<span data-ttu-id="270c3-230">Steuer</span><span class="sxs-lookup"><span data-stu-id="270c3-230">tax</span></span>
  
<span data-ttu-id="270c3-231">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-231">tax id</span></span>
  
<span data-ttu-id="270c3-232">Steuer Identifikationscode</span><span class="sxs-lookup"><span data-stu-id="270c3-232">tax identification code</span></span>
  
<span data-ttu-id="270c3-233">TIC</span><span class="sxs-lookup"><span data-stu-id="270c3-233">tic</span></span>
  
<span data-ttu-id="270c3-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="270c3-234">tic#</span></span>
  
<span data-ttu-id="270c3-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="270c3-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="270c3-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="270c3-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="270c3-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="270c3-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="270c3-238">Tschechien</span><span class="sxs-lookup"><span data-stu-id="270c3-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="270c3-239">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-239">Format</span></span>

<span data-ttu-id="270c3-240">Neun oder zehn Ziffern mit einem optionalen Backslash</span><span class="sxs-lookup"><span data-stu-id="270c3-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-241">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-241">Pattern</span></span>

<span data-ttu-id="270c3-242">Neun oder zehn Ziffern mit einem optionalen backslashl:</span><span class="sxs-lookup"><span data-stu-id="270c3-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="270c3-243">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-243">Six digits</span></span> 
    
- <span data-ttu-id="270c3-244">Ein Backslash (optional)</span><span class="sxs-lookup"><span data-stu-id="270c3-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="270c3-245">Drei oder vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-246">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-246">Checksum</span></span>

<span data-ttu-id="270c3-247">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-248">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-248">Definition</span></span>

<span data-ttu-id="270c3-249">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-250">Der reguläre Ausdruck `Regex_czech_republic_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-251">Ein Schlüsselwort `Keywords_czech_republic_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-252">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="270c3-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-254">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-254">tax number</span></span>
  
<span data-ttu-id="270c3-255">Steuer</span><span class="sxs-lookup"><span data-stu-id="270c3-255">tax</span></span>
  
<span data-ttu-id="270c3-256">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-256">tax id</span></span>
  
<span data-ttu-id="270c3-257">persönliche Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-257">personal number</span></span>
  
<span data-ttu-id="270c3-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="270c3-258">daňové číslo</span></span>
  
<span data-ttu-id="270c3-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="270c3-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="270c3-260">Dänemark</span><span class="sxs-lookup"><span data-stu-id="270c3-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="270c3-261">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-261">Format</span></span>

<span data-ttu-id="270c3-262">Zehn Ziffern mit einem Bindestrich</span><span class="sxs-lookup"><span data-stu-id="270c3-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-263">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-263">Pattern</span></span>

<span data-ttu-id="270c3-264">Zehn Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="270c3-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="270c3-265">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="270c3-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="270c3-266">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="270c3-266">A hyphen</span></span>
    
- <span data-ttu-id="270c3-267">Vier Ziffern, die einer Sequenznummer entsprechen, wobei die erste Ziffer dem Jahrhundert der Geburt entspricht und die letzte Ziffer dem Geschlecht der Person entspricht (ungerade für männliche und sogar für weiblich)</span><span class="sxs-lookup"><span data-stu-id="270c3-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-268">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-268">Checksum</span></span>

<span data-ttu-id="270c3-269">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-270">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-270">Definition</span></span>

<span data-ttu-id="270c3-271">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-272">Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-273">Ein Schlüsselwort `Keywords_denmark_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-275">Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-276">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="270c3-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-278">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-278">tax number</span></span>
  
<span data-ttu-id="270c3-279">Steuer</span><span class="sxs-lookup"><span data-stu-id="270c3-279">tax</span></span>
  
<span data-ttu-id="270c3-280">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-280">tax id</span></span>
  
<span data-ttu-id="270c3-281">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-281">cpr number</span></span>
  
<span data-ttu-id="270c3-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="270c3-282">cpr#</span></span>
  
<span data-ttu-id="270c3-283">Skate Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-283">skat nummer</span></span>
  
<span data-ttu-id="270c3-284">Skat-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="270c3-285">Estland</span><span class="sxs-lookup"><span data-stu-id="270c3-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="270c3-286">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-286">Format</span></span>

<span data-ttu-id="270c3-287">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-288">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-288">Pattern</span></span>

<span data-ttu-id="270c3-289">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="270c3-289">11 digits:</span></span>
  
-  <span data-ttu-id="270c3-290">Eine Ziffer, die dem Geschlecht und dem Jahrhundert der Geburt entspricht, wobei eine ungerade Zahl männlich ist und die gerade Zahl weiblich wie folgt angibt: 1, 2 für das 19. Jahrhundert; 3,4 für das 20. Jahrhundert; und 5, 6 für das 21. Jahrhundert</span><span class="sxs-lookup"><span data-stu-id="270c3-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="270c3-291">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="270c3-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="270c3-292">Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am gleichen Datum geboren wurden</span><span class="sxs-lookup"><span data-stu-id="270c3-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="270c3-293">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="270c3-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-294">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-294">Checksum</span></span>

<span data-ttu-id="270c3-295">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-296">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-296">Definition</span></span>

<span data-ttu-id="270c3-297">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-298">Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-299">Ein Schlüsselwort `Keywords_estonia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-300">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-301">Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-302">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="270c3-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-304">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-304">tax number</span></span>
  
<span data-ttu-id="270c3-305">Steuer</span><span class="sxs-lookup"><span data-stu-id="270c3-305">tax</span></span>
  
<span data-ttu-id="270c3-306">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-306">tax id</span></span>
  
<span data-ttu-id="270c3-307">persönlicher Code</span><span class="sxs-lookup"><span data-stu-id="270c3-307">personal code</span></span>
  
<span data-ttu-id="270c3-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="270c3-308">maksunumber</span></span>
  
<span data-ttu-id="270c3-309">maksu-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-309">maksu id</span></span>
  
<span data-ttu-id="270c3-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="270c3-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="270c3-311">Finnland</span><span class="sxs-lookup"><span data-stu-id="270c3-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="270c3-312">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-312">Format</span></span>

<span data-ttu-id="270c3-313">Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-314">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-314">Pattern</span></span>

<span data-ttu-id="270c3-315">Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen:</span><span class="sxs-lookup"><span data-stu-id="270c3-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="270c3-316">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-316">Six digits</span></span>
    
- <span data-ttu-id="270c3-317">Eine der folgenden Optionen: ein Pluszeichen, ein Minuszeichen oder der Buchstabe "a" (Groß-/Kleinschreibung nicht beachtet), wobei das Pluszeichen zwischen 1800-1899 geboren wird, das Minuszeichen zwischen 1900-1999 und "a" geboren ist 2000 und nach</span><span class="sxs-lookup"><span data-stu-id="270c3-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="270c3-318">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-318">Three digits</span></span>
    
- <span data-ttu-id="270c3-319">Ein Buchstabe oder eine Zahl</span><span class="sxs-lookup"><span data-stu-id="270c3-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-320">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-320">Checksum</span></span>

<span data-ttu-id="270c3-321">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-322">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-322">Definition</span></span>

<span data-ttu-id="270c3-323">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-324">Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-325">Ein Schlüsselwort `Keywords_finland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-326">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-327">Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-328">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="270c3-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-330">identification number</span><span class="sxs-lookup"><span data-stu-id="270c3-330">identification number</span></span>
  
<span data-ttu-id="270c3-331">persönliche ID</span><span class="sxs-lookup"><span data-stu-id="270c3-331">personal id</span></span>
  
<span data-ttu-id="270c3-332">Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-332">identity number</span></span>
  
<span data-ttu-id="270c3-333">Finnische Nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-333">finnish national id number</span></span>
  
<span data-ttu-id="270c3-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-334">personalidnumber#</span></span>
  
<span data-ttu-id="270c3-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="270c3-335">national identification number</span></span>
  
<span data-ttu-id="270c3-336">ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-336">id number</span></span>
  
<span data-ttu-id="270c3-337">nationale ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-337">national id no.</span></span>
  
<span data-ttu-id="270c3-338">nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-338">national id number</span></span>
  
<span data-ttu-id="270c3-339">ID Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-339">id no</span></span>
  
<span data-ttu-id="270c3-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="270c3-340">tunnistenumero</span></span>
  
<span data-ttu-id="270c3-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="270c3-341">henkilötunnus</span></span>
  
<span data-ttu-id="270c3-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="270c3-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="270c3-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="270c3-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="270c3-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="270c3-344">identiteetti numero</span></span>
  
<span data-ttu-id="270c3-345">Suomen der Kok henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="270c3-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="270c3-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="270c3-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="270c3-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="270c3-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="270c3-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="270c3-348">tunnusnumero</span></span>
  
<span data-ttu-id="270c3-349">der Kok tunnus numero</span><span class="sxs-lookup"><span data-stu-id="270c3-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="270c3-350">Frankreich</span><span class="sxs-lookup"><span data-stu-id="270c3-350">France</span></span>

### <a name="format"></a><span data-ttu-id="270c3-351">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-351">Format</span></span>

<span data-ttu-id="270c3-352">13 Ziffern für einzelne Personen und neun Ziffern für Entitäten</span><span class="sxs-lookup"><span data-stu-id="270c3-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-353">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-353">Pattern</span></span>

<span data-ttu-id="270c3-354">13 Ziffern für einzelne Personen:</span><span class="sxs-lookup"><span data-stu-id="270c3-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="270c3-355">Eine Ziffer, die 0, 1, 2 oder 3 sein muss</span><span class="sxs-lookup"><span data-stu-id="270c3-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="270c3-356">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-356">12 digits</span></span>
    
<span data-ttu-id="270c3-357">Neun Ziffern für Entitäten</span><span class="sxs-lookup"><span data-stu-id="270c3-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-358">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-358">Checksum</span></span>

<span data-ttu-id="270c3-359">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-360">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-360">Definition</span></span>

<span data-ttu-id="270c3-361">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-362">Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-363">Ein Schlüsselwort `Keywords_france_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-364">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-365">Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-366">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="270c3-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-368">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-368">tax identification number</span></span>
  
<span data-ttu-id="270c3-369">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-369">tax number</span></span>
  
<span data-ttu-id="270c3-370">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-370">tax id</span></span>
  
<span data-ttu-id="270c3-371">Numéro d'identification Fiscale</span><span class="sxs-lookup"><span data-stu-id="270c3-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="270c3-372">Deutschland</span><span class="sxs-lookup"><span data-stu-id="270c3-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="270c3-373">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-373">Format</span></span>

<span data-ttu-id="270c3-374">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-375">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-375">Pattern</span></span>

<span data-ttu-id="270c3-376">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="270c3-376">11 digits :</span></span>
  
-  <span data-ttu-id="270c3-377">Zehn Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-377">Ten digits</span></span> 
    
- <span data-ttu-id="270c3-378">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="270c3-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-379">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-379">Checksum</span></span>

<span data-ttu-id="270c3-380">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-381">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-381">Definition</span></span>

<span data-ttu-id="270c3-382">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-383">Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-384">Ein Schlüsselwort `Keywords_germany_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-385">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-386">Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-387">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="270c3-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-389">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-389">tax number</span></span>
  
<span data-ttu-id="270c3-390">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-390">tax no.</span></span>
  
<span data-ttu-id="270c3-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-391">taxno#</span></span>
  
<span data-ttu-id="270c3-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-392">taxnumber#</span></span>
  
<span data-ttu-id="270c3-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-393">taxnumber</span></span>
  
<span data-ttu-id="270c3-394">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-394">tax id</span></span>
  
<span data-ttu-id="270c3-395">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-395">taxid#</span></span>
  
<span data-ttu-id="270c3-396">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-396">tax identification number</span></span>
  
<span data-ttu-id="270c3-397">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-397">tax identification no.</span></span>
  
<span data-ttu-id="270c3-398">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-398">steuernummer</span></span>
  
<span data-ttu-id="270c3-399">Ingo-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-399">steuer id</span></span>
  
<span data-ttu-id="270c3-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="270c3-401">Griechenland</span><span class="sxs-lookup"><span data-stu-id="270c3-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="270c3-402">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-402">Format</span></span>

<span data-ttu-id="270c3-403">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-404">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-404">Pattern</span></span>

<span data-ttu-id="270c3-405">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-406">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-406">Checksum</span></span>

<span data-ttu-id="270c3-407">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-408">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-408">Definition</span></span>

<span data-ttu-id="270c3-409">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-410">Der reguläre Ausdruck `Regex_greece_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-411">Ein Schlüsselwort `Keywords_greece_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-412">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="270c3-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-414">AFM</span><span class="sxs-lookup"><span data-stu-id="270c3-414">afm</span></span>
  
<span data-ttu-id="270c3-415">Zinn</span><span class="sxs-lookup"><span data-stu-id="270c3-415">tin</span></span>
  
<span data-ttu-id="270c3-416">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="270c3-416">tax id no.</span></span>
  
<span data-ttu-id="270c3-417">Steuernummer Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-417">tax id no</span></span>
  
<span data-ttu-id="270c3-418">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-418">tax identification number</span></span>
  
<span data-ttu-id="270c3-419">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-419">tax registry number</span></span>
  
<span data-ttu-id="270c3-420">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-420">tax registry no.</span></span>
  
<span data-ttu-id="270c3-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="270c3-421">afm#</span></span>
  
<span data-ttu-id="270c3-422">Zinn #</span><span class="sxs-lookup"><span data-stu-id="270c3-422">tin#</span></span>
  
<span data-ttu-id="270c3-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="270c3-423">taxidno#</span></span>
  
<span data-ttu-id="270c3-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="270c3-424">taxregistryno#</span></span>
  
<span data-ttu-id="270c3-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="270c3-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="270c3-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="270c3-426">aφμ</span></span>
  
<span data-ttu-id="270c3-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="270c3-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="270c3-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="270c3-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="270c3-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="270c3-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="270c3-430">Ungarn</span><span class="sxs-lookup"><span data-stu-id="270c3-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="270c3-431">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-431">Format</span></span>

<span data-ttu-id="270c3-432">Zehn Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-433">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-433">Pattern</span></span>

<span data-ttu-id="270c3-434">Zehn Ziffern:</span><span class="sxs-lookup"><span data-stu-id="270c3-434">Ten digits:</span></span>
  
-  <span data-ttu-id="270c3-435">Eine Ziffer, die "8" sein muss</span><span class="sxs-lookup"><span data-stu-id="270c3-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="270c3-436">Fünf Ziffern, die der Anzahl von Tagen zwischen dem Datum 01/01/1867 und dem Geburtsdatum der einzelnen Personen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="270c3-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="270c3-437">Drei Ziffern, die der durch Zufall generierten Zahl entsprechen, um Personen zu unterscheiden, die am selben Tag geboren wurden</span><span class="sxs-lookup"><span data-stu-id="270c3-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="270c3-438">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="270c3-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-439">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-439">Checksum</span></span>

<span data-ttu-id="270c3-440">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-441">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-441">Definition</span></span>

<span data-ttu-id="270c3-442">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-443">Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-444">Ein Schlüsselwort `Keywords_hungary_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-445">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-446">Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-447">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="270c3-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-449">ungarische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="270c3-450">Ungarisch Zinn</span><span class="sxs-lookup"><span data-stu-id="270c3-450">hungarian tin</span></span>
  
<span data-ttu-id="270c3-451">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-451">tax id number</span></span>
  
<span data-ttu-id="270c3-452">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="270c3-452">vat number</span></span>
  
<span data-ttu-id="270c3-453">Steuerbehörde Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-453">tax authority no</span></span>
  
<span data-ttu-id="270c3-454">USt-ID-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-454">tax id tax identity number</span></span>
  
<span data-ttu-id="270c3-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-455">taxidnumber#</span></span>
  
<span data-ttu-id="270c3-456">Zinn #</span><span class="sxs-lookup"><span data-stu-id="270c3-456">tin#</span></span>
  
<span data-ttu-id="270c3-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="270c3-457">hungatiantin#</span></span>
  
<span data-ttu-id="270c3-458">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-458">tax identification no</span></span>
  
<span data-ttu-id="270c3-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="270c3-459">taxidno#</span></span>
  
<span data-ttu-id="270c3-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="270c3-460">adóazonosító szám</span></span>
  
<span data-ttu-id="270c3-461">adószám</span><span class="sxs-lookup"><span data-stu-id="270c3-461">adószám</span></span>
  
<span data-ttu-id="270c3-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="270c3-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="270c3-463">Irland</span><span class="sxs-lookup"><span data-stu-id="270c3-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="270c3-464">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-464">Format</span></span>

<span data-ttu-id="270c3-465">Sieben Ziffern, gefolgt von einem Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-466">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-466">Pattern</span></span>

<span data-ttu-id="270c3-467">Sieben Ziffern, gefolgt von einem Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="270c3-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="270c3-468">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="270c3-468">Seven digits</span></span> 
    
- <span data-ttu-id="270c3-469">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-470">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-470">Checksum</span></span>

<span data-ttu-id="270c3-471">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-472">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-472">Definition</span></span>

<span data-ttu-id="270c3-473">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-474">Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-475">Ein Schlüsselwort `Keywords_ireland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-476">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-477">Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="270c3-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-480">öffentlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-480">public service no</span></span>
  
<span data-ttu-id="270c3-481">persönlicher öffentlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-481">personal public service no</span></span>
  
<span data-ttu-id="270c3-482">PPS Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-482">pps no</span></span>
  
<span data-ttu-id="270c3-483">persönlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-483">personal service no</span></span>
  
<span data-ttu-id="270c3-484">PPS-Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-484">pps service no</span></span>
  
<span data-ttu-id="270c3-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="270c3-485">ppsno#</span></span>
  
<span data-ttu-id="270c3-486">irische PPS Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-486">irish pps no</span></span>
  
<span data-ttu-id="270c3-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="270c3-487">publicserviceno#</span></span>
  
<span data-ttu-id="270c3-488">persönliche öffentliche Dienstnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-488">personal public service number</span></span>
  
<span data-ttu-id="270c3-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="270c3-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="270c3-490">PPS-uimh</span><span class="sxs-lookup"><span data-stu-id="270c3-490">pps uimh</span></span>
  
<span data-ttu-id="270c3-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="270c3-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="270c3-492">Italien</span><span class="sxs-lookup"><span data-stu-id="270c3-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="270c3-493">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-493">Format</span></span>

<span data-ttu-id="270c3-494">16 Buchstaben und Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-495">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-495">Pattern</span></span>

<span data-ttu-id="270c3-496">16 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="270c3-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="270c3-497">Drei Buchstaben, die den ersten drei Konsonanten im Familiennamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="270c3-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="270c3-498">Drei Buchstaben, die den ersten, dritten und vierten Konsonanten im Vornamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="270c3-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="270c3-499">Zwei Ziffern, die den letzten Ziffern des Geburtsjahres entsprechen</span><span class="sxs-lookup"><span data-stu-id="270c3-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="270c3-500">Eine Ziffer, die dem Monat der Geburt entspricht – Buchstaben werden in alphabetischer Reihenfolge verwendet, aber nur die Buchstaben a bis E, H, L, M, P, R bis T werden verwendet (der Januar ist also a und Oktober ist r).</span><span class="sxs-lookup"><span data-stu-id="270c3-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="270c3-501">Zwei Ziffern, die dem Tag des Geburtsmonats entsprechen, in dem 40 dem Tag der Geburt hinzugefügt wird, damit weibliche Personen von Männern unterscheiden können</span><span class="sxs-lookup"><span data-stu-id="270c3-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="270c3-502">Vier Ziffern, die einer Ortskennzahl entsprechen, die für die Gemeinde spezifisch ist, in der die Person geboren wurde – landesweite Codes werden für fremde Länder verwendet</span><span class="sxs-lookup"><span data-stu-id="270c3-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="270c3-503">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="270c3-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-504">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-504">Checksum</span></span>

<span data-ttu-id="270c3-505">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-506">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-506">Definition</span></span>

<span data-ttu-id="270c3-507">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-508">Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-509">Ein Schlüsselwort `Keywords_italy_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-510">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-511">Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-512">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="270c3-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-514">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-514">tax number</span></span>
  
<span data-ttu-id="270c3-515">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-515">tax no.</span></span>
  
<span data-ttu-id="270c3-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-516">taxno#</span></span>
  
<span data-ttu-id="270c3-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-517">taxnumber#</span></span>
  
<span data-ttu-id="270c3-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-518">taxnumber</span></span>
  
<span data-ttu-id="270c3-519">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-519">tax id</span></span>
  
<span data-ttu-id="270c3-520">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-520">taxid#</span></span>
  
<span data-ttu-id="270c3-521">Geschäftscode</span><span class="sxs-lookup"><span data-stu-id="270c3-521">fiscal code</span></span>
  
<span data-ttu-id="270c3-522">Geschäftsjahr</span><span class="sxs-lookup"><span data-stu-id="270c3-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="270c3-523">Lettland</span><span class="sxs-lookup"><span data-stu-id="270c3-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="270c3-524">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-524">Format</span></span>

<span data-ttu-id="270c3-525">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-526">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-526">Pattern</span></span>

<span data-ttu-id="270c3-527">11 Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="270c3-528">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="270c3-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="270c3-529">Eine Ziffer, die dem Jahrhundert der Geburt entspricht, wobei "0" dem 19. Jahrhundert entspricht, "1" entspricht dem 20. Jahrhundert, und "2" entspricht dem 21. Jahrhundert</span><span class="sxs-lookup"><span data-stu-id="270c3-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="270c3-530">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-531">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-531">Checksum</span></span>

<span data-ttu-id="270c3-532">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-533">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-533">Definition</span></span>

<span data-ttu-id="270c3-534">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-535">Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-536">Ein Schlüsselwort `Keywords_latvia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-537">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-538">Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-539">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="270c3-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-541">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-541">tax number</span></span>
  
<span data-ttu-id="270c3-542">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-542">tax no.</span></span>
  
<span data-ttu-id="270c3-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-543">taxno#</span></span>
  
<span data-ttu-id="270c3-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-544">taxnumber#</span></span>
  
<span data-ttu-id="270c3-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-545">taxnumber</span></span>
  
<span data-ttu-id="270c3-546">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-546">tax id</span></span>
  
<span data-ttu-id="270c3-547">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-547">taxid#</span></span>
  
<span data-ttu-id="270c3-548">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-548">tax identification number</span></span>
  
<span data-ttu-id="270c3-549">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-549">tax identification no.</span></span>
  
<span data-ttu-id="270c3-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="270c3-550">nodokļa numurs</span></span>
  
<span data-ttu-id="270c3-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="270c3-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="270c3-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="270c3-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="270c3-553">Litauen</span><span class="sxs-lookup"><span data-stu-id="270c3-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="270c3-554">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-554">Format</span></span>

<span data-ttu-id="270c3-555">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-556">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-556">Pattern</span></span>

<span data-ttu-id="270c3-557">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-558">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-558">Checksum</span></span>

<span data-ttu-id="270c3-559">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-560">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-560">Definition</span></span>

<span data-ttu-id="270c3-561">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-562">Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-563">Ein Schlüsselwort `Keywords_lithuania_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-564">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-565">Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-566">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="270c3-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-568">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-568">tax number</span></span>
  
<span data-ttu-id="270c3-569">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-569">tax no.</span></span>
  
<span data-ttu-id="270c3-570">Steuernummer #</span><span class="sxs-lookup"><span data-stu-id="270c3-570">tax no#</span></span>
  
<span data-ttu-id="270c3-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-571">taxnumber#</span></span>
  
<span data-ttu-id="270c3-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-572">taxnumber</span></span>
  
<span data-ttu-id="270c3-573">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-573">tax id</span></span>
  
<span data-ttu-id="270c3-574">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-574">taxid#</span></span>
  
<span data-ttu-id="270c3-575">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-575">tax identification number</span></span>
  
<span data-ttu-id="270c3-576">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-576">tax identification no.</span></span>
  
<span data-ttu-id="270c3-577">mokesčių-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-577">mokesčių id</span></span>
  
<span data-ttu-id="270c3-578">mokesčių Numeris</span><span class="sxs-lookup"><span data-stu-id="270c3-578">mokesčių numeris</span></span>
  
<span data-ttu-id="270c3-579">mokesčių identifikavimas Numeris</span><span class="sxs-lookup"><span data-stu-id="270c3-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="270c3-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="270c3-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="270c3-581">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-581">Format</span></span>

<span data-ttu-id="270c3-582">13 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-583">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-583">Pattern</span></span>

<span data-ttu-id="270c3-584">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="270c3-584">13 digits:</span></span>
  
-  <span data-ttu-id="270c3-585">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-585">11 digits</span></span> 
    
- <span data-ttu-id="270c3-586">Zwei Prüfziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-587">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-587">Checksum</span></span>

<span data-ttu-id="270c3-588">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-589">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-589">Definition</span></span>

<span data-ttu-id="270c3-590">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-591">Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-592">Ein Schlüsselwort `Keywords_luxemburg_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-593">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-594">Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-595">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="270c3-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-597">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-597">tax number</span></span>
  
<span data-ttu-id="270c3-598">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-598">tax no.</span></span>
  
<span data-ttu-id="270c3-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-599">taxno#</span></span>
  
<span data-ttu-id="270c3-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-600">taxnumber#</span></span>
  
<span data-ttu-id="270c3-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-601">taxnumber</span></span>
  
<span data-ttu-id="270c3-602">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-602">tax id</span></span>
  
<span data-ttu-id="270c3-603">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-603">taxid#</span></span>
  
<span data-ttu-id="270c3-604">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-604">tax identification number</span></span>
  
<span data-ttu-id="270c3-605">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-605">tax identification no.</span></span>
  
<span data-ttu-id="270c3-606">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-606">steuernummer</span></span>
  
<span data-ttu-id="270c3-607">Ingo-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-607">steuer id</span></span>
  
<span data-ttu-id="270c3-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="270c3-609">Malta</span><span class="sxs-lookup"><span data-stu-id="270c3-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="270c3-610">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-610">Format</span></span>

<span data-ttu-id="270c3-611">Für maltesische Staatsangehörige: 7 Ziffern und ein Buchstabe im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="270c3-612">Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-613">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-613">Pattern</span></span>

<span data-ttu-id="270c3-614">Maltesische Staatsangehörige: 7 Ziffern und ein Buchstaben</span><span class="sxs-lookup"><span data-stu-id="270c3-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="270c3-615">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="270c3-615">Seven digits</span></span> 
    
- <span data-ttu-id="270c3-616">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="270c3-617">Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="270c3-618">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="270c3-619">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-619">Checksum</span></span>

<span data-ttu-id="270c3-620">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-621">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-621">Definition</span></span>

<span data-ttu-id="270c3-622">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-623">Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-624">Ein Schlüsselwort `Keywords_malta_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-625">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-626">Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-627">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="270c3-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-629">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-629">tax number</span></span>
  
<span data-ttu-id="270c3-630">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-630">tax no.</span></span>
  
<span data-ttu-id="270c3-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-631">taxno#</span></span>
  
<span data-ttu-id="270c3-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-632">taxnumber#</span></span>
  
<span data-ttu-id="270c3-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-633">taxnumber</span></span>
  
<span data-ttu-id="270c3-634">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-634">tax id</span></span>
  
<span data-ttu-id="270c3-635">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-635">taxid#</span></span>
  
<span data-ttu-id="270c3-636">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-636">tax identification number</span></span>
  
<span data-ttu-id="270c3-637">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-637">tax identification no.</span></span>
  
<span data-ttu-id="270c3-638">numru tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="270c3-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="270c3-639">ID tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="270c3-639">id tat-taxxa</span></span>
  
<span data-ttu-id="270c3-640">numru ta ' identifikazzjoni tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="270c3-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="270c3-641">Niederlande</span><span class="sxs-lookup"><span data-stu-id="270c3-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="270c3-642">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-642">Format</span></span>

<span data-ttu-id="270c3-643">Neun Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-644">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-644">Pattern</span></span>

<span data-ttu-id="270c3-645">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="270c3-646">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-646">Checksum</span></span>

<span data-ttu-id="270c3-647">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-648">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-648">Definition</span></span>

<span data-ttu-id="270c3-649">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-650">Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-651">Ein Schlüsselwort `Keywords_netherlands_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-652">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-653">Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-654">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="270c3-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-656">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="270c3-657">niederländische Steueridentifikation</span><span class="sxs-lookup"><span data-stu-id="270c3-657">netherlands tax identification</span></span>
  
<span data-ttu-id="270c3-658">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="270c3-659">niederländische Steueridentifikation</span><span class="sxs-lookup"><span data-stu-id="270c3-659">netherland's tax identification</span></span>
  
<span data-ttu-id="270c3-660">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-660">tax identification number</span></span>
  
<span data-ttu-id="270c3-661">niederländische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-661">dutch tax id</span></span>
  
<span data-ttu-id="270c3-662">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-662">dutch tax identification number</span></span>
  
<span data-ttu-id="270c3-663">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-663">tax id</span></span>
  
<span data-ttu-id="270c3-664">Steuer-ID #</span><span class="sxs-lookup"><span data-stu-id="270c3-664">tax id#</span></span>
  
<span data-ttu-id="270c3-665">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-665">tax number</span></span>
  
<span data-ttu-id="270c3-666">Steuernummer #</span><span class="sxs-lookup"><span data-stu-id="270c3-666">tax no#</span></span>
  
<span data-ttu-id="270c3-667">Steuer #</span><span class="sxs-lookup"><span data-stu-id="270c3-667">tax#</span></span>
  
<span data-ttu-id="270c3-668">Zinn</span><span class="sxs-lookup"><span data-stu-id="270c3-668">tin</span></span>
  
<span data-ttu-id="270c3-669">Zinn #</span><span class="sxs-lookup"><span data-stu-id="270c3-669">tin#</span></span>
  
<span data-ttu-id="270c3-670">Niederlande Tin</span><span class="sxs-lookup"><span data-stu-id="270c3-670">netherlands tin</span></span>
  
<span data-ttu-id="270c3-671">niederländische Zinn</span><span class="sxs-lookup"><span data-stu-id="270c3-671">netherland's tin</span></span>
  
<span data-ttu-id="270c3-672">Nederlands belasten identificatienummer</span><span class="sxs-lookup"><span data-stu-id="270c3-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="270c3-673">identificatienummer van belasten</span><span class="sxs-lookup"><span data-stu-id="270c3-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="270c3-674">identificatienummer-Belastungen</span><span class="sxs-lookup"><span data-stu-id="270c3-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="270c3-675">Nederlands belasten identificatie</span><span class="sxs-lookup"><span data-stu-id="270c3-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="270c3-676">Nederlands Belasting ID Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="270c3-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="270c3-678">BTW Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-678">btw nummer</span></span>
  
<span data-ttu-id="270c3-679">Nederlandse belasten von identificatie</span><span class="sxs-lookup"><span data-stu-id="270c3-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="270c3-680">Polen</span><span class="sxs-lookup"><span data-stu-id="270c3-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="270c3-681">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-681">Format</span></span>

<span data-ttu-id="270c3-682">Elf Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-683">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-683">Pattern</span></span>

<span data-ttu-id="270c3-684">Elf Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-685">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-685">Checksum</span></span>

<span data-ttu-id="270c3-686">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-687">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-687">Definition</span></span>

<span data-ttu-id="270c3-688">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-689">Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-690">Ein Schlüsselwort `Keywords_poland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-691">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-692">Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-693">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="270c3-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-695">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-695">tax number</span></span>
  
<span data-ttu-id="270c3-696">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-696">tax no.</span></span>
  
<span data-ttu-id="270c3-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-697">taxno#</span></span>
  
<span data-ttu-id="270c3-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-698">taxnumber#</span></span>
  
<span data-ttu-id="270c3-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-699">taxnumber</span></span>
  
<span data-ttu-id="270c3-700">NIP</span><span class="sxs-lookup"><span data-stu-id="270c3-700">nip</span></span>
  
<span data-ttu-id="270c3-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="270c3-701">nip#</span></span>
  
<span data-ttu-id="270c3-702">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-702">tax id</span></span>
  
<span data-ttu-id="270c3-703">Steuer-ID #</span><span class="sxs-lookup"><span data-stu-id="270c3-703">tax id#</span></span>
  
<span data-ttu-id="270c3-704">NIP-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-704">nip id</span></span>
  
<span data-ttu-id="270c3-705">NIP-ID #</span><span class="sxs-lookup"><span data-stu-id="270c3-705">nip id#</span></span>
  
<span data-ttu-id="270c3-706">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-706">tax identification number</span></span>
  
<span data-ttu-id="270c3-707">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-707">tax identification no.</span></span>
  
<span data-ttu-id="270c3-708">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="270c3-708">vat number</span></span>
  
<span data-ttu-id="270c3-709">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="270c3-709">vat no.</span></span>
  
<span data-ttu-id="270c3-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="270c3-710">vatno#</span></span>
  
<span data-ttu-id="270c3-711">USt-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-711">vat id</span></span>
  
<span data-ttu-id="270c3-712">USt-ID #</span><span class="sxs-lookup"><span data-stu-id="270c3-712">vat id#</span></span>
  
<span data-ttu-id="270c3-713">Numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="270c3-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="270c3-714">Polski Numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="270c3-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="270c3-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="270c3-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="270c3-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="270c3-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="270c3-717">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-717">Format</span></span>

<span data-ttu-id="270c3-718">Neun Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-719">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-719">Pattern</span></span>

<span data-ttu-id="270c3-720">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-721">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-721">Checksum</span></span>

<span data-ttu-id="270c3-722">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-723">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-723">Definition</span></span>

<span data-ttu-id="270c3-724">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-725">Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-726">Ein Schlüsselwort `Keywords_portugal_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-727">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-728">Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-729">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="270c3-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-731">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-731">tax number</span></span>
  
<span data-ttu-id="270c3-732">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-732">tax no.</span></span>
  
<span data-ttu-id="270c3-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-733">taxno#</span></span>
  
<span data-ttu-id="270c3-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="270c3-734">taxnumber#</span></span>
  
<span data-ttu-id="270c3-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="270c3-735">taxnumber</span></span>
  
<span data-ttu-id="270c3-736">NIF</span><span class="sxs-lookup"><span data-stu-id="270c3-736">nif</span></span>
  
<span data-ttu-id="270c3-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="270c3-737">nif#</span></span>
  
<span data-ttu-id="270c3-738">numerisch-Geschäftsjahr</span><span class="sxs-lookup"><span data-stu-id="270c3-738">numero fiscal</span></span>
  
<span data-ttu-id="270c3-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="270c3-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="270c3-740">Rumänien</span><span class="sxs-lookup"><span data-stu-id="270c3-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="270c3-741">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-741">Format</span></span>

<span data-ttu-id="270c3-742">13 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-743">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-743">Pattern</span></span>

<span data-ttu-id="270c3-744">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-745">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-745">Checksum</span></span>

<span data-ttu-id="270c3-746">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-747">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-747">Definition</span></span>

<span data-ttu-id="270c3-748">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-749">Der reguläre Ausdruck `Regex_romania_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-750">Ein Schlüsselwort `Keywords_romania_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-751">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="270c3-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-753">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-753">tax id</span></span>
  
<span data-ttu-id="270c3-754">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-754">tax id number</span></span>
  
<span data-ttu-id="270c3-755">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-755">tax file no</span></span>
  
<span data-ttu-id="270c3-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="270c3-756">tax file number</span></span>
  
<span data-ttu-id="270c3-757">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-757">tax no</span></span>
  
<span data-ttu-id="270c3-758">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-758">tax number</span></span>
  
<span data-ttu-id="270c3-759">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-759">taxid#</span></span>
  
<span data-ttu-id="270c3-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-760">taxno#</span></span>
  
<span data-ttu-id="270c3-761">ID-UL taxei</span><span class="sxs-lookup"><span data-stu-id="270c3-761">id-ul taxei</span></span>
  
<span data-ttu-id="270c3-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="270c3-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="270c3-763">Slowakei</span><span class="sxs-lookup"><span data-stu-id="270c3-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="270c3-764">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-764">Format</span></span>

<span data-ttu-id="270c3-765">10 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-766">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-766">Pattern</span></span>

<span data-ttu-id="270c3-767">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-768">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-768">Checksum</span></span>

<span data-ttu-id="270c3-769">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="270c3-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-770">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-770">Definition</span></span>

<span data-ttu-id="270c3-771">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-772">Der reguläre Ausdruck `Regex_slovakia_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-773">Ein Schlüsselwort `Keywords_slovakia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-774">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="270c3-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-776">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-776">tax id</span></span>
  
<span data-ttu-id="270c3-777">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-777">tax id number</span></span>
  
<span data-ttu-id="270c3-778">Tin-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-778">tin id</span></span>
  
<span data-ttu-id="270c3-779">Tin Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-779">tin no</span></span>
  
<span data-ttu-id="270c3-780">Slowakische Tin-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-780">slovakian tin id</span></span>
  
<span data-ttu-id="270c3-781">Zinn</span><span class="sxs-lookup"><span data-stu-id="270c3-781">tin</span></span>
  
<span data-ttu-id="270c3-782">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-782">tax file no</span></span>
  
<span data-ttu-id="270c3-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="270c3-783">tax file number</span></span>
  
<span data-ttu-id="270c3-784">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-784">tax no</span></span>
  
<span data-ttu-id="270c3-785">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-785">tax number</span></span>
  
<span data-ttu-id="270c3-786">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-786">taxid#</span></span>
  
<span data-ttu-id="270c3-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-787">taxno#</span></span>
  
<span data-ttu-id="270c3-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="270c3-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="270c3-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="270c3-789">daňové číslo</span></span>
  
<span data-ttu-id="270c3-790">Daňové číslo SÚBORU</span><span class="sxs-lookup"><span data-stu-id="270c3-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="270c3-791">Slowenien</span><span class="sxs-lookup"><span data-stu-id="270c3-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="270c3-792">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-792">Format</span></span>

<span data-ttu-id="270c3-793">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-794">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-794">Pattern</span></span>

<span data-ttu-id="270c3-795">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-796">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-796">Checksum</span></span>

<span data-ttu-id="270c3-797">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-798">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-798">Definition</span></span>

<span data-ttu-id="270c3-799">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-800">Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-801">Ein Schlüsselwort `Keywords_slovenia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-802">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-803">Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-804">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="270c3-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-806">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-806">tax id</span></span>
  
<span data-ttu-id="270c3-807">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-807">tax id number</span></span>
  
<span data-ttu-id="270c3-808">Tin-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-808">tin id</span></span>
  
<span data-ttu-id="270c3-809">Tin Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-809">tin no</span></span>
  
<span data-ttu-id="270c3-810">slowenische Tin-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-810">slovenian tin id</span></span>
  
<span data-ttu-id="270c3-811">Zinn</span><span class="sxs-lookup"><span data-stu-id="270c3-811">tin</span></span>
  
<span data-ttu-id="270c3-812">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-812">tax file no</span></span>
  
<span data-ttu-id="270c3-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="270c3-813">tax file number</span></span>
  
<span data-ttu-id="270c3-814">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-814">tax no</span></span>
  
<span data-ttu-id="270c3-815">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-815">tax number</span></span>
  
<span data-ttu-id="270c3-816">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-816">taxid#</span></span>
  
<span data-ttu-id="270c3-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-817">taxno#</span></span>
  
<span data-ttu-id="270c3-818">identifikacijska številka beim Davka</span><span class="sxs-lookup"><span data-stu-id="270c3-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="270c3-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="270c3-819">davčna številka</span></span>
  
<span data-ttu-id="270c3-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="270c3-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="270c3-821">Spanien</span><span class="sxs-lookup"><span data-stu-id="270c3-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="270c3-822">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-822">Format</span></span>

<span data-ttu-id="270c3-823">Sieben oder acht Ziffern und ein oder zwei Buchstaben im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-824">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-824">Pattern</span></span>

<span data-ttu-id="270c3-825">Spanisch natürliche Personen mit einem nationalen spanischen Identitätsausweis:</span><span class="sxs-lookup"><span data-stu-id="270c3-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="270c3-826">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-826">Eight digits</span></span> 
    
- <span data-ttu-id="270c3-827">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="270c3-828">Nicht-residente Spanier ohne einen nationalen Identitätsausweis in Spanien</span><span class="sxs-lookup"><span data-stu-id="270c3-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="270c3-829">Ein Großbuchstabe "L" (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="270c3-830">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="270c3-830">Seven digits</span></span>
    
- <span data-ttu-id="270c3-831">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="270c3-832">Ansässige Spanier unter 14 Jahren ohne einen nationalen spanischen Identitätsausweis:</span><span class="sxs-lookup"><span data-stu-id="270c3-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="270c3-833">Ein Großbuchstabe "K" (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="270c3-834">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="270c3-834">Seven digits</span></span> 
    
- <span data-ttu-id="270c3-835">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="270c3-836">Ausländer mit Identifikationsnummer eines Ausländers</span><span class="sxs-lookup"><span data-stu-id="270c3-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="270c3-837">Ein Großbuchstabe mit "X", "Y" oder "Z" (Groß-/Kleinschreibung wird beachtet)</span><span class="sxs-lookup"><span data-stu-id="270c3-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="270c3-838">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="270c3-838">Seven digits</span></span>
    
- <span data-ttu-id="270c3-839">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="270c3-840">Ausländer ohne Identifikationsnummer eines Ausländers</span><span class="sxs-lookup"><span data-stu-id="270c3-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="270c3-841">Ein Großbuchstabe, der "M" ist (Groß-/Kleinschreibung beachten)</span><span class="sxs-lookup"><span data-stu-id="270c3-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="270c3-842">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="270c3-842">Seven digits</span></span>
    
- <span data-ttu-id="270c3-843">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="270c3-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="270c3-844">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-844">Checksum</span></span>

<span data-ttu-id="270c3-845">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-846">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-846">Definition</span></span>

<span data-ttu-id="270c3-847">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-848">Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-849">Ein Schlüsselwort `Keywords_spain_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-850">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-851">Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-852">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="270c3-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-854">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-854">tax id</span></span>
  
<span data-ttu-id="270c3-855">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-855">tax id number</span></span>
  
<span data-ttu-id="270c3-856">CIF-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-856">cif id</span></span>
  
<span data-ttu-id="270c3-857">CIF Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-857">cif no</span></span>
  
<span data-ttu-id="270c3-858">spanische CIF-ID</span><span class="sxs-lookup"><span data-stu-id="270c3-858">spanish cif id</span></span>
  
<span data-ttu-id="270c3-859">CIF</span><span class="sxs-lookup"><span data-stu-id="270c3-859">cif</span></span>
  
<span data-ttu-id="270c3-860">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-860">tax file no</span></span>
  
<span data-ttu-id="270c3-861">spanische CIF-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-861">spanish cif number</span></span>
  
<span data-ttu-id="270c3-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="270c3-862">tax file number</span></span>
  
<span data-ttu-id="270c3-863">Spanisch CIF Nein</span><span class="sxs-lookup"><span data-stu-id="270c3-863">spanish cif no</span></span>
  
<span data-ttu-id="270c3-864">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-864">tax no</span></span>
  
<span data-ttu-id="270c3-865">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="270c3-865">tax number</span></span>
  
<span data-ttu-id="270c3-866">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-866">taxid#</span></span>
  
<span data-ttu-id="270c3-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="270c3-867">taxno#</span></span>
  
<span data-ttu-id="270c3-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="270c3-868">cifid#</span></span>
  
<span data-ttu-id="270c3-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="270c3-869">spanishcifid#</span></span>
  
<span data-ttu-id="270c3-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="270c3-870">spanishcifno#</span></span>
  
<span data-ttu-id="270c3-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="270c3-871">número de contribuyente</span></span>
  
<span data-ttu-id="270c3-872">número de Impuesto Corporativo</span><span class="sxs-lookup"><span data-stu-id="270c3-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="270c3-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="270c3-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="270c3-874">CIF-número</span><span class="sxs-lookup"><span data-stu-id="270c3-874">cif número</span></span>
  
<span data-ttu-id="270c3-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="270c3-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="270c3-876">Schweden</span><span class="sxs-lookup"><span data-stu-id="270c3-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="270c3-877">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-877">Format</span></span>

<span data-ttu-id="270c3-878">Zehn Ziffern und ein Symbol im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-879">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-879">Pattern</span></span>

<span data-ttu-id="270c3-880">Zehn Ziffern und ein Symbol:</span><span class="sxs-lookup"><span data-stu-id="270c3-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="270c3-881">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="270c3-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="270c3-882">Pluszeichen, Minuszeichen oder Backslash</span><span class="sxs-lookup"><span data-stu-id="270c3-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="270c3-883">Drei Ziffern, die die Identifikationsnummer eindeutig machen:</span><span class="sxs-lookup"><span data-stu-id="270c3-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="270c3-884">Für Zahlen, die vor 1990 ausgegeben wurden, identifizieren die siebte und die achte Ziffer den Geburts Kreis oder den in der fremde geborenen Personen.</span><span class="sxs-lookup"><span data-stu-id="270c3-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="270c3-885">Die Ziffer in der neunten Position gibt das Geschlecht entweder ungerade für männliche oder sogar für weiblich an.</span><span class="sxs-lookup"><span data-stu-id="270c3-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="270c3-886">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="270c3-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="270c3-887">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-887">Checksum</span></span>

<span data-ttu-id="270c3-888">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-889">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-889">Definition</span></span>

<span data-ttu-id="270c3-890">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-891">Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-892">Ein Schlüsselwort `Keywords_sweden_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="270c3-893">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-894">Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-895">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="270c3-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-897">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-897">tax id</span></span>
  
<span data-ttu-id="270c3-898">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="270c3-898">tax id no.</span></span>
  
<span data-ttu-id="270c3-899">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-899">tax id number</span></span>
  
<span data-ttu-id="270c3-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="270c3-900">tax identification</span></span>
  
<span data-ttu-id="270c3-901">Steueridentifikation #</span><span class="sxs-lookup"><span data-stu-id="270c3-901">tax identification#</span></span>
  
<span data-ttu-id="270c3-902">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-902">tax no.</span></span>
  
<span data-ttu-id="270c3-903">Steuer #</span><span class="sxs-lookup"><span data-stu-id="270c3-903">tax#</span></span>
  
<span data-ttu-id="270c3-904">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-904">taxid#</span></span>
  
<span data-ttu-id="270c3-905">Steuerdatei</span><span class="sxs-lookup"><span data-stu-id="270c3-905">tax file</span></span>
  
<span data-ttu-id="270c3-906">Steuerdatei-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-906">tax file no.</span></span>
  
<span data-ttu-id="270c3-907">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-907">personal id number</span></span>
  
<span data-ttu-id="270c3-908">Skate ID Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-908">skatt id nummer</span></span>
  
<span data-ttu-id="270c3-909">skatt Identifikation</span><span class="sxs-lookup"><span data-stu-id="270c3-909">skatt identifikation</span></span>
  
<span data-ttu-id="270c3-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="270c3-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="270c3-911">UK</span><span class="sxs-lookup"><span data-stu-id="270c3-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="270c3-912">Format</span><span class="sxs-lookup"><span data-stu-id="270c3-912">Format</span></span>

<span data-ttu-id="270c3-913">Unique Steuerzahler Referenz (UTR): 10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="270c3-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="270c3-914">Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="270c3-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="270c3-915">Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="270c3-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="270c3-916">Muster</span><span class="sxs-lookup"><span data-stu-id="270c3-916">Pattern</span></span>

<span data-ttu-id="270c3-917">Unique Steuerzahler Referenz (UTR): 10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="270c3-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="270c3-918">Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="270c3-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="270c3-919">Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="270c3-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="270c3-920">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="270c3-920">Checksum</span></span>

<span data-ttu-id="270c3-921">Ja</span><span class="sxs-lookup"><span data-stu-id="270c3-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="270c3-922">Definition</span><span class="sxs-lookup"><span data-stu-id="270c3-922">Definition</span></span>

<span data-ttu-id="270c3-923">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="270c3-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="270c3-924">Die- `Func_uk_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="270c3-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="270c3-925">Ein Schlüsselwort `Keywords_uk_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="270c3-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="270c3-926">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="270c3-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="270c3-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="270c3-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="270c3-928">tax id</span><span class="sxs-lookup"><span data-stu-id="270c3-928">tax id</span></span>
  
<span data-ttu-id="270c3-929">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="270c3-929">tax id no.</span></span>
  
<span data-ttu-id="270c3-930">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="270c3-930">tax id number</span></span>
  
<span data-ttu-id="270c3-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="270c3-931">tax identification</span></span>
  
<span data-ttu-id="270c3-932">Steueridentifikation #</span><span class="sxs-lookup"><span data-stu-id="270c3-932">tax identification#</span></span>
  
<span data-ttu-id="270c3-933">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-933">tax no.</span></span>
  
<span data-ttu-id="270c3-934">Steuer #</span><span class="sxs-lookup"><span data-stu-id="270c3-934">tax#</span></span>
  
<span data-ttu-id="270c3-935">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="270c3-935">taxid#</span></span>
  
<span data-ttu-id="270c3-936">Steuerdatei</span><span class="sxs-lookup"><span data-stu-id="270c3-936">tax file</span></span>
  
<span data-ttu-id="270c3-937">Steuerdatei-Nr.</span><span class="sxs-lookup"><span data-stu-id="270c3-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="270c3-938">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="270c3-938">See also</span></span>

[<span data-ttu-id="270c3-939">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="270c3-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

