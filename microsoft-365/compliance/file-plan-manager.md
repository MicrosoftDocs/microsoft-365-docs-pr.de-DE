---
title: Übersicht über den Dateiplan-Manager
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: af398293-c69d-465e-a249-d74561552d30
description: Der Dateiplan-Manager bietet erweiterte Verwaltungsfunktionen für Aufbewahrungsbezeichnungen, Aufbewahrungsbezeichnungsrichtlinien und bietet eine integrierte Möglichkeit, Bezeichnungen und Bezeichnung-zu-Inhalt-Aktivitäten in Ihrem gesamten Inhaltslebenszyklus zu durchlaufen – von der Erstellung über die Zusammenarbeit, die Datensatzdeklaration, die Aufbewahrung hin zur Disposition.
ms.openlocfilehash: 38bfb1e6a6cde931804e518660ddf6c2b45205b0
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081549"
---
# <a name="overview-of-file-plan-manager"></a><span data-ttu-id="6fa8e-103">Übersicht über den Dateiplan-Manager</span><span class="sxs-lookup"><span data-stu-id="6fa8e-103">Overview of file plan manager</span></span>

<span data-ttu-id="6fa8e-104">Der Dateiplan-Manager bietet erweiterte Verwaltungsfunktionen für Aufbewahrungsbezeichnungen, Aufbewahrungsbezeichnungsrichtlinien und bietet eine integrierte Möglichkeit, Bezeichnungen und Bezeichnung-zu-Inhalt-Aktivitäten in Ihrem gesamten Inhaltslebenszyklus zu durchlaufen – von der Erstellung über die Zusammenarbeit, die Datensatzdeklaration, die Aufbewahrung hin zur Disposition.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-104">File plan manager provides advanced management capabilities for retention labels and policies, and provides an integrated way to traverse label and label-to-content activity for your entire content lifecycle – from creation, through collaboration, record declaration, retention, and finally disposition.</span></span>

![Dateiplanseite](media/file-plan-page.png)

## <a name="accessing-file-plan-manager"></a><span data-ttu-id="6fa8e-106">Zugriff auf den Dateiplan-Manager</span><span class="sxs-lookup"><span data-stu-id="6fa8e-106">Accessing file plan manager</span></span>

<span data-ttu-id="6fa8e-107">Es gibt die folgenden beiden Anforderungen für den Zugriff auf den Dateiplan-Manager:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-107">There are two requirements to access file plan manager, they are:</span></span>
- <span data-ttu-id="6fa8e-108">Ein Office 365 Enterprise E5-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-108">An Office 365 Enterprise E5 subscription.</span></span>
- <span data-ttu-id="6fa8e-109">Der Benutzer wurde einer der folgenden Rollen des Security &amp; Compliance Centers zugewiesen:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-109">The user has been in assigned one of the following roles of the Security &amp; Compliance Center:</span></span>
    - <span data-ttu-id="6fa8e-110">Aufbewahrungs-Manager</span><span class="sxs-lookup"><span data-stu-id="6fa8e-110">Retention Manager</span></span>
    - <span data-ttu-id="6fa8e-111">Aufbewahrungs-Manager (schreibgeschützt)</span><span class="sxs-lookup"><span data-stu-id="6fa8e-111">View-only Retention Manager</span></span>

## <a name="default-retention-labels-and-label-policy"></a><span data-ttu-id="6fa8e-112">Standardmäßige Aufbewahrungsbezeichnung und Bezeichnungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="6fa8e-112">Default retention labels and label policy</span></span>

<span data-ttu-id="6fa8e-113">Wenn keine Aufbewahrungsbezeichnungen im Security & Compliance Center vorhanden sind, wird, wenn Sie im linken Navigationsbereich **Dateiplan** auswählen, eine Bezeichnungsrichtlinie mit dem Namen **Standardmäßige Veröffentlichungsrichtlinie für Datengovernance** erstellt.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-113">If there are no retention labels in the Security & Compliance Center, the first time you choose **File plan** in the left nav, this creates a label policy called **Default Data Governance Publishing Policy**.</span></span> 

<span data-ttu-id="6fa8e-114">Diese Bezeichnungsrichtlinie enthält drei Aufbewahrungsbezeichnungen:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-114">This label policy contains three retention labels:</span></span>

- <span data-ttu-id="6fa8e-115">**Operative Prozesse**</span><span class="sxs-lookup"><span data-stu-id="6fa8e-115">**Operational procedure**</span></span>
- <span data-ttu-id="6fa8e-116">**Allgemeines Geschäft**</span><span class="sxs-lookup"><span data-stu-id="6fa8e-116">**Business general**</span></span>
- <span data-ttu-id="6fa8e-117">**Vertragliche Vereinbarung**</span><span class="sxs-lookup"><span data-stu-id="6fa8e-117">**Contract agreement**</span></span>

<span data-ttu-id="6fa8e-118">Diese Aufbewahrungsbezeichnungen sind so konfiguriert, dass Inhalte nur aufbewahrt, aber nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-118">These retention labels are configured only to retain content, not delete content.</span></span> <span data-ttu-id="6fa8e-119">Diese Bezeichnungsrichtlinie wird in der gesamten Organisation veröffentlicht und kann deaktiviert oder entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-119">This label policy will be published to the entire organization and can be disabled or removed.</span></span> 

<span data-ttu-id="6fa8e-120">Sie können feststellen, wer den Dateiplan-Manager geöffnet und den Eindruck beim ersten Ausführen gestartet hat, indem Sie das Überwachungsprotokoll für die Aktivitäten **Erstellte Aufbewahrungsrichtlinie** und **Erstellte Konfiguration für eine Aufbewahrungsrichtlinie** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-120">You can determine who opened file plan manager and kicked off the first-run experience by reviewing the audit log for the activities **Created retention policy** and **Created retention configuration for a retention policy**.</span></span>

> [!NOTE]
> <span data-ttu-id="6fa8e-121">Aufgrund von Kundenfeedback haben wir dieses Feature entfernt, durch das die standardmäßigen Aufbewahrungsbezeichnungen und die oben genannte Aufbewahrungsbezeichnungsrichtlinie erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-121">Due to customer feedback, we have removed this feature that creates the default retention labels and label policy mentioned above.</span></span> <span data-ttu-id="6fa8e-122">Diese Aufbewahrungsbezeichnungen und Aufbewahrungsbezeichnungsrichtlinien werden Ihnen nur dann angezeigt, wenn Sie den Datei-Plan-Manager vor dem 11. April 2019 geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-122">You will only see this policy and labels if you used file plan manager before April 11, 2019.</span></span>

## <a name="navigating-your-file-plan"></a><span data-ttu-id="6fa8e-123">Navigieren in Ihrem Dateiplan</span><span class="sxs-lookup"><span data-stu-id="6fa8e-123">Navigating your file plan</span></span>

<span data-ttu-id="6fa8e-124">Mit dem Dateiplan-Manager können Sie leichter die Einstellungen aller Aufbewahrungsbezeichnungen und Richtlinien aus einer Ansicht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-124">File plan manager makes it easier see into and across the settings of all your retention labels and policies from one view.</span></span>

<span data-ttu-id="6fa8e-125">Beachten Sie, dass Aufbewahrungsbezeichnungen, die außerhalb des Dateiplans erstellt wurden, im Dateiplan verfügbar sind und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-125">Note that retention labels created outside of the file plan will be available in the file plan and vice versa.</span></span>

<span data-ttu-id="6fa8e-126">Auf den Registerkarten für die **Dateiplanbezeichnungen** sind die folgenden zusätzlichen Informationen und Funktionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-126">On the **file plan labels** tab, the following additional information and capabilities are available:</span></span>

### <a name="label-settings-columns"></a><span data-ttu-id="6fa8e-127">Spalten mit Bezeichnungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="6fa8e-127">Label settings columns</span></span>

- <span data-ttu-id="6fa8e-p103">**Basierend auf** gibt den Typ des Auslösers an, der den Aufbewahrungszeitraum starten kann. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-p103">**Based on** identifies the type of trigger that will start the retention period. Valid values are:</span></span>
    - <span data-ttu-id="6fa8e-130">Ereignis</span><span class="sxs-lookup"><span data-stu-id="6fa8e-130">Event</span></span>
    - <span data-ttu-id="6fa8e-131">Zeitpunkt der Erstellung</span><span class="sxs-lookup"><span data-stu-id="6fa8e-131">When created</span></span>
    - <span data-ttu-id="6fa8e-132">Zeitpunkt der letzten Änderung</span><span class="sxs-lookup"><span data-stu-id="6fa8e-132">When last modified</span></span>
    - <span data-ttu-id="6fa8e-133">Zeitpunkt der Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="6fa8e-133">When labeled</span></span>
- <span data-ttu-id="6fa8e-p104">**Datensatz** gibt an, ob das Element ein deklarierter Datensatz werden kann, wenn die Bezeichnung angewendet wurde. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-p104">**Record** identifies if the item will become a declared record when the label is applied. Valid values are:</span></span>
    - <span data-ttu-id="6fa8e-136">Nein</span><span class="sxs-lookup"><span data-stu-id="6fa8e-136">No</span></span>
    - <span data-ttu-id="6fa8e-137">Ja</span><span class="sxs-lookup"><span data-stu-id="6fa8e-137">Yes</span></span>
    - <span data-ttu-id="6fa8e-138">Yes (Vorgeschrieben)</span><span class="sxs-lookup"><span data-stu-id="6fa8e-138">Yes(Regulatory)</span></span>
- <span data-ttu-id="6fa8e-p105">**Aufbewahrung** gibt den Aufbewahrungstyp an. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-p105">**Retention** identifies the retention type. Valid values are:</span></span>
    - <span data-ttu-id="6fa8e-141">Beibehalten</span><span class="sxs-lookup"><span data-stu-id="6fa8e-141">Keep</span></span>
    - <span data-ttu-id="6fa8e-142">Beibehalten und löschen</span><span class="sxs-lookup"><span data-stu-id="6fa8e-142">Keep and delete</span></span>
    - <span data-ttu-id="6fa8e-143">Löschen</span><span class="sxs-lookup"><span data-stu-id="6fa8e-143">Delete</span></span>
- <span data-ttu-id="6fa8e-p106">**Disposition** gibt an, was mit dem Inhalt am Ende des Aufbewahrungszeitraums geschieht. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-p106">**Disposition** identifies what will happen to the content at the end of the retention period. Valid values are:</span></span>
    - <span data-ttu-id="6fa8e-146">Null</span><span class="sxs-lookup"><span data-stu-id="6fa8e-146">null</span></span>
    - <span data-ttu-id="6fa8e-147">Keine Aktion</span><span class="sxs-lookup"><span data-stu-id="6fa8e-147">No action</span></span>
    - <span data-ttu-id="6fa8e-148">Automatisch löschen</span><span class="sxs-lookup"><span data-stu-id="6fa8e-148">Auto-delete</span></span>
    - <span data-ttu-id="6fa8e-149">Überprüfung erforderlich (auch bezeichnet als Dispositionsprüfung)</span><span class="sxs-lookup"><span data-stu-id="6fa8e-149">Review required (aka Disposition review)</span></span>

![Bezeichnungseinstellungen im Dateiplan](media/file-plan-label-columns.png)

### <a name="retention-label-file-plan-descriptors-columns"></a><span data-ttu-id="6fa8e-151">Spalten mit Dateiplanbeschreibungen für Aufbewahrungsbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="6fa8e-151">Label file plan descriptors columns</span></span>

<span data-ttu-id="6fa8e-p107">Sie können nun mehr Informationen in die Konfiguration Ihrer Aufbewahrungsbezeichnungen einschließen. Durch Einfügen von Dateiplanbeschreibungen in Aufbewahrungsbezeichnungen können Sie die Verwaltbarkeit und Organisation Ihres Dateiplans verbessern.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-p107">You can now include more information in the configuration of your retention labels. Inserting file plan descriptors into labels will improve the manageability and organization of your file plan.</span></span>

<span data-ttu-id="6fa8e-p108">Für den Einstieg stellt Dateiplan-Manager einige einsatzbereite Werte für Folgendes bereit: Funktion/Abteilung, Kategorie, Autoritätstyp und Bereitstellung. Sie können neue Werte für die Dateiplanbeschreibung hinzufügen, wenn Sie eine Aufbewahrungsbezeichnung erstellen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-p108">To get you started, file plan manager provides some out-of-box values for: Function/department, Category, Authority type and Provision/citation. You can add new file plan descriptor values when creating or editing a retention label.</span></span>

<span data-ttu-id="6fa8e-156">Nachfolgend finden Sie eine Übersicht der Dateiplanbeschreibungen beim Erstellen oder Bearbeiten einer Aufbewahrungsbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-156">Here's a view of the file plan descriptors step when creating or editing a retention label.</span></span>

![Dateiplanbeschreibungen](media/file-plan-descriptors.png)

<span data-ttu-id="6fa8e-158">Nachfolgend finden Sie eine Übersicht über die Spalten mit Dateiplanbeschreibungen auf der Registerkarte „Bezeichnungen“ des Dateiplan-Managers.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-158">Here's a view of the file plan descriptors columns on the labels tab of file plan manager.</span></span>

![file-plan-descriptors-on-labels-tab.png](media/file-plan-descriptors-on-labels-tab.png)

## <a name="export-all-existing-retention-labels-to-analyze-andor-perform-offline-reviews"></a><span data-ttu-id="6fa8e-160">Exportieren aller vorhandenen Aufbewahrungsbezeichnungen zum Analysieren und/oder Durchführen von Offline Überprüfungen</span><span class="sxs-lookup"><span data-stu-id="6fa8e-160">Export all existing retention labels to analyze and/or perform offline reviews</span></span>

<span data-ttu-id="6fa8e-161">Aus dem Dateiplan-Manager können Sie die Details aller Aufbewahrungsbezeichnungen in eine CSV-Datei exportieren, mit deren Hilfe Sie regelmäßige Complianceüberprüfungen mit den Beteiligten an der Datengovernance in Ihrer Organisation durchführen können.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-161">From file plan manager, you can export the details of all retention labels into a .csv file to assist you in facilitating periodic compliance reviews with data governance stakeholders in your organization.</span></span>

<span data-ttu-id="6fa8e-162">Um alle Aufbewahrungsbezeichnungen zu exportieren, gehen Sie zu **Dateiplan-Manager** \> **Dateiplanaktionen** \> **Bezeichnungen exportieren**.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-162">To export all retention labels, go to **file plan manager** \> **file plan actions** \> **export labels**.</span></span>

![Option zum Exportieren des Dateiplans](media/file-plan-export-labels-option.png)

<span data-ttu-id="6fa8e-164">Es wird eine CSV-Datei mit allen vorhandenen Aufbewahrungsbeschriftungen geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-164">A \*.csv file containing all existing retention labels will open.</span></span>

![CSV-Datei, in der alle Aufbewahrungsbeschriftungen angezeigt werden](media/file-plan-csv-file.png)

## <a name="import-retention-labels-into-your-file-plan"></a><span data-ttu-id="6fa8e-166">Importieren von Aufbewahrungsbezeichnungen in Ihren Dateiplan</span><span class="sxs-lookup"><span data-stu-id="6fa8e-166">Import labels into your file plan</span></span>

<span data-ttu-id="6fa8e-167">Aus dem Dateiplan-Manager können Sie neue Aufbewahrungsbezeichnungen massenimportieren und vorhandene Aufbewahrungsbezeichnungen ändern.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-167">From file plan manager, you can bulk import new labels as well as modify existing retention labels.</span></span>

<span data-ttu-id="6fa8e-168">Zum Importieren von neuen Aufbewahrungsbeschriftungen und zum Aktualisieren von vorhandenen Aufbewahrungsbezeichnungen gehen Sie zu **Dateiplan-Manager** \> **Dateiplanaktionen** \> **Bezeichnungen importieren**.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-168">To import new retention labels and make updates existing retention labels, go to **file plan manager** \> **file plan actions** \> **import labels**.</span></span>

![Option zum Importieren des Dateiplans](media/file-plan-import-labels-option.png)

![Option zum Herunterladen einer leeren Vorlage für den Dateiplan](media/file-plan-blank-template-option.png)

<span data-ttu-id="6fa8e-171">Laden Sie eine leere Vorlage herunter (oder beginnen Sie mit einem Export Ihres aktuellen Dateiplans).</span><span class="sxs-lookup"><span data-stu-id="6fa8e-171">Download a blank template (or start from an export of your current file plan).</span></span>

![Leere Vorlage eines Dateiplans, geöffnet in Excel](media/file-plan-blank-template.png)

<span data-ttu-id="6fa8e-173">Füllen Sie die Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-173">Fill-out the template.</span></span> <span data-ttu-id="6fa8e-174">Diese Tabelle enthält gültige Werte.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-174">This table provides valid values.</span></span>

|<span data-ttu-id="6fa8e-175">**Eigenschaft**</span><span class="sxs-lookup"><span data-stu-id="6fa8e-175">**Property**</span></span>|<span data-ttu-id="6fa8e-176">**Typ**</span><span class="sxs-lookup"><span data-stu-id="6fa8e-176">**Type**</span></span>|<span data-ttu-id="6fa8e-177">**Gültige Werte**</span><span class="sxs-lookup"><span data-stu-id="6fa8e-177">**Valid values**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6fa8e-178">LabelName</span><span class="sxs-lookup"><span data-stu-id="6fa8e-178">LabelName</span></span>|<span data-ttu-id="6fa8e-179">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-179">String</span></span>|<span data-ttu-id="6fa8e-180">Wenn der Wert Leerzeichen enthält, setzen Sie ihn in Anführungszeichen (").</span><span class="sxs-lookup"><span data-stu-id="6fa8e-180">If the value contains spaces, enclose the value in quotation marks (").</span></span>|
|<span data-ttu-id="6fa8e-181">Comment</span><span class="sxs-lookup"><span data-stu-id="6fa8e-181">Comment</span></span>|<span data-ttu-id="6fa8e-182">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-182">String</span></span>|<span data-ttu-id="6fa8e-183">Wenn der Wert Leerzeichen enthält, setzen Sie ihn in Anführungszeichen (").</span><span class="sxs-lookup"><span data-stu-id="6fa8e-183">If the value contains spaces, enclose the value in quotation marks (").</span></span> |
|<span data-ttu-id="6fa8e-184">Notes</span><span class="sxs-lookup"><span data-stu-id="6fa8e-184">Notes</span></span>|<span data-ttu-id="6fa8e-185">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-185">String</span></span>|<span data-ttu-id="6fa8e-186">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-186">Custom</span></span>|
|<span data-ttu-id="6fa8e-187">IsRecordLabel</span><span class="sxs-lookup"><span data-stu-id="6fa8e-187">IsRecordLabel</span></span>|<span data-ttu-id="6fa8e-188">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-188">String</span></span>|<span data-ttu-id="6fa8e-189">$true: Die Bezeichnung ist eine Datensatzbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-189">The label is a record label.</span></span></br><span data-ttu-id="6fa8e-190">$false: Die Bezeichnung ist keine Datensatzbezeichnung.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-190">The label isn't a record label.</span></span> <span data-ttu-id="6fa8e-191">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-191">This is the default value.</span></span>|
|<span data-ttu-id="6fa8e-192">RetentionAction</span><span class="sxs-lookup"><span data-stu-id="6fa8e-192">RetentionAction</span></span>|<span data-ttu-id="6fa8e-193">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-193">String</span></span>|<span data-ttu-id="6fa8e-194">Delete</span><span class="sxs-lookup"><span data-stu-id="6fa8e-194">Delete</span></span></br><span data-ttu-id="6fa8e-195">Keep</span><span class="sxs-lookup"><span data-stu-id="6fa8e-195">Keep</span></span></br><span data-ttu-id="6fa8e-196">KeepAndDelete</span><span class="sxs-lookup"><span data-stu-id="6fa8e-196">KeepAndDelete</span></span> |
|<span data-ttu-id="6fa8e-197">RetentionDuration</span><span class="sxs-lookup"><span data-stu-id="6fa8e-197">RetentionDuration</span></span>|<span data-ttu-id="6fa8e-198">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-198">String</span></span>|<span data-ttu-id="6fa8e-199">Die Eigenschaft gibt die Anzahl der Tage an, die der Inhalt aufbewahrt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-199">The RetentionDuration parameter specifies the number of days to retain the content.</span></span> <span data-ttu-id="6fa8e-200">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-200">Valid values are:</span></span></br><span data-ttu-id="6fa8e-201">Positive Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-201">A positive integer.</span></span></br><span data-ttu-id="6fa8e-202">Der Wert ist unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-202">The default value is unlimited.</span></span>|
|<span data-ttu-id="6fa8e-203">RetentionType</span><span class="sxs-lookup"><span data-stu-id="6fa8e-203">RetentionType</span></span>|<span data-ttu-id="6fa8e-204">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-204">String</span></span>|<span data-ttu-id="6fa8e-205">Diese Eigenschaft gibt an, ob die Aufbewahrungsdauer aus dem Erstellungsdatum des Inhalts, dem Datum der Bezeichnung (Markierung) oder aus dem Datum der letzten Änderung berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-205">The RetentionType parameter specifies whether the retention duration is calculated  from the content creation date, tagged date, or last modification date.</span></span> <span data-ttu-id="6fa8e-206">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-206">Valid values are:</span></span></br><span data-ttu-id="6fa8e-207">CreationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="6fa8e-207">CreationAgeInDays</span></span></br><span data-ttu-id="6fa8e-208">EventAgeInDays</span><span class="sxs-lookup"><span data-stu-id="6fa8e-208">EventAgeInDays</span></span></br><span data-ttu-id="6fa8e-209">ModificationAgeInDays</span><span class="sxs-lookup"><span data-stu-id="6fa8e-209">ModificationAgeInDays</span></span></br><span data-ttu-id="6fa8e-210">TaggedAgeInDays</span><span class="sxs-lookup"><span data-stu-id="6fa8e-210">TaggedAgeInDays</span></span> |
|<span data-ttu-id="6fa8e-211">ReviewerEmail</span><span class="sxs-lookup"><span data-stu-id="6fa8e-211">ReviewerEmail</span></span>|<span data-ttu-id="6fa8e-212">SmtpAddress[]</span><span class="sxs-lookup"><span data-stu-id="6fa8e-212">SmtpAddress</span></span>|<span data-ttu-id="6fa8e-213">Diese Eigenschaft gibt die E-Mail-Adresse des Bearbeiters für Aufbewahrungsaktionen vom Typ "Delete" und "KeepAndDelete" an.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-213">The ReviewerEmail parameter specifies the email address of a reviewer for Delete and KeepAndDelete retention actions.</span></span> <span data-ttu-id="6fa8e-214">Mehrere E-Mail-Adressen können durch Kommas getrennt angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-214">You can specify multiple email addresses separated by commas.</span></span>|
|<span data-ttu-id="6fa8e-215">ReferenceId</span><span class="sxs-lookup"><span data-stu-id="6fa8e-215">ReferenceId</span></span>|<span data-ttu-id="6fa8e-216">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-216">String</span></span>|<span data-ttu-id="6fa8e-217">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-217">Custom</span></span>|
|<span data-ttu-id="6fa8e-218">DepartmentName</span><span class="sxs-lookup"><span data-stu-id="6fa8e-218">Departmentname</span></span>|<span data-ttu-id="6fa8e-219">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-219">String</span></span>|<span data-ttu-id="6fa8e-220">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-220">Custom</span></span>|
|<span data-ttu-id="6fa8e-221">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6fa8e-221">Category</span></span>|<span data-ttu-id="6fa8e-222">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-222">String</span></span>|<span data-ttu-id="6fa8e-223">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-223">Custom</span></span>|
|<span data-ttu-id="6fa8e-224">SubCategory</span><span class="sxs-lookup"><span data-stu-id="6fa8e-224">SubCategory</span></span>|<span data-ttu-id="6fa8e-225">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-225">String</span></span>|<span data-ttu-id="6fa8e-226">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-226">Custom</span></span>|
|<span data-ttu-id="6fa8e-227">AuthorityType</span><span class="sxs-lookup"><span data-stu-id="6fa8e-227">AuthorityType</span></span>|<span data-ttu-id="6fa8e-228">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-228">String</span></span>|<span data-ttu-id="6fa8e-229">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-229">Custom</span></span>|
|<span data-ttu-id="6fa8e-230">CitationName</span><span class="sxs-lookup"><span data-stu-id="6fa8e-230">CitationName</span></span>|<span data-ttu-id="6fa8e-231">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-231">String</span></span>|<span data-ttu-id="6fa8e-232">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-232">Custom</span></span>|
|<span data-ttu-id="6fa8e-233">CitationUrl</span><span class="sxs-lookup"><span data-stu-id="6fa8e-233">CitationUrl</span></span>|<span data-ttu-id="6fa8e-234">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-234">String</span></span>|<span data-ttu-id="6fa8e-235">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-235">Custom</span></span>|
|<span data-ttu-id="6fa8e-236">CitationJurisdiction</span><span class="sxs-lookup"><span data-stu-id="6fa8e-236">CitationJurisdiction</span></span>|<span data-ttu-id="6fa8e-237">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-237">String</span></span>|<span data-ttu-id="6fa8e-238">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-238">Custom</span></span>|
|<span data-ttu-id="6fa8e-239">Regulatory</span><span class="sxs-lookup"><span data-stu-id="6fa8e-239">Regulatory</span></span>|<span data-ttu-id="6fa8e-240">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-240">String</span></span>|<span data-ttu-id="6fa8e-241">Custom</span><span class="sxs-lookup"><span data-stu-id="6fa8e-241">Custom</span></span>|
|<span data-ttu-id="6fa8e-242">EventType</span><span class="sxs-lookup"><span data-stu-id="6fa8e-242">EventType</span></span>|<span data-ttu-id="6fa8e-243">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6fa8e-243">String</span></span>|<span data-ttu-id="6fa8e-244">Diese Eigenschaft gibt die Aufbewahrungsregel an, die der Bezeichnung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-244">The 
                EventType
              specifies the retention rule that's associated with the label.</span></span> <span data-ttu-id="6fa8e-245">Sie können einen beliebigen Wert verwenden, der die Regel eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-245">You can use any value that uniquely identifies the rule.</span></span> <span data-ttu-id="6fa8e-246">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6fa8e-246">For example:</span></span></br><span data-ttu-id="6fa8e-247">Name</span><span class="sxs-lookup"><span data-stu-id="6fa8e-247">Name</span></span></br><span data-ttu-id="6fa8e-248">Distinguished Name (DN)</span><span class="sxs-lookup"><span data-stu-id="6fa8e-248">Distinguished name (DN)</span></span></br><span data-ttu-id="6fa8e-249">GUID</span><span class="sxs-lookup"><span data-stu-id="6fa8e-249">GUID</span></span> </br><span data-ttu-id="6fa8e-250">Mit dem Cmdlet [Get-RetentionComplianceRule](https://docs.microsoft.com/de-DE/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) können Sie die verfügbaren Aufbewahrungsregeln anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-250">You can use the [Get-RetentionComplianceRule](https://docs.microsoft.com/en-us/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule?view=exchange-ps) cmdlet to view the available retention rules.</span></span>|

![Dateiplanvorlage mit ausgefüllten Informationen](media/file-plan-filled-out-template.png)

<span data-ttu-id="6fa8e-252">Laden Sie die ausgefüllte Vorlage hoch; die Einträge werden dann vom Dateiplan-Manager überprüft, und es werden Importstatistiken angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-252">Upload the filled-out template, and file plan manager will validate the entries and display import statistics.</span></span>

![Dateiplan-Importstatistiken](media/file-plan-import-statistics.png)

<span data-ttu-id="6fa8e-254">Für den Fall, dass ein Überprüfungsfehler vorliegt, überprüft der Dateiplanimport weiterhin jeden Eintrag in der Importdatei und zeigt alle Fehler an, wobei er die Zeilen-/Reihennummern in der Importdatei referenziert und die angezeigten Fehlerergebnisse kopiert, damit Sie einfach zur Importdatei zurückkehren und die Fehler korrigieren können.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-254">In the event there is a validation error, file plan import will continue to validate every entry in the import file and display all errors referencing line/row numbers in the import file, copy the displayed error results so that you can easilly return to the import file and correct the errors.</span></span> 

<span data-ttu-id="6fa8e-255">Wenn der Importvorgang abgeschlossen ist, kehren Sie zum Dateiplan-Manager zurück, um neuen oder vorhandenen Aufbewahrungsbezeichnungsrichtlinien neue Aufbewahrungsbezeichnungen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6fa8e-255">When the import is complete, return to file plan manager to assign new labels to new or existing policies.</span></span>

![Option zum Veröffentlichen von Bezeichnungen](media/file-plan-publish-labels-option.png)

