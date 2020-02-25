---
title: Was kommt in Microsoft Secure Score vor?
description: Beschreibt Microsoft Secure Score im Microsoft 365 Security Center, wie Details berechnet werden und welche Sicherheitsadministratoren erwarten können.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, Verbesserungs Aktionen
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 55c7cb34c5484eaf8f6693be0ce439e33a82550f
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266973"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="8a456-104">Was kommt in Microsoft Secure Score vor?</span><span class="sxs-lookup"><span data-stu-id="8a456-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="8a456-105">Um Microsoft Secure Score zu einem besseren Vertreter ihrer Sicherheitsposition zu machen und die Benutzerfreundlichkeit zu verbessern, werden wir in naher Zukunft einige Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="8a456-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="8a456-106">Ihre Punktzahl und die maximal mögliche Punktzahl ändern sich.</span><span class="sxs-lookup"><span data-stu-id="8a456-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="8a456-107">Dies impliziert jedoch keine Änderung ihrer Sicherheitsposition.</span><span class="sxs-lookup"><span data-stu-id="8a456-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="8a456-108">Informationen zu den neuesten Änderungen finden Sie unter [What es New in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="8a456-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="8a456-109">2. März 2020</span><span class="sxs-lookup"><span data-stu-id="8a456-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="8a456-110">Entfernen von Verbesserungs Aktionen aus InTune</span><span class="sxs-lookup"><span data-stu-id="8a456-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="8a456-111">Nach einer Auswertung der von InTune bereitgestellten Microsoft Secure Score Improvement-Aktionen wurde entschieden, dass Sie keine nützliche Darstellung der Sicherheitslage von Geräten in Organisationen darstellen.</span><span class="sxs-lookup"><span data-stu-id="8a456-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="8a456-112">Anstatt sich auf Richtlinien zu konzentrieren, arbeiten wir daran, Sicherheitskontrollen einzuführen, die den Konfigurationsstatus der Geräte direkt bewerten.</span><span class="sxs-lookup"><span data-stu-id="8a456-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="8a456-113">Die folgenden InTune-Verbesserungs Aktionen werden entfernt:</span><span class="sxs-lookup"><span data-stu-id="8a456-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="8a456-114">Aktivieren der Verwaltung von mobilen Geräten in Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="8a456-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="8a456-115">Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Android</span><span class="sxs-lookup"><span data-stu-id="8a456-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="8a456-116">Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Android for Work</span><span class="sxs-lookup"><span data-stu-id="8a456-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="8a456-117">Erstellen einer Microsoft InTune-App-Schutzrichtlinie für Android</span><span class="sxs-lookup"><span data-stu-id="8a456-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="8a456-118">Erstellen einer Microsoft InTune-App-Schutzrichtlinie für IOS</span><span class="sxs-lookup"><span data-stu-id="8a456-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="8a456-119">Geräte markieren, für die keine Microsoft InTune-Konformitätsrichtlinie als nicht kompatibel zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="8a456-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="8a456-120">Erstellen einer Microsoft InTune-Konformitätsrichtlinie für IOS</span><span class="sxs-lookup"><span data-stu-id="8a456-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="8a456-121">Erstellen einer Microsoft InTune-Konformitätsrichtlinie für macOS</span><span class="sxs-lookup"><span data-stu-id="8a456-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="8a456-122">Erstellen einer Microsoft InTune-Konformitätsrichtlinie für Windows</span><span class="sxs-lookup"><span data-stu-id="8a456-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="8a456-123">Erstellen eines Microsoft InTune-Konfigurationsprofils für Android</span><span class="sxs-lookup"><span data-stu-id="8a456-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="8a456-124">Erstellen eines Microsoft InTune-Konfigurationsprofils für Android for Work</span><span class="sxs-lookup"><span data-stu-id="8a456-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="8a456-125">Erstellen eines Microsoft InTune-Konfigurationsprofils für macOS</span><span class="sxs-lookup"><span data-stu-id="8a456-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="8a456-126">Erstellen eines Microsoft InTune-Konfigurationsprofils für IOS</span><span class="sxs-lookup"><span data-stu-id="8a456-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="8a456-127">Erstellen eines Microsoft InTune-Konfigurationsprofils für Windows</span><span class="sxs-lookup"><span data-stu-id="8a456-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="8a456-128">Aktivieren der verbesserten Jailbreak-Erkennung in Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="8a456-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="8a456-129">Erfordern, dass alle Geräte gepatcht werden, Virenschutz und Firewalls aktiviert sind</span><span class="sxs-lookup"><span data-stu-id="8a456-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="8a456-130">Aktivieren der Integration von Windows Defender ATP in Microsoft InTune</span><span class="sxs-lookup"><span data-stu-id="8a456-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="8a456-131">Erstellen einer Microsoft InTune-Windows-Informationsschutz Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8a456-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="8a456-132">Erfordern von erweiterten Sicherheitskonfigurationen für alle Geräte</span><span class="sxs-lookup"><span data-stu-id="8a456-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="8a456-133">Bericht überprüfen blockierter Geräte wöchentlich</span><span class="sxs-lookup"><span data-stu-id="8a456-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="8a456-134">Entfernen von Verbesserungs Aktionen, die die Erwartungen für eine zuverlässige Messung nicht erfüllen</span><span class="sxs-lookup"><span data-stu-id="8a456-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="8a456-135">Um sicherzustellen, dass die Microsoft Secure Score sinnvoll ist und dass jede Verbesserungs Aktion messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="8a456-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="8a456-136">Aktivieren der Aufzeichnung von Überwachungsdaten</span><span class="sxs-lookup"><span data-stu-id="8a456-136">Turn on audit data recording</span></span>
- <span data-ttu-id="8a456-137">Ermitteln riskanter und nicht kompatibler Shadow-IT-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="8a456-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="8a456-138">Überprüfen von Berechtigungen & blockieren riskanter OAuth-Anwendungen, die mit Ihrer Umgebung verbunden sind</span><span class="sxs-lookup"><span data-stu-id="8a456-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="8a456-139">Einrichten der Versionsverwaltung in SharePoint Online-Dokumentbibliotheken</span><span class="sxs-lookup"><span data-stu-id="8a456-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="8a456-140">Aktualisierung der MFA-Verbesserungs Aktionen</span><span class="sxs-lookup"><span data-stu-id="8a456-140">MFA improvement action updates</span></span>

<span data-ttu-id="8a456-141">Um den Anforderungen an Unternehmen Rechnung zu tragen, beim Anwenden von Richtlinien, die mit Ihrem Unternehmen zusammenarbeiten, die höchste Sicherheit zu gewährleisten, entfernt Microsoft Secure Score drei Verbesserungs Aktionen, die sich auf die mehrstufige Authentifizierung konzentrieren, und fügt zwei hinzu.</span><span class="sxs-lookup"><span data-stu-id="8a456-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="8a456-142">Die drei, die entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="8a456-142">The three that will be removed:</span></span>

- <span data-ttu-id="8a456-143">Registrieren aller Benutzer für mehrstufige Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8a456-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="8a456-144">MFA für alle Benutzer erforderlich</span><span class="sxs-lookup"><span data-stu-id="8a456-144">Require MFA for all users</span></span>
- <span data-ttu-id="8a456-145">MFA für Azure AD privilegierten Rollen erforderlich</span><span class="sxs-lookup"><span data-stu-id="8a456-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="8a456-146">Neue Verbesserungs Aktionen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="8a456-146">New improvement actions added:</span></span>

- <span data-ttu-id="8a456-147">Sicherstellen, dass alle Benutzer mehrstufige Authentifizierung für sicheren Zugriff ausführen können</span><span class="sxs-lookup"><span data-stu-id="8a456-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="8a456-148">MFA für Administratorrollen erforderlich</span><span class="sxs-lookup"><span data-stu-id="8a456-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="8a456-149">Für diese neuen Verbesserungs Aktionen müssen Sie die Benutzer oder Administratoren für die mehrstufige Authentifizierung (MFA) in Ihrem Verzeichnis registrieren und die richtigen Richtlinien festlegen, die Ihren organisatorischen Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="8a456-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="8a456-150">Das Hauptziel besteht in der Flexibilität bei gleichzeitiger Sicherstellung, dass alle Benutzer und Administratoren sich mit mehreren Faktoren oder mit risikobasierten Identitäts Überprüfungs Ansagen authentifizieren können.</span><span class="sxs-lookup"><span data-stu-id="8a456-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="8a456-151">Dies kann die Form haben, dass mehrere Richtlinien mit bereichsbezogenen Entscheidungen angewendet werden oder Sicherheitsstandards (am 16. März) festgelegt werden, mit denen Microsoft entscheiden kann, wann die Benutzer für MFA herausgefordert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8a456-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="8a456-152">Entfernen von Verbesserungs Aktionen für "überprüfen"</span><span class="sxs-lookup"><span data-stu-id="8a456-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="8a456-153">Eines der Prinzipien von Secure Score ist, dass die Bewertung standardisiert und leicht zu beziehen ist.</span><span class="sxs-lookup"><span data-stu-id="8a456-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="8a456-154">Durch Verbesserungs Aktionen, die nicht messbar oder handlungsbereit sind, wurde eine Verwechslung verursacht.</span><span class="sxs-lookup"><span data-stu-id="8a456-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="8a456-155">Ein sicheres Ergebnis von Microsoft ist nur dann sinnvoll, wenn jede Empfehlung einen klaren Effekt auf die Bewertung haben kann.</span><span class="sxs-lookup"><span data-stu-id="8a456-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="8a456-156">Überarbeitungs Verbesserungs Aktionen werden nicht auf den gleichen Standard wie andere Verbesserungs Aktionen gemessen.</span><span class="sxs-lookup"><span data-stu-id="8a456-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="8a456-157">Aus diesen Gründen werden alle Verbesserungs Aktionen, die eine Überarbeitungs Kadenz erforderten, vorübergehend entfernt.</span><span class="sxs-lookup"><span data-stu-id="8a456-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="8a456-158">Ihrerseits ist keine Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8a456-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="8a456-159">16. März 2020</span><span class="sxs-lookup"><span data-stu-id="8a456-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="8a456-160">Entfernen von Verbesserungs Aktionen, die die Erwartungen für eine zuverlässige Messung nicht erfüllen</span><span class="sxs-lookup"><span data-stu-id="8a456-160">Removing improvement actions that don't meet expectations for reliable measurement</span></span>

<span data-ttu-id="8a456-161">Um sicherzustellen, dass die Microsoft Secure Score sinnvoll ist und dass jede Verbesserungs Aktion messbar und zuverlässig ist, entfernen wir die folgenden Verbesserungs Aktionen.</span><span class="sxs-lookup"><span data-stu-id="8a456-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="8a456-162">Speichern von Benutzerdokumenten in OneDrive für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="8a456-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="8a456-163">Einrichten Office 365 Richtlinien für ATP-sichere Anlagen</span><span class="sxs-lookup"><span data-stu-id="8a456-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="8a456-164">Einrichten Office 365 sicherer Links zum Überprüfen von URLs</span><span class="sxs-lookup"><span data-stu-id="8a456-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="8a456-165">Post Fach Delegierung nicht zulassen</span><span class="sxs-lookup"><span data-stu-id="8a456-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="8a456-166">Zulassen von anonymen Gast Freigabelinks für Websites und Dokumente</span><span class="sxs-lookup"><span data-stu-id="8a456-166">Allow anonymous guest sharing links for sites and docs</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="8a456-167">Unterstützen von Sicherheitsstandards für Azure AD Verbesserungs Aktionen</span><span class="sxs-lookup"><span data-stu-id="8a456-167">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="8a456-168">Microsoft Secure Score wird Update Verbesserungs Aktionen zur Unterstützung von [Sicherheitsstandards in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), die es einfacher machen, Ihre Organisation mit vorkonfigurierten Sicherheitseinstellungen für häufige Angriffe zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8a456-168">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="8a456-169">Dies wirkt sich auf die folgenden Verbesserungs Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8a456-169">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="8a456-170">Sicherstellen, dass alle Benutzer mehrstufige Authentifizierung für sicheren Zugriff ausführen können</span><span class="sxs-lookup"><span data-stu-id="8a456-170">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="8a456-171">MFA für Administratorrollen erforderlich</span><span class="sxs-lookup"><span data-stu-id="8a456-171">Require MFA for administrative roles</span></span>
- <span data-ttu-id="8a456-172">Aktivieren der Richtlinie zum Blockieren der Legacy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8a456-172">Enable policy to block legacy authentication</span></span>
