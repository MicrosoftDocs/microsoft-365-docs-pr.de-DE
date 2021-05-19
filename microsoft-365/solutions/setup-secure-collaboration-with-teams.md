---
title: Sichere Zusammenarbeit mit Microsoft 365 einrichten
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
recommendations: false
description: Erfahren Sie, wie Sie eine sichere Inhaltszusammenarbeit in Teams, um Ihre Daten basierend auf ihrer Vertraulichkeit zu schützen.
ms.openlocfilehash: 12c8bfd2c7c59e1cc4dcf149e394d2c7dc456530
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539059"
---
# <a name="set-up-secure-collaboration-with-microsoft-365-and-microsoft-teams"></a>Einrichten einer sicheren Zusammenarbeit mit Microsoft 365 und Microsoft Teams

Die Möglichkeit zum einfachen Teilen von Informationen mit den richtigen Personen und gleichzeitiger Verhinderung von Überschattung ist der Schlüssel zum Erfolg einer Organisation. Dies umfasst die Möglichkeit, vertrauliche Daten sicher nur für diejenigen zu teilen, die Zugriff darauf haben sollten. Je nach Projekt kann dies die Freigabe vertraulicher Daten für Personen außerhalb Ihrer Organisation umfassen.

Diese Lösungsanleitung für die Zusammenarbeit umfasst zwei Komponenten, die Ihnen helfen:
- Bereitstellen Microsoft Teams mit der richtigen Schutzebene für jedes Projekt
- Konfigurieren der externen Freigabe mit den entsprechenden Sicherheitseinstellungen für jedes Projekt

![Bereitstellen Teams mit entsprechendem Schutz und Konfigurieren der externen Freigabe mit entsprechenden Sicherheitseinstellungen](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Wenn keine vielseitigen und einfach zu verwendenden Tools für die Inhaltszusammenarbeit verfügbar sind, arbeiten Benutzer häufig per E-Mail zusammen. Dies ist eine mühsame und fehleranfällige Methode der Zusammenarbeit und kann das Risiko einer unangemessenen Freigabe von Informationen erhöhen. Wenn die Freigabe von Informationen zu schwierig ist, könnten sie wieder Verbraucherprodukte verwenden, die nicht von der IT geregelt werden. Dies kann ein noch höheres Risiko darstellen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Mit Microsoft 365 können Sie Teams mit einer Vielzahl von Konfigurationen bereitstellen, die Ihnen helfen:

- Schützen Ihres geistigen Eigentums
- Einfache Zusammenarbeit ermöglichen
- Erstellen eines Gleichgewichts zwischen Sicherheit und Benutzerfreundlichkeit, das die Benutzerzufriedenheit erhöht und das Risiko von Schatten-IT reduziert

Die meisten Organisationen verfügen über eine Vielzahl von Informationen mit unterschiedlichen Vertraulichkeitsgraden und unterschiedlichen Auswirkungen auf das Unternehmen, wenn die Informationen unangemessen weitergegeben werden. Abhängig von der Vertraulichkeit eines bestimmten Informationsteils sollten Sie die Freigabe für:

- Jeder (nicht authentifiziert)
- Personen innerhalb der Organisation
- Bestimmte Personen innerhalb der Organisation
- Bestimmte Personen innerhalb und außerhalb der Organisation

Informationen wie Marketingbroschüren sind für die gemeinsame Nutzung außerhalb der Organisation gedacht. Informationen wie z. B. Mensamenüs sind nicht für die externe Freigabe gedacht, hätten aber keine geschäftlichen Auswirkungen, wenn sie extern freigegeben würden. Diese Arten von Informationen benötigen wenig oder keinen Schutz.

Dieselben Marketingbroschüren werden während der Entwicklung möglicherweise nur innerhalb der Organisation freigegeben. In diesem Fall sind die Standardfreigabeeinstellungen in Teams ausreichend.

Informationen zu einem neuen Produkt, das sich in der Entwicklung befindet, können auch innerhalb der Organisation als vertraulich betrachtet werden. In diesem Fall kann ein höherer Schutz angemessen sein. Sie könnten den Zugriff auf diese Informationen beispielsweise auf Mitglieder eines bestimmten Teams beschränken. Je nach Projekt müssen Sie möglicherweise mit Personen außerhalb Ihrer Organisation zusammenarbeiten, z. B. mit einem Anbieter oder einer Partnerorganisation.

Informationen, die für den Erfolg Ihrer Organisation entscheidend sind oder strenge Sicherheits- oder Complianceanforderungen haben, erfordern möglicherweise noch mehr Schutz.

![Risikoskala von niedrig (veröffentlichter Prospekt) bis hoch (vertrauliche Geschäftsdaten)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Für alle oben genannten Szenarien können Sie Teams in Microsoft Teams zum Speichern, Freigeben und Zusammenarbeiten an den Informationen verwenden. 

Zum Konfigurieren der sicheren Zusammenarbeit verwenden Sie diese Microsoft 365 und Features.

| Produkt oder Komponente | Funktion oder Feature | Lizenzierung |
|:-------|:-----|:-------|
| Microsoft Defender für Office 365 | Sichere Anlagen für SPO, OneDrive und Teams; Sichere Dokumente; Sichere Links für Teams    | Microsoft 365 E1, E3 und E5 |
| SharePoint    | Website- und Dateifreigaberichtlinien, Websitefreigabeberechtigungen, Freigabelinks, Zugriffsanforderungen, Einstellungen für die Websitegastfreigabe | Microsoft 365 E1, E3 und E5 |
| Microsoft Teams   | Gastzugriff, private Teams, private Kanäle | Microsoft 365 E1, E3 und E5 |
| Microsoft 365 Compliance  | Vertraulichkeitsbezeichnungen    | Microsoft 365 E3 und E5 |

### <a name="collaboration-governance"></a>Zusammenarbeitsgovernance

Microsoft 365 bietet viele Optionen für die Verwaltung Ihrer Lösung für die Zusammenarbeit. Es wird empfohlen, diese Bereitstellungsinhalte zusammen mit den Inhalten der Governance für die Zusammenarbeit zu [verwenden,](collaboration-governance-overview.md) um die beste Lösung für die Zusammenarbeit für Ihre Organisation zu erstellen.

### <a name="using-teams-for-all-kinds-of-data"></a>Verwenden Teams für alle Arten von Daten

Um den Zugriff auf Informationen mit unterschiedlichen Empfindlichkeiten zu verwalten, haben wir drei verschiedene Schutzebenen für [Teams.](configure-teams-three-tiers-protection.md) Sie können jede dieser Ebenen anpassen, um die Anforderungen oder Ihr Unternehmen besser zu erfüllen. 

![Abbildung von drei Schutzebenen für Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Diese Ebenen –  *Basisebene,* vertraulich und hochgradig sensibel *–* erhöhen schrittweise den Schutz, der dazu beit hilft, Überlagerungen und potenzielle Informationslecks zu verhindern, wie in der folgenden Tabelle dargestellt.

|-|**Basisebene**|**Vertrauliche Ebene**|**Hochsensible Ebene**|
|:--|:-----------|:------------|:-------------------|
|Öffentliches oder privates Team|Either|Private|Private|
|Nicht authentifizierte Freigabe|Gesperrt|Gesperrt|Gesperrt|
|Dateifreigabe|Zulässig|Zulässig|Nur Teambesitzer können freigaben.|
|Teammitgliedschaft|Jeder kann an öffentlichen Teams teilnehmen.<br>Die Genehmigung des Teambesitzers ist erforderlich, um privaten Teams bei treten zu können.|Genehmigung des Teambesitzers erforderlich, um beitreten zu können.|Genehmigung des Teambesitzers erforderlich, um beitreten zu können.|
|Dokumentverschlüsselung|||Verfügbar mit Vertraulichkeitsbezeichnung|
|Gastfreigabe|Zulässig|Kann zugelassen oder blockiert werden|Kann zugelassen oder blockiert werden|
|Nicht verwaltete Geräte|Keine Einschränkung|Nur-Web-Zugriff|Gesperrt|

Das Konfigurieren dieser Ebenen umfasst:

- Konfigurieren von Einstellungen in Teams für Gastzugriff und private Kanäle
- Konfigurieren von Einstellungen in der zugeordneten SharePoint eines Teams für interne und Gastfreigabe, Zugriffsanforderungen und Freigabelinks
- Konfigurieren von  *Vertraulichkeitsbezeichnungen* zum Klassifizieren der Teams und Steuern der Gastfreigabe und des Zugriffs von nicht verwalteten Geräten
- Konfigurieren einer *Vertraulichkeitsbezeichnung* für die hochsensible Ebene zum Verschlüsseln der Dokumente, auf die sie angewendet wird

Beginnen Sie mit der Basisebene, und  fügen  Sie dann Teams hinzu, die die vertraulichen und hochgradig vertraulichen Ebenen nach Bedarf verwenden, um die Informationen in Ihrer Organisation zu schützen. Sehen Sie sich die folgenden Ressourcen an, um zu beginnen:

- [Konfigurieren von Teams mit grundlegendem Schutz](configure-teams-baseline-protection.md)
- [Teams für den Schutz vertraulicher Daten konfigurieren](configure-teams-sensitive-protection.md)
- [Teams für den Schutz hochgradig vertraulicher Daten konfigurieren](configure-teams-highly-sensitive-protection.md)

Wenn Sie über ein hochsensibles Projekt verfügen, das zusätzlichen Schutz vor der Freigabe auch innerhalb Ihrer Organisation erfordert, können Sie ein Team konfigurieren, das eine eigene Vertraulichkeitsbezeichnung verwendet, um Dateien zu verschlüsseln, sodass sie nur von Teammitgliedern gelesen werden können. Weitere [Informationen finden Sie unter Konfigurieren eines Teams mit Sicherheitsisolation.](secure-teams-security-isolation.md)

### <a name="sharing-with-people-outside-your-organization"></a>Freigeben für Personen außerhalb Ihrer Organisation

Möglicherweise müssen Sie Informationen beliebiger Vertraulichkeit mit [Personen außerhalb Ihrer Organisation teilen.](collaborate-with-people-outside-your-organization.md) Dies kann von der Freigabe eines einzelnen Dokuments mit einer einzelnen Person bis zur Zusammenarbeit an einem Großprojekt mit einer großen Partnerorganisation oder Freiberuflern aus der ganzen Welt reichen. In Microsoft 365 kann dieser Bereich der externen Freigabe einfach und mit den entsprechenden Sicherheitsvorkehrungen durchgeführt werden, um Ihre vertraulichen Informationen zu schützen.

Diese Ressourcen helfen Ihnen beim Einrichten Ihrer Umgebung für die Zusammenarbeit mit Personen außerhalb Ihrer Organisation:

- [Arbeiten Sie an Dokumenten für](collaborate-on-documents.md) die Freigabe einzelner Dateien von Ordnern zusammen.
- [Arbeiten Sie auf einer Website](collaborate-in-site.md) zusammen, um mit Gästen in einer SharePoint zusammenarbeiten.
- [Zusammenarbeit als Team für](collaborate-as-team.md) die Zusammenarbeit mit Gästen in einem Team.

Je nach Vertraulichkeit der freigegebenen Informationen können Sie Sicherheitsvorkehrungen hinzufügen, um überschattet zu werden. Diese Ressourcen helfen Ihnen beim Einrichten der Schutzmaßnahmen, die Sie für Ihre Organisation benötigen:

- [Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)
- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](share-limit-accidental-exposure.md)
- [Erstellen einer sicheren Gastfreigabeumgebung](create-secure-guest-sharing-environment.md)

Wenn Sie über ein Hauptprojekt mit einer Partnerorganisation verfügen, können Sie Azure Entitlement Management verwenden, um die Gäste aus dieser Organisation in einem Team zu verwalten, das Sie für das Projekt eingerichtet haben. Siehe [Erstellen eines B2B-Extranets mit verwalteten Gästen](b2b-extranet.md) für weitere Details.



## <a name="training-for-administrators"></a>Schulung für Administratoren

Diese Schulungsmodule von Microsoft Learn helfen Ihnen, die Features für Zusammenarbeit, Governance und Identität in Teams und SharePoint.

#### <a name="teams"></a>Teams

|Schulung:|Verwalten der Zusammenarbeit im Team mit Microsoft Teams|
|:---|:---|
|![Teams -Symbol für die Zusammenarbeit](../media/manage-team-collaboration-with-microsoft-teams.svg)|Verwalten der Zusammenarbeit im Team mit Microsoft Teams bietet eine Einführung in die Features und Funktionen von Microsoft Teams, dem zentralen Hub für die Zusammenarbeit im Team in Microsoft 365. Hier erfahren Sie, wie Sie mithilfe von Teams Teamarbeit und Kommunikation innerhalb Ihrer Organisation – sowohl lokal als auch mobil – auf einer breiten Palette von Geräten – von Desktops bis Tablets und Smartphones – vereinfachen und gleichzeitig die vielfältigen Funktionen von Office 365-Anwendungen nutzen können. Sie lernen, wie Teams eine umfassende und flexible Umgebung für die Zusammenarbeit über Anwendungen und Geräte hinweg bereitstellt. Dieser Lernpfad kann Ihnen bei der Vorbereitung für die Microsoft 365-Zertifizierung: Teams Administrator Associate helfen.<br><br>2 Std. 17 Min. - Lernpfad - 5 Module|

> [!div class="nextstepaction"]
> [Starten >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Schulung:|Zusammenarbeit mithilfe von SharePoint in Microsoft 365|
|:---|:---|
|![SharePoint Schulungssymbol](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Verwalten freigegebener Inhalte mit Microsoft SharePoint bietet eine Einführung in die Features und Funktionen von SharePoint und dessen Funktionsweise mit Microsoft 365. Hier erfahren Sie mehr über die verschiedenen Typen von SharePoint-Websites, einschließlich Hubwebsites, sowie über den Schutz von Informationen, die Berichterstellung und die Überwachung. Sie erfahren außerdem, wie Sie die SharePoint-Datei- und Ordnerfreigabe verwenden, um die Zusammenarbeit zu optimieren, wie Sie Dateien extern freigeben und wie Sie SharePoint-Websites im SharePoint Admin-Center verwalten. Dieser Lernpfad kann Ihnen bei der Vorbereitung für die Microsoft 365 Certified: Teamwork Administrator Associate-Zertifizierung helfen.<br><br>1 Std. 14 Min. - Lernpfad - 4 Module|

> [!div class="nextstepaction"]
> [Starten >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>Information Protection

|Schulung:|Schützen von Unternehmensinformationen mit Microsoft 365|
|:---|:---|
|![Teams info protection training icon](../media/protect-enterprise-information-microsoft-365.svg)|Es ist schwieriger als je zuvor, die Informationen Ihrer Organisation zu schützen und zu sichern. Im Lernpfad Schützen von Unternehmensinformationen mit Microsoft 365 wird erläutert, wie Sie Ihre vertraulichen Informationen vor versehentlichem Teilen oder Missbrauch schützen, wie Sie Daten erkennen und klassifizieren, wie Sie sie mit Vertraulichkeitsbezeichnungen schützen können und wie Sie vertrauliche Informationen überwachen und analysieren können, um sich gegen den Verlust dieser Daten zu schützen. Dieser Lernpfad hilft Ihnen bei der Vorbereitung auf Microsoft 365 Certified: Security Administrator Associate and Microsoft 365 Certified: Enterprise Administration Expert certifications..<br><br>1 Std. – Lernpfad – 5 Module|

> [!div class="nextstepaction"]
> [Starten >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identität und Zugriff

|Schulung:|Identität schützen und Zugriff mit Azure Active Directory|
|:---|:---|
|![Identitäts- und Zugriffsschulungssymbol](../media/protect-identity-and-access-with-microsoft-365.svg)|Der Lernpfad Identität und Zugriff umfasst die neuesten Identitäts- und Zugriffstechnologien, Tools zur Stärkung der Authentifizierung und Anleitungen zum Identitätsschutz in Ihrer Organisation. Die Zugriffs- und Identitätstechnologien von Microsoft ermöglichen es Ihnen, die Identität Ihrer Organisation zu schützen, ob vor Ort oder in der Cloud, und ermöglichen es Ihren Benutzern, von jedem Standort aus sicher zu arbeiten. Dieser Lernpfad kann Ihnen bei der Vorbereitung für die Microsoft 365-Zertifizierung: Security Administrator Associate und Microsoft 365 Zertifizierung: Enterprise Administration Expert helfen.<br><br>2 Std. 52 Min. - Lernpfad - 6 Module|

> [!div class="nextstepaction"]
> [Starten >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Schulungen für Endbenutzer

Diese Schulungsmodule können Ihren Benutzern helfen, Teams, Gruppen und SharePoint für die Zusammenarbeit in Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Einrichten und Anpassen des Teamschulungssymbols](../media/set-up-customize-team-training.png)<br>**[Einrichten und Anpassen Ihres Teams](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint Teilen und Synchronisieren des Schulungssymbols](../media/sharepoint-share-sync-training.png)<br>**[Freigeben und Synchronisieren](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teams zum Hochladen und Suchen von Dateien (Schulungssymbol)](../media/smc-teams-upload-find-files-training.png)<br>**[Hochladen und Suchen von Dateien](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Zusammenarbeit in Teams und Kanälen (Symbol)](../media/teams-collaborate-channels-training.png)<br>**[Zusammenarbeit in Teams und Kanälen](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**|||

## <a name="illustrations"></a>Illustrationen

Diese Abbildungen helfen Ihnen zu verstehen, wie Gruppen und Teams mit anderen Diensten in Microsoft 365 interagieren und welche Governance- und Compliancefeatures zur Verfügung stehen, um diese Dienste in Ihrer Organisation zu verwalten.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Gruppen in Microsoft 365 für IT-Architekten
Was IT-Architekten über Gruppen in Microsoft 365 wissen müssen

|**Item**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturbild für Gruppen-Infografik](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Aktualisiert: Juni 2019|Diese Illustrationen erläutern die unterschiedlichen Arten von Gruppen, erklären, wie diese erstellt und verwaltet werden, und bieten einige Vorschläge für Governance.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams und verwandte Produktivitätsdienste in Microsoft 365 für IT-Architekten
Die logische Architektur von Produktivitätsdiensten in Microsoft 365, beginnend mit Microsoft Teams.

|**Item**|**Beschreibung**|
|:-----|:-----|
|[![Miniaturbild für Poster der logischen Architektur von Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Aktualisiert: April 2019   |Microsoft bietet eine Reihe von Produktivitätsdiensten für die Zusammenarbeit in den Bereichen Datengovernance, Sicherheit und Compliancefunktionen. <br/> <br/>Diese Illustrationen geben einen Einblick in die logische Architektur der Produktivitätsdienste für Enterprise Architekten, beginnend mit Microsoft Teams.|

## <a name="deploy-the-secure-collaboration-solution"></a>Bereitstellen der Lösung für die sichere Zusammenarbeit

Wenn Sie zur Bereitstellung dieser Lösung bereit sind, fahren Sie mit den folgenden Schritten fort:
1. Konfigurieren Sie [die drei verschiedenen Schutzebenen für Teams.](configure-teams-three-tiers-protection.md)
2. Konfigurieren Sie Einstellungen für [die Freigabe von Informationen beliebiger Vertraulichkeit für Personen außerhalb Ihrer Organisation.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Sicherheitsdokumentation](../security/index.yml)

[Microsoft 365-Compliance-Dokumentation](../compliance/index.yml)

[Willkommen bei Microsoft Teams](/MicrosoftTeams/Teams-overview)
