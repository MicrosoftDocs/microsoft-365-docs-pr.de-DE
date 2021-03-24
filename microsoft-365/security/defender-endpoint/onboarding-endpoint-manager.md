---
title: Onboarding mit Microsoft Endpoint Manager
description: Informationen zum Onboarding in Microsoft Defender for Endpoint mithilfe von Microsoft Endpoint Manager
keywords: onboarding, configuration, deploy, deployment, endpoint manager, mdatp, advanced threat protection, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint manager
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
ms.openlocfilehash: 4028fbaedd4e0b89b37a774b79ac5302d899ec3c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060996"
---
# <a name="onboarding-using-microsoft-endpoint-manager"></a><span data-ttu-id="ca343-104">Onboarding mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ca343-104">Onboarding using Microsoft Endpoint Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ca343-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ca343-105">**Applies to:**</span></span>
- [<span data-ttu-id="ca343-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ca343-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="ca343-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ca343-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="ca343-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ca343-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ca343-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ca343-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ca343-110">Dieser Artikel ist Teil des Bereitstellungshandbuchs und dient als Beispiel für ein Onboarding.</span><span class="sxs-lookup"><span data-stu-id="ca343-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="ca343-111">Im Thema [Planning](deployment-strategy.md) wurden verschiedene Methoden zum Onboarding von Geräten in den Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ca343-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="ca343-112">In diesem Thema wird die cloudeigene Architektur behandelt.</span><span class="sxs-lookup"><span data-stu-id="ca343-112">This topic covers the cloud-native architecture.</span></span> 

<span data-ttu-id="ca343-113">![Abbildung der cloudeigenen Architektur ](images/cloud-native-architecture.png)
 *Diagramm der Umgebungsarchitekturen*</span><span class="sxs-lookup"><span data-stu-id="ca343-113">![Image of cloud-native architecture](images/cloud-native-architecture.png)
*Diagram of environment architectures*</span></span>

<span data-ttu-id="ca343-114">Während Defender for Endpoint das Onboarding verschiedener Endpunkte und Tools unterstützt, werden diese in diesem Artikel nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="ca343-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="ca343-115">Informationen zum allgemeinen Onboarding mit anderen unterstützten Bereitstellungstools und -methoden finden Sie unter [Onboarding overview](onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="ca343-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>


<span data-ttu-id="ca343-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) ist eine Lösungsplattform, die mehrere Dienste vereint.</span><span class="sxs-lookup"><span data-stu-id="ca343-116">[Microsoft Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview) is a solution platform that unifies several services.</span></span> <span data-ttu-id="ca343-117">Es umfasst [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) für die cloudbasierte Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="ca343-117">It includes [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) for cloud-based device management.</span></span>


<span data-ttu-id="ca343-118">In diesem Thema werden Benutzer in den themen:</span><span class="sxs-lookup"><span data-stu-id="ca343-118">This topic guides users in:</span></span>
- <span data-ttu-id="ca343-119">Schritt 1: Onboarding von Geräten in den Dienst durch Erstellen einer Gruppe im Microsoft Endpoint Manager (MEM) zum Zuweisen von Konfigurationen für</span><span class="sxs-lookup"><span data-stu-id="ca343-119">Step 1: Onboarding devices to the service by creating a group in Microsoft Endpoint Manager (MEM) to assign configurations on</span></span>
- <span data-ttu-id="ca343-120">Schritt 2: Konfigurieren von Defender for Endpoint-Funktionen mithilfe von Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="ca343-120">Step 2: Configuring Defender for Endpoint capabilities using Microsoft Endpoint Manager</span></span>

<span data-ttu-id="ca343-121">In diesem Onboardingleitfaden werden Sie durch die folgenden grundlegenden Schritte geleitet, die Sie bei der Verwendung von Microsoft Endpoint Manager ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="ca343-121">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Manager:</span></span>

-   [<span data-ttu-id="ca343-122">Identifizieren von Zielgeräten oder Benutzern</span><span class="sxs-lookup"><span data-stu-id="ca343-122">Identifying target devices or users</span></span>](#identify-target-devices-or-users)

    -   <span data-ttu-id="ca343-123">Erstellen einer Azure Active Directory-Gruppe (Benutzer oder Gerät)</span><span class="sxs-lookup"><span data-stu-id="ca343-123">Creating an Azure Active Directory group (User or Device)</span></span>

-   [<span data-ttu-id="ca343-124">Erstellen eines Konfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="ca343-124">Creating a Configuration Profile</span></span>](#step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities)

    -   <span data-ttu-id="ca343-125">In Microsoft Endpoint Manager führen wir Sie beim Erstellen einer separaten Richtlinie für jede Funktion.</span><span class="sxs-lookup"><span data-stu-id="ca343-125">In Microsoft Endpoint Manager, we'll guide you in creating a separate policy for each capability.</span></span>





## <a name="resources"></a><span data-ttu-id="ca343-126">Ressourcen</span><span class="sxs-lookup"><span data-stu-id="ca343-126">Resources</span></span>


<span data-ttu-id="ca343-127">Hier sind die Links, die Sie für den Rest des Prozesses benötigen:</span><span class="sxs-lookup"><span data-stu-id="ca343-127">Here are the links you'll need for the rest of the process:</span></span>

-   [<span data-ttu-id="ca343-128">MEM-Portal</span><span class="sxs-lookup"><span data-stu-id="ca343-128">MEM portal</span></span>](https://aka.ms/memac)

-   [<span data-ttu-id="ca343-129">Security Center</span><span class="sxs-lookup"><span data-stu-id="ca343-129">Security Center</span></span>](https://securitycenter.windows.com/)

-   [<span data-ttu-id="ca343-130">Intune-Sicherheitsgrundwerte</span><span class="sxs-lookup"><span data-stu-id="ca343-130">Intune Security baselines</span></span>](https://docs.microsoft.com/mem/intune/protect/security-baseline-settings-defender-atp#microsoft-defender)

<span data-ttu-id="ca343-131">Weitere Informationen zu Microsoft Endpoint Manager finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="ca343-131">For more information about Microsoft Endpoint Manager, check out these resources:</span></span>
- [<span data-ttu-id="ca343-132">Microsoft Endpoint Manager-Seite</span><span class="sxs-lookup"><span data-stu-id="ca343-132">Microsoft Endpoint Manager page</span></span>](https://docs.microsoft.com/mem/)
- [<span data-ttu-id="ca343-133">Blogbeitrag zur Konvergenz von Intune und ConfigMgr</span><span class="sxs-lookup"><span data-stu-id="ca343-133">Blog post on convergence of Intune and ConfigMgr</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace/)
- [<span data-ttu-id="ca343-134">Einführungsvideo zu MEM</span><span class="sxs-lookup"><span data-stu-id="ca343-134">Introduction video on MEM</span></span>](https://www.microsoft.com/microsoft-365/blog/2019/11/04/use-the-power-of-cloud-intelligence-to-simplify-and-accelerate-it-and-the-move-to-a-modern-workplace)

## <a name="step-1-onboard-devices-by-creating-a-group-in-mem-to-assign-configurations-on"></a><span data-ttu-id="ca343-135">Schritt 1: Onboarding von Geräten durch Erstellen einer Gruppe in MEM zum Zuweisen von Konfigurationen für</span><span class="sxs-lookup"><span data-stu-id="ca343-135">Step 1: Onboard devices by creating a group in MEM to assign configurations on</span></span>
### <a name="identify-target-devices-or-users"></a><span data-ttu-id="ca343-136">Identifizieren von Zielgeräten oder Benutzern</span><span class="sxs-lookup"><span data-stu-id="ca343-136">Identify target devices or users</span></span>
<span data-ttu-id="ca343-137">In diesem Abschnitt erstellen wir eine Testgruppe zum Zuweisen Ihrer Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="ca343-137">In this section, we will create a test group to assign your configurations on.</span></span>

>[!NOTE]
><span data-ttu-id="ca343-138">Intune verwendet Azure Active Directory (Azure AD)-Gruppen zum Verwalten von Geräten und Benutzern.</span><span class="sxs-lookup"><span data-stu-id="ca343-138">Intune uses Azure Active Directory (Azure AD) groups to manage devices and users.</span></span> <span data-ttu-id="ca343-139">Als Intune-Administrator können Sie Gruppen entsprechend Ihren Organisatorischen Anforderungen einrichten.</span><span class="sxs-lookup"><span data-stu-id="ca343-139">As an Intune admin, you can set up groups to suit your organizational needs.</span></span><br>
<span data-ttu-id="ca343-140">Weitere Informationen finden Sie unter [Hinzufügen von Gruppen zum Organisieren von Benutzern und Geräten.](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)</span><span class="sxs-lookup"><span data-stu-id="ca343-140">For more information, see [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-a-group"></a><span data-ttu-id="ca343-141">Erstellen einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="ca343-141">Create a group</span></span>

1.  <span data-ttu-id="ca343-142">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="ca343-142">Open the MEM portal.</span></span>

2.  <span data-ttu-id="ca343-143">Öffnen **Sie Gruppen > Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="ca343-143">Open **Groups > New Group**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-144">![Abbildung des Microsoft Endpoint Manager-Portals1](images/66f724598d9c3319cba27f79dd4617a4.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-144">![Image of Microsoft Endpoint Manager portal1](images/66f724598d9c3319cba27f79dd4617a4.png)</span></span>

3.  <span data-ttu-id="ca343-145">Geben Sie Details ein, und erstellen Sie eine neue Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ca343-145">Enter details and create a new group.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-146">![Abbildung des Microsoft Endpoint Manager-Portals2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-146">![Image of Microsoft Endpoint Manager portal2](images/b1e0206d675ad07db218b63cd9b9abc3.png)</span></span>

4.  <span data-ttu-id="ca343-147">Fügen Sie Ihren Testbenutzer oder Ihr Gerät hinzu.</span><span class="sxs-lookup"><span data-stu-id="ca343-147">Add your test user or device.</span></span>

5.  <span data-ttu-id="ca343-148">Öffnen Sie **im Bereich > Alle Gruppen** ihre neue Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ca343-148">From the **Groups > All groups** pane, open your new group.</span></span>

6.  <span data-ttu-id="ca343-149">Wählen **Sie Mitglieder > Mitglieder hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-149">Select  **Members > Add members**.</span></span>

7.  <span data-ttu-id="ca343-150">Suchen Sie Den Testbenutzer oder Ihr Gerät, und wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="ca343-150">Find your test user or device and select it.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-151">![Abbildung des Microsoft Endpoint Manager-Portals3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-151">![Image of Microsoft Endpoint Manager portal3](images/149cbfdf221cdbde8159d0ab72644cd0.png)</span></span>

8.  <span data-ttu-id="ca343-152">Ihre Testgruppe hat nun ein Mitglied zum Testen.</span><span class="sxs-lookup"><span data-stu-id="ca343-152">Your testing group now has a member to test.</span></span>

## <a name="step-2-create-configuration-policies-to-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="ca343-153">Schritt 2: Erstellen von Konfigurationsrichtlinien zum Konfigurieren von Microsoft Defender for Endpoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="ca343-153">Step 2: Create configuration policies to configure Microsoft Defender for Endpoint capabilities</span></span>
<span data-ttu-id="ca343-154">Im folgenden Abschnitt erstellen Sie eine Reihe von Konfigurationsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ca343-154">In the following section, you'll create a number of configuration policies.</span></span>

<span data-ttu-id="ca343-155">Zunächst wird eine Konfigurationsrichtlinie verwendet, um auszuwählen, welche Benutzergruppen oder Geräte in Defender for Endpoint onboarded werden:</span><span class="sxs-lookup"><span data-stu-id="ca343-155">First is a configuration policy to select which groups of users or devices will be onboarded to Defender for Endpoint:</span></span>

- [<span data-ttu-id="ca343-156">Endpunkterkennung und -antwort</span><span class="sxs-lookup"><span data-stu-id="ca343-156">Endpoint detection and response</span></span>](#endpoint-detection-and-response) 

<span data-ttu-id="ca343-157">Anschließend erstellen Sie verschiedene Arten von Endpunktsicherheitsrichtlinien:</span><span class="sxs-lookup"><span data-stu-id="ca343-157">Then you will continue by creating several different types of endpoint security policies:</span></span>

- [<span data-ttu-id="ca343-158">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="ca343-158">Next-generation protection</span></span>](#next-generation-protection)
- [<span data-ttu-id="ca343-159">Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="ca343-159">Attack surface reduction</span></span>](#attack-surface-reduction--attack-surface-reduction-rules)

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="ca343-160">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ca343-160">Endpoint detection and response</span></span>

1.  <span data-ttu-id="ca343-161">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="ca343-161">Open the MEM portal.</span></span>

2.  <span data-ttu-id="ca343-162">Navigieren Sie **zu Endpoint security > Endpoint detection and response**.</span><span class="sxs-lookup"><span data-stu-id="ca343-162">Navigate to **Endpoint security > Endpoint detection and response**.</span></span> <span data-ttu-id="ca343-163">Klicken Sie auf **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ca343-163">Click on **Create Profile**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-164">![Abbildung des Microsoft Endpoint Manager-Portals4](images/58dcd48811147feb4ddc17212b7fe840.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-164">![Image of Microsoft Endpoint Manager portal4](images/58dcd48811147feb4ddc17212b7fe840.png)</span></span>

3.  <span data-ttu-id="ca343-165">Wählen **Sie unter Plattform windows 10 und höher Profil – Endpunkterkennung und -antwort > Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-165">Under **Platform, select Windows 10 and Later, Profile - Endpoint detection and response > Create**.</span></span>

4.  <span data-ttu-id="ca343-166">Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-166">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-167">![Abbildung des Microsoft Endpoint Manager-Portals5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-167">![Image of Microsoft Endpoint Manager portal5](images/a5b2d23bdd50b160fef4afd25dda28d4.png)</span></span>

5.  <span data-ttu-id="ca343-168">Wählen Sie die Einstellungen nach Bedarf aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-168">Select settings as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-169">![Abbildung des Microsoft Endpoint Manager-Portals6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-169">![Image of Microsoft Endpoint Manager portal6](images/cea7e288b5d42a9baf1aef0754ade910.png)</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca343-170">In dieser Instanz wurde dies automatisch aufgefüllt, da Defender for Endpoint bereits in Intune integriert wurde.</span><span class="sxs-lookup"><span data-stu-id="ca343-170">In this instance, this has been auto populated as Defender for Endpoint has already been integrated with Intune.</span></span> <span data-ttu-id="ca343-171">Weitere Informationen zur Integration finden Sie unter [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span><span class="sxs-lookup"><span data-stu-id="ca343-171">For more information on the integration, see [Enable Microsoft Defender for Endpoint in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-configure#to-enable-microsoft-defender-atp).</span></span>
    > 
    > <span data-ttu-id="ca343-172">Die folgende Abbildung ist ein Beispiel dafür, was Sie sehen werden, wenn Microsoft Defender for Endpoint NICHT in Intune integriert ist:</span><span class="sxs-lookup"><span data-stu-id="ca343-172">The following image is an example of what you'll see when Microsoft Defender for Endpoint is NOT integrated with Intune:</span></span>
    >
    > ![Abbildung des Microsoft Endpoint Manager-Portals7](images/2466460812371ffae2d19a10c347d6f4.png)

6.  <span data-ttu-id="ca343-174">Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-174">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-175">![Abbildung des Microsoft Endpoint Manager-Portals8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-175">![Image of Microsoft Endpoint Manager portal8](images/ef844f52ec2c0d737ce793f68b5e8408.png)</span></span>

7.  <span data-ttu-id="ca343-176">Fügen Sie test group hinzu, indem Sie **auf** Gruppen auswählen klicken, um Ihre Gruppe hinzuzufügen und auszuwählen, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-176">Add test group by clicking on **Select groups to include** and choose your group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-177">![Abbildung des Microsoft Endpoint Manager-Portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-177">![Image of Microsoft Endpoint Manager portal9](images/fc3525e20752da026ec9f46ab4fec64f.png)</span></span>

8.  <span data-ttu-id="ca343-178">Überprüfen und akzeptieren Sie, und wählen Sie **dann Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-178">Review and accept, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-179">![Abbildung des Microsoft Endpoint Manager-Portals10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-179">![Image of Microsoft Endpoint Manager portal10](images/289172dbd7bd34d55d24810d9d4d8158.png)</span></span>

9.  <span data-ttu-id="ca343-180">Sie können ihre abgeschlossene Richtlinie anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ca343-180">You can view your completed policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-181">![Abbildung des Microsoft Endpoint Manager-Portals11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-181">![Image of Microsoft Endpoint Manager portal11](images/5a568b6878be8243ea2b9d82d41ed297.png)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="ca343-182">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="ca343-182">Next-generation protection</span></span>

1.  <span data-ttu-id="ca343-183">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="ca343-183">Open the MEM portal.</span></span>

2.  <span data-ttu-id="ca343-184">Navigieren Sie **zu Endpoint security > Antivirus > Create Policy**.</span><span class="sxs-lookup"><span data-stu-id="ca343-184">Navigate to **Endpoint security > Antivirus > Create Policy**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-185">![Abbildung des Microsoft Endpoint Manager-Portals12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-185">![Image of Microsoft Endpoint Manager portal12](images/6b728d6e0d71108d768e368b416ff8ba.png)</span></span>

3.  <span data-ttu-id="ca343-186">Wählen **Sie Plattform – Windows 10 und höher – Windows und Profil – Microsoft Defender Antivirus > Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-186">Select **Platform - Windows 10 and Later - Windows and Profile – Microsoft Defender Antivirus > Create**.</span></span>

4.  <span data-ttu-id="ca343-187">Geben Sie Namen und Beschreibung ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-187">Enter name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-188">![Abbildung des Microsoft Endpoint Manager-Portals13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-188">![Image of Microsoft Endpoint Manager portal13](images/a7d738dd4509d65407b7d12beaa3e917.png)</span></span>

5.  <span data-ttu-id="ca343-189">Auf der **Seite Konfigurationseinstellungen:** Legen Sie die für Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection und Remediation) benötigten Konfigurationen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ca343-189">In the **Configuration settings page**: Set the configurations you require for Microsoft Defender Antivirus (Cloud Protection, Exclusions, Real-Time Protection, and Remediation).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-190">![Abbildung des Microsoft Endpoint Manager-Portals14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-190">![Image of Microsoft Endpoint Manager portal14](images/3840b1576d6f79a1d72eb14760ef5e8c.png)</span></span>

6.  <span data-ttu-id="ca343-191">Fügen Sie bei Bedarf Bereichstags hinzu, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-191">Add scope tags if necessary, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-192">![Abbildung des Microsoft Endpoint Manager-Portals15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-192">![Image of Microsoft Endpoint Manager portal15](images/2055e4f9b9141525c0eb681e7ba19381.png)</span></span>

7.  <span data-ttu-id="ca343-193">Wählen Sie Gruppen aus, die sie enthalten soll, weisen Sie ihrer Testgruppe zu, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-193">Select groups to include, assign to your test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-194">![Abbildung des Microsoft Endpoint Manager-Portals16](images/48318a51adee06bff3908e8ad4944dc9.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-194">![Image of Microsoft Endpoint Manager portal16](images/48318a51adee06bff3908e8ad4944dc9.png)</span></span>

8.  <span data-ttu-id="ca343-195">Überprüfen und erstellen, und wählen Sie **dann Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-195">Review and create, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-196">![Abbildung des Microsoft Endpoint Manager-Portals17](images/dfdadab79112d61bd3693d957084b0ec.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-196">![Image of Microsoft Endpoint Manager portal17](images/dfdadab79112d61bd3693d957084b0ec.png)</span></span>

9.  <span data-ttu-id="ca343-197">Sie sehen die von Ihnen erstellte Konfigurationsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="ca343-197">You'll see the configuration policy you created.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-198">![Abbildung des Microsoft Endpoint Manager-Portals18](images/38180219e632d6e4ec7bd25a46398da8.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-198">![Image of Microsoft Endpoint Manager portal18](images/38180219e632d6e4ec7bd25a46398da8.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="ca343-199">Attack Surface Reduction – Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="ca343-199">Attack Surface Reduction – Attack surface reduction rules</span></span>

1.  <span data-ttu-id="ca343-200">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="ca343-200">Open the MEM portal.</span></span>

2.  <span data-ttu-id="ca343-201">Navigieren Sie **zu Endpoint security > Attack surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="ca343-201">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="ca343-202">Wählen **Sie Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-202">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="ca343-203">Wählen **Sie Plattform – Windows 10 und höher – Profil – Attack surface reduction rules > Create aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-203">Select **Platform - Windows 10 and Later – Profile - Attack surface reduction rules > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-204">![Abbildung des Microsoft Endpoint Manager-Portals19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-204">![Image of Microsoft Endpoint Manager portal19](images/522d9bb4288dc9c1a957392b51384fdd.png)</span></span>

5.  <span data-ttu-id="ca343-205">Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-205">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-206">![Abbildung des Microsoft Endpoint Manager-Portals20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-206">![Image of Microsoft Endpoint Manager portal20](images/a5a71fd73ec389f3cdce6d1a6bd1ff31.png)</span></span>

6.  <span data-ttu-id="ca343-207">Wählen Sie **auf der Seite Konfigurationseinstellungen**: Festlegen der Konfigurationen, die Sie für Attack surface reduction rules benötigen, dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-207">In the **Configuration settings page**: Set the configurations you require for Attack surface reduction rules, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca343-208">Wir konfigurieren alle Attack surface reduction-Regeln auf Audit.</span><span class="sxs-lookup"><span data-stu-id="ca343-208">We will be configuring all of the Attack surface reduction rules to Audit.</span></span>
    > 
    > <span data-ttu-id="ca343-209">Weitere Informationen finden Sie unter [Attack surface reduction rules](attack-surface-reduction.md).</span><span class="sxs-lookup"><span data-stu-id="ca343-209">For more information, see [Attack surface reduction rules](attack-surface-reduction.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-210">![Abbildung des Microsoft Endpoint Manager-Portals21](images/dd0c00efe615a64a4a368f54257777d0.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-210">![Image of Microsoft Endpoint Manager portal21](images/dd0c00efe615a64a4a368f54257777d0.png)</span></span>

7.  <span data-ttu-id="ca343-211">Fügen Sie Bereichstags nach Bedarf hinzu, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-211">Add Scope Tags as required, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-212">![Abbildung des Microsoft Endpoint Manager-Portals22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-212">![Image of Microsoft Endpoint Manager portal22](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="ca343-213">Wählen Sie Gruppen aus, die einer Testgruppe zugewiesen werden, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-213">Select groups to include and assign to test group, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-214">![Abbildung des Microsoft Endpoint Manager-Portals23](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-214">![Image of Microsoft Endpoint Manager portal23](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9. <span data-ttu-id="ca343-215">Überprüfen Sie die Details, und wählen Sie **dann Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-215">Review the details, then select  **Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-216">![Abbildung des Microsoft Endpoint Manager-Portals24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-216">![Image of Microsoft Endpoint Manager portal24](images/2c2e87c5fedc87eba17be0cdeffdb17f.png)</span></span>

10. <span data-ttu-id="ca343-217">Anzeigen der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ca343-217">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-218">![Abbildung des Microsoft Endpoint Manager-Portals25](images/7a631d17cc42500dacad4e995823ffef.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-218">![Image of Microsoft Endpoint Manager portal25](images/7a631d17cc42500dacad4e995823ffef.png)</span></span>

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="ca343-219">Attack Surface Reduction – Web Protection</span><span class="sxs-lookup"><span data-stu-id="ca343-219">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="ca343-220">Öffnen Sie das MEM-Portal.</span><span class="sxs-lookup"><span data-stu-id="ca343-220">Open the MEM portal.</span></span>

2.  <span data-ttu-id="ca343-221">Navigieren Sie **zu Endpoint security > Attack surface reduction**.</span><span class="sxs-lookup"><span data-stu-id="ca343-221">Navigate to **Endpoint security > Attack surface reduction**.</span></span>

3.  <span data-ttu-id="ca343-222">Wählen **Sie Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-222">Select  **Create Policy**.</span></span>

4.  <span data-ttu-id="ca343-223">Wählen **Sie Windows 10 und höher – Webschutz > Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-223">Select **Windows 10 and Later – Web protection > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-224">![Abbildung des Microsoft Endpoint Manager-Portals26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-224">![Image of Microsoft Endpoint Manager portal26](images/cd7b5a1cbc16cc05f878cdc99ba4c27f.png)</span></span>

5.  <span data-ttu-id="ca343-225">Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-225">Enter a name and description, then select  **Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-226">![Abbildung des Microsoft Endpoint Manager-Portals27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-226">![Image of Microsoft Endpoint Manager portal27](images/5be573a60cd4fa56a86a6668b62dd808.png)</span></span>

6.  <span data-ttu-id="ca343-227">Wählen Sie **auf der Seite Konfigurationseinstellungen**: Legen Sie die für Web Protection benötigten Konfigurationen ein, und wählen Sie **dann Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-227">In the **Configuration settings page**: Set the configurations you require for Web Protection, then select  **Next**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca343-228">Wir konfigurieren Web Protection so, dass es blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="ca343-228">We are configuring Web Protection to Block.</span></span>
    > 
    > <span data-ttu-id="ca343-229">Weitere Informationen finden Sie unter [Web Protection](web-protection-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ca343-229">For more information, see [Web Protection](web-protection-overview.md).</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-230">![Abbildung des Microsoft Endpoint Manager-Portals28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-230">![Image of Microsoft Endpoint Manager portal28](images/6104aa33a56fab750cf30ecabef9f5b6.png)</span></span>

7.  <span data-ttu-id="ca343-231">Fügen **Sie Bereichstags wie erforderlich > Next hinzu.**</span><span class="sxs-lookup"><span data-stu-id="ca343-231">Add **Scope Tags as required > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-232">![Abbildung des Microsoft Endpoint Manager-Portals29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-232">![Image of Microsoft Endpoint Manager portal29](images/6daa8d347c98fe94a0d9c22797ff6f28.png)</span></span>

8.  <span data-ttu-id="ca343-233">Wählen **Sie Zuweisen zu Testgruppen > Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-233">Select **Assign to test group > Next**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-234">![Abbildung des Microsoft Endpoint Manager-Portals30](images/45cefc8e4e474321b4d47b4626346597.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-234">![Image of Microsoft Endpoint Manager portal30](images/45cefc8e4e474321b4d47b4626346597.png)</span></span>

9.  <span data-ttu-id="ca343-235">Wählen **Sie Überprüfen und Erstellen > Erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="ca343-235">Select **Review and Create > Create**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-236">![Abbildung des Microsoft Endpoint Manager-Portals31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-236">![Image of Microsoft Endpoint Manager portal31](images/8ee0405f1a96c23d2eb6f737f11c1ae5.png)</span></span>

10. <span data-ttu-id="ca343-237">Anzeigen der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ca343-237">View the policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-238">![Abbildung des Microsoft Endpoint Manager-Portals32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-238">![Image of Microsoft Endpoint Manager portal32](images/e74f6f6c150d017a286e6ed3dffb7757.png)</span></span>

## <a name="validate-configuration-settings"></a><span data-ttu-id="ca343-239">Überprüfen von Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ca343-239">Validate configuration settings</span></span>


### <a name="confirm-policies-have-been-applied"></a><span data-ttu-id="ca343-240">Bestätigen, dass Richtlinien angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="ca343-240">Confirm Policies have been applied</span></span>


<span data-ttu-id="ca343-241">Nachdem die Konfigurationsrichtlinie zugewiesen wurde, dauert es einige Zeit, bis sie angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ca343-241">Once the Configuration policy has been assigned, it will take some time to apply.</span></span>

<span data-ttu-id="ca343-242">Informationen zum Timing finden Sie unter [Intune-Konfigurationsinformationen](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span><span class="sxs-lookup"><span data-stu-id="ca343-242">For information on timing, see [Intune configuration information](https://docs.microsoft.com/mem/intune/configuration/device-profile-troubleshoot#how-long-does-it-take-for-devices-to-get-a-policy-profile-or-app-after-they-are-assigned).</span></span>

<span data-ttu-id="ca343-243">Führen Sie den folgenden Prozess für jede Konfigurationsrichtlinie aus, um zu bestätigen, dass die Konfigurationsrichtlinie auf Ihr Testgerät angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="ca343-243">To confirm that the configuration policy has been applied to your test device, follow the following process for each configuration policy.</span></span>

1.  <span data-ttu-id="ca343-244">Öffnen Sie das MEM-Portal, und navigieren Sie zu der relevanten Richtlinie, wie in den obigen Schritten gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca343-244">Open the MEM portal and navigate to the relevant policy as shown in the steps above.</span></span> <span data-ttu-id="ca343-245">Das folgende Beispiel zeigt die Schutzeinstellungen der nächsten Generation.</span><span class="sxs-lookup"><span data-stu-id="ca343-245">The following example shows the next generation protection settings.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-246">[![Abbildung des Microsoft Endpoint Manager-Portals33 ](images/43ab6aa74471ee2977e154a4a5ef2d39.png)](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-246">[ ![Image of Microsoft Endpoint Manager portal33](images/43ab6aa74471ee2977e154a4a5ef2d39.png) ](images/43ab6aa74471ee2977e154a4a5ef2d39.png#lightbox)</span></span>

2.  <span data-ttu-id="ca343-247">Wählen Sie die **Konfigurationsrichtlinie aus,** um den Richtlinienstatus anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="ca343-247">Select  the **Configuration Policy** to view the policy status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-248">[![Abbildung des Microsoft Endpoint Manager-Portals34 ](images/55ecaca0e4a022f0e29d45aeed724e6c.png)](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-248">[ ![Image of Microsoft Endpoint Manager portal34](images/55ecaca0e4a022f0e29d45aeed724e6c.png) ](images/55ecaca0e4a022f0e29d45aeed724e6c.png#lightbox)</span></span>

3.  <span data-ttu-id="ca343-249">Wählen  **Sie Gerätestatus aus,** um den Status zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ca343-249">Select  **Device Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-250">[![Abbildung des Microsoft Endpoint Manager-Portals35 ](images/18a50df62cc38749000dbfb48e9a4c9b.png)](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-250">[ ![Image of Microsoft Endpoint Manager portal35](images/18a50df62cc38749000dbfb48e9a4c9b.png) ](images/18a50df62cc38749000dbfb48e9a4c9b.png#lightbox)</span></span>

4.  <span data-ttu-id="ca343-251">Wählen  **Sie Benutzerstatus aus,** um den Status zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ca343-251">Select  **User Status** to see the status.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-252">[![Abbildung des Microsoft Endpoint Manager-Portals36 ](images/4e965749ff71178af8873bc91f9fe525.png)](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-252">[ ![Image of Microsoft Endpoint Manager portal36](images/4e965749ff71178af8873bc91f9fe525.png) ](images/4e965749ff71178af8873bc91f9fe525.png#lightbox)</span></span>

5.  <span data-ttu-id="ca343-253">Wählen  **Sie Status pro Einstellung aus,** um den Status zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ca343-253">Select  **Per-setting status** to see the status.</span></span>

    >[!TIP]
    ><span data-ttu-id="ca343-254">Diese Ansicht ist sehr nützlich, um Einstellungen zu identifizieren, die mit einer anderen Richtlinie in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="ca343-254">This view is very useful to identify any settings that conflict with another policy.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-255">[![Abbildung des Microsoft Endpoint Manager-Portals37 ](images/42acc69d0128ed09804010bdbdf0a43c.png)](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-255">[ ![Image of Microsoft Endpoint Manager portal37](images/42acc69d0128ed09804010bdbdf0a43c.png) ](images/42acc69d0128ed09804010bdbdf0a43c.png#lightbox)</span></span>

### <a name="endpoint-detection-and-response"></a><span data-ttu-id="ca343-256">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ca343-256">Endpoint detection and response</span></span>


1.  <span data-ttu-id="ca343-257">Vor dem Anwenden der Konfiguration sollte der Defender for Endpoint Protection-Dienst nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ca343-257">Before applying the configuration, the Defender for Endpoint Protection service should not be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-258">[![Abbildung des Dienstbereichs1 ](images/b418a232a12b3d0a65fc98248dbb0e31.png)](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-258">[ ![Image of Services panel1](images/b418a232a12b3d0a65fc98248dbb0e31.png) ](images/b418a232a12b3d0a65fc98248dbb0e31.png#lightbox)</span></span>

2.  <span data-ttu-id="ca343-259">Nachdem die Konfiguration angewendet wurde, sollte der Defender for Endpoint Protection Service gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="ca343-259">After the configuration has been applied, the Defender for Endpoint Protection Service should be started.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-260">[![Abbildung des Dienstbereichs2 ](images/a621b699899f1b41db211170074ea59e.png)](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-260">[ ![Image of Services panel2](images/a621b699899f1b41db211170074ea59e.png) ](images/a621b699899f1b41db211170074ea59e.png#lightbox)</span></span>

3.  <span data-ttu-id="ca343-261">Nachdem die Dienste auf dem Gerät ausgeführt wurden, wird das Gerät im Microsoft Defender Security Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca343-261">After the services are running on the device, the device appears in Microsoft Defender Security Center.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-262">[![Abbildung von Microsoft Defender Security Center ](images/df0c64001b9219cfbd10f8f81a273190.png)](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ca343-262">[ ![Image of Microsoft Defender Security Center](images/df0c64001b9219cfbd10f8f81a273190.png) ](images/df0c64001b9219cfbd10f8f81a273190.png#lightbox)</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="ca343-263">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="ca343-263">Next-generation protection</span></span>

1.  <span data-ttu-id="ca343-264">Bevor Sie die Richtlinie auf ein Testgerät anwenden, sollten Sie die Einstellungen wie unten gezeigt manuell verwalten können.</span><span class="sxs-lookup"><span data-stu-id="ca343-264">Before applying the policy on a test device, you should be able to manually manage the settings as shown below.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-265">![Abbildung der Einstellung Seite1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-265">![Image of setting page1](images/88efb4c3710493a53f2840c3eac3e3d3.png)</span></span>

2.  <span data-ttu-id="ca343-266">Nachdem die Richtlinie angewendet wurde, sollten Sie die Einstellungen nicht manuell verwalten können.</span><span class="sxs-lookup"><span data-stu-id="ca343-266">After the policy has been applied, you should not be able to manually manage the settings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ca343-267">In der folgenden Abbildung **werden der in der Cloud** übermittelte Schutz und der **Echtzeitschutz** aktivieren als verwaltet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ca343-267">In the following image **Turn on cloud-delivered protection** and **Turn on real-time protection** are being shown as managed.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ca343-268">![Abbildung der Einstellung Seite2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span><span class="sxs-lookup"><span data-stu-id="ca343-268">![Image of setting page2](images/9341428b2d3164ca63d7d4eaa5cff642.png)</span></span>

### <a name="attack-surface-reduction--attack-surface-reduction-rules"></a><span data-ttu-id="ca343-269">Attack Surface Reduction – Regeln zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="ca343-269">Attack Surface Reduction – Attack surface reduction rules</span></span>


1.  <span data-ttu-id="ca343-270">Bevor Sie die Richtlinie auf ein Testgerät anwenden, geben Sie ein PowerShell-Fenster ein, und geben Sie ein `Get-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="ca343-270">Before applying the policy on a test device, pen a PowerShell Window and type `Get-MpPreference`.</span></span>

2.  <span data-ttu-id="ca343-271">Dies sollte mit den folgenden Zeilen ohne Inhalt antworten:</span><span class="sxs-lookup"><span data-stu-id="ca343-271">This should respond with the following lines with no content:</span></span>

    > <span data-ttu-id="ca343-272">AttackSurfaceReductionOnlyExclusions:</span><span class="sxs-lookup"><span data-stu-id="ca343-272">AttackSurfaceReductionOnlyExclusions:</span></span>
    > 
    > <span data-ttu-id="ca343-273">AttackSurfaceReductionRules_Actions:</span><span class="sxs-lookup"><span data-stu-id="ca343-273">AttackSurfaceReductionRules_Actions:</span></span>
    > 
    > <span data-ttu-id="ca343-274">AttackSurfaceReductionRules_Ids:</span><span class="sxs-lookup"><span data-stu-id="ca343-274">AttackSurfaceReductionRules_Ids:</span></span>

    ![Abbildung der Befehlszeile1](images/cb0260d4b2636814e37eee427211fe71.png)

3.  <span data-ttu-id="ca343-276">Öffnen Sie nach dem Anwenden der Richtlinie auf ein Testgerät ein PowerShell-Windows, und geben Sie `Get-MpPreference` ein.</span><span class="sxs-lookup"><span data-stu-id="ca343-276">After applying the policy on a test device, open a PowerShell Windows and type `Get-MpPreference`.</span></span>

4.  <span data-ttu-id="ca343-277">Dies sollte mit den folgenden Zeilen mit Inhalten wie unten gezeigt reagieren:</span><span class="sxs-lookup"><span data-stu-id="ca343-277">This should respond with the following lines with content as shown below:</span></span>

    ![Abbildung der Befehlszeile2](images/619fb877791b1fc8bc7dfae1a579043d.png)

### <a name="attack-surface-reduction--web-protection"></a><span data-ttu-id="ca343-279">Attack Surface Reduction – Web Protection</span><span class="sxs-lookup"><span data-stu-id="ca343-279">Attack Surface Reduction – Web Protection</span></span>

1.  <span data-ttu-id="ca343-280">Öffnen Sie auf dem Testgerät ein PowerShell-Windows, und geben Sie `(Get-MpPreference).EnableNetworkProtection` ein.</span><span class="sxs-lookup"><span data-stu-id="ca343-280">On the test device, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

2.  <span data-ttu-id="ca343-281">Dies sollte wie unten gezeigt mit 0 antworten.</span><span class="sxs-lookup"><span data-stu-id="ca343-281">This should respond with a 0 as shown below.</span></span>

    ![Abbildung der Befehlszeile3](images/196a8e194ac99d84221f405d0f684f8c.png)

3.  <span data-ttu-id="ca343-283">Öffnen Sie nach dem Anwenden der Richtlinie ein PowerShell-Windows, und geben Sie `(Get-MpPreference).EnableNetworkProtection` ein.</span><span class="sxs-lookup"><span data-stu-id="ca343-283">After applying the policy, open a PowerShell Windows and type `(Get-MpPreference).EnableNetworkProtection`.</span></span>

4.  <span data-ttu-id="ca343-284">Dies sollte wie unten gezeigt mit 1 antworten.</span><span class="sxs-lookup"><span data-stu-id="ca343-284">This should respond with a 1 as shown below.</span></span>

    ![Abbildung der Befehlszeile4](images/c06fa3bbc2f70d59dfe1e106cd9a4683.png)
