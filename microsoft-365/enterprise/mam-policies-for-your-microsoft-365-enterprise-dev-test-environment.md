---
title: Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Verwenden Sie diese Test Umgebungs Anleitung zum Hinzufügen von InTune-Geräte Konformitätsrichtlinien zu Ihrer Microsoft 365 for Enterprise-Testumgebung.
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487412"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="07dbf-103">Geräte Konformitätsrichtlinien für Ihre Microsoft 365 für Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="07dbf-103">Device compliance policies for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="07dbf-104">*Diese Test Umgebungs Anleitung kann nur für Microsoft 365 für Enterprise-Testumgebungen verwendet werden.*</span><span class="sxs-lookup"><span data-stu-id="07dbf-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="07dbf-105">In diesem Artikel wird beschrieben, wie Sie der Microsoft 365 für Enterprise-Testumgebung eine InTune-Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte und Microsoft 365-Apps für Enterprise hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="07dbf-105">This article describes how to add an Intune device compliance policy for Windows 10 devices and Microsoft 365 Apps for enterprise to your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="07dbf-106">Das Hinzufügen einer InTune-Geräte Konformitätsrichtlinie umfasst zwei Phasen:</span><span class="sxs-lookup"><span data-stu-id="07dbf-106">Adding an Intune device compliance policy involves two phases:</span></span>
- [<span data-ttu-id="07dbf-107">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="07dbf-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="07dbf-108">Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="07dbf-108">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Testumgebungsanleitungen für die Microsoft-Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="07dbf-110">Eine visuelle Zuordnung zu allen Artikeln im Microsoft 365 for Enterprise Test Lab Guide Stack finden Sie unter [Microsoft 365 for Enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="07dbf-110">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="07dbf-111">Phase 1: Erstellen der Testumgebung für Microsoft 365 für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="07dbf-111">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="07dbf-112">Wenn Sie MAM-Richtlinien nur auf einfache Weise mit den Mindestanforderungen konfigurieren möchten, befolgen Sie die Anweisungen unter [Lightweight Base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="07dbf-112">If you want to configure MAM policies in only a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="07dbf-113">Wenn Sie MAM-Richtlinien in einem simulierten Unternehmen konfigurieren möchten, befolgen Sie die Anweisungen unter [Pass-Through-Authentifizierung](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="07dbf-113">If you want to configure MAM policies in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="07dbf-114">Für das Testen der automatisierten Lizenzierung und der Gruppenmitgliedschaft ist keine simulierte Enterprise-Testumgebung erforderlich, die ein simuliertes, mit dem Internet verbundenes Intranet und eine Verzeichnissynchronisierung für eine Active Directory-Domänendienste (AD DS) Gesamtstruktur umfasst.</span><span class="sxs-lookup"><span data-stu-id="07dbf-114">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="07dbf-115">Er wird hier als Option bereitgestellt, damit Sie die automatisierte Lizenzierung und Gruppenmitgliedschaft testen und in einer Umgebung experimentieren können, die eine typische Organisation darstellt.</span><span class="sxs-lookup"><span data-stu-id="07dbf-115">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a><span data-ttu-id="07dbf-116">Phase 2: Erstellen einer Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte</span><span class="sxs-lookup"><span data-stu-id="07dbf-116">Phase 2: Create a device compliance policy for Windows 10 devices</span></span>

<span data-ttu-id="07dbf-117">Erstellen Sie in dieser Phase eine Geräte Kompatibilitäts Richtlinie für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="07dbf-117">In this phase, create a device compliance policy for Windows 10 devices.</span></span>
  
1. <span data-ttu-id="07dbf-118">Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com) , und melden Sie sich bei Ihrem Microsoft 365 Test Lab-Abonnement mit ihrem globalen Administratorkonto an.</span><span class="sxs-lookup"><span data-stu-id="07dbf-118">Go to the [Microsoft 365 admin center](https://admin.microsoft.com) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
1. <span data-ttu-id="07dbf-119">Öffnen Sie auf einer neuen Registerkarte Ihres Browsers das Azure-Portal unter [https://portal.azure.com](https://portal.azure.com) .</span><span class="sxs-lookup"><span data-stu-id="07dbf-119">On a new tab of your browser, open the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
1. <span data-ttu-id="07dbf-120">Geben Sie im Suchfeld des Azure-Portals **InTune**ein, und wählen Sie dann **InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-120">In the search box of the Azure portal, enter **Intune**, and then select **Intune**.</span></span>
1. <span data-ttu-id="07dbf-121">Wenn Sie im Bereich " **Microsoft InTune** " die Meldung " **Geräteverwaltung noch nicht aktiviert** " angezeigt haben, wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-121">If you see a **You haven't enabled device management yet** message in the **Microsoft Intune** pane, select it.</span></span> <span data-ttu-id="07dbf-122">Wählen Sie im Bereich **Verwaltung mobiler Geräte** die Option **InTune-MDM-Autorität**aus, und wählen Sie dann auswählen aus. **Choose**</span><span class="sxs-lookup"><span data-stu-id="07dbf-122">In the **Mobile Device Management authority** pane, select **Intune MDM Authority**, and then select **Choose**.</span></span>
1. <span data-ttu-id="07dbf-123">Aktualisieren Sie die Registerkarte Browser.</span><span class="sxs-lookup"><span data-stu-id="07dbf-123">Refresh your browser tab.</span></span>
1. <span data-ttu-id="07dbf-124">Wählen Sie im linken Navigationsbereich **Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-124">In the left navigation pane, select **Groups**.</span></span>
1. <span data-ttu-id="07dbf-125">Wählen Sie im Bereich **Gruppen-alle Gruppen** die Option **+ neue Gruppe**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-125">In the **Groups-All groups** pane, select **+ New Group**.</span></span>
1. <span data-ttu-id="07dbf-126">Wählen Sie im Bereich **Gruppe** die Option **Microsoft 365** oder **Sicherheit** für **Gruppentyp?**, geben Sie **verwaltete Windows 10-Geräte Benutzer** unter **Name**ein, wählen Sie **zugewiesen** in **Mitgliedschafts**aus, und wählen Sie dann **Erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-126">In the **Group** pane, select **Microsoft 365** or **Security** for **Group type?**, enter **Managed Windows 10 device users** in **Name**, select **Assigned** in **Membership type**,  and then select **Create**.</span></span>
1. <span data-ttu-id="07dbf-127">Wählen Sie **Microsoft InTune**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-127">Select **Microsoft Intune**.</span></span>
1. <span data-ttu-id="07dbf-128">Wählen Sie im Bereich **Microsoft InTune** in der Liste **Quick Tasks** die Option **Compliance Policy erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-128">In the **Microsoft Intune** pane, in the **Quick tasks** list, select **Create a compliance policy**.</span></span>
1. <span data-ttu-id="07dbf-129">Wählen Sie im Bereich **Konformitätsrichtlinien profile** die Option **Richtlinie erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-129">In the **Compliance Policy Profiles** pane, select **Create Policy**.</span></span>
1. <span data-ttu-id="07dbf-130">Geben Sie im Bereich **Richtlinie erstellen** unter **Name den Namen** **Windows 10**ein.</span><span class="sxs-lookup"><span data-stu-id="07dbf-130">In the **Create Policy** pane, in **Name**, enter **Windows 10**.</span></span> <span data-ttu-id="07dbf-131">Wählen Sie unter **Plattform**die Option **Windows 10 und höher**aus, wählen Sie im Bereich **Windows 10-Konformitätsrichtlinie** die Option **OK** aus, und wählen Sie dann **Erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-131">In **Platform**, select **Windows 10 and later**, select **OK** in the **Windows 10 compliance policy** pane, and then select **Create**.</span></span>
1. <span data-ttu-id="07dbf-132">Wählen Sie **Konformitätsrichtlinien profile**aus, und wählen Sie dann den Richtliniennamen **Windows 10** aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-132">Select **Compliance Policy Profiles**, and then select the **Windows 10** policy name.</span></span>
1. <span data-ttu-id="07dbf-133">Wählen Sie im Fensterbereich von **Windows 10** die Option **Zuweisungen**aus, und wählen Sie dann **einzubeziehende Gruppen**auswählen aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-133">In the **Windows 10** pane, select **Assignments**, and then select **Select groups to include**.</span></span>
1. <span data-ttu-id="07dbf-134">Wählen Sie im Bereich **einzubeziehende Gruppen auswählen** die Gruppe **verwaltete Windows 10-Geräte Benutzer** aus, und wählen Sie dann **auswählen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-134">In the **Select groups to include** pane, select the **Managed Windows 10 device users** group, and then select **Select**.</span></span>
1. <span data-ttu-id="07dbf-135">Wählen Sie **Speichern**aus, wählen Sie **Microsoft InTune-Übersicht**aus, und wählen Sie dann im linken Navigationsbereich **Client-apps** aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-135">Select **Save**, select **Microsoft Intune-Overview**, and then select **Client apps** in the left navigation.</span></span>
1. <span data-ttu-id="07dbf-136">Wählen Sie im Bereich **Client apps** die Option **apps**aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-136">In the **Client Apps** pane, select **Apps**, and then select **Add**.</span></span>
1. <span data-ttu-id="07dbf-137">Wählen Sie im Bereich **app hinzufügen** die Option **App-Typ**aus, und wählen Sie dann **Windows 10** unter **Microsoft 365 Suite**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-137">In the **Add app** pane, select **App type**, and then select **Windows 10** under **Microsoft 365 Suite**.</span></span>
1. <span data-ttu-id="07dbf-138">Wählen Sie im Bereich **app hinzufügen** die Option **App Suite-Informationen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-138">In the **Add App** pane, select **App Suite Information**.</span></span>
1. <span data-ttu-id="07dbf-139">Geben Sie im Bereich **Informationen zur APP-Suite** **Microsoft 365 apps for Enterprise** in **Suite Name** und **Suite Description**ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-139">In the **App Suite Information** pane, enter **Microsoft 365 Apps for enterprise** in both **Suite Name** and **Suite Description**, and then select **OK**.</span></span>
1. <span data-ttu-id="07dbf-140">Wählen Sie im Bereich **app hinzufügen** die Option **App Suite konfigurieren**aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-140">In the **Add App** pane, select **Configure App Suite**, and then select **OK**.</span></span>
1. <span data-ttu-id="07dbf-141">Wählen Sie im Bereich **app hinzufügen** die Option **App Suite Settings**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-141">In the **Add App** pane, select **App Suite Settings**.</span></span>
1. <span data-ttu-id="07dbf-142">Wählen Sie für **Update Kanal** **halbjährliche Enterprise**aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-142">For **Update Channel**, select **Semi-Annual Enterprise**, and then select **OK**.</span></span>
1. <span data-ttu-id="07dbf-143">Wählen Sie im Bereich **app hinzufügen** die Option **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="07dbf-143">In the **Add app** pane, select **Add**.</span></span>

<span data-ttu-id="07dbf-144">Sie verfügen nun über eine Geräte Kompatibilitäts Richtlinie zum Testen der ausgewählten apps in der **Windows 10** -Geräte Kompatibilitäts Richtlinie und für Mitglieder der **verwalteten Windows 10-Geräte Benutzer** Gruppe.</span><span class="sxs-lookup"><span data-stu-id="07dbf-144">You now have a device compliance policy for testing the selected apps in the **Windows 10** device compliance policy and for members of the **Managed Windows 10 device users** group.</span></span> <span data-ttu-id="07dbf-145">Beachten Sie, dass beim Auswählen von **Microsoft 365** als Gruppentyp zusätzliche Ressourcen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="07dbf-145">Please note that selecting **Microsoft 365** as the group type creates additional resources.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="07dbf-146">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="07dbf-146">Next step</span></span>

<span data-ttu-id="07dbf-147">Untersuchen Sie weitere Features und Funktionen zur [Verwaltung mobiler Geräte](m365-enterprise-test-lab-guides.md#mobile-device-management) in Ihrer Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="07dbf-147">Explore additional [mobile device management](m365-enterprise-test-lab-guides.md#mobile-device-management) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="07dbf-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07dbf-148">See also</span></span>

<span data-ttu-id="07dbf-149">[Microsoft 365 for Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span><span class="sxs-lookup"><span data-stu-id="07dbf-149">[Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
[<span data-ttu-id="07dbf-150">Registrieren von IOS-und Android-Geräten in Ihrer Microsoft 365 for Enterprise-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="07dbf-150">Enroll iOS and Android devices in your Microsoft 365 for enterprise test environment</span></span>](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[<span data-ttu-id="07dbf-151">Übersicht über Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="07dbf-151">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="07dbf-152">Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="07dbf-152">Enterprise Mobility + Security (EMS)</span></span>](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
