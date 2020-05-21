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
description: Die Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen. Einige dieser Funktionen werden von internen Funktionen ausgeführt. In diesem Thema wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.
ms.openlocfilehash: 710cd371cbf67a03d75a928baab4b63587cdcfc1
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327747"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="d7c57-105">Wonach die DLP-Funktionen suchen</span><span class="sxs-lookup"><span data-stu-id="d7c57-105">What the DLP functions look for</span></span>

<span data-ttu-id="d7c57-106">Die Verhinderung von Datenverlust (DLP) umfasst vertrauliche Informationstypen wie Kreditkartennummer und EU-Debitkarten-Nummer, die Sie in ihren DLP-Richtlinien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d7c57-106">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="d7c57-107">Diese Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen.</span><span class="sxs-lookup"><span data-stu-id="d7c57-107">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="d7c57-108">Einige dieser Funktionen werden von internen Funktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d7c57-108">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="d7c57-109">Der vertrauliche Informationstyp Kreditkartennummer verwendet beispielsweise eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind, um zu bestätigen, dass eine Zahl eine Kreditkartennummer ist.</span><span class="sxs-lookup"><span data-stu-id="d7c57-109">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="d7c57-110">In diesem Thema wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d7c57-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="d7c57-111">Weitere Informationen finden Sie unter [sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) .</span><span class="sxs-lookup"><span data-stu-id="d7c57-111">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="d7c57-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="d7c57-112">Func_us_date</span></span>

<span data-ttu-id="d7c57-113">Diese Funktion sucht nach einem Datum in dem Format, das in den USA häufig verwendet wird. Dies umfasst die Formate "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr".</span><span class="sxs-lookup"><span data-stu-id="d7c57-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="d7c57-114">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="d7c57-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="d7c57-115">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d7c57-115">Examples:</span></span>
  
- <span data-ttu-id="d7c57-116">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-116">December 2, 2016</span></span>
    
- <span data-ttu-id="d7c57-117">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="d7c57-118">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-118">dec 02 2016</span></span>
    
- <span data-ttu-id="d7c57-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-119">12/2/2016</span></span>
    
- <span data-ttu-id="d7c57-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="d7c57-120">12/02/16</span></span>
    
- <span data-ttu-id="d7c57-121">Dez-2-2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="d7c57-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="d7c57-122">12-2-16</span></span>
    
<span data-ttu-id="d7c57-123">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="d7c57-123">Accepted month names:</span></span>
  
- <span data-ttu-id="d7c57-124">Englisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-124">English</span></span>
    
  - <span data-ttu-id="d7c57-125">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="d7c57-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d7c57-126">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="d7c57-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="d7c57-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="d7c57-127">Func_eu_date</span></span>

<span data-ttu-id="d7c57-128">Diese Funktion sucht nach einem Datum in dem Format, das in der EU häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7c57-128">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="d7c57-129">(und die meisten Orte außerhalb der USA).</span><span class="sxs-lookup"><span data-stu-id="d7c57-129">(and most places outside the U.S.).</span></span> <span data-ttu-id="d7c57-130">Dies umfasst die Formate "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Tag Monat Jahr".</span><span class="sxs-lookup"><span data-stu-id="d7c57-130">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="d7c57-131">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="d7c57-131">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="d7c57-132">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d7c57-132">Examples:</span></span>
  
- <span data-ttu-id="d7c57-133">2. Dez. 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="d7c57-134">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-134">02 dec 2016</span></span>
    
- <span data-ttu-id="d7c57-135">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="d7c57-135">2 Dec 16</span></span>
    
- <span data-ttu-id="d7c57-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-136">2/12/2016</span></span>
    
- <span data-ttu-id="d7c57-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d7c57-137">02/12/16</span></span>
    
- <span data-ttu-id="d7c57-138">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="d7c57-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d7c57-139">2-12-16</span></span>
    
<span data-ttu-id="d7c57-140">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="d7c57-140">Accepted month names:</span></span>
  
- <span data-ttu-id="d7c57-141">Englisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-141">English</span></span>
    
  - <span data-ttu-id="d7c57-142">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="d7c57-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d7c57-143">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="d7c57-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="d7c57-144">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-144">Dutch</span></span>
    
  - <span data-ttu-id="d7c57-145">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="d7c57-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="d7c57-146">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="d7c57-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="d7c57-147">Französisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-147">French</span></span>
    
  - <span data-ttu-id="d7c57-148">janvier, février, Mars, Avril, Mai, Juni juillet, août, September, Oktober, Novembre, Novembre</span><span class="sxs-lookup"><span data-stu-id="d7c57-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="d7c57-149">janv.</span><span class="sxs-lookup"><span data-stu-id="d7c57-149">janv.</span></span> <span data-ttu-id="d7c57-150">févr.</span><span class="sxs-lookup"><span data-stu-id="d7c57-150">févr.</span></span> <span data-ttu-id="d7c57-151">Mars Avril Mai Juni juil.</span><span class="sxs-lookup"><span data-stu-id="d7c57-151">mars avril mai juin juil.</span></span> <span data-ttu-id="d7c57-152">août Sept.</span><span class="sxs-lookup"><span data-stu-id="d7c57-152">août sept.</span></span> <span data-ttu-id="d7c57-153">OAT.</span><span class="sxs-lookup"><span data-stu-id="d7c57-153">oct.</span></span> <span data-ttu-id="d7c57-154">Nov.</span><span class="sxs-lookup"><span data-stu-id="d7c57-154">nov.</span></span> <span data-ttu-id="d7c57-155">déc.</span><span class="sxs-lookup"><span data-stu-id="d7c57-155">déc.</span></span>
    
- <span data-ttu-id="d7c57-156">Deutsch</span><span class="sxs-lookup"><span data-stu-id="d7c57-156">German</span></span>
    
  - <span data-ttu-id="d7c57-157">Januar, Februar, März, April, Mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="d7c57-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="d7c57-158">Jan./Jän.</span><span class="sxs-lookup"><span data-stu-id="d7c57-158">Jan./Jän.</span></span> <span data-ttu-id="d7c57-159">Februar März Apr. Mai Juni Juli Aug. Sept. Okt.</span><span class="sxs-lookup"><span data-stu-id="d7c57-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="d7c57-160">Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="d7c57-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="d7c57-161">Italienisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-161">Italian</span></span>
    
  - <span data-ttu-id="d7c57-162">gennaio, febbraio, Marzo, Aprile, Maggio, Juni, Juli, Agosto, Settembre, ottobre, Novembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="d7c57-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="d7c57-163">Genn.</span><span class="sxs-lookup"><span data-stu-id="d7c57-163">genn.</span></span> <span data-ttu-id="d7c57-164">febbr.</span><span class="sxs-lookup"><span data-stu-id="d7c57-164">febbr.</span></span> <span data-ttu-id="d7c57-165">Mrz.</span><span class="sxs-lookup"><span data-stu-id="d7c57-165">mar.</span></span> <span data-ttu-id="d7c57-166">Apr.</span><span class="sxs-lookup"><span data-stu-id="d7c57-166">apr.</span></span> <span data-ttu-id="d7c57-167">Magg.</span><span class="sxs-lookup"><span data-stu-id="d7c57-167">magg.</span></span> <span data-ttu-id="d7c57-168">Juni Juli AG.</span><span class="sxs-lookup"><span data-stu-id="d7c57-168">giugno luglio ag.</span></span> <span data-ttu-id="d7c57-169">Sett.</span><span class="sxs-lookup"><span data-stu-id="d7c57-169">sett.</span></span> <span data-ttu-id="d7c57-170">Ott.</span><span class="sxs-lookup"><span data-stu-id="d7c57-170">ott.</span></span> <span data-ttu-id="d7c57-171">Nov.</span><span class="sxs-lookup"><span data-stu-id="d7c57-171">nov.</span></span> <span data-ttu-id="d7c57-172">DIC.</span><span class="sxs-lookup"><span data-stu-id="d7c57-172">dic.</span></span>
    
- <span data-ttu-id="d7c57-173">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-173">Portuguese</span></span>
    
  - <span data-ttu-id="d7c57-174">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="d7c57-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="d7c57-175">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="d7c57-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="d7c57-176">Spanisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-176">Spanish</span></span>
    
  - <span data-ttu-id="d7c57-177">enero, Febrero, Marzo, Abril, Mayo, junio, Julio, Agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="d7c57-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="d7c57-178">enero Feb.</span><span class="sxs-lookup"><span data-stu-id="d7c57-178">enero feb.</span></span> <span data-ttu-id="d7c57-179">Marzo-ABR.</span><span class="sxs-lookup"><span data-stu-id="d7c57-179">marzo abr.</span></span> <span data-ttu-id="d7c57-180">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="d7c57-180">mayo jun.</span></span> <span data-ttu-id="d7c57-181">Juli.</span><span class="sxs-lookup"><span data-stu-id="d7c57-181">jul.</span></span> <span data-ttu-id="d7c57-182">Agosto Sept./Set.</span><span class="sxs-lookup"><span data-stu-id="d7c57-182">agosto sept./set.</span></span> <span data-ttu-id="d7c57-183">OAT.</span><span class="sxs-lookup"><span data-stu-id="d7c57-183">oct.</span></span> <span data-ttu-id="d7c57-184">Nov.</span><span class="sxs-lookup"><span data-stu-id="d7c57-184">nov.</span></span> <span data-ttu-id="d7c57-185">DIC.</span><span class="sxs-lookup"><span data-stu-id="d7c57-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="d7c57-186">Func_eu_date1 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="d7c57-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="d7c57-187">Diese Funktion ist veraltet, da Sie nur portugiesische Monatsnamen unterstützt, die nun in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d7c57-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="d7c57-188">Diese Funktion sucht nach einem Datum in dem Format, das in Portugiesisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7c57-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="d7c57-189">Das Format für diese Funktion ist identisch mit der `Func_eu_date` Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="d7c57-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="d7c57-190">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d7c57-190">Examples:</span></span>
  
- <span data-ttu-id="d7c57-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="d7c57-192">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-192">02 dez 2016</span></span>
    
- <span data-ttu-id="d7c57-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="d7c57-193">2 Dez 16</span></span>
    
- <span data-ttu-id="d7c57-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-194">2/12/2016</span></span>
    
- <span data-ttu-id="d7c57-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d7c57-195">02/12/16</span></span>
    
- <span data-ttu-id="d7c57-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="d7c57-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d7c57-197">2-12-16</span></span>
    
<span data-ttu-id="d7c57-198">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="d7c57-198">Accepted month names:</span></span>
  
- <span data-ttu-id="d7c57-199">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-199">Portuguese</span></span>
    
  - <span data-ttu-id="d7c57-200">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="d7c57-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="d7c57-201">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="d7c57-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="d7c57-202">Func_eu_date2 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="d7c57-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="d7c57-203">Diese Funktion ist veraltet, da nur niederländische Monatsnamen unterstützt werden, die jetzt in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="d7c57-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="d7c57-204">Diese Funktion sucht nach einem Datum in dem Format, das in Niederländisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d7c57-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="d7c57-205">Das Format für diese Funktion ist identisch mit der `Func_eu_date` Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="d7c57-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="d7c57-206">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d7c57-206">Examples:</span></span>
  
- <span data-ttu-id="d7c57-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="d7c57-208">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-208">02 mei 2016</span></span>
    
- <span data-ttu-id="d7c57-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="d7c57-209">2 Mei 16</span></span>
    
- <span data-ttu-id="d7c57-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-210">2/12/2016</span></span>
    
- <span data-ttu-id="d7c57-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="d7c57-211">02/12/16</span></span>
    
- <span data-ttu-id="d7c57-212">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="d7c57-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="d7c57-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="d7c57-213">2-12-16</span></span>
    
<span data-ttu-id="d7c57-214">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="d7c57-214">Accepted month names:</span></span>
  
- <span data-ttu-id="d7c57-215">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-215">Dutch</span></span>
    
  - <span data-ttu-id="d7c57-216">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="d7c57-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="d7c57-217">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="d7c57-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="d7c57-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="d7c57-218">Func_expiration_date</span></span>

<span data-ttu-id="d7c57-219">Diese Funktion sucht nach einem Datum in den Formaten, die häufig von Kredit-und Debitkarten verwendet werden, wodurch Tage zugunsten von Monaten ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d7c57-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="d7c57-220">Mit dieser Funktion werden Datumsangaben im Format "month/year", "month-year", "[Month Name] Year" und "[month Kürzel] Year" abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="d7c57-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="d7c57-221">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="d7c57-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="d7c57-222">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d7c57-222">Examples:</span></span>
  
- <span data-ttu-id="d7c57-223">MM/jj--zum Beispiel 01/11 oder 1/11</span><span class="sxs-lookup"><span data-stu-id="d7c57-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="d7c57-224">MM/jjjj--zum Beispiel 01/2011 oder 1/2011</span><span class="sxs-lookup"><span data-stu-id="d7c57-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="d7c57-225">MM-jj--zum Beispiel 01-22 oder 1-11</span><span class="sxs-lookup"><span data-stu-id="d7c57-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="d7c57-226">MM-yyyy--zum Beispiel 01-2000 oder 1-2000</span><span class="sxs-lookup"><span data-stu-id="d7c57-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="d7c57-227">Die folgenden Formate unterstützen JJ oder yyyy:</span><span class="sxs-lookup"><span data-stu-id="d7c57-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="d7c57-228">Monat-yyyy--zum Beispiel. Jan-2010 oder Januar-2010 oder Jan-10 oder Januar-10</span><span class="sxs-lookup"><span data-stu-id="d7c57-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="d7c57-229">Monat yyyy--zum Beispiel "Januar 2010" oder "Jan 2010" oder "Januar 10" oder "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="d7c57-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="d7c57-230">Monatjjjj--beispielsweise "january2010" oder "Jan2010" oder "january10" oder "Jan10"</span><span class="sxs-lookup"><span data-stu-id="d7c57-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="d7c57-231">Monat/JJJJ--zum Beispiel "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="d7c57-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="d7c57-232">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="d7c57-232">Accepted month names:</span></span>
  
- <span data-ttu-id="d7c57-233">Englisch</span><span class="sxs-lookup"><span data-stu-id="d7c57-233">English</span></span>
    
  - <span data-ttu-id="d7c57-234">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="d7c57-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="d7c57-235">Jan Feb Mär Apr Mai Juni Juli Aug Sept Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="d7c57-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="d7c57-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="d7c57-236">Func_us_address</span></span>

<span data-ttu-id="d7c57-237">Diese Funktion sucht nach einem US-Bundesland Namen oder einer postalischen Abkürzung, gefolgt von einer gültigen Postleitzahl, genauso wie Sie in Postadressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7c57-237">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="d7c57-238">Die Postleitzahl muss einer der korrekten Postleitzahlen sein, die dem US-Bundesland Namen oder der Abkürzung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d7c57-238">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="d7c57-239">Der US-Bundesland Name und die Postleitzahl können nicht durch Interpunktion oder Buchstaben getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="d7c57-239">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="d7c57-240">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="d7c57-240">Examples:</span></span>
  
- <span data-ttu-id="d7c57-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="d7c57-241">Washington 98052</span></span>
    
- <span data-ttu-id="d7c57-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="d7c57-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="d7c57-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="d7c57-243">WA 98052</span></span>
    
- <span data-ttu-id="d7c57-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="d7c57-244">WA 98052-9998</span></span>
    

