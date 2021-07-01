---
title: Onboarding mithilfe des Microsoft Endpoint Manager
description: Erfahren Sie, wie Sie das Onboarding in Microsoft Defender für Endpunkt mithilfe von Microsoft Endpoint Manager
keywords: Onboarding, Konfiguration, bereitstellen, Bereitstellung, Endpunkt-Manager, Microsoft Defender für Endpunkt, Sammlungserstellung, Endpunkterkennungsantwort, Schutz der nächsten Generation, Verringerung der Angriffsfläche, Microsoft Endpoint Manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 397aa8a0e8f0523c9975d40759d39369c221222b
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228975"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="04a67-104">Onboarding mithilfe des Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="04a67-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04a67-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="04a67-105">**Applies to:**</span></span>
- [<span data-ttu-id="04a67-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="04a67-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="04a67-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04a67-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="04a67-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="04a67-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="04a67-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="04a67-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="04a67-110">Dieser Artikel ist Teil des Bereitstellungshandbuchs und dient als Beispiel für eine Onboardingmethode.</span><span class="sxs-lookup"><span data-stu-id="04a67-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span>

<span data-ttu-id="04a67-111">Im [Thema "Planung"](deployment-strategy.md) wurden verschiedene Methoden zum Onboarding von Geräten in den Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="04a67-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="04a67-112">In diesem Thema wird die cloudeigene Architektur behandelt.</span><span class="sxs-lookup"><span data-stu-id="04a67-112">This topic covers the cloud-native architecture.</span></span>

<span data-ttu-id="04a67-113">![Abbildung der cloudeigenen Architektur ](images/cloud-native-architecture.png)
 *(Diagramm der Umgebungsarchitekturen)*</span><span class="sxs-lookup"><span data-stu-id="04a67-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="04a67-114">Während Defender für Endpunkt das Onboarding verschiedener Endpunkte und Tools unterstützt, werden diese in diesem Artikel nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="04a67-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="04a67-115">Informationen zum allgemeinen Onboarding mit anderen unterstützten Bereitstellungstools und -methoden finden Sie in der [Onboarding-Übersicht.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="04a67-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>

<span data-ttu-id="04a67-116">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) ist eine Lösungsplattform, die mehrere Dienste vereinheitlicht.</span><span class="sxs-lookup"><span data-stu-id="04a67-116">[Microsoft Endpoint Manager](/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="04a67-117">Es enthält [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) für die cloudbasierte Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="04a67-117">It includes [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>

<span data-ttu-id="04a67-118">In diesem Thema werden Benutzer zu folgenden Themen geleitet:</span><span class="sxs-lookup"><span data-stu-id="04a67-118">This topic guides users in:</span></span>

- <span data-ttu-id="04a67-119">Schritt 1: Onboarding von Geräten in den Dienst durch Erstellen einer Gruppe in Microsoft Endpoint Manager (MEM) zum Zuweisen von Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="04a67-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="04a67-120">Schritt 2: Konfigurieren von Defender für Endpunkt-Funktionen mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="04a67-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="04a67-121">Dieser Onboardingleitfaden führt Sie durch die folgenden grundlegenden Schritte, die Sie bei der Verwendung von Microsoft Endpoint Manager ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="04a67-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

- [<span data-ttu-id="04a67-122">Identifizieren von Zielgeräten oder Benutzern</span><span class="sxs-lookup"><span data-stu-id="04a67-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)
  - <span data-ttu-id="04a67-123">Erstellen einer Azure Active Directory Gruppe (Benutzer oder Gerät)</span><span class="sxs-lookup"><span data-stu-id="04a67-123">Creating an Azure Active Directory group (User or Device)</span></span>
- [<span data-ttu-id="04a67-124">Erstellen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="04a67-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)
  - <span data-ttu-id="04a67-125">In Microsoft Endpoint Manager führen wir Sie beim Erstellen einer separaten Richtlinie für jede Funktion.</span><span class="sxs-lookup"><span data-stu-id="04a67-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>

## <a name="resources"></a><span data-ttu-id="04a67-126">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="04a67-126">Resources</span></span>

<span data-ttu-id="04a67-127">Hier sind die Links, die Sie für den Rest des Prozesses benötigen:</span><span class="sxs-lookup"><span data-stu-id="04a67-127">Here are the links you'll need for the rest of the process:</span></span>

- [<span data-ttu-id="04a67-128">MEM-Portal</span><span class="sxs-lookup"><span data-stu-id="04a67-128">MEM portal</span></span>](https://aka.ms/memac)
- [<span data-ttu-id="04a67-129">Sicherheitscenter</span><span class="sxs-lookup"><span data-stu-id="04a67-129">Security Center</span></span>](https://securitycenter.windows.com/)
- [<span data-ttu-id="04a67-130">Intune-Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="04a67-130">Intune Security baselines</span></span>](/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="04a67-131">Weitere Informationen zu Microsoft Endpoint Manager finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="04a67-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>

- [<span data-ttu-id="04a67-132">Microsoft Endpoint Manager Seite</span><span class="sxs-lookup"><span data-stu-id="04a67-132">Microsoft Endpoint Manager page</span></span>](/mem/)
- [<span data-ttu-id="04a67-133">Blogbeitrag zur Konvergenz von Intune und ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="04a67-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="04a67-134">Einführungsvideo zu MEM</span><span class="sxs-lookup"><span data-stu-id="04a67-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="04a67-135">Schritt 1: Onboarding von Geräten durch Erstellen einer Gruppe in MEM zum Zuweisen von Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="04a67-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>

### <a name="identify-target-devices-or-users"></a><span data-ttu-id="04a67-136">Identifizieren von Zielgeräten oder Benutzern</span><span class="sxs-lookup"><span data-stu-id="04a67-136">Identify target devices or users</span></span>

<span data-ttu-id="04a67-137">In diesem Abschnitt erstellen wir eine Testgruppe zum Zuweisen Ihrer Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="04a67-137">In this section, we will create a test group to assign your configurations on.</span></span>

> [!NOTE]
> <span data-ttu-id="04a67-138">Intune verwendet Azure Active Directory (Azure AD)-Gruppen zum Verwalten von Geräten und Benutzern.</span><span class="sxs-lookup"><span data-stu-id="04a67-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="04a67-139">Als Intune-Administrator können Sie Gruppen für Ihre Organisatorischen Anforderungen einrichten.</span><span class="sxs-lookup"><span data-stu-id="04a67-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span>
>
> <span data-ttu-id="04a67-140">Weitere Informationen finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten.](/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="04a67-140">For more information, see [Add groups to organize users and devices](/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="04a67-141">Erstellen einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="04a67-141">Create a group</span></span>

1. <span data-ttu-id="04a67-142">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="04a67-142">Open the MEM portal.</span></span>

2. <span data-ttu-id="04a67-143">Öffnen **Sie Gruppen > neue Gruppe.**</span><span class="sxs-lookup"><span data-stu-id="04a67-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-144">![Abbildung von Microsoft Endpoint Manager Portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3. <span data-ttu-id="04a67-145">Geben Sie Details ein, und erstellen Sie eine neue Gruppe.</span><span class="sxs-lookup"><span data-stu-id="04a67-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-146">![Abbildung von Microsoft Endpoint Manager Portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4. <span data-ttu-id="04a67-147">Fügen Sie Ihren Testbenutzer oder Ihr Testgerät hinzu.</span><span class="sxs-lookup"><span data-stu-id="04a67-147">Add your test user or device.</span></span>

5. <span data-ttu-id="04a67-148">Öffnen Sie im Bereich **"Gruppen > Alle Gruppen"** die neue Gruppe.</span><span class="sxs-lookup"><span data-stu-id="04a67-148">From the **Groups > All groups** pane, open your new group.</span></span>

6. <span data-ttu-id="04a67-149">Wählen Sie  **Mitglieder > Mitglieder hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-149">Select  **Members > Add members**.</span></span>

7. <span data-ttu-id="04a67-150">Suchen Sie Den Testbenutzer oder das Testgerät, und wählen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-151">![Abbildung von Microsoft Endpoint Manager Portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8. <span data-ttu-id="04a67-152">Ihre Testgruppe verfügt nun über ein Mitglied zum Testen.</span><span class="sxs-lookup"><span data-stu-id="04a67-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="04a67-153">Schritt 2: Erstellen von Konfigurationsrichtlinien zum Konfigurieren von Microsoft Defender für Endpunktfunktionen</span><span class="sxs-lookup"><span data-stu-id="04a67-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>

<span data-ttu-id="04a67-154">Im folgenden Abschnitt erstellen Sie eine Reihe von Konfigurationsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="04a67-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="04a67-155">Zunächst ist eine Konfigurationsrichtlinie zum Auswählen der Gruppen von Benutzern oder Geräten, die in Defender für Endpunkt integriert werden:</span><span class="sxs-lookup"><span data-stu-id="04a67-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="04a67-156">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="04a67-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response)

<span data-ttu-id="04a67-157">Anschließend erstellen Sie mehrere verschiedene Arten von Endpunktsicherheitsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="04a67-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="04a67-158">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="04a67-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="04a67-159">Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="04a67-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="04a67-160">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="04a67-160">Endpoint detection and response</span></span>

1. <span data-ttu-id="04a67-161">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="04a67-161">Open the MEM portal.</span></span>

2. <span data-ttu-id="04a67-162">Navigieren Sie zu **Endpunktsicherheit > Endpunkterkennung und -antwort.**</span><span class="sxs-lookup"><span data-stu-id="04a67-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="04a67-163">Klicken Sie auf **Profil erstellen.**</span><span class="sxs-lookup"><span data-stu-id="04a67-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-164">![Abbildung von Microsoft Endpoint Manager Portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3. <span data-ttu-id="04a67-165">Wählen Sie unter **Plattform Windows 10 und höher, Profil – Endpunkterkennung und -antwort > Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection  and response > Create**.</span></span>

4. <span data-ttu-id="04a67-166">Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-167">![Abbildung von Microsoft Endpoint Manager Portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5. <span data-ttu-id="04a67-168">Wählen Sie nach Bedarf Einstellungen aus, und wählen Sie dann  **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-169">![Abbildung von Microsoft Endpoint Manager Portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="04a67-170">In diesem Fall wurde dies automatisch ausgefüllt, da Defender für Endpunkt bereits in Intune integriert wurde.</span><span class="sxs-lookup"><span data-stu-id="04a67-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="04a67-171">Weitere Informationen zur Integration finden Sie unter [Aktivieren von Microsoft Defender für Endpunkt in Intune.](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp)</span><span class="sxs-lookup"><span data-stu-id="04a67-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    >
    > <span data-ttu-id="04a67-172">Die folgende Abbildung ist ein Beispiel dafür, was Sie sehen werden, wenn Microsoft Defender für Endpunkt NICHT in Intune integriert ist:</span><span class="sxs-lookup"><span data-stu-id="04a67-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Abbildung von Microsoft Endpoint Manager Portal7](images/2466460812371ffae2d19a10c347d6f4.png)

6. <span data-ttu-id="04a67-174">Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-175">![Abbildung von Microsoft Endpoint Manager Portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7. <span data-ttu-id="04a67-176">Fügen Sie eine Testgruppe hinzu, indem Sie auf "Gruppen auswählen" klicken, um ihre Gruppe **einzuschließen** und auszuwählen, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-177">![Abbildung von Microsoft Endpoint Manager Portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8. <span data-ttu-id="04a67-178">Überprüfen und akzeptieren Sie, und wählen Sie dann  **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-179">![Abbildung von Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9. <span data-ttu-id="04a67-180">Sie können die abgeschlossene Richtlinie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="04a67-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-181">![Abbildung von Microsoft Endpoint Manager Portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="04a67-182">Schutzlösungen der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="04a67-182">Next-generation protection</span></span>

1. <span data-ttu-id="04a67-183">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="04a67-183">Open the MEM portal.</span></span>

2. <span data-ttu-id="04a67-184">Navigieren Sie zu **Endpunktsicherheit > Antivirus > Richtlinie erstellen.**</span><span class="sxs-lookup"><span data-stu-id="04a67-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-185">![Abbildung von Microsoft Endpoint Manager Portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3. <span data-ttu-id="04a67-186">Plattform auswählen **– Windows 10 und höher – Windows und Profil – Microsoft Defender Antivirus > Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="04a67-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft  Defender Antivirus > Create**.</span></span>

4. <span data-ttu-id="04a67-187">Geben Sie Den Namen und die Beschreibung ein, und wählen Sie dann  **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-188">![Abbildung von Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5. <span data-ttu-id="04a67-189">Legen Sie auf der **Seite "Konfigurationseinstellungen"** die Konfigurationen fest, die Sie für Microsoft Defender Antivirus (CloudSchutz, Ausschlüsse, Real-Time Schutz und Wartung) benötigen.</span><span class="sxs-lookup"><span data-stu-id="04a67-189">In the **Configuration settings page**: Set the configurations you require for  Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time  Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-190">![Abbildung von Microsoft Endpoint Manager Portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6. <span data-ttu-id="04a67-191">Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-192">![Abbildung von Microsoft Endpoint Manager Portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7. <span data-ttu-id="04a67-193">Wählen Sie Die einzuschließenden Gruppen aus, weisen Sie sie Ihrer Testgruppe zu, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-194">![Abbildung von Microsoft Endpoint Manager Portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8. <span data-ttu-id="04a67-195">Überprüfen und erstellen Sie, und wählen Sie dann  **"Erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-196">![Abbildung von Microsoft Endpoint Manager Portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9. <span data-ttu-id="04a67-197">Die von Ihnen erstellte Konfigurationsrichtlinie wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04a67-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-198">![Abbildung von Microsoft Endpoint Manager Portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="04a67-199">Attack Surface Reduction – Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="04a67-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1. <span data-ttu-id="04a67-200">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="04a67-200">Open the MEM portal.</span></span>

2. <span data-ttu-id="04a67-201">Navigieren Sie zu **Endpunktsicherheit > Attack Surface Reduction.**</span><span class="sxs-lookup"><span data-stu-id="04a67-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3. <span data-ttu-id="04a67-202">Wählen Sie  **"Richtlinie erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-202">Select  **Create Policy**.</span></span>

4. <span data-ttu-id="04a67-203">Select **Platform – Windows 10 and later – Profile – Attack Surface Reduction rules > Create**.</span><span class="sxs-lookup"><span data-stu-id="04a67-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction  rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-204">![Abbildung von Microsoft Endpoint Manager Portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5. <span data-ttu-id="04a67-205">Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-206">![Abbildung von Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6. <span data-ttu-id="04a67-207">Auf der **Seite "Konfigurationseinstellungen":** Legen Sie die Konfigurationen fest, die Sie für Attack Surface Reduction-Regeln benötigen, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-207">In the **Configuration settings page**: Set the configurations you require for  Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04a67-208">Wir werden alle Attack Surface Reduction-Regeln für die Überwachung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="04a67-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    >
    > <span data-ttu-id="04a67-209">Weitere Informationen finden Sie unter [Attack Surface Reduction-Regeln.](attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="04a67-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-210">![Abbildung von Microsoft Endpoint Manager Portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7. <span data-ttu-id="04a67-211">Fügen Sie bereichsbezogene Tags nach Bedarf hinzu, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-212">![Abbildung von Microsoft Endpoint Manager Portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8. <span data-ttu-id="04a67-213">Wählen Sie Gruppen aus, die der Testgruppe zugeordnet werden sollen, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-214">![Abbildung von Microsoft Endpoint Manager Portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="04a67-215">Überprüfen Sie die Details, und  **wählen** Sie dann erstellen aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-216">![Abbildung von Microsoft Endpoint Manager Portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="04a67-217">Zeigen Sie die Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="04a67-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-218">![Abbildung von Microsoft Endpoint Manager Portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="04a67-219">Attack Surface Reduction – Webschutz</span><span class="sxs-lookup"><span data-stu-id="04a67-219">Attack Surface Reduction – Web Protection</span></span>

1. <span data-ttu-id="04a67-220">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="04a67-220">Open the MEM portal.</span></span>

2. <span data-ttu-id="04a67-221">Navigieren Sie zu **Endpunktsicherheit > Attack Surface Reduction.**</span><span class="sxs-lookup"><span data-stu-id="04a67-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3. <span data-ttu-id="04a67-222">Wählen Sie  **"Richtlinie erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-222">Select  **Create Policy**.</span></span>

4. <span data-ttu-id="04a67-223">Wählen Sie **Windows 10 und höher – Webschutz > Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-224">![Abbildung von Microsoft Endpoint Manager Portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5. <span data-ttu-id="04a67-225">Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-226">![Abbildung von Microsoft Endpoint Manager Portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6. <span data-ttu-id="04a67-227">Auf der **Seite "Konfigurationseinstellungen":** Legen Sie die Konfigurationen fest, die Sie für Webschutz benötigen, und wählen Sie dann  **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04a67-228">Wir konfigurieren Webschutz so, dass er blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="04a67-228">We are configuring Web Protection to Block.</span></span>
    >
    > <span data-ttu-id="04a67-229">Weitere Informationen finden Sie unter [Webschutz.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="04a67-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-230">![Abbildung von Microsoft Endpoint Manager Portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7. <span data-ttu-id="04a67-231">Fügen Sie **> Nächsten nach Bedarf Bereichstags** hinzu.</span><span class="sxs-lookup"><span data-stu-id="04a67-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-232">![Abbildung von Microsoft Endpoint Manager Portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8. <span data-ttu-id="04a67-233">Wählen Sie **"Zu Testgruppe zuweisen" > "Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-234">![Abbildung von Microsoft Endpoint Manager Portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="04a67-235">Wählen Sie **"Überprüfen" und "Erstellen > Erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-236">![Abbildung von Microsoft Endpoint Manager Portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="04a67-237">Zeigen Sie die Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="04a67-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-238">![Abbildung von Microsoft Endpoint Manager Portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="04a67-239">Überprüfen von Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="04a67-239">Validate configuration settings</span></span>

### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="04a67-240">Bestätigen, dass Richtlinien angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="04a67-240">Confirm Policies have been applied</span></span>

<span data-ttu-id="04a67-241">Nachdem die Konfigurationsrichtlinie zugewiesen wurde, dauert es einige Zeit, bis sie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="04a67-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="04a67-242">Informationen zum Timing finden Sie unter [Intune-Konfigurationsinformationen.](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned)</span><span class="sxs-lookup"><span data-stu-id="04a67-242">For information on timing, see [Intune configuration information](/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="04a67-243">Um zu bestätigen, dass die Konfigurationsrichtlinie auf Ihr Testgerät angewendet wurde, führen Sie den folgenden Prozess für jede Konfigurationsrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="04a67-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1. <span data-ttu-id="04a67-244">Öffnen Sie das MEM-Portal, und navigieren Sie zur entsprechenden Richtlinie, wie in den obigen Schritten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="04a67-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="04a67-245">Das folgende Beispiel zeigt die Schutzeinstellungen der nächsten Generation.</span><span class="sxs-lookup"><span data-stu-id="04a67-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-246">[![Abbildung von Microsoft Endpoint Manager Portal33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2. <span data-ttu-id="04a67-247">Wählen Sie die **Konfigurationsrichtlinie** aus, um den Richtlinienstatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04a67-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-248">[![Abbildung von Microsoft Endpoint Manager Portal34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3. <span data-ttu-id="04a67-249">Wählen Sie  **"Gerätestatus"** aus, um den Status anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04a67-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-250">[![Abbildung von Microsoft Endpoint Manager Portal35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4. <span data-ttu-id="04a67-251">Wählen Sie  **"Benutzerstatus"** aus, um den Status anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04a67-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-252">[![Abbildung von Microsoft Endpoint Manager Portal36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5. <span data-ttu-id="04a67-253">Wählen Sie  **"Status pro Einstellung"** aus, um den Status anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="04a67-253">Select  **Per-setting status** to see the status.</span></span>

    > [!TIP]
    > <span data-ttu-id="04a67-254">Diese Ansicht ist sehr nützlich, um Einstellungen zu identifizieren, die mit einer anderen Richtlinie in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="04a67-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-255">[![Abbildung von Microsoft Endpoint Manager Portal37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="04a67-256">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="04a67-256">Endpoint detection and response</span></span>

1. <span data-ttu-id="04a67-257">Vor dem Anwenden der Konfiguration sollte der Defender für Endpoint Protection-Dienst nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="04a67-257">Before applying the configuration, the Defender for Endpoint  Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-258">[![Abbildung des Dienstbereichs1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2. <span data-ttu-id="04a67-259">Nachdem die Konfiguration angewendet wurde, sollte der Defender für Endpoint Protection-Dienst gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="04a67-259">After the configuration has been applied, the Defender for Endpoint  Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-260">[![Abbildung des Dienstbereichs2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3. <span data-ttu-id="04a67-261">Nachdem die Dienste auf dem Gerät ausgeführt wurden, wird das Gerät im Microsoft Defender Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04a67-261">After the services are running on the device, the device appears in Microsoft  Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-262">[![Abbildung von Microsoft Defender Security Center ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="04a67-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="04a67-263">Schutzlösungen der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="04a67-263">Next-generation protection</span></span>

1. <span data-ttu-id="04a67-264">Bevor Sie die Richtlinie auf ein Testgerät anwenden, sollten Sie in der Lage sein, die Einstellungen wie unten dargestellt manuell zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="04a67-264">Before applying the policy on a test device, you should be able to manually  manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-265">![Abbildung der Einstellungsseite1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2. <span data-ttu-id="04a67-266">Nachdem die Richtlinie angewendet wurde, sollten Sie die Einstellungen nicht manuell verwalten können.</span><span class="sxs-lookup"><span data-stu-id="04a67-266">After the policy has been applied, you should not be able to manually manage  the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04a67-267">In der folgenden Abbildung wird das Aktivieren des über die **Cloud bereitgestellten Schutzes** und das Aktivieren des **Echtzeitschutzes** als verwaltet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="04a67-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="04a67-268">![Abbildung der Einstellungsseite2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="04a67-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="04a67-269">Attack Surface Reduction – Regeln zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="04a67-269">Attack Surface Reduction – Attack surface reduction rules</span></span>

1. <span data-ttu-id="04a67-270">Bevor Sie die Richtlinie auf ein Testgerät anwenden, stiften Sie ein PowerShell-Fenster, und geben Sie `Get-MpPreference` ein.</span><span class="sxs-lookup"><span data-stu-id="04a67-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2. <span data-ttu-id="04a67-271">Dies sollte mit den folgenden Zeilen ohne Inhalt antworten:</span><span class="sxs-lookup"><span data-stu-id="04a67-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="04a67-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="04a67-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    >
    > <span data-ttu-id="04a67-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="04a67-273">AttackSurfaceReductionRules_Actions:</span></span>
    >
    > <span data-ttu-id="04a67-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="04a67-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Abbildung der Befehlszeile1](images/cb0260d4b2636814e37eee427211fe71.png)

3. <span data-ttu-id="04a67-276">Öffnen Sie nach dem Anwenden der Richtlinie auf einem Testgerät ein PowerShell-Windows und geben Sie `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="04a67-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4. <span data-ttu-id="04a67-277">Dies sollte mit den folgenden Zeilen mit Inhalt wie unten dargestellt antworten:</span><span class="sxs-lookup"><span data-stu-id="04a67-277">This should respond with the following lines with content as shown below:</span></span>

    ![Abbildung der Befehlszeile2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="04a67-279">Attack Surface Reduction – Webschutz</span><span class="sxs-lookup"><span data-stu-id="04a67-279">Attack Surface Reduction – Web Protection</span></span>

1. <span data-ttu-id="04a67-280">Öffnen Sie auf dem Testgerät eine PowerShell-Windows und geben Sie `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="04a67-280">On the test device, open a PowerShell Windows and type  `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2. <span data-ttu-id="04a67-281">Dies sollte mit einer 0 wie unten dargestellt antworten.</span><span class="sxs-lookup"><span data-stu-id="04a67-281">This should respond with a 0 as shown below.</span></span>

    ![Abbildung der Befehlszeile3](images/196a8e194ac99d84221f405d0f684f8c.png)

3. <span data-ttu-id="04a67-283">Öffnen Sie nach dem Anwenden der Richtlinie eine PowerShell-Windows und geben Sie `(Get-MpPreference).EnableNetworkProtection` .</span><span class="sxs-lookup"><span data-stu-id="04a67-283">After applying the policy, open a PowerShell Windows and type  `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4. <span data-ttu-id="04a67-284">Dies sollte mit einer 1 antworten, wie unten dargestellt.</span><span class="sxs-lookup"><span data-stu-id="04a67-284">This should respond with a 1 as shown below.</span></span>

    ![Abbildung der Befehlszeile4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
