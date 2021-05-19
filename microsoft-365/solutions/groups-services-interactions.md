---
title: Gruppen von Dienstinteraktionen
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
recommendations: false
description: Gruppen von Dienstinteraktionen
ms.openlocfilehash: f9b0d7ca61d55e3d23aa94577fc8257073b26675
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539203"
---
# <a name="groups-services-interactions"></a>Gruppen von Dienstinteraktionen

Microsoft 365 Gruppen bieten eine allgemeine Struktur für eine Reihe von Diensten und Arbeitsauslastungen innerhalb der Microsoft 365, um endbenutzern eine verbundene Benutzererfahrung zu bieten. Im Kern ist eine Microsoft 365 vorhanden, um:

- Eine Möglichkeit zum Verwalten der Mitgliedschaft (Azure AD)
- Ein Ort, an dem Nachrichten und Unterhaltungen stattfinden (Exchange Postfach, Microsoft Teams, Yammer)
- Ein Ort, an dem Dateien gespeichert werden (SharePoint)
- Ein Kalender für die Planung (Exchange)
- Ein Notizbuch zum Aufzeichnen von Notizen (OneNote)

Zum Zeitpunkt der Gruppenerstellung werden auch eine Reihe anderer Ressourcen bereitgestellt, die jedoch erst angezeigt werden, wenn erstmals über den Dienst auf sie zugegriffen wird:

- Ein Board zum Verwalten von Gruppenaufgaben (Planner)
- Ein Arbeitsbereich für die Berichterstellung (Power BI)
- Ein Bereich für freigegebene Videos (Microsoft Stream)
- Ein Bereich für freigegebene Formulare (Formulare)

In Microsoft 365 können andere Dienste mit Microsoft 365 interagieren, um gruppenmitgliedern zusätzliche Funktionen und Funktionen bereitzustellen.
Beispiele hierfür sind:

- Power Apps für Apps
- Power Automate für Workflows
- Project im Web und Roadmap für wasserfallbasiertes Projektmanagement
- Teams für kanalbasierte Unterhaltungen
- Yammer für Communitys von Interesse

## <a name="user-interactions-with-groups"></a>Benutzerinteraktionen mit Gruppen

Microsoft 365 Gruppen können über eine Vielzahl von Schnittstellen erstellt und verwaltet werden, sowohl von Administratoren als auch von Endbenutzern. 

### <a name="administrative-experiences"></a>Verwaltungserfahrungen

Administratoren können Microsoft 365 von mehreren Workload Admin Centern, Befehlszeilenschnittstellen, die Skripting unterstützen, sowie benutzerdefinierte Apps, die mit der Graph interagieren, erstellen und verwalten. Die einzige Ausnahme ist Yammer Gruppen, die innerhalb der Yammer erstellt werden müssen.

**Verwandte Einstellungen**

In den verschiedenen administrativen Schnittstellen, die Gruppeneinstellungen verwalten können, gibt es mehrere Überschneidungen, die Sie beachten sollten.

**Microsoft 365 Admin Center**

Im Microsoft 365 Admin Center ist der Gastzugriff auf Gruppen standardmäßig aktiviert, ebenso wie die Möglichkeit, Besitzern das Hinzufügen von Gästen zu ermöglichen. In diesem Admin Center sind keine weiteren Steuerelemente auf Organisationsebene für Gruppen verfügbar.

**Azure AD Admin Center**

Das Azure AD Admin Center bietet Steuerungen darüber, ob Benutzer Gruppen erstellen oder Besitzer in Azure-Portalen zuweisen können, sowie Ablauf- und Benennungsrichtlinieneinstellungen.

Das Admin Center bietet auch eine Reihe von Steuerungsmaßnahmen für Gasteinladungen, die über die des Microsoft 365 Admin Centers hinausgehen, z. B. die Möglichkeit, zu begrenzen, ob Nichtbesitzer auch Gäste einladen können.

**SharePoint**

SharePoint websites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts. Während die Mitgliedschaft SharePoint Onlinewebsites im Allgemeinen von der zugeordneten Microsoft 365 verwaltet wird, handelt es sich nicht um eine bidirektionale Beziehung. Alle Änderungen an der Mitgliedschaft auf Microsoft 365 Gruppenebene werden in SharePoint wider. Wenn die Mitgliedschaft in der SharePoint-Gruppe geändert wird, wird dies jedoch nicht in der Gruppe Microsoft 365 wider.

### <a name="user-experiences"></a>Benutzererfahrungen

Endbenutzer können Gruppen aus mehreren Diensten innerhalb Microsoft 365 erstellen, und in anderen können sie gruppenfreigaben.

Die folgenden Dienste ermöglichen das Erstellen von Gruppen durch Endbenutzer:
                         
Outlook Planner Project für das Web SharePoint Stream Microsoft Teams Yammer

**Einschränkung der Gruppenerstellung**

Ein gängiger Ansatz zum Steuern der Aussiedelung von Teams besteht in der Beschränkung, welche Benutzer sie erstellen können. Dies kann nur durch Einschränken der Erstellung von Gruppen geschehen. Dies wirkt sich auf die Möglichkeit aus, Gruppen aus anderen Diensten zu erstellen, wo dies für Endbenutzer erforderlich sein kann. Microsoft 365 Gruppen unterstützen nicht die Möglichkeit, die Erstellung von Gruppen aus einigen Apps oder Diensten einzuschränken und dies von anderen zu erlauben.

Die Erfahrung der Gruppenerstellungseinschränkung variiert zwischen Apps und Diensten:


|App oder Dienst|Umgebung|
|:-------------|:---------|
|Outlook|**Neue Gruppenoption** wird aus dem Menü Neu auf der Personenseite entfernt.|
|Planner|**Neuer Plan** erläutert, dass die Gruppenerstellung deaktiviert wurde, und bietet an, den Plan einer vorhandenen Gruppe hinzuzufügen.|
|Project für das Web und roadmap|**Im Menü** Gruppen erstellen wird erläutert, dass die Gruppenerstellung eingeschränkt ist, und es wird vorgeschlagen, eine vorhandene Gruppe zu verwenden.|
|SharePoint|Weiterhin in der Lage, eine Teamwebsite zu erstellen, die nicht mit einer Gruppe verbunden ist.|
|Stream|Die Option **"Gruppe"** wird nicht im Menü **Erstellen angezeigt.**|
|Teams|Der Benutzer kann kein Team mit einer neuen Gruppe erstellen, aber dennoch ein Team erstellen, das eine vorhandene Gruppe verwendet.<br><br>**Erstellen einer Teamschaltfläche** wird durch **Team aus einer Gruppe erstellen ersetzt.**|
|Yammer|**Erstellen einer Gruppenoption** wird aus der Hauptnavigation gruppen/communities entfernt.|

## <a name="services-interactions-with-groups"></a>Diensteinteraktionen mit Gruppen

Informationen zu unterschiedlichen Gruppentypen, deren Erstellen und Verwaltung sowie einige Empfehlungen zur Steuerung finden Sie auf dem Poster "Gruppen in Microsoft 365".

[![Miniaturbild für Gruppen-Infografik](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)

In der folgenden Tabelle finden Sie eine Übersicht Microsoft 365 Gruppeninteraktionen mit verschiedenen Diensten:

|Produkt|Features|Führt den Dienst aus<br>ohne Gruppe vorhanden?|Kann der Dienst<br>Eine Gruppe erstellen?|Löscht die<br>Instanz die Gruppe löschen?|
|:---|:---|:---|:---|:---|
|Azure AD|Mitgliedschaft, Gruppensteuerelemente, Gäste|Ja|Ja|Ja|
|Exchange|Kalender, Postfach|Ja|Ja|Ja|
|Formulare|Formular|Ja|Nein|Nein|
|OneNote|Notizbuch|Ja|Nein|Nein|
|Planner|Task Board|Nein|Ja|Ja|
|Power Apps App|App|Ja|Nein|Nein|
|Power Automate|Workflow|Ja|Nein|Nein|
|Power BI (klassisch)|Workspace|Nein|Ja|Ja|
|Power BI (neu)|Workspace|Ja|Nein|Ja|
|Project für das Web|Project Plan|Ja|Ja|Nein|
|Roadmap|Roadmap|Ja|Ja|Nein|
|SharePoint|Website|Ja|Ja|Ja|
|Stream|Kanal, Video|Ja|Ja|Ja|
|Teams|Team|Nein|Ja|Ja|
|Yammer|Group|Ja|Ja|Ja|

Während die obige Tabelle einen umfassenden Überblick über Gruppeninteraktionen mit Microsoft 365-Diensten bietet, sollten Sie eine Reihe von Nuancen und Feinheiten verstehen. In den folgenden Abschnitten werden die spezifischen Arbeitsauslastungen und deren Interaktionen mit Gruppen genauer beschrieben.

## <a name="azure-ad"></a>Azure AD

Azure AD bietet die zugrunde liegenden Identitätsverwaltungsfunktionen in Microsoft 365.

**Wichtige Features für Gruppen**

- Gruppenmitgliedschaft
- Benennungsrichtlinie
- Ablaufrichtlinie
- Gäste
- Einschränkung der Gruppenerstellung

**Kann Azure AD eine Gruppe erstellen?**

Ja, Microsoft 365 Gruppen können aus Azure AD entweder über das Verwaltungswebportal, über PowerShell oder über eine Graph werden.

**Gibt es Azure AD ohne Gruppe?**

Ja, Azure AD führt eine große Anzahl von Diensten durch, die keinen Bezug zu Microsoft 365 haben. Jede Microsoft 365 wird in Azure AD als Objekt dargestellt.

**Gibt es mehrere Instanzen von Azure AD pro Gruppe?**

Nein, es gibt nur eine Instanz von Azure AD.

**Kann Azure AD mehreren Gruppen zugeordnet werden?**

Ja, da Azure AD die zugrunde liegende Plattform ist, die den Gruppenmitgliedschaftsdienst bietet.

**Kann sich die Zuordnung von Azure AD zu einer Gruppe ändern?**

Nein, Azure AD ist die zugrunde liegende Plattform, auf der Gruppen vorhanden sind.

**Löscht das Löschen der Instanz die Gruppe?**

Wenn Sie die Gruppe in Azure AD löschen, werden relevante gruppenverkn nente Dienste und Inhalte gelöscht.

## <a name="teams"></a>Teams

Teams ist ein chatzentrierter Arbeitsbereich, der die Zusammenarbeit verbessern soll, indem eine einzigartige Schnittstelle für die Interaktion mit einer Vielzahl von Microsoft- und Drittanbieterdiensten zur Verfügung steht.

Wenn ein Team erstellt wird, werden das postfach und der gruppe Microsoft 365 zugeordnete Postfach und Kalender standardmäßig sowohl in der globalen Adressliste in Exchange als auch in Outlook. Dies kann manuell von einem Administrator außer Kraft gesetzt werden, wenn der Benutzer sowohl Outlook als auch Teams für die Microsoft 365 verwenden möchte.

**Wichtige Features für Gruppen**

- Unterhaltungen
- Kanäle & Registerkarten
- Besprechungen

**Können Teams eine Gruppe erstellen?**

Ja, das Erstellen eines neuen Teams erstellt eine neue Microsoft 365 Gruppe. Es ist auch möglich, ein Team für eine vorhandene Gruppe zu erstellen, die derzeit nicht über ein Team verfügt.

**Gibt es Teams ohne Gruppe?**

Nein, es ist nicht möglich, dass ein Team ohne eine Gruppe vorhanden ist.

**Kann es mehrere Teams pro Gruppe geben?**

Nein, die Beziehung zwischen einem Team und einer Gruppe ist 1:1.

**Kann ein Team mehreren Gruppen zugeordnet werden?**

Nein, das Team selbst kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Teams zu einer Gruppe ändern?**

Nein, das Team kann nur der Gruppe zugeordnet werden, der es ursprünglich zugeordnet wurde.

**Löscht das Löschen des Teams die Gruppe?**

Ja, durch das Löschen des Teams in Microsoft Teams werden die Gruppe, die mit der Gruppe verknüpften Dienste und der Inhalt gelöscht.

## <a name="exchange"></a>Exchange

Exchange Online bietet Messaging-, Kalender-, Kontakt- und zugehörige Funktionen. Im Kontext einer Gruppe wird nur eine einzelne Ressource zugeordnet – im Gegensatz zu einer gesamten Dienstinstanz.

**Wichtige Features für Gruppen**

- Postfach und Kalender
- Möglichkeit, alle Gruppenmitglieder per E-Mail zu senden
- Storage Teams kanalunterhaltungen für eDiscovery-Zwecke, Planner-Kommentare

**Können Exchange eine Gruppe erstellen?**

Ja, es ist möglich, eine Gruppe aus dem Exchange Online Admin Center sowie aus Outlook. Sie können auch Exchange Verteilerlisten in Microsoft 365 konvertieren.

**Gibt Exchange ohne Eine Gruppe?**

Ja, Exchange Online stellt eine Reihe von Diensten, einschließlich freigegebener Postfächer und Kalender, ohne Gruppenverbund zur Verfügung.

**Kann es mehrere Instanzen von Exchange Postfächern oder Kalendern pro Gruppe geben?**

Nein, es kann nur ein einzelnes Postfach Exchange Online Kalender für eine Gruppe sein.

**Können Exchange Postfächern und Kalendern mehreren Gruppen zugeordnet werden?**

Nein, das Postfach und der Kalender haben eine 1:1-Beziehung mit der Gruppe. Es ist möglich, das Postfach für andere Benutzer oder Gruppen zu teilen, es wird jedoch keine Form der Dienst zuordnung erstellt.

**Kann sich Exchange Zuordnung eines Postfachs oder Kalenders zu einer Gruppe ändern?**

Nein, das Postfach und der Kalender können nicht in eine andere Gruppe geändert werden. Der Inhalt kann jedoch innerhalb von Outlook oder mithilfe eines Drittanbietertools von einem Postfach in ein anderes verschoben werden.

**Löscht das Löschen des Postfachs die Gruppe?**

Ja, das Löschen des Postfachs in Exchange löscht die Gruppe sowie die gruppenverkn nenten Dienste und Inhalte.

## <a name="forms"></a>Formulare

Formulare bieten webbasierte Umfragen und Quizfragen.

**Wichtige Features für Gruppen**

- Besitz von Formularen

**Können Formulare eine Gruppe erstellen?**

Nein, Forms kann keine Gruppe erstellen.

**Sind Formulare ohne Gruppe vorhanden?**

Ja, Umfragen und Quiz können direkt im Konto eines Endbenutzers erstellt werden.

**Gibt es mehrere Formulare pro Gruppe?**

Ja, einer Gruppe können mehrere Formulare zugeordnet sein.

**Können Formulare mehreren Gruppen zugeordnet werden?**

Nein, ein Formular kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Formulars zu einer Gruppe ändern?**

Nein, sobald ein Formular einer Gruppe zugeordnet ist (entweder direkt innerhalb erstellt oder von einer Person übertragen) kann es nicht in eine andere Gruppe verschoben werden.

**Löscht das Löschen des Formulars die Gruppe?**

Nein, es ist nicht möglich, eine Gruppe aus der Forms-Schnittstelle zu löschen, sondern nur einzelne Formulare.

## <a name="onenote"></a>OneNote

OneNote ist eine digitale Notizbuchanwendung. Das OneNote, das mit einer Gruppe erstellt wurde, ist eine Datei am zugeordneten SharePoint und nicht ein mit einer Gruppe verbundener Dienst.

**Wichtige Features für Gruppen**

- Freigegebenes Notizbuch (gespeichert in der SharePoint Gruppe)

**Können OneNote eine Gruppe erstellen?**

Nein, die OneNote kann keine Gruppe erstellen.

**Sind OneNote ohne Gruppe vorhanden?**

Ja, Notizbücher können direkt in OneDrive oder an anderen freigegebenen Speicherorten erstellt werden.

**Gibt es mehrere OneNote pro Gruppe?**

Ja, ein Notizbuch wird standardmäßig erstellt, und andere können hinzugefügt werden. Jeder Link zu OneNote von gruppenverknüpfungen Diensten wird jedoch immer zum Standardnotizbuch wechseln.

**Kann ein OneNote mehreren Gruppen zugeordnet werden?**

Nein, das Notizbuch wird in der SharePoint websitebibliothek gespeichert und über verschiedene Schnittstellen verknüpft. Sie kann jedoch auf die gleiche Weise für andere Gruppen freigegeben werden, wie sie für Einzelpersonen freigegeben werden kann.

**Kann sich die Zuordnung des Notizbuchs zu einer Gruppe ändern?**

Nein, das Notizbuch selbst ist der Gruppe zugeordnet und kann direkt von anderen mit gruppengebundenen Diensten aus zugegriffen werden. Der Inhalt kann jedoch innerhalb der anwendung von einem Notizbuch in ein anderes verschoben OneNote werden.

**Löscht das Löschen des Notizbuchs die Gruppe?**

Nein, wenn das notizbuch OneNote gelöscht wird, können in einigen der gruppenverknüpfungen Dienste beschädigte Links enthalten sein.

## <a name="planner"></a>Planner

Planner ist ein einfacher Gruppenaufgabeverwaltungsdienst.

**Wichtige Features für Gruppen**

- Board für die Verwaltung von Gruppenaufgaben

**Kann Planner eine Gruppe erstellen?**

Ja, beim Erstellen eines Plans wird eine neue Gruppe erstellt.

**Gibt es ein Planner-Board ohne Gruppe?**

Nein, ein Plan muss einer Gruppe zugeordnet sein.

**Gibt es mehrere Pläne pro Gruppe?**

Ja, es können mehrere Pläne pro Gruppe möglich sein.

**Kann ein Plan mehreren Gruppen zugeordnet werden?**

Nein, ein Plan basiert ausschließlich auf der Gruppenmitgliedschaft, um den Zugriff zu bestimmen.

**Kann sich die Zuordnung eines Plans zu einer Gruppe ändern?**

Nein, beim Kopieren eines Plans wird jedoch eine neue Gruppe erstellt.

> [!NOTE]
> Eine von einer anderen Anwendung erstellte Gruppe wird für einen Benutzer nicht automatisch in Planner angezeigt. Für den anfänglichen Zugriff auf das Board müssen sie es über eine andere gruppenbasierte Schnittstelle wie z. B. Outlook.

**Löscht das Löschen des Plans die Gruppe?**

Ja, beim Löschen des Plans werden die gruppen- und gruppenverkn nenten Dienste und Inhalte gelöscht.

## <a name="power-apps"></a>Power Apps

Power Apps bietet einen Canvas für die App-Entwicklung ohne Code.

**Wichtige Features für Gruppen**

- Apps können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll

**Können Power Apps eine Gruppe erstellen?**

Nein, Power Apps kann keine Microsoft 365 erstellen.

**Sind Power Apps ohne Gruppe vorhanden?**

Ja, apps can be created within Power Apps and reside within the creators account until shared or published.

**Gibt es mehrere Apps pro Gruppe?**

Ja, es können mehrere Apps für eine Gruppe freigegeben werden.

**Können Apps mehreren Gruppen zugeordnet werden?**

Ja, eine App kann für mehrere Gruppen freigegeben werden.

**Kann sich die Zuordnung einer App zu einer Gruppe ändern?**

Ja, da die Zuordnung zwischen Power Apps und einer Microsoft 365 nur gemeinsam verwendet wird – die App befindet sich weiterhin beim Ersteller.

> [!IMPORTANT]
> [Gruppen müssen für die Sicherheit aktiviert sein, bevor Apps für sie freigegeben werden können.](/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups)

**Löscht das Löschen der App die Gruppe?**

Nein, die Apps sind nicht mit der Gruppe verbunden, es sei denn, sie werden für sie freigegeben.

## <a name="power-automate"></a>Power Automate

Power Automate (früher als Microsoft Flow bezeichnet) bietet Workflows und Automatisierungsdienste.

**Wichtige Features für Gruppen**

- Workflows können für eine Gruppe freigegeben werden, die ausgeführt und geändert werden soll.

**Können Power Automate eine Gruppe erstellen?**

Nein, Power Automate kann keine Microsoft 365 gruppe im Kontext einer zugeordneten Gruppe erstellen.

Es ist jedoch möglich, einen Fluss zu erstellen, der verschiedene Vorgänge ausführt, z. B. das Erstellen einer Azure AD-Sicherheitsgruppe oder das Aktualisieren der Mitgliedschaft Microsoft 365 Gruppe.

**Gibt es Flüsse ohne Gruppe?**

Ja, Flüsse können innerhalb von Power Automate erstellt werden und sich innerhalb des Erstellerkontos befinden, bis sie freigegeben oder veröffentlicht werden.

**Kann es mehrere Flüsse pro Gruppe geben?**

Ja, es können mehrere Flüsse für eine Gruppe freigegeben werden.

**Kann ein Fluss mehreren Gruppen zugeordnet werden?**

Ja, ein Fluss kann für mehrere Gruppen freigegeben werden.

**Kann sich die Zuordnung eines Fluss zu einer Gruppe ändern?**

Ja, da die Zuordnung zwischen Power Automate und einer Microsoft 365 nur freigaben ist – der Fluss befindet sich weiterhin beim Ersteller.

**Löscht das Löschen eines Datenflusses die Gruppe?**

Nein, wie Power Apps, sind die Flüsse nicht mit der Gruppe verbunden, es sei denn, sie werden für sie freigegeben.

## <a name="power-bi-classic"></a>Power BI (klassisch)

Power BI bietet interaktive datengesteuerte Dashboards und Berichte.

**Wichtige Features für Gruppen**

- Datenberichte

**Können Power BI eine Gruppe erstellen?**

Ja, beim Erstellen eines klassischen Arbeitsbereichs wird eine Microsoft 365 erstellt.

**Gibt Power BI klassischen Arbeitsbereich ohne Gruppe?**

Nein, [ein klassischer Arbeitsbereich in Power BI muss einer Gruppe zugeordnet sein.](/power-bi/collaborate-share/service-collaborate-power-bi-workspace)

**Kann es mehrere Power BI Arbeitsbereiche pro Gruppe geben?**

Nein, die Beziehung zwischen einem klassischen Arbeitsbereich und einer Gruppe ist 1:1.

**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**

Technisch nein, während der klassische Arbeitsbereich mit der Gruppe erstellt wird, können die Inhalte außerhalb der Gruppe für Benutzer und Sicherheitsgruppen freigegeben werden.

**Kann sich die Zuordnung des Arbeitsbereichs zu einer Gruppe ändern?**

Nein, der klassische Arbeitsbereich selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch innerhalb der Power BI oder durch lokales Exportieren von Inhalten von einem Arbeitsbereich in einen anderen verschoben werden.

**Löscht das Löschen des Arbeitsbereichs die Gruppe?**

Ja, durch das Löschen des Arbeitsbereichs in Power BI werden Gruppen- und Gruppen zugeordnete Dienste und Inhalte gelöscht.

## <a name="power-bi-new"></a>Power BI (neu)

Power BI bietet interaktive datengesteuerte Dashboards und Berichte.

Während das Erstellen eines neuen Arbeitsbereichs in Power BI keine Microsoft 365-Gruppe erstellt, erstellt das Erstellen einer Gruppe auf andere Weise einen neuen (nicht klassischen) Arbeitsbereich in Power BI.

**Wichtige Features für Gruppen**

- Datenberichte

**Können Power BI eine Gruppe erstellen?**

Nein, es ist nicht möglich, eine Microsoft 365 über die neue Power BI erstellen.

**Ist der neue Power BI ohne Gruppe vorhanden?**

Ja, es ist möglich, Berichte und Arbeitsbereiche in Power BI erstellen zu lassen, die nicht mit Microsoft 365 verknüpft sind.

**Kann es mehrere Arbeitsbereiche pro Gruppe geben?**

Ja, [mehrere arbeitsbereiche, die von Power BI erstellt werden, können für eine einzelne Gruppe freigegeben werden.](/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace)

**Kann ein Arbeitsbereich mehreren Gruppen zugeordnet werden?**

Nein, ein arbeitsbereich, der von Power BI erstellt wurde, kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Arbeitsbereichs zu einer Gruppe ändern?**

Ja und Nein. Ein arbeitsbereich, der von Power BI erstellt wurde, kann nur einer einzelnen Gruppe gleichzeitig zugeordnet werden, kann die Zuordnung jedoch jederzeit ändern. Ein arbeitsbereich, der in Power BI einer Gruppe erstellt wurde, ist dieser Gruppe dauerhaft zugeordnet.

**Löscht das Löschen des Arbeitsbereichs die Gruppe?**

Ja, durch das Löschen des Arbeitsbereichs in Power BI werden die gruppen- und gruppen zugeordneten Dienste und Inhalte gelöscht.

## <a name="project-for-the-web"></a>Project für das Web

Project für das Web bietet die Möglichkeit, Projektpläne, Gantt-Diagramme und Roadmaps zu erstellen.
Wichtige Features, die Gruppen zur Verfügung gestellt werden.

- Project-Pläne

**Kann Project für das Web eine Gruppe erstellen?**

Ja, es ist möglich, eine neue Microsoft 365 gruppe direkt aus Project web zu erstellen.

**Sind Projekte ohne Gruppe vorhanden?**

Ja, Projekte können vorhanden sein, ohne einer Microsoft 365 zugeordnet zu werden, die Zuweisung von Aufgaben erfordert jedoch eine Gruppenzuordnung.

**Gibt es mehrere Projekte pro Gruppe?**

Ja, es ist möglich, mehrere Projekte in einer einzelnen Gruppe zu verbinden.

**Kann Projekt mehreren Gruppen zugeordnet werden?**

Nein, ein Projekt kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung eines Projekts zu einer Gruppe ändern?**

Nein, sobald die Zuordnung zu einer Gruppe eingerichtet wurde, kann sie sich nicht mehr ändern.

**Löscht das Löschen des Projekts die Gruppe?**

Nein, das Löschen des Projekts in Project für das Web löscht die Gruppe nicht.

## <a name="roadmap"></a>Roadmap

Roadmap bietet die Möglichkeit, Projektpläne mit Project web und Project Online.

**Wichtige Features für Gruppen**

- Project Roadmaps

**Kann roadmap eine Gruppe erstellen?**

Ja, es ist möglich, eine neue Microsoft 365 direkt aus der Roadmap zu erstellen.

**Gibt es Roadmap ohne Gruppe?**

Ja, Roadmaps können vorhanden sein, ohne einer Microsoft 365 zugeordnet zu werden. Die Freigabe der Roadmap erfordert jedoch eine Gruppen zuordnung.

**Gibt es mehrere Roadmaps pro Gruppe?**

Ja, es ist möglich, mehrere Roadmaps mit einer einzelnen Gruppe zu verbinden.

**Kann eine Roadmap mehreren Gruppen zugeordnet werden?**

Nein, eine Roadmap kann nur einer einzelnen Gruppe zugeordnet werden.

**Kann sich die Zuordnung einer Roadmap zu einer Gruppe ändern?**

Nein, sobald die Zuordnung zu einer Gruppe eingerichtet wurde, kann sie sich nicht mehr ändern.

**Löscht das Löschen der Roadmap die Gruppe?**

Nein, beim Löschen der Roadmap wird die Gruppe nicht gelöscht.

## <a name="sharepoint"></a>SharePoint

SharePoint ist eine webbasierte Inhaltsverwaltungsplattform, die unter anderem Speicherdienste für eine Reihe von Microsoft 365 bietet.

**Wichtige Features für Gruppen**

- Dokumentbibliothek
- Bibliothek zum Speichern OneNote Notizbuchs
- Storage von Teams-Wiki-Dateien

**Können SharePoint eine Gruppe erstellen?**

Ja, das Erstellen einer Teamwebsite in SharePoint erstellt standardmäßig Microsoft 365 Gruppe. Es ist auch möglich, eine Gruppe und optional ein Team für eine vorhandene Website zu erstellen.

**Sind SharePoint Websites ohne Gruppe vorhanden?**

Ja, SharePoint bietet eine Reihe von Nicht-Gruppen zugeordneten Diensten und Websites, z. B. Kommunikations- und Hubwebsites. 

**Kann es mehrere Websites pro Gruppe geben?**

Nein, es kann nur eine einzelne Website pro Gruppe vorhanden sein. Private Kanäle in Teams zusätzliche Websites verwenden, die nicht mit der Gruppe verbunden sind.

**Können Websites mehreren Gruppen zugeordnet werden?**

Technisch nein, aber während eine Website mit einer Gruppe erstellt wird, kann der Inhalt für andere Gruppen freigegeben werden.

**Kann sich die Zuordnung einer Website zu einer Gruppe ändern?**

Nein, die Website selbst ist der Gruppe zugeordnet, der Inhalt kann jedoch innerhalb der SharePoint-Schnittstelle von einer Website zu einer anderen verschoben werden, indem Inhalte lokal oder mithilfe eines Drittanbietertools exportiert werden.

**Löscht das Löschen der Website die Gruppe?**

Ja, durch das Löschen der Website in SharePoint werden Gruppen- und Gruppen zugeordnete Dienste und Inhalte gelöscht.

## <a name="stream"></a>Stream

Microsoft Stream ist eine Videohosting- und Freigabeplattform.

**Wichtige Features für Gruppen**

- Videospeicherung
- Teams Besprechungsaufzeichnung
- Videokanäle

**Kann Stream eine Gruppe erstellen?**

Ja, es ist möglich, eine neue Microsoft 365 gruppe direkt aus Stream zu erstellen.

**Gibt es Stream ohne Gruppe?**

Ja, Videokanäle und Videos können in Stream vorhanden sein, ohne einer Gruppe zugeordnet zu werden.

**Gibt es mehrere Videos und Kanäle pro Gruppe?**

Ja, es können mehrere Videos und Kanäle in jeder Gruppe sein.

**Kann ein Video oder kanal mehreren Gruppen zugeordnet werden?**

Ja, während ein Video oder Kanal mit einer Gruppe erstellt wird, kann es für andere Gruppen freigegeben werden.

**Kann sich die Zuordnung zu einer Gruppe ändern?**

Ja und Nein; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can be associated with the group they were originally created in.

**Löscht das Löschen von Videos oder Kanälen die Gruppe?**

Nein, das Löschen von Videos oder Kanälen löscht die Gruppe nicht. Durch das Löschen der Gruppe selbst in Stream werden jedoch gruppen zugeordnete Dienste und Inhalte gelöscht, mit Ausnahme der tatsächlichen Videos.

## <a name="yammer"></a>Yammer

Yammer ist eine soziale Plattform für Unternehmen, die das Engagement der Community innerhalb und zwischen Organisationen fördert.

Beim Erstellen einer Community (früher als "Gruppe" bezeichnet) in Yammer wird ein Postfach erstellt, das derzeit jedoch nicht verwendet wird.

Eine Microsoft 365, die einem Yammer zugeordnet ist, kann nicht mit einem Team in der Microsoft Teams.

**Wichtige Features für Gruppen**

- Unterhaltungsbereich

**Kann Yammer eine Microsoft 365 erstellen?**

Ja, das Erstellen einer neuen Gruppe in Yammer erstellt eine neue Microsoft 365-Gruppe, wenn die Plattformen verbunden sind und der Benutzer die Möglichkeit hat, eine Gruppe zu erstellen.

Eine Yammer gruppe mit zugeordneter Microsoft 365 kann nicht in einer anderen Schnittstelle oder einem Dienst als in Yammer erstellt werden.

**Gibt es Yammer Gruppe ohne Microsoft 365 Gruppe?**

Ja, es ist möglich, eine Yammer gruppe ohne Microsoft 365 erstellen.

Wenn die Yammer-Plattform nicht mit Microsoft 365-Gruppen verbunden ist oder Benutzer keine Möglichkeit haben, eine Microsoft 365-Gruppe zu erstellen, werden Yammer-Gruppen ohne eine Microsoft 365 erstellt.

**Kann es mehrere Gruppen Yammer gruppen Microsoft 365 geben?**

Nein, die Beziehung zwischen einer Yammer und einer Microsoft 365 ist 1:1.

**Kann eine Yammer mehreren Gruppen zugeordnet Microsoft 365 werden?**

Nein, die Yammer gruppe kann nur einer einzelnen Gruppe zugeordnet Microsoft 365 werden. Es ist möglich, Dass Beiträge für andere Benutzergruppen freigegeben oder Yammer werden.

**Kann sich Yammer Zuordnung einer Gruppe zu einer Microsoft 365 ändern?**

Nein, die Yammer kann immer nur der Gruppe zugeordnet Microsoft 365, der sie ursprünglich zugeordnet war.

**Löscht das Löschen Yammer Gruppe die Microsoft 365 Gruppe?**

Ja, durch das Löschen der Gruppe in Yammer werden verwandte Microsoft-Gruppen- und gruppenbezogene Dienste und Inhalte gelöscht.

## <a name="related-topics"></a>Verwandte Themen

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)