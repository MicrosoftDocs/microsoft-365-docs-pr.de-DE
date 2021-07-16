---
title: Einrichten eines Connectors zum Archivieren von Zoomdaten in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Erfahren Sie, wie Sie einen 17a-4 Zoom DataParser-Connector zum Importieren und Archivieren von Zoomdaten in Microsoft 365 einrichten und verwenden.
ms.openlocfilehash: 1c70099efa17b5ff6c1c4dfcd71c6bf6790535c8
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453945"
---
# <a name="set-up-a-connector-to-archive-zoom-data"></a><span data-ttu-id="07546-103">Einrichten eines Connectors zum Archivieren von Zoomdaten</span><span class="sxs-lookup"><span data-stu-id="07546-103">Set up a connector to archive Zoom data</span></span>

<span data-ttu-id="07546-104">Verwenden Sie [den Zoom DataParser](https://www.17a-4.com/dataparser/) von 17a-4 LLC, um Daten von der Zoom-Plattform in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="07546-104">Use the [Zoom DataParser](https://www.17a-4.com/dataparser/) from 17a-4 LLC to import and archive data from the Zoom platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="07546-105">Der DataParser enthält einen Zoom-Connector, der so konfiguriert ist, dass Elemente aus einer Datenquelle eines Drittanbieters erfasst und in Microsoft 365 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="07546-105">The DataParser includes a Zoom connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="07546-106">Der Zoom DataParser-Connector konvertiert Zoomdaten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07546-106">The Zoom DataParser connector converts Zoom data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="07546-107">Nachdem Zoom-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationscompliance anwenden.</span><span class="sxs-lookup"><span data-stu-id="07546-107">After Zoom data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="07546-108">Die Verwendung eines Zoom-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Gesetzlichen und behördlichen Richtlinien einhalten kann.</span><span class="sxs-lookup"><span data-stu-id="07546-108">Using a Zoom connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-zoom-data"></a><span data-ttu-id="07546-109">Übersicht über die Archivierung von Zoomdaten</span><span class="sxs-lookup"><span data-stu-id="07546-109">Overview of archiving Zoom data</span></span>

<span data-ttu-id="07546-110">In der folgenden Übersicht wird der Prozess der Verwendung eines Datenkonnektors zum Archivieren von Zoomdaten in Microsoft 365 erläutert.</span><span class="sxs-lookup"><span data-stu-id="07546-110">The following overview explains the process of using a data connector to archive Zoom data in Microsoft 365.</span></span>

![Archivierungsworkflow für Zoomdaten von 17a-4](../media/ZoomDataParserConnectorWorkflow.png)

1. <span data-ttu-id="07546-112">Ihre Organisation arbeitet mit 17a-4 zusammen, um zoom DataParser einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="07546-112">Your organization works with 17a-4 to set up and configure the Zoom DataParser.</span></span>

2. <span data-ttu-id="07546-113">Zoomelemente werden in regelmäßigen Abständen von DataParser gesammelt.</span><span class="sxs-lookup"><span data-stu-id="07546-113">On a regular basis, Zoom items are collected by the DataParser.</span></span> <span data-ttu-id="07546-114">Der DataParser konvertiert auch den Inhalt einer Nachricht in ein E-Mail-Nachrichtenformat.</span><span class="sxs-lookup"><span data-stu-id="07546-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="07546-115">Der Zoom DataParser-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt eine Verbindung mit DataParser her und überträgt die Nachrichten an einen sicheren Azure Storage Speicherort in der Microsoft-Cloud.</span><span class="sxs-lookup"><span data-stu-id="07546-115">The Zoom DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="07546-116">Ein Unterordner im Ordner "Posteingang" mit dem Namen **"Zoom DataParser"** wird in den Benutzerpostfächern erstellt, und die Zoomelemente werden in diesen Ordner importiert.</span><span class="sxs-lookup"><span data-stu-id="07546-116">A subfolder in the Inbox folder named **Zoom DataParser** is created in the user mailboxes, and the Zoom items are imported to that folder.</span></span> <span data-ttu-id="07546-117">Der Connector bestimmt mithilfe des Werts der *E-Mail-Eigenschaft,* in welches Postfach Elemente importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="07546-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="07546-118">Jedes Zoom-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="07546-118">Every Zoom item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="07546-119">Vor dem Einrichten eines Connectors</span><span class="sxs-lookup"><span data-stu-id="07546-119">Before you set up a connector</span></span>

- <span data-ttu-id="07546-120">Erstellen Sie ein DataParser-Konto für Microsoft Connectors.</span><span class="sxs-lookup"><span data-stu-id="07546-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="07546-121">Wenden Sie sich hierzu an [17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="07546-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="07546-122">Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.</span><span class="sxs-lookup"><span data-stu-id="07546-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="07546-123">Der Benutzer, der den Zoom DataParser-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="07546-123">The user who creates the Zoom DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="07546-124">Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="07546-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="07546-125">Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="07546-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="07546-126">Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="07546-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="07546-127">Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="07546-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="07546-128">Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="07546-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-zoom-dataparser-connector"></a><span data-ttu-id="07546-129">Schritt 1: Einrichten eines Zoom DataParser-Connectors</span><span class="sxs-lookup"><span data-stu-id="07546-129">Step 1: Set up a Zoom DataParser connector</span></span>

<span data-ttu-id="07546-130">Der erste Schritt besteht darin, auf die Seite "Datenkonnektoren" im Microsoft 365 Compliance Center zuzugreifen und einen 17a-4-Connector für Zoomdaten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="07546-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for Zoom data.</span></span>

1. <span data-ttu-id="07546-131">Wechseln Sie zu <https://compliance.microsoft.com> und klicken Sie dann auf **Datenconnectors**  >  **Zoom DataParser**.</span><span class="sxs-lookup"><span data-stu-id="07546-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **Zoom DataParser**.</span></span>

2. <span data-ttu-id="07546-132">Klicken Sie auf der Seite **"DataParser-Produktbeschreibung zoomen"** auf **"Connector hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="07546-132">On the **Zoom DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="07546-133">Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**</span><span class="sxs-lookup"><span data-stu-id="07546-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="07546-134">Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="07546-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="07546-135">Melden Sie sich bei Ihrem 17a-4-Konto an, und führen Sie die Schritte im Assistenten zum Zoomen der DataParser-Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="07546-135">Sign in to your 17a-4 account and complete the steps in the Zoom DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-zoom-dataparser-connector"></a><span data-ttu-id="07546-136">Schritt 2: Konfigurieren des Zoom DataParser-Connectors</span><span class="sxs-lookup"><span data-stu-id="07546-136">Step 2: Configure the Zoom DataParser connector</span></span>

<span data-ttu-id="07546-137">Arbeiten Sie mit der 17a-4-Unterstützung, um den Zoom DataParser-Connector zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="07546-137">Work with 17a-4 Support to configure the Zoom DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="07546-138">Schritt 3: Zuordnen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="07546-138">Step 3: Map users</span></span>

<span data-ttu-id="07546-139">Der Zoom DataParser-Connector weist Benutzern automatisch ihre Microsoft 365 E-Mail-Adressen zu, bevor Daten in Microsoft 365 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="07546-139">The Zoom DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-zoom-dataparser-connector"></a><span data-ttu-id="07546-140">Schritt 4: Überwachen des Zoom DataParser-Connectors</span><span class="sxs-lookup"><span data-stu-id="07546-140">Step 4: Monitor the Zoom DataParser connector</span></span>

<span data-ttu-id="07546-141">Nachdem Sie einen Zoom DataParser-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="07546-141">After you create a Zoom DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="07546-142">Wechseln Sie in <https://compliance.microsoft.com> der linken Navigationsleiste zu "Datenconnectors", und klicken Sie auf **"Datenconnectors".**</span><span class="sxs-lookup"><span data-stu-id="07546-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="07546-143">Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den Zoom DataParser-Connector aus, den Sie erstellt haben, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.</span><span class="sxs-lookup"><span data-stu-id="07546-143">Click the **Connectors** tab and then select the Zoom DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="07546-144">Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern).</span><span class="sxs-lookup"><span data-stu-id="07546-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="07546-145">Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="07546-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="07546-146">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="07546-146">Known issues</span></span>

<span data-ttu-id="07546-147">Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="07546-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="07546-148">Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="07546-148">Support for larger items will be available at a later date.</span></span>
