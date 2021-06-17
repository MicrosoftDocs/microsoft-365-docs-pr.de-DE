---
title: Konfigurieren des Event Hubs
description: Erfahren Sie, wie Sie Ihren Event Hub konfigurieren
keywords: Event Hub, konfigurieren, Einblicke
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985587"
---
# <a name="configure-your-event-hub"></a><span data-ttu-id="eb7da-104">Konfigurieren des Event Hubs</span><span class="sxs-lookup"><span data-stu-id="eb7da-104">Configure your Event Hub</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eb7da-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eb7da-105">**Applies to:**</span></span>
- [<span data-ttu-id="eb7da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eb7da-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="eb7da-107">Erfahren Sie, wie Sie Ihren Event Hub so konfigurieren, dass er Ereignisse aus Microsoft 365 Defender erfassen kann.</span><span class="sxs-lookup"><span data-stu-id="eb7da-107">Learn how to configure your Event Hub so that it can ingest events from Microsoft 365 Defender.</span></span>


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a><span data-ttu-id="eb7da-108">Einrichten des erforderlichen Ressourcenanbieters im Event Hub-Abonnement</span><span class="sxs-lookup"><span data-stu-id="eb7da-108">Setup the required Resource Provider in the Event Hub subscription</span></span>


1. <span data-ttu-id="eb7da-109">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="eb7da-109">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
1. <span data-ttu-id="eb7da-110">Select **Subscriptions { Select the subscription the event hub will be deployed \> ***to***} \> Resource providers**.</span><span class="sxs-lookup"><span data-stu-id="eb7da-110">Select **Subscriptions \> {***Select the subscription the event hub will be deployed to***} \> Resource providers**.</span></span>
1. <span data-ttu-id="eb7da-111">Stellen Sie sicher, dass der **Microsoft.Insights-Anbieter** registriert ist.</span><span class="sxs-lookup"><span data-stu-id="eb7da-111">Verify that the **Microsoft.Insights** Provider is registered.</span></span> <span data-ttu-id="eb7da-112">Andernfalls registrieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="eb7da-112">Otherwise, register it.</span></span>

![Abbildung der Ressourcenanbieter in Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a><span data-ttu-id="eb7da-114">Einrichten Azure Active Directory App-Registrierung</span><span class="sxs-lookup"><span data-stu-id="eb7da-114">Setup Azure Active Directory App Registration</span></span>


><span data-ttu-id="eb7da-115">! [HINWEIS] Sie müssen über eine Administratorrolle verfügen, oder Azure Active Directory (AAD) muss so festgelegt sein, dass Nicht-Administratoren Apps registrieren können.</span><span class="sxs-lookup"><span data-stu-id="eb7da-115">![NOTE] You must have Administrator role or Azure Active Directory (AAD) must be set to allow non-Administrators to register apps.</span></span> <span data-ttu-id="eb7da-116">Sie müssen auch über eine Besitzer- oder Benutzerzugriffsadministratorrolle verfügen, um dem Dienstprinzipal eine Rolle zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eb7da-116">You must also have an Owner or User Access Administrator role to assign the service principal a role.</span></span>  
><span data-ttu-id="eb7da-117">Weitere Informationen finden Sie unter [Erstellen einer Azure AD-App & Dienstprinzipals im Portal – Microsoft Identity Platform \| Microsoft-Dokumentation.](/azure/active-directory/develop/howto-create-service-principal-portal)</span><span class="sxs-lookup"><span data-stu-id="eb7da-117">For more information, see [Create an Azure AD app & service principal in the portal - Microsoft identity platform \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).</span></span>

1. <span data-ttu-id="eb7da-118">Erstellen Sie eine neue Registrierung (die inhärent einen Dienstprinzipal erstellt) in **Azure Active Directory \> App-Registrierungen \> Neue Registrierung.**</span><span class="sxs-lookup"><span data-stu-id="eb7da-118">Create a new registration (which inherently creates a service principal) in **Azure Active Directory \> App registrations \> New registration.**</span></span>

1. <span data-ttu-id="eb7da-119">Füllen Sie das Formular nur mit dem Namen aus (es ist kein Umleitungs-URI erforderlich).</span><span class="sxs-lookup"><span data-stu-id="eb7da-119">Fill out the form with just the Name (no Redirect URI is required).</span></span>

    ![Abbildung der Registrierung einer Anwendung](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Abbildung der Übersichtsinformationen](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. <span data-ttu-id="eb7da-122">Erstellen Sie einen geheimen Schlüssel, indem Sie auf **Zertifikate & geheimen \> Schlüsseln neuer geheimer Clientschlüssel** klicken:</span><span class="sxs-lookup"><span data-stu-id="eb7da-122">Create a secret by clicking on **Certificates & secrets \> New client secret**:</span></span>

    ![Abbildung von Zertifikaten und geheimen Schlüsseln](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
><span data-ttu-id="eb7da-124">**Sie können nicht erneut auf den geheimen Clientschlüssel zugreifen. Stellen Sie daher sicher, dass Sie ihn speichern.**</span><span class="sxs-lookup"><span data-stu-id="eb7da-124">**You won't be able to access the client secret again so make sure to save it**.</span></span>

## <a name="setup-event-hub-namespace"></a><span data-ttu-id="eb7da-125">Setup Event Hub-Namespace</span><span class="sxs-lookup"><span data-stu-id="eb7da-125">Setup Event Hub namespace</span></span>


1. <span data-ttu-id="eb7da-126">Erstellen sie einen Event Hub-Namespace:</span><span class="sxs-lookup"><span data-stu-id="eb7da-126">Create an Event Hub Namespace:</span></span>

    <span data-ttu-id="eb7da-127">Wechseln **Sie zu "Event Hubs \> Hinzufügen",** und wählen Sie die Preisstufe, durchsatzeinheiten und die automatische Aufblasung (erfordert Standardpreise und unter Features) für die erwartete Last aus.</span><span class="sxs-lookup"><span data-stu-id="eb7da-127">Go **to Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.</span></span>  
    <span data-ttu-id="eb7da-128">Weitere Informationen finden Sie unter [Preise – Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span><span class="sxs-lookup"><span data-stu-id="eb7da-128">For more information, see [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)</span></span>

    >[!NOTE]
    > <span data-ttu-id="eb7da-129">Sie können einen vorhandenen Event Hub verwenden, aber der Durchsatz und die Skalierung werden auf Namespaceebene festgelegt, daher wird empfohlen, einen Event Hub im zugehörigen Namespace zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="eb7da-129">You can use an existing event hub, but the throughput and scaling are set at the namespace level so it is recommended to place an event hub in itsown namespace.</span></span>

   ![Abbildung des Event Hub-Namensraums](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. <span data-ttu-id="eb7da-131">Sie benötigen auch die Ressourcen-ID dieses Event Hub-Namespace.</span><span class="sxs-lookup"><span data-stu-id="eb7da-131">You will also need the Resource ID of this Event Hub Namespace.</span></span> <span data-ttu-id="eb7da-132">Wechseln Sie zu den Eigenschaften ihrer Azure Event Hubs-Namespaceseite. \></span><span class="sxs-lookup"><span data-stu-id="eb7da-132">Go to your Azure Event Hubs namespace page \> Properties.</span></span> <span data-ttu-id="eb7da-133">Kopieren Sie den Text unter "Ressourcen-ID", und notieren Sie ihn für die Verwendung im abschnitt "M365-Konfiguration" weiter unten.</span><span class="sxs-lookup"><span data-stu-id="eb7da-133">Copy the text under Resource ID and record it for use during the M365 Configuration section below.</span></span> 

    ![Abbildung der Eigenschaften](../../media/759498162a4e93cbf17c4130d704d164.png)

1. <span data-ttu-id="eb7da-135">Nachdem der Event Hub-Namespace erstellt wurde, müssen Sie den App-Registrierungsdienstprinzipal als Leser, Azure Event Hubs-Datenempfänger und den Benutzer hinzufügen, der sich bei Microsoft 365 Defender als Mitwirkender anmeldet (dies kann auch auf Ressourcengruppen- oder Abonnementebene erfolgen).</span><span class="sxs-lookup"><span data-stu-id="eb7da-135">Once the Event Hub Namespace is created you will need to add the App Registration Service Principal as Reader, Azure Event Hubs Data Receiver, and the user who will be logging into Microsoft 365 Defender as Contributor (this can also be done at Resource Group or Subscription level).</span></span>

    <span data-ttu-id="eb7da-136">Dies geschieht in **Event Hubs Namespace \> Access Control (IAM) \> Hinzufügen** und Überprüfen unter **Rollenzuweisungen:**</span><span class="sxs-lookup"><span data-stu-id="eb7da-136">This is done in **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:</span></span>

    ![Abbildung der Zugriffssteuerung](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a><span data-ttu-id="eb7da-138">Setup Event Hub</span><span class="sxs-lookup"><span data-stu-id="eb7da-138">Setup Event Hub</span></span>


<span data-ttu-id="eb7da-139">**Option 1:**</span><span class="sxs-lookup"><span data-stu-id="eb7da-139">**Option 1:**</span></span>

<span data-ttu-id="eb7da-140">Sie können einen Event Hub in Ihrem Namespace erstellen, und **alle** Ereignistypen (Tabellen), die Sie exportieren möchten, werden in **diesen** Event Hub geschrieben.</span><span class="sxs-lookup"><span data-stu-id="eb7da-140">You can create an Event Hub within your Namespace and **all** the Event Types (Tables) you select to export will be written into this **one** Event Hub.</span></span>

<span data-ttu-id="eb7da-141">**Option 2:**</span><span class="sxs-lookup"><span data-stu-id="eb7da-141">**Option 2:**</span></span>

<span data-ttu-id="eb7da-142">Anstatt alle Ereignistypen (Tabellen) in einen Event Hub zu exportieren, können Sie jede Tabelle in einen anderen Event Hub innerhalb des Event Hub-Namespace exportieren (einen Event Hub pro Ereignistyp).</span><span class="sxs-lookup"><span data-stu-id="eb7da-142">Instead of exporting all the Event Types (Tables) into one Event Hub, you can export each table into a different Event Hub inside your Event Hub Namespace (one Event Hub per Event Type).</span></span>  

<span data-ttu-id="eb7da-143">In dieser Option erstellt Microsoft 365 Defender Event Hubs für Sie.</span><span class="sxs-lookup"><span data-stu-id="eb7da-143">In this option, Microsoft 365 Defender will create Event Hubs for you.</span></span>  
>[!NOTE]
> <span data-ttu-id="eb7da-144">Wenn Sie einen Event Hub-Namespace verwenden, der **nicht** Teil eines Event Hub-Clusters ist, können Sie aufgrund einer Azure-Einschränkung von 10 Event Hubs pro Event Hub-Namespace nur bis zu 10 Ereignistypen (Tabellen) auswählen, die in jedem export Einstellungen exportiert werden sollen, den Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="eb7da-144">If you are using an Event Hub Namespace that is **not** part of an Event Hub Cluster, you will only be able to choose up to 10 Event Types (Tables) to export in each Export Settings you define, due to an Azure limitation of 10 Event Hubs per Event Hub Namespace.</span></span>

<span data-ttu-id="eb7da-145">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eb7da-145">For example:</span></span>

![Abbildung des Beispiel-Event Hub](../../media/005c1f6c10c34420d387f594987f9ffe.png)

<span data-ttu-id="eb7da-147">Wenn Sie diese Option auswählen, können Sie zum Abschnitt "Konfigurieren Microsoft 365 Defender zum Senden von [E-Mail-Tabellen"](#configure-microsoft-365-defender-to-send-email-tables) wechseln.</span><span class="sxs-lookup"><span data-stu-id="eb7da-147">If you choose this option, you can skip to the [Configure Microsoft 365 Defender to send email tables](#configure-microsoft-365-defender-to-send-email-tables) section.</span></span>

<span data-ttu-id="eb7da-148">Erstellen Sie einen Event Hub in Ihrem Namespace, indem Sie **Event Hubs \> + Event Hub** auswählen.</span><span class="sxs-lookup"><span data-stu-id="eb7da-148">Create an Event Hub within your Namespace by selecting **Event Hubs \> + Event Hub**.</span></span>

<span data-ttu-id="eb7da-149">Die Partitionsanzahl ermöglicht zusätzlichen Durchsatz über Parallelität. Daher wird empfohlen, diese Anzahl basierend auf der erwarteten Last zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="eb7da-149">The Partition Count allows for additional throughput via parallelism, so it is recommended to increase this number based on the load you are expecting.</span></span>  
<span data-ttu-id="eb7da-150">Es werden standardmäßige Nachrichtenaufbewahrungs- und Aufnahmewerte von 1 und "Aus" empfohlen.</span><span class="sxs-lookup"><span data-stu-id="eb7da-150">Default Message Retention and Capture values of 1 and Off are recommended.</span></span>

![Abbildung zum Erstellen des Event Hubs](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

<span data-ttu-id="eb7da-152">Für diesen Event Hub (nicht namespace) müssen Sie eine Shared Access Policy mit Send, Listen Claims konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="eb7da-152">For this Event Hub (not namespace) you will need to configure a Shared Access Policy with Send, Listen Claims.</span></span> <span data-ttu-id="eb7da-153">Klicken Sie auf Ihre Richtlinien für den freigegebenen Zugriff auf **den Event Hub + \> \> Hinzufügen,** und geben Sie ihr dann einen Richtliniennamen (nicht an anderer Stelle verwendet), und aktivieren Sie **"Senden** und **Überwachen".**</span><span class="sxs-lookup"><span data-stu-id="eb7da-153">Click on your **Event Hub \> Shared access policies \> + Add** and then give it a Policy name (not used elsewhere) and check **Send** and **Listen**.</span></span>

![Abbildung der Richtlinien für den freigegebenen Zugriff](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a><span data-ttu-id="eb7da-155">Konfigurieren Microsoft 365 Defender zum Senden von E-Mail-Tabellen</span><span class="sxs-lookup"><span data-stu-id="eb7da-155">Configure Microsoft 365 Defender to send email tables</span></span>


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a><span data-ttu-id="eb7da-156">Einrichten Microsoft 365 Defender Senden von E-Mail-Tabellen an Splunk über den Event Hub</span><span class="sxs-lookup"><span data-stu-id="eb7da-156">Setup Microsoft 365 Defender send Email tables to Splunk via Event Hub</span></span>


1. <span data-ttu-id="eb7da-157">Melden Sie sich bei Microsoft 365 Defender <https://security.microsoft.com> mit einem Konto an, das alle folgenden Rollenanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="eb7da-157">Login to Microsoft 365 Defender at <https://security.microsoft.com> with an account that meets all the following role requirements:</span></span>

    - <span data-ttu-id="eb7da-158">Rolle "Mitwirkender" auf der Event *Hub-Namespaceressourcenebene* oder höher für den Event Hub, in den Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="eb7da-158">Contributor role at the Event Hub *Namespace* Resource level or higher for the Event Hub that you will be exporting to.</span></span> <span data-ttu-id="eb7da-159">Ohne dies erhalten Sie einen Exportfehler, wenn Sie versuchen, die Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="eb7da-159">Without this you will get an export error when you try to save the settings.</span></span>

    - <span data-ttu-id="eb7da-160">Rolle "Globaler Administrator" oder "Sicherheitsadministrator" auf dem Mandanten, der an Microsoft 365 Defender und Azure gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="eb7da-160">Global Admin or Security Admin Role on the tenant tied to Microsoft 365 Defender and Azure.</span></span>

    ![Abbildung des Sicherheitsportals](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. <span data-ttu-id="eb7da-162">Klicken Sie auf **"Rohdatenexport" \> und "Hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="eb7da-162">Click on **Raw Data Export \> +Add**.</span></span>

    <span data-ttu-id="eb7da-163">Sie verwenden jetzt die Daten, die Sie oben notiert haben.</span><span class="sxs-lookup"><span data-stu-id="eb7da-163">You will now use the data that your recorded above.</span></span>

    <span data-ttu-id="eb7da-164">**Name:** Dies ist lokal und sollte das sein, was in Ihrer Umgebung funktioniert.</span><span class="sxs-lookup"><span data-stu-id="eb7da-164">**Name**: This is local and should be whatever works in your environment.</span></span>

    <span data-ttu-id="eb7da-165">**Weiterleiten von Ereignissen an den Event Hub:** Aktivieren Sie dieses Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="eb7da-165">**Forward events to event hub**: Select this checkbox.</span></span>

    <span data-ttu-id="eb7da-166">**Event-Hub-Ressourcen-ID:** Dies ist die Event Hub-Namespace-Ressourcen-ID, die Sie oben beim Einrichten des Event Hubs notiert haben.</span><span class="sxs-lookup"><span data-stu-id="eb7da-166">**Event-Hub Resource ID**: This is the Event Hub Namespace Resource ID you  recorded above when you setup the Event Hub.</span></span>

    <span data-ttu-id="eb7da-167">**Event-Hub-Name:** Wenn Sie einen Event Hub in Ihrem Event Hub-Namespace erstellt haben, fügen Sie den event Hub-Namen ein, den Sie oben notiert haben.</span><span class="sxs-lookup"><span data-stu-id="eb7da-167">**Event-Hub name**:  If you created an Event Hub inside your Event Hub Namespace, paste the Event Hub  name you recorded above.</span></span>

    <span data-ttu-id="eb7da-168">Wenn Sie Microsoft 365 Defender das Erstellen von Event Hubs pro Ereignistypen (Tabellen) für Sie überlassen möchten, lassen Sie dieses Feld leer.</span><span class="sxs-lookup"><span data-stu-id="eb7da-168">If you choose to let Microsoft 365 Defender to create Event Hubs per Event Types  (Tables) for you, leave this field empty.</span></span>

    <span data-ttu-id="eb7da-169">**Ereignistypen:** Wählen Sie die Tabellen für die erweiterte Suche aus, die Sie an den Event Hub und dann an Ihre benutzerdefinierte App weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="eb7da-169">**Event Types**: Select the Advanced Hunting tables that you want to forward to the Event Hub and then on to your custom app.</span></span> <span data-ttu-id="eb7da-170">Warnungstabellen stammen aus Microsoft 365 Defender, Gerätetabellen stammen aus Microsoft Defender für Endpunkt (EDR), und E-Mail-Tabellen stammen aus Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="eb7da-170">Alert tables are from Microsoft 365 Defender, Devices tables are from Microsoft Defender for Endpoint (EDR), and Email tables are from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="eb7da-171">E-Mail-Ereignisse zeichnet alle E-Mail-Transaktionen auf.</span><span class="sxs-lookup"><span data-stu-id="eb7da-171">Email Events records all Email Transactions.</span></span> <span data-ttu-id="eb7da-172">Die URL (SafeLinks), Attachment (Safe Attachments) und Post Delivery Events (ZAP) werden ebenfalls aufgezeichnet und können mit den E-Mail-Ereignissen im NetworkMessageId-Feld verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="eb7da-172">The URL (SafeLinks), Attachment (Safe Attachments) and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.</span></span>

    ![Abbildung der Streaming-API-Einstellungen](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. <span data-ttu-id="eb7da-174">Stellen Sie sicher, dass Sie auf **"Übermitteln"** klicken.</span><span class="sxs-lookup"><span data-stu-id="eb7da-174">Make sure to click **Submit**.</span></span>

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a><span data-ttu-id="eb7da-175">Überprüfen, ob die Ereignisse in den Event Hub exportiert werden</span><span class="sxs-lookup"><span data-stu-id="eb7da-175">Verify that the events are being exported to the Event Hub</span></span>


<span data-ttu-id="eb7da-176">Sie können überprüfen, ob Ereignisse an den Event Hub gesendet werden, indem Sie eine einfache Advanced Hunting-Abfrage ausführen.</span><span class="sxs-lookup"><span data-stu-id="eb7da-176">You can verify that events are being sent to the Event Hub by running a basic Advanced Hunting query.</span></span> <span data-ttu-id="eb7da-177">Wählen Sie **"Erweiterte \> Suche \> suchen" aus,** und geben Sie die folgende Abfrage ein:</span><span class="sxs-lookup"><span data-stu-id="eb7da-177">Select **Hunting \> Advanced Hunting \> Query** and enter the following query:</span></span>

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

<span data-ttu-id="eb7da-178">Dies zeigt Ihnen, wie viele E-Mails in der letzten Stunde in allen anderen Tabellen eingegangen sind.</span><span class="sxs-lookup"><span data-stu-id="eb7da-178">This will show you how many emails were received in the last hour joined across all the other tables.</span></span> <span data-ttu-id="eb7da-179">Außerdem wird angezeigt, ob Ereignisse angezeigt werden, die in den Event Hub exportiert werden können.</span><span class="sxs-lookup"><span data-stu-id="eb7da-179">It will also show you if you are seeing events that could be exported to the event hub.</span></span> <span data-ttu-id="eb7da-180">Wenn diese Anzahl 0 anzeigt, werden keine Daten angezeigt, die an den Event Hub gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="eb7da-180">If this count shows 0 then you won't see any data going out to the Event Hub.</span></span>

![Abbildung der erweiterten Suche](../../media/c305e57dc6f72fa9eb035943f244738e.png)

<span data-ttu-id="eb7da-182">Nachdem Sie überprüft haben, dass Daten exportiert werden müssen, können Sie den Event Hub anzeigen, um zu überprüfen, ob Nachrichten eintreffen.</span><span class="sxs-lookup"><span data-stu-id="eb7da-182">Once you have verified there is data to export, you can view the Event Hub to verify that messages are incoming.</span></span> <span data-ttu-id="eb7da-183">Dies kann bis zu einer Stunde dauern.</span><span class="sxs-lookup"><span data-stu-id="eb7da-183">This can take up to one hour.</span></span> 
 
1. <span data-ttu-id="eb7da-184">Wechseln Sie in Azure zu **Event Hubs \> Click on the Namespace Event \> Hubs Click on the Event \> Hub**.</span><span class="sxs-lookup"><span data-stu-id="eb7da-184">In Azure, go to **Event Hubs \> Click on the Namespace \> Event Hubs \> Click on the Event Hub**.</span></span>  
1. <span data-ttu-id="eb7da-185">Scrollen Sie unter **"Übersicht"** nach unten, und im Diagramm "Nachrichten" sollten eingehende Nachrichten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eb7da-185">Under **Overview**, scroll down and in the Messages graph you should see Incoming Messages.</span></span> <span data-ttu-id="eb7da-186">Wenn keine Ergebnisse angezeigt werden, gibt es keine Nachrichten, die Ihre benutzerdefinierte App erfassen kann.</span><span class="sxs-lookup"><span data-stu-id="eb7da-186">If you don't see any results, then there will be no messages for your custom app to ingest.</span></span>

    ![Abbildung der Registerkarte "Übersicht" mit Nachrichten](../../media/e88060e315d76e74269a3fc866df047f.png)
