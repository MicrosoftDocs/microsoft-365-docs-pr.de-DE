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
description: Erfahren Sie, wie Sie eine sichere Zusammenarbeit an Inhalten in Teams einrichten, um Ihre Daten basierend auf ihrer Vertraulichkeit zu schützen.
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233856"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Sichere Zusammenarbeit mit Microsoft 365 einrichten

Die Möglichkeit, Informationen problemlos mit den richtigen Personen zu teilen und gleichzeitig eine Überschattung zu verhindern, ist der Schlüssel zum Erfolg einer Organisation. Dies umfasst die Möglichkeit, vertrauliche Daten sicher nur mit Personen zu teilen, die Zugriff darauf haben sollen. Je nach Projekt kann dies die Freigabe vertraulicher Daten für Personen außerhalb Ihrer Organisation umfassen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Diese Lösungsanleitung für die Zusammenarbeit umfasst zwei Komponenten, die Ihnen helfen:
- Bereitstellen von Microsoft Teams mit dem richtigen Schutzniveau für jedes Projekt
- Konfigurieren der externen Freigabe mit geeigneten Sicherheitseinstellungen für jedes Projekt

![Bereitstellen von Teams mit entsprechendem Schutz und Konfigurieren der externen Freigabe mit entsprechenden Sicherheitseinstellungen](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Wenn vielseitige und einfach zu verwendende Tools für die Zusammenarbeit an Inhalten nicht verfügbar sind, arbeiten Benutzer häufig per E-Mail zusammen. Dies ist eine mühsame und fehleranfällige Methode der Zusammenarbeit und kann das Risiko einer unangemessenen Freigabe von Informationen erhöhen. Wenn die Freigabe von Informationen zu schwierig ist, könnten sie wieder Verbraucherprodukte verwenden, die nicht von der IT kontrolliert werden. Dies kann ein noch höheres Risiko darstellen.

Mit Microsoft 365 können Sie Teams mit einer Vielzahl von Konfigurationen bereitstellen, die Ihnen helfen:

- Schützen Ihres geistigen Eigentums
- Einfache Zusammenarbeit ermöglichen
- Erstellen eines Gleichgewichts zwischen Sicherheit und Benutzerfreundlichkeit, das die Zufriedenheit der Benutzer erhöht und das Risiko von Schatten-IT reduziert

Die meisten Organisationen verfügen über eine Vielzahl von Informationen mit unterschiedlichem Grad an Vertraulichkeit und unterschiedlichen Auswirkungen auf das Unternehmen, wenn die Informationen unangemessen freigegeben werden. Abhängig von der Vertraulichkeit eines bestimmten Informationsteils möchten Sie möglicherweise die Freigabe für:

- Jeder (nicht authentifiziert)
- Personen innerhalb der Organisation
- Bestimmte Personen innerhalb der Organisation
- Bestimmte Personen innerhalb und außerhalb der Organisation

Informationen wie Marketingkampagnen sind für die Freigabe außerhalb der Organisation gedacht. Informationen wie "Menus" sind nicht für die externe Freigabe gedacht, haben aber keine geschäftlichen Auswirkungen, wenn sie extern freigegeben werden. Diese Informationstypen benötigen wenig oder keinen Schutz.

Die gleichen Marketingkampagnen werden während der Entwicklung möglicherweise nur innerhalb der Organisation geteilt. In diesem Fall sind die Standardfreigabeeinstellungen in Teams möglicherweise ausreichend.

Informationen zu einem neuen Produkt, das sich in der Entwicklung befindet, können auch innerhalb der Organisation als vertraulich betrachtet werden. In diesem Fall kann ein höherer Schutz angemessen sein. Sie können den Zugriff auf diese Informationen beispielsweise auf Mitglieder eines bestimmten Teams beschränken. Je nach Projekt müssen Sie möglicherweise mit Personen außerhalb Ihrer Organisation zusammenarbeiten, z. B. mit einem Anbieter oder einer Partnerorganisation.

Informationen, die für den Erfolg Ihrer Organisation entscheidend sind oder strenge Sicherheits- oder Complianceanforderungen haben, erfordern möglicherweise noch mehr Schutz.

![Risikoskala von niedrig (veröffentlicht) bis hoch (vertrauliche Geschäftsdaten)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Für alle oben genannten Szenarien können Sie Teams in Microsoft Teams verwenden, um die Informationen zu speichern, zu teilen und zusammenzuarbeiten. 

Um eine sichere Zusammenarbeit zu konfigurieren, verwenden Sie diese Microsoft 365-Funktionen und -Features.

| Produkt oder Komponente | Funktion oder Feature | Lizenzierung |
|:-------|:-----|:-------|
| Microsoft Defender für Office 365 | Sichere Anlagen für SPO, OneDrive und Teams; Sichere Dokumente; Sichere Links für Teams    | Microsoft 365 E1, E3 und E5 |
| SharePoint    | Website- und Dateifreigaberichtlinien, Websitefreigabeberechtigungen, Freigabelinks, Zugriffsanforderungen, Einstellungen für die Website-Gastfreigabe | Microsoft 365 E1, E3 und E5 |
| Microsoft Teams   | Gastzugriff, private Teams, private Kanäle | Microsoft 365 E1, E3 und E5 |
| Microsoft 365 Compliance  | Vertraulichkeitsbezeichnungen    | Microsoft 365 E3 und E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Verwenden von Teams für alle Arten von Daten

Um den Zugriff auf Informationen mit unterschiedlichen Empfindlichkeiten zu verwalten, haben wir drei verschiedene Schutzebenen für [Teams entwickelt.](configure-teams-three-tiers-protection.md) Sie können jede dieser Ebenen anpassen, um die Anforderungen oder Ihr Unternehmen besser zu erfüllen. 

![Miniaturbild für Poster der logischen Architektur von Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Diese Ebenen *–* *Basisplan,* vertraulich und hochgradig vertraulich *–* erhöhen schrittweise die Schutzmaßnahmen, die dazu beitragen, Überlagerungen und potenzielle Informationslecks zu verhindern, wie in der folgenden Tabelle dargestellt.

|-|**Basisebene**|**Ebene "Vertraulich"**|**Stufe "Hochgradig vertraulich"**|
|:--|:-----------|:------------|:-------------------|
|Öffentliches oder privates Team|Eine der beiden|Private|Private|
|Nicht authentifizierte Freigabe|Gesperrt|Gesperrt|Gesperrt|
|Dateifreigabe|Zulässig|Zulässig|Nur Teambesitzer können freigaben.|
|Teammitgliedschaft|Jeder kann an öffentlichen Teams teilnehmen.<br>Genehmigung des Teambesitzers erforderlich, um privaten Teams bei treten zu können.|Genehmigung des Teambesitzers für den Beitritt erforderlich.|Genehmigung des Teambesitzers für den Beitritt erforderlich.|
|Dokumentverschlüsselung|||Verfügbar mit Vertraulichkeitsbezeichnung|
|Gastfreigabe|Zulässig|Kann zugelassen oder blockiert werden|Kann zugelassen oder blockiert werden|
|Nicht verwaltete Geräte|Keine Einschränkung|Nur-Web-Zugriff|Gesperrt|

Das Konfigurieren dieser Ebenen umfasst:

- Konfigurieren von Einstellungen in Teams für den Gastzugriff und private Kanäle
- Konfigurieren von Einstellungen auf der zugeordneten SharePoint-Website eines Teams für die interne freigabe und Gastfreigabe, Zugriffsanforderungen und Freigabelinks
- Konfigurieren von  *Vertraulichkeitsbezeichnungen* zur Klassifizierung der Teams und Steuern der Gastfreigabe und des Zugriffs von nicht verwalteten Geräten aus für die sensiblen und hochgradig vertraulichen Ebenen
- Konfigurieren einer *Vertraulichkeitsbezeichnung* zum Verschlüsseln der Dokumente, auf die sie angewendet wird, für die Stufe "Hochgradig vertraulich"

Beginnen Sie mit der Basisebene, und  fügen  Sie dann Teams hinzu, die die vertraulichen und hochgradig vertraulichen Ebenen nach Bedarf verwenden, um die Informationen in Ihrer Organisation zu schützen. Sehen Sie sich die folgenden Ressourcen an, um zu beginnen:

- [Konfigurieren von Teams mit grundlegendem Schutz](configure-teams-baseline-protection.md)
- [Teams für den Schutz vertraulicher Daten konfigurieren](configure-teams-sensitive-protection.md)
- [Teams für den Schutz hochgradig vertraulicher Daten konfigurieren](configure-teams-highly-sensitive-protection.md)

Wenn Sie über ein hochsensibles Projekt verfügen, das zusätzlichen Schutz vor der Freigabe auch innerhalb Ihrer Organisation erfordert, können Sie ein Team konfigurieren, das eine eigene Vertraulichkeitsbezeichnung verwendet, um Dateien zu verschlüsseln, sodass nur Teammitglieder sie lesen können. Weitere [Informationen finden Sie unter "Konfigurieren eines Teams mit Sicherheitsisolation".](secure-teams-security-isolation.md)

### <a name="sharing-with-people-outside-your-organization"></a>Freigabe für Personen außerhalb Ihrer Organisation

Möglicherweise müssen Sie Informationen zu [vertraulichkeitsempfindlichen](collaborate-with-people-outside-your-organization.md)Informationen für Personen außerhalb Ihrer Organisation freigeben. Dies kann von der Freigabe eines einzelnen Dokuments mit einer einzelnen Person bis zur Zusammenarbeit an einem Größeren Projekt mit einer großen Partnerorganisation oder Mitläufern aus der ganzen Welt reichen. In Microsoft 365 kann dieser Bereich der externen Freigabe problemlos und mit den entsprechenden Sicherheitsvorkehrungen zum Schutz Ihrer vertraulichen Informationen durchgeführt werden.

Diese Ressourcen helfen Ihnen bei den ersten Schritte beim Einrichten Ihrer Umgebung für die Zusammenarbeit mit Personen außerhalb Ihrer Organisation:

- [Arbeiten Sie an Dokumenten zusammen,](collaborate-on-documents.md) um einzelne Dateien von Ordnern gemeinsam zu verwenden.
- [Arbeiten Sie auf einer Website zusammen,](collaborate-in-site.md) um mit Gästen auf einer SharePoint-Website zusammenzuarbeiten.
- [Arbeiten Sie als Team zusammen,](collaborate-as-team.md) um mit Gästen in einem Team zusammenzuarbeiten.

Abhängig von der Vertraulichkeit der freigegebenen Informationen können Sie Sicherheitsvorkehrungen hinzufügen, um eine Überschr nkung zu verhindern. Diese Ressourcen helfen Ihnen beim Einrichten der Schutzmaßnahmen, die Sie für Ihre Organisation benötigen:

- [Bewährte Methoden zum Freigeben von Dateien und Ordnern für nicht authentifizierte Benutzer](best-practices-anonymous-sharing.md)
- [Begrenzen der versehentlichen Gefährdung von Dateien bei der Freigabe für Personen außerhalb Ihrer Organisation](share-limit-accidental-exposure.md)
- [Erstellen einer sicheren Gastfreigabeumgebung](create-secure-guest-sharing-environment.md)

Wenn Sie über ein Größeres Projekt mit einer Partnerorganisation verfügen, können Sie Azure Entitlement Management verwenden, um die Gäste aus dieser Organisation in einem Team zu verwalten, das Sie für das Projekt eingerichtet haben. Weitere Informationen finden Sie unter "Erstellen [eines B2B-Extranets mit verwalteten](b2b-extranet.md) Gästen".

## <a name="deploy-the-secure-collaboration-solution"></a>Bereitstellen der Lösung für die sichere Zusammenarbeit

Wenn Sie bereit sind, diese Lösung bereitstellen zu können, fahren Sie mit den folgenden Schritten fort:
1. Konfigurieren Sie [die drei verschiedenen Schutzebenen für Teams.](configure-teams-three-tiers-protection.md)
2. Konfigurieren Sie Einstellungen für [die Freigabe von Informationen beliebiger Vertraulichkeit für Personen außerhalb Ihrer Organisation.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Sicherheitsdokumentation](https://docs.microsoft.com/microsoft-365/security)

[Microsoft 365-Compliance-Dokumentation](https://docs.microsoft.com/microsoft-365/compliance)

[Willkommen bei Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
