---
title: Übersicht über Dispositions Überprüfungen
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Wenn Sie eine Aufbewahrungs Bezeichnung erstellen, in der Inhalte in Microsoft 365 aufbewahrt werden, können Sie eine Dispositions Überprüfung am Ende des Aufbewahrungszeitraums auslösen.
ms.openlocfilehash: 8dafaf45df0d681880ef513c9feab6b833c99cb8
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595230"
---
# <a name="overview-of-disposition-reviews"></a>Übersicht über Dispositions Überprüfungen

Wenn der Inhalt das Ende seines Aufbewahrungszeitraums erreicht, gibt es mehrere Gründe, warum Sie diesen Inhalt möglicherweise überprüfen möchten, um zu entscheiden, ob er sicher gelöscht werden kann ("verworfen"). Beispielsweise müssen Sie Folgendes tun:
  
- Anhalten des Löschvorgangs ("Disposition") relevanter Inhalte im Fall eines Rechtsstreits oder einer Überprüfung.
    
- Entfernen Sie Inhalte aus der Dispositionsliste, die in einem Archiv gespeichert werden sollen, wenn diese Inhalte Forschungs-oder Verlaufswerte aufweisen.
    
- Weisen Sie dem Inhalt eine andere Beibehaltungsdauer zu, wenn es sich bei der ursprünglichen Richtlinie um eine temporäre oder provisorische Lösung handelt.
    
- Zurückgeben der Inhalte an Clients oder übertragen an eine andere Organisation.
    
Wenn Sie eine Aufbewahrungs Bezeichnung im Microsoft 365 Compliance Center, im Microsoft 365 Security Center oder im Office 365 Security #a0 Compliance Center erstellen, können Sie eine Dispositions Überprüfung am Ende des Aufbewahrungszeitraums auslösen. In einer Dispositions Überprüfung:
  
- Die Personen, die Sie auswählen, erhalten eine e-Mail-Benachrichtigung, dass Sie Inhalte zur Überprüfung haben. Bei diesen Prüfern kann es sich um einzelne Benutzer, Verteilungs-oder Sicherheitsgruppen oder Office 365 Gruppen handeln. Beachten Sie, dass Benachrichtigungen auf wöchentlicher Basis gesendet werden.
    
- Die Bearbeiter wechseln zur Seite " **Disposition** " im Security &amp; Compliance Center, um den Inhalt zu überprüfen. Die Bearbeiter können sehen, wie viele Elemente für jede Aufbewahrungs Bezeichnung auf die Disposition warten, und wählen dann eine Aufbewahrungs Bezeichnung aus, um den gesamten Inhalt mit dieser Bezeichnung anzuzeigen.
    
- Für jedes Dokument oder jede e-Mail kann der Prüfer Folgendes tun:
    
  - Wenden Sie eine andere Aufbewahrungs Bezeichnung an.
    
  - Beibehaltungsdauer verlängern.
    
  - Endgültig löschen.
    
- Bearbeiter können entweder ausstehende oder abgeschlossene Dispositionen anzeigen und diese Liste als CSV-Datei exportieren.

> [!NOTE]
> Für Dispositions Überprüfungen ist ein Office 365 Enterprise E5-Abonnement erforderlich.
  
Eine Dispositions Überprüfung kann Inhalte in Exchange-Postfächern, SharePoint-Websites, OneDrive-Konten und Office 365 Gruppen enthalten. Inhalte, die auf eine Dispositions Überprüfung an diesen Speicherorten warten, werden erst gelöscht, nachdem ein Prüfer die Inhalte endgültig gelöscht hat.
  
![Seite "Dispositions" im Security and Compliance Center](media/Retention-Dispositions-v2-page.png)


## <a name="setting-up-the-disposition-review-by-creating-a-retention-label"></a>Einrichten der Dispositions Überprüfung durch Erstellen einer Aufbewahrungs Bezeichnung

Dies ist der grundlegende Workflow zum Einrichten einer Dispositions Überprüfung. Beachten Sie, dass dieser Fluss eine Aufbewahrungs Bezeichnung zeigt, die veröffentlicht und dann manuell von einem Benutzer angewendet wird. Alternativ kann eine Aufbewahrungs Bezeichnung, die eine Dispositions Überprüfung auslöst, automatisch auf Inhalte angewendet werden.
  
![Diagramm zum Anzeigen des Ablaufs der Dispositions Funktion](media/5fb3f33a-cb53-468c-becc-6dda0ec52778.png)
  
Eine Dispositions Überprüfung ist eine Option, wenn Sie eine Aufbewahrungs Bezeichnung in Office 365 erstellen. Diese Option steht in einer Aufbewahrungsrichtlinie nicht zur Verfügung, sondern nur in einer Aufbewahrungs Bezeichnung, die für die Beibehaltung von Inhalt konfiguriert ist.
  
Weitere Informationen zu Aufbewahrungs Bezeichnungen finden Sie unter [Overview of Retention Labels](labels.md).
  
![Aufbewahrungseinstellungen für eine Bezeichnung](media/a16dd202-8862-40ac-80ff-6fee974de5da.png)
 
> [!NOTE]
> Wenn Sie die Option " **diese Personen Benachrichtigen" angeben, wenn Elemente zur Überarbeitung verfügbar sind**, geben Sie einen Benutzer oder eine e-Mail-aktivierte Sicherheitsgruppe an. Für diese Option werden Office 365 Gruppen nicht unterstützt.

## <a name="disposing-content"></a>Freigeben von Inhalten

Wenn ein Prüfer per e-Mail benachrichtigt wird, dass der Inhalt überprüft werden kann, kann er zur Seite " **Disposition** " im Security &amp; Compliance Center wechseln. Die Bearbeiter können sehen, wie viele Elemente für jede Aufbewahrungs Bezeichnung auf die Disposition warten, und wählen dann eine Aufbewahrungs Bezeichnung aus, um den gesamten Inhalt mit dieser Bezeichnung anzuzeigen.

Nachdem Sie eine Aufbewahrungs Bezeichnung ausgewählt haben, werden auf der nächsten Seite alle ausstehenden Dispositionen für diese Bezeichnung angezeigt.

![Dispositions Optionen](media/Retention-Disposition-options-v2.png)

Der Prüfer kann dann: 
  
- Wenden Sie eine andere Aufbewahrungs Bezeichnung an.
    
- Verlängern Sie den Aufbewahrungszeitraum.
    
- Löschen Sie das Element endgültig.

Beachten Sie, dass ein Prüfer mehrere Elemente auswählen und gleichzeitig freigeben kann.
    
Ein Prüfer kann auch den Link verwenden, um das Dokument an seinem ursprünglichen Speicherort anzuzeigen, wenn der Prüfer über Berechtigungen für diesen Speicherort verfügt. Während einer Dispositions Überprüfung werden die Inhalte nie von Ihrem ursprünglichen Speicherort verschoben, und Sie werden erst gelöscht, wenn sich der Bearbeiter dafür entscheidet.
  
Beachten Sie, dass die e-Mail-Benachrichtigungen wöchentlich automatisch an Prüfer gesendet werden. Wenn der Inhalt das Ende seines Aufbewahrungszeitraums erreicht, kann es bis zu sieben Tage dauern, bis die Bearbeiter die e-Mail-Benachrichtigung erhalten, dass der Inhalt auf die Disposition wartet.
  
Beachten Sie außerdem, dass alle Dispositionsaktionen überwacht werden. Um dies sicherzustellen, müssen Sie die Überwachung mindestens einen Tag vor der ersten Dispositionsaktion aktivieren – Weitere Informationen finden Sie unter [Durchsuchen des Überwachungsprotokolls im Office 365 &amp; Security Compliance Center](search-the-audit-log-in-security-and-compliance.md). 
  
## <a name="permissions-for-disposition"></a>Berechtigungen für die Disposition

Um Zugriff auf die **Dispositions** Seite zu erhalten, müssen Bearbeiter Mitglieder der **Dispositions-Verwaltungs** Rolle und der Rolle " **Überwachungsprotokolle nur anzeigen** " sein. Es wird empfohlen, eine neue Rollengruppe mit dem Namen **Dispositions Prüfer**zu erstellen und diese beiden Rollen zu dieser Rollengruppe hinzuzufügen. 

Spezifisch für die Rolle " **nur Ansichts Überwachungsprotokolle** ":

- Da es sich bei dem zugrunde liegenden Cmdlet, das zum Durchsuchen des Überwachungsprotokolls verwendet wird, um ein Exchange Online-Cmdlet handelt, müssen Sie Benutzer diese Rolle mithilfe des [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center)anstatt mithilfe der Seite **Berechtigungen** im Security #a0 Compliance Center zuweisen. Anweisungen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

- Office 365 Gruppen werden für diese Rolle nicht unterstützt. Weisen Sie stattdessen Benutzerpostfächer, e-Mail-Benutzer oder e-Mail-aktivierte Sicherheitsgruppen zu.

Anweisungen zum Erteilen von Benutzern der **Dispositions Verwaltungs** Rolle und zum Erstellen Ihrer neuen Funktion " **Dispositions Prüfer** " finden Sie unter [Erteilen von Benutzern den Zugriff auf das Office 365 Security &amp; Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
## <a name="how-long-until-disposed-content-is-permanently-deleted"></a>Wie lange, bis verworfene Inhalte endgültig gelöscht werden

Inhalte, die auf eine Dispositions Überprüfung warten, werden erst gelöscht, nachdem ein Prüfer die Inhalte endgültig gelöscht hat. Wenn der Bearbeiter diese Option auswählt, wird der Inhalt der SharePoint-Website oder des OneDrive-Kontos für den in diesem Abschnitt beschriebenen standardmäßigen Cleanupprozess zugelassen: [So funktioniert eine Aufbewahrungsrichtlinie mit Inhalten](retention-policies.md#how-a-retention-policy-works-with-content-in-place).
  
Dies bedeutet, dass:
  
- Der Inhalt in einer Dokumentbibliothek wird **innerhalb von 7 Tagen** nach der Disposition in den Papierkorb der ersten Stufe verschoben und anschließend **93 Tage** nach dem Löschen endgültig gelöscht. Der Papierkorb wird von der Suche nicht indiziert, sodass der Inhalt für einen eDiscovery-Speicher nicht verfügbar ist.

- Der Inhalt in der Aufbewahrungs Archiv-Bibliothek wird **innerhalb von 7 Tagen** nach der Disposition endgültig gelöscht.

- Elemente in einem Exchange-Postfach werden innerhalb von **14 Tagen** nach der Disposition endgültig gelöscht. (Beachten Sie, dass 14 Tage die Standardeinstellung ist, aber Sie kann bis zu 30 Tage konfiguriert werden.)
    
## <a name="view-pending-dispositions-and-disposed-items"></a>Anzeigen ausstehender Dispositionen und verworfener Elemente

Auf der Seite **ausstehende Disposition** können Sie ausstehende und abgeschlossene Dispositionen für eine bestimmte Aufbewahrungs Bezeichnung anzeigen: 
  
- Die **ausstehende Disposition** zeigt Elemente an, die das Ende Ihres Aufbewahrungszeitraums erreicht haben und eine Dispositions Überprüfung erfordern. Nachdem Sie jedes Element überprüft haben, entscheiden Sie, ob Sie eine andere Aufbewahrungs Bezeichnung anwenden möchten, den Aufbewahrungszeitraum verlängern oder endgültig löschen möchten. Sie können mehrere Elemente auswählen.
    
- Auf der Registerkarte " **verworfene Elemente** " werden Dispositionen angezeigt, die während einer Dispositions Überprüfung zum Löschen genehmigt wurden und jetzt endgültig gelöscht werden oder Elemente als Datensätze markiert wurden, die nun gelöscht wurden. Elemente, für die eine andere Aufbewahrungs Bezeichnung verwendet wurde oder deren Beibehaltungsdauer im Rahmen einer Überprüfung erweitert wurde, werden hier nicht angezeigt.

![Dispositions Registerkarten](media/Retention-Disposition-tabs.png)
    
### <a name="filter-the-disposition-views"></a>Filtern der Dispositions Ansichten

Sie können diese Ansichten nach Aufbewahrungs Bezeichnung oder Zeitbereich filtern. Für ausstehende Dispositionen basiert der Zeitbereich auf dem Ablaufdatum. Bei freigestellten Elementen basiert der Zeitbereich auf dem Löschdatum.
  
![Optionen für den Dispositions Filter](media/Retention-filter-options.png)

### <a name="export-the-disposition-items"></a>Exportieren der Dispositionselemente

Darüber hinaus können Sie die Elemente in jeder Ansicht als CSV-Datei exportieren, die Sie in Excel öffnen können.
  
![Exportierte Dispositionsdaten in Excel](media/08e3bc09-b132-47b4-a051-a590b697e725.png)
  

