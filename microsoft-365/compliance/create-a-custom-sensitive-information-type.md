---
title: Erstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/17/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie benutzerdefinierten Typen für vertrauliche Informationen für DLP in der grafischen Benutzeroberfläche im Security & Compliance Center erstellen, ändern, entfernen und testen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 59d16ed662ff1b577bbb6c8388c5d27836832c1f
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681721"
---
<!-- rename md file to match the display name -->
# <a name="create-a-custom-sensitive-information-type-in-the-security--compliance-center"></a><span data-ttu-id="dc888-103">Erstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dc888-103">Create a custom sensitive information type in the Security & Compliance Center</span></span>

<span data-ttu-id="dc888-104">Lesen Sie diesen Artikel, zumErstellen eines benutzerdefinierten vertraulichen Informationstyps im Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span><span class="sxs-lookup"><span data-stu-id="dc888-104">Read this article to create a custom sensitive information type in the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="dc888-105">Die benutzerdefinierte Typen vertraulicher Informationen, die Sie mit dieser Methode erstellen, werden zum Regelpaket namens `Microsoft.SCCManaged.CustomRulePack`hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dc888-105">The custom sensitive information types that you create by using this method are added to the rule package named `Microsoft.SCCManaged.CustomRulePack`.</span></span>

<span data-ttu-id="dc888-106">Sie können auch benutzerdefinierte vertrauliche Informationstypen mithilfe von PowerShell und genauer Datenübereinstimmung erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc888-106">You can also create custom sensitive information types by using PowerShell and Exact Data Match capabilities.</span></span> <span data-ttu-id="dc888-107">Weitere Informationen zu diesen Methoden finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="dc888-107">To learn more about those methods, see:</span></span>
- [<span data-ttu-id="dc888-108">Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell</span><span class="sxs-lookup"><span data-stu-id="dc888-108">Create a custom sensitive information type in Security & Compliance Center PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [<span data-ttu-id="dc888-109">Erstellen eines benutzerdefinierten vertraulichen Informationstyps für DLP mit genauer Datenübereinstimmung (EDM)</span><span class="sxs-lookup"><span data-stu-id="dc888-109">Create a custom sensitive information type for DLP with Exact Data Match (EDM)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

> [!NOTE]
> <span data-ttu-id="dc888-110">Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Sprachen mit Doublebyte-Zeichensätzen für:</span><span class="sxs-lookup"><span data-stu-id="dc888-110">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="dc888-111">Chinesisch (vereinfacht)</span><span class="sxs-lookup"><span data-stu-id="dc888-111">Chinese (simplified)</span></span>
> - <span data-ttu-id="dc888-112">Chinesisch (traditionell)</span><span class="sxs-lookup"><span data-stu-id="dc888-112">Chinese (traditional)</span></span>
> - <span data-ttu-id="dc888-113">Koreanisch</span><span class="sxs-lookup"><span data-stu-id="dc888-113">Korean</span></span>
> - <span data-ttu-id="dc888-114">Japanisch</span><span class="sxs-lookup"><span data-stu-id="dc888-114">Japanese</span></span>
>
><span data-ttu-id="dc888-115">Diese Unterstützung ist für vertrauliche Informationstypen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc888-115">This support is available for sensitive information types.</span></span> <span data-ttu-id="dc888-116">Weitere Informationen hierzu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).</span><span class="sxs-lookup"><span data-stu-id="dc888-116">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dc888-117">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="dc888-117">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="dc888-118">Sie sollten über globale Administrator-oder Compliance-Administratorberechtigungen verfügen, um über die Benutzeroberfläche einen benutzerdefinierten vertraulichen Informationstyp erstellen, testen und bereitstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="dc888-118">You should have Global admin or Compliance admin permissions to create, test, and deploy a custom sensitive information type through the UI.</span></span> <span data-ttu-id="dc888-119">Informationen hierzu finden Sie unter[Zu Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span><span class="sxs-lookup"><span data-stu-id="dc888-119">See [About admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.</span></span>

- <span data-ttu-id="dc888-120">Ihre Organisation muss über ein Abonnement verfügen, z. B. Office 365 Enterprise, das Verhinderung von Datenverlust (DLP) beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="dc888-120">Your organization must have a subscription, such as Office 365 Enterprise, that includes Data Loss Prevention (DLP).</span></span> <span data-ttu-id="dc888-121">Siehe [Nachrichtenrichtlinie und Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span><span class="sxs-lookup"><span data-stu-id="dc888-121">See [Messaging Policy and Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc).</span></span> 

- <span data-ttu-id="dc888-p106">Benutzerdefinierte Typen für vertrauliche Informationen erfordern Kenntnisse über reguläre Ausdrücke (RegEx). Weitere Informationen über das Modul Boost.RegEx (vormals als RegEx++ bezeichnet), das für die Textverarbeitung verwendet wird, finden Sie unter [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span><span class="sxs-lookup"><span data-stu-id="dc888-p106">Custom sensitive information types require familiarity with regular expressions (RegEx). For more information about the Boost.RegEx (formerly known as RegEx++) engine that's used for processing the text, see [Boost.Regex 5.1.3](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/).</span></span>

  <span data-ttu-id="dc888-124">Der Kundendienst und Support von Microsoft kann beim Erstellen benutzerdefinierter Klassifizierungen oder Muster für reguläre Ausdrücke keine Unterstützung anbieten.</span><span class="sxs-lookup"><span data-stu-id="dc888-124">Microsoft Customer Service & Support can't assist with creating custom classifications or regular expression patterns.</span></span> <span data-ttu-id="dc888-125">Die Supportmitarbeiter können eingeschränkten Support für das Feature bereitstellen, beispielsweise Muster für reguläre Ausdrücke zu Testzwecken oder Hilfestellung bei der Problembehandlung eines bestehenden Musters für reguläre Ausdrücke, das nicht wie erwartet ausgelöst wird, es können jedoch keine Zusicherungen dahingehend gegeben werden, dass benutzerdefinierte Entwicklungen für die Inhaltsübereinstimmung Ihre Anforderungen oder Verpflichtungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="dc888-125">Support engineers can provide limited support for the feature, such as, providing sample regular expression patterns for testing purposes, or assisting with troubleshooting an existing regular expression pattern that's not triggering as expected, but can't provide assurances that any custom content-matching development will fulfill your requirements or obligations.</span></span>

- <span data-ttu-id="dc888-126">DLP verwendet den Suchcrawler zum Erkennen und Klassifizieren vertraulicher Informationen in SharePoint Online- und OneDrive for Business-Websites.</span><span class="sxs-lookup"><span data-stu-id="dc888-126">DLP uses the search crawler to identify and classify sensitive information in SharePoint Online and OneDrive for Business sites.</span></span> <span data-ttu-id="dc888-127">Um den neuen benutzerdefinierten vertraulichen Informationstyp in vorhandenen Inhalten zu identifizieren, müssen die Inhalte erneut durchforstet werden.</span><span class="sxs-lookup"><span data-stu-id="dc888-127">To identify your new custom sensitive information type in existing content, the content must be re-crawled.</span></span> <span data-ttu-id="dc888-128">Inhalte werden basierend auf einem Zeitplan durchforstet, aber Sie können Inhalte für eine Websitesammlung, Liste oder Bibliothek manuell erneut durchforsten.</span><span class="sxs-lookup"><span data-stu-id="dc888-128">Content is crawled based on a schedule, but you can manually re-crawl content for a site collection, list, or library.</span></span> <span data-ttu-id="dc888-129">Weitere Informationen finden Sie unter [Manuelles Anfordern des Durchforstens und des erneuten Indizierens einer Website, Bibliothek oder Liste](https://docs.microsoft.com/sharepoint/crawl-site-content).</span><span class="sxs-lookup"><span data-stu-id="dc888-129">For more information, see [Manually request crawling and re-indexing of a site, a library or a list](https://docs.microsoft.com/sharepoint/crawl-site-content).</span></span>

## <a name="create-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="dc888-130">Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dc888-130">Create custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="dc888-131">Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="dc888-131">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

<span data-ttu-id="dc888-132">Die Einstellungen sind selbsterklärend und werden auf der entsprechenden Seite des Assistenten erläutert:</span><span class="sxs-lookup"><span data-stu-id="dc888-132">The settings are fairly self-evident, and are explained on the associate page of the wizard:</span></span>

- <span data-ttu-id="dc888-133">**Name**</span><span class="sxs-lookup"><span data-stu-id="dc888-133">**Name**</span></span>

- <span data-ttu-id="dc888-134">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="dc888-134">**Description**</span></span>

- <span data-ttu-id="dc888-135">**Näherung**</span><span class="sxs-lookup"><span data-stu-id="dc888-135">**Proximity**</span></span>

- <span data-ttu-id="dc888-136">**Zuverlässigkeitsstufe**</span><span class="sxs-lookup"><span data-stu-id="dc888-136">**Confidence level**</span></span>

- <span data-ttu-id="dc888-137">**Primäres Muster-Element** (Schlüsselwörter, reguläre Ausdrücke oder Wörterbuch)</span><span class="sxs-lookup"><span data-stu-id="dc888-137">**Primary pattern element** (keywords, regular expression, or dictionary)</span></span>

- <span data-ttu-id="dc888-138">Optionale Elemente für **unterstützende Muster** (Schlüsselwörter, reguläre Ausdrücke oder Wörterbuch) und einen entsprechenden Wert für **Mindestkosten**.</span><span class="sxs-lookup"><span data-stu-id="dc888-138">Optional **Supporting pattern elements** (keywords, regular expression, or dictionary) and a corresponding **Minimum cost** value.</span></span>

<span data-ttu-id="dc888-p109">Sehen Sie sich das folgende Szenario an: Sie möchten einen benutzerdefinierten Typ für vertrauliche Informationen, der neunstellige Mitarbeiternummern in Inhalten erkennt, zusammen mit den Schlüsselwörtern „Mitarbeiter“, „ID“ und „Ausweis“. Um diesen benutzerdefinierten Typ für vertrauliche Information zu erstellen, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dc888-p109">Here's a scenario: You want a custom sensitive information type that detects 9-digit employee numbers in content, along with the keywords "employee" "ID" and "badge". To create this custom sensitive information type, do the following steps:</span></span>

1. <span data-ttu-id="dc888-141">Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="dc888-141">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and click **Create**.</span></span>

    ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Erstellen“](../media/scc-cust-sens-info-type-new.png)

2. <span data-ttu-id="dc888-143">Geben Sie auf der Seite **Namen und Beschreibung auswählen**, die geöffnet wird, die folgenden Werte ein:</span><span class="sxs-lookup"><span data-stu-id="dc888-143">In the **Choose a name and description** page that opens, enter the following values:</span></span>

  - <span data-ttu-id="dc888-144">**Name**: Mitarbeiter-ID.</span><span class="sxs-lookup"><span data-stu-id="dc888-144">**Name**: Employee ID.</span></span>

  - <span data-ttu-id="dc888-145">**Beschreibung**: Neunstellige Contoso-Mitarbeiter-ID-Nummern erkennen.</span><span class="sxs-lookup"><span data-stu-id="dc888-145">**Description**: Detect nine-digit Contoso employee ID numbers.</span></span>

    ![Seite „Name und Beschreibung“](../media/scc-cust-sens-info-type-new-name-desc.png)

    <span data-ttu-id="dc888-147">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc888-147">When you're finished, click **Next**.</span></span>

3. <span data-ttu-id="dc888-148">Klicken Sie auf der Seite **Anforderungen für Übereinstimmung** auf **Element hinzufügen**, um die folgenden Einstellungen zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="dc888-148">In the **Requirements for matching** page that opens, click **Add an element** configure the following settings:</span></span>

    - <span data-ttu-id="dc888-149">**Inhalt erkennen, der Folgendes enthält**:</span><span class="sxs-lookup"><span data-stu-id="dc888-149">**Detect content containing**:</span></span>
 
      <span data-ttu-id="dc888-p110">a. Klicken Sie auf die Option, dass **eines der folgenden Elemente enthalten sein muss**, und wählen Sie **Regulärer Ausdruck** aus.</span><span class="sxs-lookup"><span data-stu-id="dc888-p110">a. Click **Any of these** and select **Regular expression**.</span></span>

      <span data-ttu-id="dc888-p111">b. Geben Sie in dem Feld für den regulären Ausdruck `(\s)(\d{9})(\s)` ein (neunstellige Zahlen umgeben von einem Leerzeichen).</span><span class="sxs-lookup"><span data-stu-id="dc888-p111">b. In the regular expression box, enter `(\s)(\d{9})(\s)` (nine-digit numbers surrounded by white space).</span></span>
  
    - <span data-ttu-id="dc888-154">**Unterstützende Elemente**: Klicken Sie auf **Unterstützende Elemente hinzufügen**, und wählen Sie **Enthält die folgende Schlüsselwortliste** aus.</span><span class="sxs-lookup"><span data-stu-id="dc888-154">**Supporting elements**: Click **Add supporting elements** and select **Contains this keyword list**.</span></span>

    - <span data-ttu-id="dc888-155">Konfigurieren Sie in dem Bereich **Enthält die folgende Schlüsselwortliste**, der angezeigt wird, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="dc888-155">In the **Contains this keyword list** area that appears, configure the following settings:</span></span>

      - <span data-ttu-id="dc888-156">**Schlüsselwortliste**: Geben Sie den folgenden Wert ein: Mitarbeiter,ID,Ausweis.</span><span class="sxs-lookup"><span data-stu-id="dc888-156">**Keyword list**: Enter the following value: employee,ID,badge.</span></span>

      - <span data-ttu-id="dc888-157">**Mindestanzahl**: Behalten Sie den Standardwert 1 bei.</span><span class="sxs-lookup"><span data-stu-id="dc888-157">**Minimum count**: Leave the default value 1.</span></span>

    - <span data-ttu-id="dc888-158">Behalten Sie den Standardwert 60 für den **Zuverlässigkeitsgrad** bei.</span><span class="sxs-lookup"><span data-stu-id="dc888-158">Leave the default **Confidence level** value 60.</span></span> 

    - <span data-ttu-id="dc888-159">Behalten Sie den Standardwert 300 für den **Zeichenabstand** bei.</span><span class="sxs-lookup"><span data-stu-id="dc888-159">Leave the default **Character proximity** value 300.</span></span>

    ![Seite „Anforderungen für Übereinstimmung“](../media/scc-cust-sens-info-type-new-reqs.png)

    <span data-ttu-id="dc888-161">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc888-161">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="dc888-162">Überprüfen Sie auf der Seite **Überprüfen und Abschließen** die Einstellungen, und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dc888-162">On the **Review and finalize** page that opens, review the settings and click **Finish**.</span></span>

    ![Seite „Überprüfen und Abschließen“](../media/scc-cust-sens-info-type-new-review.png)

5. <span data-ttu-id="dc888-p112">Auf der nächsten Seite werden Sie aufgefordert, den neuen benutzerdefinierten Typ für vertrauliche Informationen zu testen. Klicken Sie dazu auf **Ja**. Weitere Informationen finden Sie unter [Testen von benutzerdefinierten Typen für vertrauliche Information im Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). Um die Regel später zu testen, klicken Sie auf **Nein**.</span><span class="sxs-lookup"><span data-stu-id="dc888-p112">The next page encourages you to test the new custom sensitive information type by clicking **Yes**. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center). To test the rule later, click **No**.</span></span>

    ![Testempfehlungsseite](../media/scc-cust-sens-info-type-new-test.png)

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="dc888-168">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="dc888-168">How do you know this worked?</span></span>

<span data-ttu-id="dc888-169">Um sicherzustellen, dass Sie einen neuen Typ für vertrauliche Informationen erstellt haben, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dc888-169">To verify that you've successfully created a new sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="dc888-170">Wechseln Sie zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und bestätigen Sie, dass der neue benutzerdefinierte Typ für vertrauliche Informationen aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="dc888-170">Go to **Classifications** \> **Sensitive info types** and verify the new custom sensitive information type is listed.</span></span>

  - <span data-ttu-id="dc888-p113">Testen Sie den neuen benutzerdefinierten Typ für vertrauliche Informationen. Weitere Informationen finden Sie unter [Testen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="dc888-p113">Test the new custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="modify-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="dc888-173">Ändern von benutzerdefinierten Typen für vertrauliche Information im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dc888-173">Modify custom sensitive information types in the Security & Compliance Center</span></span>

<span data-ttu-id="dc888-174">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="dc888-174">**Notes**:</span></span>
<!-- check to see if this note contradicts the guidance in "customize a built in sensitive information type customize-a-built-in-sensitive-information-type it sure seems like it does-->
- <span data-ttu-id="dc888-p114">Sie können nur benutzerdefinierte Typen für vertrauliche Informationen ändern; integrierte Typen vertraulicher Informationen können nicht geändert werden. Sie können aber PowerShell verwenden, um integrierte Typen vertraulicher Informationen zu exportieren, diese anzupassen und sie als benutzerdefinierte Typen vertraulicher Informationen zu importieren. Weitere Informationen finden Sie unter [Anpassen eines integrierten benutzerdefinierten Typs für vertrauliche Informationen](customize-a-built-in-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="dc888-p114">You can only modify custom sensitive information types; you can't modify built-in sensitive information types. But you can use PowerShell to export built-in custom sensitive information types, customize them, and import them as custom sensitive information types. For more information, see [Customize a built-in sensitive information type](customize-a-built-in-sensitive-information-type.md).</span></span>

- <span data-ttu-id="dc888-p115">Sie können nur benutzerdefinierte Typen für vertrauliche Informationen ändern, die Sie in der Benutzeroberfläche erstellt haben. Wenn Sie das [PowerShell-Verfahren](create-a-custom-sensitive-information-type-in-scc-powershell.md) zum Importieren eines Regelpakets für benutzerdefinierte Typen für vertrauliche Informationen verwendet haben, erhalten Sie eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="dc888-p115">You can only modify custom sensitive information types that you created in the UI. If you used the [PowerShell procedure](create-a-custom-sensitive-information-type-in-scc-powershell.md) to import a custom sensitive information type rule package, you'll get an error.</span></span>

<span data-ttu-id="dc888-180">Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und wählen Sie den benutzerdefinierten Typ vertraulicher Informationen aus, den Sie ändern möchten. Klicken Sie anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="dc888-180">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**, select the custom sensitive information type that you want to modify, and then click **Edit**.</span></span>

  ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Bearbeiten“](../media/scc-cust-sens-info-type-edit.png)

<span data-ttu-id="dc888-p116">Hier stehen die gleichen Optionen wie beim Erstellen des benutzerdefinierten Typs für vertrauliche Informationen im Security & Compliance Center zur Verfügung. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="dc888-p116">The same options are available here as when you created the custom sensitive information type in the Security & Compliance Center. For more information, see [Create custom sensitive information types in the Security & Compliance Center](#create-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="dc888-184">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="dc888-184">How do you know this worked?</span></span>

<span data-ttu-id="dc888-185">Um sicherzustellen, dass Sie einen neuen Typ für vertrauliche Informationen erfolgreich geändert haben, führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="dc888-185">To verify that you've successfully modified a sensitive information type, do any of the following steps:</span></span>

  - <span data-ttu-id="dc888-186">Wechseln Sie zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, um die Eigenschaften des geänderten benutzerdefinierten Typs vertraulicher Informationen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dc888-186">Go to **Classifications** \> **Sensitive info types** to verify the properties of the modified custom sensitive information type.</span></span> 

  - <span data-ttu-id="dc888-p117">Testen Sie den geänderten benutzerdefinierten Typ für vertrauliche Informationen. Weitere Informationen finden Sie unter [Testen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span><span class="sxs-lookup"><span data-stu-id="dc888-p117">Test the modified custom sensitive information type. For more information, see [Test custom sensitive information types in the Security & Compliance Center](#test-custom-sensitive-information-types-in-the-security--compliance-center).</span></span>

## <a name="remove-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="dc888-189">Entfernen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dc888-189">Remove custom sensitive information types in the Security & Compliance Center</span></span> 

<span data-ttu-id="dc888-190">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="dc888-190">**Notes**:</span></span>

- <span data-ttu-id="dc888-191">Sie können nur benutzerdefinierte Typen für vertrauliche Informationen entfernen; Sie können keine integrierten Typen vertraulicher Informationen entfernen.</span><span class="sxs-lookup"><span data-stu-id="dc888-191">You can only remove custom sensitive information types; you can't remove built-in sensitive information types.</span></span>

- <span data-ttu-id="dc888-192">Bevor Sie einen benutzerdefinierten Typ für vertrauliche Informationen entfernen, überprüfen Sie, dass keine DLP-Richtlinien oder Exchange-Nachrichtenflussregeln (auch bezeichnet als Transportregeln) mehr auf den Typ vertraulicher Informationen verweisen.</span><span class="sxs-lookup"><span data-stu-id="dc888-192">Before your remove a custom sensitive information type, verify that no DLP policies or Exchange mail flow rules (also known as transport rules) still reference the sensitive information type.</span></span>

1. <span data-ttu-id="dc888-193">Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und wählen Sie einen oder mehrere benutzerdefinierte Typen vertraulicher Informationen aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="dc888-193">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types** and select one or more custom sensitive information types that you want to remove.</span></span>

2. <span data-ttu-id="dc888-194">Klicken Sie in dem Fenster, das geöffnet wird, auf **Löschen** (oder auf **Typen vertraulicher Informationen löschen**, wenn Sie mehrere ausgewählt haben).</span><span class="sxs-lookup"><span data-stu-id="dc888-194">In the fly-out that opens, click **Delete** (or **Delete sensitive info types** if you selected more than one).</span></span>

    ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Löschen“](../media/scc-cust-sens-info-type-delete.png)

3. <span data-ttu-id="dc888-196">Klicken Sie in der angezeigten Warnmeldung auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="dc888-196">In the warning message that appears, click **Yes**.</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="dc888-197">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="dc888-197">How do you know this worked?</span></span>

<span data-ttu-id="dc888-198">Um sicherzustellen, dass Sie einen benutzerdefinierten Typ vertraulicher Informationen erfolgreich entfernt haben, wechseln Sie zu **Klassifizierungen** \> **Typen vertraulicher Informationen**, und bestätigen Sie, dass der benutzerdefinierte Typ vertraulicher Informationen nicht mehr aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="dc888-198">To verify that you've successfully removed a custom sensitive information type, go to **Classifications** \> **Sensitive info types** to verify the custom sensitive information type is no longer listed.</span></span>

## <a name="test-custom-sensitive-information-types-in-the-security--compliance-center"></a><span data-ttu-id="dc888-199">Testen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="dc888-199">Test custom sensitive information types in the Security & Compliance Center</span></span>

1. <span data-ttu-id="dc888-200">Wechseln Sie im Security & Compliance Center zu **Klassifizierungen** \> **Typen vertraulicher Informationen**.</span><span class="sxs-lookup"><span data-stu-id="dc888-200">In the Security & Compliance Center, go to **Classifications** \> **Sensitive info types**.</span></span>

2. <span data-ttu-id="dc888-p118">Wählen Sie einen oder mehrere benutzerdefinierte Typen vertraulicher Informationen aus, die Sie testen möchten. Klicken Sie in dem Fenster, das geöffnet wird, auf **Typ testen** (oder auf **Typen vertraulicher Informationen testen**, wenn Sie mehrere ausgewählt haben).</span><span class="sxs-lookup"><span data-stu-id="dc888-p118">Select one or more custom sensitive information types to test. In the fly-out that opens, click **Test type** (or **Test sensitive info types** if you selected more than one).</span></span>

    ![Speicherort der Typen für vertrauliche Informationen und Schaltfläche „Typ testen“](../media/scc-cust-sens-info-type-test.png)

3. <span data-ttu-id="dc888-204">Laden Sie auf der Seite **Zu testende Datei hochladen**, die geöffnet wird, per Drag & Drop ein zu testendes Dokument hoch, oder klicken Sie auf **Durchsuchen**, und wählen Sie eine Datei aus.</span><span class="sxs-lookup"><span data-stu-id="dc888-204">On the **Upload file to test** page that opens, upload a document to test by dragging and dropping a file or by clicking **Browse** and selecting a file.</span></span>

    ![Seite „Zu testende Datei hochladen“](../media/scc-cust-sens-info-type-test-upload.png)

4. <span data-ttu-id="dc888-206">Klicken Sie auf die Schaltfläche **Testen**, um das Dokument auf Musterübereinstimmungen in der Datei zu testen.</span><span class="sxs-lookup"><span data-stu-id="dc888-206">Click the **Test** button to test the document for pattern matches in the file.</span></span>

5. <span data-ttu-id="dc888-207">Klicken Sie auf der Seite **Übereinstimmungsergebnisse** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="dc888-207">On the **Match results** page, click **Finish**.</span></span>

    ![Übereinstimmungsergebnisse](../media/scc-cust-sens-info-type-test-results.png)
