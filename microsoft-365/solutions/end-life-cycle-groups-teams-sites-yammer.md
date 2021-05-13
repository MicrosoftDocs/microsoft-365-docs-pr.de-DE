---
title: End-of-Lifecycle-Optionen für Gruppen, Teams und Yammer
ms.reviewer: mmclean
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: End-of-Lifecycle-Optionen für Gruppen, Teams und Yammer.
ms.openlocfilehash: 468f41df747b6cf12d3f6619d79cb97248eba1d1
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52346426"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>End-of-Lifecycle-Optionen für Gruppen, Teams und Yammer

Microsoft 365 Gruppen und Microsoft Teams arbeiten mit mehreren verbundenen Diensten. Wenn eine Gruppe oder ein Team gelöscht wird, werden die meisten Informationen in den verbundenen Diensten ebenfalls gelöscht. In diesem Artikel werden Optionen zum Beibehalten von Informationen beschrieben, indem sie vor dem Löschen aus der Gruppe oder dem Team gelöscht werden.

Eine gängige Praxis für Gruppen oder Teams, die nicht mehr benötigt werden, ist das Verschieben der Dateien aus dem Team und das Archivieren der Dateien an einem anderen Speicherort, z. B. SharePoint Dokumentbibliothek. Diese Vorgehensweise basiert auf einer älteren Arbeitsweise, bei der Informationen in Dateien und Ordnern gespeichert werden und die Kommunikation per E-Mail erfolgt.

In der folgenden Tabelle sind die Dienste, die Gruppen und Teams zugeordnet sind, sowie die wichtigsten Inhaltstypen in den einzelnen Gruppen aufgeführt:

|Dienst|Inhaltstypen|
|:------|:---------------|
|Teams|Kanalunterhaltungen, Dateien in Kanälen|
|Formulare|Umfragestruktur und Ergebnisse|
|OneNote|Notizbuch|
|Outlook|E-Mail und Kalender|
|Planner|Project Status- und Vorgangsinformationen|
|Power Automate|Workflows|
|Power BI|Daten, Berichte und Dashboards|
|Project im Web|Project-Pläne|
|Roadmap|Roadmaps|
|SharePoint|Dateien, Listen, Teams Kanal-Wiki-Daten|
|Stream|Videos|
|Yammer|Unterhaltungen|

Beim Löschen einer Gruppe oder eines Teams werden die meisten zugeordneten Ressourcen ebenfalls gelöscht. Ausnahmen sind:

- Videos in Stream bleiben erhalten und gehören der Person, die sie hochgeladen/aufgezeichnet hat.
- Flüsse in Power Automate verbleiben und befinden sich im Besitz der Person, die sie erstellt hat.
- Project und Roadmapdaten in Project im Web bleiben im CDS erhalten und können separat wiederhergestellt werden.

Gruppen und Teams verbleiben 30 Tage lang im Status "Soft-Delete" und können jederzeit wiederhergestellt werden. Nach den 30 Tagen werden sie jedoch und alle zugehörigen Ressourcen wie Dienste und Inhalte aus der Microsoft 365 gelöscht. Alle durch eine Aufbewahrungsrichtlinie geschützten Inhalte bleiben über eDiscovery-Suchen verfügbar.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Überlegungen zum Ende des Lebenszyklus für gruppenverkn nnte Dienste

Es gibt drei wichtige Bereiche, die Team- und Gruppenbesitzer und IT-Administratoren beim Löschen einer Gruppe oder eines Teams berücksichtigen müssen.

**Content**

Muss der Inhalt beibehalten werden, nachdem das Team nicht mehr da ist? Reicht es aus, sich auf die Aufbewahrungsfunktionen von Microsoft 365 zu verlassen, oder ist ein Teil der Inhalte in Apps und Diensten, die keine Aufbewahrung anbieten? Muss der Inhalt für datensatzverwaltungs-, archiv- oder zukünftige Verwendungs- und Referenzzwecke aufbewahrt werden?

Um potenzielle Datenverluste zu vermeiden, müssen diese Fragen gestellt werden, bevor ein Team archiviert oder gelöscht wird.

**Dienste**

Muss der Inhalt im aktuellen Arbeitsformular bleiben? Muss beispielsweise der Power BI weiterhin zugänglich sein? Müssen die Formularergebnisse in der visuellen Zusammenfassungsansicht verfügbar sein? Sind die Listen in SharePoint verknüpft oder eingebettet?

Diese Fragen müssen gestellt werden, bevor die zugrunde liegende Gruppe gelöscht wird, da das Exportieren des Inhalts möglicherweise nicht ausreicht.

**Gäste**

Wenn Gäste zu einem Team eingeladen werden, wird in der Hostorganisation ein Gastkonto erstellt Azure Active Directory bevor sie dem Team hinzugefügt werden. Wenn ein Team gelöscht wird, werden Gäste nicht aus Azure Active Directory. Gäste können zwar nicht auf Gruppen, Websites, Teams oder Inhalte zugreifen, die nicht für sie freigegeben wurden, aber sie können weiterhin potenziell Features innerhalb von Microsoft Teams wie das Starten von Chats, Sprach- und Videoanrufen und die Verwendung von Apps verwenden.

Ein Team- oder Gruppenbesitzer kann jemanden von außerhalb der Organisation einladen, ein Gast in Azure Active Directory zu einem Team zu werden. Ein Teambesitzer kann den Gast jedoch nicht aus Azure Active Directory. Das Löschen von Konten kann nur von einem globalen Administrator oder Benutzeradministrator ausgeführt werden.

Es ist wichtig, Gastbewertungen durchzuführen und zu verstehen, ob Gäste nach dem Löschen des Azure Active Directory entfernt werden müssen. Es kann ein gültiger Fall sein, dass Gäste im Verzeichnis verbleiben, z. B. Mitglied anderer Teams sein oder andere Dienste Microsoft 365 verwenden.

## <a name="teams"></a>Teams

Teams inhalte werden hauptsächlich in Form von Unterhaltungen verwendet.

Unterhaltungen in Kanälen können nicht mit systemeigenen Funktionen kopiert oder verschoben Microsoft Teams werden. Sie können jedoch mithilfe der Graph exportiert werden.

Wenn außerdem eine Aufbewahrungsrichtlinie auf Teams angewendet wird, werden die Unterhaltungen beibehalten und über eDiscovery-Suchen verfügbar. Mithilfe von advanced eDiscovery können Sie [eine chat-Teams rekonstruieren.](/microsoft-365/compliance/conversation-review-sets)


### <a name="archiving-a-team"></a>Archivierung eines Teams

Der Vorteil der [Archivierung eines Teams](/microsoftteams/archive-or-delete-a-team) ist, dass es vollzugriff auf das Team bietet, wie es war. Benutzer können weiterhin Kanalunterhaltungen durchsuchen und Dateien öffnen, auch wenn sie nicht aktiv sind. Darüber hinaus können Teams nicht archiviert werden, wenn die Arbeit an ihnen fortgesetzt werden muss (z. B. wenn ein Projekt erweitert wird).

Wenn ein Team von einem Besitzer archiviert wird, ist es auf schreibgeschützt für Mitglieder sowohl für Inhalte innerhalb des Teams als auch bei Auswahl der zugeordneten SharePoint festgelegt. Ziel dieser Aktion ist es, sicherzustellen, dass Unterhaltungen in Kanälen in ihrem vorhandenen Status erhalten bleiben, zusammen mit SharePoint-basierten Inhalten wie Dateien und Wikis.

In der SharePoint gibt es keine sichtbaren Änderungen. Es können jedoch keine Änderungen an Dateien oder Listen vorgenommen werden, da SharePoint Berechtigungen für die Microsoft 365 auf **Websitebesucher festgelegt sind.** Dies umfasst OneNote Notizbuch für das Team, das in der Websiteressourcenbibliothek auf der SharePoint gespeichert ist.

Wenn ein Team archiviert wird, unterliegt die zugrunde liegende Microsoft 365 weiterhin der Ablaufrichtlinie (sofern festgelegt), und daher muss der Besitzer das Team weiterhin erneuern.

Während die Kanalunterhaltungen des Teams und SharePoint Websiteinhalte auf schreibgeschützt festgelegt sind, wird dies nicht auf andere zugeordnete Dienste angewendet:

- Planner-Buckets und -Aufgaben können weiterhin erstellt, geändert und gelöscht werden.
- Formulare können weiterhin Übermittlungen empfangen.
- Das Outlook kann weiterhin E-Mails empfangen.
- Power BI Dashboards, Berichte und Daten können weiterhin geändert werden.
- Projekte und Roadmaps können weiterhin Project im Web bearbeitet werden.
- Videos können weiterhin in Stream hochgeladen, geändert und gelöscht werden.
- Flüsse in Power Automate können weiterhin erstellt, geändert, gelöscht und weiterhin ausgeführt werden. (Es wird jedoch ein Fehler angezeigt, falls erforderlich, um eine Nachricht an einen Kanal des archivierten Teams zu senden.)

## <a name="forms"></a>Formulare

Ein Formular kann zwar von einem einzelnen Konto in eine Gruppe verschoben werden, es kann jedoch nicht von einer Gruppe in eine andere verschoben oder kopiert werden. Es stehen drei Optionen für ein Formular zur Verfügung, wenn ein Team gelöscht wird.

**Duplizieren des Formulars**

Formulare können [als Vorlagen freigegeben werden,](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)sodass andere Benutzer sie in ihr eigenes Konto oder eine Gruppe kopieren können. Dadurch werden die Daten aus Ergebnisübermittlungen nicht beibehalten. nur Formularstruktur, z. B. Fragen und Einstellungen.

**Exportieren von Ergebnissen in eine Kalkulationstabelle**

Wenn die Daten der Formularantworten beibehalten werden müssen, kann dies erreicht werden, indem die Ergebnisse in eine Excel [exportiert werden.](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af) Dadurch werden nur die Fragen und ihre Antworten als Daten exportiert– es sind keine von Forms erstellten Diagramme enthalten.

**Löschen des Formulars**

Während das Löschen der Gruppe auch zum Löschen zugeordneter [](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) Formulare führt, können Gruppenmitglieder sie direkt löschen, ohne besitzer der Gruppe zu sein. Dies ist jedoch ein manueller Schritt, der keinen zusätzlichen Vorteil bietet.

## <a name="onenote"></a>OneNote

Das OneNote, das in einer Gruppe enthalten ist, wird in der Websiteressourcenbibliothek innerhalb der zugeordneten SharePoint gespeichert. Während Notizbuchdateien manchmal auf mehrere einzelne Dateien verteilt werden können, können sie nicht kopiert und unabhängig geöffnet werden. Stattdessen muss der Inhalt des notizbuchs OneNote verschoben oder mit einem OneNote 2016.

**Verschieben von Seiten und Abschnitten in ein anderes Notizbuch**

[Das individuelle Verschieben von Seiten](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) oder Abschnitten in ein anderes Notizbuch bietet Besitzern die Möglichkeit, ihre Daten zu bereinigen und nur die zu speichernden Daten zu übernehmen.

**Exportieren des gesamten Notizbuchs als Paket**

Wenn das gesamte Notizbuch mit seiner vorhandenen Struktur beibehalten werden muss, kann es als [OneNote-Paketdatei](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) exportiert und dann an einen neuen Speicherort importiert werden. Stattdessen kann dies als Methode zum Beibehalten des Inhalts in einer einzelnen Datei anstelle der vorhandenen Mehrdateistruktur verwendet werden.

**Als PDF drucken**

In Szenarien, in denen einige Inhalte des Notizbuchs nur als Referenz oder als Datensätze aufbewahrt werden müssen, können einzelne Seiten in PDF gedruckt und an anderer [Stelle gespeichert werden.](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)

## <a name="mailbox-and-calendar"></a>Postfach und Kalender

Es ist nicht ungewöhnlich, dass das dem Gruppen zugeordnete Postfach verwendet wird, auch wenn viele Unterhaltungen innerhalb von Teamkanälen geführt wurden. Das Postfach speichert nur E-Mails, die direkt an das Postfach gesendet wurden, und enthält keine E-Mails, die direkt an Kanäle gesendet wurden.

In einigen Fällen können die im Postfach gespeicherten E-Mails Benachrichtigungen über Besprechungen, Planner-Aufgabenupdates und andere von der App oder vom System generierte Nachrichten sein. Es ist wichtig, dass der Inhalt des Postfachs überprüft wird, um zu bestimmen, ob der Inhalt beibehalten oder gelöscht werden soll.

Wenn eine Aufbewahrungsrichtlinie in Exchange angewendet wird, werden die E-Mails und Kalenderelemente beibehalten und über eDiscovery-Suchen verfügbar.

**Exportieren von E-Mails und Kalendern**

Team- oder Gruppenmitglieder können den Inhalt des Postfachs und Kalenders in eine Outlook [-Datei (Data/ Personal Storage) exportieren.](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91) Diese Datei kann dann an anderer Stelle gespeichert werden, oder der Inhalt kann in ein anderes Postfach importiert werden. Erstere wird nicht empfohlen, da der Inhalt der PST-Datei nicht durchsucht werden kann, ohne sie in Outlook zu öffnen, und die Datei selbst kann im Laufe der Zeit beschädigt werden.

**Von der IT durchgeführte Inhaltsmigration**

Administratoren können Tools von Drittanbietern verwenden, um E-Mails und Kalenderinhalte ohne Benutzereingriff zwischen Postfächern zu migrieren. Ein potenzieller Speicherort könnte ein freigegebenes Postfach sein, das nur als "Archiv" des Gruppenpostfachinhalts erstellt wurde.

## <a name="planner"></a>Planner

Jede Gruppe oder jedes Team kann mehrere Pläne haben. Es ist wichtig, während des Off-Boarding-Prozesses sicherzustellen, dass aufbewahrungsanforderungen für jeden Plan erfüllt werden. Wie die anderen Dienste gibt es mehrere Ansätze für off-Board-Inhalte in Planner.

**Exportieren des Plans in eine Tabellenkalkulation**

Wenn es nur erforderlich ist, eine Kopie des Plans für Die Aufzeichnungszwecke zu behalten, besteht der einfachste Ansatz in dem Exportieren des Plans in eine Excel [Tabellenkalkulation.](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a) Dies ist eine one-way-Aktion. Es gibt keine Möglichkeit, Pläne aus einer Tabellenkalkulation zu importieren.

> [!IMPORTANT]
> Das Exportieren eines Plans in Excel enthält die meisten Informationen innerhalb des Plans, enthält jedoch keine Kommentare, Links oder Dateien.

**Kopieren und Verschieben von Vorgängen in einen anderen Plan**

Während das Kopieren oder Verschieben von Vorgängen in einen [](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) anderen Plan wie eine Lösung aussieht, können einzelne Vorgänge nur zwischen Plänen innerhalb derselben Gruppe kopiert oder verschoben werden. Dadurch werden die Daten nicht gespeichert, wenn die dem Plan zugeordnete Gruppe gelöscht wird.

**Kopieren des gesamten Plans**

Es ist auch möglich, den [gesamten Plan zu kopieren.](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4) Das Kopieren kann nicht in eine vorhandene Gruppe durchgeführt werden. Wenn Sie den Plan kopieren, wird eine neue Gruppe erstellt. Darüber hinaus enthält das Kopieren des gesamten Plans keine Kommentare, Zuordnungen, Links, Anlagen oder Datumsangaben.

## <a name="power-automate"></a>Power Automate

Flüsse, die in Power Automate erstellt und einer Gruppe oder einem Team zugeordnet sind, gehören nicht zur Gruppe. Sie befinden sich im Besitz des Erstellers und werden nur für andere Benutzer und Gruppen freigegeben. Sie sind also nicht betroffen, wenn eine Gruppe oder ein Team gelöscht wird.

**Ändern des Besitzes des Datenflusses**

Wenn der Fluss weiterhin ausgeführt werden muss, können alle Besitzer andere Benutzer oder Microsoft 365 als Besitzer hinzufügen.

**Exportieren des Datenflusses**

Wenn der Fluss nicht weiter ausgeführt werden muss, er jedoch für eine [](https://flow.microsoft.com/blog/import-export-bap-packages/) mögliche zukünftige Verwendung beibehalten werden muss, kann er als Datei exportiert und später erneut importiert werden.

## <a name="power-bi"></a>Power BI

Power BI Daten und Arbeitsbereiche können unabhängig von Gruppen und Teams ausgeführt werden, und wie andere Arbeitsauslastungen bieten unterschiedliche Möglichkeiten zum Off-Board-Arbeiten.

**Kopieren von Berichten in einen anderen Arbeitsbereich**

Wenn Sie den Bericht benötigen, nachdem die Gruppe oder das Team gelöscht wurde, kann er aus dem vorhandenen Arbeitsbereich in einen anderen Arbeitsbereich innerhalb von [Power BI.](/power-bi/connect-data/service-datasets-copy-reports)

**Exportieren von Daten aus einem Dashboard oder Bericht**

Wenn der Bericht nicht mehr aktiv sein muss, die Daten jedoch aufbewahrt werden müssen, kann er in die [Excel.](/power-bi/visuals/power-bi-visualization-export-data)

## <a name="project"></a>Project

Projekte und Roadmaps, die in Project für das Web erstellt wurden, sind Microsoft 365-Gruppen zugeordnet und haben Ansätze für off-boarding ähnlich wie Power BI.

**Zuweisen des Projekts zu einer anderen Gruppe**

Wenn das Projekt in seinem Funktionszustand über die Lebensdauer der Gruppe oder des Teams hinaus beibehalten werden muss, kann es einer anderen Gruppe zugewiesen Microsoft 365 [werden.](/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) Dies kann über das Dynamics 365 Administration Center geschehen.

**Exportieren von Daten aus dem Projekt oder der Roadmap**

Mithilfe des Dynamics 365 Administration Center können Benutzerdaten aus dem Projekt in [eine](/project-for-the-web/export-user-data-from-project-for-the-web) Tabellenkalkulation exportiert werden. Die Daten können auch in Project exportiert werden (. MPP) und XML-Dateiformate mithilfe von PowerShell.

## <a name="sharepoint"></a>SharePoint

Alle Dateien in Teamkanälen werden im SharePoint der zugeordneten Gruppe gespeichert. In einigen Fällen können andere Inhalte als Dokumente in SharePoint, z. B. Listen oder Seiten, vorhanden sein.

Dateien werden in der Regel an drei primären Speicherorten innerhalb eines SharePoint gespeichert:

- Seiten – Bibliothek für Websiteseiten
- Bilder, die in Seiten verwendet werden – Bibliothek für Websiteressourcen
- Dateien in Kanälen – Dokumentbibliothek
- Wikiseiten – Teams Wiki-Datenbibliothek

Wenn die Website über eine oder mehrere Unterwebsites verfügt, muss der Off-Boarding-Prozess für jede Unterwebsite wiederholt werden. Wenn das Team private Kanäle enthält, gibt es eine separate SharePoint für jeden Kanal.

Es ist wichtig, beim Entfernen von Dateien aus einer Gruppe oder einem Team zu berücksichtigen, dass sie möglicherweise für Benutzer freigegeben werden, die nicht Mitglied der Gruppe oder des Teams sind. Möglicherweise möchten Sie die bevorstehende Änderung an sie kommunizieren.

**Herunterladen von Dateien**

Dateien, die in SharePoint in einer der oben genannten Bibliotheken gespeichert sind, können auf [einen lokalen Computer heruntergeladen werden.](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)

**Verschieben von Dateien**

Darüber hinaus können Dateien an einen anderen Speicherort innerhalb SharePoint z. B. eine [Bibliothek an einer anderen Website verschoben werden.](https://support.office.com/article/00e2f483-4df3-46be-a861-1f5f0c1a87bc)

**Exportliste**

Daten, die in SharePoint gespeichert [](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)sind, können in eine Excel exportiert und erneut in eine Liste an einer anderen Website importiert werden.

Alternativ kann ein Drittanbietertool verwendet werden, um die Liste zwischen Websites zu migrieren, um Funktionen, Listenansichten, Formatierungen und andere Attribute zu erhalten.

**"Exportieren" von Wikidateien**

Wikiinhalte innerhalb von Teamkanälen werden in einer HTML-formatierten Datei in einer dedizierten Bibliothek der zugeordneten SharePoint gespeichert. Sie können nicht ohne Weiteres exportiert und in ein anderes Kanalwiki importiert werden, können jedoch in eine HTML-Datei konvertiert und als Webseite geöffnet werden.

## <a name="microsoft-stream"></a>Microsoft Stream

Wie Power Automate werden Videos in Stream, die einer Gruppe oder einem Team zugeordnet sind, nicht tatsächlich im Besitz der Gruppe und nicht gelöscht, wenn die Gruppe gelöscht wird. Videos in Stream gehören der Person, die das Video hochgeladen oder erstellt hat, auch wenn sie Benutzer oder Gruppen als Besitzer hinzufügen. Besprechungen, die in einem Teams aufgezeichnet werden, gehören der Person, die die Aufzeichnung gestartet hat.

**Hinzufügen anderer Besitzer**

Da das Video beim Löschen der Gruppe in Stream aufbewahrt wird, kann der ursprüngliche Besitzer das Video für andere Benutzer und Gruppen freigeben und sogar als [Besitzer hinzufügen.](/stream/portal-edit-video)

**Video herunterladen**

In Szenarien, in denen das Video nicht in Stream aufbewahrt werden muss oder an einem alternativen Speicherort wie einem Datensatzverwaltungssystem gespeichert werden muss, kann ein Besitzer es lokal [herunterladen.](/stream/portal-download-video)

## <a name="yammer"></a>Yammer

Im Gegensatz zu Unterhaltungen in Microsoft Teams bietet Yammer Sowohl Benutzern als auch Administratoren Optionen zum Verschieben oder Exportieren von Unterhaltungen.

**Verschieben von Unterhaltungen in eine andere Gruppe oder Community**

Unterhaltungen können von jedem Benutzer Yammer in eine andere Gruppe verschoben werden, nicht nur von Besitzern oder Administratoren. Dies ist sowohl in der [klassischen Yammer](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872) als auch in den [neuen Yammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) möglich.

**Exportieren von Netzwerkdaten**

Yammer [Netzwerkadministratoren exportieren Netzwerkdaten](/yammer/manage-security-and-compliance/export-yammer-enterprise-data). Dadurch werden jedoch alle Unterhaltungen für das gesamte Netzwerk exportiert. Der resultierende Export listet die Gruppen-ID auf. Es ist möglich, Unterhaltungen basierend auf dieser ID zu filtern.
