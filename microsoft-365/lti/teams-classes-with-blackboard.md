---
title: Verwenden Microsoft Teams Klassen mit Blackboard Learn Ultra
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
description: Verwenden Microsoft Teams Klassen mit Blackboard Learn Ultra
ms.openlocfilehash: a97d5bf56e1e045ccb0ef7cc66ecef7dfba4041a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454638"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="478b2-103">Verwenden Microsoft Teams Klassen mit Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="478b2-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="478b2-104">Teamwork ist der Kern jeder modernen Organisation.</span><span class="sxs-lookup"><span data-stu-id="478b2-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="478b2-105">Durch die Förderung der Zusammenarbeit ist dies ein definierendes Merkmal jeder erfolgreichen Institution.</span><span class="sxs-lookup"><span data-stu-id="478b2-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="478b2-106">Sie können alle Funktionen und Features von Blackboard Learn Ultra verbessern, indem Sie sie mit Microsoft Teams Klassen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="478b2-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="478b2-107">Ihre Klassen können Echtzeitunterhaltungen, Videobesprechungen oder asynchrone Interaktionen umfassen.</span><span class="sxs-lookup"><span data-stu-id="478b2-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="478b2-108">Sie können Dateifreigabe- und -erstellungsfunktionen für Ihre Schüler/Studenten an einem zentralen Ort hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="478b2-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="478b2-109">Microsoft Teams Klassen mit Learn Ultra definieren die Dynamik des Lehrens neu und was effektives Lernen bedeutet.</span><span class="sxs-lookup"><span data-stu-id="478b2-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="478b2-110">Stellen Sie sicher, dass Sie das Feld "Bildungs-E-Mail" in Ihrem [Schülerinformationssystem (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning) erfolgreich eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="478b2-110">Ensure that you have successfully set up the Institution Email field in your [Student Information System (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span></span>
>
><span data-ttu-id="478b2-111">Die Integration der Microsoft Teams Klassen basiert auf dem E-Mail-Feld der Bildungseinrichtung in Ihrem SIS, um dem [Benutzerprinzipalnamen (User Principle Name, UPN)](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes)des richtigen Microsoft Azure Active Directory (AAD) zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="478b2-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) [User Principle Name (UPN)](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes).</span></span> <span data-ttu-id="478b2-112">Wenn keine Institutions-E-Mail bereitgestellt wurde, wird standardmäßig die vorhandene E-Mail verwendet.</span><span class="sxs-lookup"><span data-stu-id="478b2-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="478b2-113">Es wird empfohlen, dieses Feld für jeden Benutzer festzulegen, um sicherzustellen, dass seine Daten korrekt synchronisiert werden und dass es keinen Konflikt zwischen AAD und Blackboard Learn Ultra gibt.</span><span class="sxs-lookup"><span data-stu-id="478b2-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="478b2-114">Wenn Sie dieses Feld in Ihrer SIS-Zuordnung nicht entsprechend festgelegt haben, funktioniert die Integration weiterhin, benutzer werden jedoch möglicherweise nicht in den Teams erstellten Klassen angezeigt, und es können Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="478b2-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="478b2-115">Unterstützung der zuordnung von institutionsbasierten Daten – Sis-Feld für Institution-E-Mail</span><span class="sxs-lookup"><span data-stu-id="478b2-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="478b2-116">Im Rahmen der Weiterentwicklung der Cloudanbieterintegration hat Blackboard Learn Ultra sowohl in der Integration des Student Information System Framework als auch in öffentlichen REST-APIs ein neues **E-Mail-Feld** für Die Bildungseinrichtung erstellt, mit dem Einrichtungen den Datensynchronisierungsprozess zwischen Blackboard Learn Ultra und AAD effektiv verwalten können.</span><span class="sxs-lookup"><span data-stu-id="478b2-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="478b2-117">Was bedeutet die E-Mail-Adresse der Bildungseinrichtung und was unterstützt sie?</span><span class="sxs-lookup"><span data-stu-id="478b2-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="478b2-118">Das **E-Mail-Feld "Institution"** ermöglicht angepasste Feldzuordnungen zwischen den extern unterstützten Datenquellen eines Clients und Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="478b2-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="478b2-119">Wenn Datenquellen Cloudanbieter sind, z. B. Microsoft, ist der Benutzerprinzipalname (User Principle Name, UPN) ein primärer eindeutiger Bezeichner für jeden Benutzer, der aus einem UPN-Präfix (kontoname des Benutzers) und einem UPN-Suffix (einem DNS-Domänennamen) besteht, die mit einem @-Symbol verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="478b2-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="478b2-120">Dadurch wird eine eindeutige E-Mail-Adresse für jeden bestimmten Benutzer innerhalb des Microsoft Azure Active Directory erstellt.</span><span class="sxs-lookup"><span data-stu-id="478b2-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="478b2-121">Um sicherzustellen, dass die Daten korrekt sind und Registrierungen oder Mitgliedschaften zwischen Blackboard Learn Ultra und Microsoft Teams Klassen ordnungsgemäß erreicht werden, muss die E-Mail-Adresse eines Benutzers zwischen beiden Systemen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="478b2-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="478b2-122">In Blackboard Learn Ultra können Benutzer ihre vorhandene E-Mail-Adresse auf der Benutzeroberfläche ändern oder überschreiben, was zu Synchronisierungsfehlern führen kann und der Benutzer einem Kursteam nicht ordnungsgemäß hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="478b2-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="478b2-123">Die **E-Mail-Feldzuordnung** der Institution stellt sicher, dass diese Sicherheits- und Überprüfungsstufe ordnungsgemäß verwaltet werden kann, unabhängig davon, ob Benutzer ihre E-Mails innerhalb von Blackboard Learn Ultra geändert haben oder nicht.</span><span class="sxs-lookup"><span data-stu-id="478b2-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="478b2-124">Wenn zwei E-Mail-Adressen unterschiedlich sind:</span><span class="sxs-lookup"><span data-stu-id="478b2-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="478b2-125">Es muss eine Entscheidung darüber getroffen werden, welche Quelle Vorrang hat und sowohl als E-Mail-Person als auch als E-Mail-Institution getroffen wird.</span><span class="sxs-lookup"><span data-stu-id="478b2-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="478b2-126">Oder</span><span class="sxs-lookup"><span data-stu-id="478b2-126">Or</span></span>
- <span data-ttu-id="478b2-127">Eine Institution kann eine benutzerdefinierte Feldzuordnung in ihrer Institution-E-Mail festlegen, die einen potenziellen Konflikt lösen kann.</span><span class="sxs-lookup"><span data-stu-id="478b2-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="478b2-128">Die **Institution Email field** mapping is now available for all existing SIS integration types at Advanced Configuration **Einstellungen** Users Learn  >  **Object Type** Field  >  **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="478b2-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="478b2-129">Es ist wichtig zu beachten, dass die **Institutions-E-Mail** standardmäßig für alle **SIS-Formate auf "Personen-E-Mail"** festgelegt ist und für jede Person eindeutig sein muss.</span><span class="sxs-lookup"><span data-stu-id="478b2-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="478b2-130">Alle vorhandenen Integrationen, die eingerichtet und ausgeführt werden, verfügen über diese Datenzuordnung, da SIS benutzer nicht importieren kann, wenn ihre E-Mails dupliziert sind.</span><span class="sxs-lookup"><span data-stu-id="478b2-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="478b2-131">Wenn eine Bildungseinrichtung die Möglichkeit benötigt, die E-Mail-Adresse der Bildungseinrichtung in **"Benutzerdefiniert"** zu ändern, muss sie dies über die **erweiterte Konfiguration Einstellungen** im SIS verwalten.</span><span class="sxs-lookup"><span data-stu-id="478b2-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="478b2-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="478b2-132">Requirements</span></span>

<span data-ttu-id="478b2-133">Die Integration der Microsoft Teams Klassen ist nur für Kurse in **der Extremkursansicht** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="478b2-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="478b2-134">Ihre Bildungseinrichtung muss diese Anforderungen erfüllen, um sie zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="478b2-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="478b2-135">Blackboard Learn Ultra Learn SaaS mit aktivierter Ultra-Basisnavigation</span><span class="sxs-lookup"><span data-stu-id="478b2-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

  ![Ein Beispiel für das Feature ist in Kursen aktiviert](media/feature-availability.png)

- <span data-ttu-id="478b2-137">Aktivieren Sie LTI für die Verwendung in Kursen.</span><span class="sxs-lookup"><span data-stu-id="478b2-137">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="478b2-138">a.</span><span class="sxs-lookup"><span data-stu-id="478b2-138">a.</span></span> <span data-ttu-id="478b2-139">Wechseln Sie zum **Administratorbereich**  >  **LTI-Toolanbieter**  >  **verwalten globale Eigenschaften.**</span><span class="sxs-lookup"><span data-stu-id="478b2-139">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="478b2-140">b.</span><span class="sxs-lookup"><span data-stu-id="478b2-140">b.</span></span> <span data-ttu-id="478b2-141">Wählen Sie **"LTI Aktiviert" in "Kurse"** und optional **"In Organisationen aktiviert" aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-141">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="478b2-142">c.</span><span class="sxs-lookup"><span data-stu-id="478b2-142">c.</span></span> <span data-ttu-id="478b2-143">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-143">Select **Submit**.</span></span>

- <span data-ttu-id="478b2-144">LTI muss konfiguriert sein</span><span class="sxs-lookup"><span data-stu-id="478b2-144">Must have LTI configured</span></span>

- <span data-ttu-id="478b2-145">Hinzufügen von Blackboard Learn Super Teams Klassen LTI-Integration</span><span class="sxs-lookup"><span data-stu-id="478b2-145">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="478b2-146">Add Microsoft Teams Classes LTI 1.3 Tool</span><span class="sxs-lookup"><span data-stu-id="478b2-146">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="478b2-147">Hinzufügen des REST-API-Tools und der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="478b2-147">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="478b2-148">Konfigurieren und Genehmigen Microsoft Teams Klassenintegration</span><span class="sxs-lookup"><span data-stu-id="478b2-148">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="478b2-149">Hinzufügen des Tools "Blackboard Learn Super Teams Classes LTI 1.3"</span><span class="sxs-lookup"><span data-stu-id="478b2-149">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="478b2-150">Wählen Sie im **Administratorbereich** **LTI-Toolanbieter aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-150">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="478b2-151">Wählen Sie **"LTI 1.3-Tool registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-151">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="478b2-152">Geben Sie im **Feld "Client-ID"** diese ID ein, oder kopieren Sie sie, und fügen Sie sie ein:</span><span class="sxs-lookup"><span data-stu-id="478b2-152">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="478b2-153">Überprüfen Sie alle Einstellungen, die vorab ausgefüllt wurden, und wählen **Sie "Toolstatus"** aus, und wählen Sie dann **"Aktiviert"** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-153">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="478b2-154">Wählen Sie in **"Institution Policies"** **die Option "Rolle im Kurs", "Name"** und **"E-Mail-Adresse"** aus, und wählen Sie dann für beide die Option **"Ja"** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-154">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="478b2-155">Wählen Sie **"Dienstzugriff zulassen"** und **"Mitgliedschaftsdienstzugriff zulassen" aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-155">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="478b2-156">Hinzufügen des Tools Microsoft Teams Klassen LTI 1.3</span><span class="sxs-lookup"><span data-stu-id="478b2-156">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="478b2-157">Wählen Sie im **Administratorbereich** **LTI-Toolanbieter aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-157">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="478b2-158">Wählen Sie **"LTI 1.3-Tool registrieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-158">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="478b2-159">Geben Sie im **Feld "Client-ID"** diese ID ein, oder kopieren Sie sie, und fügen Sie sie ein:</span><span class="sxs-lookup"><span data-stu-id="478b2-159">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="478b2-160">Überprüfen Sie alle Einstellungen, die bereits ausgefüllt wurden, und wählen *Sie "Toolstatus"* aus, und wählen Sie *"Aktiviert" aus.*</span><span class="sxs-lookup"><span data-stu-id="478b2-160">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="478b2-161">Wählen Sie in **"Institution Policies"** **die Rolle in "Kurs", "Name"** und **"E-Mail-Adresse"** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-161">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="478b2-162">Wählen Sie für beides **"Ja"** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-162">Select **Yes** for both.</span></span>

6. <span data-ttu-id="478b2-163">Wählen Sie **"Dienstzugriff zulassen"** und **"Mitgliedschaftsdienstzugriff zulassen" aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-163">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="478b2-164">Hinzufügen des REST-API-Tools</span><span class="sxs-lookup"><span data-stu-id="478b2-164">Add the REST API tool</span></span>

1. <span data-ttu-id="478b2-165">Navigieren Sie im **Administratorbereich** zu **"Integrationen",** und wählen Sie **"Rest-API-Integrationen" aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-165">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="478b2-166">Wählen Sie **Integration erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-166">Select **Create Integration**.</span></span>

3. <span data-ttu-id="478b2-167">Geben Sie im **Feld "Anwendungs-ID"** diese ID ein, oder kopieren Sie sie, und fügen Sie sie ein:</span><span class="sxs-lookup"><span data-stu-id="478b2-167">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="478b2-168">Geben Sie einen Benutzer für diese Integration ein.</span><span class="sxs-lookup"><span data-stu-id="478b2-168">Type a user for this integration.</span></span>

   <span data-ttu-id="478b2-169">Dieser Benutzer ist der Benutzer mit dem Zugriff auf die Home-API, dem die Anwendung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="478b2-169">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="478b2-170">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-170">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="478b2-171">Hinzufügen der ursprungsübergreifenden Ressourcenfreigabe</span><span class="sxs-lookup"><span data-stu-id="478b2-171">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="478b2-172">Navigieren Sie im **Administratorbereich** zu **"Integrationen",** und wählen Sie \**Ursprungsübergreifende Ressourcenfreigabe aus.*</span><span class="sxs-lookup"><span data-stu-id="478b2-172">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="478b2-173">Wählen Sie **"Konfiguration erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="478b2-173">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="478b2-174">In the **Origin** field, type of copy and paste this URL:</span><span class="sxs-lookup"><span data-stu-id="478b2-174">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="478b2-175">Geben Sie im Feld **"Zulässige Kopfzeilen"** die Berechtigung **ein.**</span><span class="sxs-lookup"><span data-stu-id="478b2-175">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="478b2-176">**Auf "Verfügbar"** auf **"Ja"** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="478b2-176">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="478b2-177">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-177">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="478b2-178">Konfigurieren und Genehmigen Microsoft Teams Klassenintegration</span><span class="sxs-lookup"><span data-stu-id="478b2-178">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="478b2-179">Um Ihre Blackboard Learn Ultra-Instanz erfolgreich in Microsoft Teams Klassen zu integrieren, müssen Sie sicherstellen, dass die Blackboard Learn Ultra-Anwendung für den Zugriff innerhalb Ihres Microsoft Azure Mandanten genehmigt wurde.</span><span class="sxs-lookup"><span data-stu-id="478b2-179">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="478b2-180">Dies ist ein Prozess, der vom Microsoft 365 globalen Administrator Ihrer Bildungseinrichtung abgeschlossen werden muss.</span><span class="sxs-lookup"><span data-stu-id="478b2-180">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="478b2-181">Dieser Vorgang kann entweder vor oder nach der Konfiguration der LTI-Anwendungen in Ihrer Blackboard Learn Ultra-Instanz erfolgen.</span><span class="sxs-lookup"><span data-stu-id="478b2-181">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="478b2-182">Vor dem Konfigurieren der LTI-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="478b2-182">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="478b2-183">Wenn Sie die Blackboard Learn Ultra Teams Classes Azure-App vor dem Konfigurieren der LTI-Integrationen genehmigen möchten, müssen Sie zum **Microsoft Identity Platform Admin Consent Endpoint umleiten.**</span><span class="sxs-lookup"><span data-stu-id="478b2-183">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="478b2-184">Die URL wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="478b2-184">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="478b2-185">Sie ersetzen **{Tenant}** durch Ihre spezifische institutionsspezifische Microsoft Azure Mandanten-ID.</span><span class="sxs-lookup"><span data-stu-id="478b2-185">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

<span data-ttu-id="478b2-186">Es wird ein Berechtigungsfenster angezeigt, in dem erläutert wird, dass Sie Blackboard Learn Ultra die Berechtigung erteilen, auf Microsoft Teams zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="478b2-186">You'll see a permissions window that explains you're giving permission to Blackboard Learn Ultra to access Microsoft Teams.</span></span>

![Das Berechtigungsfenster für Microsoft und Blackboard](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="478b2-188">Nach dem Konfigurieren der LTI-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="478b2-188">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="478b2-189">Navigieren Sie im **Administratorbereich** zu **Tools und Hilfsprogrammen,** und wählen Sie **Microsoft Teams Integrationsadministrator** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-189">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="478b2-190">Wählen Sie **"Microsoft Teams aktivieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-190">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="478b2-191">Fügen Sie Ihre **Microsoft-Mandanten-ID** in das verfügbare Textfeld ein.</span><span class="sxs-lookup"><span data-stu-id="478b2-191">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="478b2-192">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="478b2-192">Choose one of the following options:</span></span>

   - <span data-ttu-id="478b2-193">Wenn die App vorab zugestimmt hat, wird ein kleines Häkchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="478b2-193">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="478b2-194">Wenn das Häkchen angezeigt wird, wählen Sie **Absenden** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-194">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="478b2-195">Wenn die Zustimmung nicht genehmigt wurde, führen Sie die beschriebenen Schritte aus, um die URL für die Zustimmung zu generieren und zur Genehmigung an den Microsoft 365 globalen Administrator zu senden.</span><span class="sxs-lookup"><span data-stu-id="478b2-195">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="478b2-196">Nachdem Sie die Genehmigungsbestätigung erhalten haben, wählen Sie **"Erneut versuchen"** aus, um dies zu bestätigen, und wählen Sie dann **"Absenden"** aus.</span><span class="sxs-lookup"><span data-stu-id="478b2-196">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>

   ![Ein Dialogfeld, das angibt, dass Ihr Zugriff blockiert wurde](media/blocked-access.png)