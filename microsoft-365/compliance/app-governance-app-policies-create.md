---
title: Erstellen von App-Richtlinien
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Erstellen von App-Richtlinien.
ms.openlocfilehash: 66d8dda7c9cd768d6971e2b58dca4c9c5437e5bb
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438060"
---
# <a name="create-app-policies"></a><span data-ttu-id="a365f-103">Erstellen von App-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a365f-103">Create app policies</span></span>

><span data-ttu-id="a365f-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="a365f-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="a365f-105">Neben einer Reihe integrierter Funktionen zur Erkennung von anomalem App-Verhalten und zur Generierung von Warnungen sind App-Richtlinien in Microsoft-App-Governance eine Möglichkeit für Sie:</span><span class="sxs-lookup"><span data-stu-id="a365f-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="a365f-106">Geben Sie Bedingungen an, unter denen Sie von der App-Governance über das App-Verhalten informiert werden, um eine automatische oder manuelle Wartung vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="a365f-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="a365f-107">Implementieren Sie die App-Compliancerichtlinien für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="a365f-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="a365f-108">Sie können App-Richtlinien aus bereitgestellten Vorlagen erstellen, die angepasst werden können, oder Sie können eine eigene benutzerdefinierte App-Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="a365f-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="a365f-109">Um eine neue App-Richtlinie zu erstellen, wechseln Sie zur Seite **Microsoft 365 Compliance Center > App-Governance > Übersichtsseite > Richtlinien**:</span><span class="sxs-lookup"><span data-stu-id="a365f-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="a365f-110">Um eine neue App-Richtlinie mit Vorlagen für die App-Nutzung zu erstellen, wählen Sie **Richtlinie erstellen** unter **App-Nutzungsrichtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="a365f-111">Um eine neue App-Richtlinie mit Vorlagen für die App-Berechtigungen zu erstellen, wählen Sie **Richtlinie erstellen** unter **Berechtigungsrichtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="a365f-112">Um eine neue App-Richtlinie für die App-Zertifizierung oder eine benutzerdefinierte Richtlinie zu erstellen, wählen Sie **Neue erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="a365f-113">App-Richtlinienvorlagen</span><span class="sxs-lookup"><span data-stu-id="a365f-113">App policy templates</span></span>

<span data-ttu-id="a365f-114">Um eine neue App-Richtlinie basierend auf einer App-Richtlinienvorlage zu erstellen, wählen Sie auf der Seite **App-Richtlinienvorlage auswählen** eine App-Vorlagenkategorie, anschließend den Namen der Vorlage und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="a365f-115">App-Governance verfügt über drei Kategorien von App-Richtlinienvorlagen.</span><span class="sxs-lookup"><span data-stu-id="a365f-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="a365f-116">App-Benutzer- und -Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="a365f-116">App users and data access</span></span>

<span data-ttu-id="a365f-117">App-Governance stellt diese Vorlagen bereit, um Warnungen für die App-Nutzung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a365f-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="a365f-118">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="a365f-118">Template name</span></span> | <span data-ttu-id="a365f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a365f-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="a365f-120">Neue App mit einer großen Anzahl von Datenzugriffen</span><span class="sxs-lookup"><span data-stu-id="a365f-120">New app with a high volume of data access</span></span> | <span data-ttu-id="a365f-121">Hebt alle kürzlich registrierten Apps mit einer großen Anzahl von Datenzugriffen hervor, um sicherzustellen, dass es sich dabei um erwartete Datenmuster handelt.</span><span class="sxs-lookup"><span data-stu-id="a365f-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="a365f-p101">Standardmäßig kennzeichnet diese Richtlinie alle Apps, die in den letzten 7 Tagen registriert wurden und in diesem Zeitraum auf über mehr als 1 GB Daten zugreifen konnten. Diese Richtlinie kann mit weiteren Bedingungen und Aktionen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-p101">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period. This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="a365f-124">App-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="a365f-124">App Permissions</span></span>

<span data-ttu-id="a365f-125">App-Governance stellt diese Vorlagen bereit, um Warnungen für App-Berechtigungen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a365f-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="a365f-126">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="a365f-126">Template name</span></span> | <span data-ttu-id="a365f-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a365f-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="a365f-128">Überprivilegierte Apps</span><span class="sxs-lookup"><span data-stu-id="a365f-128">Overprivileged apps</span></span> | <span data-ttu-id="a365f-129">Hebt alle Apps hervor, denen mehr Berechtigungen erteilt wurden, als verwendet werden, um zu ermitteln, wo Berechtigungen reduziert werden können.</span><span class="sxs-lookup"><span data-stu-id="a365f-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="a365f-130">Standardmäßig kennzeichnet diese Richtlinie alle Apps, die als „Überprivilegiert“ gekennzeichnet sind, wenn sie 90 Tage lang nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="a365f-131">Dieser Zeitraumfilter kann mit weiteren Bedingungen und Aktionen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="a365f-132">Neue App mit hoher Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a365f-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="a365f-133">Hebt alle neuen Apps mit hoher Berechtigung hervor, um Apps mit potenziell großem Fußabdruck zu erkennen, die möglicherweise weitere Untersuchungen erfordern.</span><span class="sxs-lookup"><span data-stu-id="a365f-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="a365f-134">Standardmäßig werden durch diese Richtlinie alle Apps gekennzeichnet, die in den letzten 7 Tagen registriert wurden und über weitreichende Berechtigungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="a365f-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="a365f-135">App-Zertifizierung</span><span class="sxs-lookup"><span data-stu-id="a365f-135">App certification</span></span>

<span data-ttu-id="a365f-136">App-Governance stellt diese Vorlagen bereit, um Warnungen für App-Zertifizierungen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a365f-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="a365f-137">Vorlagenname</span><span class="sxs-lookup"><span data-stu-id="a365f-137">Template name</span></span> | <span data-ttu-id="a365f-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a365f-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="a365f-139">Neue, nicht zertifizierte App</span><span class="sxs-lookup"><span data-stu-id="a365f-139">New uncertified app</span></span> | <span data-ttu-id="a365f-140">Hebt neue Apps hervor, die nicht den App-Zertifizierungsprozess durchlaufen haben, um sicherzustellen, dass sie im Mandanten erwartet werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="a365f-141">Standardmäßig werden durch diese Richtlinie alle Apps gekennzeichnet, die in den letzten sieben Tagen registriert wurden und nicht zertifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="a365f-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="a365f-142">Benutzerdefinierte App-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a365f-142">Custom app policies</span></span>

<span data-ttu-id="a365f-143">Verwenden Sie eine benutzerdefinierte App-Richtlinie für Aktionen, die nicht bereits von einer der integrierten Vorlagen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="a365f-144">Um eine neue benutzerdefinierte App-Richtlinie zu erstellen, wählen Sie zuerst auf der Seite **Richtlinien** die Option **Neue erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="a365f-145">Wählen Sie auf der Seite **App-Richtlinienvorlage auswählen** die Kategorie **Benutzerdefiniert**, die Vorlage **Benutzerdefinierte Richtlinie** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="a365f-146">Konfigurieren Sie auf der Seite **Name und Beschreibung** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a365f-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="a365f-147">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="a365f-147">Policy Name</span></span>

- <span data-ttu-id="a365f-148">Richtlinienbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a365f-148">Policy Description</span></span>

- <span data-ttu-id="a365f-149">Wählen Sie den Richtlinienschweregrad aus, der den Schweregrad der von dieser Richtlinie generierten Warnungen festlegt.</span><span class="sxs-lookup"><span data-stu-id="a365f-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="a365f-150">High</span><span class="sxs-lookup"><span data-stu-id="a365f-150">High</span></span>
  - <span data-ttu-id="a365f-151">Medium</span><span class="sxs-lookup"><span data-stu-id="a365f-151">Medium</span></span>
  - <span data-ttu-id="a365f-152">Niedrig</span><span class="sxs-lookup"><span data-stu-id="a365f-152">Low</span></span>

<span data-ttu-id="a365f-153">Wählen Sie auf der Seite **Richtlinieneinstellungen und -bedingungen auswählen** für **Auswählen, für welche Apps diese Richtlinie gilt** Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a365f-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="a365f-154">Alle Apps</span><span class="sxs-lookup"><span data-stu-id="a365f-154">All Apps</span></span>
- <span data-ttu-id="a365f-155">Bestimmte Apps auswählen</span><span class="sxs-lookup"><span data-stu-id="a365f-155">Choose specific apps</span></span>

  <span data-ttu-id="a365f-156">In einem Bereich können Sie eine oder mehrere Apps auswählen.</span><span class="sxs-lookup"><span data-stu-id="a365f-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="a365f-157">Wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-157">Select **Add**.</span></span>

<span data-ttu-id="a365f-158">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-158">Select **Next**.</span></span>

<span data-ttu-id="a365f-159">Wählen Sie auf der Seite **Richtlinieneinstellungen und -bedingungen auswählen** die Option **Neue Bedingungen für Richtlinie festlegen** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="a365f-160">Im Bereich **Regel erstellen** können Sie Bedingungen für eine neue Regel auswählen.</span><span class="sxs-lookup"><span data-stu-id="a365f-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="a365f-161">Wählen Sie **Bedingung hinzufügen** aus. Wählen Sie dann Bedingungen aus der Liste aus, und geben Sie den Wert der Bedingung an.</span><span class="sxs-lookup"><span data-stu-id="a365f-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="a365f-162">Sie können mehrere Bedingungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a365f-162">You can add multiple conditions.</span></span>

<span data-ttu-id="a365f-163">Im Folgenden finden Sie die verfügbaren Bedingungen für eine benutzerdefinierte App-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a365f-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="a365f-164">Bedingung</span><span class="sxs-lookup"><span data-stu-id="a365f-164">Condition</span></span> | <span data-ttu-id="a365f-165">Akzeptierte Bedingungswerte</span><span class="sxs-lookup"><span data-stu-id="a365f-165">Condition values accepted</span></span> | <span data-ttu-id="a365f-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a365f-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="a365f-167">App-Registrierungsalter</span><span class="sxs-lookup"><span data-stu-id="a365f-167">App registration age</span></span> | <span data-ttu-id="a365f-168">Innerhalb der letzten x Tage</span><span class="sxs-lookup"><span data-stu-id="a365f-168">Within last X days</span></span> |  |
| <span data-ttu-id="a365f-169">App-Zertifizierung</span><span class="sxs-lookup"><span data-stu-id="a365f-169">App certification</span></span> | <span data-ttu-id="a365f-170">Grundlegende Compliance, MCAS-Compliance oder N/V</span><span class="sxs-lookup"><span data-stu-id="a365f-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="a365f-171">Microsoft 365-Zertifizierung</span><span class="sxs-lookup"><span data-stu-id="a365f-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="a365f-172">Herausgeberüberprüfung</span><span class="sxs-lookup"><span data-stu-id="a365f-172">Publisher verification</span></span> | <span data-ttu-id="a365f-173">Ja oder Nein</span><span class="sxs-lookup"><span data-stu-id="a365f-173">Yes or No</span></span> | [<span data-ttu-id="a365f-174">Herausgeberüberprüfung</span><span class="sxs-lookup"><span data-stu-id="a365f-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="a365f-175">Anwendungsberechtigung</span><span class="sxs-lookup"><span data-stu-id="a365f-175">Application Permission</span></span> | <span data-ttu-id="a365f-176">Wählen Sie mindestens eine API-Berechtigung aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="a365f-177">Microsoft Graph-Berechtigungsreferenz</span><span class="sxs-lookup"><span data-stu-id="a365f-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="a365f-178">Delegierte Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a365f-178">Delegated Permission</span></span> | <span data-ttu-id="a365f-179">Wählen Sie mindestens eine API-Berechtigung aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="a365f-180">Microsoft Graph-Berechtigungsreferenz</span><span class="sxs-lookup"><span data-stu-id="a365f-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="a365f-181">Hohe Berechtigung</span><span class="sxs-lookup"><span data-stu-id="a365f-181">High privilege</span></span> | <span data-ttu-id="a365f-182">Ja oder Nein</span><span class="sxs-lookup"><span data-stu-id="a365f-182">Yes or No</span></span> | <span data-ttu-id="a365f-183">Dies ist eine interne Bezeichnung, die auf der gleichen Logik basiert, die von MCAS verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a365f-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="a365f-184">Überprivilegierte App</span><span class="sxs-lookup"><span data-stu-id="a365f-184">Overprivileged app</span></span> | <span data-ttu-id="a365f-185">Ja oder Nein</span><span class="sxs-lookup"><span data-stu-id="a365f-185">Yes or No</span></span> | <span data-ttu-id="a365f-186">Apps, denen mehr Berechtigungen gewährt wurden, als von ihnen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="a365f-187">Zugriff auf App-Daten</span><span class="sxs-lookup"><span data-stu-id="a365f-187">App data access</span></span> | <span data-ttu-id="a365f-188">Mehr als x GB Datenzugriff pro Stunde</span><span class="sxs-lookup"><span data-stu-id="a365f-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="a365f-189">Trend des Zugriffs auf App-Daten</span><span class="sxs-lookup"><span data-stu-id="a365f-189">App data access trend</span></span> | <span data-ttu-id="a365f-190">x % Erhöhung der Datennutzung in den letzten 7 Tagen</span><span class="sxs-lookup"><span data-stu-id="a365f-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="a365f-191">App-API-Zugriff</span><span class="sxs-lookup"><span data-stu-id="a365f-191">App API Access</span></span> | <span data-ttu-id="a365f-192">Mehr als x API-Aufrufe pro Stunde</span><span class="sxs-lookup"><span data-stu-id="a365f-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="a365f-193">Trend des App-API-Zugriffs</span><span class="sxs-lookup"><span data-stu-id="a365f-193">App API Access trend</span></span> | <span data-ttu-id="a365f-194">x % Erhöhung der API-Aufrufe in den letzten 7 Tagen</span><span class="sxs-lookup"><span data-stu-id="a365f-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="a365f-195">Benutzer, die zugestimmt haben</span><span class="sxs-lookup"><span data-stu-id="a365f-195">Users consented</span></span> | <span data-ttu-id="a365f-196">(Größer als oder kleiner als) x Benutzer, die zugestimmt haben</span><span class="sxs-lookup"><span data-stu-id="a365f-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="a365f-197">Prioritärer Benutzer hat zugestimmt</span><span class="sxs-lookup"><span data-stu-id="a365f-197">Priority user consented</span></span> | <span data-ttu-id="a365f-198">Ja oder Nein</span><span class="sxs-lookup"><span data-stu-id="a365f-198">Yes or No</span></span> | <span data-ttu-id="a365f-199">Benutzer mit einem [Prioritätskonto](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="a365f-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="a365f-200">App zugestimmt von</span><span class="sxs-lookup"><span data-stu-id="a365f-200">App consented by</span></span> | <span data-ttu-id="a365f-201">Benutzer aus Liste auswählen</span><span class="sxs-lookup"><span data-stu-id="a365f-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="a365f-202">Rolle des zustimmenden Benutzers</span><span class="sxs-lookup"><span data-stu-id="a365f-202">Consenting user’s role</span></span> | <span data-ttu-id="a365f-203">Wählen Sie einen oder mehrere aus: Teams-Administrator, Verzeichnisleseberechtigter, Sicherheitsleseberechtigter, Complianceadministrator, Sicherheitsadministrator, Helpdeskadministrator, SharePoint-Administrator, Exchange-Administrator, Globaler Leseberechtigter, Globaler Administrator, Compliancedatenadministrator, Benutzeradministrator, Dienstsupportadministrator</span><span class="sxs-lookup"><span data-stu-id="a365f-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="a365f-204">Mehrfachauswahl zulässig.</span><span class="sxs-lookup"><span data-stu-id="a365f-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="a365f-205">Jede Azure AD-Rolle mit zugewiesenem Mitglied sollte in dieser Liste verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="a365f-206">Zugriff auf Workload</span><span class="sxs-lookup"><span data-stu-id="a365f-206">Workload accessed</span></span> | <span data-ttu-id="a365f-207">OneDrive und/oder SharePoint und/oder Exchange</span><span class="sxs-lookup"><span data-stu-id="a365f-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="a365f-208">Mehrfachauswahl zulässig.</span><span class="sxs-lookup"><span data-stu-id="a365f-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="a365f-209">Fehlerrate</span><span class="sxs-lookup"><span data-stu-id="a365f-209">Error rate</span></span> | <span data-ttu-id="a365f-210">Die Fehlerrate ist in den letzten 7 Tagen größer als x %, wobei x ein vom Administrator definierter Wert ist.</span><span class="sxs-lookup"><span data-stu-id="a365f-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="a365f-211">Alle angegebenen Bedingungen müssen erfüllt sein, damit diese App-Richtlinie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="a365f-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="a365f-212">Wenn Sie alle gewünschten Bedingungen angegeben haben, wählen Sie **Speichern** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="a365f-213">Wählen Sie auf der Seite **Richtlinienaktionen definieren** die Option **App deaktivieren** aus, wenn die App-Governance die App deaktivieren soll, sobald eine Warnung basierend auf dieser Richtlinie generiert wird, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="a365f-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="a365f-214">Wählen Sie auf der Seite **Richtlinienstatus definieren** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a365f-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="a365f-215">**Überwachungsmodus**: Richtlinien werden ausgewertet, aber konfigurierte Aktionen werden nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a365f-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="a365f-216">Richtlinien für den Überwachungsmodus werden in der Liste der Richtlinien mit dem Status **Überwachung** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a365f-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="a365f-217">**Aktiv**: Richtlinien werden ausgewertet, und die konfigurierten Aktionen werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a365f-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="a365f-218">**Inaktiv**: Richtlinien werden nicht ausgewertet, und die konfigurierten Aktionen werden nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a365f-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="a365f-219">Testen und Überwachen Ihrer neuen App-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="a365f-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="a365f-220">Nachdem Ihre App-Richtlinie erstellt wurde, sollten Sie sie auf der Seite **Richtlinien** überwachen, um sicherzustellen, dass während des Tests eine erwartete Anzahl aktiver Warnungen und gesamter Warnungen registriert werden.</span><span class="sxs-lookup"><span data-stu-id="a365f-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![Übersichtsseite der MAPG-Richtlinien im Microsoft 365 Compliance Center mit einer hervorgehobenen Richtlinie](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="a365f-222">Wenn die Anzahl der Warnungen unerwartet niedrig ist, bearbeiten Sie die Einstellungen der App-Richtlinie, um sicherzustellen, dass Sie sie ordnungsgemäß konfiguriert haben, bevor Sie ihren Status festlegen.</span><span class="sxs-lookup"><span data-stu-id="a365f-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="a365f-223">Im Folgenden finden Sie ein Beispiel für einen Prozess zum Erstellen, Testen und anschließenden Aktivieren der Richtlinie:</span><span class="sxs-lookup"><span data-stu-id="a365f-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="a365f-224">Erstellen Sie die neue Richtlinie mit Schweregrad, Apps, Bedingungen und Aktionen, legen Sie Ausgangswerte fest, und setzen Sie den Status auf **Überwachungsmodus**.</span><span class="sxs-lookup"><span data-stu-id="a365f-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="a365f-225">Überprüfen Sie auf erwartetes Verhalten, z. B. generierte Warnungen.</span><span class="sxs-lookup"><span data-stu-id="a365f-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="a365f-226">Wenn das Verhalten nicht den Erwartungen entspricht, bearbeiten Sie die Richtlinien-Apps, Bedingungen und Aktionseinstellungen nach Bedarf, und kehren Sie zu Schritt 2 zurück.</span><span class="sxs-lookup"><span data-stu-id="a365f-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="a365f-227">Wenn das Verhalten den Erwartungen entspricht, bearbeiten Sie die Richtlinie, und ändern Sie ihren Status in **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="a365f-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![Der Workflow zum Erstellen von App-Richtlinien](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="a365f-229">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="a365f-229">Next step</span></span>

[<span data-ttu-id="a365f-230">Verwalten Sie Ihre App-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="a365f-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
