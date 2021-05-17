---
title: Verwenden der Freigabeüberwachung im Überwachungsprotokoll
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
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: Administratoren erfahren, wie Sie die Freigabeüberwachung im Überwachungsprotokoll Microsoft 365 verwenden, um Ressourcen zu identifizieren, die für Benutzer außerhalb ihrer Organisation freigegeben wurden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d26a8022f8d59aeb56a03c50ae546777c882ef7a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819295"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Verwenden der Freigabeüberwachung im Überwachungsprotokoll

Die Freigabe ist eine wichtige Aktivität in SharePoint Online und OneDrive for Business und wird in Organisationen häufig verwendet. Administratoren können die Freigabeüberwachung im Überwachungsprotokoll verwenden, um zu bestimmen, wie die Freigabe in ihrer Organisation verwendet wird. 
  
## <a name="the-sharepoint-sharing-schema"></a>Das SharePoint Freigabeschema

Freigabeereignisse (ohne Ereignisse im Zusammenhang mit Freigaberichtlinien und Freigabelinks) unterscheiden sich von datei- und ordnerbezogenen Ereignissen auf eine primäre Weise: Ein Benutzer macht eine Aktion, die auswirkungen auf einen anderen Benutzer hat. Beispielsweise, wenn eine Ressource Benutzer A Benutzer B Zugriff auf eine Datei gewährt. In diesem Beispiel ist Benutzer A der *handelnde Benutzer und* Benutzer B der *Zielbenutzer.* Im SharePoint Dateischema wirkt sich die Aktion des handelnden Benutzers nur auf die Datei selbst aus. Wenn Benutzer A eine Datei öffnet, sind die einzigen Informationen, die im **FileAccessed-Ereignis** benötigt werden, der handelnde Benutzer. Um diesen Unterschied zu erkennen, gibt es ein separates Schema namens *SharePoint Freigabeschema,* das weitere Informationen zu Freigabeereignissen erfasst. Dadurch wird sichergestellt, dass Administratoren einblicken können, wer eine Ressource freigegeben hat, und den Benutzer, für den die Ressource freigegeben wurde. 
  
Das Freigabeschema stellt zwei zusätzliche Felder in einem Überwachungsdatensatz im Zusammenhang mit Freigabeereignissen zur Verfügung: 
  
- **TargetUserOrGroupType:** Gibt an, ob der Zielbenutzer oder die Zielgruppe Mitglied, Gast, SharePointGroup, SecurityGroup oder Partner ist.

- **TargetUserOrGroupName:** Speichert den UPN oder den Namen des Zielbenutzers oder der Gruppe, für den eine Ressource freigegeben wurde (Benutzer B im vorherigen Beispiel). 

Diese beiden Felder können neben anderen Eigenschaften aus dem Überwachungsprotokollschema, z. B. Benutzer,  Vorgang  und Datum, den vollständigen Bericht darüber erzählen, welcher Benutzer welche Ressource für wen und wann freigegeben *hat.*  
  
Es gibt eine weitere Schemaeigenschaft, die für die Freigabegeschichte wichtig ist. Wenn Sie Die Suchergebnisse des Überwachungsprotokolls exportieren, speichert die **Spalte AuditData** in der exportierten CSV-Datei Informationen zu Freigabeereignissen. Wenn ein Benutzer z. B. eine Website für einen anderen Benutzer teilt, wird dies durch Hinzufügen des Zielbenutzers zu einer gruppe SharePoint erreicht. Die **Spalte AuditData** erfasst diese Informationen, um Kontext für Administratoren zu bieten. Anweisungen zum Analysieren der Informationen in der Spalte **AuditData** finden Sie unter Schritt [2.](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log)

## <a name="sharepoint-sharing-events"></a>SharePoint von Freigabeereignissen

Die Freigabe wird definiert, wenn ein Benutzer *(der* handelnde Benutzer) eine Ressource für einen anderen Benutzer (den *Zielbenutzer) freigeben* möchte. Überwachungsdatensätze im Zusammenhang mit der Freigabe einer Ressource für einen externen Benutzer (ein Benutzer, der sich außerhalb Ihrer Organisation befindet und kein Gastkonto im Azure Active Directory Ihrer Organisation hat) werden durch die folgenden Ereignisse identifiziert, die im Überwachungsprotokoll protokolliert werden:

- **SharingInvitationCreated:** Ein Benutzer in Ihrer Organisation hat versucht, eine Ressource (wahrscheinlich eine Website) mit einem externen Benutzer zu teilen. Dies führt zu einer externen Freigabeeinladung, die an den Zielbenutzer gesendet wird. Zu diesem Zeitpunkt wird kein Zugriff auf die Ressource gewährt.

- **SharingInvitationAccepted:** Der externe Benutzer hat die vom handelnden Benutzer gesendete Freigabeeinladung angenommen und hat nun Zugriff auf die Ressource.

- **AnonymousLinkCreated:** Für eine Ressource wird ein anonymer Link (auch "Jeder"-Link genannt) erstellt. Da ein anonymer Link erstellt und dann kopiert werden kann, kann davon ausgegangen werden, dass jedes Dokument mit einem anonymen Link für einen Zielbenutzer freigegeben wurde.

- **AnonymousLinkUsed:** Wie der Name schon sagt, wird dieses Ereignis protokolliert, wenn ein anonymer Link für den Zugriff auf eine Ressource verwendet wird. 

- **SecureLinkCreated:** Ein Benutzer hat einen "bestimmten Personenlink" erstellt, um eine Ressource für eine bestimmte Person zu teilen. Bei diesem Zielbenutzer kann es sich um eine Person außerhalb Ihrer Organisation handelt. Die Person, für die die Ressource freigegeben ist, wird im Überwachungsdatensatz für das **AddedToSecureLink-Ereignis** identifiziert. Die Zeitstempel für diese beiden Ereignisse sind nahezu identisch.

- **AddedToSecureLink:** Einem bestimmten Personenlink wurde ein Benutzer hinzugefügt. Verwenden Sie in diesem Ereignis das **Feld TargetUserOrGroupName,** um den Benutzer zu identifizieren, der dem entsprechenden bestimmten Personenlink hinzugefügt wurde. Bei diesem Zielbenutzer kann es sich um eine Person außerhalb Ihrer Organisation handelt.

## <a name="sharing-auditing-work-flow"></a>Freigabe des Überwachungsarbeitsflusses
  
Wenn ein Benutzer (der handelnde Benutzer) eine Ressource für einen anderen Benutzer (den Zielbenutzer) freigeben möchte, überprüft SharePoint (oder OneDrive for Business) zuerst, ob die E-Mail-Adresse des Zielbenutzers bereits einem Benutzerkonto im Verzeichnis der Organisation zugeordnet ist. Wenn sich der Zielbenutzer im Verzeichnis befindet (und über ein entsprechendes Gastbenutzerkonto verfügt), führt SharePoint die folgenden Schritte aus:
  
-  Weist sofort den Zielbenutzerberechtigungen für den Zugriff auf die Ressource zu, indem der Zielbenutzer der entsprechenden SharePoint hinzugefügt wird, und protokolliert ein **AddedToGroup-Ereignis.** 
    
- Sendet eine Freigabebenachrichtigung an die E-Mail-Adresse des Zielbenutzers.
    
- Protokolliert ein **SharingSet-Ereignis.** Dieses Ereignis hat den Anzeigenamen "Freigegebene Datei, Ordner oder Website" unter **Freigabe-** und Zugriffsanforderungsaktivitäten in der Aktivitätenauswahl des Überwachungsprotokollsuchtools. Siehe Screenshot in [Schritt 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file). 
    
Wenn sich ein Benutzerkonto für den Zielbenutzer nicht im Verzeichnis befindet, führt SharePoint die folgenden Schritte aus: 
    
   - Protokolliert eines der folgenden Ereignisse, je nachdem, wie die Ressource freigegeben wird:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (dieses Ereignis wird nur protokolliert, wenn es sich bei der freigegebenen Ressource um eine Website handelt)
    
   - Wenn der Zielbenutzer die an ihn gesendete Freigabeeinladung akzeptiert (indem er auf den Link in der Einladung klickt), protokolliert SharePoint ein **SharingInvitationAccepted-Ereignis** und weist den Zielbenutzerberechtigungen den Zugriff auf die Ressource zu. Wenn dem Zielbenutzer ein anonymer Link gesendet wird, wird das **AnonymousLinkUsed-Ereignis** protokolliert, nachdem der Zielbenutzer den Link zum Zugriff auf die Ressource verwendet hat. Bei sicheren Links wird **ein FileAccessed-Ereignis** protokolliert, wenn ein externer Benutzer den Link verwendet, um auf die Ressource zuzugreifen.

Weitere Informationen zum Zielbenutzer werden ebenfalls protokolliert, z. B. die Identität des Benutzers, an den die Einladung eingeladen wird, und der Benutzer, der die Einladung akzeptiert. In einigen Fällen können diese Benutzer (oder E-Mail-Adressen) unterschiedlich sein. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Identifizieren von Ressourcen, die für externe Benutzer freigegeben wurden

Eine allgemeine Anforderung für Administratoren ist das Erstellen einer Liste aller Ressourcen, die für Benutzer außerhalb der Organisation freigegeben wurden. Mithilfe der Freigabeüberwachung in Office 365 Können Administratoren diese Liste generieren. Die gehen so:
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Schritt 1: Suchen nach Freigabeereignissen und Exportieren der Ergebnisse in eine CSV-Datei

Der erste Schritt besteht im Durchsuchen des Überwachungsprotokolls nach Freigabeereignissen. Weitere Informationen (einschließlich der erforderlichen Berechtigungen) zum Durchsuchen des Überwachungsprotokolls finden Sie unter Durchsuchen des Überwachungsprotokolls im [Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im Security & Compliance Center im linken Bereich auf **Suchen**   > **Überwachungsprotokollsuche**.
    
    Die Seite **Überwachungsprotokollsuche** wird angezeigt. 
    
4. Klicken **Sie unter Aktivitäten** auf **Freigabe- und Zugriffsanforderungsaktivitäten,** um nach Freigabeereignissen zu suchen. 
    
    ![Wählen Sie unter Aktivitäten die Option Freigabe- und Zugriffsanforderungsaktivitäten aus.](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Wählen Sie einen Datums- und Zeitbereich aus, um die Freigabeereignisse zu finden, die innerhalb dieses Zeitraums aufgetreten sind. 
    
6. Klicken Sie **auf Suchen,** um die Suche ausführen zu können. 
    
7. Wenn die Suche abgeschlossen ist und die Ergebnisse angezeigt werden, klicken Sie auf **Ergebnisse exportieren** Alle \> **Ergebnisse herunterladen.**
    
    Nachdem Sie die Exportoption ausgewählt haben, werden Sie in einer Meldung am unteren Rand des Fensters aufgefordert, die CSV-Datei zu öffnen oder zu speichern.
    
8. Klicken **Sie auf** Speichern unter, und speichern Sie die \>  CSV-Datei in einem Ordner auf Dem lokalen Computer. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Schritt 2: Formatieren des exportierten Überwachungsprotokolls mithilfe des PowerQuery-Editors

Im nächsten Schritt wird das JSON-Transformationsfeature im Power Query Editor in Excel verwendet, um jede Eigenschaft in der **Spalte AuditData** (die aus einem JSON-Objekt mit mehreren Eigenschaften besteht) in eine eigene Spalte zu teilen. Auf diese Weise können Sie Spalten filtern, um Datensätze im Zusammenhang mit der Freigabe anzuzeigen

Schrittweise Anleitungen finden Sie unter "Schritt 2: Formatieren von exportierten Überwachungsprotokollen mithilfe des Power Query-Editors" in [Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Schritt 3: Filtern der CSV-Datei nach Ressourcen, die für externe Benutzer freigegeben sind

Im nächsten Schritt wird die CSV nach den verschiedenen freigabebezogenen Ereignissen gefiltert, die zuvor im Abschnitt SharePoint [der Freigabeereignisse beschrieben](#sharepoint-sharing-events) wurden. Alternativ können Sie die **Spalte TargetUserOrGroupType** so filtern, dass alle Datensätze angezeigt werden, bei denen der Wert dieser Eigenschaft **Guest ist.** 

Nachdem Sie die Anweisungen im vorherigen Schritt zum Vorbereiten der CSV-Datei mithilfe des PowerQuery-Editors befolgt haben, gehen Sie wie folgt vor:
    
1. Öffnen Sie Excel Datei, die Sie in Schritt 2 erstellt haben. 

2. Klicken Sie **auf der** Registerkarte Start auf Sortieren **& Filter**, und klicken Sie dann auf **Filtern**.
    
3. Löschen Sie in der **Dropdownliste** &  Filter sortieren in der Spalte Vorgänge alle Auswahlen, wählen Sie dann ein oder mehrere der folgenden Freigabeereignisse aus, und klicken Sie dann auf **Ok**.
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel zeigt die Zeilen für die ausgewählten Ereignisse an.
    
4. Wechseln Sie zur Spalte **TargetUserOrGroupType,** und wählen Sie sie aus. 
    
5. Löschen Sie **in & Dropdownliste** Sortieren und Filtern alle Auswahlen, wählen Sie **dann TargetUserOrGroupType:Guest** aus, und klicken Sie auf **Ok**.
    
    Jetzt Excel die Zeilen für Freigabeereignisse und für den Zielbenutzer außerhalb Ihrer Organisation angezeigt, da externe Benutzer durch den Wert **TargetUserOrGroupType:Guest identifiziert werden.** 
  
> [!TIP]
> Für die angezeigten Überwachungsdatensätze identifiziert die **Spalte ObjectId** die Ressource, die für den Zielbenutzer freigegeben wurde. beispiel:  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .
