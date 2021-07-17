---
title: Aktivieren der Evaluierungsumgebung für Microsoft Defender für Office 365 in Ihrer Produktionsumgebung, Aktivieren der Auswertung, Aktivierung
description: Schritte zum Aktivieren der Microsoft Defender für Office 365-Evaluierung mit Testlizenzen, MX-Datensatzbehandlung, & Überwachung akzeptierter Domänen und eingehenden Verbindungen.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: how-to
ms.technology: m365d
ms.openlocfilehash: c0736b93c314c3086f8a52477622c6bcfa4096a0
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458365"
---
# <a name="enable-the-evaluation-environment"></a><span data-ttu-id="00b2d-104">Aktivieren der Evaluierungsumgebung</span><span class="sxs-lookup"><span data-stu-id="00b2d-104">Enable the evaluation environment</span></span>

<span data-ttu-id="00b2d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="00b2d-105">**Applies to:**</span></span>
- <span data-ttu-id="00b2d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00b2d-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="00b2d-107">Dieser Artikel ist [Schritt 2 von 3](eval-defender-office-365-overview.md) beim Einrichten der Evaluierungsumgebung für Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="00b2d-107">This article is [Step 2 of 3](eval-defender-office-365-overview.md) in the process of setting up the evaluation environment for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="00b2d-108">Weitere Informationen zu diesem Prozess finden Sie im [Übersichtsartikel.](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="00b2d-108">For more information about this process, see the [overview article](eval-defender-office-365-overview.md).</span></span>

<span data-ttu-id="00b2d-109">Führen Sie die folgenden Schritte aus, um die Auswertung für Microsoft Defender für Office 365 zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="00b2d-109">Use the following steps to enable the evaluation for Microsoft Defender for Office 365.</span></span>


![Schritte zum Aktivieren von Microsoft Defender für Office 365 in der Microsoft Defender-Evaluierungsumgebung](../../media/defender/m365-defender-office-eval-enable-steps.png)

- [<span data-ttu-id="00b2d-111">Schritt 1: Aktivieren von Testlizenzen</span><span class="sxs-lookup"><span data-stu-id="00b2d-111">Step 1: Activate trial licenses</span></span>](#step-1-activate-trial-licenses)
- [<span data-ttu-id="00b2d-112">Schritt 2: Überwachen und Überprüfen des öffentlichen MX-Eintrags</span><span class="sxs-lookup"><span data-stu-id="00b2d-112">Step 2: Audit and verify the public MX record</span></span>](#step-2-audit-and-verify-the-public-mx-record)
- [<span data-ttu-id="00b2d-113">Schritt 3: Überwachen akzeptierter Domänen</span><span class="sxs-lookup"><span data-stu-id="00b2d-113">Step 3: Audit accepted domains</span></span>](#step-3-audit-accepted-domains)
- [<span data-ttu-id="00b2d-114">Schritt 4: Überwachen eingehender Connectors</span><span class="sxs-lookup"><span data-stu-id="00b2d-114">Step 4: Audit inbound connectors</span></span>](#step-4-audit-inbound-connectors)
- [<span data-ttu-id="00b2d-115">Schritt 5: Aktivieren der Auswertung</span><span class="sxs-lookup"><span data-stu-id="00b2d-115">Step 5: Activate the evaluation</span></span>](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a><span data-ttu-id="00b2d-116">Schritt 1: Aktivieren von Testlizenzen</span><span class="sxs-lookup"><span data-stu-id="00b2d-116">Step 1: Activate trial licenses</span></span>

<span data-ttu-id="00b2d-117">Melden Sie sich bei Ihrer vorhandenen Microsoft Defender for Office 365-Umgebung oder dem Mandantenverwaltungsportal an.</span><span class="sxs-lookup"><span data-stu-id="00b2d-117">Log on to your existing Microsoft Defender for Office 365 environment or tenant administration portal.</span></span>

1. <span data-ttu-id="00b2d-118">Navigieren Sie zum Verwaltungsportal.</span><span class="sxs-lookup"><span data-stu-id="00b2d-118">Navigate to the administration portal.</span></span>
2. <span data-ttu-id="00b2d-119">Wählen Sie in der Schnellstartleiste "Dienste kaufen" aus.</span><span class="sxs-lookup"><span data-stu-id="00b2d-119">Select Purchase Services from the quick launch.</span></span>

:::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Klicken Sie im Navigationsbereich von Office 365 auf &quot;Dienste kaufen&quot;.":::

3.  <span data-ttu-id="00b2d-121">Scrollen Sie nach unten zum Add-On Abschnitt (oder suchen Sie nach "Defender"), um den Microsoft Defender für Office 365 Pläne zu suchen.</span><span class="sxs-lookup"><span data-stu-id="00b2d-121">Scroll down to the Add-On section (or search for "Defender") to locate the Microsoft Defender for Office 365 plans.</span></span>
4.  <span data-ttu-id="00b2d-122">Klicken Sie auf "Details" neben dem Plan, den Sie auswerten möchten.</span><span class="sxs-lookup"><span data-stu-id="00b2d-122">Click Details next the plan you want to evaluate.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Klicken Sie als Nächstes auf die Schaltfläche &quot;Details&quot;.":::

5. <span data-ttu-id="00b2d-124">Klicken Sie auf den Link *"Kostenlose Testversion starten".*</span><span class="sxs-lookup"><span data-stu-id="00b2d-124">Click the *Start free trial* link.</span></span>

:::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Klicken Sie in diesem Bereich auf die kostenlose Testversion *Hyperlink*.":::

6. <span data-ttu-id="00b2d-126">Bestätigen Sie Ihre Anforderung, und klicken Sie auf die Schaltfläche *"Jetzt testen".*</span><span class="sxs-lookup"><span data-stu-id="00b2d-126">Confirm your request and click the *Try now* button.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Klicken Sie nun auf die Schaltfläche &quot;Jetzt testen*&quot;.":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a><span data-ttu-id="00b2d-128">Schritt 2: Überwachen und Überprüfen des öffentlichen MX-Eintrags</span><span class="sxs-lookup"><span data-stu-id="00b2d-128">Step 2: Audit and verify the public MX record</span></span>

<span data-ttu-id="00b2d-129">Um Microsoft Defender für Office 365 effektiv zu bewerten, ist es wichtig, dass eingehende externe E-Mails über die ihrem Mandanten zugeordnete Exchange Online Protection instanz (EOP) weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="00b2d-129">To effectively evaluate Microsoft Defender for Office 365, it's important that inbound external email be relayed through the Exchange Online Protection (EOP) instance associated with your tenant.</span></span>

1. <span data-ttu-id="00b2d-130">Melden Sie sich beim M365-Verwaltungsportal an, erweitern Sie Einstellungen, und wählen Sie "Domänen" aus.</span><span class="sxs-lookup"><span data-stu-id="00b2d-130">Log on to the M365 Admin Portal, expand Settings, and select Domains.</span></span>
2. <span data-ttu-id="00b2d-131">Wählen Sie Ihre überprüfte E-Mail-Domäne aus, und klicken Sie auf "DNS verwalten".</span><span class="sxs-lookup"><span data-stu-id="00b2d-131">Select your verified email domain and click Manage DNS.</span></span>
3. <span data-ttu-id="00b2d-132">Notieren Sie sich den MX-Eintrag, der generiert und Ihrem EOP-Mandanten zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="00b2d-132">Make note of the MX record generated and assigned to your EOP tenant.</span></span>
4. <span data-ttu-id="00b2d-133">Greifen Sie auf Ihre externe (öffentliche) DNS-Zone zu, und überprüfen Sie den primären MX-Eintrag, der Ihrer E-Mail-Domäne zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="00b2d-133">Access your external (public) DNS zone and check the primary MX record associated with your email domain.</span></span>
    - <span data-ttu-id="00b2d-134">*Wenn Ihr öffentlicher MX-Eintrag derzeit mit der zugewiesenen EOP-Adresse übereinstimmt (z. B. tenant-com.mail.protection.outlook.com), sollten keine weiteren Routingänderungen erforderlich sein.*</span><span class="sxs-lookup"><span data-stu-id="00b2d-134">*If your public MX record currently matches the assigned EOP address (e.g. tenant-com.mail.protection.outlook.com) then no further routing changes should be required*.</span></span>
    - <span data-ttu-id="00b2d-135">Wenn Ihr öffentlicher MX-Eintrag derzeit in ein SMTP-Gateway eines Drittanbieters oder lokalen Anbieters aufgelöst wird, sind möglicherweise zusätzliche Routingkonfigurationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="00b2d-135">If your public MX record currently resolves to a third-party or on-premises SMTP gateway then additional routing configurations may be required.</span></span>
    - <span data-ttu-id="00b2d-136">Wenn Ihr öffentlicher MX-Eintrag derzeit in lokale Exchange aufgelöst wird, befinden Sie sich möglicherweise immer noch in einem Hybridmodell, in dem einige Empfängerpostfächer noch nicht zu EXO migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="00b2d-136">If your public MX record currently resolves to on-premises Exchange then you may still be in a hybrid model where some recipient mailbox have not yet been migrated to EXO.</span></span>

## <a name="step-3-audit-accepted-domains"></a><span data-ttu-id="00b2d-137">Schritt 3: Überwachen akzeptierter Domänen</span><span class="sxs-lookup"><span data-stu-id="00b2d-137">Step 3: Audit accepted domains</span></span>

1. <span data-ttu-id="00b2d-138">Melden Sie sich im Exchange Online Admin Portal an, wählen Sie "E-Mail Flow" aus, und klicken Sie dann auf "Akzeptierte Domänen".</span><span class="sxs-lookup"><span data-stu-id="00b2d-138">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Accepted Domains.</span></span>
2. <span data-ttu-id="00b2d-139">Notieren Sie sich aus der Liste der akzeptierten Domänen, die in Ihrem Mandanten hinzugefügt und überprüft wurden, den **Domänentyp** für Ihre primäre E-Mail-Domäne.</span><span class="sxs-lookup"><span data-stu-id="00b2d-139">From the list of accepted domains that have been added and verified in your tenant, make note of the **domain type** for your primary email domain.</span></span>
    - <span data-ttu-id="00b2d-140">Wenn der Domänentyp auf ***Autoritativ*** festgelegt ist, wird davon ausgegangen, dass sich alle Empfängerpostfächer für Ihre Organisation derzeit in Exchange Online befinden.</span><span class="sxs-lookup"><span data-stu-id="00b2d-140">If the domain type is set to ***Authoritative*** then it is assumed all recipient mailboxes for your organization currently reside in Exchange Online.</span></span>
    - <span data-ttu-id="00b2d-141">Wenn der Domänentyp auf ***"Internes Relay"*** festgelegt ist, befinden Sie sich möglicherweise noch in einem Hybridmodell, in dem sich einige Empfängerpostfächer weiterhin lokal befinden.</span><span class="sxs-lookup"><span data-stu-id="00b2d-141">If the domain type is set to ***Internal Relay*** then you may still be in a hybrid model where some recipient mailboxes still reside on-premises.</span></span>

## <a name="step-4-audit-inbound-connectors"></a><span data-ttu-id="00b2d-142">Schritt 4: Überwachen eingehender Connectors</span><span class="sxs-lookup"><span data-stu-id="00b2d-142">Step 4: Audit inbound connectors</span></span>

1. <span data-ttu-id="00b2d-143">Melden Sie sich im Exchange Online Admin Portal an, wählen Sie E-Mail-Flow aus, und klicken Sie dann auf Connectors.</span><span class="sxs-lookup"><span data-stu-id="00b2d-143">Log on the Exchange Online Admin Portal, select Mail Flow, and then click Connectors.</span></span>
2. <span data-ttu-id="00b2d-144">Notieren Sie sich aus der Liste der konfigurierten Connectors alle Einträge, die aus der **Partnerorganisation** stammen und mit einem SMTP-Gateway eines Drittanbieters korrelieren können.</span><span class="sxs-lookup"><span data-stu-id="00b2d-144">From the list of configured connectors, make note of any entries which are from **Partner Organization** and may correlate to a third-party SMTP gateway.</span></span>
3. <span data-ttu-id="00b2d-145">Notieren Sie sich aus der Liste der konfigurierten Connectors alle Einträge, die **vom E-Mail-Server Ihrer Organisation** bezeichnet werden, was möglicherweise darauf hinweist, dass Sie sich noch in einem Hybridszenario befinden.</span><span class="sxs-lookup"><span data-stu-id="00b2d-145">From the list of configured connectors, make note of any entries labeled **From your organization's email server** which may indicate that you are still in hybrid scenario.</span></span>

## <a name="step-5-activate-the-evaluation"></a><span data-ttu-id="00b2d-146">Schritt 5: Aktivieren der Auswertung</span><span class="sxs-lookup"><span data-stu-id="00b2d-146">Step 5: Activate the evaluation</span></span>

<span data-ttu-id="00b2d-147">Verwenden Sie die hier aufgeführten Anweisungen, um Microsoft Defender für Office 365 Auswertung über das Microsoft 365 Defender Portal zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="00b2d-147">Use the instructions here to activate your Microsoft Defender for Office 365 evaluation from the Microsoft 365 Defender portal.</span></span>

1. <span data-ttu-id="00b2d-148">Melden Sie sich bei Ihrem Mandanten mit einem Konto an, das Zugriff auf das Microsoft 365 Defender-Portal hat.</span><span class="sxs-lookup"><span data-stu-id="00b2d-148">Log on to your tenant with an account that has access to the Microsoft 365 Defender portal.</span></span>
2. <span data-ttu-id="00b2d-149">Wählen Sie aus, ob Sie das **Microsoft 365 Defender-Portal** zur Standardschnittstelle für Microsoft Defender für Office 365 Verwaltung machen möchten (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="00b2d-149">Choose whether you want to make the **Microsoft 365 Defender portal** your default interface for Microsoft Defender for Office 365 administration (recommended).</span></span>

:::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Klicken Sie auf die Schaltfläche &quot;Einstellungen aktivieren&quot;, um das zentrale und verbesserte Microsoft 365 Defender-Portal für die Verwaltung zu verwenden.":::

3. <span data-ttu-id="00b2d-151">Wählen Sie im Navigationsmenü **"Richtlinien & Regeln"** unter *"E-Mail & Zusammenarbeit"* aus.</span><span class="sxs-lookup"><span data-stu-id="00b2d-151">From the navigation menu, select **Policies & Rules** under *Email & Collaboration*.</span></span>

:::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Hier sehen Sie ein Bild des Menüs &quot;E-Mail & Zusammenarbeit&quot;, das auf Richtlinien & Regeln zeigt. Klicken Sie darauf!":::

4. <span data-ttu-id="00b2d-153">Klicken Sie im Dashboard *"Richtlinie & Regeln"* auf **"Bedrohungsrichtlinien".**</span><span class="sxs-lookup"><span data-stu-id="00b2d-153">On the *Policy & Rules* dashboard, click **Threat Policies**.</span></span>

:::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Abbildung des Richtlinien-&-Regeldashboards und eines Pfeils, der auf Bedrohungsrichtlinien zeigt. Klicken Sie als Nächstes darauf!":::

5. <span data-ttu-id="00b2d-155">Scrollen Sie nach unten zu *zusätzlichen Richtlinien,* und wählen Sie die Kachel **"Defender für Office 365 auswerten".**</span><span class="sxs-lookup"><span data-stu-id="00b2d-155">Scroll down to *Additional Policies* and select the **Evaluate Defender for Office 365** tile.</span></span>

:::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Die Kachel &quot;Eval Defender für Office 365&quot; gibt an, dass es sich um eine 30-tägige Testversion über E-Mail-& Zusammenarbeitsvektoren handelt. Klicken Sie durch.":::

6. <span data-ttu-id="00b2d-157">Wählen Sie nun aus, ob externe E-Mails direkt an Exchange Online oder an ein Gateway oder einen Dienst eines Drittanbieters weitergeroutet werden, und klicken Sie auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="00b2d-157">Now choose whether external email routes to Exchange Online directly, or to a third-party gateway or service, and click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Defender für Office 365 wertet das Senden von E-Mails an Ihre Exchange Online Postfächer aus. Geben Sie details dazu an, wie Ihre E-Mails jetzt weitergeleitet werden, einschließlich des Namens des ausgehenden Connectors, der Ihre E-Mails leitet. Wenn Sie nur Exchange Online Protection (EOP) verwenden, verfügen Sie nicht über einen Connector. Wählen Sie einen von mir, der einen Drittanbieter oder lokalen Anbieter verwendet, oder verwenden Sie nur EOP.":::

7. <span data-ttu-id="00b2d-159">Wenn Sie ein Drittanbietergateway verwenden, wählen Sie den Namen des Anbieters in der Dropdownliste zusammen mit dem eingehenden Connector aus, der dieser Lösung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="00b2d-159">If you use a third-party gateway, select the vendor name from the drop-down along with the inbound connector associated with that solution.</span></span> <span data-ttu-id="00b2d-160">Wenn Sie Ihre Antworten aufgelistet haben, klicken Sie auf "Weiter".</span><span class="sxs-lookup"><span data-stu-id="00b2d-160">When you've listed your answers, click Next.</span></span>

:::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="In diesem Dialogfeld wählen Sie den Drittanbieterdienst aus, den Ihre Organisation verwendet, oder wählen *Other* aus. Wählen Sie im nächsten Dialogfeld nach unten den eingehenden Connector aus. Klicken Sie dann auf &quot;Weiter&quot;.":::

8. <span data-ttu-id="00b2d-162">Überprüfen Sie Ihre Einstellungen, und klicken Sie auf die Schaltfläche **"Evaluierung erstellen".**</span><span class="sxs-lookup"><span data-stu-id="00b2d-162">Review your settings and click the **Create Evaluation** button.</span></span>

|  |  |
|---------|---------|
|  :::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Dieser Bereich enthält eine Dropdownliste, um Ihre Einstellungen zu überprüfen. Sie verfügt auch über einen klickbaren Link zum Bearbeiten des Routingtyps, falls erforderlich. Wenn Sie fertig sind, klicken Sie auf die große blaue Schaltfläche &quot;Auswertung erstellen&quot;.":::   |   :::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Und jetzt ist die Einrichtung abgeschlossen. Die blaue Schaltfläche auf dieser Seite lautet &quot;Zur Auswertung wechseln&quot;.":::      |

## <a name="next-steps"></a><span data-ttu-id="00b2d-165">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="00b2d-165">Next steps</span></span>

<span data-ttu-id="00b2d-166">Schritt 3 von 3: Einrichten des Pilotprojekts für Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="00b2d-166">Step 3 of 3: Set up the pilot for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="00b2d-167">Kehren Sie zur Übersicht über [das Auswerten von Microsoft Defender für Office 365](eval-defender-office-365-overview.md)</span><span class="sxs-lookup"><span data-stu-id="00b2d-167">Return to the overview for [Evaluate Microsoft Defender for Office 365](eval-defender-office-365-overview.md)</span></span>

<span data-ttu-id="00b2d-168">Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="00b2d-168">Return to the overview for [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)</span></span>