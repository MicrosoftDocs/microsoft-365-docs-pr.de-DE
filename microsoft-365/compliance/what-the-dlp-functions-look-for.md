---
title: Wonach die DLP-Funktionen suchen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, was die Funktionen zur Verhinderung von Datenverlust Prevention (DLP) suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819275"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="cdad4-103">Wonach die DLP-Funktionen suchen</span><span class="sxs-lookup"><span data-stu-id="cdad4-103">What the DLP functions look for</span></span>

<span data-ttu-id="cdad4-104">Die Verhinderung von Datenverlust (DLP) umfasst vertrauliche Informationstypen wie Kreditkartennummer und EU-Debitkarten-Nummer, die Sie in ihren DLP-Richtlinien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cdad4-104">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="cdad4-105">Diese Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen.</span><span class="sxs-lookup"><span data-stu-id="cdad4-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="cdad4-106">Einige dieser Funktionen werden von internen Funktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cdad4-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="cdad4-107">Der vertrauliche Informationstyp Kreditkartennummer verwendet beispielsweise eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind, um zu bestätigen, dass eine Zahl eine Kreditkartennummer ist.</span><span class="sxs-lookup"><span data-stu-id="cdad4-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="cdad4-108">In diesem Thema wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="cdad4-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="cdad4-109">Weitere Informationen finden Sie unter [sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) .</span><span class="sxs-lookup"><span data-stu-id="cdad4-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="cdad4-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="cdad4-110">Func_us_date</span></span>

<span data-ttu-id="cdad4-111">Diese Funktion sucht nach einem Datum in dem Format, das in den USA häufig verwendet wird. Dies umfasst die Formate "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr".</span><span class="sxs-lookup"><span data-stu-id="cdad4-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="cdad4-112">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="cdad4-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="cdad4-113">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cdad4-113">Examples:</span></span>
  
- <span data-ttu-id="cdad4-114">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-114">December 2, 2016</span></span>
    
- <span data-ttu-id="cdad4-115">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="cdad4-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-116">dec 02 2016</span></span>
    
- <span data-ttu-id="cdad4-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-117">12/2/2016</span></span>
    
- <span data-ttu-id="cdad4-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="cdad4-118">12/02/16</span></span>
    
- <span data-ttu-id="cdad4-119">Dez-2-2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="cdad4-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="cdad4-120">12-2-16</span></span>
    
<span data-ttu-id="cdad4-121">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="cdad4-121">Accepted month names:</span></span>
  
- <span data-ttu-id="cdad4-122">English</span><span class="sxs-lookup"><span data-stu-id="cdad4-122">English</span></span>
    
  - <span data-ttu-id="cdad4-123">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="cdad4-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="cdad4-124">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="cdad4-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="cdad4-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="cdad4-125">Func_eu_date</span></span>

<span data-ttu-id="cdad4-126">Diese Funktion sucht nach einem Datum in dem Format, das in der EU häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cdad4-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="cdad4-127">(und die meisten Orte außerhalb der USA).</span><span class="sxs-lookup"><span data-stu-id="cdad4-127">(and most places outside the U.S.).</span></span> <span data-ttu-id="cdad4-128">Dies umfasst die Formate "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Tag Monat Jahr".</span><span class="sxs-lookup"><span data-stu-id="cdad4-128">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="cdad4-129">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="cdad4-129">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="cdad4-130">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cdad4-130">Examples:</span></span>
  
- <span data-ttu-id="cdad4-131">2. Dez. 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="cdad4-132">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-132">02 dec 2016</span></span>
    
- <span data-ttu-id="cdad4-133">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="cdad4-133">2 Dec 16</span></span>
    
- <span data-ttu-id="cdad4-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-134">2/12/2016</span></span>
    
- <span data-ttu-id="cdad4-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="cdad4-135">02/12/16</span></span>
    
- <span data-ttu-id="cdad4-136">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="cdad4-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="cdad4-137">2-12-16</span></span>
    
<span data-ttu-id="cdad4-138">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="cdad4-138">Accepted month names:</span></span>
  
- <span data-ttu-id="cdad4-139">English</span><span class="sxs-lookup"><span data-stu-id="cdad4-139">English</span></span>
    
  - <span data-ttu-id="cdad4-140">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="cdad4-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="cdad4-141">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="cdad4-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="cdad4-142">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="cdad4-142">Dutch</span></span>
    
  - <span data-ttu-id="cdad4-143">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="cdad4-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="cdad4-144">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="cdad4-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="cdad4-145">Französisch</span><span class="sxs-lookup"><span data-stu-id="cdad4-145">French</span></span>
    
  - <span data-ttu-id="cdad4-146">janvier, février, Mars, Avril, Mai, Juni juillet, août, September, Oktober, Novembre, Novembre</span><span class="sxs-lookup"><span data-stu-id="cdad4-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="cdad4-147">janv.</span><span class="sxs-lookup"><span data-stu-id="cdad4-147">janv.</span></span> <span data-ttu-id="cdad4-148">févr.</span><span class="sxs-lookup"><span data-stu-id="cdad4-148">févr.</span></span> <span data-ttu-id="cdad4-149">Mars Avril Mai Juni juil.</span><span class="sxs-lookup"><span data-stu-id="cdad4-149">mars avril mai juin juil.</span></span> <span data-ttu-id="cdad4-150">août Sept.</span><span class="sxs-lookup"><span data-stu-id="cdad4-150">août sept.</span></span> <span data-ttu-id="cdad4-151">OAT.</span><span class="sxs-lookup"><span data-stu-id="cdad4-151">oct.</span></span> <span data-ttu-id="cdad4-152">Nov.</span><span class="sxs-lookup"><span data-stu-id="cdad4-152">nov.</span></span> <span data-ttu-id="cdad4-153">déc.</span><span class="sxs-lookup"><span data-stu-id="cdad4-153">déc.</span></span>
    
- <span data-ttu-id="cdad4-154">Deutsch</span><span class="sxs-lookup"><span data-stu-id="cdad4-154">German</span></span>
    
  - <span data-ttu-id="cdad4-155">Januar, Februar, März, April, Mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="cdad4-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="cdad4-156">Jan./Jän.</span><span class="sxs-lookup"><span data-stu-id="cdad4-156">Jan./Jän.</span></span> <span data-ttu-id="cdad4-157">Februar März Apr. Mai Juni Juli Aug. Sept. Okt.</span><span class="sxs-lookup"><span data-stu-id="cdad4-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="cdad4-158">Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="cdad4-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="cdad4-159">Italienisch</span><span class="sxs-lookup"><span data-stu-id="cdad4-159">Italian</span></span>
    
  - <span data-ttu-id="cdad4-160">gennaio, febbraio, Marzo, Aprile, Maggio, Juni, Juli, Agosto, Settembre, ottobre, Novembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="cdad4-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="cdad4-161">Genn.</span><span class="sxs-lookup"><span data-stu-id="cdad4-161">genn.</span></span> <span data-ttu-id="cdad4-162">febbr.</span><span class="sxs-lookup"><span data-stu-id="cdad4-162">febbr.</span></span> <span data-ttu-id="cdad4-163">Mrz.</span><span class="sxs-lookup"><span data-stu-id="cdad4-163">mar.</span></span> <span data-ttu-id="cdad4-164">Apr.</span><span class="sxs-lookup"><span data-stu-id="cdad4-164">apr.</span></span> <span data-ttu-id="cdad4-165">Magg.</span><span class="sxs-lookup"><span data-stu-id="cdad4-165">magg.</span></span> <span data-ttu-id="cdad4-166">Juni Juli AG.</span><span class="sxs-lookup"><span data-stu-id="cdad4-166">giugno luglio ag.</span></span> <span data-ttu-id="cdad4-167">Sett.</span><span class="sxs-lookup"><span data-stu-id="cdad4-167">sett.</span></span> <span data-ttu-id="cdad4-168">Ott.</span><span class="sxs-lookup"><span data-stu-id="cdad4-168">ott.</span></span> <span data-ttu-id="cdad4-169">Nov.</span><span class="sxs-lookup"><span data-stu-id="cdad4-169">nov.</span></span> <span data-ttu-id="cdad4-170">DIC.</span><span class="sxs-lookup"><span data-stu-id="cdad4-170">dic.</span></span>
    
- <span data-ttu-id="cdad4-171">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="cdad4-171">Portuguese</span></span>
    
  - <span data-ttu-id="cdad4-172">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="cdad4-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="cdad4-173">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="cdad4-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="cdad4-174">Spanisch</span><span class="sxs-lookup"><span data-stu-id="cdad4-174">Spanish</span></span>
    
  - <span data-ttu-id="cdad4-175">enero, Febrero, Marzo, Abril, Mayo, junio, Julio, Agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="cdad4-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="cdad4-176">enero Feb.</span><span class="sxs-lookup"><span data-stu-id="cdad4-176">enero feb.</span></span> <span data-ttu-id="cdad4-177">Marzo-ABR.</span><span class="sxs-lookup"><span data-stu-id="cdad4-177">marzo abr.</span></span> <span data-ttu-id="cdad4-178">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="cdad4-178">mayo jun.</span></span> <span data-ttu-id="cdad4-179">Juli.</span><span class="sxs-lookup"><span data-stu-id="cdad4-179">jul.</span></span> <span data-ttu-id="cdad4-180">Agosto Sept./Set.</span><span class="sxs-lookup"><span data-stu-id="cdad4-180">agosto sept./set.</span></span> <span data-ttu-id="cdad4-181">OAT.</span><span class="sxs-lookup"><span data-stu-id="cdad4-181">oct.</span></span> <span data-ttu-id="cdad4-182">Nov.</span><span class="sxs-lookup"><span data-stu-id="cdad4-182">nov.</span></span> <span data-ttu-id="cdad4-183">DIC.</span><span class="sxs-lookup"><span data-stu-id="cdad4-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="cdad4-184">Func_eu_date1 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="cdad4-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="cdad4-185">Diese Funktion ist veraltet, da Sie nur portugiesische Monatsnamen unterstützt, die nun in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cdad4-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="cdad4-186">Diese Funktion sucht nach einem Datum in dem Format, das in Portugiesisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cdad4-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="cdad4-187">Das Format für diese Funktion ist identisch mit der `Func_eu_date` Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="cdad4-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="cdad4-188">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cdad4-188">Examples:</span></span>
  
- <span data-ttu-id="cdad4-189">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="cdad4-190">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-190">02 dez 2016</span></span>
    
- <span data-ttu-id="cdad4-191">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="cdad4-191">2 Dez 16</span></span>
    
- <span data-ttu-id="cdad4-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-192">2/12/2016</span></span>
    
- <span data-ttu-id="cdad4-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="cdad4-193">02/12/16</span></span>
    
- <span data-ttu-id="cdad4-194">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="cdad4-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="cdad4-195">2-12-16</span></span>
    
<span data-ttu-id="cdad4-196">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="cdad4-196">Accepted month names:</span></span>
  
- <span data-ttu-id="cdad4-197">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="cdad4-197">Portuguese</span></span>
    
  - <span data-ttu-id="cdad4-198">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="cdad4-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="cdad4-199">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="cdad4-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="cdad4-200">Func_eu_date2 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="cdad4-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="cdad4-201">Diese Funktion ist veraltet, da nur niederländische Monatsnamen unterstützt werden, die jetzt in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="cdad4-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="cdad4-202">Diese Funktion sucht nach einem Datum in dem Format, das in Niederländisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cdad4-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="cdad4-203">Das Format für diese Funktion ist identisch mit der `Func_eu_date` Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="cdad4-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="cdad4-204">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cdad4-204">Examples:</span></span>
  
- <span data-ttu-id="cdad4-205">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="cdad4-206">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-206">02 mei 2016</span></span>
    
- <span data-ttu-id="cdad4-207">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="cdad4-207">2 Mei 16</span></span>
    
- <span data-ttu-id="cdad4-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-208">2/12/2016</span></span>
    
- <span data-ttu-id="cdad4-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="cdad4-209">02/12/16</span></span>
    
- <span data-ttu-id="cdad4-210">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="cdad4-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="cdad4-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="cdad4-211">2-12-16</span></span>
    
<span data-ttu-id="cdad4-212">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="cdad4-212">Accepted month names:</span></span>
  
- <span data-ttu-id="cdad4-213">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="cdad4-213">Dutch</span></span>
    
  - <span data-ttu-id="cdad4-214">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="cdad4-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="cdad4-215">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="cdad4-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="cdad4-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="cdad4-216">Func_expiration_date</span></span>

<span data-ttu-id="cdad4-217">Diese Funktion sucht nach einem Datum in den Formaten, die häufig von Kredit-und Debitkarten verwendet werden, wodurch Tage zugunsten von Monaten ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="cdad4-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="cdad4-218">Mit dieser Funktion werden Datumsangaben im Format "month/year", "month-year", "[Month Name] Year" und "[month Kürzel] Year" abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="cdad4-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="cdad4-219">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="cdad4-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="cdad4-220">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cdad4-220">Examples:</span></span>
  
- <span data-ttu-id="cdad4-221">MM/jj--zum Beispiel 01/11 oder 1/11</span><span class="sxs-lookup"><span data-stu-id="cdad4-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="cdad4-222">MM/jjjj--zum Beispiel 01/2011 oder 1/2011</span><span class="sxs-lookup"><span data-stu-id="cdad4-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="cdad4-223">MM-jj--zum Beispiel 01-22 oder 1-11</span><span class="sxs-lookup"><span data-stu-id="cdad4-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="cdad4-224">MM-yyyy--zum Beispiel 01-2000 oder 1-2000</span><span class="sxs-lookup"><span data-stu-id="cdad4-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="cdad4-225">Die folgenden Formate unterstützen JJ oder yyyy:</span><span class="sxs-lookup"><span data-stu-id="cdad4-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="cdad4-226">Monat-yyyy--zum Beispiel. Jan-2010 oder Januar-2010 oder Jan-10 oder Januar-10</span><span class="sxs-lookup"><span data-stu-id="cdad4-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="cdad4-227">Monat yyyy--zum Beispiel "Januar 2010" oder "Jan 2010" oder "Januar 10" oder "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="cdad4-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="cdad4-228">Monatjjjj--beispielsweise "january2010" oder "Jan2010" oder "january10" oder "Jan10"</span><span class="sxs-lookup"><span data-stu-id="cdad4-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="cdad4-229">Monat/JJJJ--zum Beispiel "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="cdad4-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="cdad4-230">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="cdad4-230">Accepted month names:</span></span>
  
- <span data-ttu-id="cdad4-231">English</span><span class="sxs-lookup"><span data-stu-id="cdad4-231">English</span></span>
    
  - <span data-ttu-id="cdad4-232">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="cdad4-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="cdad4-233">Jan Feb Mär Apr Mai Juni Juli Aug Sept Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="cdad4-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="cdad4-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="cdad4-234">Func_us_address</span></span>

<span data-ttu-id="cdad4-235">Diese Funktion sucht nach einem US-Bundesland Namen oder einer postalischen Abkürzung, gefolgt von einer gültigen Postleitzahl, genauso wie Sie in Postadressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cdad4-235">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="cdad4-236">Die Postleitzahl muss einer der korrekten Postleitzahlen sein, die dem US-Bundesland Namen oder der Abkürzung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="cdad4-236">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="cdad4-237">Der US-Bundesland Name und die Postleitzahl können nicht durch Interpunktion oder Buchstaben getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="cdad4-237">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="cdad4-238">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cdad4-238">Examples:</span></span>
  
- <span data-ttu-id="cdad4-239">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="cdad4-239">Washington 98052</span></span>
    
- <span data-ttu-id="cdad4-240">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="cdad4-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="cdad4-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="cdad4-241">WA 98052</span></span>
    
- <span data-ttu-id="cdad4-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="cdad4-242">WA 98052-9998</span></span>
    

