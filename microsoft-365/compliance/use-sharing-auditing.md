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
description: 'Die Freigabe ist eine wichtige Aktivität in SharePoint Online und OneDrive für Unternehmen. Administratoren können jetzt die Freigabe Überwachung im Überwachungsprotokoll verwenden, um Ressourcen zu identifizieren, die für Benutzer außerhalb Ihrer Organisation freigegeben wurden. '
ms.openlocfilehash: 63b56831dc5409cc92a0c4a2f4bf002cd268a878
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626381"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Verwenden der Freigabeüberwachung im Überwachungsprotokoll

Die Freigabe ist eine wichtige Aktivität in SharePoint Online und OneDrive für Unternehmen und wird in Organisationen häufig verwendet. Administratoren können die Freigabe Überwachung im Überwachungsprotokoll verwenden, um zu bestimmen, wie die Freigabe in Ihrer Organisation verwendet wird. 
  
## <a name="the-sharepoint-sharing-schema"></a>Das SharePoint-Freigabe Schema

Freigabe Ereignisse (nicht einschließlich der Ereignisse im Zusammenhang mit Freigaberichtlinien und Freigabelinks) unterscheiden sich in erster Linie von Datei-und ordnerbezogenen Ereignissen: ein Benutzer führt eine Aktion aus, die sich auf einen anderen Benutzer auswirkt. Wenn beispielsweise ein Ressourcen Benutzer a dem Benutzer B Zugriff auf eine Datei gewährt. In diesem Beispiel ist Benutzer A der *stellvertretende Benutzer* , und Benutzer B ist der *Zielbenutzer*. Im SharePoint-Datei Schema wirkt sich die Aktion des handelnden Benutzers nur auf die Datei selbst aus. Wenn Benutzer a eine Datei öffnet, sind die einzigen Informationen, die im **fileaccessed** -Ereignis erforderlich sind, der Benutzer, der fungiert. Um diesen Unterschied zu beheben, gibt es ein separates Schema, das als *SharePoint-Freigabe Schema*bezeichnet wird und in dem weitere Informationen zur Freigabe von Ereignissen erfasst werden. Dadurch wird sichergestellt, dass Administratoren Einblick in die Person haben, die eine Ressource freigegeben hat, und den Benutzer, für den die Ressource freigegeben wurde. 
  
Das Freigabe Schema stellt zwei zusätzliche Felder in einem Überwachungseintrag im Zusammenhang mit Freigabe Ereignissen bereit: 
  
- **TargetUserOrGroupType:** Gibt an, ob der Zielbenutzer oder die Zielgruppe Mitglied, Gast, share pointgroup, SecurityGroup oder Partner ist.

- **TargetUserOrGroupName:** Speichert den UPN oder Namen des Zielbenutzers oder der Zielgruppe, für die eine Ressource freigegeben wurde (Benutzer B im vorherigen Beispiel). 

Diese beiden Felder können zusätzlich zu anderen Eigenschaften aus dem Überwachungsprotokoll Schema wie "User", "Operation" und "Date" die ganze Geschichte darüber erzählen, *welcher* Benutzer *welche* Ressource mit *wem* und *wann*freigegeben hat. 
  
Es gibt eine andere Schemaeigenschaft, die für den Freigabe Text wichtig ist. Wenn Sie Überwachungsprotokoll-Suchergebnisse exportieren, werden in der **Auditdata** -Spalte in der exportierten CSV-Dateiinformationen zu Freigabe Ereignissen gespeichert. Wenn ein Benutzer beispielsweise eine Website für einen anderen Benutzer freigibt, wird dies erreicht, indem der Zielbenutzer einer SharePoint-Gruppe hinzugefügt wird. Die **Auditdata** -Spalte erfasst diese Informationen, um Administratoren Kontext bereitzustellen. In [Schritt 2](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) finden Sie Anweisungen zum Analysieren der Informationen in der Spalte **Auditdata** .

## <a name="sharepoint-sharing-events"></a>SharePoint-Freigabe Ereignisse

Die Freigabe wird definiert, wenn ein Benutzer (der *Stell* Ende Benutzer) eine Ressource für einen anderen Benutzer freigeben möchte (den *Ziel* Benutzer). Überwachungsdatensätze im Zusammenhang mit der Freigabe einer Ressource für einen externen Benutzer (ein Benutzer, der sich außerhalb Ihrer Organisation befindet und kein Gastkonto in der Azure-Active Directory Ihrer Organisation hat) werden durch die folgenden Ereignisse identifiziert, die im Überwachungsprotokoll protokolliert werden:

- **SharingInvitationCreated:** Ein Benutzer in Ihrer Organisation hat versucht, eine Ressource (wahrscheinlich eine Website) mit einem externen Benutzer freizugeben. Dies führt dazu, dass eine externe Freigabeeinladung an den Zielbenutzer gesendet wird. Zu diesem Zeitpunkt wird kein Zugriff auf die Ressource gewährt.

- **SharingInvitationAccepted:** Der externe Benutzer hat die von dem handelnden Benutzer gesendete Freigabeeinladung akzeptiert und hat nun Zugriff auf die Ressource.

- **AnonymousLinkCreated:** Für eine Ressource wird ein anonymer Link (auch als "jeder"-Link bezeichnet) erstellt. Da ein anonymer Link erstellt und dann kopiert werden kann, ist es sinnvoll anzunehmen, dass jedes Dokument mit einem anonymen Link für einen Zielbenutzer freigegeben wurde.

- **AnonymousLinkUsed:** Wie der Name schon sagt, wird dieses Ereignis protokolliert, wenn ein anonymer Link für den Zugriff auf eine Ressource verwendet wird. 

- **SecureLinkCreated:** Ein Benutzer hat einen "bestimmten Personen Link" erstellt, um eine Ressource für eine bestimmte Person freizugeben. Dieser Zielbenutzer kann jemand sein, der sich außerhalb Ihrer Organisation befindet. Die Person, für die die Ressource freigegeben wurde, wird im Überwachungseintrag für das **AddedToSecureLink** -Ereignis identifiziert. Die Zeitstempel für diese beiden Ereignisse sind nahezu identisch.

- **AddedToSecureLink:** Ein Benutzer wurde einem bestimmten Personen Link hinzugefügt. Verwenden Sie das Feld **TargetUserOrGroupName** in diesem Ereignis, um den Benutzer zu identifizieren, der dem entsprechenden Link für bestimmte Personen hinzugefügt wurde. Dieser Zielbenutzer kann jemand sein, der sich außerhalb Ihrer Organisation befindet.

## <a name="sharing-auditing-work-flow"></a>Freigabe Überwachungs Workflow
  
Wenn ein Benutzer (der stellvertretender Benutzer) eine Ressource für einen anderen Benutzer (den Zielbenutzer) freigeben möchte, überprüft SharePoint (oder OneDrive für Unternehmen) zunächst, ob die e-Mail-Adresse des Zielbenutzers bereits einem Benutzerkonto im Verzeichnis der Organisation zugeordnet ist. Wenn sich der Zielbenutzer im Verzeichnis befindet (und über ein entsprechendes Gastbenutzerkonto verfügt), führt SharePoint folgende Schritte aus:
  
-  Weist sofort die Zielbenutzer Berechtigungen für den Zugriff auf die Ressource zu, indem der Zielbenutzer der entsprechenden SharePoint-Gruppe hinzugefügt wird, und protokolliert ein **AddedToGroup** -Ereignis. 
    
- Sendet eine Freigabe Benachrichtigung an die e-Mail-Adresse des Zielbenutzers.
    
- Protokolliert ein **sharingset** -Ereignis. Dieses Ereignis weist den Anzeigenamen "freigegebene Datei, Ordner oder Website" unter **Freigabe-und Zugriffs Anforderungs Aktivitäten** in der Aktivitäts Auswahl des Überwachungsprotokoll-Such Tools auf. Siehe Screenshot in [Schritt 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file). 
    
Wenn sich ein Benutzerkonto für den Zielbenutzer nicht im Verzeichnis befindet, führt SharePoint Folgendes aus: 
    
   - Protokolliert eines der folgenden Ereignisse, je nachdem, wie die Ressource freigegeben wird:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (dieses Ereignis wird nur protokolliert, wenn es sich bei der freigegebenen Ressource um eine Website handelt)
    
   - Wenn der Zielbenutzer die an Sie gesendete Freigabeeinladung annimmt (durch Klicken auf den Link in der Einladung), protokolliert SharePoint ein **SharingInvitationAccepted** -Ereignis und weist den Zielbenutzer Berechtigungen für den Zugriff auf die Ressource zu. Wenn dem Zielbenutzer ein anonymer Link gesendet wird, wird das **AnonymousLinkUsed** -Ereignis protokolliert, nachdem der Zielbenutzer den Link für den Zugriff auf die Ressource verwendet hat. Für sichere Links wird ein **fileaccessed** -Ereignis protokolliert, wenn ein externer Benutzer den Link für den Zugriff auf die Ressource verwendet.

Weitere Informationen zum Zielbenutzer werden ebenfalls protokolliert, beispielsweise die Identität des Benutzers, an den die Einladung erfolgt, und der Benutzer, der die Einladung annimmt. In einigen Fällen können diese Benutzer (oder e-Mail-Adressen) unterschiedlich sein. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Vorgehensweise identifizieren von Ressourcen, die für externe Benutzer freigegeben sind

Eine häufige Anforderung an Administratoren ist das Erstellen einer Liste aller Ressourcen, die für Benutzer außerhalb der Organisation freigegeben wurden. Mithilfe der Freigabe Überwachung in Office 365 können Administratoren diese Liste generieren. Die gehen so:
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Schritt 1: Suchen nach Freigabe Ereignissen und Exportieren der Ergebnisse in eine CSV-Datei

Der erste Schritt besteht darin, das Überwachungsprotokoll nach Freigabe Ereignissen zu durchsuchen. Weitere Informationen (einschließlich der erforderlichen Berechtigungen) zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.
    
3. Klicken Sie im Security & Compliance Center im linken Bereich auf **Suchen**   > **Überwachungsprotokollsuche**.
    
    Die Seite **Überwachungsprotokollsuche** wird angezeigt. 
    
4. Klicken Sie unter **Aktivitäten**auf **Freigabe-und Zugriffs Anforderungs Aktivitäten** , um nach Freigabe bezogenen Ereignissen zu suchen. 
    
    ![Wählen Sie unter Aktivitäten die Option Freigabe-und Zugriffs Anforderungs Aktivitäten aus.](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  Wählen Sie einen Datums-und Zeitbereich aus, um die Freigabe Ereignisse zu finden, die innerhalb dieses Zeitraums aufgetreten sind. 
    
6. Klicken Sie auf **Suchen** , um die Suche auszuführen. 
    
7. Wenn die Suche abgeschlossen ist und die Ergebnisse angezeigt werden, klicken Sie auf **Ergebnisse** \> exportieren **alle Ergebnisse herunterladen**.
    
    Nachdem Sie die Option Exportieren ausgewählt haben, werden Sie im unteren Bereich des Fensters aufgefordert, die CSV-Datei zu öffnen oder zu speichern.
    
8. Klicken Sie auf Save **As** **Speichern** \> und speichern Sie die CSV-Datei in einem Ordner auf Ihrem lokalen Computer. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Schritt 2: Formatieren des exportierten Überwachungsprotokolls mithilfe des PowerQuery-Editors

Im nächsten Schritt wird das JSON-Transformations Feature im Power Query-Editor in Excel verwendet, um die einzelnen Eigenschaften in der **Auditdata** -Spalte (die aus einem JSON-Objekt mit mehreren Eigenschaften besteht) in eine eigene Spalte aufzuteilen. Auf diese Weise können Sie Spalten filtern, um Datensätze im Zusammenhang mit Freigabe anzuzeigen.

Eine Schritt-für-Schritt-Anleitung finden Sie unter "Schritt 2: Formatieren des exportierten Überwachungsprotokolls mit dem Power Query Editor" unter [exportieren, konfigurieren und Anzeigen von Überwachungsprotokolldaten Sätzen](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Schritt 3: Filtern der CSV-Datei nach Ressourcen, die für externe Benutzer freigegeben sind

Der nächste Schritt besteht darin, die CSV-Datei für die verschiedenen Freigabe bezogenen Ereignisse zu filtern, die zuvor im Abschnitt [SharePoint-Freigabe Ereignisse](#sharepoint-sharing-events) beschrieben wurden. Alternativ können Sie die **TargetUserOrGroupType** -Spalte filtern, um alle Datensätze anzuzeigen, bei denen der Wert dieser Eigenschaft **Gast**ist. 

Nachdem Sie die Anweisungen im vorherigen Schritt zum Vorbereiten der CSV-Datei mithilfe des PowerQuery-Editors befolgt haben, gehen Sie wie folgt vor:
    
1. Öffnen Sie die Excel-Datei, die Sie in Schritt 2 erstellt haben. 

2. Klicken Sie auf der Registerkarte **Start** auf **& Filter sortieren**, und klicken Sie dann auf **Filter**.
    
3. Deaktivieren Sie in der Dropdownliste **Sort & Filter** in der Spalte **Vorgänge** die Option Alle Optionen, und wählen Sie dann mindestens einen der folgenden Freigabe bezogenen Ereignisse aus, und klicken Sie dann auf **OK**.
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel zeigt die Zeilen für die Ereignisse an, die Sie ausgewählt haben.
    
4. Wechseln Sie zur Spalte mit dem Namen **TargetUserOrGroupType** , und wählen Sie Sie aus. 
    
5. Deaktivieren Sie in der Dropdownliste **Sortier & Filter** die Option alle Auswahlen, wählen Sie **TargetUserOrGroupType: Gast**aus, und klicken Sie dann auf **OK**.
    
    In Excel werden nun die Zeilen für Freigabe Ereignisse und die Position des Zielbenutzers außerhalb Ihrer Organisation angezeigt, da externe Benutzer durch den Wert **TargetUserOrGroupType: Guest**identifiziert werden. 
  
> [!TIP]
> Für die angezeigten Überwachungsdatensätze identifiziert die **objectID** -Spalte die Ressource, die für den Zielbenutzer freigegeben wurde. zum Beispiel `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`.
