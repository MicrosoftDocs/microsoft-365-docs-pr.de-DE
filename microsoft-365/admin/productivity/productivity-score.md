---
title: Microsoft-Produktivitätsbewertung
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
description: Erfahren Sie, wie die Microsoft-Produktivitätsbewertung Messwerte für Personen- und Technologieerfahrungen widerspiegelt und vergleichen Sie sie mit Organisationen ähnlicher Größe.
ms.openlocfilehash: ddbc1590abc1383035db1852345310bfc8dd196d
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393667"
---
# <a name="microsoft-productivity-score"></a>Microsoft-Produktivitätsbewertung 

Die Produktivitätsbewertung unterstützt den Prozess der digitalen Transformation mit Einblicken dazu, wie Ihre Organisation Microsoft 365 und die Technologielösungen verwendet, von denen es unterstützt wird. Das Bewertungsergebnis Ihrer Organisation reflektiert Messungen der Mitarbeiter- und Technologieerfahrung und kann mit Benchmarks von Organisationen verglichen werden, die größenmäßig Ihrer ähnlich sind.

Es umfasst:

- **Metriken**, die Ihnen dabei helfen, zu sehen, wo Sie sich auf dem Weg der digitalen Transformation befinden.
- **Erkenntnisse** zu den Daten, mit denen Sie Potential zur Verbesserung der Produktivität und Zufriedenheit in Ihrer Organisation identifizieren können.
- **Empfohlene Maßnahmen**, mit denen Sie Ihrer Organisation helfen können, Microsoft 365-Produkte effizient zu nutzen.

Es werden Metriken, Erkenntnisse und Empfehlungen in zwei Bereichen bereitgestellt: 

- **Mitarbeitererfahrung:** Quantifiziert, wie die Organisation mit Microsoft 365-Kategorien wie Zusammenarbeit an Inhalten, Mobilität, Kommunikation, Besprechungen und Teamwork arbeitet.  

    In jeder der genannten Kategorien wird auf öffentliche Forschung eingegangen, um bewährte Methoden und die entsprechenden Vorteile im Sinne betrieblicher Effizienz zu ermitteln. So haben Untersuchungen von Forrester beispielsweise ergeben, dass Personen, die in der Cloud zusammenarbeiten und Inhalte für andere freigeben (anstatt Anlagen per E-Mail zu senden), bis zu 100 Minuten pro Woche sparen können. Die Verwendung solcher bewährten Methoden in Ihrer Organisation wird zudem quantifiziert, damit Sie sehen können, wo Sie sich auf dem Weg der digitalen Transformation befinden. 

- **Technologieerfahrung:** Ihre Organisation hängt von zuverlässigen und leistungsfähigen Technologien wie auch von der effizienten Nutzung von Microsoft 365 ab. [Endpunktanalyse:](https://aka.ms/endpointanalytics) Sie hilft Ihnen zu verstehen, wie Ihre Organisation durch Probleme mit der Leistung und Integrität Ihrer Hardware und Software beeinträchtigt werden kann. Die Microsoft 365 Apps-Integrität hilft Ihnen zu verstehen, ob Microsoft 365-Apps auf den Geräten in Ihrer Organisation in den empfohlenen Kanälen ausgeführt werden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einen Überblick und Einzelheiten zu den Voraussetzungen finden Sie unter [Was ist die Endpunktanalyse](/mem/analytics/overview). Weitere Informationen zu den Insights in die Microsoft 365-Netzwerkverbindungen finden Sie unter [Überblick über die Netzwerkverbindungen](../../enterprise/microsoft-365-networking-overview.md).

Für Mitarbeitererfahrungsdaten benötigen Sie ein Abonnement für Microsoft 365 für Business oder Office 365 für Unternehmen. Für Endpunktanalysedaten Ihres Mandanten müssen Sie Microsoft Intune zu Ihrem Abonnement hinzufügen. Intune hilft beim Schutz Ihrer Unternehmensdaten durch die Verwaltung von Geräten und Apps. Sobald Sie Intune hinzugefügt haben, können Sie die Endpunktanalyse innerhalb der Intune-Umgebung aktivieren. Um mehr über Microsoft Intune zu erfahren, lesen Sie die [Microsoft Intune-Dokumentation](/mem/intune/). 

> [!NOTE]
> Eine Lizenz für Workplace Analytics ist nicht Voraussetzung, um die Produktivitätsbewertungsfunktionen nutzen zu können.

Die Produktivitätsbewertung steht nur im Microsoft 365 Admin Center zur Verfügung und kann nur von IT-Experten genutzt werden, die über eine der folgenden Rollen verfügen:  

- Globaler Administrator
- Exchange-Administrator
- SharePoint-Administrator
- Skype for Business-Administrator
- Microsoft Teams-Administrator
- Globaler Leser
- Berichteleser
- Leseberechtigter für Verwendungszusammenfassungsberichte

> [!NOTE]
> Nur ein IT-Experte mit der Rolle „Globaler Administrator“ kann einen Mandanten für die Produktivitätsbewertung registrieren oder auswählen.

Das Modell der Rollenbasierten Zugriffssteuerung für die Produktivitätsbewertung hilf Organisationen dabei, digitale Transformationen mit Microsoft 365 zu fördern, indem es Flexibilität beim Zuweisen von Rollen an IT-Experten innerhalb einer Organisation bietet.

Microsoft hat sich zum Schutz persönlicher Daten verpflichtet. In diesem [Datenschutzdokument](privacy.md) werden die von uns bereitgestellten Steuerelemente erläutert, mit denen Sie als IT-Administrator Ihrer Organisation sicherstellen können, dass die Informationen nutzbar sind und zugleich das Vertrauen, das Sie in Microsoft setzen, nicht beeinträchtigt wird.

Sie finden die Bewertung über die Startseite von Microsoft 365 Admin unter **Berichte** > **Produktivitätsbewertung**.
  
## <a name="how-the-score-is-calculated"></a>So wird Ihre Bewertung berechnet

Ihre Produktivitätsbewertung basiert auf den kombinierten Bewertungen der Kategorien Mitarbeiter- und Technologieerfahrung. Jede Kategorie wird gleich gewichtet, mit einem Total von 100 Punkten. Die höchste mögliche Produktivitätsbewertung liegt bei 800.

### <a name="score-categories"></a>Bewertungskategorien 

- Kommunikation (100 Punkte)
- Besprechungen (100 Punkte)
- Zusammenarbeit an Inhalten (100 Punkte)
- Teamarbeit (100 Punkte)
- Mobilität (100 Punkte)
- Endpunktanalyse (100 Punkte)
- Netzwerkverbindungen (100 Punkte)
- Microsoft 365 Apps-Integrität (100 Punkte)
- **Höchstmögliches Gesamtergebnis: 800 Punkte**
 
In jeder Bewertungskategorie werden die wichtigsten Indikatoren für die Verwendung von Microsoft 365 in Ihrer Organisation auf dem Weg der digitalen Transformation quantifiziert. Wir bieten 28-Tage- und 180-Tage-Ansichten der Schlüsselaktivitäten. Wir stellen auch unterstützende Metriken zur Verfügung, die nicht Teil der Punkteberechnung sind, aber wichtig sind, um zugrunde liegende Nutzungsstatistiken und Konfigurationen zu identifizieren, bei denen Sie ansetzen können.

### <a name="products-included-in-productivity-score"></a>Produkte, die bei der Produktivitätsbewertung berücksichtigt werden 

Die Produktivitätsbewertung enthält Daten zu Exchange, SharePoint, OneDrive, Microsoft Teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer und Skype.

Das Bewertungsergebnis Ihrer Organisation wird täglich aktualisiert und spiegelt Benutzeraktionen wider, die in den letzten 28 Tagen (einschließlich des aktuellen Tags) durchgeführt wurden.

## <a name="interpreting-your-organizations-productivity-score"></a>Interpretieren der Produktivitätsbewertung Ihrer Organisation 

Auf der Startseite der Produktivitätsbewertung sehen Sie die Gesamtpunktzahl und den Bewertungsverlauf Ihrer Organisation sowie die wichtigsten Erkenntnisse für jede Kategorie.

:::image type="content" source="../../media/prodscore-landing.png" alt-text="Produktivitätsbewertungsseite unter &quot;Berichte&quot;.":::

**Das Bewertungsergebnis Ihrer Organisation** wird als Prozentwert und in Punkten angezeigt. Sie können Ihre Punkte im Zähler und die maximal möglichen Punkte im Nenner sehen.

Mit dem **Peer-Benchmark** können Sie die Bewertung Ihrer Organisation mit Unternehmen ähnlich dem Ihren vergleichen. Der Peer-Benchmark für die Kategorie der Mitarbeitererfahrung wird als Durchschnitt der Maßnahmen innerhalb einer Reihe ähnlicher Unternehmen berechnet. Die Gruppe der Unternehmen besteht aus Firmen in Ihrer Region mit einer ähnlichen Anzahl lizenzierter Benutzer, Lizenztypen, Branchen und Erfahrungen mit Microsoft 365.

> [!NOTE]
> Microsoft verwendet interne Daten, um die Branche festzulegen, die auf eine Organisation zutrifft. Mandaten unter einer übergeordneten Organisation erhalten die gleiche Branche zugewiesen wie die übergeordnete Organisation. Organisationen können Branchenzuweisungen nicht anzeigen oder ändern.

Der Peer-Benchmark für die Endpunktanalyse enthält Ziele für die Leistung beim Gerätestart und die empfohlene Softwarekonfiguration basierend auf aggregierten Medianwerten über alle Mandanten hinweg.

Der empfohlene Benchmark-Wert für Netzwerkverbindungen beträgt 80 Punkte.

Der Abschnitt **Score-Aufschlüsselung** enthält eine Aufschlüsselung Ihrer Produktivitätsbewertung mit Benchmarks in den Bereichen Mitarbeiter- und Technologie-Erfahrungen.

Der Bewertungsverlauf zeigt Ihnen, wie sich Ihr Ergebnis in jeder Kategorie innerhalb der letzten sechs Monate verändert hat.

Die Bereiche **Mitarbeiter-Erfahrungen** und **Technologie-Erfahrungen** enthalten die wichtigsten Erkenntnisse für die Kategorien in diesen Bereichen. Sie können jede Kategorie auswählen, um vertiefte Einblicke zu sehen.

## <a name="category-details-pages"></a>Kategoriedetailseiten

Jede Kategoriedetailseite zeigt die wichtigsten Erkenntnisse und unterstützenden Metriken sowie zugehörige Forschungsergebnisse und Maßnahmen an, die Sie ergreifen können, um Veränderungen in Ihrem Unternehmen voranzutreiben. Forschungsergebnisse unterstützen die Bedeutung und Begründung der wichtigsten Erkenntnisse für jede Kategorie. Weitere Informationen [finden Sie im Forrester-Bericht](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2PBrb).

Die Detailseiten sind:
- [Inhaltszusammenarbeit – Mitarbeiter-Erfahrungen](content-collaboration.md)
- [Kommunikation – Mitarbeiter-Erfahrungen](communication.md)
- [Besprechungen – Mitarbeiter-Erfahrungen](meetings.md)
- [Mobilität – Mitarbeiter-Erfahrungen](mobility.md)
- [Teamarbeit – Mitarbeiter-Erfahrungen](teamwork.md)
- [Microsoft 365 Apps-Integrität – Technologie-Erfahrungen](apps-health.md)
- [Endpunktanalysen](/mem/analytics/productivity-score)

## <a name="business-continuity-special-report"></a>Spezialbericht zur Geschäftskontinuität

Der Bericht zur Geschäftskontinuität ist ein zeitlich begrenzter Workplace Intelligence-Bericht, der allen Microsoft 365-Kunden zur Verfügung steht, um sie bei der Führung ihres Unternehmens in dieser herausfordernden Zeit zu unterstützen.  

Dieser Bericht hilft Organisationen beim Verständnis folgender Aspekte: 

- Wie Zusammenarbeit und Kommunikation von der Umstellung auf Remote-Arbeit beeinflusst wird. 

- Die Auswirkungen auf die Work-Life-Balance bei der Anpassung der Mitarbeiter an die Arbeit von zu Hause aus. 

- Ob Remote-Besprechungen eine effektive Entscheidungsfindung fördern.

[Weitere Informationen zum Bericht zur Geschäftskontinuität](/Workplace-Analytics/tutorials/bcrps)

[Weitere Informationen über Microsoft Graph](/graph/).

> [!NOTE]
> Benutzer haben auch die Möglichkeit, über das [MyAnalytics-Dashboard](/workplace-analytics/myanalytics/use/dashboard-2) Einblicke in die Produktivität zu erhalten.


## <a name="we-want-to-hear-from-you"></a>Wir freuen uns über Ihr Feedback

Teilen Sie uns Ihre Gedanken zur Produktivitätsbewertung mit und Ihre Ideen, wie sie verbessert werden könnte. Verwenden Sie dafür die **Feedback**-Abschnitte innerhalb des Produkts und/oder wenden Sie sich an das für die Produktivitätsbewertung zuständige Team unter prodscorefeedback@microsoft.com.

## <a name="related-content"></a>Verwandte Inhalte

[Überwachen der Microsoft 365-Aktivitäten mit Hilfe von Berichten](../../admin/activity-reports/activity-reports.md) (Artikel)\
[Aktivieren von Analysen zur Nutzung von Microsoft 365](../../admin/usage-analytics/enable-usage-analytics.md) (Artikel)\
[Übersicht über das Microsoft 365 Admin Center](../../business-video/admin-center-overview.md) (Video)