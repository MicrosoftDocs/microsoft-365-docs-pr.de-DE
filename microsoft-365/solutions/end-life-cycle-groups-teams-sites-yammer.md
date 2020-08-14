---
title: Ende der Lebenszyklusoptionen für Gruppen, Teams und jammern
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Ende der Lebenszyklusoptionen für Gruppen, Teams und jammern.
ms.openlocfilehash: ab06f06cc65614ee313892a026c2f482d641791f
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662631"
---
# <a name="end-of-lifecycle-options-for-groups-teams-and-yammer"></a>Ende der Lebenszyklusoptionen für Gruppen, Teams und jammern

Microsoft 365-Gruppen und Microsoft Teams arbeiten mit einer Vielzahl von verbundenen Diensten. Wenn eine Gruppe oder ein Team gelöscht wird, werden die meisten Informationen in den verbundenen Diensten ebenfalls gelöscht. In diesem Artikel werden Optionen zum Beibehalten von Informationen beschrieben, indem Sie Sie vor dem Löschen aus der Gruppe oder aus dem Team verschieben.

Eine gängige Vorgehensweise für Gruppen oder Teams, die nicht mehr benötigt werden, besteht darin, die Dateien aus dem Team zu entfernen und an einem anderen Speicherort wie einer SharePoint-Dokumentbibliothek zu speichern, die als Repository oder Archiv fungiert. Diese Vorgehensweise basiert auf einer Legacy-Arbeitsweise, in der Informationen in Dateien und Ordnern gespeichert werden, und die Kommunikation erfolgt per e-Mail.

In der folgenden Tabelle werden die Dienste beschrieben, die mit Gruppen und Teams zusammenhängen, sowie die wichtigsten Inhaltstypen, die in den einzelnen gefunden werden:

|Dienst|Inhaltstypen|
|:------|:---------------|
|Teams|Kanal Unterhaltungen, Dateien in Kanälen|
|Formulare|Vermessungs Struktur und Ergebnisse|
|OneNote|Notizbuch|
|Outlook|E-Mail und Kalender|
|Planner|Projektstatus und Vorgangsinformationen|
|Power Automate|Workflows|
|Power BI|Daten, Berichte und Dashboards|
|Project im Internet|Projektpläne|
|Roadmap|Roadmaps|
|SharePoint|Dateien, Listen, wiki-Daten in Microsoft Teams-Kanälen|
|Stream|Videos|
|Yammer|Unterhaltungen|

Beim Löschen einer Gruppe oder eines Teams werden die meisten zugeordneten Ressourcen ebenfalls gelöscht. Einige der Ausnahmen zu diesem gehören Videos in Stream – diese bleiben und werden immer noch von der Person besessen, die Sie hochgeladen/aufgezeichnet hat, ebenso wie Flows in Power automatisieren. Projekt-und Roadmap-Daten in Project im Internet verbleiben in den CDs und können separat wiederhergestellt werden.

Gruppen und Teams verbleiben 30 Tage lang im Status "Soft-Delete" und können jederzeit wiederhergestellt werden. Nach Ablauf der 30 Tage und der zugehörigen Ressourcen wie Dienste und Inhalte werden Sie jedoch vollständig aus der Microsoft 365-Umgebung gelöscht. Alle Inhalte, die durch eine Aufbewahrungsrichtlinie geschützt sind, bleiben über eDiscovery-suchen verfügbar.

## <a name="end-of-life-cycle-considerations-for-group-connected-services"></a>Überlegungen zum Lebenszyklusende für Gruppen verbundene Dienste

Es gibt drei wichtige Bereiche, die Team-und Gruppenbesitzer und IT-Administratoren beim Löschen einer Gruppe oder eines Teams berücksichtigen müssen.

**Inhalt**

Müssen die Inhalte beibehalten werden, nachdem das Team nicht mehr funktionsfähig oder noch nicht vorhanden ist? Genügt es, sich auf die Aufbewahrungsfunktionen von Microsoft 365 zu verlassen, oder handelt es sich um einen Teil des Inhalts in apps und Diensten, die keine Aufbewahrung anbieten? Muss der Inhalt für Zwecke der Datensatzverwaltung, für Archivierungszwecke oder für zukünftige Verwendungs-und Referenzzwecke aufbewahrt werden?

Diese Fragen müssen gestellt werden, bevor ein Team archiviert oder gelöscht wird, um potenzielle Datenverluste zu vermeiden.

**Dienste**

Müssen die Benutzer über die Inhalte in verschiedenen apps und Diensten in Ihrem aktuellen arbeitsformular bleiben? Muss beispielsweise der Power BI-Bericht weiterhin zugänglich sein, müssen die Formularergebnisse in der visuellen Zusammenfassungsansicht verfügbar sein, sind die Listen in SharePoint mit verknüpfter oder eingebetteter beliebiger Stelle?

Ähnlich wie bei den inhaltlichen Überlegungen müssen diese Fragen vor dem Löschen der zugrunde liegenden Gruppe gestellt werden, da ein einfaches Exportieren des Inhalts möglicherweise nicht ausreicht.

**Gäste**

Wenn Gäste zu einem Team eingeladen werden, erstellt der Workflow seine Identität in der Azure-Active Directory der Host Organisation, bevor er dem Team hinzugefügt wird. Wenn ein Team gelöscht wird, werden Gäste nicht aus Azure Active Directory entfernt und als solche noch in der Microsoft Teams-Umgebung vorhanden. Während Gäste nicht auf Gruppen, Websites, Teams oder Inhalte zugreifen können, die nicht für Sie freigegeben wurden, können Sie weiterhin Features in Microsoft Teams nutzen, beispielsweise Chats, sprach-und Videoanrufe initiieren und Apps verwenden.

Ein Team-oder Gruppenbesitzer kann einen externen Benutzer einladen, ein Gast in Azure Active Directory zu werden, ihn dem Team hinzuzufügen und aus dem Team zu entfernen. Ein Teambesitzer kann den Gast jedoch nicht aus Azure Active Directory entfernen – Dies kann nur von einem globalen Administrator oder Benutzer Administrator ausgeführt werden.

Deshalb ist es wichtig, Gästebewertungen durchzuführen und zu verstehen, ob Gäste beim Löschen von Teams aus Azure Active Directory entfernt werden müssen. Es kann einen gültigen Fall geben, dass Gäste im Verzeichnis bleiben, beispielsweise Mitglied eines oder mehrerer anderer Teams oder andere Microsoft 365-oder Azure-Dienste verwenden.

## <a name="teams"></a>Teams

Teams-spezifische Inhalte sind hauptsächlich in Form von Unterhaltungen.

Unterhaltungen in Kanälen können nicht mit systemeigenen Microsoft Teams-Funktionen kopiert oder verschoben werden. Sie können jedoch mithilfe der Graph-API exportiert werden.

Wenn außerdem eine Aufbewahrungsrichtlinie auf Teams angewendet wird, werden die Unterhaltungen beibehalten und über eDiscovery-Suchvorgänge zur Verfügung gestellt. (Elemente, die in eDiscovery-suchen gefunden werden, können exportiert werden, es gibt jedoch keinen Kontext oder keine Struktur aus ihrer ursprünglichen Quelle, sondern lediglich einzelne Nachrichten.)

### <a name="archiving-a-team"></a>Archivieren eines Teams

Der Vorteil der [Archivierung eines Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team) liegt darin, dass es den vollständigen Zugriff auf das Team ermöglicht, sodass Benutzer weiterhin Kanal Unterhaltungen durchsuchen und Dateien öffnen können, auch wenn Sie nicht aktiv sind. Darüber hinaus können Teams nicht archiviert werden, wenn es erforderlich ist, diese weiter zu bearbeiten (beispielsweise im Fall einer Project-Erweiterung).

Wenn ein Team von einem Besitzer archiviert wird, wird es für Mitglieder sowohl für die Inhalte innerhalb des Teams als auch für die zugehörige SharePoint-Website als schreibgeschützt festgelegt. Das Ziel dieser Aktion besteht darin, sicherzustellen, dass Unterhaltungen in Kanälen im vorhandenen Zustand beibehalten werden, zusammen mit SharePoint-basierten Inhalten wie Dateien und Wikis.

In der SharePoint-Website gibt es keine sichtbaren Änderungen, es können jedoch keine Änderungen an Dateien oder Listen vorgenommen werden, da die SharePoint-basierte Berechtigungsgruppe für die Microsoft 365-Gruppe auf Websitebesucher Ebene festgelegt ist. Dies umfasst das OneNote-Notizbuch für das Team, da dieses in der Bibliothek Website Objekte auf der SharePoint-Website gespeichert wird.

Wenn ein Team archiviert wird, unterliegt die zugrunde liegende Microsoft 365-Gruppe weiterhin der Ablaufrichtlinie (falls festgelegt), und als solcher muss der Besitzer das Team weiterhin erneuern.

Während die Kanal Unterhaltungen und SharePoint-Websiteinhalte des Teams auf schreibgeschützt festgelegt sind, wird das gleiche nicht auf andere zugeordnete Dienste angewendet:

- Planner-Buckets und-Aufgaben können weiterhin erstellt, geändert und gelöscht werden
- Formulare können weiterhin Übermittlungen empfangen
- Das Outlook-Postfach kann weiterhin e-Mails empfangen
- Power BI-Dashboards, Berichte und Daten können noch geändert werden
- Projekte und Roadmaps können weiterhin in Project im Internet bearbeitet werden
- Videos können weiterhin im Stream hochgeladen, geändert und gelöscht werden.
- Flows in Power Automation können weiterhin erstellt, geändert, gelöscht und weiterhin ausgeführt werden (bei Bedarf wird jedoch ein Fehler angezeigt, wenn eine Nachricht an einen Kanal des archivierten Teams gesendet wird).

## <a name="forms"></a>Formulare

Während ein Formular von einem einzelnen Konto in eine Gruppe verschoben werden kann, kann es nicht verschoben oder von einer Gruppe in eine andere kopiert werden. Für ein Formular stehen drei Optionen zur Verfügung, wenn ein Team gelöscht wird.

**Duplizieren des Formulars**

Formulare können [als Vorlagen freigegeben](https://support.microsoft.com/office/82ea9d8a-260a-47a0-afdb-497f3d746e3f)werden, sodass andere Benutzer Sie in Ihr eigenes Konto oder eine Gruppe kopieren können. Die Daten aus Ergebnis Übermittlungen werden dadurch nicht beibehalten. nur Formularstruktur wie Fragen und Einstellungen.

**Exportieren von Ergebnissen in ein Arbeitsblatt**

Wenn die Daten der Formularantworten beibehalten werden müssen, kann dies erreicht werden, indem [die Ergebnisse in ein Excel-Arbeitsblatt exportiert](https://support.office.com/article/02859424-341d-406f-b32a-9a0fbaf357af)werden. Dadurch werden die Fragen und Ihre Antworten nur als Daten exportiert – es werden keine von Formularen erstellten Grafiken einbezogen.


**Löschen des Formulars**

Während das Löschen der Gruppe auch dazu führen kann, dass alle zugeordneten Formulare gelöscht werden, können Gruppenmitglieder [Sie direkt löschen](https://support.microsoft.com/office/2207e468-ce1b-4c4a-a256-caf631d87af0) , ohne ein Besitzer der Gruppe zu sein – dies ist jedoch ein manueller Schritt, der keinen zusätzlichen Nutzen bringt.

## <a name="onenote"></a>OneNote

Das in einer Gruppe enthaltene OneNote-Notizbuch wird in der Bibliothek Website Objekte auf der zugehörigen SharePoint-Website gespeichert. Während Notebook-Dateien manchmal auf mehrere einzelne Dateien verteilt werden können, können Sie nicht einfach kopiert und unabhängig voneinander geöffnet werden. Stattdessen muss der Inhalt des OneNote-Notizbuchs mit OneNote 2016 verschoben oder exportiert werden.

**Seiten und Abschnitte in ein anderes Notizbuch verlagern**

Durch das [individuelle Verschieben von Seiten oder Abschnitten in ein anderes Notizbuch](https://support.office.com/article/c3c8b098-7f9c-4c2a-a0dc-ebb83bc76364) erhalten Besitzer die Möglichkeit, Ihre Daten zu bereinigen und nur das beizubehalten, was aufbewahrt werden muss.

**Exportieren des gesamten Notebooks als Paket**

Wenn das gesamte Notizbuch mit der vorhandenen Struktur beibehalten werden muss, kann es [als OneNote-Paketdatei exportiert](https://support.office.com/article/a4b60da5-8f33-464e-b1ba-b95ce540f309) und anschließend an einen neuen Speicherort importiert werden. Alternativ kann dies als Methode verwendet werden, um den Inhalt in einer einzigen Datei anstelle der vorhandenen mehr Dateistruktur beizubehalten.

**Als PDF drucken**

In Szenarien, in denen einige Inhalte des Notizbuchs nur als Referenz oder als Datensätze aufbewahrt werden müssen, können einzelne Seiten [in PDF gedruckt und an anderer Stelle gespeichert](https://support.office.com/article/13d173b5-7f4c-45a8-94eb-9354d63af5cd)werden.

## <a name="mailbox-and-calendar"></a>Postfach und Kalender

Es ist nicht ungewöhnlich, dass das mit der Gruppe verbundene Postfach verwendet wird, obwohl viele Unterhaltungen möglicherweise in Team Kanälen durchgeführt wurden. Das Postfach speichert nur e-Mails, die direkt per e-Mail an Sie gesendet wurden, und enthält keine e-Mails, die direkt an Kanäle gesendet wurden.

In einigen Fällen können die im Postfach gespeicherten e-Mails einfach Benachrichtigungen über Besprechungen, Planner-Aufgaben Aktualisierungen und andere vom APP oder System generierte Nachrichten sein. Es ist wichtig, dass der Inhalt des Postfachs überprüft wird, um festzustellen, ob der Inhalt aufbewahrt oder gelöscht werden soll.

Wenn eine Aufbewahrungsrichtlinie auf Exchange angewendet wird, werden die e-Mails und Kalenderelemente beibehalten und über eDiscovery-Suchvorgänge zur Verfügung gestellt.

**Exportieren von e-Mail und Kalender**

Team-oder Gruppenmitglieder können [den Inhalt des Postfachs und Kalenders in eine PST-Datei (Outlook Data/Personal Storage) exportieren](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91). Diese Datei kann dann an anderer Stelle gespeichert werden, oder der Inhalt kann in ein anderes Postfach importiert werden. Die erste wird nicht empfohlen, da der Inhalt der PST-Datei nicht durchsuchbar ist, ohne Sie in Outlook zu öffnen, und die Datei selbst kann im Laufe der Zeit beschädigt werden.

**Durch IT-durchgeführte Inhaltsmigration**

Administratoren können Tools von Drittanbietern verwenden, um e-Mails und Kalender Inhalte zwischen Postfächern ohne Benutzereingriff zu migrieren. Ein möglicher Speicherort kann ein freigegebenes Postfach sein, das lediglich als "Archiv" der Gruppen Postfachinhalte dient.

## <a name="planner"></a>Planner

Jede Gruppe oder jedes Team kann mehrere Pläne haben. Es ist wichtig, dass Sie während des offboarding-Prozesses sicherstellen, dass alle Pläne berücksichtigt werden, ob der Inhalt beibehalten wird. Wie die anderen Produkte gibt es verschiedene Ansätze zum extern von Inhalten in Planner.

**Exportieren des Plans in ein Arbeitsblatt**

Wenn nur eine Kopie des Plans zur Aufbewahrung von Datensätzen aufbewahrt werden muss, besteht der einfachste Ansatz darin, [den Plan in ein Excel-Arbeitsblatt zu exportieren](https://support.microsoft.com/office/4d850c6e-e548-4aab-83b4-b62b68662d2a). Dies ist eine unidirektionale Aktion, da es keine Option zum Importieren von Plänen aus einer Kalkulationstabelle gibt.

> [!IMPORTANT]
> Beim Exportieren eines Plans nach Excel werden die meisten Informationen innerhalb des Plans übernommen, es werden jedoch keine Kommentare, Links oder Dateien eingefügt.

**Kopieren und verlagern von Vorgängen in einen anderen Plan**

Dies scheint zwar eine Lösung zu sein, aber einzelne Vorgänge können nur zwischen den Plänen innerhalb der gleichen Gruppe [kopiert oder verschoben](https://support.microsoft.com/office/ad43a5d8-c1ad-42fd-b3da-fe97d72c8a1b) werden, wodurch der Vorteil in dem Fall negiert wird, dass die dem Plan zugeordnete Gruppe gelöscht wird.

**Gesamten Plan kopieren**

Es ist auch möglich, [den gesamten Plan zu kopieren](https://support.microsoft.com/office/50401e13-a25f-40df-93c6-b608cc28c3d4). Dies kann jedoch nicht für eine vorhandene Gruppe oder sogar innerhalb derselben Gruppe sein. Durch Kopieren des Plans wird eine neue Gruppe erstellt. Darüber hinaus enthält das Kopieren des gesamten Plans keine Kommentare, Zuweisungen, Verknüpfungen, Anlagen oder Daten.

## <a name="power-automate"></a>Power Automate

Flows, die in Power Automation erstellt und einer Gruppe oder einem Team zugeordnet sind, gehören nicht zur Gruppe, sondern befinden sich im Besitz des Erstellers und werden nur für andere Benutzer und Gruppen freigegeben. Sie sind daher nicht betroffen, wenn eine Gruppe oder ein Team gelöscht wird.

**Ändern des Besitzes des Flusses**

Wenn der Workflow weiterhin in Betrieb sein muss, können alle Besitzer einfach andere Benutzer oder Microsoft 365-Gruppen als Besitzer hinzufügen.

**Exportieren des Flusses**

Wenn der Workflow nicht weiter ausgeführt werden muss, aber für eine mögliche zukünftige Verwendung beibehalten werden muss, kann er [als Datei exportiert](https://flow.microsoft.com/blog/import-export-bap-packages/) und später erneut importiert werden.

## <a name="power-bi"></a>Power BI

Power BI-Daten und-Arbeitsbereiche können unabhängig von Gruppen und Teams betrieben werden, und wie andere Arbeitslasten bieten unterschiedliche Möglichkeiten der offboarded.

**Kopieren von Berichten in einen anderen Arbeitsbereich**

Wenn der Bericht in seinem Funktionszustand über die Lebensdauer der Gruppe oder des Teams hinaus aufbewahrt werden muss, kann er [aus dem vorhandenen Arbeitsbereich in einen anderen Arbeitsbereich innerhalb von Power BI kopiert](https://docs.microsoft.com/power-bi/connect-data/service-datasets-copy-reports)werden.

**Exportieren von Daten aus einem Dashboard oder Bericht**

Wenn der Bericht nicht mehr aktiv sein muss, aber die Daten beibehalten werden müssen, kann er auch [nach Excel exportiert](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data)werden.

## <a name="project"></a>Project

Projekte und Roadmaps, die in Project im Internet erstellt wurden, können Microsoft 365-Gruppen zugeordnet werden und bieten offboarding ähnliche Ansätze wie Power BI.

**Zuweisen des Projekts zu einer anderen Gruppe**

Wenn das Projekt in seinem Funktionszustand über die Lebensdauer der Gruppe oder des Teams hinaus beibehalten werden muss, kann es mithilfe der Dynamics 365-Verwaltungskonsole [einer anderen Microsoft 365-Gruppe zugewiesen](https://docs.microsoft.com/project-for-the-web/access-a-project-after-group-is-deleted#reassign-the-project) werden.

**Exportieren von Daten aus dem Projekt oder der Roadmap**

Mithilfe der Dynamics 365-Verwaltungskonsole können Sie [Benutzerdaten aus dem Projekt](https://docs.microsoft.com/project-for-the-web/export-user-data-from-project-for-the-web) in eine Kalkulationstabelle exportieren, oder wenn Sie ein PowerShell-Skript verwenden, können die Daten in die Projektdatei (exportiert werden. MPP) und XML-Dateiformate.

## <a name="sharepoint"></a>SharePoint
Alle Dateien in Team Kanälen werden in der Dokumentbibliothek auf der SharePoint-Website der zugeordneten Gruppe gespeichert. In einigen Fällen können andere Inhalte als Dokumente in SharePoint vorhanden sein, beispielsweise Listen oder Seiten.
Dateien werden in der Regel an drei primären Speicherorten in einer SharePoint-Website gespeichert:

- Seiten – Bibliothek für Website Seiten
- In Seiten verwendete Bilder – Bibliothek für Website Objekte
- Dateien in Kanälen – Bibliothek "Dokumente"
- Wiki-Seiten – Microsoft Teams wiki-Datenbibliothek

Wenn die Website über eine oder mehrere Unterwebsites verschachtelt ist, muss der offboarding-Prozess für jede Unterwebsite wiederholt werden. Wenn das Team private Kanäle enthält, gibt es eine separate SharePoint-Website für jeden Kanal.

Es ist wichtig, beim Entfernen von Dateien aus einer Gruppe oder einem Team festzustellen, dass Sie möglicherweise für Benutzer freigegeben werden, die nicht Mitglieder der Gruppe oder des Teams sind (ob intern oder extern für die Organisation), und als solche kann es sinnvoll sein, Ihnen die bevorstehende Änderung mitzuteilen.

**Herunterladen von Dateien**

Im Fall von Dateien, die in SharePoint in einer der oben genannten Bibliotheken gespeichert sind, können diese [auf einen lokalen Computer heruntergeladen](https://support.office.com/article/5c7397b7-19c7-4893-84fe-d02e8fa5df05)werden.

**Dateien verlagern**

Darüber hinaus können Dateien an einen anderen Speicherort in SharePoint verschoben werden, beispielsweise an eine Bibliothek an einer anderen Website.
Referenz https://support.office.com/en-us/article/move-or-copy-files-in-sharepoint-00e2f483-4df3-46be-a861-1f5f0c1a87bc

**Liste exportieren** In SharePoint-Listen gespeicherte Daten können in [eine Excel-Kalkulationstabelle exportiert](https://support.office.com/article/bfb2ea48-6118-4fa9-abb6-cced9424e5d9)und erneut in eine Liste in einer anderen Website importiert werden.

Alternativ kann ein Drittanbietertool verwendet werden, um die Liste zwischen Websites zu migrieren, um Funktionen, Listenansichten, Formatierungen und andere Attribute beizubehalten.

**"Exportieren" von wiki-Dateien**

Wiki-Inhalte innerhalb von Team Kanälen werden in einer HTML-formatierten Datei in einer dedizierten Bibliothek der zugeordneten SharePoint-Website gespeichert. Sie können nicht ohne weiteres exportiert und in ein anderes Kanal wiki importiert werden, sondern können in eine HTML-Datei konvertiert und als Webseite geöffnet werden.

## <a name="microsoft-stream"></a>Microsoft Stream

Wie Power Automation sind Videos im Datenstrom, die einer Gruppe oder einem Team zugeordnet sind, nicht tatsächlich im Besitz der Gruppe und werden nicht gelöscht, wenn die Gruppe gelöscht wird. Videos im Datenstrom befinden sich im Besitz der Person, die das Video hochgeladen oder erstellt hat, selbst wenn Sie Benutzer oder Gruppen als Besitzer hinzufügen. Dies gilt auch für Besprechungen, die in einem Teams-Kanal aufgezeichnet werden. Sie befinden sich im Besitz der Person, die die Aufzeichnung initiiert hat.

**Hinzufügen weiterer Besitzer**

Da das Video unabhängig von der Gruppen Löschung im Datenstrom aufbewahrt wird, kann der ursprüngliche Besitzer [das Video für andere Benutzer und Gruppen freigeben und es sogar als Besitzer hinzufügen](https://docs.microsoft.com/stream/portal-edit-video).

**Video herunterladen**

In Szenarien, in denen das Video nicht im Datenstrom aufbewahrt werden muss oder an einem alternativen Speicherort wie einem Datensatzverwaltungssystem gespeichert werden muss, kann ein Besitzer [es lokal herunterladen](https://docs.microsoft.com/stream/portal-download-video) .

## <a name="yammer"></a>Yammer

Im Gegensatz zu Unterhaltungen in Microsoft Teams bietet jammern sowohl Benutzern als auch Administratoren Optionen zum umlegen oder Exportieren von Unterhaltungen.

**Verlagern von Unterhaltungen in eine andere Gruppe oder Community**

Unterhaltungen können von jedem Benutzer in eine andere Jammer Gruppe verschoben werden, nicht nur auf Besitzer oder Administratoren. Dies ist sowohl im [klassischen jammern](https://support.office.com/article/149c6399-4ac1-4ced-84d7-e0660960a872)als auch in den [neuen Jammer](https://support.office.com/article/d63debf1-1c90-4ec5-b5ae-8a00939a1680) Schnittstellen möglich.

**Exportieren von Netzwerkdaten**

Jammern von Netzwerkadministratoren können einen [Export von Netzwerkdaten](https://docs.microsoft.com/yammer/manage-security-and-compliance/export-yammer-enterprise-data)durchführen, wobei allerdings alle Unterhaltungen für das gesamte Netzwerk exportiert werden. Der resultierende Export listet jedoch die Gruppen-ID auf, sodass es möglich ist, Unterhaltungen basierend auf diesem zu filtern.
