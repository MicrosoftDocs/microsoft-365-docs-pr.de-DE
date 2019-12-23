---
title: Inhaltssuche in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 53390468-eec6-45cb-b6cd-7511f9c909e4
description: Verwenden Sie das Tool für die Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365, um in Postfächern, SharePoint Online-Websites, OneDrive-Konten, Microsoft Teams, Office 365-Gruppen und Skype for Business-Unterhaltungen nach Inhalten zu suchen. Sie können Schlüsselwort-Suchabfragen und Suchbedingungen verwenden, um die Suchergebnisse einzugrenzen. Anschließend können Sie die Suchergebnisse in der Vorschau anzeigen und exportieren. Die Inhaltssuche ist außerdem ein effektives Tool zum Suchen nach Inhalten, die mit einem DSGVO-Antrag einer betroffenen Person in Zusammenhang stehen.
ms.openlocfilehash: d27bce246cabfafd343286fc40ea670bfe560b9e
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967518"
---
# <a name="content-search-in-office-365"></a>Inhaltssuche in Office 365

Mithilfe des eDiscovery-Tools für die Inhaltssuche im Compliance Center in Office 365 oder Microsoft 365 können Sie nach lokalen Elementen wie E-Mails, Dokumenten und Chat-Unterhaltungen in Ihrer Office 365-Organisation suchen. Mithilfe dieses Tools können Sie nach Elementen in folgenden Office 365-Diensten suchen:
  
- Exchange-Postfächer und öffentliche Ordner
    
- SharePoint Online-Websites und OneDrive for Business-Konten
    
- Skype for Business-Unterhaltungen
    
- Microsoft Teams 
    
- Office 365-Gruppen
    
Nach dem Ausführen einer Inhaltssuche werden die Anzahl der Inhaltsspeicherorte und die geschätzte Anzahl der Suchergebnisse in den Suchstatistiken angezeigt. Sie können auch schnell Statistiken anzeigen, beispielsweise zu den inhaltsspeicherorten mit den meisten Elementen, die der Suchabfrage entsprechen. Nach dem Ausführen einer Suche können Sie eine Vorschau der Ergebnisse anzeigen oder Sie auf einen lokalen Computer exportieren.

## <a name="create-a-search"></a>Erstellen einer Suche

Um Zugriff auf die **Inhaltssuche** zu erhalten, Inhaltssuchen auszuführen und die Suchergebnisse in der Vorschau anzuzeigen, müssen Administratoren, Compliance Officer oder eDiscovery-Manager Mitglied der Rollengruppe "eDiscovery-Manager" im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
  
1. Rufen Sie die Seite [https://protection.office.com](https://protection.office.com)auf und melden Sie sich mit Ihrer E-Mail -Adresse und Ihrem Kennwort für Office 365 an.
    
2. Klicken Sie auf **Suche** \> **Inhaltssuche**.
    
3. Klicken Sie auf der Seite **Suche** auf den Pfeil neben ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Neue Suche**. 
    
    ![Die Dropdownliste "Neue Suche"](media/76b25861-55c5-4f50-9d48-9e2be2d0d078.png)
  
    Sie können eine der folgenden Optionen auswählen:
    
    - **Geführte Suche:** Bei dieser Option wird ein Assistent gestartet, der Sie durch das Erstellen der Suche führt. Die Benutzeroberflächen zum Auswählen von Inhaltsspeicherorten und Erstellen der Suchabfrage sind identisch mit jener der Option **Neue Suche**. 
    
    - **Neue Suche:** Bei dieser Option wird eine aktualisierte Benutzeroberfläche zum Erstellen einer Suche angezeigt. Dies ist die Standardoption, wenn Sie auf **Neue Suche** klicken.
    
    - **Suche anhand einer ID-Liste:** Mithilfe dieser Option können Sie nach bestimmten E-Mail-Nachrichten und anderen Postfachelementen anhand einer Liste von Exchange-IDs suchen. Zum Erstellen einer Suche anhand einer ID-Liste (formell als "gezielte Suche" bezeichnet) übermitteln Sie eine durch Trennzeichen getrennte Datei (CSV), in der die Postfachelemente angegeben werden, nach denen gesucht werden soll. Anweisungen hierzu finden Sie unter [Erstellen einer CSV-Datei für eine Inhaltssuche anhand einer ID-Liste in Office 365](csv-file-for-an-id-list-content-search.md).
    
    Die restlichen Schritte in diesem Verfahren entsprechen dem standardmäßigen neuen Such-Workflow.
    
4. Klicken Sie in der Dropdownliste auf **Neue Suche**. 
    
5. Geben Sie unter **Suchabfrage** die folgenden Elemente an:
    
    ![Geben Sie Schlüsselwörter, Bedingungen und zu durchsuchende Speicherorte an](media/1e6de9dd-eac9-4e2a-819d-9740cf6c9106.png)
  
   - **Zu suchende Schlüsselwörter:** Geben Sie eine Suchabfrage in das Feld **Schlüsselwörter** ein. Sie können Schlüsselwörter, Nachrichteneigenschaften wie das Sende- und Empfangsdatum oder Dokumenteigenschaften wie Dateinamen oder das Datum angeben, an dem ein Dokument zuletzt geändert wurde. Sie können auch komplexere Abfragen mit booleschen Operatoren wie **AND**, **OR**, **NOT** und **NEAR** verwenden. Sie können auch nach vertraulichen Informationen (z. B. Sozialversicherungsnummern) in Dokumenten oder nach Dokumenten suchen, die extern freigegeben wurden. Wenn Sie das Schlüsselwortfeld leer lassen, werden alle Inhalte in den angegebenen Inhaltsspeicherorten in die Suchergebnisse eingeschlossen.
    
      Alternativ können Sie auf das Kontrollkästchen **Schlüsselwortliste anzeigen** klicken, und dann in jede Zeile ein Schlüsselwort eingeben. Wenn Sie dies tun, werden die Schlüsselwörter in den einzelnen Zeilen der erstellten Suchabfrage mit einem logischen (**c:s**)-Operator verknüpft. Dessen Funktionsweise ist mit jener des **OR**-Operators vergleichbar. 
    
      Gründe für die Verwendung der Schlüsselwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern entsprechen. Dadurch können Sie schnell erkennen, welche Schlüsselwörter am effektivsten (und am wenigsten effektiv) sind. Sie können auch einen (in Klammern eingeschlossenen) Schlüsselwortausdruck in einer Zeile verwenden. Weitere Informationen zu Suchstatistiken finden Sie unter [Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse](view-keyword-statistics-for-content-search.md).

     > [!NOTE]
     > Um Probleme durch umfangreiche Schlüsselwortlisten zu verringern, ist die Schlüsselwortliste jetzt auf 20 Zeilen beschränkt.
    
    - **Bedingungen:** Sie können Suchbedingungen hinzufügen, um die Suche einzuschränken und eine verfeinerte Suchergebnisliste zu erhalten. Jede Bedingung fügt eine Klausel zur Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist logisch mit der Schlüsselwortabfrage (im Feld „Schlüsselwort“ angegeben) durch einen logischen (**c:s**)-Operator verknüpft. Dessen Funktionsweise ist mit jener des **OR**-Operators vergleichbar. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch eine oder mehrere Bedingungen erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können die Suchergebnisse mithilfe von Bedingungen weiter eingegrenzt werden. Eine Liste samt Beschreibung der Bedingungen, die Sie in einer Suchabfrage verwenden können, finden Sie im Abschnitt "Suchbedingungen" unter [Schlüsselwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md#search-conditions).
    
       - **Speicherorte:** Wählen Sie die Inhaltsspeicherorte aus, die durchsucht werden sollen.
    
      - **Alle Speicherorte:**  Wählen Sie diese Option aus, um sämtliche Inhaltsspeicherorte in Ihrer Organisation zu durchsuchen. Dazu zählen E-Mails in allen Exchange-Postfächern (einschließlich aller inaktiven Postfächer, Postfächer für alle Office 365-Gruppen, Postfächer für alle Microsoft Teams), alle Skype for Business-Unterhaltungen, alle SharePoint- und OneDrive for Business-Websites (einschließlich der Websites für alle Office 365-Gruppen und Microsoft Teams) sowie Elemente in allen öffentlichen Exchange-Ordnern.
    
      - **Bestimmte Speicherorte:**  Wählen Sie diese Option aus, um bestimmte Inhaltsspeicherorte zu durchsuchen. Sie können alle inhaltsspeicherorte für einen bestimmten Office 365-Dienst durchsuchen (z. B. alle Exchange-Postfächer oder alle SharePoint-Websites durchsuchen), oder in jedem der angezeigten Office 365-Dienste bestimmte Speicherorte durchsuchen. 
    
        ![Die Benutzeroberfläche zum Auswählen der Inhaltsspeicherorte, die durchsucht werden sollen](media/9a09708b-f8a2-4382-8c4e-2c610ec33c72.png)
  
         Sie können auch Verteilergruppen zur Liste der zu durchsuchenden Exchange-Postfächer hinzufügen. Bei Verteilergruppen werden die Postfächer der Gruppenmitglieder durchsucht. Dynamische Verteilergruppen werden nicht unterstützt.
    
       > [!NOTE]
       > Wenn Sie alle Postfach-Speicherorte oder nur bestimmte Postfächer durchsuchen, werden beim Exportieren der Ergebnisse einer Inhaltssuche auch Daten aus anderen Office 365-Anwendungen, die in Benutzerpostfächern gespeichert sind, einbezogen. Diese Daten werden nicht in die geschätzten Suchergebnisse einbezogen und sind für die Vorschau nicht verfügbar. Sie in den Suchergebnisse enthalten, wenn Sie diese exportieren und herunterladen. Weitere Informationen finden Sie unter [In Exchange Online-Postfächern gespeicherte Inhalte](what-is-stored-in-exo-mailbox.md).

    
6. Nachdem Sie Ihre Suchabfrage eingerichtet haben, klicken Sie auf **Speichern und ausführen**.
    
7. Geben Sie auf der Seite **Suche speichern** einen Namen für diese Suche ein sowie eine optionale Beschreibung, durch die Sie sie leichter identifizieren können. Der Name der Suche darf in Ihrer Organisation nur einmalig vorkommen. 
    
8. Klicken Sie auf **Speichern**, um die Suche zu starten. 
    
    Nachdem die Suche gespeichert und ausgeführt wurde, werden alle von der Suche zurückgegebenen Ergebnisse im Ergebnisbereich angezeigt. Je nachdem, welche Einstellungen Sie für die Vorschau gewählt haben, werden die Suchergebnisse direkt angezeigt, oder Sie müssen auf **Vorschau der Ergebnisse** klicken, um diese anzuzeigen. Ausführliche Informationen finden Sie im nächsten Abschnitt. 
    
Um erneut auf diese Inhaltssuche oder auf andere Inhaltssuchen, die auf der Seite **Inhaltssuche** aufgelistet sind, zuzugreifen, wählen Sie die gewünschte Suche aus, und klicken Sie dann auf **Öffnen**. 
  
Um die Ergebnisse zu löschen oder eine neue Suche zu erstellen, klicken Sie auf ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif) **Neue Suche**. 
  
## <a name="preview-search-results"></a>Vorschau von Suchergebnissen anzeigen

Es gibt zwei Einstellungsoptionen für die Vorschau der Suchergebnisse. Klicken Sie nach dem Ausführen einer neuen Suche oder dem Öffnen einer vorhandenen Suche auf **Einzelne Ergebnisse**, um die folgenden Vorschaueinstellungen anzuzeigen: 
  
![Einstellungen für die Vorschau von Suchergebnissen](media/83519477-1c85-4442-8886-481f186fd758.png)
  
1. **Vorschau der Ergebnisse automatisch anzeigen:** Bei dieser Einstellung werden die Suchergebnisse angezeigt, nachdem Sie eine Suche durchgeführt haben.
    
2. **Vorschau der Ergebnisse manuell anzeigen:** Bei dieser Einstellung werden Platzhalter im Ergebnisbereich sowie die Schaltfläche **Vorschau der Ergebnisse** angezeigt, auf die Sie klicken müssen, damit die Suchergebnisse angezeigt werden. Dies ist die Standardeinstellung. Dass die Suchergebnisse beim Öffnen einer vorhandenen Suche nicht automatisch angezeigt werden trägt dazu bei, die Suchleistung zu verbessern. 
    
Es gibt Beschränkungen hinsichtlich der Anzahl der Elemente, die in der Vorschau angezeigt werden können. Weitere Informationen finden Sie unter [Grenzwerte für die Inhaltssuche](limits-for-content-search.md). 
  
Eine Liste der unterstützten Dateitypen, die in der Vorschau angezeigt werden können, finden Sie unter [Vorschau von Suchergebnissen anzeigen](#previewing-search-results) im Abschnitt "Weitere Informationen zur Inhaltssuche". Wenn für den Dateityp weder die Vorschau noch das Herunterladen einer Kopie des Dokuments unterstützt wird, können Sie auf **Ursprüngliche Datei herunterladen**, um sie auf den lokalen Computer herunterzuladen. Bei ASPX-Webseiten ist die URL der Seite eingeschlossen, Sie haben möglicherweise jedoch keine Berechtigungen zum Zugriff auf die Seite. 
  
Nicht indizierte Elemente können außerdem nicht in der Vorschau angezeigt werden.
  
## <a name="view-information-and-statistics-about-a-search"></a>Anzeigen von Informationen und Statistiken zu einer Suche

Nachdem Sie eine Inhaltssuche erstellt und ausgeführt haben, können Sie Statistiken über die geschätzten Suchergebnisse anzeigen. Dies umfasst eine Übersicht über die Suchergebnisse, die Abfragestatistiken, z. B. die Anzahl der Inhaltsspeicherorte mit Elementen, die der Suchabfrage entsprechen, und die Namen von Inhaltsspeicherorten, die die meisten übereinstimmenden Objekte enthalten. Sie können Statistiken für eine oder mehrere Inhaltssuchen anzeigen. Auf diese Weise können Sie schnell die Ergebnisse für mehrere Suchvorgänge vergleichen und Entscheidungen hinsichtlich der Effektivität Ihrer Suchabfragen treffen.
  
Sie können auch die Such- und Schlüsselwortstatistik in einer CSV-Datei herunterladen. Auf diese Weise können Sie die Filter- und Sortierfunktionen in Excel dazu verwenden, um Ergebnisse zu vergleichen und Berichte für Ihre Suchergebnisse vorzubereiten.
  
So zeigen Sie Suchstatistiken an:
  
1. Klicken Sie auf der Seite **Inhaltssuche** auf **Öffnen**, und klicken Sie dann auf die Suche, deren Statistik Sie anzeigen möchten. 
    
2. Klicken Sie auf der Flyoutseite auf **Abfrage öffnen**. 
    
3. Klicken Sie in der Dropdownliste **Einzelne Ergebnisse** auf **Suchstatistiken**.
    
4. Klicken Sie in der Dropdownliste **Typ** auf eine der folgenden Optionen, je nachdem, welche Suchstatistiken Sie anzeigen möchten. 
    
  - **Zusammenfassung:** Zeigt Statistiken für jeden Typ von durchsuchten Inhaltsspeicherorten an. Diese umfassen die Anzahl der Inhaltsspeicherorte mit Elementen, die der Suchabfrage entsprechen, sowie die Gesamtanzahl und die Größe von Suchergebniselementen. Dies ist die Standardeinstellung.
    
  - **Abfragen:** Bei dieser Option werden Statistiken zur Suchabfrage angezeigt. Dazu zählen der Typ des Inhaltsspeicherorts, auf den die Abfragestatistiken zutreffen, ein Teil der Suchabfrage, auf den die Statistiken zutreffen (beachten Sie, dass **Primär** die gesamte Suchabfrage angibt), die Anzahl der Inhaltsspeicherorte mit Elementen, die der Suchabfrage entsprechen, sowie die Gesamtanzahl und Größe der (am angegebenen Inhaltsspeicherort) gefundenen Elemente, die der Suchabfrage entsprechen. Außerdem werden Statistiken für nicht indizierte Elemente (auch als *teilweise indizierte Elemente* bezeichnet) angezeigt. Allerdings sind in den Statistiken nur teilweise indizierte Elemente aus Postfächern enthalten. Teilweise indizierte Elemente aus SharePoint und OneDrive werden nicht in die Statistiken einbezogen.
    
  - **Am häufigsten verwendete Speicherorte:** Bei dieser Option werden Statistiken zur Anzahl der Elemente angezeigt, die der Suchabfrage an jedem Inhaltsspeicherort entsprechen. Es werden die ersten 1.000 Speicherorte angezeigt.
    
Weitere Details zu Suchstatistiken finden Sie unter [Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse](view-keyword-statistics-for-content-search.md).
  
  
## <a name="export-search-results"></a>Exportieren der Suchergebnisse

Nachdem eine Suche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse auf einen lokalen Computer exportieren. Wenn Sie E-Mail-Ergebnisse exportieren, können diese als PST-Dateien oder als einzelne Nachrichten (.msg-Dateien) auf Ihren Computer heruntergeladen werden. Wenn Sie Inhalte aus SharePoint- und OneDrive-Websites exportieren, werden Kopien der systemeigenen Office-Dokumente exportiert. Es gibt noch weitere Dokumente und Berichte, die zusammen mit den Suchergebnissen exportiert werden. Sie können auch den Suchergebnisbericht ohne die eigentlichen Elemente exportieren.
  
So exportieren Sie Suchergebnisse:
  
1. Wählen Sie auf der Seite **Inhaltssuche** die Suche aus, deren Suchergebnisse Sie exportieren möchten. 
    
2. Klicken Sie auf der Flyoutseite auf ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Mehr**, und klicken Sie dann auf **Ergebnisse exportieren**. Sie können auch einen Suchergebnisbericht exportieren.
    
3. Füllen Sie die Abschnitte auf der Flyoutseite **Ergebnisse exportieren** aus. Verwenden Sie die Bildlaufleiste, um alle Exportoptionen anzuzeigen. 
    
Ausführlichere Anweisungen und Tipps zur Problembehandlung finden Sie unter:
  
- [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)
    
- [Exportieren eines Inhaltssuchberichts](export-a-content-search-report.md)
    
  
## <a name="more-information-about-content-search"></a>Weitere Informationen zur Inhaltssuche

Weitere Informationen zu Inhaltssuchen finden Sie in den folgenden Abschnitten.
  
[Grenzwerte für Inhaltssuchen](#content-search-limits)
  
[Erstellen einer Suchabfrage](#building-a-search-query)
  
[Durchsuchen von OneDrive-Konten](#searching-onedrive-accounts)
  
[Durchsuchen von Microsoft Teams and Office 365-Gruppen](#searching-microsoft-teams-and-office-365-groups)
  
[Durchsuchen von inaktiven Postfächern](#searching-inactive-mailboxes)
  
[Durchsuchen von getrennten oder nicht mehr lizensierten Postfächern](#searching-disconnected-or-de-licensed-mailboxes)

[Vorschau von Suchergebnissen anzeigen](#previewing-search-results)
  
[Teilweise indizierte Elemente](#partially-indexed-items)

[Suchen nach Inhalten in einer SharePoint-Multi-Geo-Umgebung](#searching-for-content-in-a-sharepoint-multi-geo-environment)
  
### <a name="content-search-limits"></a>Grenzwerte für Inhaltssuchen

- Eine Beschreibung der Einschränkungen, die für das Inhaltssuchfeature gelten, finden Sie unter [Grenzwerte für die Inhaltssuche](limits-for-content-search.md).
    
- Microsoft sammelt Leistungsdaten für alle Inhaltssuchen, die von Office 365-Organisationen durchgeführt werden. Obwohl sich die Komplexität einer Suchabfrage negativ auf die Suchzeiten auswirken kann, ist die Anzahl der durchsuchten Postfächer der Faktor, der die Suchdauer am stärksten beeinflusst. Microsoft bietet zwar keine Vereinbarung zum Servicelevel (Service Level Agreement, SLA) für Suchzeiten an, in der folgenden Tabelle werden jedoch durchschnittliche Suchzeiten für eine Inhaltssuche basierend auf der Anzahl der in die Suche einbezogenen Postfächer angegeben.
    
|**Anzahl Postfächer**|**Durchschnittliche Suchzeit**|
|:-----|:-----|
|100  <br/> |30 Sekunden  <br/> |
|1.000  <br/> |45 Sekunden  <br/> |
|10.000  <br/> |4 Minuten  <br/> |
|25.000  <br/> |10 Minuten  <br/> |
|50.000  <br/> |20 Minuten  <br/> |
|100.000  <br/> |25 Minuten  <br/> |
  
### <a name="building-a-search-query"></a>Erstellen einer Suchabfrage

Ausführliche Informationen zum Erstellen einer Suchabfrage mithilfe von booleschen Suchoperatoren und Suchbedingungen sowie zum Suchen nach vertraulichen Informationstypen und Inhalten, die für Benutzer außerhalb Ihrer Organisation freigegeben wurden, finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
Bedenken Sie bei der Verwendung einer Schlüsselwortliste zum Erstellen einer Suchabfrage die folgenden Punkte:
  
- Sie müssen das Kontrollkästchen **Stichwortliste anzeigen** aktivieren und dann jedes Schlüsselwort in eine separate Zeile eingeben, um eine Suchabfrage zu erstellen, wobei die Schlüsselwörter (oder Schlüsselwortausdrücke) in jeder Zeile durch den Operator **OR** verbunden sind. Wenn Sie eine Liste von Schlüsselwörtern in das Schlüsselwortfeld einfügen oder nach der Eingabe eines Schlüsselworts die **EINGABETASTE** drücken, werden die Schlüsselwörter nicht mit dem Operator **OR** verbunden. Nachfolgend finden Sie falsche und richtige Beispiele für das Hinzufügen einer Liste von Schlüsselwörtern. 
    
    **Falsch**
    
    ![Falsche Methode zum Formatieren einer Schlüsselwortliste (indem Sie die Liste in das Schlüsselwortfeld einfügen)](media/fb54e3df-232a-439a-b3d7-27a60ec76a4c.png)
  
    **Richtig**
    
    ![Richtige Methode zum Formatieren einer Schlüsselwortliste (indem Sie das Kontrollkästchen aktivieren und die Liste anschließend einfügen)](media/5d511a7b-c1f9-499c-bffe-e075bfc9adec.png)
  
- Sie können auch eine Liste von Schlüsselwörtern oder Schlüsselwortausdrücken in einer Excel-Datei oder einer reinen Textdatei vorbereiten, und diese Liste dann kopieren und in die Schlüsselwortliste einfügen. Zu diesem Zweck müssen Sie das Kontrollkästchen **Schlüsselwortliste anzeigen** aktivieren. Klicken Sie dann auf die erste Zeile in der Schlüsselwortliste, und fügen Sie Ihre Liste ein. Jede Zeile aus der Excel- oder TXT-Datei wird in eine separate Zeile in der Schlüsselwortliste eingefügt. 
    
- Nachdem Sie eine Abfrage mithilfe der Schlüsselwortliste erstellt haben, ist es ratsam, die Suchabfragesyntax zu überprüfen, um sicherzustellen, dass die Suchabfrage Ihren Vorstellungen entspricht. In der Suchabfrage, die im Detailbereich unter **Abfrage** angezeigt wird, sind die Schlüsselwörter durch den Text **(c:s)** voneinander getrennt. Dies weist darauf hin, dass die Schlüsselwörter durch einen logischen Operator verbunden sind, dessen Funktionsweise mit jener des **OR**-Operators vergleichbar ist. Wenn Ihre Suchabfrage Bedingungen enthält, sind die Schlüsselwörter und die Bedingungen entsprechend durch den Text **(c:c)** voneinander getrennt. Dies weist darauf hin, dass die Schlüsselwörter durch einen logischen Operator verbunden sind, dessen Funktionsweise mit jener des **AND**-Operators vergleichbar ist. Es folgt ein Beispiel für die (im Bereich "Details" angezeigte) Suchabfrage, die sich ergibt, wenn Sie die Schlüsselwortliste und eine Bedingung verwenden. 
    
    ![Beispiel für die Abfrage, die unter Verwendung der Schlüsselwortliste und einer Bedingung erstellt wird](media/b463750c-57fa-4602-9fed-0d5a420db3ad.png)
  
- Wenn Sie eine Inhaltssuche ausführen, überprüft Office 365 die Suchabfrage automatisch auf nicht unterstützte Zeichen und boolesche Operatoren, die nicht groß geschrieben sind. Nicht unterstützte Zeichen sind häufig ausgeblendet und verursachen in der Regel einen Suchfehler, oder es werden unerwartete Ergebnisse zurückgegeben. Weitere Informationen zu den nicht unterstützten Zeichen, nach denen gesucht wird, finden Sie unter [Überprüfen der Inhaltssuchabfrage auf Fehler](check-your-content-search-query-for-errors.md).
    
- Wenn eine Suchabfrage Schlüsselwörter für nichtenglische Zeichen enthält (z. B. chinesische Zeichen), können Sie auf **Abfragesprache Land/Region**![Query language-country/region icon in Content search](media/8d4b60c8-e1f1-40f9-88ae-ee2a7eca0886.png) klicken und einen Kulturcodewert für Sprache und Region für die Suche auswählen. Die standardmäßige Sprache/Region ist neutral. Woran erkennen Sie, dass Sie die Spracheinstellung für eine Inhaltssuche ändern müssen? Wenn Sie sicher sind, dass bestimmte Inhaltsspeicherorte nichtenglische Zeichen enthalten, nach denen Sie suchen, die Suche jedoch keine Ergebnisse zurückgibt, könnte die Spracheinstellung die Ursache sein. 
  
### <a name="searching-onedrive-accounts"></a>Durchsuchen von OneDrive-Konten

- Wie Sie eine Liste der URLs für die OneDrive-Websites in Ihrer Organisation erstellen können erfahren Sie unter [Erstellen einer Liste aller OneDrive-Speicherorte in Ihrer Organisation](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Mit dem Skript in diesem Artikel wird eine Textdatei erstellt, die eine Liste aller OneDrive-Websites enthält. Um dieses Skript ausführen zu können, müssen Sie die SharePoint Online-Verwaltungsshell installieren und verwenden. Achten Sie darauf, die URL für die "MeineWebsite"-Domäne Ihrer Organisation an jede OneDrive-Website anzuhängen, die Sie durchsuchen möchten. Dies ist die Domäne, die Ihr gesamtes OneDrive enthält, z. B. `https://contoso-my.sharepoint.com`. Hier ein Beispiel für die URL der OneDrive-Website eines Benutzers: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
    
    In den seltenen Fällen, in denen der Benutzerprinzipalname (User Principal Name, UPN) einer Person geändert wird, wird die URL für deren OneDrive-Speicherort so geändert, dass der neue UPN integriert ist. In diesem Fall müssen Sie eine Inhaltssuche entsprechend ändern, indem Sie die neue OneDrive-URL für den Benutzer hinzufügen und die alte entfernen.
  
### <a name="searching-microsoft-teams-and-office-365-groups"></a>Durchsuchen von Microsoft Teams and Office 365-Gruppen

Sie können ein Postfach durchsuchen, das einer Office 365-Gruppe oder einem Microsoft-Team zugeordnet ist. Da Microsoft Teams auf Office 365-Gruppen aufgebaut ist, ist das Durchsuchen bei beiden ähnlich. In beiden Fällen wird nur das Gruppen- bzw. das Team-Postfach durchsucht. Die Postfächer der Gruppen- oder Teammitglieder werden nicht durchsucht. Um diese zu durchsuchen, müssen sie eigens zur Suche hinzugefügt werden.
  
Beachten Sie die folgenden Punkte, wenn Sie in Microsoft Teams und Office 365-Gruppen nach Inhalten suchen.
  
- Um nach Inhalten in Teams und Office 365-Gruppen zu suchen, müssen Sie das Postfach und die SharePoint-Website angeben, die der Gruppe oder dem Team zugeordnet sind.
    
- Führen Sie das **Get-UnifiedGroup**-Cmdlet in Exchange Online aus, um die Eigenschaften für ein Team oder eine Office 365-Gruppe anzuzeigen. Dies ist eine gute Möglichkeit zum Abrufen der URL der einem Team oder einer Gruppe zugeordneten Website. Mit dem folgenden Befehl werden z. B. ausgewählte Eigenschaften für die Office 365-Gruppe „Geschäftsleitung“ angezeigt: 
    
  ```text
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroup**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde. 
  
- Wenn ein Benutzerpostfach durchsucht wird, werden keine Office 365-Gruppen durchsucht, denen der Benutzer angehört. Außerdem werden beim Durchsuchen eines Teams oder einer Office 365-Gruppe nur das von Ihnen angegebene Gruppenpostfach und die von Ihnen angegebene Gruppen-Website durchsucht. Die Postfächer und OneDrive for Business-Konten von Gruppenmitgliedern werden nicht durchsucht, es sei denn, Sie fügen sie der Suche explizit hinzu.
    
- Eine Liste der Mitglieder eines Teams oder einer Office 365-Gruppe können Sie über die Eigenschaften auf der Seite **Start \> Gruppen** im Microsoft 365 Admin Center anzeigen. Alternativ können Sie den folgenden Befehl in Exchange Online-PowerShell ausführen: 
    
  ```powershell
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroupLinks**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde. 
  
- Unterhaltungen, die Bestandteil eines Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Team zugeordnet ist. Gleichermaßen werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Postfach und die SharePoint-Website des Teams als Inhaltsspeicherort hinzufügen, um Unterhaltungen und Dateien in einem Kanal zu durchsuchen.
    
- Demgegenüber werden Unterhaltungen, die Bestandteil der Chatliste in Teams sind, in den Exchange Online-Postfächern der Benutzer gespeichert, die am Chat teilnehmen. Und in Chatunterhaltungen freigegebene Dateien werden im OneDrive for Business-Konto des Benutzers gespeichert, der die Datei freigibt. Daher müssen Sie die Postfächer und OneDrive for Business-Konten der jeweiligen Benutzer als Inhaltsspeicherorte hinzufügen, um Unterhaltungen und Dateien in der Chatliste zu durchsuchen.
    
    > [!NOTE]
    > Benutzer mit lokalen Postfächern könnten in einer Exchange-Hybridbereitstellung an Unterhaltungen teilnehmen, die Teil der Chat-Liste in Microsoft Teams sind. In diesem Fall können Inhalte aus diesen Unterhaltungen ebenfalls durchsucht werden, weil sie in einem Cloud-basierten Speicherbereich (als *Cloud-basiertes Postfach für lokale Benutzer* bezeichnet) für Benutzer gespeichert sind, die über ein lokales Postfach verfügen. Weitere Informationen finden Sie unter [Durchsuchen von Cloud-basierten Postfächern für lokale Benutzer in Office 365](search-cloud-based-mailboxes-for-on-premises-users.md).
  
- Jedes Team bzw. jeder Team-Kanal enthält ein Wiki zum Erstellen von Notizen und zum Thema Zusammenarbeit. Die Wiki-Inhalte werden automatisch in einer Datei im MHT-Format gespeichert. Diese Datei wird in der Dokumentbibliothek für Wiki-Daten auf der SharePoint-Website des Teams gespeichert. Sie können das Tool für die Inhaltssuche zum Durchsuchen des Wikis verwenden, indem Sie die SharePoint-Website des Teams als den zu durchsuchenden Inhaltsspeicherort angeben. 
    
    > [!NOTE]
    > Die Möglichkeit zum Durchsuchen des Wikis für ein Team oder einen Kanal (beim Durchsuchen der SharePoint-Website des Teams) wurde am 22. Juni 2017 freigegeben. Es können Wiki-Seiten, die an diesem Datum oder später gespeichert oder aktualisiert wurden, durchsucht werden. Wiki-Seiten, die das letzte Mal vor diesem Datum gespeichert oder aktualisiert wurden, sind nicht für die Suche verfügbar. 
 
- Zusammenfassungsinformationen für Besprechungen und Anrufe in einem Teams-Kanal werden außerdem in den Postfächern der Benutzer gespeichert, die an der Besprechung oder dem Anruf teilgenommen haben. Dies bedeutet, dass Sie die Inhaltssuche verwenden können, um diese Zusammenfassungen zu durchsuchen. Zusammenfassungsinformationen umfassen Folgendes: 
  
  - Datum, Startzeit, Endzeit und Dauer einer Besprechung oder eines Anrufs

  - Das Datum und die Uhrzeit, zu denen die einzelnen Teilnehmer der Besprechung oder dem Anruf beigetreten sind oder diese verlassen haben

  - An Voicemail gesendete Anrufe

  - Verpasste oder unbeantwortete Anrufe

  - Anrufweiterleitungen, die als zwei getrennte Anrufe dargestellt werden

  Es kann bis zu acht Stunden dauern, bis durchsuchbare Zusammenfassungen zu Besprechungen und Anrufen verfügbar sind.

  In den Suchergebnissen werden Besprechungszusammenfassungen im Feld **Typ** als **Besprechung**und Anrufübersichten als **Anruf** gekennzeichnet. Außerdem werden Unterhaltungen, die zu einem Teams-Kanals gehören und 1xN-Chats sind, im Feld **Typ** als **Sofortnachricht** gekennzeichnet.
  
  ![Teams-Besprechungen, Anrufe und 1xN-Chats sind im Feld "Typ" angegeben](media/O365-ContentSearch-Teams-MessageKind.png)

- Sie können die E-Mail-Eigenschaft **Art** oder die Suchbedingung **Art der Nachricht** verwenden, um gezielt nach Inhalten in Teams zu suchen. 
  
  - Wenn Sie die Eigenschaft **Art** als Teil der Keywordsuchabfrage verwenden möchten, geben Sie im Feld **Schlüsselwörter** bei einer Suchabfrage `kind:microsoftteams` ein.

    ![Verwenden Sie "kind:microsoftteams" im Feld "Schlüsselwörter"](media/O365-ContentSearch-Teams-Keywords.png)
  
  - Wenn Sie eine Suchbedingung verwenden möchten, fügen Sie die Bedingung **Art der Nachricht** hinzu, und verwenden Sie den Wert `microsoftteams`. 

    ![Verwenden Sie die Bedingung "Art der Nachricht" mit dem Wert "microsoftteams".](media/O365-ContentSearch-Teams-MessageKindCondition.png)

Bedingungen sind durch den Operator **AND** logisch mit der Schlüsselwortabfrage verknüpft. Dies bedeutet, dass ein Element sowohl der Schlüsselwortabfrage als auch der Suchbedingung entsprechen muss, damit es in den Suchergebnissen zurückgegeben wird. Weitere Informationen finden Sie im Abschnitt "Richtlinien für die Verwendung von Bedingungen" unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md#guidelines-for-using-conditions).
  
### <a name="searching-inactive-mailboxes"></a>Durchsuchen von inaktiven Postfächern

Im Rahmen einer Inhaltssuche können auch inaktive Postfächer durchsucht werden. Um eine Liste der inaktiven Postfächer in Ihrer Organisation abzurufen, führen Sie in Exchange Online PowerShell den Befehl `Get-Mailbox -InactiveMailboxOnly` aus. Alternativ können Sie im Security & Compliance Center zu **Information governance**\> **Aufbewahrung** wechseln, und dann auf **Weitere**![Navigation Bar ellipses](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) \> **Inaktive Postfächer** klicken.
  
Folgende Dinge sollten beim Durchsuchen inaktiver Postfächer beachtet werden:

- Wenn eine bestehende Inhaltssuche ein Benutzerpostfach einschließt und dieses wird deaktiviert, wird es weiterhin nach Inhalten durchsucht, wenn die Suche nach der Deaktivierung erneut ausgeführt wird.
    
- Es kann vorkommen, dass ein Benutzer über ein aktives und ein inaktives Postfach mit der gleichen SMTP-Adresse verfügt. In solchen Fällen wird nur jenes Postfach durchsucht, das Sie als Ort für eine Inhaltssuche auswählen. Anders ausgedrückt: Wenn Sie das Postfach eines Benutzers zu einer Suche hinzufügen, können Sie nicht davon ausgehen, dass sowohl aktive als auch inaktive Postfächer durchsucht werden. Nur das Postfach, das Sie der Suche explizit hinzufügen, wird durchsucht.
    
- Sie können die Security & Compliance Center-PowerShell verwenden, um eine Inhaltssuche zum Durchsuchen eines inaktiven Postfachs zu erstellen. Dazu müssen Sie vor der E-Mail-Adresse des inaktiven Postfachs einen Punkt ( . ) einfügen. Mit dem folgenden Befehl wird beispielsweise eine Inhaltssuche erstellt, die ein inaktives Postfach mit der E-Mail-Adresse pavelb@contoso.onmicrosoft.com durchsucht:

   ``` 
   New-ComplianceSearch -name InactiveMailboxSearch -ExchangeLocation .pavelb@contoso.onmicrosoft.com -AllowNotFoundExchangeLocationsEnabled $true
   ```

- Es wird dringend empfohlen, die Verwendung der gleichen SMTP-Adresse für ein aktives und ein inaktives Postfach zu vermeiden. Wenn eine SMTP-Adresse, die derzeit einem inaktiven Postfach zugeordnet ist, wiederverwendet werden soll, wird empfohlen, das inaktive Postfach oder dessen Inhalt in einem aktiven Postfach (bzw. im Archiv eines aktiven Postfachs) rückzuspeichern, und das inaktive Postfach anschließend zu löschen. Weitere Informationen hierzu finden Sie in einem der folgenden Beiträge:
    
  - [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md)
    
  - [Rückspeichern eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md)
    
  - [Löschen eines inaktiven Postfachs in Office 365](delete-an-inactive-mailbox.md)

### <a name="searching-disconnected-or-de-licensed-mailboxes"></a>Durchsuchen von getrennten oder nicht mehr lizensierten Postfächern

Wenn die Exchange Online-Lizenz (oder die gesamte Office 365-Lizenz) aus einem Benutzerkonto in Office 365 oder in Azure Active Directory entfernt wird, wird das Postfach des betreffenden Benutzers zu einem *getrennten* Postfach. Dies bedeutet, dass das Postfach nicht mehr mit dem Benutzerkonto verknüpft ist. Beim Durchsuchen von getrennten Postfächern geschieht Folgendes:

- Wenn die Lizenz aus einem Postfach entfernt wird, kann das Postfach nicht mehr durchsucht werden. 

- Schließt eine bestehende Inhaltssuche ein Postfach ein, aus dem die Lizenz entfernt wurde, werden bei erneuten Inhaltssuchen keine Suchergebnisse aus dem getrennten Postfach angezeigt.

- Wenn Sie das Cmdlet **New-ComplianceSearch** zum Erstellen einer Inhaltssuche verwenden, und ein getrenntes Postfach als Exchange-Inhaltsspeicherort für die Suche festlegen, gibt die Inhaltssuche keine Suchergebnisse aus dem getrennten Postfach zurück.

Wenn Sie die Daten in einem getrennten Postfach beibehalten müssen, damit sie durchsuchbar sind, müssen Sie eine Aufbewahrung für das Postfach einrichten, bevor Sie die Lizenz entfernen. Dadurch bleiben die Daten erhalten und das getrennte Postfach durchsuchbar, bis die Aufbewahrung entfernt wird. Weitere Informationen zu Aufbewahrungen finden Sie unter [Identifizieren des Typs der Aufbewahrung für ein Exchange Online-Postfach](identify-a-hold-on-an-exchange-online-mailbox.md)

### <a name="previewing-search-results"></a>Vorschau der Suchergebnisse anzeigen

Unterstützte Dateitypen können im Vorschaufenster angezeigt werden. Wenn ein Dateityp nicht unterstützt wird, müssen Sie eine Kopie der Datei auf Ihren lokalen Computer herunterladen, um sie anzeigen zu können. Die folgenden Dateitypen werden unterstützt und können im Suchergebnisbereich in einer Vorschau angezeigt werden.
  
- .TXT, .HTML, .MHTML
    
- .EML
    
- .DOC, .DOCX, .DOCM
    
- .PPTM, .PPTX
    
- .PDF
    
Darüber hinaus werden die folgenden Dateicontainertypen unterstützt. Eine Liste der Dateien in einem Container können Sie im Vorschaubereich anzeigen.
  
- .ZIP
    
- .GZIP
    
### <a name="partially-indexed-items"></a>Teilweise indizierte Elemente

- Wie zuvor erläutert, werden teilweise indizierte Elemente in Postfächern in die geschätzten Suchergebnisse einbezogen. Teilweise indizierte Elemente aus SharePoint und OneDrive werden nicht in die geschätzten Suchergebnissen einbezogen. 
    
- Wenn ein teilweise indiziertes Element der Suchabfrage entspricht (weil andere Nachrichten- oder Dokumenteigenschaften die Suchkriterien erfüllen), wird es nicht in die geschätzte Anzahl nicht indizierter Elemente einbezogen. Wenn ein teilweise indiziertes Element durch die Suchkriterien ausgeschlossen ist, wird es nicht in die geschätzte Anzahl nicht indizierter Elemente einbezogen. Weitere Informationen finden Sie unter [Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md).

### <a name="searching-for-content-in-a-sharepoint-multi-geo-environment"></a>Suchen nach Inhalten in einer SharePoint-Multi-Geo-Umgebung

Wenn es erforderlich ist, dass ein eDiscovery-Manager nach Inhalten in SharePoint und OneDrive in verschiedenen Regionen in einer [SharePoint-Multi-Geo-Umgebung](https://go.microsoft.com/fwlink/?linkid=860840) sucht, müssen Sie die folgenden Schritte ausführen, um dies zu erreichen:
   
1. Erstellen Sie ein separates Benutzerkonto für jeden geografischen Satellitenstandort, den der eDiscovery-Manager durchsuchen muss. Wenn Sie nach Inhalten auf Websites an diesem geografischen Standort suchen möchten, muss sich der eDiscovery-Manager bei dem Konto anmelden, das Sie für diesen Standort erstellt haben, und dann eine Inhaltssuche ausführen.

2. Erstellen Sie einen Suchberechtigungsfilter (und das entsprechende Benutzerkonto) für jeden geografischen Satellitenstandort, den der eDiscovery-Manager durchsuchen muss. Jeder dieser Suchberechtigungsfilter beschränkt den Umfang der Inhaltssuche auf einen bestimmten geografischen Standort, wenn der eDiscovery-Manager bei dem diesem Standort zugeordneten Benutzerkonto angemeldet ist.
 
> [!TIP]
> Wenn Sie das Suchtool in [Advanced eDiscovery](overview-ediscovery-20.md) verwenden, brauchen Sie diese Strategie nicht zu verwenden. Der Grund dafür ist, dass beim Durchsuchen von SharePoint-Websites und OneDrive-Konten in Advanced eDiscovery alle Datacenter durchsucht werden. Sie müssen diese Strategie der regionsspezifischen Benutzerkonten und Suchberechtigungsfilter nur bei Verwendung des Tools für die Inhaltssuche und beim Ausführen von Suchvorgängen verwenden, die [eDiscovery-Fällen](ediscovery-cases.md) zugeordnet sind. 


Angenommen, ein eDiscovery-Manager muss nach SharePoint- und OneDrive-Inhalten an Satellitenstandorten in Nordamerika, Europa, und Asien-Pazifik suchen. Der erste Schritt besteht darin, drei Benutzerkonten zu erstellen (jeweils eines für jeden Standort). Als Nächstes erstellen Sie drei Suchberechtigungsfilter (jeweils einen für jeden Standort *und* das entsprechende Benutzerkonto). Nachfolgend finden Sie Beispiele für die drei Suchberechtigungsfilter für dieses Szenario. In jedem dieser Beispiele gibt die **Region** den Standort des SharePoint-Datacenters für diesen geografischen Raum an, und der Parameter **Benutzer** gibt das entsprechende Benutzerkonto an. 

**Nordamerika**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-NAM" -Users ediscovery-nam@contoso.com -Region NAM -Action ALL
```

**Europa**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-EUR" -Users ediscovery-eur@contoso.com -Region EUR -Action ALL
```

**Asiatisch-pazifischer Raum**

```powershell
New-ComplianceSecurityFilter -FilterName "SPMultiGeo-APC" -Users ediscovery-apc@contoso.com -Region APC -Action ALL
```

Beachten Sie die folgenden Punkte, wenn Sie Suchberechtigungsfilter verwenden, um nach Inhalten in Multi-Geo-Umgebungen zu suchen:

- Der Parameter **Region** leitet Suchvorgänge an den angegebenen Satellitenstandort weiter. Wenn ein eDiscovery-Manager nur SharePoint- und OneDrive-Websites außerhalb der im Suchberechtigungsfilter angegebenen Region durchsucht, werden keine Suchergebnisse zurückgegeben. 

- Der Parameter **Region** steuert keine Suchvorgänge in Exchange-Postfächern. Beim Durchsuchen von Postfächern werden alle Datacenter durchsucht. 
    
Weitere Informationen zum Verwenden von Suchberechtigungsfiltern in einer Multi-Geo-Umgebung finden Sie im Abschnitt "Durchsuchen und Exportieren von Inhalten in Multi-Geo-Umgebungen" unter [Einrichten von Compliance-Grenzwerten für eDiscovery-Untersuchungen](set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments).
