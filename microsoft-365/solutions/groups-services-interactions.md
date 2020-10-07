---
title: Gruppen Dienst Interaktionen
ms.reviewer: ''
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
description: Gruppen Dienst Interaktionen
ms.openlocfilehash: 235a897314a784ba3bb1ac50fe8bdfe9986a70d3
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377629"
---
# <a name="groups-services-interactions"></a>Gruppen Dienst Interaktionen

Microsoft 365 Groups stellt eine allgemeine Struktur für eine Reihe von Diensten und Arbeitslasten innerhalb der Microsoft 365-Plattform bereit, um eine verbundene Benutzeroberfläche für Endbenutzer zu bieten. In seinem Kern besteht eine Microsoft 365-Gruppe, die Folgendes bereitstellt:

- Eine Möglichkeit zum Verwalten der Mitgliedschaft (Azure AD)
- Ein Ort, an dem Messaging und Unterhaltungen stattfinden (Exchange-Postfach, Microsoft Teams, jammern)
- Platz für Dateien, die gespeichert werden sollen (SharePoint)
- Ein Kalender für die Planung (Exchange)
- Ein Notizbuch zum Erfassen von Notizen (OneNote)

Zum Zeitpunkt der Gruppenerstellung wird auch eine Reihe von anderen Ressourcen bereitgestellt, die jedoch erst sichtbar sind, wenn Sie zum ersten Mal aus dem Dienst abgerufen wurden:

- Ein Board für die Verwaltung von Gruppenaufgaben (Planer)
- Ein Arbeitsbereich für die Berichterstellung (Power BI)
- Ein Bereich für freigegebene Videos (Microsoft Stream)
- Ein Bereich für freigegebene Formulare (Formulare)

In Microsoft 365 können andere Dienste mit Microsoft 365-Gruppen interagieren, um zusätzliche Funktionen und Funktionen für Gruppenmitglieder bereitzustellen.
Beispiele hierfür sind:

- Power Apps für apps
- Power Automation für Workflows
- Project im Internet und Roadmap für Wasserfall basierte Projektverwaltung
- Teams für kanalbasierte Unterhaltungen
- Jammern für Interessengemeinschaften

## <a name="user-interactions-with-groups"></a>Benutzerinteraktionen mit Gruppen

Microsoft 365-Gruppen können von einer Vielzahl von Schnittstellen sowohl von Administratoren als auch von Endbenutzern erstellt und verwaltet werden. 

### <a name="administrative-experiences"></a>Administrative Erfahrungen

Administratoren können Microsoft 365-Gruppen aus mehreren der Arbeits Auslastungs-Admin Center, Befehlszeilenschnittstellen, die Skripts unterstützen, sowie von benutzerdefinierten apps, die mit der Graph-API interagieren, erstellen und verwalten. Die einzige Ausnahme hiervon sind Jammer Gruppen, die innerhalb der Jammer-Weboberfläche erstellt werden müssen.

**Verwandte Einstellungen**

In den verschiedenen administrativen Schnittstellen, die Gruppeneinstellungen verwalten können, gibt es mehrere Überschneidungen, die Sie beachten sollten.

**Microsoft 365 Admin Center**

Im Microsoft 365 Admin Center ist Gastzugriff auf Gruppen standardmäßig aktiviert, ebenso wie die Möglichkeit, Besitzern das Hinzufügen von Gästen zu gestatten. In diesem Admin Center stehen keine weiteren Steuerelemente auf Organisationsebene für Gruppen zur Verfügung.

**Azure AD Admin Center**

Das Azure AD Admin Center bietet Steuerelemente, um festzustellen, ob Benutzergruppen erstellen oder Besitzer in Azure-Portalen zuweisen können, sowie Ablauf-und Benennungsrichtlinien Einstellungen.

Das Admin Center bietet auch eine Reihe von Kontrollmaßnahmen für Gast Einladungen, die über das Microsoft 365 Admin Center hinausgehen, beispielsweise die Möglichkeit zu begrenzen, ob nicht-Besitzer auch Gäste einladen können.

**SharePoint**

SharePoint-Websites werden mit den Sicherheitsgruppen "Besitzer", "Mitglied" und "Besucher" erstellt, wobei die ersten beiden mit Ihren Microsoft 365-Gruppen Kollegen übereinstimmen. Während die Mitgliedschaft für SharePoint Online Websites in der Regel von der zugeordneten Microsoft 365-Gruppe verwaltet wird, handelt es sich nicht um eine bidirektionale Beziehung. Alle Änderungen an der Mitgliedschaft auf der Microsoft 365-Gruppenebene spiegeln sich in SharePoint wider, wenn sich die Mitgliedschaft in der SharePoint-Gruppe jedoch ändert, wird dies nicht in der Microsoft 365-Gruppe widergespiegelt.

### <a name="user-experiences"></a>Benutzeroberflächen

Endbenutzer können Gruppen aus mehreren der Dienste in Microsoft 365 erstellen, und in anderen können Sie nur für eine Gruppe freigeben.

Die folgenden Dienste ermöglichen die Erstellung von Gruppen durch Endbenutzer:
                         
Outlook Planner-Projekt für den SharePoint-Stream von Microsoft Teams jammern

**Einschränkung der Gruppenerstellung**

Ein allgemeiner Ansatz zur Steuerung der Ausbreitung von Teams besteht darin, zu begrenzen, welche Benutzer diese erstellen können. Dies kann nur durch Einschränken der Gruppenerstellung erfolgen. Dies wirkt sich auf die Möglichkeit aus, Gruppen aus anderen Diensten zu erstellen, die für Endbenutzer möglicherweise erforderlich sind. Microsoft 365-Gruppen unterstützen nicht die Möglichkeit, die Erstellung von Gruppen für einige apps oder Dienste einzuschränken, während Sie von anderen Benutzern zugelassen werden.

Die Einschränkungen bei der Gruppenerstellung sind zwischen apps und Diensten unterschiedlich:


|APP oder Dienst|Umgebung|
|:-------------|:---------|
|Outlook|**Neue Gruppen** Option wird aus dem Menü "neu" auf der Seite "Personen" entfernt|
|Planner|In **neuem Plan** wird erklärt, dass die Gruppenerstellung deaktiviert wurde und das Hinzufügen des Plans zu einer vorhandenen Gruppe angeboten wird.|
|Projekt für das Internet und Roadmap|Im Menü **Gruppe erstellen** wird erklärt, dass die Gruppenerstellung eingeschränkt ist und eine vorhandene Gruppe verwendet werden soll.|
|SharePoint|Weiterhin in der Lage, eine Teamwebsite zu erstellen, die nicht mit einer Gruppe verbunden ist.|
|Stream|Die Option **Gruppieren** wird nicht unter dem **Menü Erstellen**angezeigt.|
|Teams|Der Benutzer kann kein Team mit einer neuen Gruppe erstellen, aber trotzdem ein Team erstellen, das eine vorhandene Gruppe verwendet.<br><br>**Die Schaltfläche Team erstellen** wird durch **Team erstellen aus einer Gruppe**ersetzt.|
|Yammer|**Die Option "Gruppe erstellen** " wird aus der Navigation der Hauptgruppen/Communitys entfernt.|

## <a name="services-interactions-with-groups"></a>Dienst Interaktionen mit Gruppen

Auf dem Poster "Groups in Microsoft 365" finden Sie Informationen zu unterschiedlichen Gruppentypen, zu deren Erstellung und Verwaltung sowie zu einigen Governance-Empfehlungen.

[![Miniaturbild für Gruppen-Infografik](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

Die folgende Tabelle enthält eine Übersicht über die Interaktionen von Microsoft 365-Gruppen mit verschiedenen Diensten:

|Produkt|Features|Übernimmt der Dienst<br>ohne Gruppe vorhanden?|Kann der Dienst<br>Gruppe erstellen?|Löscht das<br>Instanz löschen der Gruppe?|
|:---|:---|:---|:---|:---|
|Azure AD|Mitgliedschaft, gruppensteuerelemente, Gäste|Ja|Ja|Ja|
|Exchange|Kalender, Postfach|Ja|Ja|Ja|
|Formulare|Formular|Ja|Nein|Nein|
|OneNote|Notizbuch|Ja|Nein|Nein|
|Planner|Aufgaben Ausschuss|Nein|Ja|Ja|
|Power apps-App|App|Ja|Nein|Nein|
|Power Automate|Workflow|Ja|Nein|Nein|
|Power BI (klassisch)|Workspace|Nein|Ja|Ja|
|Power BI (neu)|Workspace|Ja|Nein|Ja|
|Project für das Web|Projektplan|Ja|Ja|Nein|
|Roadmap|Roadmap|Ja|Ja|Nein|
|SharePoint|Website|Ja|Ja|Ja|
|Stream|Kanal, Video|Ja|Ja|Ja|
|Teams|Team|Nein|Ja|Ja|
|Yammer|Group|Ja|Ja|Ja|

Während die obige Tabelle eine allgemeine Übersicht über die Gruppeninteraktionen mit Microsoft 365-Diensten bietet, gibt es eine Reihe von Nuancen und Feinheiten, die Sie verstehen sollten. In den folgenden Abschnitten werden die spezifischen Arbeitsauslastungen und ihre Interaktionen mit Gruppen eingehend untersucht.

## <a name="azure-ad"></a>Azure AD

Azure AD stellt die zugrunde liegenden Identitäts Verwaltungsfunktionen in Microsoft 365 bereit.

**Für Gruppen bereitgestellte wichtige Features**

- Gruppenmitgliedschaft
- Benennungsrichtlinie
- Ablaufrichtlinie
- Gäste
- Einschränkung der Gruppenerstellung

**Kann Azure AD eine Gruppe erstellen?**

Ja, Microsoft 365-Gruppen können aus Azure AD entweder über das Administrations Webportal, über PowerShell oder Graph-API erstellt werden.

**Gibt es Azure AD ohne Gruppe?**

Ja, Azure AD führt eine große Anzahl von Diensten aus, die keinen Bezug zu Microsoft 365-Gruppen haben. Jede Microsoft 365-Gruppe wird als Objekt in Azure AD dargestellt.

**Kann es mehrere Instanzen von Azure AD pro Gruppe geben?**

Nein, es gibt nur eine Instanz von Azure AD.

**Können Azure AD mehreren Gruppen zugeordnet werden?**

Ja, da Azure Ad die zugrunde liegende Plattform ist, die den Gruppen Mitgliedschaftsdienst bereitstellt.

**Kann die Zuordnung von Azure AD zu einer Gruppe geändert werden?**

Nein, Azure AD ist die zugrunde liegende Plattform, auf der Gruppen vorhanden sind.

**Löscht die Instanz gelöscht die Gruppe?**

Durch das Löschen der Gruppe in Azure AD werden relevante gruppenbezogene Dienste und Inhalte gelöscht.

## <a name="teams"></a>Teams

Teams ist ein Chat-zentrierter Arbeitsbereich zur Verbesserung der Zusammenarbeit, indem eine singuläre Schnittstelle für die Interaktion mit einer Vielzahl von Microsoft-und Drittanbieterdiensten bereitgestellt wird.

Wenn ein Team erstellt wird, werden standardmäßig das Postfach und der Kalender, die der Microsoft 365-Gruppe zugeordnet sind, sowohl in der globalen Adressliste in Exchange als auch in Outlook ausgeblendet. Dies kann manuell von einem Administrator außer Kraft gesetzt werden, wenn der Benutzer sowohl Outlook als auch Teams in derselben Microsoft 365-Gruppe verwenden möchte.

**Für Gruppen bereitgestellte wichtige Features**

- Unterhaltungen
- Kanäle & Registerkarten
- Besprechungen

**Können Teams eine Gruppe erstellen?**

Ja, mit dem Erstellen eines neuen Teams wird eine neue Microsoft 365-Gruppe erstellt. Es ist auch möglich, ein Team für eine vorhandene Gruppe zu erstellen, die derzeit nicht über eine Gruppe verfügt.

**Gibt es Teams ohne Gruppe?**

Nein, es ist nicht möglich, dass ein Team ohne Gruppe vorhanden ist.

**Kann es mehrere Teams pro Gruppe geben?**

Nein, die Beziehung zwischen einem Team und einer Gruppe beträgt 1:1.

**Kann ein Team mehreren Gruppen zugeordnet werden?**

Nein, das Team selbst kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Teams mit einer Gruppe ändern?**

Nein, das Team kann immer nur der Gruppe zugeordnet werden, der es ursprünglich zugeordnet war.

**Löscht das Team das Löschen der Gruppe?**

Ja, durch das Löschen des Teams in Microsoft Teams werden die Gruppe, die gruppenbezogenen Dienste und Inhalte gelöscht.

## <a name="exchange"></a>Exchange

Exchange Online bietet Messaging-, Kalender-, Kontakt-und zugehörige Funktionen. Im Kontext einer Gruppe wird nur eine einzelne Ressource zugeordnet – im Gegensatz zu einer ganzen Dienstinstanz.

**Für Gruppen bereitgestellte wichtige Features**

- Postfach und Kalender
- E-Mail-Funktion für alle Gruppenmitglieder
- Speicherung von Microsoft Teams-Kanal Unterhaltungen für eDiscovery-Zwecke, planerische Kommentare

**Kann Exchange eine Gruppe erstellen?**

Ja, es ist möglich, eine Gruppe sowohl aus dem Exchange Online Admin Center als auch aus Outlook zu erstellen. Sie können auch Exchange-Verteilerlisten in Microsoft 365-Gruppen umwandeln.

**Existiert Exchange ohne Gruppe?**

Ja, Exchange Online stellt eine Reihe von Diensten bereit, einschließlich freigegebener Postfächer und Kalender ohne Gruppenzuordnung.

**Kann es mehrere Instanzen von Exchange-Postfächern oder Kalendern pro Gruppe geben?**

Nein, es kann nur ein einzelnes Exchange Online Postfach und ein einzelner Kalender für eine Gruppe sein.

**Können Exchange-Postfächer und Kalender mehreren Gruppen zugeordnet werden?**

Nein, das Postfach und der Kalender weisen eine 1:1-Beziehung mit der Gruppe auf. Es ist möglich, das Postfach für andere Benutzer oder Gruppen freizugeben, allerdings wird dadurch keine Form von Dienstzuordnungen hergestellt.

**Kann die Zuordnung des Exchange-Postfachs oder des Kalenders mit einer Gruppe geändert werden?**

Nein, das Postfach und der Kalender können nicht in eine andere Gruppe geändert werden. Der Inhalt kann jedoch in Outlook oder mithilfe eines Drittanbietertools von einem Postfach in ein anderes verschoben werden.

**Wird durch das Löschen des Postfachs die Gruppe gelöscht?**

Ja, durch das Löschen des Postfachs in Exchange werden sowohl die Gruppe als auch die gruppenbezogenen Dienste und Inhalte gelöscht.

## <a name="forms"></a>Formulare

Formulare bieten webbasierte Umfragen und Quiz.

**Für Gruppen bereitgestellte wichtige Features**

- Besitz von Formularen

**Können Formulare eine Gruppe erstellen?**

Nein, Formulare können keine Gruppe erstellen.

**Gibt es Formulare ohne Gruppe?**

Ja, Umfragen und Quiz können direkt im Konto eines Endbenutzers erstellt werden.

**Kann es mehrere Formulare pro Gruppe geben?**

Ja, es kann mehrere Formulare geben, die einer Gruppe zugeordnet sind.

**Können Formulare mehreren Gruppen zugeordnet werden?**

Nein, ein Formular kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Formulars zu einer Gruppe ändern?**

Nein, wenn ein Formular einer Gruppe zugeordnet ist (entweder direkt in erstellt oder von einer Person übertragen wurde), kann es nicht in eine andere Gruppe verschoben werden.

**Wird durch das Löschen des Formulars die Gruppe gelöscht?**

Nein, es ist nicht möglich, eine Gruppe aus der Formularschnittstelle zu löschen, sondern nur einzelne Formulare.

## <a name="onenote"></a>OneNote

OneNote ist eine digitale Notebook-Anwendung. Das OneNote-Notizbuch, das mit einer Gruppe erstellt wurde, ist eine Datei in der zugeordneten SharePoint-Website und nicht ein mit der Gruppe verbundener Dienst.

**Für Gruppen bereitgestellte wichtige Features**

- Freigegebenes Notizbuch (in der SharePoint-Bibliothek mit Gruppenzuordnung gespeichert)

**Kann OneNote eine Gruppe erstellen?**

Nein, die OneNote-Anwendung kann keine Gruppe erstellen.

**Gibt es OneNote-Notizbücher ohne Gruppe?**

Ja, Notizbücher können direkt in OneDrive oder an anderen freigegebenen Speicherorten erstellt werden.

**Kann es mehrere OneNote-Notizbücher pro Gruppe geben?**

Ja, ein Notizbuch wird standardmäßig erstellt, andere können hinzugefügt werden, allerdings wird jeder Link zu OneNote von gruppenbezogenen Diensten immer an das Standardnotizbuch weitergegeben.

**Kann ein OneNote-Notizbuch mehreren Gruppen zugeordnet werden?**

Nein, das Notizbuch wird in der mit der Gruppe verknüpften SharePoint-Website Bibliothek gespeichert und mit verschiedenen Schnittstellen verknüpft. Sie kann jedoch für andere Gruppen auf die gleiche Weise freigegeben werden, wie Sie für einzelne Personen freigegeben werden kann.

**Kann die Verbindung des Notizbuchs mit einer Gruppe geändert werden?**

Nein, das Notizbuch selbst ist der Gruppe zugeordnet und kann direkt über andere Gruppen verbundene Dienste aufgerufen werden, der Inhalt kann jedoch in der OneNote-Anwendung von einem Notizbuch in ein anderes verschoben werden.

**Löscht das Notizbuch das Löschen der Gruppe?**

Nein, wenn das OneNote-Notizbuch jedoch gelöscht wird, sind möglicherweise fehlerhafte Links in einigen der Gruppen zugeordneten Dienste vorhanden.

## <a name="planner"></a>Planner

Planner ist ein einfacher Verwaltungsdienst für Gruppenaufgaben.

**Für Gruppen bereitgestellte wichtige Features**

- Vorstand für die Verwaltung von Gruppenaufgaben

**Kann Planner eine Gruppe erstellen?**

Ja, bei der Erstellung eines Plans wird eine neue Gruppe erstellt.

**Besteht ein Planer-Motherboard ohne Gruppe?**

Nein, ein Plan muss einer Gruppe zugeordnet sein.

**Kann es mehrere Pläne pro Gruppe geben?**

Ja, es kann mehrere Pläne pro Gruppe geben.

**Kann ein Plan mehreren Gruppen zugeordnet werden?**

Nein, ein Plan basiert ausschließlich auf der Gruppenmitgliedschaft, um den Zugriff zu bestimmen.

**Kann sich die Zuordnung eines Plans zu einer Gruppe ändern?**

Nein, beim Kopieren eines Plans wird jedoch eine neue Gruppe erstellt.

> [!NOTE]
> Eine Gruppe, die von einer anderen Anwendung erstellt wurde, wird für einen Benutzer nicht automatisch in Planner angezeigt. Um zunächst auf das Motherboard zugreifen zu können, müssen Sie es aus einer anderen gruppenbasierten Schnittstelle wie Outlook öffnen.

**Löscht der Plan das Löschen der Gruppe?**

Ja, durch das Löschen des Plans werden die Gruppe und die gruppenbezogenen Dienste und Inhalte gelöscht.

## <a name="power-apps"></a>Power-Apps

Power-Apps bieten eine Leinwand für die APP-Entwicklung ohne Code.

**Für Gruppen bereitgestellte wichtige Features**

- Apps können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll.

**Können Power apps eine Gruppe erstellen?**

Nein, Power Apps können keine Microsoft 365-Gruppe erstellen.

**Gibt es Power-apps ohne Gruppe?**

Ja, Apps können in Power Apps erstellt und innerhalb des Creators-Kontos gespeichert werden, bis Sie freigegeben oder veröffentlicht werden.

**Kann es mehrere apps pro Gruppe geben?**

Ja, es können mehrere Apps für eine Gruppe freigegeben werden.

**Können apps mehreren Gruppen zugeordnet werden?**

Ja, eine APP kann für mehrere Gruppen freigegeben werden.

**Kann sich die Zuordnung einer APP mit einer Gruppe ändern?**

Ja, da die Zuordnung zwischen Power apps und einer Microsoft 365-Gruppe nur gemeinsam genutzt wird – die APP befindet sich immer noch beim Creator.

> [!IMPORTANT]
> [Für Gruppen muss die Sicherheit aktiviert sein, damit Apps für Sie freigegeben werden können](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).

**Löscht die APP das Löschen der Gruppe?**

Nein, die apps sind nicht mit der anderen Gruppe verbunden, als für Sie freigegeben wurde.

## <a name="power-automate"></a>Power Automate

Power Automation (früher bekannt als Microsoft Flow) bietet Workflows und Automatisierungs Dienste.

**Für Gruppen bereitgestellte wichtige Features**

- Workflows können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll.

**Kann Power Automation eine Gruppe erstellen?**

Nein, Power Automation kann keine Microsoft 365-Gruppe im Kontext einer Verbindung mit einem erstellen.

Es ist jedoch möglich, einen Fluss zu erstellen, der verschiedene Vorgänge wie das Erstellen einer Azure AD Sicherheitsgruppe oder das Aktualisieren der Mitgliedschaft einer Microsoft 365-Gruppe ausführt.

**Gibt es Flüsse ohne Gruppe?**

Ja, Flows können innerhalb von Power Automation erstellt und innerhalb des Creators-Kontos gespeichert werden, bis Sie freigegeben oder veröffentlicht werden.

**Kann es mehrere Flows pro Gruppe geben?**

Ja, es können mehrere Flows für eine Gruppe freigegeben werden.

**Kann ein Flow mehreren Gruppen zugeordnet werden?**

Ja, ein Fluss kann für mehrere Gruppen freigegeben werden.

**Kann sich die Zuordnung eines Flows mit einer Gruppe ändern?**

Ja, da die Verbindung zwischen Power Automation und einer Microsoft 365-Gruppe nur gemeinsam genutzt wird – der Fluss befindet sich immer noch bei dem Ersteller.

**Wird durch Löschen eines Flows die Gruppe gelöscht?**

Nein, wie Power-apps sind die Flows nicht mit der anderen Gruppe verbunden, als Sie für Sie freigegeben hat.

## <a name="power-bi-classic"></a>Power BI (klassisch)

Power BI bietet interaktive datengesteuerte Dashboards und Berichte.

**Für Gruppen bereitgestellte wichtige Features**

- Daten Berichte

**Kann Power BI eine Gruppe erstellen?**

Ja, durch das Erstellen eines klassischen Arbeitsbereichs wird eine Microsoft 365-Gruppe erstellt.

**Gibt es einen Power BI Classic-Arbeitsbereich ohne Gruppe?**

Nein, [ein klassischer Arbeitsbereich in Power BI muss einer Gruppe zugeordnet sein](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).

**Kann es mehrere Power BI-Arbeitsbereiche pro Gruppe geben?**

Nein, die Beziehung zwischen einem klassischen Arbeitsbereich und einer Gruppe beträgt 1:1.

**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**

Technisch gesehen Nein, während der klassische Arbeitsbereich mit der Gruppe erstellt wird, können die Inhalte außerhalb der Gruppe mit Benutzern und Sicherheitsgruppen freigegeben werden.

**Kann die Zuordnung des Arbeitsbereichs zu einer Gruppe geändert werden?**

Nein, der klassische Arbeitsbereich selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch in der Power BI-Schnittstelle von einem Arbeitsbereich in einen anderen verschoben werden oder indem Inhalt lokal exportiert wird.

**Wird durch Löschen des Arbeitsbereichs die Gruppe gelöscht?**

Ja, durch das Löschen des Arbeitsbereichs in Power BI werden Gruppen Dienste und Inhalte gelöscht, die Gruppen zugeordnet sind.

## <a name="power-bi-new"></a>Power BI (neu)

Power BI bietet interaktive datengesteuerte Dashboards und Berichte.

Während das Erstellen eines neuen Arbeitsbereichs in Power BI keine Microsoft 365-Gruppe erstellt, wird durch Erstellen einer Gruppe auf andere Weise ein neuer (nicht klassischer) Arbeitsbereich in Power BI erstellt.

**Für Gruppen bereitgestellte wichtige Features**

- Daten Berichte

**Kann Power BI eine Gruppe erstellen?**

Nein, es ist nicht möglich, eine Microsoft 365-Gruppe aus der neuen Power BI-Schnittstelle zu erstellen.

**Gibt es den neuen Power BI-Arbeitsbereich ohne Gruppe?**

Ja, es ist möglich, dass in Power BI Berichte und Arbeitsbereiche erstellt werden, die nicht mit Microsoft 365-Gruppen verknüpft sind.

**Kann es mehrere Arbeitsbereiche pro Gruppe geben?**

Ja, [mehrere Arbeitsbereiche, die von Power BI erstellt wurden, können für eine einzelne Gruppe freigegeben werden](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).

**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**

Nein, ein von Power BI erstellter Arbeitsbereich kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Arbeitsbereichs mit einer Gruppe ändern?**

Ja und Nein. Ein von Power BI erstellter Arbeitsbereich kann nur einer einzelnen Gruppe gleichzeitig zugeordnet werden, kann die Zuordnung jedoch jederzeit ändern. Ein Arbeitsbereich, der in Power BI von einer Gruppe erstellt wurde, ist dieser Gruppe dauerhaft zugeordnet.

**Wird durch Löschen des Arbeitsbereichs die Gruppe gelöscht?**

Ja, durch das Löschen des Arbeitsbereichs in Power BI werden die Gruppe und die gruppenbezogenen Dienste und Inhalte gelöscht.

## <a name="project-for-the-web"></a>Project für das Web

Project für das Internet bietet die Möglichkeit zum Erstellen von Projektplänen, Gantt-Diagrammen und Roadmaps.
Für Gruppen bereitgestellte Hauptfeatures.

- Projektpläne

**Kann Project für das Internet eine Gruppe erstellen?**

Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus Project für das Internet zu erstellen.

**Gibt es Projekte ohne Gruppe?**

Ja, Projekte können vorhanden sein, ohne einer Microsoft 365-Gruppe zugeordnet zu sein, jedoch erfordert die Zuweisung von Aufgaben eine Gruppenzuordnung.

**Kann es mehrere Projekte pro Gruppe geben?**

Ja, es ist möglich, mehrere Projekte in einer einzelnen Gruppe zu verbinden.

**Kann Project mehreren Gruppen zugeordnet werden?**

Nein, ein Projekt kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Projekts mit einer Gruppe ändern?**

Nein, wenn die Zuordnung mit einer Gruppe hergestellt wird, kann Sie nicht geändert werden.

**Löscht das Löschen des Projekts die Gruppe?**

Nein, wenn das Projekt in Project für das Internet gelöscht wird, wird die Gruppe nicht gelöscht.

## <a name="roadmap"></a>Roadmap

Roadmap bietet die Möglichkeit zum Erstellen von Projekt-Roadmaps mit Project für das Internet und Project online.

**Für Gruppen bereitgestellte wichtige Features**

- Projekt-Roadmaps

**Kann Roadmap eine Gruppe erstellen?**

Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus der Roadmap zu erstellen.

**Gibt es eine Roadmap ohne Gruppe?**

Ja, Roadmaps können vorhanden sein, ohne einer Microsoft 365-Gruppe zugeordnet zu sein, allerdings erfordert die Freigabe der Roadmap eine Gruppenzuordnung.

**Kann es mehrere Roadmaps pro Gruppe geben?**

Ja, es ist möglich, mehrere Roadmaps mit einer einzelnen Gruppe zu verbinden.

**Kann eine Roadmap mehreren Gruppen zugeordnet werden?**

Nein, eine Roadmap kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung einer Roadmap zu einer Gruppe ändern?**

Nein, wenn die Zuordnung mit einer Gruppe hergestellt wird, kann Sie nicht geändert werden.

**Wird durch das Löschen der Roadmap die Gruppe gelöscht?**

Nein, durch das Löschen der Roadmap wird die Gruppe nicht gelöscht.

## <a name="sharepoint"></a>SharePoint

SharePoint ist eine webbasierte Content Management-Plattform, die unter anderem Speicherdienste für eine Reihe von Microsoft 365-Diensten bereitstellt.

**Für Gruppen bereitgestellte wichtige Features**

- Dokumentbibliothek
- Bibliothek zum Speichern des OneNote-Notizbuchs
- Speichern von wiki-Dateien für Microsoft Teams

**Kann SharePoint eine Gruppe erstellen?**

Ja, durch das Erstellen einer Teamwebsite in SharePoint wird standardmäßig eine Microsoft 365-Gruppe erstellt. Es ist auch möglich, eine Gruppe und optional ein Team für eine vorhandene Website zu erstellen.

**Sind SharePoint-Websites ohne Gruppe vorhanden?**

Ja, SharePoint bietet eine Reihe nicht Gruppen zugeordneter Dienste und Websites wie Kommunikation und Hub-Websites. 

**Kann es mehrere Standorte pro Gruppe geben?**

Nein, es kann nur einen einzelnen Standort pro Gruppe geben. Private Kanäle in Microsoft Teams verwenden zusätzliche Websites, die nicht mit der Gruppe verbunden sind.

**Können Websites mehreren Gruppen zugeordnet werden?**

Technisch gesehen Nein, aber während eine Website mit einer Gruppe erstellt wird, können die Inhalte für andere Gruppen freigegeben werden.

**Kann sich die Zuordnung einer Website zu einer Gruppe ändern?**

Nein, die Website selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch von einer Website in eine andere innerhalb der SharePoint-Benutzeroberfläche verschoben werden, indem Inhalte lokal exportiert werden oder ein Drittanbietertool verwendet wird.

**Löscht die Website gelöscht die Gruppe?**

Ja, durch das Löschen der Website in SharePoint werden Gruppen-und gruppenbezogene Dienste und Inhalte gelöscht.

## <a name="stream"></a>Stream

Microsoft Stream ist eine Plattform für Video Hosting und-Freigaben.

**Für Gruppen bereitgestellte wichtige Features**

- Video Speicher
- Teams-Besprechungsaufzeichnung
- Video Kanäle

**Kann Stream eine Gruppe erstellen?**

Ja, es ist möglich, eine neue Microsoft 365-Gruppe direkt aus dem Datenstrom zu erstellen.

**Gibt es Datenstrom ohne Gruppe?**

Ja, Videokanäle und Videos können in Stream vorhanden sein, ohne einer Gruppe zugeordnet zu sein.

**Kann es mehrere Videos und Kanäle pro Gruppe geben?**

Ja, in jeder Gruppe kann es mehrere Videos und Kanäle geben.

**Kann ein Video oder Kanal mehreren Gruppen zugeordnet werden?**

Ja, während ein Video oder Kanal mit einer Gruppe erstellt wird, kann es für andere Gruppen freigegeben werden.

**Kann sich die Zuordnung zu einer Gruppe ändern?**

Ja und Nein; Videos im Datenstrom befinden sich im Besitz des ursprünglichen Uploaders oder der Besprechungsaufzeichnung und können daher jeder Gruppe zugeordnet werden, Videokanäle können jedoch nur der Gruppe zugeordnet werden, in der Sie ursprünglich erstellt wurden.

**Löscht das Löschen von Videos oder Kanälen die Gruppe?**

Nein, durch das Löschen von Videos oder Kanälen wird die Gruppe nicht gelöscht. Durch das Löschen der Gruppe selbst in Stream werden jedoch gruppenbezogene Dienste und Inhalte gelöscht, mit Ausnahme der tatsächlichen Videos.

## <a name="yammer"></a>Yammer

Jammern ist eine Enterprise-Plattform für soziale Netzwerke, die das Engagement der Community innerhalb und zwischen Organisationen fördern soll.

Durch das Erstellen einer Community (früher als "Group" bezeichnet) in jammern wird ein Postfach erstellt, das derzeit jedoch nicht verwendet wird.

Eine Microsoft 365-Gruppe, die mit "jammern" verknüpft ist, kann nicht mit einem Team in Microsoft Teams verwendet werden.

**Für Gruppen bereitgestellte wichtige Features**

- Unterhaltungsbereich

**Kann jammern eine Microsoft 365-Gruppe erstellen?**

Ja, beim Erstellen einer neuen Gruppe in "jammern" wird eine neue Microsoft 365-Gruppe erstellt, wenn die Plattformen verbunden sind und der Benutzer die Möglichkeit hat, eine Gruppe zu erstellen.

Eine Jammer Gruppe mit zugeordneter Microsoft 365-Gruppe kann nicht in einer anderen Schnittstelle oder einem anderen Dienst als "jammern" erstellt werden.

**Gibt es eine Jammer Gruppe ohne Microsoft 365-Gruppe?**

Ja, es ist möglich, eine Jammer Gruppe ohne Microsoft 365-Gruppe zu erstellen.

Wenn die Jammer Plattform nicht mit Microsoft 365-Gruppen verbunden ist oder Benutzer nicht in der Lage sind, eine Microsoft 365-Gruppe zu erstellen, werden Jammer Gruppen ohne Microsoft 365 Group Association erstellt.

**Kann es mehrere Jammer Gruppen pro Microsoft 365-Gruppe geben?**

Nein, die Beziehung zwischen einer Jammer Gruppe und einer Microsoft 365-Gruppe lautet 1:1.

**Kann eine Jammer Gruppe mehreren Microsoft 365-Gruppen zugeordnet werden?**

Nein, die Gruppe "jammern" kann nur einer einzelnen Microsoft 365-Gruppe zugeordnet werden. Es ist möglich, dass Beiträge für andere Jammer Gruppen freigegeben oder verschoben werden.

**Kann die Zuordnung einer Jammer Gruppe zu einer Microsoft 365-Gruppe geändert werden?**

Nein, die Gruppe "jammern" kann immer nur der Microsoft 365-Gruppe zugeordnet werden, der Sie ursprünglich zugeordnet war.

**Löscht die Gruppe "jammern" die Microsoft 365-Gruppe?**

Ja, durch das Löschen der Gruppe in "jammern" werden die zugehörigen Dienste und Inhalte von Microsoft Group und Group gelöscht.

