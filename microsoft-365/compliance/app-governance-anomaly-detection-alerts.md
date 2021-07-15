---
title: Untersuchen von Benachrichtigungen zur Anomalieerkennung
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Untersuchen Sie Benachrichtigungen zur Anomalieerkennung.
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420244"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="f578a-103">Untersuchen von Benachrichtigungen zur Anomalieerkennung</span><span class="sxs-lookup"><span data-stu-id="f578a-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="f578a-104">Die Microsoft App-Governance bietet Sicherheitserkennungen und Benachrichtigungen für bösartige Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="f578a-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="f578a-105">Der Zweck dieses Leitfadens ist es, Ihnen allgemeine und praktische Informationen zu jeder Benachrichtigung zu geben, um Sie bei Ihren Untersuchungs- und Behebungsaufgaben zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f578a-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="f578a-106">In diesem Leitfaden eingeschlossen sind allgemeine Informationen über die Bedingungen für das Auslösen von Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="f578a-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="f578a-107">Weil Anomalie-Erkennungen von Natur aus nicht-deterministisch sind, werden sie nur ausgelöst, wenn es ein von der Norm abweichendes Verhalten gibt.</span><span class="sxs-lookup"><span data-stu-id="f578a-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="f578a-108">Schließlich können einige Benachrichtigungen in der Vorschau sein, daher sollten Sie regelmäßig die offizielle Dokumentation auf den aktuellen Status der Benachrichtigungen überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f578a-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="f578a-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="f578a-109">MITRE ATT&CK</span></span>

<span data-ttu-id="f578a-110">Um die Beziehung zwischen den Microsoft App-Governance-Benachrichtigungen und der bekannten MITRE ATT&CK-Matrix einfacher abbilden zu können, haben wir die Benachrichtigungen nach der entsprechenden MITRE ATT&CK-Taktik kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="f578a-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="f578a-111">Diese zusätzliche Referenz erleichtert das Verständnis der mutmaßlichen Angriffstechnik, die möglicherweise verwendet wird, wenn die Microsoft-Anwendungssicherheits- und Governance-Benachrichtigung ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f578a-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="f578a-112">Dieser Leitfaden enthält Informationen zur Untersuchung und Behebung von Microsoft App-Governance-Benachrichtigungen in den folgenden Kategorien.</span><span class="sxs-lookup"><span data-stu-id="f578a-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="f578a-113">Erstzugriff</span><span class="sxs-lookup"><span data-stu-id="f578a-113">Initial Access</span></span>
- <span data-ttu-id="f578a-114">Ausführung</span><span class="sxs-lookup"><span data-stu-id="f578a-114">Execution</span></span>
- <span data-ttu-id="f578a-115">Persistenz</span><span class="sxs-lookup"><span data-stu-id="f578a-115">Persistence</span></span>
- <span data-ttu-id="f578a-116">Rechteausweitung</span><span class="sxs-lookup"><span data-stu-id="f578a-116">Privilege Escalation</span></span>
- <span data-ttu-id="f578a-117">Verteidigungsumgehung</span><span class="sxs-lookup"><span data-stu-id="f578a-117">Defense Evasion</span></span>
- <span data-ttu-id="f578a-118">Zugriff auf Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f578a-118">Credential Access</span></span>
- <span data-ttu-id="f578a-119">Sammlung</span><span class="sxs-lookup"><span data-stu-id="f578a-119">Collection</span></span>
- <span data-ttu-id="f578a-120">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="f578a-120">Exfiltration</span></span>
- <span data-ttu-id="f578a-121">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="f578a-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="f578a-122">Klassifizierungen der Sicherheitsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="f578a-122">Security alert classifications</span></span>

<span data-ttu-id="f578a-123">Nach einer ordnungsgemäßen Untersuchung können alle Microsoft App-Governance-Benachrichtigungen einem der folgenden Aktivitätstypen zugeordnet werden:</span><span class="sxs-lookup"><span data-stu-id="f578a-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="f578a-124">Wahr-Positiv (True positive, TP): Eine Benachrichtigung über eine bestätigte bösartige Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f578a-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="f578a-125">Gutartig Wahr-Positiv (Benign true positive, B-TP): Eine Benachrichtigung über eine verdächtige, aber nicht bösartige Aktivität, wie z. B. ein Penetrationstest oder eine andere, autorisierte verdächtige Aktion.</span><span class="sxs-lookup"><span data-stu-id="f578a-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="f578a-126">Falsch-Positiv (False positive, FP): Eine Benachrichtigung über eine nicht-bösartige Aktivität.</span><span class="sxs-lookup"><span data-stu-id="f578a-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="f578a-127">Allgemeine Untersuchungsschritte</span><span class="sxs-lookup"><span data-stu-id="f578a-127">General investigation steps</span></span>

<span data-ttu-id="f578a-128">Verwenden Sie die folgende allgemeine Richtlinie, wenn Sie eine beliebige Art von Benachrichtigung untersuchen, um ein besseres Verständnis der potenziellen Bedrohung zu erhalten, bevor Sie die empfohlene Maßnahme anwenden.</span><span class="sxs-lookup"><span data-stu-id="f578a-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="f578a-129">Überprüfen Sie den Schweregrad der App und vergleichen Sie ihn mit dem Rest der Apps in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="f578a-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="f578a-130">Diese Überprüfung wird Ihnen beim Identifizieren der Apps in Ihrem Mandanten helfen, die ein größeres Risiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="f578a-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="f578a-131">Wenn Sie ein TP-Ereignis identifizieren, überprüfen Sie alle App-Aktivitäten, um ein Verständnis über die Auswirkung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f578a-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="f578a-132">Überprüfen Sie beispielsweise die folgenden App-Informationen:</span><span class="sxs-lookup"><span data-stu-id="f578a-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="f578a-133">Bereiche mit gewährtem Zugriff</span><span class="sxs-lookup"><span data-stu-id="f578a-133">Scopes granted access</span></span>
  - <span data-ttu-id="f578a-134">Ungewohntes Verhalten</span><span class="sxs-lookup"><span data-stu-id="f578a-134">Unusual behavior</span></span>  
  - <span data-ttu-id="f578a-135">IP-Adresse und Standort</span><span class="sxs-lookup"><span data-stu-id="f578a-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="f578a-136">Benachrichtigungen beim Erstzugriff</span><span class="sxs-lookup"><span data-stu-id="f578a-136">Initial access alerts</span></span>

<span data-ttu-id="f578a-137">In diesem Abschnitt werden Benachrichtigungen beschrieben, die darauf hinweisen, dass eine bösartige App möglicherweise versucht, in Ihrer Organisation Fuß zu fassen.</span><span class="sxs-lookup"><span data-stu-id="f578a-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="f578a-138">Codierter App-Name mit verdächtigen Zustimmungsbereichen</span><span class="sxs-lookup"><span data-stu-id="f578a-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="f578a-139">**Schweregrad:** Mittel</span><span class="sxs-lookup"><span data-stu-id="f578a-139">**Severity:** Medium</span></span>

<span data-ttu-id="f578a-140">**Beschreibung**: Diese Erkennung identifiziert OAuth-Apps mit Zeichen, beispielsweise Unicode oder codierten Zeichen, die für verdächtige Zustimmungsbereiche angefordert wurden, und die auf E-Mail-Ordner von Benutzern über die Graph-API zugegriffen haben.</span><span class="sxs-lookup"><span data-stu-id="f578a-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="f578a-141">Diese Benachrichtigung kann auf einen Versuch hinweisen, eine bösartige App als bekannte und vertrauenswürdige App zu tarnen, damit Angreifer die Benutzer dazu verleiten können, der bösartigen App zuzustimmen.</span><span class="sxs-lookup"><span data-stu-id="f578a-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="f578a-142">**TP oder FP?**</span><span class="sxs-lookup"><span data-stu-id="f578a-142">**TP or FP?**</span></span>

- <span data-ttu-id="f578a-143">**TP**: Wenn Sie bestätigen können, dass die OAuth-App den Anzeigenamen mit verdächtigen Bereichen codiert hat, die von einer unbekannten Quelle geliefert wurden, dann wird ein Wahr-Positiv angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f578a-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="f578a-144">**Empfohlene Aktion**: Überprüfen Sie die Berechtigungsebene, welche diese App angefordert hat, und welche Benutzer den Zugriff gewährten.</span><span class="sxs-lookup"><span data-stu-id="f578a-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="f578a-145">Sie können basierend auf Ihrer Untersuchung entscheiden, den Zugriff auf diese App zu verbieten.</span><span class="sxs-lookup"><span data-stu-id="f578a-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="f578a-146">Um den Zugriff auf die App zu verbieten, wählen Sie auf der Seite der OAuth-Apps in der Zeile, in der die zu verbietende App erscheint, das Verbotssymbol.</span><span class="sxs-lookup"><span data-stu-id="f578a-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="f578a-147">Sie können entscheiden, ob Sie die Benutzer informieren wollen, dass die von ihnen installierte und autorisierte App verboten wurde.</span><span class="sxs-lookup"><span data-stu-id="f578a-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="f578a-148">Die Benachrichtigung teilt den Benutzern mit, dass die App deaktiviert wird, und dass sie keinen Zugriff auf die verbundene App haben werden.</span><span class="sxs-lookup"><span data-stu-id="f578a-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="f578a-149">Wenn die Benutzer dies nicht erfahren sollen, deaktivieren Sie im Dialogfeld die Option „Benutzer benachrichtigen, die Zugriff auf diese gesperrte App erteilt haben“.</span><span class="sxs-lookup"><span data-stu-id="f578a-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="f578a-150">Es wird empfohlen, dass Sie den App-Benutzern mitteilen, dass die Verwendung ihrer App demnächst verboten wird.</span><span class="sxs-lookup"><span data-stu-id="f578a-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="f578a-151">**FP**: Wenn Sie bestätigen werden, dass die App einen codierten Namen hat, aber eine legitime geschäftliche Verwendung in der Organisation besitzt.</span><span class="sxs-lookup"><span data-stu-id="f578a-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="f578a-152">**Empfohlene Aktion**: Schließen Sie die Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="f578a-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f578a-153">Verständnis des Umfangs der Sicherheitsverletzung</span><span class="sxs-lookup"><span data-stu-id="f578a-153">Understand the scope of the breach</span></span>

<span data-ttu-id="f578a-154">Folgen Sie dem Lernprogramm zur [Untersuchung riskanter OAuth-Apps](/cloud-app-security/investigate-risky-oauth).</span><span class="sxs-lookup"><span data-stu-id="f578a-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="f578a-155">OAuth-Apps mit Lesebereichen haben eine verdächtige Antwort-URL</span><span class="sxs-lookup"><span data-stu-id="f578a-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="f578a-156">**Schweregrad**: Mittel</span><span class="sxs-lookup"><span data-stu-id="f578a-156">**Severity**: Medium</span></span>

<span data-ttu-id="f578a-157">**Beschreibung**: Diese Erkennung identifiziert eine OAuth-App mit nur Lesebereichen wie User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared, umgeleitet über die Graph-API an eine verdächtige Antwort-URL.</span><span class="sxs-lookup"><span data-stu-id="f578a-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="f578a-158">Diese Aktivität soll darauf hinweisen, dass eine bösartige App mit weniger privilegierten Berechtigungen (z. B. Lesebereiche) ausgenutzt werden könnte, um das Benutzerkonto auszuspähen.</span><span class="sxs-lookup"><span data-stu-id="f578a-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="f578a-159">**TP oder FP?**</span><span class="sxs-lookup"><span data-stu-id="f578a-159">**TP or FP?**</span></span>

- <span data-ttu-id="f578a-160">**TP**: Wenn Sie bestätigen können, dass die OAuth-App mit Lesebereich von einer unbekannten Quelle geliefert wird und auf eine verdächtige URL umleitet, dann wird ein TP angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f578a-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="f578a-161">**Empfohlene Aktion**: Überprüfen Sie die Antwort-URL und die Bereiche, die von der App angeforderte werden.</span><span class="sxs-lookup"><span data-stu-id="f578a-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="f578a-162">Sie können basierend auf Ihrer Untersuchung entscheiden, den Zugriff auf diese App zu verbieten.</span><span class="sxs-lookup"><span data-stu-id="f578a-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="f578a-163">Überprüfen Sie die Berechtigungsebene, welche diese App angefordert hat, und welche Benutzer den Zugriff gewährt haben.</span><span class="sxs-lookup"><span data-stu-id="f578a-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="f578a-164">Um den Zugriff auf die App zu verbieten, wählen Sie auf der Seite der OAuth-Apps in der Zeile, in der die zu verbietende App erscheint, das Verbotssymbol.</span><span class="sxs-lookup"><span data-stu-id="f578a-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="f578a-165">Sie können entscheiden, ob Sie die Benutzer informieren wollen, dass die von ihnen installierte und autorisierte App verboten wurde.</span><span class="sxs-lookup"><span data-stu-id="f578a-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="f578a-166">Die Benachrichtigung teilt den Benutzern mit, dass die App deaktiviert wird, und dass sie keinen Zugriff auf die verbundene App haben werden.</span><span class="sxs-lookup"><span data-stu-id="f578a-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="f578a-167">Wenn die Benutzer dies nicht erfahren sollen, deaktivieren Sie im Dialogfeld die Option „Benutzer benachrichtigen, die Zugriff auf diese gesperrte App erteilt haben“.</span><span class="sxs-lookup"><span data-stu-id="f578a-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="f578a-168">Es wird empfohlen, dass Sie den App-Benutzern mitteilen, dass die Verwendung ihrer App demnächst verboten wird.</span><span class="sxs-lookup"><span data-stu-id="f578a-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="f578a-169">**B-TP**: Wenn Sie nach der Untersuchung bestätigen können, dass die App eine legitime geschäftliche Verwendung in der Organisation besitzt.</span><span class="sxs-lookup"><span data-stu-id="f578a-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="f578a-170">**Empfohlene Aktion**: Schließen Sie die Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="f578a-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f578a-171">Verständnis des Umfangs der Sicherheitsverletzung</span><span class="sxs-lookup"><span data-stu-id="f578a-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="f578a-172">Überprüfen Sie alle von dieser App ausgeführten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="f578a-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="f578a-173">Wenn Sie vermuten, dass eine App verdächtig ist, empfehlen wir Ihnen, den Namen und die Antwort-URL der App in verschiedenen App-Stores zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f578a-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="f578a-174">Wenn Sie App-Stores überprüfen, konzentrieren Sie sich auf die folgenden Typen von Apps:</span><span class="sxs-lookup"><span data-stu-id="f578a-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="f578a-175">Apps, die kürzlich erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f578a-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="f578a-176">Apps mit einer verdächtigen Antwort-URL</span><span class="sxs-lookup"><span data-stu-id="f578a-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="f578a-177">Apps, die in der letzten Zeit nicht aktualisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="f578a-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="f578a-178">Fehlende Aktualisierungen können darauf hinweisen, dass die App nicht mehr unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="f578a-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="f578a-179">Wenn Sie immer noch vermuten, dass eine App verdächtig ist, können Sie den Namen der App, den Namen des Herausgebers und die Antwort-URL online recherchieren.</span><span class="sxs-lookup"><span data-stu-id="f578a-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="f578a-180">Persistenz-Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="f578a-180">Persistence alerts</span></span>

<span data-ttu-id="f578a-181">In diesem Abschnitt werden Benachrichtigungen beschrieben, die darauf hinweisen, dass ein bösartiger Akteur möglicherweise versucht, in Ihrer Organisation Fuß zu fassen.</span><span class="sxs-lookup"><span data-stu-id="f578a-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="f578a-182">App mit verdächtigem OAuth-Bereich erstellt eine Posteingangsregel</span><span class="sxs-lookup"><span data-stu-id="f578a-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="f578a-183">**Schweregrad**: Mittel</span><span class="sxs-lookup"><span data-stu-id="f578a-183">**Severity**: Medium</span></span>

<span data-ttu-id="f578a-184">**MITRE-IDs**: T1137.005, T1114</span><span class="sxs-lookup"><span data-stu-id="f578a-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="f578a-185">Diese Erkennung identifiziert eine OAuth-App, die verdächtigen Bereichen zugestimmt hat, eine verdächtige Posteingangsregel erstellt und dann über die Graph-API auf die E-Mail-Ordner und -Nachrichten von Benutzern zugegriffen hat.</span><span class="sxs-lookup"><span data-stu-id="f578a-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="f578a-186">Posteingangsregeln, wie z. B. das Weiterleiten aller oder bestimmter E-Mails an ein anderes E-Mail-Konto, und Graph-Aufrufe für den Zugriff auf E-Mails und das Senden an ein anderes E-Mail-Konto, können ein Versuch sein, Informationen aus Ihrer Organisation zu exfiltrieren.</span><span class="sxs-lookup"><span data-stu-id="f578a-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="f578a-187">**TP oder FP?**</span><span class="sxs-lookup"><span data-stu-id="f578a-187">**TP or FP?**</span></span>

- <span data-ttu-id="f578a-188">**TP**: Wenn Sie bestätigen können, dass die Posteingangsregel von einer OAuth-App einer Drittpartei erstellt wurde, mit verdächtigen Bereichen, die von einer unbekannten Quelle geliefert wurden, dann wird ein Wahr-Positiv angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f578a-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="f578a-189">**Empfohlene Aktion**: Deaktivieren und entfernen Sie die App, setzen Sie das Kennwort zurück, und entfernen Sie die Posteingangsregel.</span><span class="sxs-lookup"><span data-stu-id="f578a-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="f578a-190">Folgen Sie dem Lernprogramm zum „Zurücksetzen eines Passworts mit Azure Active Directory“ und folgen Sie dem Lernprogramm zum „Entfernen der Posteingangsregel“.</span><span class="sxs-lookup"><span data-stu-id="f578a-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="f578a-191">**FP**: Wenn Sie bestätigen können, dass die App aus legitimen Gründen eine Posteingangsregel für ein neues oder persönliches externes E-Mail-Konto erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="f578a-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="f578a-192">**Empfohlene Aktion**: Schließen Sie die Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="f578a-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f578a-193">Verständnis des Umfangs der Sicherheitsverletzung</span><span class="sxs-lookup"><span data-stu-id="f578a-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="f578a-194">Überprüfen Sie alle von dieser App ausgeführten Aktivitäten.</span><span class="sxs-lookup"><span data-stu-id="f578a-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="f578a-195">Überprüfen Sie die Bereiche, die von der App gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="f578a-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="f578a-196">Überprüfen Sie die Aktion und die Bedingung der Posteingangsregel, die von der App erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f578a-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="f578a-197">Sammlungsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="f578a-197">Collection alerts</span></span>

<span data-ttu-id="f578a-198">In diesem Abschnitt werden Benachrichtigungen beschrieben, die darauf hinweisen, dass ein bösartiger Akteur möglicherweise versucht, in Ihrer Organisation die für sein Ziel interessanten Daten zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="f578a-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="f578a-199">App hat anomale Graph-Aufrufe gemacht, um E-Mails zu lesen</span><span class="sxs-lookup"><span data-stu-id="f578a-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="f578a-200">**Schweregrad**: Mittel</span><span class="sxs-lookup"><span data-stu-id="f578a-200">**Severity**: Medium</span></span>

<span data-ttu-id="f578a-201">**MITRE-ID**: T1114</span><span class="sxs-lookup"><span data-stu-id="f578a-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="f578a-202">Diese Erkennung identifiziert, wenn die Branchen (Line of Business, LOB)-OAuth-App über die Graph-API auf ein ungewöhnliches und hohes Volumen von E-Mail-Ordnern und -Nachrichten des Benutzers zugreift, was auf eine versuchte Sicherheitsverletzung in Ihrer Organisation hinweisen kann.</span><span class="sxs-lookup"><span data-stu-id="f578a-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="f578a-203">**TP oder FP?**</span><span class="sxs-lookup"><span data-stu-id="f578a-203">**TP or FP?**</span></span>

- <span data-ttu-id="f578a-204">**TP**: Wenn Sie bestätigen können, dass die ungewöhnliche Graph-Aktivität von der Branchen (Line of Business, LOB)-OAuth-App durchgeführt wurde, dann wird ein Wahr-Positiv angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f578a-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="f578a-205">**Empfohlene Aktionen**: Deaktivieren Sie die App vorübergehend, setzen Sie das Kennwort zurück, und aktivieren Sie dann die App erneut.</span><span class="sxs-lookup"><span data-stu-id="f578a-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="f578a-206">Folgen Sie dem Lernprogramm zum „Zurücksetzen eines Kennworts mit dem Azure Active Directory“.</span><span class="sxs-lookup"><span data-stu-id="f578a-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="f578a-207">**FP**: Wenn Sie bestätigen können, dass die App für ein ungewöhnlich hohes Volumen an Graph-Aufrufen vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="f578a-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="f578a-208">**Empfohlene Aktion**: Schließen Sie die Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="f578a-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="f578a-209">Verständnis des Umfangs der Sicherheitsverletzung</span><span class="sxs-lookup"><span data-stu-id="f578a-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="f578a-210">Überprüfen Sie das Aktivitätsprotokoll auf Ereignisse, die von dieser App ausgeführt wurden, um ein besseres Verständnis für andere Aktivitäten von Graph zu erhalten, die E-Mails lesen und versuchen, vertrauliche E-Mail-Informationen der Benutzer zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="f578a-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="f578a-211">Überwachen Sie, ob der App unerwartete Anmeldeinformationen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="f578a-211">Monitor for unexpected credential being added to the app.</span></span>
