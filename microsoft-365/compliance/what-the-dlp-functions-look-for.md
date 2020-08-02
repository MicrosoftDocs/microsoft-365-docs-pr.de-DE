---
title: Was die Funktionen zur Verhinderung von Datenverlust (DLP) suchen
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
description: Erfahren Sie, worauf die Funktionen zur Verhinderung von Datenverlust (DLP) achten.
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536310"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="e23ab-103">Wonach die DLP-Funktionen suchen</span><span class="sxs-lookup"><span data-stu-id="e23ab-103">What the DLP functions look for</span></span>

<span data-ttu-id="e23ab-104">Die Verhinderung von Datenverlust (DLP) umfasst vertrauliche Informationstypen wie Kreditkartennummer und EU-Debitkarten-Nummer, die Sie in ihren DLP-Richtlinien verwenden können.</span><span class="sxs-lookup"><span data-stu-id="e23ab-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="e23ab-105">Diese Typen vertraulicher Informationen suchen nach einem bestimmten Muster und bestätigen es, indem Sie eine ordnungsgemäße Formatierung sicherstellen, Prüfsummen erzwingen und nach relevanten Schlüsselwörtern oder anderen Informationen suchen.</span><span class="sxs-lookup"><span data-stu-id="e23ab-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="e23ab-106">Einige dieser Funktionen werden von internen Funktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e23ab-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="e23ab-107">Der vertrauliche Informationstyp Kreditkartennummer verwendet beispielsweise eine Funktion, um nach Datumsangaben zu suchen, die wie ein Ablaufdatum formatiert sind, um zu bestätigen, dass eine Zahl eine Kreditkartennummer ist.</span><span class="sxs-lookup"><span data-stu-id="e23ab-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="e23ab-108">In diesem Artikel wird erläutert, wonach diese Funktionen suchen, damit Sie besser verstehen, wie die vordefinierten Typen vertraulicher Informationen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="e23ab-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="e23ab-109">Weitere Informationen finden Sie unter [sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) .</span><span class="sxs-lookup"><span data-stu-id="e23ab-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="e23ab-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="e23ab-110">Func_us_date</span></span>

<span data-ttu-id="e23ab-111">Diese Funktion sucht nach einem Datum in dem Format, das in den USA häufig verwendet wird. Dies umfasst die Formate "Monat/Tag/Jahr", "Monat-Tag-Jahr" und "Monat Tag Jahr".</span><span class="sxs-lookup"><span data-stu-id="e23ab-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="e23ab-112">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="e23ab-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="e23ab-113">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e23ab-113">Examples:</span></span>
  
- <span data-ttu-id="e23ab-114">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-114">December 2, 2016</span></span>
    
- <span data-ttu-id="e23ab-115">2. Dezember 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="e23ab-116">Dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-116">dec 02 2016</span></span>
    
- <span data-ttu-id="e23ab-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-117">12/2/2016</span></span>
    
- <span data-ttu-id="e23ab-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="e23ab-118">12/02/16</span></span>
    
- <span data-ttu-id="e23ab-119">Dez-2-2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="e23ab-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="e23ab-120">12-2-16</span></span>
    
<span data-ttu-id="e23ab-121">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="e23ab-121">Accepted month names:</span></span>
  
- <span data-ttu-id="e23ab-122">English</span><span class="sxs-lookup"><span data-stu-id="e23ab-122">English</span></span>
    
  - <span data-ttu-id="e23ab-123">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="e23ab-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e23ab-124">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="e23ab-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="e23ab-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="e23ab-125">Func_eu_date</span></span>

<span data-ttu-id="e23ab-126">Diese Funktion sucht nach einem Datum in dem Format, das in der EU häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e23ab-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="e23ab-127">(und die meisten Orte außerhalb der USA), wie "Tag/Monat/Jahr", "Tag-Monat-Jahr" und "Tag Monat Jahr".</span><span class="sxs-lookup"><span data-stu-id="e23ab-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="e23ab-128">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="e23ab-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e23ab-129">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e23ab-129">Examples:</span></span>
  
- <span data-ttu-id="e23ab-130">2. Dez. 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="e23ab-131">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-131">02 dec 2016</span></span>
    
- <span data-ttu-id="e23ab-132">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="e23ab-132">2 Dec 16</span></span>
    
- <span data-ttu-id="e23ab-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-133">2/12/2016</span></span>
    
- <span data-ttu-id="e23ab-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e23ab-134">02/12/16</span></span>
    
- <span data-ttu-id="e23ab-135">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="e23ab-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e23ab-136">2-12-16</span></span>
    
<span data-ttu-id="e23ab-137">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="e23ab-137">Accepted month names:</span></span>
  
- <span data-ttu-id="e23ab-138">English</span><span class="sxs-lookup"><span data-stu-id="e23ab-138">English</span></span>
    
  - <span data-ttu-id="e23ab-139">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="e23ab-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e23ab-140">Jan. Feb. Mär. Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="e23ab-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="e23ab-141">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="e23ab-141">Dutch</span></span>
    
  - <span data-ttu-id="e23ab-142">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="e23ab-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e23ab-143">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept Oct Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="e23ab-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="e23ab-144">Französisch</span><span class="sxs-lookup"><span data-stu-id="e23ab-144">French</span></span>
    
  - <span data-ttu-id="e23ab-145">janvier, février, Mars, Avril, Mai, Juni juillet, août, September, Oktober, Novembre, Novembre</span><span class="sxs-lookup"><span data-stu-id="e23ab-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="e23ab-146">janv.</span><span class="sxs-lookup"><span data-stu-id="e23ab-146">janv.</span></span> <span data-ttu-id="e23ab-147">févr.</span><span class="sxs-lookup"><span data-stu-id="e23ab-147">févr.</span></span> <span data-ttu-id="e23ab-148">Mars Avril Mai Juni juil.</span><span class="sxs-lookup"><span data-stu-id="e23ab-148">mars avril mai juin juil.</span></span> <span data-ttu-id="e23ab-149">août Sept.</span><span class="sxs-lookup"><span data-stu-id="e23ab-149">août sept.</span></span> <span data-ttu-id="e23ab-150">OAT.</span><span class="sxs-lookup"><span data-stu-id="e23ab-150">oct.</span></span> <span data-ttu-id="e23ab-151">Nov.</span><span class="sxs-lookup"><span data-stu-id="e23ab-151">nov.</span></span> <span data-ttu-id="e23ab-152">déc.</span><span class="sxs-lookup"><span data-stu-id="e23ab-152">déc.</span></span>
    
- <span data-ttu-id="e23ab-153">Deutsch</span><span class="sxs-lookup"><span data-stu-id="e23ab-153">German</span></span>
    
  - <span data-ttu-id="e23ab-154">Januar, Februar, März, April, Mai, Juni Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="e23ab-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="e23ab-155">Jan./Jän.</span><span class="sxs-lookup"><span data-stu-id="e23ab-155">Jan./Jän.</span></span> <span data-ttu-id="e23ab-156">Februar März Apr. Mai Juni Juli Aug. Sept. Okt.</span><span class="sxs-lookup"><span data-stu-id="e23ab-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="e23ab-157">Nov. Dez.</span><span class="sxs-lookup"><span data-stu-id="e23ab-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="e23ab-158">Italienisch</span><span class="sxs-lookup"><span data-stu-id="e23ab-158">Italian</span></span>
    
  - <span data-ttu-id="e23ab-159">gennaio, febbraio, Marzo, Aprile, Maggio, Juni, Juli, Agosto, Settembre, ottobre, Novembre, Dezember</span><span class="sxs-lookup"><span data-stu-id="e23ab-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="e23ab-160">Genn.</span><span class="sxs-lookup"><span data-stu-id="e23ab-160">genn.</span></span> <span data-ttu-id="e23ab-161">febbr.</span><span class="sxs-lookup"><span data-stu-id="e23ab-161">febbr.</span></span> <span data-ttu-id="e23ab-162">Mrz.</span><span class="sxs-lookup"><span data-stu-id="e23ab-162">mar.</span></span> <span data-ttu-id="e23ab-163">Apr.</span><span class="sxs-lookup"><span data-stu-id="e23ab-163">apr.</span></span> <span data-ttu-id="e23ab-164">Magg.</span><span class="sxs-lookup"><span data-stu-id="e23ab-164">magg.</span></span> <span data-ttu-id="e23ab-165">Juni Juli AG.</span><span class="sxs-lookup"><span data-stu-id="e23ab-165">giugno luglio ag.</span></span> <span data-ttu-id="e23ab-166">Sett.</span><span class="sxs-lookup"><span data-stu-id="e23ab-166">sett.</span></span> <span data-ttu-id="e23ab-167">Ott.</span><span class="sxs-lookup"><span data-stu-id="e23ab-167">ott.</span></span> <span data-ttu-id="e23ab-168">Nov.</span><span class="sxs-lookup"><span data-stu-id="e23ab-168">nov.</span></span> <span data-ttu-id="e23ab-169">DIC.</span><span class="sxs-lookup"><span data-stu-id="e23ab-169">dic.</span></span>
    
- <span data-ttu-id="e23ab-170">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="e23ab-170">Portuguese</span></span>
    
  - <span data-ttu-id="e23ab-171">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="e23ab-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e23ab-172">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="e23ab-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="e23ab-173">Spanisch</span><span class="sxs-lookup"><span data-stu-id="e23ab-173">Spanish</span></span>
    
  - <span data-ttu-id="e23ab-174">enero, Febrero, Marzo, Abril, Mayo, junio, Julio, Agosto, Septiembre, Octubre, Noviembre, Diciembre</span><span class="sxs-lookup"><span data-stu-id="e23ab-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="e23ab-175">enero Feb.</span><span class="sxs-lookup"><span data-stu-id="e23ab-175">enero feb.</span></span> <span data-ttu-id="e23ab-176">Marzo-ABR.</span><span class="sxs-lookup"><span data-stu-id="e23ab-176">marzo abr.</span></span> <span data-ttu-id="e23ab-177">Mayo Jun.</span><span class="sxs-lookup"><span data-stu-id="e23ab-177">mayo jun.</span></span> <span data-ttu-id="e23ab-178">Juli.</span><span class="sxs-lookup"><span data-stu-id="e23ab-178">jul.</span></span> <span data-ttu-id="e23ab-179">Agosto Sept./Set.</span><span class="sxs-lookup"><span data-stu-id="e23ab-179">agosto sept./set.</span></span> <span data-ttu-id="e23ab-180">OAT.</span><span class="sxs-lookup"><span data-stu-id="e23ab-180">oct.</span></span> <span data-ttu-id="e23ab-181">Nov.</span><span class="sxs-lookup"><span data-stu-id="e23ab-181">nov.</span></span> <span data-ttu-id="e23ab-182">DIC.</span><span class="sxs-lookup"><span data-stu-id="e23ab-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="e23ab-183">Func_eu_date1 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e23ab-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e23ab-184">Diese Funktion ist veraltet, da Sie nur portugiesische Monatsnamen unterstützt, die nun in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e23ab-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e23ab-185">Diese Funktion sucht nach einem Datum in dem Format, das in Portugiesisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e23ab-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="e23ab-186">Das Format für diese Funktion ist identisch mit der `Func_eu_date` Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="e23ab-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e23ab-187">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e23ab-187">Examples:</span></span>
  
- <span data-ttu-id="e23ab-188">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="e23ab-189">02 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-189">02 dez 2016</span></span>
    
- <span data-ttu-id="e23ab-190">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="e23ab-190">2 Dez 16</span></span>
    
- <span data-ttu-id="e23ab-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-191">2/12/2016</span></span>
    
- <span data-ttu-id="e23ab-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e23ab-192">02/12/16</span></span>
    
- <span data-ttu-id="e23ab-193">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="e23ab-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e23ab-194">2-12-16</span></span>
    
<span data-ttu-id="e23ab-195">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="e23ab-195">Accepted month names:</span></span>
  
- <span data-ttu-id="e23ab-196">Portugiesisch</span><span class="sxs-lookup"><span data-stu-id="e23ab-196">Portuguese</span></span>
    
  - <span data-ttu-id="e23ab-197">Janeiro, Fevereiro, Março, Marco, Abril, Maio, Junho, Julho, Agosto, Setembro, Outubro, Novembro, Dezembro</span><span class="sxs-lookup"><span data-stu-id="e23ab-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e23ab-198">Jan FEV Mär ABR Mai Jun Jul ago festgelegt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="e23ab-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="e23ab-199">Func_eu_date2 (veraltet)</span><span class="sxs-lookup"><span data-stu-id="e23ab-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e23ab-200">Diese Funktion ist veraltet, da nur niederländische Monatsnamen unterstützt werden, die jetzt in der `Func_eu_date` obigen Funktion enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e23ab-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e23ab-201">Diese Funktion sucht nach einem Datum in dem Format, das in Niederländisch häufig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e23ab-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="e23ab-202">Das Format für diese Funktion ist identisch mit der `Func_eu_date` Unterschiede nur in der verwendeten Sprache.</span><span class="sxs-lookup"><span data-stu-id="e23ab-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e23ab-203">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e23ab-203">Examples:</span></span>
  
- <span data-ttu-id="e23ab-204">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="e23ab-205">02 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-205">02 mei 2016</span></span>
    
- <span data-ttu-id="e23ab-206">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="e23ab-206">2 Mei 16</span></span>
    
- <span data-ttu-id="e23ab-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-207">2/12/2016</span></span>
    
- <span data-ttu-id="e23ab-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e23ab-208">02/12/16</span></span>
    
- <span data-ttu-id="e23ab-209">2-Mei-2016</span><span class="sxs-lookup"><span data-stu-id="e23ab-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="e23ab-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e23ab-210">2-12-16</span></span>
    
<span data-ttu-id="e23ab-211">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="e23ab-211">Accepted month names:</span></span>
  
- <span data-ttu-id="e23ab-212">Niederländisch</span><span class="sxs-lookup"><span data-stu-id="e23ab-212">Dutch</span></span>
    
  - <span data-ttu-id="e23ab-213">Januari, februari, maart, April, Mei, Juni, Juli, Augustus, September, ocktober, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="e23ab-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e23ab-214">Jan Feb maart Apr Mei Jun Jul Aug Sep Sept. Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="e23ab-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="e23ab-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="e23ab-215">Func_expiration_date</span></span>

<span data-ttu-id="e23ab-216">Diese Funktion sucht nach einem Datum in den Formaten, die häufig von Kredit-und Debitkarten verwendet werden, wodurch Tage zugunsten von Monaten ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e23ab-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="e23ab-217">Mit dieser Funktion werden Datumsangaben im Format "month/year", "month-year", "[Month Name] Year" und "[month Kürzel] Year" abgeglichen.</span><span class="sxs-lookup"><span data-stu-id="e23ab-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="e23ab-218">Bei den Namen oder Abkürzungen von Monaten wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="e23ab-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e23ab-219">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e23ab-219">Examples:</span></span>
  
- <span data-ttu-id="e23ab-220">MM/jj--zum Beispiel 01/11 oder 1/11</span><span class="sxs-lookup"><span data-stu-id="e23ab-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="e23ab-221">MM/jjjj--zum Beispiel 01/2011 oder 1/2011</span><span class="sxs-lookup"><span data-stu-id="e23ab-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="e23ab-222">MM-jj--zum Beispiel 01-22 oder 1-11</span><span class="sxs-lookup"><span data-stu-id="e23ab-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="e23ab-223">MM-yyyy--zum Beispiel 01-2000 oder 1-2000</span><span class="sxs-lookup"><span data-stu-id="e23ab-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="e23ab-224">Die folgenden Formate unterstützen JJ oder yyyy:</span><span class="sxs-lookup"><span data-stu-id="e23ab-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="e23ab-225">Monat-yyyy--zum Beispiel Jan-2010 oder Januar-2010 oder Jan-10 oder Januar-10</span><span class="sxs-lookup"><span data-stu-id="e23ab-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="e23ab-226">Monat yyyy--zum Beispiel "Januar 2010" oder "Jan 2010" oder "Januar 10" oder "Jan 10"</span><span class="sxs-lookup"><span data-stu-id="e23ab-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="e23ab-227">Monatjjjj--beispielsweise "january2010" oder "Jan2010" oder "january10" oder "Jan10"</span><span class="sxs-lookup"><span data-stu-id="e23ab-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="e23ab-228">Monat/JJJJ--zum Beispiel "Januar/2010" oder "Jan/2010" oder "Januar/10" oder "Jan/10"</span><span class="sxs-lookup"><span data-stu-id="e23ab-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="e23ab-229">Akzeptierte Monatsnamen:</span><span class="sxs-lookup"><span data-stu-id="e23ab-229">Accepted month names:</span></span>
  
- <span data-ttu-id="e23ab-230">English</span><span class="sxs-lookup"><span data-stu-id="e23ab-230">English</span></span>
    
  - <span data-ttu-id="e23ab-231">Januar, Februar, März, April, Mai, Juni, Juli, August, September, Oktober, November, Dezember</span><span class="sxs-lookup"><span data-stu-id="e23ab-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e23ab-232">Jan Feb Mär Apr Mai Juni Juli Aug Sept Okt Nov Dez</span><span class="sxs-lookup"><span data-stu-id="e23ab-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="e23ab-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="e23ab-233">Func_us_address</span></span>

<span data-ttu-id="e23ab-234">Diese Funktion sucht nach einem US-Bundesland Namen oder einer postalischen Abkürzung, gefolgt von einer gültigen Postleitzahl, so wie Sie in Postadressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e23ab-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="e23ab-235">Die Postleitzahl muss einer der korrekten Postleitzahlen sein, die dem US-Bundesland Namen oder der Abkürzung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e23ab-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="e23ab-236">Der US-Bundesland Name und die Postleitzahl können nicht durch Interpunktion oder Buchstaben getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="e23ab-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="e23ab-237">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="e23ab-237">Examples:</span></span>
  
- <span data-ttu-id="e23ab-238">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="e23ab-238">Washington 98052</span></span>
    
- <span data-ttu-id="e23ab-239">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e23ab-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="e23ab-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="e23ab-240">WA 98052</span></span>
    
- <span data-ttu-id="e23ab-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e23ab-241">WA 98052-9998</span></span>
    

