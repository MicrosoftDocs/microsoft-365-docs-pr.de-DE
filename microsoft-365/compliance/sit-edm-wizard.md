---
title: Verwenden Sie den Assistenten für das Schema exakter Datenübereinstimmung und vertrauliche Informationstypen.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie den Assistenten für das Schema exakter Datenübereinstimmung und vertrauliche Informationstypen verwenden können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2081de887e09794350222dac3527bb3ff932837a
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49699147"
---
# <a name="use-the-exact-data-match-schema-and-sensitive-information-type-wizard"></a><span data-ttu-id="36553-103">Verwenden Sie den Assistenten für das Schema exakter Datenübereinstimmung und vertrauliche Informationstypen.</span><span class="sxs-lookup"><span data-stu-id="36553-103">Use the Exact Data Match Schema and Sensitive Information Type Wizard</span></span>

<span data-ttu-id="36553-104">[Das Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit auf genauer Datenübereinstimmung (Exact Data Match, EDM) basierender Klassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md) umfasst mehrere Schritte.</span><span class="sxs-lookup"><span data-stu-id="36553-104">[Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)  involves many steps.</span></span>  <span data-ttu-id="36553-105">Sie können diesen Assistenten verwenden, im Ihre Schema- und Musterdateien für vertrauliche Informationstypen (Regelpaket) zu erstellen, um den Prozess zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="36553-105">You can use this wizard to create your schema and sensitive information type pattern (rule package) files to help simplify the process.</span></span>

> [!NOTE]
> <span data-ttu-id="36553-106">Der Assistent für das Schema genauer Datenübereinstimmung und vertraulicher Informationstypen ist nur für die World Wide- und GCC-Cloud verfügbar.</span><span class="sxs-lookup"><span data-stu-id="36553-106">The Exact Data Match Schema and Sensitive Information Type Wizard is only available for the World Wide and GCC clouds only.</span></span>

<span data-ttu-id="36553-107">Der Assistent kann verwendet werden an Stelle von:</span><span class="sxs-lookup"><span data-stu-id="36553-107">This wizard can be used instead of the:</span></span>

- [<span data-ttu-id="36553-108">Definieren des Schemas für Ihre Datenbank mit vertraulichen Informationen</span><span class="sxs-lookup"><span data-stu-id="36553-108">Define the schema for your database of sensitive information</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#define-the-schema-for-your-database-of-sensitive-information)
- [<span data-ttu-id="36553-109">Richten Sie ein Muster (Regelpaket) ein</span><span class="sxs-lookup"><span data-stu-id="36553-109">Set up a pattern (rule package)</span></span>](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#set-up-a-rule-package)

<span data-ttu-id="36553-110">Schritte für [Teil 1: Einrichten der EDM-basierten Klassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span><span class="sxs-lookup"><span data-stu-id="36553-110">steps in [Part 1: Set up EDM-based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-1-set-up-edm-based-classification).</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="36553-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="36553-111">Pre-requisites</span></span>

1. <span data-ttu-id="36553-112">Machen Sie sich mit den Schritten vertraut, um einen benutzerdefinierten vertraulichen Informationstyp mit dem EDM-[Workflow auf einen Blick](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="36553-112">Familiarize yourself with the steps to create a custom sensitive information type with EDM [work flow at a glance](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#the-work-flow-at-a-glance).</span></span>

2. <span data-ttu-id="36553-113">Führen Sie die Schritte im Abschnitt [Vertrauliche Daten im .csv-Format speichern](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) durch.</span><span class="sxs-lookup"><span data-stu-id="36553-113">Perform the steps in the [Save sensitive data in .csv format](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#save-sensitive-data-in-csv-format) section.</span></span>

## <a name="use-the-exact-data-match-schema-and-sensitive-information-type-pattern-wizard"></a><span data-ttu-id="36553-114">Verwenden Sie den Assistenten für das Schema für exakte Datenübereinstimmung und Muster vertraulicher Informationstypen</span><span class="sxs-lookup"><span data-stu-id="36553-114">Use the exact data match schema and sensitive information type pattern wizard</span></span>

1. <span data-ttu-id="36553-115">Wechseln Sie im Microsoft 365 Compliance Center Ihres Mandaten zu **Datenklassifizierung** > **Genaue Datenübereinstimmung**.</span><span class="sxs-lookup"><span data-stu-id="36553-115">In the Microsoft 365 Compliance center for your tenant go to **Data classification** > **Exact data matches**.</span></span>

2. <span data-ttu-id="36553-116">Wählen Sie **EDM-Schema erstellen**, um das Flyout des Assistenten für die Schema-Konfiguration zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="36553-116">Choose **Create EDM schema** to open the schema wizard configuration flyout.</span></span>

![Flyout des Assistenten für die Erstellung der EDM-Schema-Konfiguration](../media/edm-schema-wizard-1.png)

3. <span data-ttu-id="36553-118">Geben Sie einen geeigneten **Namen** und eine **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="36553-118">Fill in an appropriate **Name** and **Description**.</span></span>

4. <span data-ttu-id="36553-119">Wählen Sie **Trennzeichen und Satzzeichen für alle Schemafelder ignorieren**, wenn Sie dieses Verhalten wünschen.</span><span class="sxs-lookup"><span data-stu-id="36553-119">Choose **Ignore delimiters and punctuations for all schema fields** if you want that behavior.</span></span> <span data-ttu-id="36553-120">Weitere Informationen zum Konfigurieren von EDM zum Ignorieren von Groß- und Kleinschreibung oder Trennzeichen finden Sie unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps mit auf EDM (genaue Datenübereinstimmung) basierender Klassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="36553-120">To learn more about configuring EDM to ignore case or delimitere, see [Creating a custom sensitive information type with Exact Data Match (EDM) based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

5. <span data-ttu-id="36553-121">Geben Sie die gewünschten Werte ein für Ihr **Schemafeld #1** und fügen Sie wenn notwendig weitere Felder ein.</span><span class="sxs-lookup"><span data-stu-id="36553-121">Fill in your desired values for your **Schema field #1** and add more fields as needed.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="36553-122">Mindestens eines, aber nicht mehr als fünf Ihrer Schemafelder müssen als durchsuchbar gekennzeichnet sein.</span><span class="sxs-lookup"><span data-stu-id="36553-122">At least one, but no more than five of your schema fields must be designated as searchable.</span></span>

6. <span data-ttu-id="36553-123">Wählen Sie Speichern aus.</span><span class="sxs-lookup"><span data-stu-id="36553-123">Choose save.</span></span> <span data-ttu-id="36553-124">Ihr Schema wird jetzt aufgeführt sein.</span><span class="sxs-lookup"><span data-stu-id="36553-124">Your schema will now be listed.</span></span>

7. <span data-ttu-id="36553-125">Wählen Sie **Vertrauliche EDM-Informationstypen** und **Erstellen von vertraulichen EDM-Informationstypen**, um den Assistenten für die Konfigurations von vertraulichen Informationstypen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="36553-125">Choose **EDM sensitive info types** and **Create EDM sensitive info type** to open the sensitive info type configuration wizard.</span></span>

8. <span data-ttu-id="36553-126">Wählen Sie **Auswahl eines bestehenden EDM-Schemas** und wählen Sie dann das Schema aus, das Sie in den Schritten 2–6 der Liste erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="36553-126">Choose **Choose an existing EDM schema** and choose the schema you created in steps 2-6 from the list.</span></span>

9. <span data-ttu-id="36553-127">Wählen Sie **Weiter** und dann **Muster erstellen**.</span><span class="sxs-lookup"><span data-stu-id="36553-127">Choose **Next** and choose **Create pattern**.</span></span>

10. <span data-ttu-id="36553-128">Wählen Sie das **Konfidenzniveau** und das **Primäre Element** aus.</span><span class="sxs-lookup"><span data-stu-id="36553-128">Choose the **Confidence level** and **Primary element**.</span></span>  <span data-ttu-id="36553-129">Weitere Informationen zum Konfigurieren eines Musters finden Sie unter [Erstellen eines vertraulichen Informationstyps im Compliance-Center](create-a-custom-sensitive-information-type.md)</span><span class="sxs-lookup"><span data-stu-id="36553-129">To learn more about configuring a pattern, see [Create a custom sensitive information type in the Compliance Center](create-a-custom-sensitive-information-type.md)</span></span>

11.  <span data-ttu-id="36553-130">Wählen Sie den **Vertraulicher Informationstyp des primären Elementes**, um ihn zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="36553-130">Choose the **Primary element's sensitive info type** to associate it with.</span></span> <span data-ttu-id="36553-131">Weitere Informationen über die verfügbaren vertraulichen Informationstypen finden Sie unter [Entitätsdefinitionen für vertrauliche Informationstypen](sensitive-information-type-entity-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="36553-131">See [Sensitive Information Type Entity Definitions](sensitive-information-type-entity-definitions.md) to learn more about the available sensitive information types.</span></span>

12. <span data-ttu-id="36553-132">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="36553-132">Choose **Done**.</span></span>

13. <span data-ttu-id="36553-133">Wählen Sie ihre gewünschten **Konfidenzniveau und Zeichennähe**.</span><span class="sxs-lookup"><span data-stu-id="36553-133">Choose your desired **Confidence level and character proximity**.</span></span>  <span data-ttu-id="36553-134">Dies wird der Standardwert sein für sämtliche vertraulichen EDM-Informationstypen</span><span class="sxs-lookup"><span data-stu-id="36553-134">This will be the default value for the whole EDM sensitive info type</span></span>

13. <span data-ttu-id="36553-135">Wählen Sie **Muster erstellen** aus, wenn Sie zusätzliche Muster für Ihre vertraulichen EDM-Informationstypen erstellen wollen.</span><span class="sxs-lookup"><span data-stu-id="36553-135">Choose **Create pattern** if you want to creaet additional patterns for your EDM sensitive info type.</span></span>

14. <span data-ttu-id="36553-136">Wählen Sie **Weiter** und geben Sie einen **Namen** und eine **Beschreibung für Administratoren** ein.</span><span class="sxs-lookup"><span data-stu-id="36553-136">Choose **Next** and fill in a **Name** and **Description for admins**.</span></span>

15. <span data-ttu-id="36553-137">Überprüfen Sie und wählen Sie dann **Übermitteln** aus.</span><span class="sxs-lookup"><span data-stu-id="36553-137">Review and choose **Submit**.</span></span>

<span data-ttu-id="36553-138">Sie können ein Muster für vertrauliche Informationstypen löschen oder bearbeiten, indem Sie es auswählen, wodurch die Steuerelemente für das Löschen und Bearbeiten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="36553-138">You can delete or edit the sensitive information type pattern by selecting it which surfaces the edit and delete controls.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36553-139">Wenn Sie ein Schema entfernen möchten, dieses aber bereits mit einem vertraulichen EDM-Informationstyp verbunden ist, dann müssen Sie zuerst den vertraulichen EDM-Informationstyp löschen, um das Schema löschen zu können.</span><span class="sxs-lookup"><span data-stu-id="36553-139">If you want to remove a schema, and it is already associated with an EDM sensitive info type, you must first delete the EDM sensitive info type, then you can delete the schema.</span></span>

## <a name="post-steps"></a><span data-ttu-id="36553-140">Nachbearbeitungsschritte</span><span class="sxs-lookup"><span data-stu-id="36553-140">Post steps</span></span>

<span data-ttu-id="36553-141">Nachdem Sie diesen Assistenten für die Erstellung der EDM-Schema- und -Musterdateien (Regelpaket) verwendet haben, müssen Sie trotzdem noch die Schritte in [Teil 2: Hashing und Hochladen der vertraulichen Daten](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) durchführen, bevor Sie den benutzerdefinierten vertraulichen EDM-Informationstyp verwenden können.</span><span class="sxs-lookup"><span data-stu-id="36553-141">After you have used this wizard to create your EDM schema and pattern (rule package) files, you still have to perform the steps in [Part 2: Hash and upload the sensitive data](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md#part-2-hash-and-upload-the-sensitive-data) before you can use the EDM custom sensitive information type.</span></span>