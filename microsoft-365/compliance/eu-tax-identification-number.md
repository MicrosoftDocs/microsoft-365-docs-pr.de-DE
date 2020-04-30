---
title: EU-Steueridentifikationsnummer
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn der vertrauliche Informationstyp "EU-Steueridentifikationsnummer" erkannt wird. Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.
ms.openlocfilehash: 5f779974266045d7099b599700c7168162d9d81e
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938671"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="482d0-104">EU-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-104">EU Tax Identification Number</span></span>

<span data-ttu-id="482d0-105">In diesem Thema wird gezeigt, was eine DLP-Richtlinie (Data Loss Prevention) sucht, wenn Sie den Typ der vertraulichen Informationen für die EU-Steueridentifikationsnummer (TIN) erkennt.</span><span class="sxs-lookup"><span data-stu-id="482d0-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="482d0-106">Dieser Typ vertraulicher Informationen definiert unterschiedliche Muster, Stichwörter und andere Beweise für jedes Land.</span><span class="sxs-lookup"><span data-stu-id="482d0-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="482d0-107">Österreich</span><span class="sxs-lookup"><span data-stu-id="482d0-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="482d0-108">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-108">Format</span></span>

<span data-ttu-id="482d0-109">Neun Ziffern mit optionalem Bindestrich und Schrägstrich</span><span class="sxs-lookup"><span data-stu-id="482d0-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-110">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-110">Pattern</span></span>

<span data-ttu-id="482d0-111">Neun Ziffern mit optionalem Bindestrich und Schrägstrich:</span><span class="sxs-lookup"><span data-stu-id="482d0-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="482d0-112">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-112">Two digits</span></span> 
    
- <span data-ttu-id="482d0-113">Ein Bindestrich (optional)</span><span class="sxs-lookup"><span data-stu-id="482d0-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="482d0-114">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-114">Three digits</span></span>
    
- <span data-ttu-id="482d0-115">Ein Schrägstrich (optional)</span><span class="sxs-lookup"><span data-stu-id="482d0-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="482d0-116">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-117">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-117">Checksum</span></span>

<span data-ttu-id="482d0-118">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-119">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-119">Definition</span></span>

<span data-ttu-id="482d0-120">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-121">Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-122">Ein Schlüsselwort `Keywords_austria_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-123">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-124">Die- `Func_austria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-125">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="482d0-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-127">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-127">tax number</span></span>
  
<span data-ttu-id="482d0-128">number</span><span class="sxs-lookup"><span data-stu-id="482d0-128">number</span></span>
  
<span data-ttu-id="482d0-129">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-129">tax registration number</span></span>
  
<span data-ttu-id="482d0-130">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-130">tax id</span></span>
  
<span data-ttu-id="482d0-131">St.Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-131">st.nr.</span></span>
  
<span data-ttu-id="482d0-132">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="482d0-133">Belgien</span><span class="sxs-lookup"><span data-stu-id="482d0-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="482d0-134">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-134">Format</span></span>

<span data-ttu-id="482d0-135">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-136">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-136">Pattern</span></span>

<span data-ttu-id="482d0-137">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="482d0-137">11 digits:</span></span>
  
- <span data-ttu-id="482d0-138">Zwei Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-138">Two digits</span></span>
    
- <span data-ttu-id="482d0-139">A "0" oder "1"</span><span class="sxs-lookup"><span data-stu-id="482d0-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="482d0-140">Eine Ziffer</span><span class="sxs-lookup"><span data-stu-id="482d0-140">One digit</span></span>
    
- <span data-ttu-id="482d0-141">A "0" oder "1" oder "2" oder "3"</span><span class="sxs-lookup"><span data-stu-id="482d0-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="482d0-142">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-143">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-143">Checksum</span></span>

<span data-ttu-id="482d0-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-145">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-145">Definition</span></span>

<span data-ttu-id="482d0-146">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-147">Der reguläre Ausdruck `Regex_belgium_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-148">Ein Schlüsselwort `Keywords_belgium_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="482d0-149">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="482d0-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-151">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-151">tax number</span></span>
  
<span data-ttu-id="482d0-152">nationale Registrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-152">national registration number</span></span>
  
<span data-ttu-id="482d0-153">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-153">tax registration number</span></span>
  
<span data-ttu-id="482d0-154">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-154">tax id</span></span>
  
<span data-ttu-id="482d0-155">NIF</span><span class="sxs-lookup"><span data-stu-id="482d0-155">nif</span></span>
  
<span data-ttu-id="482d0-156">NIF #</span><span class="sxs-lookup"><span data-stu-id="482d0-156">nif#</span></span>
  
<span data-ttu-id="482d0-157">Numéro de Registre National</span><span class="sxs-lookup"><span data-stu-id="482d0-157">numéro de registre national</span></span>
  
<span data-ttu-id="482d0-158">Numéro d'identification Fiscale</span><span class="sxs-lookup"><span data-stu-id="482d0-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="482d0-159">Bulgarien</span><span class="sxs-lookup"><span data-stu-id="482d0-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="482d0-160">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-160">Format</span></span>

<span data-ttu-id="482d0-161">Zehn Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-162">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-162">Pattern</span></span>

<span data-ttu-id="482d0-163">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-164">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-164">Checksum</span></span>

<span data-ttu-id="482d0-165">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-166">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-166">Definition</span></span>

<span data-ttu-id="482d0-167">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-168">Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-169">Ein Schlüsselwort `Keywords_bulgaria_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-170">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-171">Die- `Func_bulgaria_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-172">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="482d0-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-174">BUCN</span><span class="sxs-lookup"><span data-stu-id="482d0-174">bucn</span></span>
  
<span data-ttu-id="482d0-175">einheitliche Zivil Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-175">uniform civil number</span></span>
  
<span data-ttu-id="482d0-176">BUCN #</span><span class="sxs-lookup"><span data-stu-id="482d0-176">bucn#</span></span>
  
<span data-ttu-id="482d0-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="482d0-178">Uniform Civil ID</span><span class="sxs-lookup"><span data-stu-id="482d0-178">uniform civil id</span></span>
  
<span data-ttu-id="482d0-179">Uniform Civil Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-179">uniform civil no</span></span>
  
<span data-ttu-id="482d0-180">EGN</span><span class="sxs-lookup"><span data-stu-id="482d0-180">egn</span></span>
  
<span data-ttu-id="482d0-181">Bulgarische Uniform Civil Number</span><span class="sxs-lookup"><span data-stu-id="482d0-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="482d0-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="482d0-182">uniformcivilno#</span></span>
  
<span data-ttu-id="482d0-183">EGN #</span><span class="sxs-lookup"><span data-stu-id="482d0-183">egn#</span></span>
  
<span data-ttu-id="482d0-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="482d0-184">униформ граждански номер</span></span>
  
<span data-ttu-id="482d0-185">униформ-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-185">униформ id</span></span>
  
<span data-ttu-id="482d0-186">униформ-граждански-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-186">униформ граждански id</span></span>
  
<span data-ttu-id="482d0-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="482d0-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="482d0-188">Kroatien</span><span class="sxs-lookup"><span data-stu-id="482d0-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="482d0-189">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-189">Format</span></span>

<span data-ttu-id="482d0-190">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-191">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-191">Pattern</span></span>

<span data-ttu-id="482d0-192">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="482d0-192">11 digits:</span></span>
  
- <span data-ttu-id="482d0-193">Zehn Ziffern, nach dem Zufallsprinzip ausgewählt</span><span class="sxs-lookup"><span data-stu-id="482d0-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="482d0-194">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="482d0-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-195">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-195">Checksum</span></span>

<span data-ttu-id="482d0-196">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-197">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-197">Definition</span></span>

<span data-ttu-id="482d0-198">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-199">Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-200">Ein Schlüsselwort `Keywords_croatia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-201">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-202">Die- `Func_croatia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-203">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="482d0-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-205">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-205">tax number</span></span>
  
<span data-ttu-id="482d0-206">Steuer</span><span class="sxs-lookup"><span data-stu-id="482d0-206">tax</span></span>
  
<span data-ttu-id="482d0-207">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-207">tax id</span></span>
  
<span data-ttu-id="482d0-208">oid</span><span class="sxs-lookup"><span data-stu-id="482d0-208">oid</span></span>
  
<span data-ttu-id="482d0-209">OID #</span><span class="sxs-lookup"><span data-stu-id="482d0-209">oid#</span></span>
  
<span data-ttu-id="482d0-210">porezni Broj</span><span class="sxs-lookup"><span data-stu-id="482d0-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="482d0-211">Zypern</span><span class="sxs-lookup"><span data-stu-id="482d0-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="482d0-212">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-212">Format</span></span>

<span data-ttu-id="482d0-213">Acht Ziffern und ein Buchstabe im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-214">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-214">Pattern</span></span>

<span data-ttu-id="482d0-215">Acht Ziffern und ein Buchstabe:</span><span class="sxs-lookup"><span data-stu-id="482d0-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="482d0-216">A "0"</span><span class="sxs-lookup"><span data-stu-id="482d0-216">A "0"</span></span> 
    
- <span data-ttu-id="482d0-217">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="482d0-217">Seven digits</span></span>
    
- <span data-ttu-id="482d0-218">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-219">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-219">Checksum</span></span>

<span data-ttu-id="482d0-220">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-221">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-221">Definition</span></span>

<span data-ttu-id="482d0-222">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-223">Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-224">Ein Schlüsselwort `Keywords_cyprus_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-225">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-226">Die- `Func_cyprus_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-227">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="482d0-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-229">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-229">tax number</span></span>
  
<span data-ttu-id="482d0-230">Steuer</span><span class="sxs-lookup"><span data-stu-id="482d0-230">tax</span></span>
  
<span data-ttu-id="482d0-231">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-231">tax id</span></span>
  
<span data-ttu-id="482d0-232">Steuer Identifikationscode</span><span class="sxs-lookup"><span data-stu-id="482d0-232">tax identification code</span></span>
  
<span data-ttu-id="482d0-233">TIC</span><span class="sxs-lookup"><span data-stu-id="482d0-233">tic</span></span>
  
<span data-ttu-id="482d0-234">TIC #</span><span class="sxs-lookup"><span data-stu-id="482d0-234">tic#</span></span>
  
<span data-ttu-id="482d0-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="482d0-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="482d0-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="482d0-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="482d0-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="482d0-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="482d0-238">Tschechien</span><span class="sxs-lookup"><span data-stu-id="482d0-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="482d0-239">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-239">Format</span></span>

<span data-ttu-id="482d0-240">Neun oder zehn Ziffern mit einem optionalen Backslash</span><span class="sxs-lookup"><span data-stu-id="482d0-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-241">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-241">Pattern</span></span>

<span data-ttu-id="482d0-242">Neun oder zehn Ziffern mit einem optionalen backslashl:</span><span class="sxs-lookup"><span data-stu-id="482d0-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="482d0-243">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-243">Six digits</span></span> 
    
- <span data-ttu-id="482d0-244">Ein Backslash (optional)</span><span class="sxs-lookup"><span data-stu-id="482d0-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="482d0-245">Drei oder vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-246">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-246">Checksum</span></span>

<span data-ttu-id="482d0-247">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-248">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-248">Definition</span></span>

<span data-ttu-id="482d0-249">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-250">Der reguläre Ausdruck `Regex_czech_republic_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-251">Ein Schlüsselwort `Keywords_czech_republic_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="482d0-252">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="482d0-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-254">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-254">tax number</span></span>
  
<span data-ttu-id="482d0-255">Steuer</span><span class="sxs-lookup"><span data-stu-id="482d0-255">tax</span></span>
  
<span data-ttu-id="482d0-256">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-256">tax id</span></span>
  
<span data-ttu-id="482d0-257">persönliche Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-257">personal number</span></span>
  
<span data-ttu-id="482d0-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="482d0-258">daňové číslo</span></span>
  
<span data-ttu-id="482d0-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="482d0-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="482d0-260">Dänemark</span><span class="sxs-lookup"><span data-stu-id="482d0-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="482d0-261">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-261">Format</span></span>

<span data-ttu-id="482d0-262">Zehn Ziffern mit einem Bindestrich</span><span class="sxs-lookup"><span data-stu-id="482d0-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-263">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-263">Pattern</span></span>

<span data-ttu-id="482d0-264">Zehn Ziffern mit einem Bindestrich:</span><span class="sxs-lookup"><span data-stu-id="482d0-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="482d0-265">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="482d0-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="482d0-266">Ein Bindestrich </span><span class="sxs-lookup"><span data-stu-id="482d0-266">A hyphen</span></span>
    
- <span data-ttu-id="482d0-267">Vier Ziffern, die einer Sequenznummer entsprechen, wobei die erste Ziffer dem Jahrhundert der Geburt entspricht und die letzte Ziffer dem Geschlecht der Person entspricht (ungerade für männliche und sogar für weiblich)</span><span class="sxs-lookup"><span data-stu-id="482d0-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-268">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-268">Checksum</span></span>

<span data-ttu-id="482d0-269">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-270">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-270">Definition</span></span>

<span data-ttu-id="482d0-271">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-272">Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-273">Ein Schlüsselwort `Keywords_denmark_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-274">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-275">Die- `Func_denmark_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-276">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="482d0-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-278">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-278">tax number</span></span>
  
<span data-ttu-id="482d0-279">Steuer</span><span class="sxs-lookup"><span data-stu-id="482d0-279">tax</span></span>
  
<span data-ttu-id="482d0-280">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-280">tax id</span></span>
  
<span data-ttu-id="482d0-281">CPR-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-281">cpr number</span></span>
  
<span data-ttu-id="482d0-282">CPR #</span><span class="sxs-lookup"><span data-stu-id="482d0-282">cpr#</span></span>
  
<span data-ttu-id="482d0-283">Skate Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-283">skat nummer</span></span>
  
<span data-ttu-id="482d0-284">Skat-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="482d0-285">Estland</span><span class="sxs-lookup"><span data-stu-id="482d0-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="482d0-286">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-286">Format</span></span>

<span data-ttu-id="482d0-287">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-288">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-288">Pattern</span></span>

<span data-ttu-id="482d0-289">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="482d0-289">11 digits:</span></span>
  
-  <span data-ttu-id="482d0-290">Eine Ziffer, die dem Geschlecht und dem Jahrhundert der Geburt entspricht, wobei eine ungerade Zahl männlich ist und die gerade Zahl weiblich wie folgt angibt: 1, 2 für das 19. Jahrhundert; 3,4 für das 20. Jahrhundert; und 5, 6 für das 21. Jahrhundert</span><span class="sxs-lookup"><span data-stu-id="482d0-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="482d0-291">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="482d0-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="482d0-292">Drei Ziffern, die einer Seriennummer entsprechen, die Personen trennt, die am gleichen Datum geboren wurden</span><span class="sxs-lookup"><span data-stu-id="482d0-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="482d0-293">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="482d0-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-294">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-294">Checksum</span></span>

<span data-ttu-id="482d0-295">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-296">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-296">Definition</span></span>

<span data-ttu-id="482d0-297">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-298">Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-299">Ein Schlüsselwort `Keywords_estonia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-300">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-301">Die- `Func_estonia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-302">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="482d0-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-304">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-304">tax number</span></span>
  
<span data-ttu-id="482d0-305">Steuer</span><span class="sxs-lookup"><span data-stu-id="482d0-305">tax</span></span>
  
<span data-ttu-id="482d0-306">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-306">tax id</span></span>
  
<span data-ttu-id="482d0-307">persönlicher Code</span><span class="sxs-lookup"><span data-stu-id="482d0-307">personal code</span></span>
  
<span data-ttu-id="482d0-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="482d0-308">maksunumber</span></span>
  
<span data-ttu-id="482d0-309">maksu-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-309">maksu id</span></span>
  
<span data-ttu-id="482d0-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="482d0-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="482d0-311">Finnland</span><span class="sxs-lookup"><span data-stu-id="482d0-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="482d0-312">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-312">Format</span></span>

<span data-ttu-id="482d0-313">Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-314">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-314">Pattern</span></span>

<span data-ttu-id="482d0-315">Eine Kombination aus 11 Zeichen aus Ziffern, Buchstaben und Plus-und Minuszeichen:</span><span class="sxs-lookup"><span data-stu-id="482d0-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="482d0-316">Sechs Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-316">Six digits</span></span>
    
- <span data-ttu-id="482d0-317">Eine der folgenden Optionen: ein Pluszeichen, ein Minuszeichen oder der Buchstabe "a" (Groß-/Kleinschreibung nicht beachtet), wobei das Pluszeichen zwischen 1800-1899 geboren wird, das Minuszeichen zwischen 1900-1999 und "a" geboren ist 2000 und nach</span><span class="sxs-lookup"><span data-stu-id="482d0-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="482d0-318">Drei Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-318">Three digits</span></span>
    
- <span data-ttu-id="482d0-319">Ein Buchstabe oder eine Zahl</span><span class="sxs-lookup"><span data-stu-id="482d0-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-320">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-320">Checksum</span></span>

<span data-ttu-id="482d0-321">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-322">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-322">Definition</span></span>

<span data-ttu-id="482d0-323">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-324">Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-325">Ein Schlüsselwort `Keywords_finland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-326">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-327">Die- `Func_finland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-328">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="482d0-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-330">identification number</span><span class="sxs-lookup"><span data-stu-id="482d0-330">identification number</span></span>
  
<span data-ttu-id="482d0-331">persönliche ID</span><span class="sxs-lookup"><span data-stu-id="482d0-331">personal id</span></span>
  
<span data-ttu-id="482d0-332">Identitätsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-332">identity number</span></span>
  
<span data-ttu-id="482d0-333">Finnische Nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-333">finnish national id number</span></span>
  
<span data-ttu-id="482d0-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-334">personalidnumber#</span></span>
  
<span data-ttu-id="482d0-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="482d0-335">national identification number</span></span>
  
<span data-ttu-id="482d0-336">ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-336">id number</span></span>
  
<span data-ttu-id="482d0-337">nationale ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-337">national id no.</span></span>
  
<span data-ttu-id="482d0-338">nationale ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-338">national id number</span></span>
  
<span data-ttu-id="482d0-339">ID Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-339">id no</span></span>
  
<span data-ttu-id="482d0-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="482d0-340">tunnistenumero</span></span>
  
<span data-ttu-id="482d0-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="482d0-341">henkilötunnus</span></span>
  
<span data-ttu-id="482d0-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="482d0-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="482d0-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="482d0-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="482d0-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="482d0-344">identiteetti numero</span></span>
  
<span data-ttu-id="482d0-345">Suomen der Kok henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="482d0-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="482d0-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="482d0-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="482d0-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="482d0-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="482d0-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="482d0-348">tunnusnumero</span></span>
  
<span data-ttu-id="482d0-349">der Kok tunnus numero</span><span class="sxs-lookup"><span data-stu-id="482d0-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="482d0-350">Frankreich</span><span class="sxs-lookup"><span data-stu-id="482d0-350">France</span></span>

### <a name="format"></a><span data-ttu-id="482d0-351">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-351">Format</span></span>

<span data-ttu-id="482d0-352">13 Ziffern für einzelne Personen und neun Ziffern für Entitäten</span><span class="sxs-lookup"><span data-stu-id="482d0-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-353">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-353">Pattern</span></span>

<span data-ttu-id="482d0-354">13 Ziffern für einzelne Personen:</span><span class="sxs-lookup"><span data-stu-id="482d0-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="482d0-355">Eine Ziffer, die 0, 1, 2 oder 3 sein muss</span><span class="sxs-lookup"><span data-stu-id="482d0-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="482d0-356">12 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-356">12 digits</span></span>
    
<span data-ttu-id="482d0-357">Neun Ziffern für Entitäten</span><span class="sxs-lookup"><span data-stu-id="482d0-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-358">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-358">Checksum</span></span>

<span data-ttu-id="482d0-359">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-360">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-360">Definition</span></span>

<span data-ttu-id="482d0-361">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-362">Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-363">Ein Schlüsselwort `Keywords_france_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-364">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-365">Die- `Func_france_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-366">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="482d0-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-368">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-368">tax identification number</span></span>
  
<span data-ttu-id="482d0-369">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-369">tax number</span></span>
  
<span data-ttu-id="482d0-370">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-370">tax id</span></span>
  
<span data-ttu-id="482d0-371">Numéro d'identification Fiscale</span><span class="sxs-lookup"><span data-stu-id="482d0-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="482d0-372">Deutschland</span><span class="sxs-lookup"><span data-stu-id="482d0-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="482d0-373">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-373">Format</span></span>

<span data-ttu-id="482d0-374">11 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-375">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-375">Pattern</span></span>

<span data-ttu-id="482d0-376">11 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="482d0-376">11 digits :</span></span>
  
-  <span data-ttu-id="482d0-377">Zehn Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-377">Ten digits</span></span> 
    
- <span data-ttu-id="482d0-378">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="482d0-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-379">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-379">Checksum</span></span>

<span data-ttu-id="482d0-380">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-381">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-381">Definition</span></span>

<span data-ttu-id="482d0-382">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-383">Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-384">Ein Schlüsselwort `Keywords_germany_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-385">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-386">Die- `Func_germany_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-387">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="482d0-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-389">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-389">tax number</span></span>
  
<span data-ttu-id="482d0-390">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-390">tax no.</span></span>
  
<span data-ttu-id="482d0-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-391">taxno#</span></span>
  
<span data-ttu-id="482d0-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-392">taxnumber#</span></span>
  
<span data-ttu-id="482d0-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-393">taxnumber</span></span>
  
<span data-ttu-id="482d0-394">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-394">tax id</span></span>
  
<span data-ttu-id="482d0-395">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-395">taxid#</span></span>
  
<span data-ttu-id="482d0-396">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-396">tax identification number</span></span>
  
<span data-ttu-id="482d0-397">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-397">tax identification no.</span></span>
  
<span data-ttu-id="482d0-398">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-398">steuernummer</span></span>
  
<span data-ttu-id="482d0-399">Ingo-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-399">steuer id</span></span>
  
<span data-ttu-id="482d0-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="482d0-401">Griechenland</span><span class="sxs-lookup"><span data-stu-id="482d0-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="482d0-402">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-402">Format</span></span>

<span data-ttu-id="482d0-403">Neun Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-404">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-404">Pattern</span></span>

<span data-ttu-id="482d0-405">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-406">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-406">Checksum</span></span>

<span data-ttu-id="482d0-407">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-408">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-408">Definition</span></span>

<span data-ttu-id="482d0-409">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-410">Der reguläre Ausdruck `Regex_greece_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-411">Ein Schlüsselwort `Keywords_greece_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="482d0-412">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="482d0-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-414">AFM</span><span class="sxs-lookup"><span data-stu-id="482d0-414">afm</span></span>
  
<span data-ttu-id="482d0-415">Zinn</span><span class="sxs-lookup"><span data-stu-id="482d0-415">tin</span></span>
  
<span data-ttu-id="482d0-416">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="482d0-416">tax id no.</span></span>
  
<span data-ttu-id="482d0-417">Steuernummer Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-417">tax id no</span></span>
  
<span data-ttu-id="482d0-418">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-418">tax identification number</span></span>
  
<span data-ttu-id="482d0-419">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-419">tax registry number</span></span>
  
<span data-ttu-id="482d0-420">Steuerregistrierungsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-420">tax registry no.</span></span>
  
<span data-ttu-id="482d0-421">AFM #</span><span class="sxs-lookup"><span data-stu-id="482d0-421">afm#</span></span>
  
<span data-ttu-id="482d0-422">Zinn #</span><span class="sxs-lookup"><span data-stu-id="482d0-422">tin#</span></span>
  
<span data-ttu-id="482d0-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="482d0-423">taxidno#</span></span>
  
<span data-ttu-id="482d0-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="482d0-424">taxregistryno#</span></span>
  
<span data-ttu-id="482d0-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="482d0-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="482d0-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="482d0-426">aφμ</span></span>
  
<span data-ttu-id="482d0-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="482d0-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="482d0-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="482d0-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="482d0-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="482d0-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="482d0-430">Ungarn</span><span class="sxs-lookup"><span data-stu-id="482d0-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="482d0-431">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-431">Format</span></span>

<span data-ttu-id="482d0-432">Zehn Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-433">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-433">Pattern</span></span>

<span data-ttu-id="482d0-434">Zehn Ziffern:</span><span class="sxs-lookup"><span data-stu-id="482d0-434">Ten digits:</span></span>
  
-  <span data-ttu-id="482d0-435">Eine Ziffer, die "8" sein muss</span><span class="sxs-lookup"><span data-stu-id="482d0-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="482d0-436">Fünf Ziffern, die der Anzahl von Tagen zwischen dem Datum 01/01/1867 und dem Geburtsdatum der einzelnen Personen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="482d0-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="482d0-437">Drei Ziffern, die der durch Zufall generierten Zahl entsprechen, um Personen zu unterscheiden, die am selben Tag geboren wurden</span><span class="sxs-lookup"><span data-stu-id="482d0-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="482d0-438">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="482d0-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-439">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-439">Checksum</span></span>

<span data-ttu-id="482d0-440">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-441">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-441">Definition</span></span>

<span data-ttu-id="482d0-442">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-443">Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-444">Ein Schlüsselwort `Keywords_hungary_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-445">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-446">Die- `Func_hungary_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-447">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="482d0-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-449">ungarische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="482d0-450">Ungarisch Zinn</span><span class="sxs-lookup"><span data-stu-id="482d0-450">hungarian tin</span></span>
  
<span data-ttu-id="482d0-451">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-451">tax id number</span></span>
  
<span data-ttu-id="482d0-452">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="482d0-452">vat number</span></span>
  
<span data-ttu-id="482d0-453">Steuerbehörde Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-453">tax authority no</span></span>
  
<span data-ttu-id="482d0-454">USt-ID-Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-454">tax id tax identity number</span></span>
  
<span data-ttu-id="482d0-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-455">taxidnumber#</span></span>
  
<span data-ttu-id="482d0-456">Zinn #</span><span class="sxs-lookup"><span data-stu-id="482d0-456">tin#</span></span>
  
<span data-ttu-id="482d0-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="482d0-457">hungatiantin#</span></span>
  
<span data-ttu-id="482d0-458">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-458">tax identification no</span></span>
  
<span data-ttu-id="482d0-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="482d0-459">taxidno#</span></span>
  
<span data-ttu-id="482d0-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="482d0-460">adóazonosító szám</span></span>
  
<span data-ttu-id="482d0-461">adószám</span><span class="sxs-lookup"><span data-stu-id="482d0-461">adószám</span></span>
  
<span data-ttu-id="482d0-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="482d0-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="482d0-463">Irland</span><span class="sxs-lookup"><span data-stu-id="482d0-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="482d0-464">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-464">Format</span></span>

<span data-ttu-id="482d0-465">Sieben Ziffern, gefolgt von einem Buchstaben ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-466">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-466">Pattern</span></span>

<span data-ttu-id="482d0-467">Sieben Ziffern, gefolgt von einem Buchstaben:</span><span class="sxs-lookup"><span data-stu-id="482d0-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="482d0-468">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="482d0-468">Seven digits</span></span> 
    
- <span data-ttu-id="482d0-469">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-470">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-470">Checksum</span></span>

<span data-ttu-id="482d0-471">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-472">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-472">Definition</span></span>

<span data-ttu-id="482d0-473">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-474">Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-475">Ein Schlüsselwort `Keywords_ireland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-476">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-477">Die- `Func_ireland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-478">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="482d0-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-480">öffentlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-480">public service no</span></span>
  
<span data-ttu-id="482d0-481">persönlicher öffentlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-481">personal public service no</span></span>
  
<span data-ttu-id="482d0-482">PPS Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-482">pps no</span></span>
  
<span data-ttu-id="482d0-483">persönlicher Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-483">personal service no</span></span>
  
<span data-ttu-id="482d0-484">PPS-Dienst Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-484">pps service no</span></span>
  
<span data-ttu-id="482d0-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="482d0-485">ppsno#</span></span>
  
<span data-ttu-id="482d0-486">irische PPS Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-486">irish pps no</span></span>
  
<span data-ttu-id="482d0-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="482d0-487">publicserviceno#</span></span>
  
<span data-ttu-id="482d0-488">persönliche öffentliche Dienstnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-488">personal public service number</span></span>
  
<span data-ttu-id="482d0-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="482d0-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="482d0-490">PPS-uimh</span><span class="sxs-lookup"><span data-stu-id="482d0-490">pps uimh</span></span>
  
<span data-ttu-id="482d0-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="482d0-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="482d0-492">Italien</span><span class="sxs-lookup"><span data-stu-id="482d0-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="482d0-493">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-493">Format</span></span>

<span data-ttu-id="482d0-494">16 Buchstaben und Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-495">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-495">Pattern</span></span>

<span data-ttu-id="482d0-496">16 Buchstaben und Ziffern:</span><span class="sxs-lookup"><span data-stu-id="482d0-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="482d0-497">Drei Buchstaben, die den ersten drei Konsonanten im Familiennamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="482d0-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="482d0-498">Drei Buchstaben, die den ersten, dritten und vierten Konsonanten im Vornamen entsprechen</span><span class="sxs-lookup"><span data-stu-id="482d0-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="482d0-499">Zwei Ziffern, die den letzten Ziffern des Geburtsjahres entsprechen</span><span class="sxs-lookup"><span data-stu-id="482d0-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="482d0-500">Eine Ziffer, die dem Monat der Geburt entspricht – Buchstaben werden in alphabetischer Reihenfolge verwendet, aber nur die Buchstaben a bis E, H, L, M, P, R bis T werden verwendet (der Januar ist also a und Oktober ist r).</span><span class="sxs-lookup"><span data-stu-id="482d0-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="482d0-501">Zwei Ziffern, die dem Tag des Geburtsmonats entsprechen, in dem 40 dem Tag der Geburt hinzugefügt wird, damit weibliche Personen von Männern unterscheiden können</span><span class="sxs-lookup"><span data-stu-id="482d0-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="482d0-502">Vier Ziffern, die einer Ortskennzahl entsprechen, die für die Gemeinde spezifisch ist, in der die Person geboren wurde – landesweite Codes werden für fremde Länder verwendet</span><span class="sxs-lookup"><span data-stu-id="482d0-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="482d0-503">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="482d0-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-504">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-504">Checksum</span></span>

<span data-ttu-id="482d0-505">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-506">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-506">Definition</span></span>

<span data-ttu-id="482d0-507">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-508">Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-509">Ein Schlüsselwort `Keywords_italy_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-510">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-511">Die- `Func_italy_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-512">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="482d0-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-514">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-514">tax number</span></span>
  
<span data-ttu-id="482d0-515">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-515">tax no.</span></span>
  
<span data-ttu-id="482d0-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-516">taxno#</span></span>
  
<span data-ttu-id="482d0-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-517">taxnumber#</span></span>
  
<span data-ttu-id="482d0-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-518">taxnumber</span></span>
  
<span data-ttu-id="482d0-519">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-519">tax id</span></span>
  
<span data-ttu-id="482d0-520">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-520">taxid#</span></span>
  
<span data-ttu-id="482d0-521">Geschäftscode</span><span class="sxs-lookup"><span data-stu-id="482d0-521">fiscal code</span></span>
  
<span data-ttu-id="482d0-522">Geschäftsjahr</span><span class="sxs-lookup"><span data-stu-id="482d0-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="482d0-523">Lettland</span><span class="sxs-lookup"><span data-stu-id="482d0-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="482d0-524">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-524">Format</span></span>

<span data-ttu-id="482d0-525">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-526">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-526">Pattern</span></span>

<span data-ttu-id="482d0-527">11 Ziffern im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="482d0-528">Sechs Ziffern, die dem Geburtsdatum entsprechen (TTMMJJ)</span><span class="sxs-lookup"><span data-stu-id="482d0-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="482d0-529">Eine Ziffer, die dem Jahrhundert der Geburt entspricht, wobei "0" dem 19. Jahrhundert entspricht, "1" entspricht dem 20. Jahrhundert, und "2" entspricht dem 21. Jahrhundert</span><span class="sxs-lookup"><span data-stu-id="482d0-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="482d0-530">Vier Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-531">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-531">Checksum</span></span>

<span data-ttu-id="482d0-532">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-533">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-533">Definition</span></span>

<span data-ttu-id="482d0-534">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-535">Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-536">Ein Schlüsselwort `Keywords_latvia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-537">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-538">Die- `Func_latvia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-539">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="482d0-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-541">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-541">tax number</span></span>
  
<span data-ttu-id="482d0-542">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-542">tax no.</span></span>
  
<span data-ttu-id="482d0-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-543">taxno#</span></span>
  
<span data-ttu-id="482d0-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-544">taxnumber#</span></span>
  
<span data-ttu-id="482d0-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-545">taxnumber</span></span>
  
<span data-ttu-id="482d0-546">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-546">tax id</span></span>
  
<span data-ttu-id="482d0-547">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-547">taxid#</span></span>
  
<span data-ttu-id="482d0-548">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-548">tax identification number</span></span>
  
<span data-ttu-id="482d0-549">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-549">tax identification no.</span></span>
  
<span data-ttu-id="482d0-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="482d0-550">nodokļa numurs</span></span>
  
<span data-ttu-id="482d0-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="482d0-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="482d0-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="482d0-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="482d0-553">Litauen</span><span class="sxs-lookup"><span data-stu-id="482d0-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="482d0-554">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-554">Format</span></span>

<span data-ttu-id="482d0-555">11 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-556">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-556">Pattern</span></span>

<span data-ttu-id="482d0-557">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-558">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-558">Checksum</span></span>

<span data-ttu-id="482d0-559">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-560">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-560">Definition</span></span>

<span data-ttu-id="482d0-561">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-562">Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-563">Ein Schlüsselwort `Keywords_lithuania_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-564">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-565">Die- `Func_lithuania_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-566">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="482d0-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-568">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-568">tax number</span></span>
  
<span data-ttu-id="482d0-569">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-569">tax no.</span></span>
  
<span data-ttu-id="482d0-570">Steuernummer #</span><span class="sxs-lookup"><span data-stu-id="482d0-570">tax no#</span></span>
  
<span data-ttu-id="482d0-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-571">taxnumber#</span></span>
  
<span data-ttu-id="482d0-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-572">taxnumber</span></span>
  
<span data-ttu-id="482d0-573">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-573">tax id</span></span>
  
<span data-ttu-id="482d0-574">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-574">taxid#</span></span>
  
<span data-ttu-id="482d0-575">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-575">tax identification number</span></span>
  
<span data-ttu-id="482d0-576">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-576">tax identification no.</span></span>
  
<span data-ttu-id="482d0-577">mokesčių-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-577">mokesčių id</span></span>
  
<span data-ttu-id="482d0-578">mokesčių Numeris</span><span class="sxs-lookup"><span data-stu-id="482d0-578">mokesčių numeris</span></span>
  
<span data-ttu-id="482d0-579">mokesčių identifikavimas Numeris</span><span class="sxs-lookup"><span data-stu-id="482d0-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="482d0-580">Luxemburg</span><span class="sxs-lookup"><span data-stu-id="482d0-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="482d0-581">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-581">Format</span></span>

<span data-ttu-id="482d0-582">13 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-583">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-583">Pattern</span></span>

<span data-ttu-id="482d0-584">13 Ziffern:</span><span class="sxs-lookup"><span data-stu-id="482d0-584">13 digits:</span></span>
  
-  <span data-ttu-id="482d0-585">11 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-585">11 digits</span></span> 
    
- <span data-ttu-id="482d0-586">Zwei Prüfziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-587">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-587">Checksum</span></span>

<span data-ttu-id="482d0-588">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-589">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-589">Definition</span></span>

<span data-ttu-id="482d0-590">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-591">Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-592">Ein Schlüsselwort `Keywords_luxemburg_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-593">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-594">Die- `Func_luxemburg_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-595">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="482d0-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-597">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-597">tax number</span></span>
  
<span data-ttu-id="482d0-598">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-598">tax no.</span></span>
  
<span data-ttu-id="482d0-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-599">taxno#</span></span>
  
<span data-ttu-id="482d0-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-600">taxnumber#</span></span>
  
<span data-ttu-id="482d0-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-601">taxnumber</span></span>
  
<span data-ttu-id="482d0-602">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-602">tax id</span></span>
  
<span data-ttu-id="482d0-603">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-603">taxid#</span></span>
  
<span data-ttu-id="482d0-604">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-604">tax identification number</span></span>
  
<span data-ttu-id="482d0-605">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-605">tax identification no.</span></span>
  
<span data-ttu-id="482d0-606">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-606">steuernummer</span></span>
  
<span data-ttu-id="482d0-607">Ingo-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-607">steuer id</span></span>
  
<span data-ttu-id="482d0-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="482d0-609">Malta</span><span class="sxs-lookup"><span data-stu-id="482d0-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="482d0-610">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-610">Format</span></span>

<span data-ttu-id="482d0-611">Für maltesische Staatsangehörige: 7 Ziffern und ein Buchstabe im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="482d0-612">Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-613">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-613">Pattern</span></span>

<span data-ttu-id="482d0-614">Maltesische Staatsangehörige: 7 Ziffern und ein Buchstaben</span><span class="sxs-lookup"><span data-stu-id="482d0-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="482d0-615">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="482d0-615">Seven digits</span></span> 
    
- <span data-ttu-id="482d0-616">Ein Buchstabe (ohne Berücksichtigung der Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="482d0-617">Nicht-maltesische Staatsangehörige und maltesische Entitäten: 9 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="482d0-618">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="482d0-619">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-619">Checksum</span></span>

<span data-ttu-id="482d0-620">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-621">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-621">Definition</span></span>

<span data-ttu-id="482d0-622">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-623">Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-624">Ein Schlüsselwort `Keywords_malta_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-625">Eine DLP-Richtlinie ist zu 65 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-626">Die- `Func_malta_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-627">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="482d0-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-629">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-629">tax number</span></span>
  
<span data-ttu-id="482d0-630">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-630">tax no.</span></span>
  
<span data-ttu-id="482d0-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-631">taxno#</span></span>
  
<span data-ttu-id="482d0-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-632">taxnumber#</span></span>
  
<span data-ttu-id="482d0-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-633">taxnumber</span></span>
  
<span data-ttu-id="482d0-634">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-634">tax id</span></span>
  
<span data-ttu-id="482d0-635">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-635">taxid#</span></span>
  
<span data-ttu-id="482d0-636">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-636">tax identification number</span></span>
  
<span data-ttu-id="482d0-637">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-637">tax identification no.</span></span>
  
<span data-ttu-id="482d0-638">numru tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="482d0-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="482d0-639">ID tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="482d0-639">id tat-taxxa</span></span>
  
<span data-ttu-id="482d0-640">numru ta ' identifikazzjoni tat-Taxxa</span><span class="sxs-lookup"><span data-stu-id="482d0-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="482d0-641">Niederlande</span><span class="sxs-lookup"><span data-stu-id="482d0-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="482d0-642">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-642">Format</span></span>

<span data-ttu-id="482d0-643">Neun Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-644">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-644">Pattern</span></span>

<span data-ttu-id="482d0-645">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="482d0-646">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-646">Checksum</span></span>

<span data-ttu-id="482d0-647">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-648">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-648">Definition</span></span>

<span data-ttu-id="482d0-649">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-650">Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-651">Ein Schlüsselwort `Keywords_netherlands_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-652">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-653">Die- `Func_netherlands_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-654">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="482d0-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-656">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="482d0-657">niederländische Steueridentifikation</span><span class="sxs-lookup"><span data-stu-id="482d0-657">netherlands tax identification</span></span>
  
<span data-ttu-id="482d0-658">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="482d0-659">niederländische Steueridentifikation</span><span class="sxs-lookup"><span data-stu-id="482d0-659">netherland's tax identification</span></span>
  
<span data-ttu-id="482d0-660">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-660">tax identification number</span></span>
  
<span data-ttu-id="482d0-661">niederländische Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-661">dutch tax id</span></span>
  
<span data-ttu-id="482d0-662">niederländische Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-662">dutch tax identification number</span></span>
  
<span data-ttu-id="482d0-663">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-663">tax id</span></span>
  
<span data-ttu-id="482d0-664">Steuer-ID #</span><span class="sxs-lookup"><span data-stu-id="482d0-664">tax id#</span></span>
  
<span data-ttu-id="482d0-665">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-665">tax number</span></span>
  
<span data-ttu-id="482d0-666">Steuernummer #</span><span class="sxs-lookup"><span data-stu-id="482d0-666">tax no#</span></span>
  
<span data-ttu-id="482d0-667">Steuer #</span><span class="sxs-lookup"><span data-stu-id="482d0-667">tax#</span></span>
  
<span data-ttu-id="482d0-668">Zinn</span><span class="sxs-lookup"><span data-stu-id="482d0-668">tin</span></span>
  
<span data-ttu-id="482d0-669">Zinn #</span><span class="sxs-lookup"><span data-stu-id="482d0-669">tin#</span></span>
  
<span data-ttu-id="482d0-670">Niederlande Tin</span><span class="sxs-lookup"><span data-stu-id="482d0-670">netherlands tin</span></span>
  
<span data-ttu-id="482d0-671">niederländische Zinn</span><span class="sxs-lookup"><span data-stu-id="482d0-671">netherland's tin</span></span>
  
<span data-ttu-id="482d0-672">Nederlands belasten identificatienummer</span><span class="sxs-lookup"><span data-stu-id="482d0-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="482d0-673">identificatienummer van belasten</span><span class="sxs-lookup"><span data-stu-id="482d0-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="482d0-674">identificatienummer-Belastungen</span><span class="sxs-lookup"><span data-stu-id="482d0-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="482d0-675">Nederlands belasten identificatie</span><span class="sxs-lookup"><span data-stu-id="482d0-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="482d0-676">Nederlands Belasting ID Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="482d0-677">Nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="482d0-678">BTW Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-678">btw nummer</span></span>
  
<span data-ttu-id="482d0-679">Nederlandse belasten von identificatie</span><span class="sxs-lookup"><span data-stu-id="482d0-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="482d0-680">Polen</span><span class="sxs-lookup"><span data-stu-id="482d0-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="482d0-681">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-681">Format</span></span>

<span data-ttu-id="482d0-682">Elf Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-683">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-683">Pattern</span></span>

<span data-ttu-id="482d0-684">Elf Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-685">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-685">Checksum</span></span>

<span data-ttu-id="482d0-686">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-687">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-687">Definition</span></span>

<span data-ttu-id="482d0-688">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-689">Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-690">Ein Schlüsselwort `Keywords_poland_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-691">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-692">Die- `Func_poland_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-693">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="482d0-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-695">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-695">tax number</span></span>
  
<span data-ttu-id="482d0-696">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-696">tax no.</span></span>
  
<span data-ttu-id="482d0-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-697">taxno#</span></span>
  
<span data-ttu-id="482d0-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-698">taxnumber#</span></span>
  
<span data-ttu-id="482d0-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-699">taxnumber</span></span>
  
<span data-ttu-id="482d0-700">NIP</span><span class="sxs-lookup"><span data-stu-id="482d0-700">nip</span></span>
  
<span data-ttu-id="482d0-701">NIP #</span><span class="sxs-lookup"><span data-stu-id="482d0-701">nip#</span></span>
  
<span data-ttu-id="482d0-702">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-702">tax id</span></span>
  
<span data-ttu-id="482d0-703">Steuer-ID #</span><span class="sxs-lookup"><span data-stu-id="482d0-703">tax id#</span></span>
  
<span data-ttu-id="482d0-704">NIP-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-704">nip id</span></span>
  
<span data-ttu-id="482d0-705">NIP-ID #</span><span class="sxs-lookup"><span data-stu-id="482d0-705">nip id#</span></span>
  
<span data-ttu-id="482d0-706">Steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-706">tax identification number</span></span>
  
<span data-ttu-id="482d0-707">USt-ID-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-707">tax identification no.</span></span>
  
<span data-ttu-id="482d0-708">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="482d0-708">vat number</span></span>
  
<span data-ttu-id="482d0-709">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="482d0-709">vat no.</span></span>
  
<span data-ttu-id="482d0-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="482d0-710">vatno#</span></span>
  
<span data-ttu-id="482d0-711">USt-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-711">vat id</span></span>
  
<span data-ttu-id="482d0-712">USt-ID #</span><span class="sxs-lookup"><span data-stu-id="482d0-712">vat id#</span></span>
  
<span data-ttu-id="482d0-713">Numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="482d0-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="482d0-714">Polski Numer identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="482d0-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="482d0-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="482d0-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="482d0-716">Portugal</span><span class="sxs-lookup"><span data-stu-id="482d0-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="482d0-717">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-717">Format</span></span>

<span data-ttu-id="482d0-718">Neun Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-719">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-719">Pattern</span></span>

<span data-ttu-id="482d0-720">Neun Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-721">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-721">Checksum</span></span>

<span data-ttu-id="482d0-722">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-723">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-723">Definition</span></span>

<span data-ttu-id="482d0-724">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-725">Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-726">Ein Schlüsselwort `Keywords_portugal_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-727">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-728">Die- `Func_portugal_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-729">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="482d0-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-731">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-731">tax number</span></span>
  
<span data-ttu-id="482d0-732">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-732">tax no.</span></span>
  
<span data-ttu-id="482d0-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-733">taxno#</span></span>
  
<span data-ttu-id="482d0-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="482d0-734">taxnumber#</span></span>
  
<span data-ttu-id="482d0-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="482d0-735">taxnumber</span></span>
  
<span data-ttu-id="482d0-736">NIF</span><span class="sxs-lookup"><span data-stu-id="482d0-736">nif</span></span>
  
<span data-ttu-id="482d0-737">NIF #</span><span class="sxs-lookup"><span data-stu-id="482d0-737">nif#</span></span>
  
<span data-ttu-id="482d0-738">numerisch-Geschäftsjahr</span><span class="sxs-lookup"><span data-stu-id="482d0-738">numero fiscal</span></span>
  
<span data-ttu-id="482d0-739">número de identificação Fiscal</span><span class="sxs-lookup"><span data-stu-id="482d0-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="482d0-740">Rumänien</span><span class="sxs-lookup"><span data-stu-id="482d0-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="482d0-741">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-741">Format</span></span>

<span data-ttu-id="482d0-742">13 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-743">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-743">Pattern</span></span>

<span data-ttu-id="482d0-744">13 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-745">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-745">Checksum</span></span>

<span data-ttu-id="482d0-746">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-747">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-747">Definition</span></span>

<span data-ttu-id="482d0-748">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-749">Der reguläre Ausdruck `Regex_romania_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-750">Ein Schlüsselwort `Keywords_romania_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="482d0-751">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="482d0-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-753">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-753">tax id</span></span>
  
<span data-ttu-id="482d0-754">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-754">tax id number</span></span>
  
<span data-ttu-id="482d0-755">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-755">tax file no</span></span>
  
<span data-ttu-id="482d0-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="482d0-756">tax file number</span></span>
  
<span data-ttu-id="482d0-757">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-757">tax no</span></span>
  
<span data-ttu-id="482d0-758">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-758">tax number</span></span>
  
<span data-ttu-id="482d0-759">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-759">taxid#</span></span>
  
<span data-ttu-id="482d0-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-760">taxno#</span></span>
  
<span data-ttu-id="482d0-761">ID-UL taxei</span><span class="sxs-lookup"><span data-stu-id="482d0-761">id-ul taxei</span></span>
  
<span data-ttu-id="482d0-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="482d0-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="482d0-763">Slowakei</span><span class="sxs-lookup"><span data-stu-id="482d0-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="482d0-764">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-764">Format</span></span>

<span data-ttu-id="482d0-765">10 Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-766">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-766">Pattern</span></span>

<span data-ttu-id="482d0-767">10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-768">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-768">Checksum</span></span>

<span data-ttu-id="482d0-769">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="482d0-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-770">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-770">Definition</span></span>

<span data-ttu-id="482d0-771">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-772">Der reguläre Ausdruck `Regex_slovakia_eu_tax_file_number` sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-773">Ein Schlüsselwort `Keywords_slovakia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="482d0-774">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="482d0-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-776">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-776">tax id</span></span>
  
<span data-ttu-id="482d0-777">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-777">tax id number</span></span>
  
<span data-ttu-id="482d0-778">Tin-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-778">tin id</span></span>
  
<span data-ttu-id="482d0-779">Tin Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-779">tin no</span></span>
  
<span data-ttu-id="482d0-780">Slowakische Tin-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-780">slovakian tin id</span></span>
  
<span data-ttu-id="482d0-781">Zinn</span><span class="sxs-lookup"><span data-stu-id="482d0-781">tin</span></span>
  
<span data-ttu-id="482d0-782">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-782">tax file no</span></span>
  
<span data-ttu-id="482d0-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="482d0-783">tax file number</span></span>
  
<span data-ttu-id="482d0-784">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-784">tax no</span></span>
  
<span data-ttu-id="482d0-785">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-785">tax number</span></span>
  
<span data-ttu-id="482d0-786">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-786">taxid#</span></span>
  
<span data-ttu-id="482d0-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-787">taxno#</span></span>
  
<span data-ttu-id="482d0-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="482d0-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="482d0-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="482d0-789">daňové číslo</span></span>
  
<span data-ttu-id="482d0-790">Daňové číslo SÚBORU</span><span class="sxs-lookup"><span data-stu-id="482d0-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="482d0-791">Slowenien</span><span class="sxs-lookup"><span data-stu-id="482d0-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="482d0-792">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-792">Format</span></span>

<span data-ttu-id="482d0-793">Acht Ziffern ohne Leerzeichen oder Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-794">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-794">Pattern</span></span>

<span data-ttu-id="482d0-795">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-796">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-796">Checksum</span></span>

<span data-ttu-id="482d0-797">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-798">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-798">Definition</span></span>

<span data-ttu-id="482d0-799">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-800">Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-801">Ein Schlüsselwort `Keywords_slovenia_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-802">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-803">Die- `Func_slovenia_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-804">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="482d0-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-806">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-806">tax id</span></span>
  
<span data-ttu-id="482d0-807">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-807">tax id number</span></span>
  
<span data-ttu-id="482d0-808">Tin-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-808">tin id</span></span>
  
<span data-ttu-id="482d0-809">Tin Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-809">tin no</span></span>
  
<span data-ttu-id="482d0-810">slowenische Tin-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-810">slovenian tin id</span></span>
  
<span data-ttu-id="482d0-811">Zinn</span><span class="sxs-lookup"><span data-stu-id="482d0-811">tin</span></span>
  
<span data-ttu-id="482d0-812">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-812">tax file no</span></span>
  
<span data-ttu-id="482d0-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="482d0-813">tax file number</span></span>
  
<span data-ttu-id="482d0-814">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-814">tax no</span></span>
  
<span data-ttu-id="482d0-815">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-815">tax number</span></span>
  
<span data-ttu-id="482d0-816">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-816">taxid#</span></span>
  
<span data-ttu-id="482d0-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-817">taxno#</span></span>
  
<span data-ttu-id="482d0-818">identifikacijska številka beim Davka</span><span class="sxs-lookup"><span data-stu-id="482d0-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="482d0-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="482d0-819">davčna številka</span></span>
  
<span data-ttu-id="482d0-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="482d0-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="482d0-821">Spanien</span><span class="sxs-lookup"><span data-stu-id="482d0-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="482d0-822">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-822">Format</span></span>

<span data-ttu-id="482d0-823">Sieben oder acht Ziffern und ein oder zwei Buchstaben im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-824">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-824">Pattern</span></span>

<span data-ttu-id="482d0-825">Spanisch natürliche Personen mit einem nationalen spanischen Identitätsausweis:</span><span class="sxs-lookup"><span data-stu-id="482d0-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="482d0-826">Acht Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-826">Eight digits</span></span> 
    
- <span data-ttu-id="482d0-827">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="482d0-828">Nicht-residente Spanier ohne einen nationalen Identitätsausweis in Spanien</span><span class="sxs-lookup"><span data-stu-id="482d0-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="482d0-829">Ein Großbuchstabe "L" (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="482d0-830">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="482d0-830">Seven digits</span></span>
    
- <span data-ttu-id="482d0-831">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="482d0-832">Ansässige Spanier unter 14 Jahren ohne einen nationalen spanischen Identitätsausweis:</span><span class="sxs-lookup"><span data-stu-id="482d0-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="482d0-833">Ein Großbuchstabe "K" (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="482d0-834">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="482d0-834">Seven digits</span></span> 
    
- <span data-ttu-id="482d0-835">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="482d0-836">Ausländer mit Identifikationsnummer eines Ausländers</span><span class="sxs-lookup"><span data-stu-id="482d0-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="482d0-837">Ein Großbuchstabe mit "X", "Y" oder "Z" (Groß-/Kleinschreibung wird beachtet)</span><span class="sxs-lookup"><span data-stu-id="482d0-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="482d0-838">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="482d0-838">Seven digits</span></span>
    
- <span data-ttu-id="482d0-839">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="482d0-840">Ausländer ohne Identifikationsnummer eines Ausländers</span><span class="sxs-lookup"><span data-stu-id="482d0-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="482d0-841">Ein Großbuchstabe, der "M" ist (Groß-/Kleinschreibung beachten)</span><span class="sxs-lookup"><span data-stu-id="482d0-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="482d0-842">Sieben Ziffern </span><span class="sxs-lookup"><span data-stu-id="482d0-842">Seven digits</span></span>
    
- <span data-ttu-id="482d0-843">Ein Großbuchstabe (Unterscheidung nach Groß-/Kleinschreibung)</span><span class="sxs-lookup"><span data-stu-id="482d0-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="482d0-844">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-844">Checksum</span></span>

<span data-ttu-id="482d0-845">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-846">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-846">Definition</span></span>

<span data-ttu-id="482d0-847">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-848">Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-849">Ein Schlüsselwort `Keywords_spain_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-850">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-851">Die- `Func_spain_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-852">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="482d0-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-854">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-854">tax id</span></span>
  
<span data-ttu-id="482d0-855">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-855">tax id number</span></span>
  
<span data-ttu-id="482d0-856">CIF-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-856">cif id</span></span>
  
<span data-ttu-id="482d0-857">CIF Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-857">cif no</span></span>
  
<span data-ttu-id="482d0-858">spanische CIF-ID</span><span class="sxs-lookup"><span data-stu-id="482d0-858">spanish cif id</span></span>
  
<span data-ttu-id="482d0-859">CIF</span><span class="sxs-lookup"><span data-stu-id="482d0-859">cif</span></span>
  
<span data-ttu-id="482d0-860">Steuerdatei Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-860">tax file no</span></span>
  
<span data-ttu-id="482d0-861">spanische CIF-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-861">spanish cif number</span></span>
  
<span data-ttu-id="482d0-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="482d0-862">tax file number</span></span>
  
<span data-ttu-id="482d0-863">Spanisch CIF Nein</span><span class="sxs-lookup"><span data-stu-id="482d0-863">spanish cif no</span></span>
  
<span data-ttu-id="482d0-864">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-864">tax no</span></span>
  
<span data-ttu-id="482d0-865">Steuernummer</span><span class="sxs-lookup"><span data-stu-id="482d0-865">tax number</span></span>
  
<span data-ttu-id="482d0-866">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-866">taxid#</span></span>
  
<span data-ttu-id="482d0-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="482d0-867">taxno#</span></span>
  
<span data-ttu-id="482d0-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="482d0-868">cifid#</span></span>
  
<span data-ttu-id="482d0-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="482d0-869">spanishcifid#</span></span>
  
<span data-ttu-id="482d0-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="482d0-870">spanishcifno#</span></span>
  
<span data-ttu-id="482d0-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="482d0-871">número de contribuyente</span></span>
  
<span data-ttu-id="482d0-872">número de Impuesto Corporativo</span><span class="sxs-lookup"><span data-stu-id="482d0-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="482d0-873">número de Identificación Fiscal</span><span class="sxs-lookup"><span data-stu-id="482d0-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="482d0-874">CIF-número</span><span class="sxs-lookup"><span data-stu-id="482d0-874">cif número</span></span>
  
<span data-ttu-id="482d0-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="482d0-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="482d0-876">Schweden</span><span class="sxs-lookup"><span data-stu-id="482d0-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="482d0-877">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-877">Format</span></span>

<span data-ttu-id="482d0-878">Zehn Ziffern und ein Symbol im angegebenen Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-879">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-879">Pattern</span></span>

<span data-ttu-id="482d0-880">Zehn Ziffern und ein Symbol:</span><span class="sxs-lookup"><span data-stu-id="482d0-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="482d0-881">Sechs Ziffern, die dem Geburtsdatum entsprechen (JJMMTT)</span><span class="sxs-lookup"><span data-stu-id="482d0-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="482d0-882">Pluszeichen, Minuszeichen oder Backslash</span><span class="sxs-lookup"><span data-stu-id="482d0-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="482d0-883">Drei Ziffern, die die Identifikationsnummer eindeutig machen:</span><span class="sxs-lookup"><span data-stu-id="482d0-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="482d0-884">Für Zahlen, die vor 1990 ausgegeben wurden, identifizieren die siebte und die achte Ziffer den Geburts Kreis oder den in der fremde geborenen Personen.</span><span class="sxs-lookup"><span data-stu-id="482d0-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="482d0-885">Die Ziffer in der neunten Position gibt das Geschlecht entweder ungerade für männliche oder sogar für weiblich an.</span><span class="sxs-lookup"><span data-stu-id="482d0-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="482d0-886">Eine Prüfziffer</span><span class="sxs-lookup"><span data-stu-id="482d0-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="482d0-887">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-887">Checksum</span></span>

<span data-ttu-id="482d0-888">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-889">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-889">Definition</span></span>

<span data-ttu-id="482d0-890">Eine DLP-Richtlinie ist zu 85 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-891">Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-892">Ein Schlüsselwort `Keywords_sweden_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="482d0-893">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-894">Die- `Func_sweden_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="482d0-895">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="482d0-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-897">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-897">tax id</span></span>
  
<span data-ttu-id="482d0-898">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="482d0-898">tax id no.</span></span>
  
<span data-ttu-id="482d0-899">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-899">tax id number</span></span>
  
<span data-ttu-id="482d0-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="482d0-900">tax identification</span></span>
  
<span data-ttu-id="482d0-901">Steueridentifikation #</span><span class="sxs-lookup"><span data-stu-id="482d0-901">tax identification#</span></span>
  
<span data-ttu-id="482d0-902">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-902">tax no.</span></span>
  
<span data-ttu-id="482d0-903">Steuer #</span><span class="sxs-lookup"><span data-stu-id="482d0-903">tax#</span></span>
  
<span data-ttu-id="482d0-904">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-904">taxid#</span></span>
  
<span data-ttu-id="482d0-905">Steuerdatei</span><span class="sxs-lookup"><span data-stu-id="482d0-905">tax file</span></span>
  
<span data-ttu-id="482d0-906">Steuerdatei-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-906">tax file no.</span></span>
  
<span data-ttu-id="482d0-907">persönliche ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-907">personal id number</span></span>
  
<span data-ttu-id="482d0-908">Skate ID Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-908">skatt id nummer</span></span>
  
<span data-ttu-id="482d0-909">skatt Identifikation</span><span class="sxs-lookup"><span data-stu-id="482d0-909">skatt identifikation</span></span>
  
<span data-ttu-id="482d0-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="482d0-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="482d0-911">UK</span><span class="sxs-lookup"><span data-stu-id="482d0-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="482d0-912">Format</span><span class="sxs-lookup"><span data-stu-id="482d0-912">Format</span></span>

<span data-ttu-id="482d0-913">Unique Steuerzahler Referenz (UTR): 10 Ziffern ohne Leerzeichen und Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="482d0-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="482d0-914">Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="482d0-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="482d0-915">Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="482d0-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="482d0-916">Muster</span><span class="sxs-lookup"><span data-stu-id="482d0-916">Pattern</span></span>

<span data-ttu-id="482d0-917">Unique Steuerzahler Referenz (UTR): 10 Ziffern</span><span class="sxs-lookup"><span data-stu-id="482d0-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="482d0-918">Nationale Versicherungsnummer (Nino): Weitere Informationen finden Sie im Abschnitt "U.K.</span><span class="sxs-lookup"><span data-stu-id="482d0-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="482d0-919">Nationale Versicherungsnummer (Nino) "in [dem, wonach die Typen vertraulicher Informationen suchen](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="482d0-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="482d0-920">Prüfsumme</span><span class="sxs-lookup"><span data-stu-id="482d0-920">Checksum</span></span>

<span data-ttu-id="482d0-921">Ja</span><span class="sxs-lookup"><span data-stu-id="482d0-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="482d0-922">Definition</span><span class="sxs-lookup"><span data-stu-id="482d0-922">Definition</span></span>

<span data-ttu-id="482d0-923">Eine DLP-Richtlinie ist zu 75 % sicher, dass diese Art von vertraulichen Informationen erkannt wurde, wenn Folgendes innerhalb von 300 Zeichen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="482d0-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="482d0-924">Die- `Func_uk_eu_tax_file_number` Funktion sucht nach Inhalten, die mit dem Muster übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="482d0-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="482d0-925">Ein Schlüsselwort `Keywords_uk_eu_tax_file_number` aus wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="482d0-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="482d0-926">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="482d0-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="482d0-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="482d0-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="482d0-928">tax id</span><span class="sxs-lookup"><span data-stu-id="482d0-928">tax id</span></span>
  
<span data-ttu-id="482d0-929">USt-IdNr.</span><span class="sxs-lookup"><span data-stu-id="482d0-929">tax id no.</span></span>
  
<span data-ttu-id="482d0-930">USt-ID-Nummer</span><span class="sxs-lookup"><span data-stu-id="482d0-930">tax id number</span></span>
  
<span data-ttu-id="482d0-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="482d0-931">tax identification</span></span>
  
<span data-ttu-id="482d0-932">Steueridentifikation #</span><span class="sxs-lookup"><span data-stu-id="482d0-932">tax identification#</span></span>
  
<span data-ttu-id="482d0-933">Steuer-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-933">tax no.</span></span>
  
<span data-ttu-id="482d0-934">Steuer #</span><span class="sxs-lookup"><span data-stu-id="482d0-934">tax#</span></span>
  
<span data-ttu-id="482d0-935">per Taxi #</span><span class="sxs-lookup"><span data-stu-id="482d0-935">taxid#</span></span>
  
<span data-ttu-id="482d0-936">Steuerdatei</span><span class="sxs-lookup"><span data-stu-id="482d0-936">tax file</span></span>
  
<span data-ttu-id="482d0-937">Steuerdatei-Nr.</span><span class="sxs-lookup"><span data-stu-id="482d0-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="482d0-938">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="482d0-938">See also</span></span>

[<span data-ttu-id="482d0-939">Wonach die Typen von vertraulichen Informationen suchen</span><span class="sxs-lookup"><span data-stu-id="482d0-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

