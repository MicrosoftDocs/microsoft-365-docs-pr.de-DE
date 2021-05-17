---
title: Einrichten Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: In diesem Artikel wird beschrieben, wie Sie Advanced eDiscovery einrichten, damit Sie mit dem Erstellen und Verwalten von Fällen beginnen können. Außerdem werden die erforderlichen Microsoft-Abonnements und -Lizenzierung beschrieben. Nachdem Sie einige kurze Schritte abgeschlossen haben, ist das Advanced eDiscovery einsatzbereit.
ms.openlocfilehash: 6c6aed482da8f203154d94313ec04519d6a330ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919745"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a><span data-ttu-id="c072b-105">Einrichten Microsoft 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c072b-105">Set up Microsoft 365 Advanced eDiscovery</span></span>

<span data-ttu-id="c072b-106">Advanced eDiscovery in Microsoft 365 bietet einen End-to-End-Workflow zum Beibehalten, Sammeln, Überprüfen, Analysieren und Exportieren von Daten, die auf interne und externe Untersuchungen Ihrer Organisation reagieren.</span><span class="sxs-lookup"><span data-stu-id="c072b-106">Advanced eDiscovery in Microsoft 365 provides an end-to-end workflow to preserve, collect, review, analyze, and export data that's responsive to your organization's internal and external investigations.</span></span> <span data-ttu-id="c072b-107">Für die Bereitstellung von Advanced eDiscovery ist nichts erforderlich, aber es gibt einige erforderliche Aufgaben, die ein IT-Administrator und ein eDiscovery-Manager ausführen müssen, bevor Ihre Organisation mit der Erstellung und Verwendung von Advanced eDiscovery-Fällen beginnen kann, um Ihre Untersuchungen zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="c072b-107">Nothing is needed to deploy Advanced eDiscovery, but there are some prerequisite tasks that an IT admin and eDiscovery manager have to complete before your organization can start to create and use Advanced eDiscovery cases to manage your investigations.</span></span>

<span data-ttu-id="c072b-108">In diesem Artikel werden die folgenden Schritte zum Einrichten von Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c072b-108">This article discusses the following steps necessary to set up Advanced eDiscovery.</span></span>

![Schritte zum Einrichten Advanced eDiscovery](../media/set-up-advanced-ediscovery.png)

<span data-ttu-id="c072b-110">Dies umfasst die Sicherstellung der ordnungsgemäßen Lizenzierung, die für den Zugriff auf Advanced eDiscovery und das Hinzufügen von Verwahrern zu Fällen erforderlich ist, und das Zuweisen von Berechtigungen zu Ihrem Rechts- und Untersuchungsteam, damit diese auf Fälle zugreifen und diese verwalten können.</span><span class="sxs-lookup"><span data-stu-id="c072b-110">This includes ensuring the proper licensing required to access Advanced eDiscovery and add custodians to cases, and assigning permissions to your legal and investigation team so they can access and manage cases.</span></span>

## <a name="step-1-verify-and-assign-appropriate-licenses"></a><span data-ttu-id="c072b-111">Schritt 1: Überprüfen und Zuweisen entsprechender Lizenzen</span><span class="sxs-lookup"><span data-stu-id="c072b-111">Step 1: Verify and assign appropriate licenses</span></span>

<span data-ttu-id="c072b-112">Die Lizenzierung Advanced eDiscovery erfordert das entsprechende Organisationsabonnement und die Benutzerlizenzierung.</span><span class="sxs-lookup"><span data-stu-id="c072b-112">Licensing for Advanced eDiscovery requires the appropriate organization subscription and per-user licensing.</span></span> <span data-ttu-id="c072b-113">Eine Liste der Lizenzierungsanforderungen für Advanced eDiscovery finden Sie unter [Abonnements und Lizenzierung](overview-ediscovery-20.md#subscriptions-and-licensing).</span><span class="sxs-lookup"><span data-stu-id="c072b-113">For a list of licensing requirements for Advanced eDiscovery, see [Subscriptions and licensing](overview-ediscovery-20.md#subscriptions-and-licensing).</span></span>

## <a name="step-2-assign-ediscovery-permissions"></a><span data-ttu-id="c072b-114">Schritt 2: Zuweisen von eDiscovery-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="c072b-114">Step 2: Assign eDiscovery permissions</span></span>

<span data-ttu-id="c072b-115">Um auf Advanced eDiscovery oder als Mitglied eines Advanced eDiscovery hinzugefügt werden, muss einem Benutzer die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="c072b-115">To access Advanced eDiscovery or added as a member of an Advanced eDiscovery case, a user must be assigned the appropriate permissions.</span></span> <span data-ttu-id="c072b-116">Insbesondere muss ein Benutzer als Mitglied der Rollengruppe eDiscovery Manager im Security & Compliance Center hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c072b-116">Specifically, a user must be added as a member of the eDiscovery Manager role group in the Security & Compliance Center.</span></span> <span data-ttu-id="c072b-117">Mitglieder dieser Rollengruppe können Advanced eDiscovery verwalten.</span><span class="sxs-lookup"><span data-stu-id="c072b-117">Members of this role group can create and manage Advanced eDiscovery cases.</span></span> <span data-ttu-id="c072b-118">Sie können Mitglieder hinzufügen und entfernen, Verwahrer und Inhaltsspeicherorte in der Warteschleife platzieren, Benachrichtigungen über rechtliches Halterecht verwalten, in einem Fall zugeordnete Suchen erstellen und bearbeiten, Suchergebnisse zu einem Überprüfungssatz hinzufügen, Daten in einem Überprüfungssatz analysieren und aus einem Advanced eDiscovery-Fall exportieren und herunterladen.</span><span class="sxs-lookup"><span data-stu-id="c072b-118">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit searches associated in a case, add search results to a review set, analyze data in a review set, and export and download from an Advanced eDiscovery case.</span></span>

<span data-ttu-id="c072b-119">Führen Sie die folgenden Schritte aus, um der Rollengruppe eDiscovery Manager Benutzer hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="c072b-119">Complete the following steps to add users to the eDiscovery Manager role group:</span></span>

1. <span data-ttu-id="c072b-120">Wechseln Sie zu, und melden Sie sich mit den Anmeldeinformationen für ein <https://protection.office.com/permissions> Administratorkonto in Ihrer Microsoft 365 an.</span><span class="sxs-lookup"><span data-stu-id="c072b-120">Go to <https://protection.office.com/permissions> and sign in using the credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="c072b-121">Wählen Sie **auf der** Seite Berechtigungen die **Rollengruppe eDiscovery-Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="c072b-121">On the **Permissions** page, select the **eDiscovery Manager** role group.</span></span>

3. <span data-ttu-id="c072b-122">Klicken Sie auf der Flyoutseite  des eDiscovery-Managers neben dem **eDiscovery-Manager** auf Bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c072b-122">On the eDiscovery Manager flyout page, click **Edit** next to the **eDiscovery Manager** section.</span></span>

4. <span data-ttu-id="c072b-123">Klicken Sie auf der Seite **eDiscovery-Manager** auswählen im Assistenten zum Bearbeiten von Rollengruppen auf **eDiscovery-Manager auswählen.**</span><span class="sxs-lookup"><span data-stu-id="c072b-123">On the **Choose eDiscovery Manager** page in the edit role group wizard, click **Choose eDiscovery Manager**.</span></span>

5. <span data-ttu-id="c072b-124">Klicken **Sie auf** Hinzufügen, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c072b-124">Click **Add** then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="c072b-125">Klicken **Sie auf** Hinzufügen, um die ausgewählten Benutzer hinzuzufügen, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="c072b-125">Click **Add** to add the selected users, and then click **Done**.</span></span>

7. <span data-ttu-id="c072b-126">Klicken **Sie auf Speichern,** um die Benutzer zur Rollengruppe hinzuzufügen, und klicken Sie dann auf **Schließen,** um den Schritt zu vervollständigen.</span><span class="sxs-lookup"><span data-stu-id="c072b-126">Click **Save** to add the users to the role group, and then click **Close** to complete the step.</span></span>

### <a name="more-information-about-the-ediscovery-manager-role-group"></a><span data-ttu-id="c072b-127">Weitere Informationen zur Rollengruppe eDiscovery-Manager</span><span class="sxs-lookup"><span data-stu-id="c072b-127">More information about the eDiscovery Manager role group</span></span>

<span data-ttu-id="c072b-128">Die Rollengruppe eDiscovery Manager besteht aus zwei Untergruppen.</span><span class="sxs-lookup"><span data-stu-id="c072b-128">There are two subgroups in the eDiscovery Manager role group.</span></span> <span data-ttu-id="c072b-129">Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.</span><span class="sxs-lookup"><span data-stu-id="c072b-129">The difference between these subgroups is based on scope.</span></span>

- <span data-ttu-id="c072b-130">**eDiscovery Manager**: Kann die von ihnen erstellten Advanced eDiscovery anzeigen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="c072b-130">**eDiscovery Manager**: Can view and manage the Advanced eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="c072b-131">Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falls hinzu fügt, kann der zweite eDiscovery-Manager den Fall nicht auf der seite Advanced eDiscovery im Compliance Center anzeigen oder öffnen.</span><span class="sxs-lookup"><span data-stu-id="c072b-131">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the Advanced eDiscovery page in the compliance center.</span></span> <span data-ttu-id="c072b-132">Im Allgemeinen können die meisten Personen in Ihrer Organisation der Untergruppe eDiscovery Manager hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c072b-132">In general, most people in your organization can be added to the eDiscovery Manager subgroup.</span></span>

- <span data-ttu-id="c072b-133">**eDiscovery-Administrator:** Kann alle Fallverwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="c072b-133">**eDiscovery Administrator**: Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="c072b-134">Außerdem kann ein eDiscovery-Administrator Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c072b-134">Additionally, an eDiscovery Administrator can:</span></span>

  - <span data-ttu-id="c072b-135">Anzeigen aller Fälle, die auf der Seite „ Advanced eDiscovery“ aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="c072b-135">View all cases that are listed on the Advanced eDiscovery page.</span></span>
  
  - <span data-ttu-id="c072b-136">Verwalten aller Fälle in der Organisation, nachdem er sich selbst als Fallmitglied hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="c072b-136">Manage any case in the organization after they add themselves as a member of the case.</span></span>

  - <span data-ttu-id="c072b-137">Zugreifen auf und Exportieren von Falldaten für jeden Fall in der Organisation.</span><span class="sxs-lookup"><span data-stu-id="c072b-137">Access and export case data for any case in the organization.</span></span>

  <span data-ttu-id="c072b-138">Aufgrund des breit gefächerten Zugriffs sollte eine Organisation nur über wenige Administratoren verfügen, die Mitglieder der Untergruppe der eDiscovery-Administratoren sind.</span><span class="sxs-lookup"><span data-stu-id="c072b-138">Because of the broad scope of access, an organization should have only a few admins who are members of the eDiscovery Administrators subgroup.</span></span>

<span data-ttu-id="c072b-139">Weitere Informationen zu eDiscovery-Berechtigungen und eine Beschreibung jeder Rolle, die der Rollengruppe eDiscovery-Manager zugewiesen ist, finden Sie unter [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c072b-139">For more information about eDiscovery permissions and a description of each role that's assigned to the eDiscovery Manager role group, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a><span data-ttu-id="c072b-140">Schritt 3: Konfigurieren globaler Einstellungen für Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c072b-140">Step 3: Configure global settings for Advanced eDiscovery</span></span>

<span data-ttu-id="c072b-141">Der letzte Schritt, der abgeschlossen werden muss, bevor Personen in Ihrer Organisation mit dem Erstellen und Verwenden von Fällen beginnen, besteht in der Konfiguration globaler Einstellungen, die für alle Fälle in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="c072b-141">The last step to complete before people in your organization start to create and use cases is to configure global settings that apply to all cases in your organization.</span></span> <span data-ttu-id="c072b-142">Derzeit ist die einzige globale Einstellung die Erkennung von *Anwalts-Client-Rechten* (in Zukunft sind weitere globale Einstellungen verfügbar).</span><span class="sxs-lookup"><span data-stu-id="c072b-142">At this time, the only global setting is *attorney-client privilege detection* (more global settings will be available in the future).</span></span> <span data-ttu-id="c072b-143">Diese Einstellung ermöglicht die Ausführung des Anwalts-Client-Berechtigungsmodells, wenn Sie Daten in einem Überprüfungssatz analysieren.</span><span class="sxs-lookup"><span data-stu-id="c072b-143">This setting enables the attorney-client privilege model to run when you analyze data in a review set.</span></span> <span data-ttu-id="c072b-144">Das Modell verwendet maschinelles Lernen, um die Wahrscheinlichkeit zu bestimmen, dass ein Dokument Inhalte enthält, die rechtlicher Natur sind.</span><span class="sxs-lookup"><span data-stu-id="c072b-144">The model uses machine learning to determine the likelihood that a document contains content that is legal in nature.</span></span> <span data-ttu-id="c072b-145">Außerdem werden die Teilnehmer von Dokumenten mit einer Anwaltsliste verglichen (die Sie beim Einrichten des Modells übermitteln), um festzustellen, ob ein Dokument über mindestens einen Teilnehmer verfügt, der Anwalt ist.</span><span class="sxs-lookup"><span data-stu-id="c072b-145">It also compares the participants of documents with an attorney list (that you submit when setting up the model) to determine if a document has at least one participant who is an attorney.</span></span>

<span data-ttu-id="c072b-146">Weitere Informationen zum Einrichten und Verwenden des Anwalts-Client-Berechtigungserkennungsmodells finden Sie unter [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span><span class="sxs-lookup"><span data-stu-id="c072b-146">For more information about setting up and using the attorney-client privilege detection model, see [Set up attorney-client privilege detection in Advanced eDiscovery](attorney-privilege-detection.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c072b-147">Dies ist ein optionaler Schritt, den Sie jederzeit ausführen können.</span><span class="sxs-lookup"><span data-stu-id="c072b-147">This is an optional step that you can perform anytime.</span></span> <span data-ttu-id="c072b-148">Wenn Sie das Erkennungsmodell für Anwalts-Client-Rechte nicht implementieren, können Sie keine Advanced eDiscovery erstellen.</span><span class="sxs-lookup"><span data-stu-id="c072b-148">Not implementing the attorney-client privilege detection model doesn't prevent you from creating and using Advanced eDiscovery cases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c072b-149">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c072b-149">Next steps</span></span>

<span data-ttu-id="c072b-150">Nachdem Sie die Advanced eDiscovery eingerichtet haben, können Sie [einen Fall erstellen.](create-and-manage-advanced-ediscoveryv2-case.md)</span><span class="sxs-lookup"><span data-stu-id="c072b-150">After you set up Advanced eDiscovery, you're ready to [create a case](create-and-manage-advanced-ediscoveryv2-case.md).</span></span>