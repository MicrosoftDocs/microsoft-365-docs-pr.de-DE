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
description: Der Administrator kann erfahren, wie die Freigabeüberwachung im Microsoft 365 Überwachungsprotokoll verwendet wird, um Ressourcen zu identifizieren, die für Benutzer außerhalb ihrer Organisation freigegeben wurden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 302ad7665c83ee9061b2e1965ef03ec25d0aab58
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341508"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>Verwenden der Freigabeüberwachung im Überwachungsprotokoll

Die Freigabe ist eine wichtige Aktivität in SharePoint Online- und OneDrive for Business und wird häufig in Organisationen verwendet. Administratoren können die Freigabeüberwachung im Überwachungsprotokoll verwenden, um zu bestimmen, wie die Freigabe in ihrer Organisation verwendet wird. 
  
## <a name="the-sharepoint-sharing-schema"></a>Das SharePoint-Freigabeschema

Freigabeereignisse (ohne Ereignisse im Zusammenhang mit Freigaberichtlinien und Freigabelinks) unterscheiden sich primär von Datei- und Ordnerereignissen: Ein Benutzer führt eine Aktion aus, die sich auf einen anderen Benutzer auswirkt. Beispielsweise, wenn eine Ressource Benutzer A Benutzer B Zugriff auf eine Datei gewährt. In diesem Beispiel ist Benutzer A der *handelnde Benutzer* und Benutzer B der *Zielbenutzer.* Im SharePoint Dateischema wirkt sich die Aktion des handelnden Benutzers nur auf die Datei selbst aus. Wenn Benutzer A eine Datei öffnet, sind die einzigen im **FileAccessed-Ereignis** benötigten Informationen der handelnde Benutzer. Um diesen Unterschied zu beheben, gibt es ein separates Schema, das *als SharePoint Freigabeschema* bezeichnet wird und weitere Informationen zu Freigabeereignissen erfasst. Dadurch wird sichergestellt, dass Administratoren Einblicke darin haben, für wen eine Ressource freigegeben wurde und für wen die Ressource freigegeben wurde. 
  
Das Freigabeschema stellt zwei zusätzliche Felder in einem Überwachungsdatensatz im Zusammenhang mit Freigabeereignissen bereit: 
  
- **TargetUserOrGroupType:** Gibt an, ob der Zielbenutzer oder die Zielgruppe Mitglied, Gast, SharePointGroup, SecurityGroup oder Partner ist.

- **TargetUserOrGroupName:** Speichert den UPN oder namen des Zielbenutzers oder der Zielgruppe, für den bzw. die eine Ressource freigegeben wurde (Benutzer B im vorherigen Beispiel). 

Diese beiden Felder können zusätzlich zu anderen Eigenschaften aus dem Überwachungsprotokollschema, z. B. Benutzer, Vorgang und Datum, den vollständigen Bericht darüber  *vermitteln, welcher*  Benutzer  *welche*  Ressource für  *wen*  und  *wann* freigegeben hat. 
  
Es gibt eine weitere Schemaeigenschaft, die für die Freigabe wichtig ist. Wenn Sie Die Suchergebnisse des Überwachungsprotokolls exportieren, werden in der **Spalte "AuditData"** in der exportierten CSV-Datei Informationen zu Freigabeereignissen gespeichert. Wenn ein Benutzer beispielsweise eine Website für einen anderen Benutzer teilt, wird dies erreicht, indem der Zielbenutzer einer SharePoint Gruppe hinzugefügt wird. In **der Spalte "AuditData" werden** diese Informationen erfasst, um Administratoren Kontext bereitzustellen. Anweisungen zum Analysieren der Informationen in der **Spalte "AuditData"** finden Sie in [Schritt 2.](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log)

## <a name="sharepoint-sharing-events"></a>SharePoint Freigabeereignisse

Die Freigabe wird definiert, wenn ein Benutzer (der *handelnde* Benutzer) eine Ressource für einen anderen Benutzer (den *Zielbenutzer)* freigeben möchte. Überwachungsdatensätze im Zusammenhang mit der Freigabe einer Ressource für einen externen Benutzer (ein Benutzer, der sich außerhalb Ihrer Organisation befindet und kein Gastkonto im Azure Active Directory Ihrer Organisation hat) werden durch die folgenden Ereignisse identifiziert, die im Überwachungsprotokoll protokolliert werden:

- **SharingInvitationCreated:** Ein Benutzer in Ihrer Organisation hat versucht, eine Ressource (wahrscheinlich eine Website) für einen externen Benutzer freizugeben. Dies führt zu einer externen Freigabe-Einladung, die an den Zielbenutzer gesendet wird. An dieser Stelle wird kein Zugriff auf die Ressource gewährt.

- **SharingInvitationAccepted:** Der externe Benutzer hat die vom handelnden Benutzer gesendete Freigabe-Einladung angenommen und hat nun Zugriff auf die Ressource.

- **AnonymousLinkCreated:** Ein anonymer Link (auch als "Jeder"-Link bezeichnet) wird für eine Ressource erstellt. Da ein anonymer Link erstellt und dann kopiert werden kann, kann davon ausgegangen werden, dass alle Dokumente, die einen anonymen Link haben, für einen Zielbenutzer freigegeben wurden.

- **AnonymousLinkUsed:** Wie der Name schon sagt, wird dieses Ereignis protokolliert, wenn ein anonymer Link für den Zugriff auf eine Ressource verwendet wird. 

- **SecureLinkCreated:** Ein Benutzer hat einen "bestimmten Personenlink" erstellt, um eine Ressource für eine bestimmte Person freizugeben. Bei diesem Zielbenutzer kann es sich um eine Person außerhalb Ihrer Organisation handelt. Die Person, für die die Ressource freigegeben ist, wird im Überwachungsdatensatz für das **AddedToSecureLink-Ereignis** identifiziert. Die Zeitstempel für diese beiden Ereignisse sind nahezu identisch.

- **AddedToSecureLink:** Ein Benutzer wurde einem bestimmten Personenlink hinzugefügt. Verwenden Sie das **TargetUserOrGroupName-Feld** in diesem Ereignis, um den Benutzer zu identifizieren, der dem entsprechenden spezifischen Personenlink hinzugefügt wurde. Bei diesem Zielbenutzer kann es sich um eine Person außerhalb Ihrer Organisation handelt.

## <a name="sharing-auditing-work-flow"></a>Freigabeüberwachungs-Arbeitsablauf
  
Wenn ein Benutzer (der handelnde Benutzer) eine Ressource für einen anderen Benutzer (den Zielbenutzer) freigeben möchte, überprüft SharePoint (oder OneDrive for Business), ob die E-Mail-Adresse des Zielbenutzers bereits einem Benutzerkonto im Verzeichnis der Organisation zugeordnet ist. Wenn sich der Zielbenutzer im Verzeichnis befindet (und über ein entsprechendes Gastbenutzerkonto verfügt), führt SharePoint die folgenden Aktionen aus:
  
-  Weist sofort die Berechtigungen des Zielbenutzers für den Zugriff auf die Ressource zu, indem der Zielbenutzer der entsprechenden SharePoint-Gruppe hinzugefügt wird, und protokolliert ein **AddedToGroup-Ereignis.** 
    
- Sendet eine Freigabebenachrichtigung an die E-Mail-Adresse des Zielbenutzers.
    
- Protokolliert ein **SharingSet-Ereignis.** Dieses Ereignis hat den Anzeigenamen "Freigegebene Datei, Ordner oder Website" unter **"Freigabe- und Zugriffsanforderungsaktivitäten"** in der Aktivitätenauswahl des Überwachungsprotokoll-Suchtools. Sehen Sie sich den Screenshot in [Schritt 1](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file)an. 
    
Wenn sich ein Benutzerkonto für den Zielbenutzer nicht im Verzeichnis befindet, führt SharePoint folgende Aktionen aus: 
    
   - Protokolliert eines der folgenden Ereignisse basierend auf der Art und Weise, wie die Ressource freigegeben wird:
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated** (dieses Ereignis wird nur protokolliert, wenn die freigegebene Ressource eine Website ist)
    
   - Wenn der Zielbenutzer die Freigabeeinladung annimmt, die an ihn gesendet wird (durch Klicken auf den Link in der Einladung), protokolliert SharePoint ein **SharingInvitationAccepted-Ereignis** und weist die Berechtigungen des Zielbenutzers für den Zugriff auf die Ressource zu. Wenn dem Zielbenutzer ein anonymer Link gesendet wird, wird das **AnonymousLinkUsed-Ereignis** protokolliert, nachdem der Zielbenutzer den Link für den Zugriff auf die Ressource verwendet hat. Bei sicheren Links wird ein **FileAccessed-Ereignis** protokolliert, wenn ein externer Benutzer den Link für den Zugriff auf die Ressource verwendet.

Zusätzliche Informationen über den Zielbenutzer werden ebenfalls protokolliert, z. B. die Identität des Benutzers, dem die Einladung zugeordnet ist, und des Benutzers, der die Einladung annimmt. In einigen Fällen können diese Benutzer (oder E-Mail-Adressen) unterschiedlich sein. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>Identifizieren von Ressourcen, die für externe Benutzer freigegeben sind

Eine allgemeine Anforderung für Administratoren ist das Erstellen einer Liste aller Ressourcen, die für Benutzer außerhalb der Organisation freigegeben wurden. Mithilfe der Freigabeüberwachung in Office 365 können Administratoren diese Liste generieren. Die gehen so:
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>Schritt 1: Suchen nach Freigabeereignissen und Exportieren der Ergebnisse in eine CSV-Datei

Der erste Schritt besteht darin, das Überwachungsprotokoll nach Freigabeereignissen zu durchsuchen. Weitere Informationen (einschließlich der erforderlichen Berechtigungen) zum Durchsuchen des Überwachungsprotokolls finden Sie unter [Durchsuchen des Überwachungsprotokolls im Security & Compliance Center.](search-the-audit-log-in-security-and-compliance.md)
  
1. Wechseln Sie zu <https://compliance.microsoft.com>.

2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.

3. Klicken Sie im linken Bereich des Microsoft 365 Compliance Center auf **"Überwachen".**

    Die Seite **Überwachung** wird angezeigt.

4. Klicken Sie unter **"Aktivitäten"** auf **"Freigabe- und Zugriffsanforderungsaktivitäten",** um nach freigabebezogenen Ereignissen zu suchen. 

    ![Wählen Sie unter "Aktivitäten" die Option "Freigabe- und Zugriffsanforderungsaktivitäten" aus.](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. Wählen Sie einen Datums- und Uhrzeitbereich aus, um die Freigabeereignisse zu finden, die innerhalb dieses Zeitraums aufgetreten sind. 

6. Klicken Sie auf **"Suchen",** um die Suche auszuführen. 

7. Wenn die Suche abgeschlossen ist und die Ergebnisse angezeigt werden, klicken Sie auf **"Ergebnisse** \> **exportieren" alle Ergebnisse herunterladen.**

    Nachdem Sie die Exportoption ausgewählt haben, werden Sie in einer Meldung am unteren Rand des Fensters aufgefordert, die CSV-Datei zu öffnen oder zu speichern.

8. Klicken  Sie auf \> **Speichern unter,** und speichern Sie die CSV-Datei in einem Ordner auf Ihrem lokalen Computer. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>Schritt 2: Verwenden des PowerQuery-Editors zum Formatieren des exportierten Überwachungsprotokolls

Der nächste Schritt besteht darin, das JSON-Transformationsfeature im Power Query Editor in Excel zu verwenden, um jede Eigenschaft in der **AuditData-Spalte** (die aus einem JSON-Objekt mit mehreren Eigenschaften besteht) in eine eigene Spalte aufzuteilen. Auf diese Weise können Sie Spalten filtern, um Datensätze im Zusammenhang mit der Freigabe anzuzeigen.

Schrittweise Anleitungen finden Sie unter "Schritt 2: Formatieren von exportierten Überwachungsprotokollen mithilfe des Power Query-Editors" in [Exportieren, Konfigurieren und Anzeigen von Überwachungsprotokoll-Datensätzen](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor).

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>Schritt 3: Filtern der CSV-Datei nach Ressourcen, die für externe Benutzer freigegeben wurden

Der nächste Schritt besteht darin, die CSV-Datei nach den verschiedenen freigabebezogenen Ereignissen zu filtern, die zuvor im Abschnitt [SharePoint Freigabeereignisse](#sharepoint-sharing-events) beschrieben wurden. Alternativ können Sie die **Spalte "TargetUserOrGroupType"** filtern, um alle Datensätze anzuzeigen, bei denen der Wert dieser Eigenschaft **"Guest"** lautet. 

Nachdem Sie die Anweisungen im vorherigen Schritt befolgt haben, um die CSV-Datei mithilfe des PowerQuery-Editors vorzubereiten, gehen Sie wie folgt vor:
    
1. Öffnen Sie die Excel Datei, die Sie in Schritt 2 erstellt haben. 

2. Klicken Sie auf der Registerkarte **"Start"** auf **"Sortieren" & "Filtern",** und klicken Sie dann auf **"Filtern".**
    
3. Löschen Sie in der Dropdownliste **Sortieren &** Filtern in der Spalte **Vorgänge** alle Auswahlen, wählen Sie dann eines oder mehrere der folgenden freigabebezogenen Ereignisse aus, und klicken Sie dann auf **OK.**
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel zeigt die Zeilen für die ausgewählten Ereignisse an.
    
4. Wechseln Sie zur Spalte mit dem Namen **TargetUserOrGroupType,** und wählen Sie sie aus. 
    
5. Löschen Sie in der Dropdownliste **Sortieren &** Filtern alle Auswahlen, wählen Sie **"TargetUserOrGroupType:Guest" aus,** und klicken Sie auf **"Ok".**
    
    Jetzt zeigt Excel die Zeilen für die Freigabe von Ereignissen und den Ort an, an dem sich der Zielbenutzer außerhalb Ihrer Organisation befindet, da externe Benutzer durch den Wert **TargetUserOrGroupType:Guest** identifiziert werden. 
  
> [!TIP]
> Für die angezeigten Überwachungsdatensätze identifiziert die **Spalte "ObjectId"** die Ressource, die für den Zielbenutzer freigegeben wurde. Beispiel:  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` .
