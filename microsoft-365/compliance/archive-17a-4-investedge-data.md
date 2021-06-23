---
title: Einrichten eines Connectors zum Archivieren von InvestEdge-Daten in Microsoft 365
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
description: Erfahren Sie, wie Sie einen 17a-4 InvestEdge DataParser-Connector einrichten und verwenden, um InvestEdge-Daten in Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: fd384cb25486c4fa072dc17283c5b73e26e514a6
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53097131"
---
# <a name="set-up-a-connector-to-archive-investedge-data-preview"></a><span data-ttu-id="0cbef-103">Einrichten eines Connectors zum Archivieren von InvestEdge-Daten (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="0cbef-103">Set up a connector to archive InvestEdge data (preview)</span></span>

<span data-ttu-id="0cbef-104">Verwenden Sie ["InvestEdge DataParser"](https://www.17a-4.com/investedge-dataparser/) von 17a-4 LLC, um Daten aus "InvestEdge" in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren.</span><span class="sxs-lookup"><span data-stu-id="0cbef-104">Use the [InvestEdge DataParser](https://www.17a-4.com/investedge-dataparser/) from 17a-4 LLC to import and archive data from InvestEdge to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="0cbef-105">The DataParser includes a InvestEdge connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0cbef-105">The DataParser includes a InvestEdge connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="0cbef-106">Der InvestEdge DataParser-Connector konvertiert InvestEdge-Daten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0cbef-106">The InvestEdge DataParser connector converts InvestEdge data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="0cbef-107">Nachdem InvestEdge-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationscompliance anwenden.</span><span class="sxs-lookup"><span data-stu-id="0cbef-107">After InvestEdge data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="0cbef-108">Die Verwendung eines InvestEdge-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Regierungsrichtlinien und behördlichen Richtlinien zu halten.</span><span class="sxs-lookup"><span data-stu-id="0cbef-108">Using a InvestEdge connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-investedge-data"></a><span data-ttu-id="0cbef-109">Übersicht über die Archivierung von InvestEdge-Daten</span><span class="sxs-lookup"><span data-stu-id="0cbef-109">Overview of archiving InvestEdge data</span></span>

<span data-ttu-id="0cbef-110">In der folgenden Übersicht wird der Prozess der Verwendung eines Datenkonnektors zum Archivieren von InvestEdge-Daten in Microsoft 365 erläutert.</span><span class="sxs-lookup"><span data-stu-id="0cbef-110">The following overview explains the process of using a data connector to archive InvestEdge data in Microsoft 365.</span></span>

![Archivierungsworkflow für InvestEdge-Daten von 17a-4](../media/InvestEdgeDataParserConnectorWorkflow.png)

1. <span data-ttu-id="0cbef-112">Ihre Organisation arbeitet mit 17a-4 zusammen, um "InvestEdge DataParser" einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0cbef-112">Your organization works with 17a-4 to set up and configure the InvestEdge DataParser.</span></span>

2. <span data-ttu-id="0cbef-113">In regelmäßigen Abständen werden "InvestEdge"-Elemente von DataParser gesammelt.</span><span class="sxs-lookup"><span data-stu-id="0cbef-113">On a regular basis, InvestEdge items are collected by the DataParser.</span></span> <span data-ttu-id="0cbef-114">Der DataParser konvertiert auch den Inhalt einer Nachricht in ein E-Mail-Nachrichtenformat.</span><span class="sxs-lookup"><span data-stu-id="0cbef-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="0cbef-115">Der InvestEdge DataParser-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt eine Verbindung mit DataParser her und überträgt die Nachrichten an einen sicheren Azure Storage Speicherort in der Microsoft-Cloud.</span><span class="sxs-lookup"><span data-stu-id="0cbef-115">The InvestEdge DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="0cbef-116">Ein Unterordner im Posteingangsordner mit dem Namen **"InvestEdge DataParser"** wird in den Benutzerpostfächern erstellt, und die "InvestEdge"-Elemente werden in diesen Ordner importiert.</span><span class="sxs-lookup"><span data-stu-id="0cbef-116">A subfolder in the Inbox folder named **InvestEdge DataParser** is created in the user mailboxes, and the InvestEdge items are imported to that folder.</span></span> <span data-ttu-id="0cbef-117">Der Connector bestimmt mithilfe des Werts der *E-Mail-Eigenschaft,* in welches Postfach Elemente importiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="0cbef-118">Jedes InvestEdge-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.</span><span class="sxs-lookup"><span data-stu-id="0cbef-118">Every InvestEdge item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="0cbef-119">Vor dem Einrichten eines Connectors</span><span class="sxs-lookup"><span data-stu-id="0cbef-119">Before you set up a connector</span></span>

- <span data-ttu-id="0cbef-120">Erstellen Sie ein DataParser-Konto für Microsoft Connectors.</span><span class="sxs-lookup"><span data-stu-id="0cbef-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="0cbef-121">Wenden Sie sich hierzu an [17a-4 LLC.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="0cbef-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="0cbef-122">Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="0cbef-123">Der Benutzer, der den "InvestEdge DataParser"-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="0cbef-123">The user who creates the InvestEdge DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="0cbef-124">Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="0cbef-125">Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="0cbef-126">Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="0cbef-127">Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="0cbef-128">Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".</span><span class="sxs-lookup"><span data-stu-id="0cbef-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-investedge-dataparser-connector"></a><span data-ttu-id="0cbef-129">Schritt 1: Einrichten eines InvestEdge DataParser-Connectors</span><span class="sxs-lookup"><span data-stu-id="0cbef-129">Step 1: Set up a InvestEdge DataParser connector</span></span>

<span data-ttu-id="0cbef-130">Der erste Schritt besteht darin, auf die Seite "Datenkonnektoren" im Microsoft 365 Compliance Center zuzugreifen und einen 17a-4-Connector für InvestEdge-Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for InvestEdge data.</span></span>

1. <span data-ttu-id="0cbef-131">Wechseln Sie zu <https://compliance.microsoft.com> "Data Connectors InvestEdge DataParser", und klicken Sie dann auf **"Datenkonnektoren".**  >  </span><span class="sxs-lookup"><span data-stu-id="0cbef-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **InvestEdge DataParser**.</span></span>

2. <span data-ttu-id="0cbef-132">Klicken Sie auf der Seite **"InvestEdge DataParser-Produktbeschreibung"** auf **"Connector hinzufügen".**</span><span class="sxs-lookup"><span data-stu-id="0cbef-132">On the **InvestEdge DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="0cbef-133">Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**</span><span class="sxs-lookup"><span data-stu-id="0cbef-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="0cbef-134">Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="0cbef-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="0cbef-135">Melden Sie sich bei Ihrem 17a-4-Konto an, und führen Sie die Schritte im InvestEdge DataParser-Verbindungs-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="0cbef-135">Sign in to your 17a-4 account and complete the steps in the InvestEdge DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-investedge-dataparser-connector"></a><span data-ttu-id="0cbef-136">Schritt 2: Konfigurieren des "InvestEdge DataParser"-Connectors</span><span class="sxs-lookup"><span data-stu-id="0cbef-136">Step 2: Configure the InvestEdge DataParser connector</span></span>

<span data-ttu-id="0cbef-137">Arbeiten Sie mit dem 17a-4-Support, um den InvestEdge DataParser-Connector zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0cbef-137">Work with 17a-4 Support to configure the InvestEdge DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="0cbef-138">Schritt 3: Zuordnen von Benutzern</span><span class="sxs-lookup"><span data-stu-id="0cbef-138">Step 3: Map users</span></span>

<span data-ttu-id="0cbef-139">Der InvestEdge DataParser-Connector ordnen Benutzer automatisch ihren Microsoft 365 E-Mail-Adressen zu, bevor Daten in Microsoft 365 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="0cbef-139">The InvestEdge DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-investedge-dataparser-connector"></a><span data-ttu-id="0cbef-140">Schritt 4: Überwachen des InvestEdge DataParser-Connectors</span><span class="sxs-lookup"><span data-stu-id="0cbef-140">Step 4: Monitor the InvestEdge DataParser connector</span></span>

<span data-ttu-id="0cbef-141">Nachdem Sie einen InvestEdge DataParser-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0cbef-141">After you create a InvestEdge DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="0cbef-142">Navigieren Sie im linken Navigationsbereich zu <https://compliance.microsoft.com> "Datenconnectors", und klicken Sie auf **"Datenconnectors".**</span><span class="sxs-lookup"><span data-stu-id="0cbef-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="0cbef-143">Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den Von Ihnen erstellten InvestEdge DataParser-Connector aus, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.</span><span class="sxs-lookup"><span data-stu-id="0cbef-143">Click the **Connectors** tab and then select the InvestEdge DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="0cbef-144">Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern).</span><span class="sxs-lookup"><span data-stu-id="0cbef-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="0cbef-145">Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="0cbef-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="0cbef-146">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="0cbef-146">Known issues</span></span>

<span data-ttu-id="0cbef-147">Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0cbef-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="0cbef-148">Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="0cbef-148">Support for larger items will be available at a later date.</span></span>
