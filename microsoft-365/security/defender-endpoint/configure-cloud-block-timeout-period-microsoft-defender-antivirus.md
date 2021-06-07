---
title: Konfigurieren des Timeoutzeitraums für Microsoft Defender Antivirus Cloudblock
description: Sie können konfigurieren, wie lange Microsoft Defender Antivirus die Ausführung einer Datei blockieren, während Sie auf eine Cloudermittlung warten.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender, Cloud, Timeout, blockieren, Zeitraum, Sekunden
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789087"
---
# <a name="configure-the-cloud-block-timeout-period"></a><span data-ttu-id="52cc6-104">Konfigurieren des Timeoutzeitraums für Cloudblockierung</span><span class="sxs-lookup"><span data-stu-id="52cc6-104">Configure the cloud block timeout period</span></span>

<span data-ttu-id="52cc6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="52cc6-105">**Applies to:**</span></span>

- [<span data-ttu-id="52cc6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="52cc6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="52cc6-107">Wenn Microsoft Defender Antivirus eine verdächtige Datei findet, kann sie verhindern, dass die Datei ausgeführt wird, während sie den [Microsoft Defender Antivirus Clouddienst](cloud-protection-microsoft-defender-antivirus.md)abfragt.</span><span class="sxs-lookup"><span data-stu-id="52cc6-107">When Microsoft Defender Antivirus finds a suspicious file, it can prevent the file from running while it queries the [Microsoft Defender Antivirus cloud service](cloud-protection-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="52cc6-108">Der Standardzeitraum, für den die Datei [blockiert](configure-block-at-first-sight-microsoft-defender-antivirus.md) wird, beträgt 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="52cc6-108">The default period that the file is [blocked](configure-block-at-first-sight-microsoft-defender-antivirus.md) is 10 seconds.</span></span> <span data-ttu-id="52cc6-109">Wenn Sie ein Sicherheitsadministrator sind, können Sie mehr Zeit angeben, bis die Datei ausgeführt werden darf.</span><span class="sxs-lookup"><span data-stu-id="52cc6-109">If you're a security administrator, you can specify more time to wait before the file is allowed to run.</span></span> <span data-ttu-id="52cc6-110">Durch die Erweiterung des Cloudblock-Timeoutzeitraums kann sichergestellt werden, dass genügend Zeit für eine ordnungsgemäße Entscheidung vom Microsoft Defender Antivirus Clouddienst vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="52cc6-110">Extending the cloud block timeout period can help ensure there is enough time to receive a proper determination from the Microsoft Defender Antivirus cloud service.</span></span>

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a><span data-ttu-id="52cc6-111">Voraussetzungen für die Verwendung des erweiterten Cloudblock-Timeouts</span><span class="sxs-lookup"><span data-stu-id="52cc6-111">Prerequisites to use the extended cloud block timeout</span></span>

<span data-ttu-id="52cc6-112">["Beim ersten Sichten blockieren"](configure-block-at-first-sight-microsoft-defender-antivirus.md) und seine Voraussetzungen müssen aktiviert sein, bevor Sie einen erweiterten Timeoutzeitraum angeben können.</span><span class="sxs-lookup"><span data-stu-id="52cc6-112">[Block at first sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) and its prerequisites must be enabled before you can specify an extended timeout period.</span></span>

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a><span data-ttu-id="52cc6-113">Angeben des erweiterten Timeoutzeitraums mithilfe von Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="52cc6-113">Specify the extended timeout period using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="52cc6-114">Sie können den Cloudblock-Timeoutzeitraum mit einer [Endpunktsicherheitsrichtlinie in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy)angeben.</span><span class="sxs-lookup"><span data-stu-id="52cc6-114">You can specify the cloud block timeout period with an [endpoint security policy in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).</span></span>

1. <span data-ttu-id="52cc6-115">Wechseln Sie zum Endpoint Manager Admin Center ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="52cc6-115">Go to the Endpoint Manager admin center ([https://endpoint.microsoft.com/](https://endpoint.microsoft.com/)) and sign in.</span></span>

2. <span data-ttu-id="52cc6-116">Wählen Sie **Endpunktsicherheit** aus, und wählen Sie dann unter **"Verwalten"** die Option **"Antivirus"** aus.</span><span class="sxs-lookup"><span data-stu-id="52cc6-116">Select **Endpoint security**, and then under **Manage**, choose **Antivirus**.</span></span>

3. <span data-ttu-id="52cc6-117">Wählen (oder erstellen) Sie eine Antivirenrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="52cc6-117">Select (or create) an antivirus policy.</span></span>

4. <span data-ttu-id="52cc6-118">Erweitern Sie im Abschnitt **"Konfigurationseinstellungen"** den **Cloudschutz.**</span><span class="sxs-lookup"><span data-stu-id="52cc6-118">In the **Configuration settings** section, expand **Cloud protection**.</span></span> <span data-ttu-id="52cc6-119">Geben Sie dann im Feld **"Defender Cloud Extended Timeout In Seconds"** die mehr Zeit (in Sekunden) von 1 Sekunde bis 50 Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="52cc6-119">Then, in the **Defender Cloud Extended Timeout In Seconds** box, specify the more time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="52cc6-120">Alles, was Sie angeben, wird den Standardmäßigen 10 Sekunden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52cc6-120">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="52cc6-121">(Dieser Schritt ist optional) Nehmen Sie weitere Änderungen an Ihrer Antivirenrichtlinie vor.</span><span class="sxs-lookup"><span data-stu-id="52cc6-121">(This step is optional) Make any other changes to your antivirus policy.</span></span> <span data-ttu-id="52cc6-122">(Benötigen Sie Hilfe?</span><span class="sxs-lookup"><span data-stu-id="52cc6-122">(Need help?</span></span> <span data-ttu-id="52cc6-123">Informationen [zu Microsoft Defender Antivirus Richtlinie in Microsoft Intune finden Sie unter Einstellungen.)](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)</span><span class="sxs-lookup"><span data-stu-id="52cc6-123">See [Settings for Microsoft Defender Antivirus policy in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)</span></span>

6. <span data-ttu-id="52cc6-124">Wählen Sie **"Weiter"** aus, und beenden Sie die Konfiguration Ihrer Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="52cc6-124">Choose **Next**, and finish configuring your policy.</span></span>

## <a name="specify-the-extended-timeout-period-using-group-policy"></a><span data-ttu-id="52cc6-125">Angeben des erweiterten Timeoutzeitraums mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="52cc6-125">Specify the extended timeout period using Group Policy</span></span>

<span data-ttu-id="52cc6-126">Mithilfe von Gruppenrichtlinien können Sie ein erweitertes Timeout für Cloudüberprüfungen angeben.</span><span class="sxs-lookup"><span data-stu-id="52cc6-126">You can use Group Policy to specify an extended timeout for cloud checks.</span></span>

1. <span data-ttu-id="52cc6-127">Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="52cc6-127">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span></span>

2. <span data-ttu-id="52cc6-128">Klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="52cc6-128">Right-click the Group Policy Object you want to configure and then select **Edit**.</span></span>

3. <span data-ttu-id="52cc6-129">Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und wählen Sie dann **administrative Vorlagen** aus.</span><span class="sxs-lookup"><span data-stu-id="52cc6-129">In the **Group Policy Management Editor**, go to **Computer configuration**, and then select **Administrative templates**.</span></span>

3. <span data-ttu-id="52cc6-130">Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **MpEngine**.</span><span class="sxs-lookup"><span data-stu-id="52cc6-130">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **MpEngine**.</span></span>

4. <span data-ttu-id="52cc6-131">Doppelklicken Sie auf **"Erweiterte Cloudüberprüfung konfigurieren",** und stellen Sie sicher, dass die Option aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="52cc6-131">Double-click **Configure extended cloud check** and ensure the option is enabled.</span></span> 

   <span data-ttu-id="52cc6-132">Geben Sie den zusätzlichen Zeitraum an, um zu verhindern, dass die Datei ausgeführt wird, während sie auf eine Cloudermittlung wartet.</span><span class="sxs-lookup"><span data-stu-id="52cc6-132">Specify the extra amount of time to prevent the file from running while waiting for a cloud determination.</span></span> <span data-ttu-id="52cc6-133">Geben Sie die zusätzliche Zeit in Sekunden von 1 Sekunde bis 50 Sekunden an.</span><span class="sxs-lookup"><span data-stu-id="52cc6-133">Specify the extra time, in seconds, from 1 second to 50 seconds.</span></span> <span data-ttu-id="52cc6-134">Alles, was Sie angeben, wird den Standardmäßigen 10 Sekunden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="52cc6-134">Whatever you specify is added to the default 10 seconds.</span></span>

5. <span data-ttu-id="52cc6-135">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="52cc6-135">Select **OK**.</span></span>

 