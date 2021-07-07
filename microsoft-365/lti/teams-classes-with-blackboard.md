---
title: Integrieren Microsoft Teams Klassen in Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrieren Microsoft Teams Klassen in Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314491"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="a5a0e-103">Verwenden Microsoft Teams Klassen mit Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="a5a0e-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="a5a0e-104">Teamwork ist der Kern jeder modernen Organisation.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="a5a0e-105">Durch die Förderung der Zusammenarbeit ist dies ein definierendes Merkmal jeder erfolgreichen Institution.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="a5a0e-106">Sie können alle Funktionen und Features von Blackboard Learn Ultra verbessern, indem Sie sie mit Microsoft Teams Klassen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="a5a0e-107">Ihre Klassen können Echtzeitunterhaltungen, Videobesprechungen oder asynchrone Interaktionen umfassen.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="a5a0e-108">Sie können Dateifreigabe- und -erstellungserfahrungen für Ihre Schüler und Studenten an einem zentralen Ort hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="a5a0e-109">Microsoft Teams Klassen mit Learn Ultra definieren die Dynamik des Lehrens neu und definieren, was effektives Lernen bedeutet.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5a0e-110">Stellen Sie sicher, dass Sie das Feld "Bildungs-E-Mail" in Ihrem Schülerinformationssystem (SIS) erfolgreich eingerichtet haben. `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="a5a0e-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="a5a0e-111">Die Integration der Microsoft Teams Klassen basiert auf dem E-Mail-Feld der Bildungseinrichtung in Ihrem SIS, um den Benutzerprinzipalnamen (User Principal Name, UPN) des richtigen Microsoft Azure Active Directory (AAD) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="a5a0e-112">Wenn keine Institutions-E-Mail bereitgestellt wurde, wird standardmäßig die vorhandene E-Mail verwendet.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="a5a0e-113">Es wird empfohlen, dieses Feld für jeden Benutzer festzulegen, um sicherzustellen, dass seine Daten korrekt synchronisiert werden und dass zwischen Microsoft AAD und Blackboard Learn Ultra kein Konflikt mit E-Mail-Daten besteht.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="a5a0e-114">Wenn Sie dieses Feld in Ihrer SIS-Zuordnung nicht entsprechend festgelegt haben, funktioniert die Integration weiterhin, aber benutzer werden möglicherweise nicht in den erstellten Teams Klassen angezeigt, und es können Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="a5a0e-115">Unterstützung der zuordnung von institutionsbasierten Daten – Sis-Feld für Institution-E-Mail</span><span class="sxs-lookup"><span data-stu-id="a5a0e-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="a5a0e-116">Im Rahmen der Weiterentwicklung der Cloudanbieterintegration hat Blackboard Learn Ultra sowohl in der Integration des Student Information System Framework als auch in den öffentlichen REST-APIs ein neues **E-Mail-Feld** für Die Bildungseinrichtung erstellt, das es Einrichtungen ermöglicht, den Datensynchronisierungsprozess zwischen Blackboard Learn Ultra und Microsoft AAD effektiv zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="a5a0e-117">Was bedeutet die E-Mail-Adresse der Bildungseinrichtung und was unterstützt sie?</span><span class="sxs-lookup"><span data-stu-id="a5a0e-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="a5a0e-118">Das **E-Mail-Feld "Institution"** ermöglicht angepasste Feldzuordnungen zwischen den extern unterstützten Datenquellen eines Clients und Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="a5a0e-119">Wenn Datenquellen Cloudanbieter sind, z. B. Microsoft, ist der Benutzerprinzipalname (User Principle Name, UPN) ein primärer eindeutiger Bezeichner für jeden Benutzer, der aus einem UPN-Präfix (kontoname des Benutzers) und einem UPN-Suffix (einem DNS-Domänennamen) besteht, die mit einem @-Symbol verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="a5a0e-120">Dadurch wird eine eindeutige E-Mail-Adresse für jeden bestimmten Benutzer innerhalb des Microsoft Azure Active Directory erstellt.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="a5a0e-121">Um sicherzustellen, dass die Daten korrekt sind und Registrierungen oder Mitgliedschaften zwischen Blackboard Learn Ultra und Microsoft Teams Klassen korrekt erreicht werden, muss die E-Mail-Adresse eines Benutzers zwischen beiden Systemen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="a5a0e-122">In Blackboard Learn Ultra können Benutzer ihre vorhandene E-Mail-Adresse auf der Benutzeroberfläche ändern oder überschreiben, was zu Synchronisierungsfehlern führen kann und der Benutzer einem Kursteam nicht ordnungsgemäß hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="a5a0e-123">Die **E-Mail-Feldzuordnung** der Institution stellt sicher, dass diese Sicherheits- und Überprüfungsstufe ordnungsgemäß verwaltet werden kann, unabhängig davon, ob Benutzer ihre E-Mails innerhalb von Blackboard Learn Ultra geändert haben oder nicht.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="a5a0e-124">Wenn zwei E-Mail-Adressen unterschiedlich sind:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="a5a0e-125">Es muss eine Entscheidung darüber getroffen werden, welche Quelle Vorrang hat und sowohl als E-Mail-Person als auch als E-Mail-Institution getroffen wird.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="a5a0e-126">Oder:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-126">Or</span></span>
- <span data-ttu-id="a5a0e-127">Eine Institution kann eine benutzerdefinierte Feldzuordnung in ihrer Institution-E-Mail festlegen, die einen potenziellen Konflikt lösen kann.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="a5a0e-128">Die **Institution Email field** mapping is now available for all existing SIS integration types at Advanced Configuration **Einstellungen** Users Learn  >  **Object Type** Field  >  **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="a5a0e-129">Es ist wichtig zu beachten, dass die **Institutions-E-Mail** standardmäßig für alle **SIS-Formate auf "Personen-E-Mail"** festgelegt ist und für jede Person eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="a5a0e-130">Alle vorhandenen Integrationen, die eingerichtet und ausgeführt werden, verfügen über diese Datenzuordnung, da SIS benutzer nicht importieren kann, wenn ihre E-Mails dupliziert sind.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="a5a0e-131">Wenn eine Bildungseinrichtung die Möglichkeit benötigt, die E-Mail-Adresse der Bildungseinrichtung in **"Benutzerdefiniert"** zu ändern, muss sie dies über die **erweiterte Konfiguration Einstellungen** im SIS verwalten.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="a5a0e-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5a0e-132">Requirements</span></span>

<span data-ttu-id="a5a0e-133">Die integration von Microsoft Teams Klassen ist nur für **Kurse in der Extremkursansicht** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="a5a0e-134">Ihre Bildungseinrichtung muss diese Anforderungen erfüllen, um sie zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="a5a0e-135">Blackboard Learn Ultra Learn SaaS mit aktivierter Ultra-Basisnavigation</span><span class="sxs-lookup"><span data-stu-id="a5a0e-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="a5a0e-136">Aktivieren Sie LTI für die Verwendung in Kursen.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="a5a0e-137">a.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-137">a.</span></span> <span data-ttu-id="a5a0e-138">Wechseln Sie zum **Administratorbereich**  >  **LTI-Toolanbieter**  >  **verwalten globale Eigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="a5a0e-139">b.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-139">b.</span></span> <span data-ttu-id="a5a0e-140">Wählen Sie **"LTI Aktiviert" in "Kurse"** und optional **"Aktiviert in Organisationen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="a5a0e-141">c.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-141">c.</span></span> <span data-ttu-id="a5a0e-142">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-142">Select **Submit**.</span></span>

- <span data-ttu-id="a5a0e-143">LTI muss konfiguriert sein</span><span class="sxs-lookup"><span data-stu-id="a5a0e-143">Must have LTI configured</span></span>

- <span data-ttu-id="a5a0e-144">Hinzufügen von Blackboard Learn Super Teams Klassen LTI-Integration</span><span class="sxs-lookup"><span data-stu-id="a5a0e-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="a5a0e-145">Add Microsoft Teams Classes LTI 1.3 Tool</span><span class="sxs-lookup"><span data-stu-id="a5a0e-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="a5a0e-146">Hinzufügen des REST-API-Tools und der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="a5a0e-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="a5a0e-147">Konfigurieren und Genehmigen Microsoft Teams Klassenintegration</span><span class="sxs-lookup"><span data-stu-id="a5a0e-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="a5a0e-148">Hinzufügen des Tools "Blackboard Learn Ultra Teams Classes LTI 1.3"</span><span class="sxs-lookup"><span data-stu-id="a5a0e-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="a5a0e-149">Wählen Sie im **Administratorbereich** **LTI-Toolanbieter aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="a5a0e-150">Wählen Sie **"LTI 1.3-Tool registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="a5a0e-151">Geben Sie im **Feld "Client-ID"** diese ID ein, oder kopieren Sie sie, und fügen Sie sie ein:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="a5a0e-152">Überprüfen Sie alle Einstellungen, die bereits ausgefüllt wurden, und wählen **Sie "Toolstatus"** aus, und wählen Sie dann **"Aktiviert"** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="a5a0e-153">Wählen Sie in **"Institution Policies"** **die Option "Rolle im Kurs", "Name"** und **"E-Mail-Adresse"** aus, und wählen Sie dann für beide die Option **"Ja"** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="a5a0e-154">Wählen Sie **"Dienstzugriff zulassen"** und **"Mitgliedschaftsdienstzugriff zulassen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="a5a0e-155">Hinzufügen des Tools Microsoft Teams Klassen LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="a5a0e-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="a5a0e-156">Wählen Sie im **Administratorbereich** **LTI-Toolanbieter aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="a5a0e-157">Wählen Sie **"LTI 1.3-Tool registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="a5a0e-158">Geben Sie im **Feld "Client-ID"** diese ID ein, oder kopieren Sie sie, und fügen Sie sie ein:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="a5a0e-159">Überprüfen Sie alle Einstellungen, die bereits ausgefüllt wurden, und wählen *Sie "Toolstatus"* aus, und wählen Sie *"Aktiviert" aus.*</span><span class="sxs-lookup"><span data-stu-id="a5a0e-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="a5a0e-160">Wählen Sie in **"Institution Policies"** **die Rolle in "Kurs", "Name"** und **"E-Mail-Adresse"** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="a5a0e-161">Wählen Sie für beides **"Ja"** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="a5a0e-162">Wählen Sie **"Dienstzugriff zulassen"** und **"Mitgliedschaftsdienstzugriff zulassen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="a5a0e-163">Hinzufügen des REST-API-Tools</span><span class="sxs-lookup"><span data-stu-id="a5a0e-163">Add the REST API tool</span></span>

1. <span data-ttu-id="a5a0e-164">Navigieren Sie im **Administratorbereich** zu **"Integrationen",** und wählen Sie **"Rest-API-Integrationen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="a5a0e-165">Wählen Sie **Integration erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="a5a0e-166">Geben Sie im **Feld "Anwendungs-ID"** diese ID ein, oder kopieren Sie sie, und fügen Sie sie ein:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="a5a0e-167">Geben Sie einen Benutzer für diese Integration ein.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-167">Type a user for this integration.</span></span>

   <span data-ttu-id="a5a0e-168">Dieser Benutzer ist der Benutzer mit dem Zugriff auf die Home-API, dem die Anwendung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="a5a0e-169">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="a5a0e-170">Hinzufügen der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="a5a0e-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="a5a0e-171">Navigieren Sie im **Administratorbereich** zu **"Integrationen",** und wählen Sie \**Ursprungsübergreifende Ressourcenfreigabe aus.*</span><span class="sxs-lookup"><span data-stu-id="a5a0e-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="a5a0e-172">Wählen Sie **"Konfiguration erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="a5a0e-173">In the **Origin** field, type of copy and paste this URL:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="a5a0e-174">Geben Sie im Feld **"Zulässige Kopfzeilen"** die Berechtigung **ein.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="a5a0e-175">**Auf "Verfügbar"** auf **"Ja"** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="a5a0e-176">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="a5a0e-177">Konfigurieren und Genehmigen Microsoft Teams Klassenintegration</span><span class="sxs-lookup"><span data-stu-id="a5a0e-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="a5a0e-178">Um Ihre Blackboard Learn Ultra-Instanz erfolgreich in Microsoft Teams Klassen zu integrieren, müssen Sie sicherstellen, dass die Blackboard Learn Ultra-Anwendung für den Zugriff innerhalb Ihres Microsoft Azure Mandanten genehmigt wurde.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="a5a0e-179">Dies ist ein Prozess, der vom Microsoft 365 globalen Administrator Ihrer Bildungseinrichtung abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="a5a0e-180">Dieser Vorgang kann entweder vor oder nach der Konfiguration der LTI-Anwendungen in Ihrer Blackboard Learn Ultra-Instanz durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="a5a0e-181">Vor dem Konfigurieren der LTI-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a5a0e-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="a5a0e-182">Wenn Sie die Blackboard Learn Ultra Teams Classes Azure-App vor dem Konfigurieren der LTI-Integrationen genehmigen möchten, müssen Sie zum **Microsoft Identity Platform Admin Consent Endpoint umleiten.**</span><span class="sxs-lookup"><span data-stu-id="a5a0e-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="a5a0e-183">Die URL wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="a5a0e-184">Sie ersetzen **{Tenant}** durch Ihre spezifische institutionsspezifische Microsoft Azure Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="a5a0e-185">Nach dem Konfigurieren der LTI-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a5a0e-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="a5a0e-186">Navigieren Sie im **Administratorbereich** zu **Tools und Hilfsprogrammen,** und wählen Sie **Microsoft Teams Integrationsadministrator** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="a5a0e-187">Wählen Sie **"Microsoft Teams aktivieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="a5a0e-188">Fügen Sie Ihre **Microsoft-Mandanten-ID** in das verfügbare Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="a5a0e-189">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a5a0e-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="a5a0e-190">Wenn die App vorab zugestimmt hat, wird ein kleines Häkchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="a5a0e-191">Wenn das Häkchen angezeigt wird, wählen Sie **Absenden** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="a5a0e-192">Wenn die Zustimmung nicht genehmigt wurde, führen Sie die beschriebenen Schritte aus, um die URL für die Zustimmung zu generieren und sie zur Genehmigung an den Microsoft 365 globalen Administrator zu senden.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="a5a0e-193">Nachdem Sie die Genehmigungsbestätigung erhalten haben, wählen Sie **"Erneut versuchen"** aus, um dies zu bestätigen, und wählen Sie dann **"Absenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="a5a0e-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>
