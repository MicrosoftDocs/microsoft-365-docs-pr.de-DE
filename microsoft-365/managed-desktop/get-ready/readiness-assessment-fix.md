---
title: Beheben von Problemen, die mit dem Readiness Assessment Tool gefunden wurden
description: Detaillierte Aktionen, die für jedes von dem Tool gefundene Problem ausgeführt werden sollten
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 642de80e1a133f212b7afb6774d9aab2eeaabdbf
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941409"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="06b2a-104">Beheben von Problemen, die mit dem Readiness Assessment Tool gefunden wurden</span><span class="sxs-lookup"><span data-stu-id="06b2a-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="06b2a-105">Für jede Überprüfung meldet das Tool eine von vier möglichen Ergebnissen:</span><span class="sxs-lookup"><span data-stu-id="06b2a-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="06b2a-106">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="06b2a-106">Result</span></span>  |<span data-ttu-id="06b2a-107">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="06b2a-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="06b2a-108">Bereit</span><span class="sxs-lookup"><span data-stu-id="06b2a-108">Ready</span></span>     | <span data-ttu-id="06b2a-109">Vor Abschluss der Registrierung ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06b2a-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="06b2a-110">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="06b2a-110">Advisory</span></span>    | <span data-ttu-id="06b2a-111">Befolgen Sie die Schritte im Tool oder in diesem Artikel, um die besten Erfahrungen bei der Registrierung und für Benutzer zu finden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="06b2a-112">Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie das erste Gerät bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="06b2a-113">Nicht bereit</span><span class="sxs-lookup"><span data-stu-id="06b2a-113">Not ready</span></span> | <span data-ttu-id="06b2a-114">*Die Registrierung schlägt fehl, wenn Sie diese Probleme nicht beheben.*</span><span class="sxs-lookup"><span data-stu-id="06b2a-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="06b2a-115">Befolgen Sie die Schritte im Tool oder in diesem Artikel, um Sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="06b2a-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="06b2a-116">Fehler</span><span class="sxs-lookup"><span data-stu-id="06b2a-116">Error</span></span> | <span data-ttu-id="06b2a-117">Die von Ihnen verwendete Azure Active Director (AD)-Rolle verfügt nicht über ausreichende Berechtigungen zum Ausführen dieser Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="06b2a-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="06b2a-118">Microsoft InTune-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="06b2a-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="06b2a-119">Autopilot-Bereitstellungsprofil</span><span class="sxs-lookup"><span data-stu-id="06b2a-119">Autopilot deployment profile</span></span>

<span data-ttu-id="06b2a-120">Es sollten keine Autopilot-Profile vorhanden sein, die auf zugewiesene oder dynamische Gruppen abzielen, die von Microsoft Managed Desktop verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="06b2a-121">Microsoft Managed Desktop verwendet Autopilot, um neue Geräte vorzusehen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="06b2a-122">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-122">**Not ready**</span></span>

<span data-ttu-id="06b2a-123">Sie verfügen über ein Autopilot-Profil, das allen Geräten zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="06b2a-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="06b2a-124">Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="06b2a-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="06b2a-125">Nachdem Sie die Microsoft Managed Desktop-Registrierung eingerichtet haben, müssen Sie Ihre Autopilot-Richtlinie so konfigurieren, dass die **modernen Arbeitsplatz Geräte-alle** Azure Ad Gruppe ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="06b2a-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="06b2a-126">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-126">**Advisory**</span></span>

<span data-ttu-id="06b2a-127">Stellen Sie sicher, dass Ihre Autopilot-Profile auf eine zugewiesene oder dynamische Azure Ad Gruppe Zielen, die keine von Microsoft verwalteten Desktop-Geräte enthält, die bei der Registrierung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="06b2a-128">Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="06b2a-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="06b2a-129">Nachdem Sie die Microsoft Managed Desktop-Registrierung eingerichtet haben, müssen Sie Ihre Autopilot-Richtlinie so konfigurieren, dass die **modernen Arbeitsplatz Geräte-alle** Azure Ad Gruppe ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="06b2a-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="06b2a-130">Zertifikat-Konnektoren</span><span class="sxs-lookup"><span data-stu-id="06b2a-130">Certificate connectors</span></span>

<span data-ttu-id="06b2a-131">Wenn Sie über die von den Geräten, die Sie in Microsoft Managed Desktop registrieren möchten, verwendeten Zertifikat-Konnektoren haben, können die Connectors keine Fehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="06b2a-132">Nur einer der folgenden Hinweise wird auf Ihre Situation zutreffen, daher sollten Sie Sie sorgfältig überprüfen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="06b2a-133">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-133">**Advisory**</span></span>

<span data-ttu-id="06b2a-134">Es sind keine Zertifikat-Konnektoren vorhanden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-134">No certificate connectors are present.</span></span> <span data-ttu-id="06b2a-135">Es ist möglich, dass Sie keine Konnektoren benötigen, aber Sie sollten überprüfen, ob Sie möglicherweise einige für die Netzwerkkonnektivität mit Microsoft Managed Desktop-Geräten benötigen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-136">Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="06b2a-137">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-137">**Advisory**</span></span>

<span data-ttu-id="06b2a-138">Mindestens ein Zertifikat-Konnektor hat einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="06b2a-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="06b2a-139">Wenn Sie diesen Connector für die Verbindung mit Microsoft Managed Desktop-Geräten benötigen, müssen Sie den Fehler beheben.</span><span class="sxs-lookup"><span data-stu-id="06b2a-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="06b2a-140">Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="06b2a-141">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-141">**Advisory**</span></span>

<span data-ttu-id="06b2a-142">Sie verfügen über mindestens einen Zertifikat-Konnektor, und es werden keine Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="06b2a-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="06b2a-143">Möglicherweise müssen Sie jedoch ein Profil erstellen, um den Connector für Microsoft Managed Desktop-Geräte wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-144">Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="06b2a-145">Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="06b2a-145">Conditional access policies</span></span>

<span data-ttu-id="06b2a-146">Richtlinien für bedingten Zugriff in ihrer Azure AD Organisation dürfen keine Microsoft Manage Desktop-Benutzer abzielen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="06b2a-147">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-147">**Not ready**</span></span>

<span data-ttu-id="06b2a-148">Sie haben mindestens eine Richtlinie für den bedingten Zugriff, die auf alle Benutzer abzielt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="06b2a-149">Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe zurück, die nicht die Azure Ad Gruppe von Microsoft Managed Desktop-Dienstkonten enthält, die bei der Registrierung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="06b2a-150">Schritte finden Sie unter [bedingter Zugriff: Benutzer und Gruppen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="06b2a-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="06b2a-151">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-151">**Advisory**</span></span>

<span data-ttu-id="06b2a-152">Stellen Sie sicher, dass alle Richtlinien für den bedingten Zugriff die Azure Ad Gruppe für **moderne Arbeitsplatz Dienstkonten** ausschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="06b2a-153">Schritte finden Sie unter [Anpassen des bedingten Zugriffs](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="06b2a-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="06b2a-154">Die **Dienstkonten für moderne Arbeitsplatz Dienste** Azure Ad Gruppe ist eine dynamische Gruppe, die wir bei der Registrierung für den Dienst erstellen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="06b2a-155">Sie müssen zurückkehren, um diese Gruppe nach der Registrierung auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="06b2a-156">Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard Operating Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="06b2a-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="06b2a-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="06b2a-157">**Error**</span></span>

<span data-ttu-id="06b2a-158">Die Intune-Administrator Rolle verfügt über keine ausreichenden Berechtigungen für diese Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="06b2a-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="06b2a-159">Sie benötigen auch eine dieser Azure AD Rollen, die zum Ausführen dieser Überprüfung zugewiesen sind:</span><span class="sxs-lookup"><span data-stu-id="06b2a-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="06b2a-160">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="06b2a-160">Security Reader</span></span>
- <span data-ttu-id="06b2a-161">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="06b2a-161">Security Administrator</span></span>
- <span data-ttu-id="06b2a-162">Administrator für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="06b2a-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="06b2a-163">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="06b2a-163">Global Reader</span></span>
- <span data-ttu-id="06b2a-164">Geräte Administrator</span><span class="sxs-lookup"><span data-stu-id="06b2a-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="06b2a-165">Geräte Konformitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="06b2a-165">Device Compliance policies</span></span>

<span data-ttu-id="06b2a-166">InTune-Geräte Konformitätsrichtlinien in ihrer Azure AD Organisation dürfen keine Microsoft Managed Desktop-Benutzer adressieren.</span><span class="sxs-lookup"><span data-stu-id="06b2a-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="06b2a-167">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-167">**Not ready**</span></span>

<span data-ttu-id="06b2a-168">Sie haben mindestens eine Konformitätsrichtlinie, die auf alle Benutzer abzielt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="06b2a-169">Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe, die keine Benutzer von Microsoft Managed Desktop enthält.</span><span class="sxs-lookup"><span data-stu-id="06b2a-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="06b2a-170">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="06b2a-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="06b2a-171">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-171">**Advisory**</span></span>

<span data-ttu-id="06b2a-172">Stellen Sie sicher, dass alle Konformitätsrichtlinien, die Sie verwenden, keine von Microsoft verwalteten Desktop Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="06b2a-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="06b2a-173">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="06b2a-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="06b2a-174">Geräte Konfigurationsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="06b2a-174">Device Configuration policies</span></span>

<span data-ttu-id="06b2a-175">InTune-Geräte Konfigurationsrichtlinien in ihrer Azure AD Organisation dürfen keine Microsoft Manage-Desktop Geräte oder-Benutzer als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="06b2a-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="06b2a-176">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-176">**Not ready**</span></span>

<span data-ttu-id="06b2a-177">Sie verfügen über mindestens eine Konfigurationsrichtlinie, die auf alle Benutzer, alle Geräte oder beides abzielt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="06b2a-178">Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe, die keine verwalteten Desktop Geräte von Microsoft enthält, zurück.</span><span class="sxs-lookup"><span data-stu-id="06b2a-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-179">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="06b2a-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="06b2a-180">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-180">**Advisory**</span></span>

<span data-ttu-id="06b2a-181">Stellen Sie sicher, dass alle Konformitätsrichtlinien, die Sie verwenden, keine von Microsoft verwalteten Desktop Geräte oder Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="06b2a-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="06b2a-182">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="06b2a-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="06b2a-183">Einschränkungen für Gerätetypen</span><span class="sxs-lookup"><span data-stu-id="06b2a-183">Device type restrictions</span></span>

<span data-ttu-id="06b2a-184">Microsoft Managed Desktop-Geräte müssen sich in InTune registrieren können.</span><span class="sxs-lookup"><span data-stu-id="06b2a-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="06b2a-185">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-185">**Not ready**</span></span>

<span data-ttu-id="06b2a-186">Befolgen Sie die Schritte unter [Festlegen von Registrierungs Einschränkungen](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) , um die Einstellung in **zulassen** zu ändern.</span><span class="sxs-lookup"><span data-stu-id="06b2a-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="06b2a-187">Seite "Registrierungs Status"</span><span class="sxs-lookup"><span data-stu-id="06b2a-187">Enrollment Status Page</span></span>

<span data-ttu-id="06b2a-188">Derzeit ist die Registrierungs Status Seite (ESP) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="06b2a-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="06b2a-189">Wenn Sie an der öffentlichen Vorschau dieses Features teilnehmen, können Sie dieses Element ignorieren.</span><span class="sxs-lookup"><span data-stu-id="06b2a-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="06b2a-190">Weitere Informationen finden Sie unter [First-Run-Erfahrung mit Autopilot und der Registrierungs Status Seite](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="06b2a-191">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-191">**Not ready**</span></span>

<span data-ttu-id="06b2a-192">Sie haben das ESP-Standardprofil festgelegt, um den **Fortschritt der APP-und Profilkonfiguration anzuzeigen**.</span><span class="sxs-lookup"><span data-stu-id="06b2a-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="06b2a-193">Deaktivieren Sie diese Einstellung, oder stellen Sie sicher, dass die Zuweisungen für eine beliebige Azure Ad Gruppe keine von Microsoft verwalteten Desktop Geräte enthalten, indem Sie die Schritte unter [Einrichten der Registrierungs Status Seite](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)befolgen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="06b2a-194">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-194">**Advisory**</span></span>

<span data-ttu-id="06b2a-195">Stellen Sie sicher, dass alle Profile mit der Einstellung " **App-und Profil Konfigurationsstatus anzeigen** " keiner Azure Ad Gruppe zugeordnet sind, die Microsoft Managed Desktop-Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="06b2a-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-196">Weitere Informationen finden Sie unter [Einrichten der Registrierungs Status Seite](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="06b2a-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="06b2a-197">InTune-Registrierung</span><span class="sxs-lookup"><span data-stu-id="06b2a-197">Intune enrollment</span></span>

<span data-ttu-id="06b2a-198">Windows 10-Geräte in ihrer Azure AD Organisation müssen automatisch in InTune registriert sein.</span><span class="sxs-lookup"><span data-stu-id="06b2a-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="06b2a-199">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-199">**Advisory**</span></span>

<span data-ttu-id="06b2a-200">Stellen Sie sicher, dass der MDM-Benutzerbereich auf " **some** " oder " **all** " festgelegt ist, nicht auf **None**.</span><span class="sxs-lookup"><span data-stu-id="06b2a-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="06b2a-201">Wenn Sie **einige** auswählen, kehren Sie nach der Registrierung zurück, und wählen Sie die Gruppe **moderner Arbeitsplatz-alle** Azure AD für **Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="06b2a-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="06b2a-202">Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="06b2a-202">Microsoft Store for Business</span></span>

<span data-ttu-id="06b2a-203">Microsoft Store for Business wird verwendet, damit Sie das Unternehmens Portal herunterladen können, um einige apps wie Microsoft Project und Microsoft Visio bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="06b2a-204">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-204">**Not ready**</span></span>

<span data-ttu-id="06b2a-205">Microsoft Store for Business ist entweder nicht aktiviert oder nicht mit InTune synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="06b2a-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="06b2a-206">Weitere Informationen finden Sie unter [Verwalten von Volumen erworbenen Apps aus dem Microsoft Store for Business mit Microsoft InTune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) und [Installieren des InTune-Unternehmensportals auf auf Geräten](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="06b2a-207">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="06b2a-207">Multi-factor authentication</span></span>

<span data-ttu-id="06b2a-208">Die mehrstufige Authentifizierung darf nicht versehentlich auf von Microsoft verwaltete Desktop Dienstkonten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="06b2a-209">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-209">**Not ready**</span></span>

<span data-ttu-id="06b2a-210">Sie haben einige Richtlinien für die mehrstufige Authentifizierung (MFA) als "erforderlich" für Richtlinien für bedingten Zugriff festgelegt, die allen Benutzern zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="06b2a-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="06b2a-211">Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="06b2a-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-212">Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="06b2a-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="06b2a-213">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-213">**Advisory**</span></span>

<span data-ttu-id="06b2a-214">Stellen Sie sicher, dass alle bedingten Zugriffsrichtlinien, die MFA erfordern, den **modernen Arbeitsplatz-alle** Azure Ad Gruppe ausschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="06b2a-215">Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="06b2a-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="06b2a-216">Die Gruppe " **moderner Arbeitsplatz-alle** Azure AD" ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="06b2a-217">**Error**</span><span class="sxs-lookup"><span data-stu-id="06b2a-217">**Error**</span></span>

<span data-ttu-id="06b2a-218">Die Intune-Administrator Rolle verfügt über keine ausreichenden Berechtigungen für diese Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="06b2a-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="06b2a-219">Sie benötigen auch eine dieser Azure AD Rollen, die zum Ausführen dieser Überprüfung zugewiesen sind:</span><span class="sxs-lookup"><span data-stu-id="06b2a-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="06b2a-220">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="06b2a-220">Security Reader</span></span>
- <span data-ttu-id="06b2a-221">Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="06b2a-221">Security Administrator</span></span>
- <span data-ttu-id="06b2a-222">Administrator für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="06b2a-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="06b2a-223">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="06b2a-223">Global Reader</span></span>
- <span data-ttu-id="06b2a-224">Geräte Administrator</span><span class="sxs-lookup"><span data-stu-id="06b2a-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="06b2a-225">PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="06b2a-225">PowerShell scripts</span></span>

<span data-ttu-id="06b2a-226">Windows PowerShell Skripts können nicht auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop-Geräte abzielt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="06b2a-227">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-227">**Advisory**</span></span>

<span data-ttu-id="06b2a-228">Stellen Sie sicher, dass Windows PowerShell Skripts in ihrer Azure AD Organisation nicht auf Microsoft Manage-Desktop Geräte oder-Benutzer abzielen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="06b2a-229">Weisen Sie kein PowerShell-Skript zu, das auf alle Benutzer, alle Geräte oder beides abzielt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="06b2a-230">Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="06b2a-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-231">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Skripts auf Windows 10-Geräten in InTune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="06b2a-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="06b2a-232">Region</span><span class="sxs-lookup"><span data-stu-id="06b2a-232">Region</span></span>

<span data-ttu-id="06b2a-233">Ihre Region muss von Microsoft Managed Desktop unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="06b2a-234">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-234">**Not ready**</span></span>

<span data-ttu-id="06b2a-235">Ihre Azure AD Organisations Region wird derzeit nicht von Microsoft Managed Desktop unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="06b2a-236">Weitere Informationen finden Sie unter [unterstützte Regionen und Sprachen in Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="06b2a-237">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-237">**Advisory**</span></span>

<span data-ttu-id="06b2a-238">Mindestens ein Land, in dem sich Ihre Azure AD Organisation befindet, wird von Microsoft Managed Desktop nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="06b2a-239">Weitere Informationen finden Sie unter [unterstützte Regionen und Sprachen in Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="06b2a-240">Sicherheitsbasislinien</span><span class="sxs-lookup"><span data-stu-id="06b2a-240">Security baselines</span></span>

<span data-ttu-id="06b2a-241">Sicherheitsbasislinien sollten nicht auf Microsoft Managed Desktop-Geräte abzielen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="06b2a-242">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-242">**Not ready**</span></span>

<span data-ttu-id="06b2a-243">Sie verfügen über ein Sicherheitsbasis Profil, das auf alle Benutzer, alle Geräte oder beides abzielt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="06b2a-244">Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="06b2a-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-245">Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="06b2a-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="06b2a-246">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-246">**Advisory**</span></span>

<span data-ttu-id="06b2a-247">Stellen Sie sicher, dass alle Sicherheitsbasis Richtlinien, auf denen Sie Microsoft Managed Desktop-Geräte ausschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-248">Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="06b2a-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="06b2a-249">Die **moderne Arbeitsplatz Geräte-alle** Azure Ad Gruppe ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="06b2a-250">Windows-apps</span><span class="sxs-lookup"><span data-stu-id="06b2a-250">Windows apps</span></span>

<span data-ttu-id="06b2a-251">Überprüfen Sie die apps, die Ihre Microsoft Managed Desktop-Benutzer haben sollen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="06b2a-252">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-252">**Advisory**</span></span>

<span data-ttu-id="06b2a-253">Sie sollten eine Inventarisierung der apps vorbereiten, die ihre von Microsoft verwalteten Desktop-Benutzer haben sollen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="06b2a-254">Stellen Sie sicher, dass diese apps von InTune bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="06b2a-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="06b2a-255">Weitere Informationen finden Sie unter [apps in Microsoft Managed Desktop](apps.md).</span><span class="sxs-lookup"><span data-stu-id="06b2a-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="06b2a-256">Sie können Ihren Microsoft-Konto Vertreter für eine Abfrage im Microsoft Endpoint Configuration Manager bitten, um die apps zu identifizieren, die für die Migration zu InTune bereit sind oder Anpassungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="06b2a-257">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="06b2a-257">Windows Hello for Business</span></span>

<span data-ttu-id="06b2a-258">Microsoft Managed Desktop erfordert die Aktivierung von Windows Hello for Business.</span><span class="sxs-lookup"><span data-stu-id="06b2a-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="06b2a-259">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-259">**Not ready**</span></span>

<span data-ttu-id="06b2a-260">Windows Hello for Business ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="06b2a-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="06b2a-261">Aktivieren Sie es, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) ausführen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="06b2a-262">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-262">**Advisory**</span></span>

<span data-ttu-id="06b2a-263">Windows Hello for Business ist nicht eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="06b2a-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="06b2a-264">Aktivieren Sie es, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)ausführen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="06b2a-265">Windows 10-Update klingelt</span><span class="sxs-lookup"><span data-stu-id="06b2a-265">Windows 10 update rings</span></span>

<span data-ttu-id="06b2a-266">Die Richtlinie "Windows 10 Update Ring" in InTune darf nicht auf Microsoft-verwaltete Desktop Geräte abzielen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="06b2a-267">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-267">**Not ready**</span></span>

<span data-ttu-id="06b2a-268">Sie haben eine Richtlinie "Update Ring", die auf alle Geräte, alle Benutzer oder beides abzielt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="06b2a-269">Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="06b2a-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="06b2a-270">Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="06b2a-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="06b2a-271">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-271">**Advisory**</span></span>

<span data-ttu-id="06b2a-272">Stellen Sie sicher, dass alle Update Ring-Richtlinien den **modernen Arbeitsplatz-alle** Azure Ad Gruppe ausschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-272">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="06b2a-273">Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="06b2a-273">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="06b2a-274">Die **moderne Arbeitsplatz Geräte-alle** Azure Ad Gruppe ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-274">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="06b2a-275">Azure Active Directory-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="06b2a-275">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="06b2a-276">Ad-hoc-Abonnements</span><span class="sxs-lookup"><span data-stu-id="06b2a-276">Ad hoc subscriptions</span></span>

<span data-ttu-id="06b2a-277">Gibt an, wie eine Einstellung überprüft wird, die (wenn Sie auf "false" festgelegt ist) möglicherweise verhindert, dass das Roaming von Unternehmensstatus ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="06b2a-277">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="06b2a-278">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-278">**Advisory**</span></span>

<span data-ttu-id="06b2a-279">Stellen Sie sicher, dass **AllowAdHocSubscriptions** auf **true** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="06b2a-279">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="06b2a-280">Andernfalls funktioniert das Roaming im Enterprise-Status möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="06b2a-280">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="06b2a-281">Weitere Informationen finden Sie unter [Sets-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="06b2a-281">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="06b2a-282">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="06b2a-282">Enterprise State Roaming</span></span>

<span data-ttu-id="06b2a-283">Das Enterprise-Status-Roaming sollte aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="06b2a-283">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="06b2a-284">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-284">**Advisory**</span></span>

<span data-ttu-id="06b2a-285">Stellen Sie sicher, dass das Enterprise-Status-Roaming für **alle** oder für **ausgewählte** Gruppen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="06b2a-285">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="06b2a-286">Weitere Informationen finden Sie unter [enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="06b2a-286">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="06b2a-287">Lizenzen</span><span class="sxs-lookup"><span data-stu-id="06b2a-287">Licenses</span></span>

<span data-ttu-id="06b2a-288">Für die Verwendung von Microsoft Managed Desktop sind eine Reihe von Lizenzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="06b2a-288">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="06b2a-289">**Nicht einsatzfähig**</span><span class="sxs-lookup"><span data-stu-id="06b2a-289">**Not Ready**</span></span>

<span data-ttu-id="06b2a-290">Sie verfügen nicht über alle Lizenzen, die Sie für die Verwendung von Microsoft Managed Desktop benötigen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-290">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="06b2a-291">Weitere Informationen finden Sie unter [Microsoft Managed Desktop Technologies](../intro/technologies.md) und [mehr zu Lizenzen](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="06b2a-291">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="06b2a-292">Namen von Sicherheitskonten</span><span class="sxs-lookup"><span data-stu-id="06b2a-292">Security account names</span></span>

<span data-ttu-id="06b2a-293">Bestimmte Namen von Sicherheitskonten können Konflikte mit denen verursachen, die von Microsoft Managed Desktop erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-293">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="06b2a-294">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-294">**Not ready**</span></span>

<span data-ttu-id="06b2a-295">Sie haben mindestens einen Kontonamen, der mit den von Microsoft Managed Desktop erstellten Konflikten in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="06b2a-295">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="06b2a-296">Arbeiten Sie mit Ihrem Microsoft-Konto Vertreter zusammen, um diese Kontonamen auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-296">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="06b2a-297">Sicherheitsadministrator Rollen</span><span class="sxs-lookup"><span data-stu-id="06b2a-297">Security administrator roles</span></span>

<span data-ttu-id="06b2a-298">Benutzer mit bestimmten Sicherheitsrollen müssen diese in Microsoft Defender für Endpoint zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="06b2a-298">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="06b2a-299">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-299">**Advisory**</span></span>

<span data-ttu-id="06b2a-300">Wenn Sie eine dieser Rollen in ihrer Azure AD Organisation zugewiesen haben, stellen Sie sicher, dass diese Rollen auch in Microsoft Defender für Endpoint zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="06b2a-300">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="06b2a-301">Andernfalls können Administratoren mit diesen Rollen nicht auf das Verwaltungsportal zugreifen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-301">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="06b2a-302">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="06b2a-302">Security Reader</span></span>
- <span data-ttu-id="06b2a-303">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="06b2a-303">Security Operator</span></span>
- <span data-ttu-id="06b2a-304">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="06b2a-304">Global Reader</span></span>

<span data-ttu-id="06b2a-305">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="06b2a-305">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="06b2a-306">Sicherheitsstandard</span><span class="sxs-lookup"><span data-stu-id="06b2a-306">Security default</span></span>

<span data-ttu-id="06b2a-307">Sicherheitsstandards in Azure Active Directory verhindern, dass von Microsoft Managed Desktop Ihre Geräte verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-307">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="06b2a-308">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="06b2a-308">**Not ready**</span></span>

<span data-ttu-id="06b2a-309">Sie haben Sicherheitsstandards aktiviert.</span><span class="sxs-lookup"><span data-stu-id="06b2a-309">You have Security defaults turned on.</span></span> <span data-ttu-id="06b2a-310">Deaktivieren Sie Sicherheitseinstellungen, und richten Sie Richtlinien für bedingten Zugriff ein.</span><span class="sxs-lookup"><span data-stu-id="06b2a-310">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="06b2a-311">Weitere Informationen finden Sie unter [Common Conditional Access Policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="06b2a-311">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="06b2a-312">Zurücksetzen von Self-Service-Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="06b2a-312">Self-service Password Reset</span></span>

<span data-ttu-id="06b2a-313">Self-Service Password Reset (SSPR) sollte für alle Benutzer mit Ausnahme von Microsoft Managed Desktop-Dienstkonten aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="06b2a-313">Self-service Password Reset (SSPR) should be enabled for all users excluding Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="06b2a-314">Weitere Informationen finden Sie unter [Lernprogramm: Aktivieren von Benutzern zum Entsperren Ihres Kontos oder Zurücksetzen von Kennwörtern mithilfe von Azure Active Directory Self-Service Password Reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="06b2a-314">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="06b2a-315">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-315">**Advisory**</span></span>

<span data-ttu-id="06b2a-316">Stellen Sie sicher, dass die SSPR **Selected** -Einstellung Microsoft Managed Desktop-Geräte enthält, aber Microsoft Managed Desktop-Dienstkonten ausschließt.</span><span class="sxs-lookup"><span data-stu-id="06b2a-316">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices but excludes Microsoft Managed Desktop service accounts.</span></span> <span data-ttu-id="06b2a-317">Microsoft Managed Desktop-Dienstkonten können nicht wie erwartet funktionieren, wenn SSPR aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="06b2a-317">Microsoft Managed Desktop service accounts cannot work as expected when SSPR is enabled.</span></span>  


### <a name="standard-user-role"></a><span data-ttu-id="06b2a-318">Standard Benutzerrolle</span><span class="sxs-lookup"><span data-stu-id="06b2a-318">Standard user role</span></span>

<span data-ttu-id="06b2a-319">Neben den Benutzern, denen Azure AD Rollen globaler Administrator und Geräteadministrator zugewiesen sind, sind Microsoft Managed Desktop-Benutzer Standardbenutzer ohne lokale Administratorrechte.</span><span class="sxs-lookup"><span data-stu-id="06b2a-319">Other than those users who are assigned Azure AD roles of Global administrator and Device administrator, Microsoft Managed Desktop users will be standard users without local administrator privileges.</span></span> <span data-ttu-id="06b2a-320">Allen anderen Benutzern wird beim Starten Ihres von Microsoft verwalteten Desktop Geräts eine Standardbenutzerrolle zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-320">All other users will be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="06b2a-321">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-321">**Advisory**</span></span>

<span data-ttu-id="06b2a-322">Microsoft Managed Desktop-Benutzer verfügen nicht über lokale Administratorrechte auf Ihren von Microsoft verwalteten Desktopgeräten, nachdem Sie sich registriert haben.</span><span class="sxs-lookup"><span data-stu-id="06b2a-322">Microsoft Managed Desktop users will not have local administrator privileges on their Microsoft Managed Desktop devices after enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="06b2a-323">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="06b2a-323">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="06b2a-324">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="06b2a-324">OneDrive for Business</span></span>

<span data-ttu-id="06b2a-325">Die Einstellung **Synchronisierung nur auf PCs zulassen, die mit bestimmten Domänen verbunden sind,** wird mit dem Microsoft Managed Desktop in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="06b2a-325">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="06b2a-326">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="06b2a-326">**Advisory**</span></span>

<span data-ttu-id="06b2a-327">Sie verwenden die Einstellung **Synchronisierung nur für PCs zulassen, die mit bestimmten Domänen verbunden** sind.</span><span class="sxs-lookup"><span data-stu-id="06b2a-327">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="06b2a-328">Diese Einstellung funktioniert nicht mit Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="06b2a-328">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="06b2a-329">Deaktivieren Sie diese Einstellung, und richten Sie OneDrive für Unternehmen für die Verwendung einer Richtlinie für bedingten Zugriff ein.</span><span class="sxs-lookup"><span data-stu-id="06b2a-329">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="06b2a-330">Weitere Informationen finden Sie unter [Planen einer Bereitstellung für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) .</span><span class="sxs-lookup"><span data-stu-id="06b2a-330">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

