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
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656139"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="2fa7d-104">Beheben von Problemen, die mit dem Readiness Assessment Tool gefunden wurden</span><span class="sxs-lookup"><span data-stu-id="2fa7d-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="2fa7d-105">Für jede Überprüfung meldet das Tool eines von drei möglichen Ergebnissen:</span><span class="sxs-lookup"><span data-stu-id="2fa7d-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="2fa7d-106">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="2fa7d-106">Result</span></span>  |<span data-ttu-id="2fa7d-107">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="2fa7d-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="2fa7d-108">Bereit</span><span class="sxs-lookup"><span data-stu-id="2fa7d-108">Ready</span></span>     | <span data-ttu-id="2fa7d-109">Vor Abschluss der Registrierung ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="2fa7d-110">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="2fa7d-110">Advisory</span></span>    | <span data-ttu-id="2fa7d-111">Befolgen Sie die Schritte im Tool oder in diesem Artikel, um die besten Erfahrungen bei der Registrierung und für Benutzer zu finden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="2fa7d-112">Sie *können* die Registrierung abschließen, aber Sie müssen diese Probleme beheben, bevor Sie das erste Gerät bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="2fa7d-113">Nicht bereit</span><span class="sxs-lookup"><span data-stu-id="2fa7d-113">Not ready</span></span> | <span data-ttu-id="2fa7d-114">*Die Registrierung schlägt fehl, wenn Sie diese Probleme nicht beheben.*</span><span class="sxs-lookup"><span data-stu-id="2fa7d-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="2fa7d-115">Befolgen Sie die Schritte im Tool oder in diesem Artikel, um Sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="2fa7d-116">Microsoft InTune-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="2fa7d-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="2fa7d-117">Autopilot-Bereitstellungsprofil</span><span class="sxs-lookup"><span data-stu-id="2fa7d-117">Autopilot deployment profile</span></span>

<span data-ttu-id="2fa7d-118">Es sollten keine Autopilot-Profile vorhanden sein, die auf zugewiesene oder dynamische Gruppen abzielen, die von Microsoft Managed Desktop verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="2fa7d-119">Microsoft Managed Desktop verwendet Autopilot, um neue Geräte vorzusehen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="2fa7d-120">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-120">**Not ready**</span></span>

<span data-ttu-id="2fa7d-121">Sie verfügen über ein Autopilot-Profil, das allen Geräten zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="2fa7d-122">Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="2fa7d-123">Nachdem Sie die Microsoft Managed Desktop-Registrierung eingerichtet haben, müssen Sie Ihre Autopilot-Richtlinie so konfigurieren, dass die **modernen Arbeitsplatz Geräte-alle** Azure Ad Gruppe ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="2fa7d-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="2fa7d-124">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-124">**Advisory**</span></span>

<span data-ttu-id="2fa7d-125">Stellen Sie sicher, dass Ihre Autopilot-Profile auf eine zugewiesene oder dynamische Azure Ad Gruppe Zielen, die keine von Microsoft verwalteten Desktop-Geräte enthält, die bei der Registrierung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="2fa7d-126">Schritte finden Sie unter [Registrieren von Windows-Geräten in InTune mithilfe von Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="2fa7d-127">Nachdem Sie die Microsoft Managed Desktop-Registrierung eingerichtet haben, müssen Sie Ihre Autopilot-Richtlinie so konfigurieren, dass die **modernen Arbeitsplatz Geräte-alle** Azure Ad Gruppe ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="2fa7d-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="2fa7d-128">Zertifikat-Konnektoren</span><span class="sxs-lookup"><span data-stu-id="2fa7d-128">Certificate connectors</span></span>

<span data-ttu-id="2fa7d-129">Wenn Sie über die von den Geräten, die Sie in Microsoft Managed Desktop registrieren möchten, verwendeten Zertifikat-Konnektoren haben, können die Connectors keine Fehler aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="2fa7d-130">Nur einer der folgenden Hinweise wird auf Ihre Situation zutreffen, daher sollten Sie Sie sorgfältig überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="2fa7d-131">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-131">**Advisory**</span></span>

<span data-ttu-id="2fa7d-132">Es sind keine Zertifikat-Konnektoren vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-132">No certificate connectors are present.</span></span> <span data-ttu-id="2fa7d-133">Es ist möglich, dass Sie keine Konnektoren benötigen, aber Sie sollten überprüfen, ob Sie möglicherweise einige für die Netzwerkkonnektivität mit Microsoft Managed Desktop-Geräten benötigen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-134">Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="2fa7d-135">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-135">**Advisory**</span></span>

<span data-ttu-id="2fa7d-136">Mindestens ein Zertifikat-Konnektor hat einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="2fa7d-137">Wenn Sie diesen Connector für die Verbindung mit Microsoft Managed Desktop-Geräten benötigen, müssen Sie den Fehler beheben.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="2fa7d-138">Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="2fa7d-139">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-139">**Advisory**</span></span>

<span data-ttu-id="2fa7d-140">Sie verfügen über mindestens einen Zertifikat-Konnektor, und es werden keine Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="2fa7d-141">Möglicherweise müssen Sie jedoch ein Profil erstellen, um den Connector für Microsoft Managed Desktop-Geräte wiederzuverwenden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-142">Weitere Informationen finden Sie unter [Prepare Certificates and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="2fa7d-143">Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="2fa7d-143">Conditional access policies</span></span>

<span data-ttu-id="2fa7d-144">Richtlinien für bedingten Zugriff in ihrer Azure AD Organisation dürfen keine Microsoft Manage Desktop-Benutzer abzielen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="2fa7d-145">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-145">**Not ready**</span></span>

<span data-ttu-id="2fa7d-146">Sie haben mindestens eine Richtlinie für den bedingten Zugriff, die auf alle Benutzer abzielt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="2fa7d-147">Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe zurück, die nicht die Azure Ad Gruppe von Microsoft Managed Desktop-Dienstkonten enthält, die bei der Registrierung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="2fa7d-148">Schritte finden Sie unter [bedingter Zugriff: Benutzer und Gruppen](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="2fa7d-149">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-149">**Advisory**</span></span>

<span data-ttu-id="2fa7d-150">Stellen Sie sicher, dass alle Richtlinien für den bedingten Zugriff die Azure Ad Gruppe für **moderne Arbeitsplatz Dienstkonten** ausschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="2fa7d-151">Schritte finden Sie unter [Anpassen des bedingten Zugriffs](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="2fa7d-152">Die **Dienstkonten für moderne Arbeitsplatz Dienste** Azure Ad Gruppe ist eine dynamische Gruppe, die wir bei der Registrierung für den Dienst erstellen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="2fa7d-153">Sie müssen zurückkehren, um diese Gruppe nach der Registrierung auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="2fa7d-154">Weitere Informationen zu diesen Dienstkonten finden Sie unter [Standard Operating Procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="2fa7d-155">Geräte Konformitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2fa7d-155">Device Compliance policies</span></span>

<span data-ttu-id="2fa7d-156">InTune-Geräte Konformitätsrichtlinien in ihrer Azure AD Organisation dürfen keine Microsoft Managed Desktop-Benutzer adressieren.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="2fa7d-157">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-157">**Not ready**</span></span>

<span data-ttu-id="2fa7d-158">Sie haben mindestens eine Konformitätsrichtlinie, die auf alle Benutzer abzielt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="2fa7d-159">Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe, die keine Benutzer von Microsoft Managed Desktop enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="2fa7d-160">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="2fa7d-161">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-161">**Advisory**</span></span>

<span data-ttu-id="2fa7d-162">Stellen Sie sicher, dass alle Konformitätsrichtlinien, die Sie verwenden, keine von Microsoft verwalteten Desktop Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="2fa7d-163">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="2fa7d-164">Geräte Konfigurationsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="2fa7d-164">Device Configuration policies</span></span>

<span data-ttu-id="2fa7d-165">InTune-Geräte Konfigurationsrichtlinien in ihrer Azure AD Organisation dürfen keine Microsoft Manage-Desktop Geräte oder-Benutzer als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="2fa7d-166">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-166">**Not ready**</span></span>

<span data-ttu-id="2fa7d-167">Sie verfügen über mindestens eine Konfigurationsrichtlinie, die auf alle Benutzer, alle Geräte oder beides abzielt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="2fa7d-168">Setzen Sie die Richtlinie auf eine bestimmte Azure Ad Gruppe, die keine verwalteten Desktop Geräte von Microsoft enthält, zurück.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-169">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="2fa7d-170">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-170">**Advisory**</span></span>

<span data-ttu-id="2fa7d-171">Stellen Sie sicher, dass alle Konformitätsrichtlinien, die Sie verwenden, keine von Microsoft verwalteten Desktop Geräte oder Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="2fa7d-172">Eine schrittweise Anleitung finden Sie unter [Create a Compliance Policy in Microsoft InTune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="2fa7d-173">Einschränkungen für Gerätetypen</span><span class="sxs-lookup"><span data-stu-id="2fa7d-173">Device type restrictions</span></span>

<span data-ttu-id="2fa7d-174">Microsoft Managed Desktop-Geräte müssen sich in InTune registrieren können.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="2fa7d-175">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-175">**Not ready**</span></span>

<span data-ttu-id="2fa7d-176">Befolgen Sie die Schritte unter [Festlegen von Registrierungs Einschränkungen](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) , um die Einstellung in **zulassen**zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="2fa7d-177">Seite "Registrierungs Status"</span><span class="sxs-lookup"><span data-stu-id="2fa7d-177">Enrollment Status Page</span></span>

<span data-ttu-id="2fa7d-178">Derzeit ist die Registrierungs Status Seite (ESP) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="2fa7d-179">Wenn Sie an der öffentlichen Vorschau dieses Features teilnehmen, können Sie dieses Element ignorieren.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="2fa7d-180">Weitere Informationen finden Sie unter [First-Run-Erfahrung mit Autopilot und der Registrierungs Status Seite](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="2fa7d-181">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-181">**Not ready**</span></span>

<span data-ttu-id="2fa7d-182">Sie haben das ESP-Standardprofil festgelegt, um den **Fortschritt der APP-und Profilkonfiguration anzuzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="2fa7d-183">Deaktivieren Sie diese Einstellung, indem Sie die Schritte unter [Einrichten der Registrierungs Status Seite](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status)ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="2fa7d-184">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-184">**Advisory**</span></span>

<span data-ttu-id="2fa7d-185">Stellen Sie sicher, dass alle Profile mit der Einstellung " **App-und Profil Konfigurationsstatus anzeigen** " keiner Azure Ad Gruppe zugeordnet sind, die Microsoft Managed Desktop-Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-186">Weitere Informationen finden Sie unter [Einrichten der Registrierungs Status Seite](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="2fa7d-187">InTune-Registrierung</span><span class="sxs-lookup"><span data-stu-id="2fa7d-187">Intune enrollment</span></span>

<span data-ttu-id="2fa7d-188">Windows 10-Geräte in ihrer Azure AD Organisation müssen automatisch in InTune registriert sein.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="2fa7d-189">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-189">**Not ready**</span></span>

<span data-ttu-id="2fa7d-190">Benutzer in ihrer Azure AD Organisation werden nicht automatisch in Microsoft InTune registriert.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="2fa7d-191">Ändern Sie den MDM-Benutzerbereich in **einen** oder **alle**.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="2fa7d-192">Wenn Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-192">If you choose.</span></span> <span data-ttu-id="2fa7d-193">Einige \* \*, kehren Sie nach der Registrierung zurück, und wählen Sie die Gruppe **moderner Arbeitsplatz-alle** Azure AD für **Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="2fa7d-194">Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="2fa7d-194">Microsoft Store for Business</span></span>

<span data-ttu-id="2fa7d-195">Microsoft Store for Business wird verwendet, damit Sie das Unternehmens Portal herunterladen können, um einige apps wie Microsoft Project und Microsoft Visio bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="2fa7d-196">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-196">**Not ready**</span></span>

<span data-ttu-id="2fa7d-197">Microsoft Store for Business ist entweder nicht aktiviert oder nicht mit InTune synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="2fa7d-198">Weitere Informationen finden Sie unter [Verwalten von Volumen erworbenen Apps aus dem Microsoft Store for Business mit Microsoft InTune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) und [Installieren des InTune-Unternehmensportals auf auf Geräten](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="2fa7d-199">Mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="2fa7d-199">Multi-factor authentication</span></span>

<span data-ttu-id="2fa7d-200">Die mehrstufige Authentifizierung darf nicht versehentlich auf von Microsoft verwaltete Desktop Dienstkonten angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="2fa7d-201">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-201">**Not ready**</span></span>

<span data-ttu-id="2fa7d-202">Sie haben einige Richtlinien für die mehrstufige Authentifizierung (MFA) als "erforderlich" für Richtlinien für bedingten Zugriff festgelegt, die allen Benutzern zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="2fa7d-203">Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-204">Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="2fa7d-205">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-205">**Advisory**</span></span>

<span data-ttu-id="2fa7d-206">Stellen Sie sicher, dass alle bedingten Zugriffsrichtlinien, die MFA erfordern, den **modernen Arbeitsplatz-alle** Azure Ad Gruppe ausschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="2fa7d-207">Weitere Informationen finden Sie unter [bedingter Zugriffsrichtlinien](#conditional-access-policies) und [bedingter Zugriff: MFA für alle Benutzer erforderlich](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="2fa7d-208">Die Gruppe " **moderner Arbeitsplatz-alle** Azure AD" ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="2fa7d-209">PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="2fa7d-209">PowerShell scripts</span></span>

<span data-ttu-id="2fa7d-210">Windows PowerShell Skripts können nicht auf eine Weise zugewiesen werden, die auf Microsoft Managed Desktop-Geräte abzielt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="2fa7d-211">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-211">**Advisory**</span></span>

<span data-ttu-id="2fa7d-212">Stellen Sie sicher, dass Windows PowerShell Skripts in ihrer Azure AD Organisation nicht auf Microsoft Manage-Desktop Geräte oder-Benutzer abzielen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="2fa7d-213">Weitere Informationen finden Sie unter [Verwenden von PowerShell-Skripts auf Windows 10-Geräten in InTune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="2fa7d-214">Region</span><span class="sxs-lookup"><span data-stu-id="2fa7d-214">Region</span></span>

<span data-ttu-id="2fa7d-215">Ihre Region muss von Microsoft Managed Desktop unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="2fa7d-216">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-216">**Not ready**</span></span>

<span data-ttu-id="2fa7d-217">Ihre Azure AD Organisations Region wird derzeit nicht von Microsoft Managed Desktop unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="2fa7d-218">Weitere Informationen finden Sie unter [unterstützte Regionen und Sprachen in Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="2fa7d-219">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-219">**Advisory**</span></span>

<span data-ttu-id="2fa7d-220">Mindestens ein Land, in dem sich Ihre Azure AD Organisation befindet, wird von Microsoft Managed Desktop nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="2fa7d-221">Weitere Informationen finden Sie unter [unterstützte Regionen und Sprachen in Microsoft Managed Desktop](../service-description/regions-languages.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="2fa7d-222">Sicherheitsbasislinien</span><span class="sxs-lookup"><span data-stu-id="2fa7d-222">Security baselines</span></span>

<span data-ttu-id="2fa7d-223">Sicherheitsbasislinien sollten nicht auf Microsoft Managed Desktop-Geräte abzielen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="2fa7d-224">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-224">**Not ready**</span></span>

<span data-ttu-id="2fa7d-225">Sie verfügen über ein Sicherheitsbasis Profil, das auf alle Benutzer, alle Geräte oder beides abzielt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="2fa7d-226">Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-227">Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="2fa7d-228">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-228">**Advisory**</span></span>

<span data-ttu-id="2fa7d-229">Stellen Sie sicher, dass alle Sicherheitsbasis Richtlinien, auf denen Sie Microsoft Managed Desktop-Geräte ausschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-230">Eine schrittweise Anleitung finden Sie unter [use Security Baselines to configure Windows 10 Devices in InTune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="2fa7d-231">Die **moderne Arbeitsplatz Geräte-alle** Azure Ad Gruppe ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="2fa7d-232">Windows-apps</span><span class="sxs-lookup"><span data-stu-id="2fa7d-232">Windows apps</span></span>

<span data-ttu-id="2fa7d-233">Überprüfen Sie die apps, die Ihre Microsoft Managed Desktop-Benutzer haben sollen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="2fa7d-234">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-234">**Advisory**</span></span>

<span data-ttu-id="2fa7d-235">Sie sollten eine Inventarisierung der apps vorbereiten, die ihre von Microsoft verwalteten Desktop-Benutzer haben sollen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="2fa7d-236">Stellen Sie sicher, dass diese apps von InTune bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="2fa7d-237">Weitere Informationen finden Sie unter [apps in Microsoft Managed Desktop](apps.md).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="2fa7d-238">Sie können Ihren Microsoft-Konto Vertreter für eine Abfrage im Microsoft Endpoint Configuration Manager bitten, um die apps zu identifizieren, die für die Migration zu InTune bereit sind oder Anpassungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="2fa7d-239">Windows Hello for Business</span><span class="sxs-lookup"><span data-stu-id="2fa7d-239">Windows Hello for Business</span></span>

<span data-ttu-id="2fa7d-240">Microsoft Managed Desktop erfordert die Aktivierung von Windows Hello for Business.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="2fa7d-241">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-241">**Not ready**</span></span>

<span data-ttu-id="2fa7d-242">Windows Hello for Business ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="2fa7d-243">Aktivieren Sie es, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy) ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="2fa7d-244">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-244">**Advisory**</span></span>

<span data-ttu-id="2fa7d-245">Windows Hello for Business ist nicht eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="2fa7d-246">Aktivieren Sie es, indem Sie die Schritte unter [Erstellen einer Windows Hello for Business-Richtlinie](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)ausführen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="2fa7d-247">Windows 10-Update klingelt</span><span class="sxs-lookup"><span data-stu-id="2fa7d-247">Windows 10 update rings</span></span>

<span data-ttu-id="2fa7d-248">Die Richtlinie "Windows 10 Update Ring" in InTune darf nicht auf Microsoft-verwaltete Desktop Geräte abzielen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="2fa7d-249">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-249">**Not ready**</span></span>

<span data-ttu-id="2fa7d-250">Sie haben eine Richtlinie "Update Ring", die auf alle Geräte, alle Benutzer oder beides abzielt.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="2fa7d-251">Ändern Sie die Richtlinie so, dass eine Zuweisung verwendet wird, die auf eine bestimmte Azure Ad Gruppe zielt, die keine von Microsoft verwalteten Desktop Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2fa7d-252">Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="2fa7d-253">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-253">**Advisory**</span></span>

<span data-ttu-id="2fa7d-254">Stellen Sie sicher, dass alle Update Ring-Richtlinien den **modernen Arbeitsplatz-alle** Azure Ad Gruppe ausschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="2fa7d-255">Eine schrittweise Anleitung finden Sie unter [Manage Windows 10 Softwareupdates in InTune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="2fa7d-256">Die **moderne Arbeitsplatz Geräte-alle** Azure Ad Gruppe ist eine dynamische Gruppe, die wir erstellen, wenn Sie sich für Microsoft Managed Desktop registrieren, damit Sie nach der Registrierung zurückkehren müssen, um diese Gruppe auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="2fa7d-257">Azure Active Directory-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="2fa7d-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="2fa7d-258">Ad-hoc-Abonnements</span><span class="sxs-lookup"><span data-stu-id="2fa7d-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="2fa7d-259">Gibt an, wie eine Einstellung überprüft wird, die (wenn Sie auf "false" festgelegt ist) möglicherweise verhindert, dass das Roaming von Unternehmensstatus ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="2fa7d-260">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-260">**Advisory**</span></span>

<span data-ttu-id="2fa7d-261">Stellen Sie sicher, dass **AllowAdHocSubscriptions** auf **true**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="2fa7d-262">Andernfalls funktioniert das Roaming im Enterprise-Status möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="2fa7d-263">Weitere Informationen finden Sie unter [Sets-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="2fa7d-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="2fa7d-264">Enterprise State Roaming</span></span>

<span data-ttu-id="2fa7d-265">Das Enterprise-Status-Roaming sollte aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="2fa7d-266">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-266">**Advisory**</span></span>

<span data-ttu-id="2fa7d-267">Stellen Sie sicher, dass das Enterprise-Status-Roaming für **alle** oder für **ausgewählte** Gruppen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="2fa7d-268">Weitere Informationen finden Sie unter [enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="2fa7d-269">Lizenzen</span><span class="sxs-lookup"><span data-stu-id="2fa7d-269">Licenses</span></span>

<span data-ttu-id="2fa7d-270">Für die Verwendung von Microsoft Managed Desktop sind eine Reihe von Lizenzen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="2fa7d-271">**Nicht einsatzfähig**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-271">**Not Ready**</span></span>

<span data-ttu-id="2fa7d-272">Sie verfügen nicht über alle Lizenzen, die Sie für die Verwendung von Microsoft Managed Desktop benötigen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="2fa7d-273">Weitere Informationen finden Sie unter [Microsoft Managed Desktop Technologies](../intro/technologies.md) und [mehr zu Lizenzen](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="2fa7d-274">Namen von Sicherheitskonten</span><span class="sxs-lookup"><span data-stu-id="2fa7d-274">Security account names</span></span>

<span data-ttu-id="2fa7d-275">Bestimmte Namen von Sicherheitskonten können Konflikte mit denen verursachen, die von Microsoft Managed Desktop erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="2fa7d-276">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-276">**Not ready**</span></span>

<span data-ttu-id="2fa7d-277">Sie haben mindestens einen Kontonamen, der mit den von Microsoft Managed Desktop erstellten Konflikten in Konflikt steht.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="2fa7d-278">Arbeiten Sie mit Ihrem Microsoft-Konto Vertreter zusammen, um diese Kontonamen auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="2fa7d-279">Sicherheitsadministrator Rollen</span><span class="sxs-lookup"><span data-stu-id="2fa7d-279">Security administrator roles</span></span>

<span data-ttu-id="2fa7d-280">Benutzer mit bestimmten Sicherheitsrollen müssen diese in Microsoft Defender für Endpoint zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="2fa7d-281">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-281">**Advisory**</span></span>

<span data-ttu-id="2fa7d-282">Wenn Sie eine dieser Rollen in ihrer Azure AD Organisation zugewiesen haben, stellen Sie sicher, dass diese Rollen auch in Microsoft Defender für Endpoint zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="2fa7d-283">Andernfalls können Administratoren mit diesen Rollen nicht auf das Verwaltungsportal zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="2fa7d-284">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="2fa7d-284">Security Reader</span></span>
- <span data-ttu-id="2fa7d-285">Sicherheitsoperator</span><span class="sxs-lookup"><span data-stu-id="2fa7d-285">Security Operator</span></span>
- <span data-ttu-id="2fa7d-286">Globaler Leser</span><span class="sxs-lookup"><span data-stu-id="2fa7d-286">Global Reader</span></span>

<span data-ttu-id="2fa7d-287">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen für die rollenbasierte Zugriffssteuerung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="2fa7d-288">Sicherheitsstandard</span><span class="sxs-lookup"><span data-stu-id="2fa7d-288">Security default</span></span>

<span data-ttu-id="2fa7d-289">Sicherheitsstandards in Azure Active Directory verhindern, dass von Microsoft Managed Desktop Ihre Geräte verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="2fa7d-290">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-290">**Not ready**</span></span>

<span data-ttu-id="2fa7d-291">Sie haben Sicherheitsstandards aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-291">You have Security defaults turned on.</span></span> <span data-ttu-id="2fa7d-292">Deaktivieren Sie Sicherheitseinstellungen, und richten Sie Richtlinien für bedingten Zugriff ein.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="2fa7d-293">Weitere Informationen finden Sie unter [Common Conditional Access Policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="2fa7d-294">Zurücksetzen von Self-Service-Kennwörtern</span><span class="sxs-lookup"><span data-stu-id="2fa7d-294">Self-service Password Reset</span></span>

<span data-ttu-id="2fa7d-295">Self-Service Password Reset (SSPR) muss aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="2fa7d-296">**Nicht bereit**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-296">**Not ready**</span></span>

<span data-ttu-id="2fa7d-297">SSPR muss für alle Benutzer aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="2fa7d-298">Wenn dies nicht der Fall ist, können die Microsoft Managed Desktop-Dienstkonten nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="2fa7d-299">Weitere Informationen finden Sie unter [Lernprogramm: Aktivieren von Benutzern zum Entsperren Ihres Kontos oder Zurücksetzen von Kennwörtern mithilfe von Azure Active Directory Self-Service Password Reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="2fa7d-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="2fa7d-300">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-300">**Advisory**</span></span>

<span data-ttu-id="2fa7d-301">Stellen Sie sicher, dass die SSPR **Selected** -Einstellung Microsoft Managed Desktop Devices enthält.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="2fa7d-302">Standard Benutzerrolle</span><span class="sxs-lookup"><span data-stu-id="2fa7d-302">Standard user role</span></span>

<span data-ttu-id="2fa7d-303">Microsoft Managed Desktop-Benutzer sollten Standardbenutzer ohne lokale Administratorrechte sein.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="2fa7d-304">Ihnen wird beim Starten Ihres von Microsoft verwalteten Desktop Geräts eine Standardbenutzerrolle zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="2fa7d-305">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-305">**Advisory**</span></span>

<span data-ttu-id="2fa7d-306">Microsoft Managed Desktop-Benutzer sollten vor dem registrieren keine lokalen Administratorrechte haben.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="2fa7d-307">Microsoft 365 Apps for Enterprise</span><span class="sxs-lookup"><span data-stu-id="2fa7d-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="2fa7d-308">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="2fa7d-308">OneDrive for Business</span></span>

<span data-ttu-id="2fa7d-309">Die Einstellung **Synchronisierung nur auf PCs zulassen, die mit bestimmten Domänen verbunden sind,** wird mit dem Microsoft Managed Desktop in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="2fa7d-310">**Empfehlung**</span><span class="sxs-lookup"><span data-stu-id="2fa7d-310">**Advisory**</span></span>

<span data-ttu-id="2fa7d-311">Sie verwenden die Einstellung **Synchronisierung nur für PCs zulassen, die mit bestimmten Domänen verbunden** sind.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="2fa7d-312">Diese Einstellung funktioniert nicht mit Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="2fa7d-313">Deaktivieren Sie diese Einstellung, und richten Sie OneDrive für Unternehmen für die Verwendung einer Richtlinie für bedingten Zugriff ein.</span><span class="sxs-lookup"><span data-stu-id="2fa7d-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="2fa7d-314">Weitere Informationen finden Sie unter [Planen einer Bereitstellung für bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) .</span><span class="sxs-lookup"><span data-stu-id="2fa7d-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

