---
title: Konfigurieren von Warnungsbenachrichtigungen in Microsoft Defender für Endpunkt
description: Sie können Microsoft Defender für Endpunkt verwenden, um E-Mail-Benachrichtigungseinstellungen für Sicherheitswarnungen basierend auf dem Schweregrad und anderen Kriterien zu konfigurieren.
keywords: E-Mail-Benachrichtigungen, Warnungsbenachrichtigungen konfigurieren, Microsoft Defender für Endpunkt, Microsoft Defender für Endpunktbenachrichtigungen, Windows 10 Enterprise, Windows 10 Education
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2b638742e29d5ca0a8b74adfa6796380114d24a3
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339502"
---
# <a name="configure-alert-notifications-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="bc9b8-104">Konfigurieren von Warnungsbenachrichtigungen in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bc9b8-104">Configure alert notifications in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc9b8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bc9b8-105">**Applies to:**</span></span>
- [<span data-ttu-id="bc9b8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bc9b8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="bc9b8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bc9b8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bc9b8-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="bc9b8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="bc9b8-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="bc9b8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-emailconfig-abovefoldlink)

<span data-ttu-id="bc9b8-110">Sie können Defender für Endpunkt so konfigurieren, dass E-Mail-Benachrichtigungen an angegebene Empfänger für neue Warnungen gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-110">You can configure Defender for Endpoint to send email notifications to specified recipients for new alerts.</span></span> <span data-ttu-id="bc9b8-111">Mit diesem Feature können Sie eine Gruppe von Personen identifizieren, die sofort informiert werden und basierend auf ihrem Schweregrad auf Warnungen reagieren können.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-111">This feature enables you to identify a group of individuals who will immediately be informed and can act on alerts based on their severity.</span></span>

> [!NOTE]
> <span data-ttu-id="bc9b8-112">Nur Benutzer mit berechtigungen zum Verwalten von Sicherheitseinstellungen können E-Mail-Benachrichtigungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-112">Only users with 'Manage security settings' permissions can configure email notifications.</span></span> <span data-ttu-id="bc9b8-113">Wenn Sie die grundlegende Berechtigungsverwaltung verwendet haben, können Benutzer mit Sicherheitsadministrator- oder globalen Administratorrollen E-Mail-Benachrichtigungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-113">If you've chosen to use basic permissions management, users with Security Administrator or Global Administrator roles can configure email notifications.</span></span>

<span data-ttu-id="bc9b8-114">Sie können die Warnungsschweregrade festlegen, die Benachrichtigungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-114">You can set the alert severity levels that trigger notifications.</span></span> <span data-ttu-id="bc9b8-115">Sie können auch Empfänger der E-Mail-Benachrichtigung hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-115">You can also add or remove recipients of the email notification.</span></span> <span data-ttu-id="bc9b8-116">Neue Empfänger werden über Warnungen benachrichtigt, die ausgelöst werden, nachdem sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-116">New recipients get notified about alerts triggered after they're added.</span></span> <span data-ttu-id="bc9b8-117">Weitere Informationen zu Warnungen finden Sie unter [Anzeigen und Organisieren der Warnungswarteschlange.](alerts-queue.md)</span><span class="sxs-lookup"><span data-stu-id="bc9b8-117">For more information about alerts, see [View and organize the Alerts queue](alerts-queue.md).</span></span>

<span data-ttu-id="bc9b8-118">Wenn Sie die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) verwenden, erhalten Empfänger nur Benachrichtigungen basierend auf den Gerätegruppen, die in der Benachrichtigungsregel konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-118">If you're using role-based access control (RBAC), recipients will only receive notifications based on the device groups that were configured in the notification rule.</span></span>
<span data-ttu-id="bc9b8-119">Benutzer mit der richtigen Berechtigung können nur Benachrichtigungen erstellen, bearbeiten oder löschen, die auf ihren Gerätegruppenverwaltungsbereich beschränkt sind.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-119">Users with the proper permission can only create, edit, or delete notifications that are limited to their device group management scope.</span></span>
<span data-ttu-id="bc9b8-120">Nur Benutzer, die der Rolle "Globaler Administrator" zugewiesen sind, können Benachrichtigungsregeln verwalten, die für alle Gerätegruppen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-120">Only users assigned to the Global administrator role can manage notification rules that are configured for all device groups.</span></span>

<span data-ttu-id="bc9b8-121">Die E-Mail-Benachrichtigung enthält grundlegende Informationen zu der Warnung und einen Link zum Portal, in dem Sie weitere Untersuchungen durchführen können.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-121">The email notification includes basic information about the alert and a link to the portal where you can do further investigation.</span></span>

## <a name="create-rules-for-alert-notifications"></a><span data-ttu-id="bc9b8-122">Erstellen von Regeln für Warnungsbenachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="bc9b8-122">Create rules for alert notifications</span></span>
<span data-ttu-id="bc9b8-123">Sie können Regeln erstellen, die die Geräte und Warnungsschweregrade zum Senden von E-Mail-Benachrichtigungen für und die Benachrichtigungsempfänger bestimmen.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-123">You can create rules that determine the devices and alert severities to send email notifications for and the notification recipients.</span></span>


1. <span data-ttu-id="bc9b8-124">Wählen Sie im Navigationsbereich **Einstellungen**  >    >  **Endpunkte Allgemeine**  >  **E-Mail-Benachrichtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-124">In the navigation pane, select **Settings** > **Endpoints** > **General** > **Email notifications**.</span></span>

2. <span data-ttu-id="bc9b8-125">Klicken Sie auf **"Element hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="bc9b8-125">Click **Add item**.</span></span>

3. <span data-ttu-id="bc9b8-126">Geben Sie die allgemeinen Informationen an:</span><span class="sxs-lookup"><span data-stu-id="bc9b8-126">Specify the General information:</span></span>
    - <span data-ttu-id="bc9b8-127">**Regelname** : Geben Sie einen Namen für die Benachrichtigungsregel an.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-127">**Rule name** - Specify a name for the notification rule.</span></span>
    - <span data-ttu-id="bc9b8-128">**Organisationsname einschließen** – Geben Sie den Kundennamen an, der in der E-Mail-Benachrichtigung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-128">**Include organization name** - Specify the customer name that appears on the email notification.</span></span>
    - <span data-ttu-id="bc9b8-129">**Mandantenspezifischer Portallink** einschließen – Fügt einen Link mit der Mandanten-ID hinzu, um den Zugriff auf einen bestimmten Mandanten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-129">**Include tenant-specific portal link** - Adds a link with the tenant ID to allow access to a specific tenant.</span></span>
    - <span data-ttu-id="bc9b8-130">**Geräteinformationen einschließen** – Enthält den Gerätenamen im E-Mail-Warnungstext.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-130">**Include device information** - Includes the device name in the email alert body.</span></span>

        > [!NOTE]
        > <span data-ttu-id="bc9b8-131">Diese Informationen werden möglicherweise von Empfänger-E-Mail-Servern verarbeitet, die sich nicht an dem geografischen Standort befinden, den Sie für Ihre Defender für Endpunkt-Daten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-131">This information might be processed by recipient mail servers that ar not in the geographic location you have selected for your Defender for Endpoint data.</span></span>

    - <span data-ttu-id="bc9b8-132">**Geräte** – Wählen Sie aus, ob Empfänger bei Warnungen auf allen Geräten benachrichtigt werden sollen (nur globale Administratorrolle) oder in ausgewählten Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-132">**Devices** - Choose whether to notify recipients for alerts on all devices (Global administrator role only) or on selected device groups.</span></span> <span data-ttu-id="bc9b8-133">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Gerätegruppen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="bc9b8-133">For more information, see [Create and manage device groups](machine-groups.md).</span></span>
    - <span data-ttu-id="bc9b8-134">**Warnungsschweregrad** – Wählen Sie den Warnungsschweregrad aus.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-134">**Alert severity** - Choose the alert severity level.</span></span>

4. <span data-ttu-id="bc9b8-135">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-135">Click **Next**.</span></span>

5. <span data-ttu-id="bc9b8-136">Geben Sie die E-Mail-Adresse des Empfängers ein, und klicken Sie dann auf **"Empfänger hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="bc9b8-136">Enter the recipient's email address then click **Add recipient**.</span></span> <span data-ttu-id="bc9b8-137">Sie können mehrere E-Mail-Adressen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-137">You can add multiple email addresses.</span></span>

6. <span data-ttu-id="bc9b8-138">Überprüfen Sie, ob E-Mail-Empfänger die E-Mail-Benachrichtigungen erhalten können, indem Sie **"Test-E-Mail senden"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-138">Check that email recipients can receive the email notifications by selecting **Send test email**.</span></span>

7. <span data-ttu-id="bc9b8-139">Klicken Sie auf **"Benachrichtigungsregel speichern".**</span><span class="sxs-lookup"><span data-stu-id="bc9b8-139">Click **Save notification rule**.</span></span>

## <a name="edit-a-notification-rule"></a><span data-ttu-id="bc9b8-140">Bearbeiten einer Benachrichtigungsregel</span><span class="sxs-lookup"><span data-stu-id="bc9b8-140">Edit a notification rule</span></span>

1. <span data-ttu-id="bc9b8-141">Wählen Sie die Benachrichtigungsregel aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-141">Select the notification rule you'd like to edit.</span></span>

2. <span data-ttu-id="bc9b8-142">Aktualisieren Sie die Registerkarteninformationen "Allgemein" und "Empfänger".</span><span class="sxs-lookup"><span data-stu-id="bc9b8-142">Update the General and Recipient tab information.</span></span>

3. <span data-ttu-id="bc9b8-143">Klicken Sie auf **"Benachrichtigungsregel speichern".**</span><span class="sxs-lookup"><span data-stu-id="bc9b8-143">Click **Save notification rule**.</span></span>

## <a name="delete-notification-rule"></a><span data-ttu-id="bc9b8-144">Benachrichtigungsregel löschen</span><span class="sxs-lookup"><span data-stu-id="bc9b8-144">Delete notification rule</span></span>

1. <span data-ttu-id="bc9b8-145">Wählen Sie die Benachrichtigungsregel aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-145">Select the notification rule you'd like to delete.</span></span>

2. <span data-ttu-id="bc9b8-146">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-146">Click **Delete**.</span></span>

## <a name="troubleshoot-email-notifications-for-alerts"></a><span data-ttu-id="bc9b8-147">Problembehandlung bei E-Mail-Benachrichtigungen für Warnungen</span><span class="sxs-lookup"><span data-stu-id="bc9b8-147">Troubleshoot email notifications for alerts</span></span>

<span data-ttu-id="bc9b8-148">In diesem Abschnitt werden verschiedene Probleme aufgeführt, die bei der Verwendung von E-Mail-Benachrichtigungen für Warnungen auftreten können.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-148">This section lists various issues that you may encounter when using email notifications for alerts.</span></span>

<span data-ttu-id="bc9b8-149">**Problem:** Beabsichtigte Empfänger melden, dass sie die Benachrichtigungen nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-149">**Problem:** Intended recipients report they're not getting the notifications.</span></span>

<span data-ttu-id="bc9b8-150">**Lösung:** Stellen Sie sicher, dass die Benachrichtigungen nicht durch E-Mail-Filter blockiert werden:</span><span class="sxs-lookup"><span data-stu-id="bc9b8-150">**Solution:** Make sure that the notifications aren't blocked by email filters:</span></span>

1. <span data-ttu-id="bc9b8-151">Überprüfen Sie, ob die Defender für Endpunkt-E-Mail-Benachrichtigungen nicht an den Junk-E-Mail-Ordner gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-151">Check that the Defender for Endpoint email notifications aren't sent to the Junk Email folder.</span></span> <span data-ttu-id="bc9b8-152">Markieren Sie sie als "Nicht junk".</span><span class="sxs-lookup"><span data-stu-id="bc9b8-152">Mark them as Not junk.</span></span>
2. <span data-ttu-id="bc9b8-153">Überprüfen Sie, ob Ihr E-Mail-Sicherheitsprodukt die E-Mail-Benachrichtigungen von Defender für Endpunkt nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-153">Check that your email security product isn't blocking the email notifications from Defender for Endpoint.</span></span>
3. <span data-ttu-id="bc9b8-154">Überprüfen Sie ihre E-Mail-Anwendungsregeln, die Ihre Defender für Endpunkt-E-Mail-Benachrichtigungen möglicherweise abfangen und verschieben.</span><span class="sxs-lookup"><span data-stu-id="bc9b8-154">Check your email application rules that might be catching and moving your Defender for Endpoint email notifications.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bc9b8-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bc9b8-155">Related topics</span></span>

- [<span data-ttu-id="bc9b8-156">Aktualisieren der Einstellungen für die Datenaufbewahrung</span><span class="sxs-lookup"><span data-stu-id="bc9b8-156">Update data retention settings</span></span>](data-retention-settings.md)
- [<span data-ttu-id="bc9b8-157">Konfigurieren erweiterter Funktionen</span><span class="sxs-lookup"><span data-stu-id="bc9b8-157">Configure advanced features</span></span>](advanced-features.md)
- [<span data-ttu-id="bc9b8-158">Konfigurieren von E-Mail-Benachrichtigungen zu Sicherheitsrisiken in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bc9b8-158">Configure vulnerability email notifications in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/configure-vulnerability-email-notifications)
