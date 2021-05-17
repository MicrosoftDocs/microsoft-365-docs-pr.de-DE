---
title: Microsoft Productivity Score – Inhaltszusammenarbeit
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Details zur Inhaltszusammenarbeit – Die Produktivitätssentwertung für Personen.
ms.openlocfilehash: 43a5fbc3b1c4b6227cd29d79bfb0928a3b4b8ac9
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903322"
---
# <a name="content-collaboration--people-experiences"></a>Inhaltszusammenarbeit – Erfahrungen mit Personen

Die Produktivitätswertung bietet Einblicke in die digitale Transformationsreise Ihrer Organisation durch die Verwendung von Microsoft 365 und die Technologieerfahrungen, die sie unterstützen. Die Bewertung Ihrer Organisation spiegelt Messungen der Benutzer- und Technologieerfahrung wider und kann mit Benchmarks von Organisationen vergleichbar mit Ihrer verglichen werden. Die Kategorie für die Inhaltszusammenarbeit ist Teil der Personenerfahrungsmessungen. Weitere Informationen finden Sie in der [Übersicht über die Produktivitätsergebnis](productivity-score.md) und in [der Datenschutzerklärung von Microsoft.](https://privacy.microsoft.com/privacystatement)

## <a name="prerequisites"></a>Voraussetzungen

Um mit Denkkenntnissen zur Inhaltszusammenarbeit zu beginnen, müssen Personen in Ihrer Organisation lizenziert sein für:

- OneDrive for Business
- SharePoint
- Exchange Online

Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](../manage/assign-licenses-to-users.md).

 Nachdem Personen in den oben genannten Produkten in den letzten 28 Tagen mindestens einmal aktiv waren, werden Sie die Einblicke sehen.

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>Warum ihre Organisation&#39;Bewertung der Inhaltszusammenarbeit wichtig ist

Ein wichtiger Aspekt der digitalen Transformation ist die Zusammenarbeit von Personen in Dateien. Mit Ihren Inhalten Microsoft 365 Personen auf Inhalte zugreifen, erstellen, ändern und zusammenarbeiten sie mit anderen Personen von jedem Beliebigen Ort aus. Untersuchungen zeigen, dass jede Person bei der Zusammenarbeit mit Onlinedateien durchschnittlich 100 Minuten pro Woche speichert. [Weitere Informationen finden Sie im Nachweis](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

## <a name="how-we-calculate-the-content-collaboration-score"></a>Berechnen der Bewertung für die Inhaltszusammenarbeit

Wir bieten einen primären Einblick, der die wichtigsten Metriken für die Inhaltszusammenarbeit in Ihrer Organisation enthält. Anschließend wird ein unten beschriebenes Bewertungsframework für diese Metriken verwendet, um die Bewertung Ihrer Organisation zu berechnen.

> [!NOTE]
> Am 22. April 2021 haben wir die Berechnung der Metrik der Mitarbeiter geändert. Dies wirkt [sich auf den primären Einblick,](#primary-insight)die Einblicke [in](#number-of-files-collaborated-on)die Dateizusammenarbeit und die Art und Weise aus, wie die Bewertung der Inhaltszusammenarbeit gemessen wird. Diese Änderung trägt dazu bei, das Rauschen in den Daten von nicht menschlichen Agents (oder Bots) von Microsoft und anderen Drittanbieteranwendungen zu reduzieren, was zu einer genaueren und umsetzbaren Bewertung führt.

### <a name="primary-insight"></a>Primärer Einblick

Microsoft OneDrive for Business und SharePoint Personen dabei helfen, ihre individuellen und freigegebenen Inhalte in Microsoft 365 Geräten und Anwendungen zu erstellen, zu lesen und zu entdecken. Darüber hinaus können Benutzer Inhalte sicher freigeben und zusammenarbeiten. Der primäre Einblick enthält Informationen von allen, die OneDrive for Business und SharePoint. Darüber hinaus werden die Details darüber, wie viele Personen Inhalte lesen, erstellen und zusammenarbeiten, die in OneDrive for Business und SharePoint.

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="Primäre Einblicke aus der Bewertung der Zusammenarbeit in der Kommunikation.":::


Für diese Informationen berücksichtigte Typen sind Word-, Excel-, PowerPoint-, OneNote- und PDF-Dateien.

1. **Header:** Zeigt den Prozentsatz der Personen in Ihrer Organisation an, die Zugriff auf OneDrive oder SharePoint, die an Inhalten zusammenarbeiten.
2. **Textkörper:** Enthält weitere Informationen dazu, wie das Verhalten beim Lesen und Erstellen von Dateien online mit der Zusammenarbeit an Dateien verknüpft ist.
3. **Visualisierung (aktueller Status):**
    - Horizontale Balken, bei denen die blau gefärbten Abschnitte den Prozentsatz der Personen darstellen, die für die Dateizusammenarbeit über OneDrive oder SharePoint aktiviert sind, die in den letzten 28 Tagen **Leser,** Ersteller oder Mitarbeiter in Onlinedateien waren. 

        Sie sind wie folgt definiert:</br>
        **Leser:** Personen, die auf Onlinedateien in einem OneDrive oder SharePoint.</br>
        **Ersteller:** Personen, die Onlinedateien erstellen, ändern, hochladen, synchronisieren, einchecken, kopieren oder OneDrive oder SharePoint verschieben.</br>
        **Mitarbeiter:** Personen, die mit Onlinedateien mithilfe von OneDrive oder SharePoint. Zwei Personen sind Mitarbeiter, wenn einer von ihnen eine Online-Office-App oder PDF liest oder bearbeitet, nachdem die andere Person sie innerhalb eines 28-Tage-Fensters erstellt oder geändert hat.

        > [!NOTE]
        > Die in der Visualisierung berücksichtigten Dateien sind Word-, Excel-, PowerPoint-, OneNote- oder PDF-Dateien, die online sind und in OneDrive oder SharePoint. 

    - Die Hervorhebung (Zähler/Nenner) der Bruchzahl wird verwendet, um den Prozentsatz zu berechnen, der in den einzelnen horizontalen Balken ausgedrückt wird.
    
      - **Leser:**</br>
          - Zähler: Anzahl der Personen, die in den letzten 28 Tagen auf Onlinedateien in OneDrive oder SharePoint zugreifen oder diese herunterladen</br>
          - Nenner: Anzahl der Personen, die mindestens 1 der letzten 28 Tage Zugriff auf OneDrive oder SharePoint hatten</br>
      - **Ersteller:**</br>
        - Zähler: Anzahl der Personen, die in den letzten 28 Tagen Onlinedateien in OneDrive oder SharePoint erstellen, ändern, hochladen, synchronisieren, einchecken, kopieren oder verschieben</br>
        - Nenner: Anzahl der Personen, die mindestens 1 der letzten 28 Tage Zugriff auf OneDrive oder SharePoint hatten. </br> 
      - **Mitarbeiter:**</br>
        - Zähler: Anzahl der Personen, die in den letzten 28 Tagen an Onlinedateien in OneDrive oder SharePoint zusammenarbeiten</br>
        - Nenner: Anzahl der Personen, auf die OneDrive oder SharePoint mindestens 1 der letzten 28 Tage Zugriff hatten

    - Der Peer-Benchmarkwert für alle Leser, Ersteller und Mitarbeiter wird ebenfalls als Prozentsatz angezeigt. Mit anderen Worten, der Wert der Anzahl der Ersteller wird als Prozentsatz der Anzahl von Personen angezeigt, die Zugriff auf OneDrive oder SharePoint.
    
1. **Link zu Ressourcen:** Wählen Sie diesen Link aus, um zusammengeknallte Videos und andere verwandte Hilfeinhalte anzuzeigen.


#### <a name="trend-visualization-of-primary-insight"></a>Trendvisualisierung primärer Einblicke

Das Diagramm trendvisualisierungen zeigt die Trendlinie der wichtigsten Kennzahlen für Leser, Ersteller und Mitarbeiter in den letzten 180 Tagen. Jeder Datenpunkt im Diagramm ist ein Aggregat der Aktivität der letzten 28 Tage. Jeder Erstellerdatenpunkt bietet eine Anzahl aller Personen, die innerhalb der letzten 28 Tage für jedes Datum auf der x-Achse als Ersteller markiert wurden.

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="Diagramm mit Trends für die Zusammenarbeit primärer Einblick.":::

### <a name="scoring-framework"></a>Bewertungsframework

Die Bewertung der Inhaltszusammenarbeit für Ihre Organisation misst auf aggregierter (Organisations-)Ebene, ob Personen online Office Dateien wie Word, Excel, PowerPoint, OneNote oder PDFs oder in OneDrive oder SharePoint lesen, erstellen oder zusammenarbeiten.

Die Ergebnisse werden nicht auf der einzelnen Benutzerebene bereitgestellt.

## <a name="explore-how-your-organization-collaborates"></a>Erfahren Sie, wie Ihre Organisation zusammenarbeitet

Darüber hinaus stellen wir Ihnen Informationen zur Verfügung, mit deren Hilfe Sie einblicken können, wie Ihre Organisation an Inhalten zusammenarbeitt. Diese zusätzlichen Metriken tragen nicht direkt zu Ihrer Produktivitätsleistung bei, sondern helfen Ihnen, einen Aktionsplan als Teil Ihrer digitalen Transformation zu erstellen, um die Arbeit von Personen zu optimieren.

### <a name="creating-files-in-onedrive-or-sharepoint"></a>Erstellen von Dateien in OneDrive oder SharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="Diagramm, das die Anzahl der Personen anschaut, die Dateien in OneDrive oder SharePoint":::

1. **Header:** Momente prozentsatz der Personen, die in Microsoft 365 Office, die Dateien auf einer OneDrive oder einer SharePoint.
2. **Textkörper:** Enthält Informationen zum Wert der Inhaltserstellung in OneDrive und SharePoint.
3. **Visualisierung:** Die Aufschlüsselung in der Visualisierung stellt den Umfang dar, in dem Personen, die Microsoft Office-Apps zum Erstellen von Dateien in OneDrive und SharePoint verwenden, wie folgt:
      - **OneDrive:** Der blaue (farbige) Teil der Leiste und der Bruch auf der Leiste stellen den Prozentsatz der Personen dar, die in Office Anwendungen aktiv sind, die Inhalte auf OneDrive erstellen:
        - Zähler: Die Anzahl der Personen, die innerhalb der letzten 28 Tage Office Dateien in OneDrive erstellen, ändern, hochladen, synchronisieren, einchecken, kopieren oder verschieben.</br>
        - Nenner: Die Anzahl der Personen, die innerhalb der letzten 28 Tage Zugriff auf OneDrive oder SharePoint und auf Office-Dateien haben.
      - **SharePoint:** Der blaue (farbige) Teil der Leiste und der Bruch auf der Leiste stellen den Prozentsatz der Personen dar, die in Office-Anwendungen aktiv sind und Inhalte auf SharePoint erstellen:</br>
         - Zähler: Die Anzahl der Personen, die dateien (Microsoft Word, Excel, PowerPoint oder OneNote) auf SharePoint innerhalb der letzten 28 Tage erstellen, ändern, hochladen, synchronisieren, einchecken Office, kopieren oder verschieben.</br>
        - Nenner: Die Anzahl der Personen, die zugriff auf OneDrive oder SharePoint haben und innerhalb der letzten 28 Tage auf Office Dateien zugegriffen haben.

4. **Link zu Ressourcen:** Wählen Sie diesen Link aus, um Hilfeinhalte anzuzeigen.

### <a name="use-of-attachments-in-email"></a>Verwenden von Anlagen in E-Mails

:::image type="content" source="../../media/emailattachments.png" alt-text="Verwendung von E-Mail-Anlagen.":::

1. **Header: Momente** prozentsatz der Personen, die Anlagen in E-Mails verwenden, die nicht in E-Mails gespeichert OneDrive oder SharePoint.
2. **Textkörper:** Enthält Informationen über den Wert der Freigabe von Links zu Onlinedateien aus sicht der Zusammenarbeit und Sicherheit.
3. **Visualisierung:** Die Aufschlüsselung in der Visualisierung soll das Ausmaß darstellen, in dem Personen, die Inhalte in E-Mails anfügen, unterschiedliche Modi verwenden (Dateien nicht auf OneDrive oder SharePoint, Links zu Onlinedateien und in die E-Mail eingebettete Links):
      - **Anfügen von Dateien:** Der blaue (farbige) Teil der Leiste und der Bruch (Zähler/Nenner) auf der Leiste stellen den Prozentsatz der Personen dar, die Anlagen in E-Mails verwenden.
        - Zähler: Die Anzahl der Personen, die Dateien an E-Mails anfügen, die innerhalb der letzten 28 Tage nicht OneDrive oder SharePoint gespeichert wurden.
        - Nenner: Die Anzahl der Personen, die innerhalb der letzten 28 Tage Zugriff auf Exchange und OneDrive, SharePoint oder beides hatten.
      - **Links zu Onlinedateien:** Der blaue (farbige) Teil der Leiste und der Bruch (Zähler/Nenner) auf der Leiste stellen den Prozentsatz der Personen dar, die Anlagen verwenden und Links zu Dateien in E-Mails anfügen.
        - Zähler: Die Anzahl der Personen, die innerhalb der letzten 28 Tage Links zu Onlinedateien (gespeichert in OneDrive oder SharePoint) an E-Mails anfügen.
        - Nenner: Die Anzahl der Personen, die innerhalb der letzten 28 Tage Zugriff auf Exchange und OneDrive, SharePoint oder beide haben.
      - **Einbetten von Links in E-Mail:** Der blaue (farbige) Teil der Leiste und der Bruch auf der Leiste stellen den Prozentsatz der Personen dar, die Links in den Textkörper der E-Mails einbetten.
        - Zähler: Die Anzahl der Personen, die Links in E-Mails in Onlinedateien einbetten (gespeichert in OneDrive oder SharePoint) innerhalb der letzten 28 Tage.
        - Nenner: Die Anzahl der Personen, die innerhalb der letzten 28 Tage Zugriff auf Exchange und OneDrive, SharePoint oder beide haben.
4. **Link zu Ressourcen:** Wählen Sie diesen Link aus, um Hilfeinhalte anzuzeigen.

### <a name="sharing-of-online-files"></a>Freigeben von Onlinedateien

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="Diagramm, das die Anzahl der Personen anschaut, die Dateien online freigeben.":::

1. **Header:** Momente prozentuale Anzahl von Personen, auf die OneDrive oder SharePoint, die Dateien extern freigeben.
2. **Textkörper:** Enthält Informationen zu den Administratoren,&#39; die Dateifreigabeeinstellungen in der Organisation ändern können, um die für Ihre Organisation am besten geeignete Ebene der Zusammenarbeit zu ermöglichen.
3. **Visualisierung:** Gibt an, in welchem Umfang Personen, die Zugriff auf OneDrive oder SharePoint haben, Dateien intern oder extern freigeben:
      - **Extern:** Der blaue (farbige) Teil der Leiste und der Bruch (Zähler/Nenner) auf der Leiste stellen den Prozentsatz der Personen dar, die Zugriff auf OneDrive oder SharePoint haben und Dateien extern freigeben.
        -  Zähler: Die Anzahl der Personen, für die dateien extern in den letzten 28 Tagen freigegeben wurden
        - Nenner: Die Gesamtzahl der Personen, die mindestens 1 der letzten 28 Tage Zugriff auf OneDrive oder SharePoint hatten.
      - **Nur intern:** Der blaue (farbige) Teil der Leiste und der Bruch (Zähler/Nenner) auf der Leiste stellen den Prozentsatz der Personen dar, die Zugriff auf OneDrive oder SharePoint haben und Dateien nur intern freigeben.
        - Zähler: Die Anzahl der Personen, die intern nur innerhalb der letzten 28 Tage freigegebene Dateien haben
        - Nenner: Die Gesamtzahl der Personen, die mindestens 1 der letzten 28 Tage Zugriff auf OneDrive oder SharePoint hatten.
4. **Link zu Ressourcen:** Wählen Sie diesen Link aus, um Hilfeinhalte anzuzeigen.

### <a name="number-of-files-collaborated-on"></a>Anzahl der gemeinsamen Dateien

:::image type="content" source="../../media/intensityofcollab.png" alt-text="Diagramm, das zeigt, an wie vielen Dateien am meisten zusammengearbeitet wurde.":::

1. **Header:** Momente prozentsatz der Personen, die Zugriff auf OneDrive oder SharePoint, die an 4 oder mehr Dateien zusammenarbeiten.
2. **Textkörper:** Enthält Informationen dazu, wie Benutzer Onlinedateien für eine bessere Zusammenarbeit nutzen können.
3. **Visualisierung:** Zeigt eine Verteilung der Personen an, die Zugriff auf OneDrive oder SharePoint haben, basierend auf der Anzahl der Dateien, an denen sie zusammenarbeiten. Dies wird in den folgenden vier Kategorien gezeigt (für jede stellen der blaue Teil der Leiste und der Bruch den Prozentsatz der Personen dar, die Zugriff auf OneDrive oder SharePoint haben, die in diese Kategorie fallen):
      - **Keine Zusammenarbeit:**
        - Numerator: Anzahl der Personen, die in den letzten 28 Tagen nicht an Dateien zusammenarbeiten.
        - Nenner: Die Gesamtzahl der Personen, die zugriff auf OneDrive oder SharePoint mindestens 1 der letzten 28 Tage haben.
      - **Zusammenarbeit an 1-3-Dateien:**
        - Zähler: Anzahl der Personen, die in den letzten 28 Tagen an 1-3 Dateien zusammenarbeiten.
        - Nenner: Gesamtzahl der Personen, die mindestens 1 der letzten 28 Tage Zugriff auf OneDrive oder SharePoint hatten.
      - **Zusammenarbeit an 4-10-Dateien:**
        - Zähler: Anzahl der Personen, die in den letzten 28 Tagen an 4-10 Dateien zusammenarbeiten.
        - Nenner: Gesamtzahl der Personen, die mindestens 1 der letzten 28 Tage Zugriff auf OneDrive oder SharePoint hatten.
      - **Zusammenarbeit an 11 oder mehr Dateien:**
        - Zähler: Anzahl der Personen, die in den letzten 28 Tagen an 11 oder mehr Dateien zusammenarbeiten.
        - Nenner: Gesamtzahl der Personen, die mindestens 1 der letzten 28 Tage Zugriff auf OneDrive oder SharePoint hatten.
        
4. **Link zu Ressourcen:** Wählen Sie diesen Link aus, um Hilfeinhalte anzuzeigen.

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>Netzwerkleistungsstärke für OneDrive und SharePoint

:::image type="content" source="../../media/networkperfstrength.png" alt-text="Diagramm mit der Netzwerkleistung für OneDrive und SharePoint.":::

1. **Header:** Momente prozentsatz aller getesteten Geräte mit schlechter Netzwerkverbindung zu OneDrive und SharePoint. 
2. **Textkörper:** Enthält Informationen dazu, warum die Netzwerkverbindungsleistung für die Zusammenarbeit wichtig ist. 
3. **Visualisierung:** Zeigt einen Prozentsatz der Geräte mit unterschiedlichen Ebenen der Netzwerkkonnektivitätsleistung im Zusammenhang mit OneDrive und SharePoint:
      - **81-100 (am besten):** Der dunkelgrüne (farbige) Teil der Leiste stellt den Prozentsatz der Geräte mit der besten Leistung dar.
      - **61-80**: Der grüne (farbige) Teil der Leiste stellt den Prozentsatz der Geräte mit einer Netzwerkleistungsleistung zwischen 60 und 80 dar. 
      - **41-60**: Der orangefarbene Teil der Leiste stellt den Prozentsatz der Geräte mit einer Netzwerkleistungsleistung zwischen 40 und 60 dar. 
      - **21-40**: Der rote (farbige) Teil der Leiste stellt den Prozentsatz der Geräte mit einer Netzwerkleistungsleistung zwischen 20 und 40 dar. 
      - **0-20**: Der dunkelrote (farbige) Teil der Leiste stellt den Prozentsatz der Geräte mit der schlechtesten Netzwerkleistungsleistung zwischen 0 und 20 dar. 

## <a name="related-content"></a>Verwandte Inhalte

[Microsoft 365 apps health – Technologieerfahrungen](apps-health.md) (Artikel)\
[Kommunikation – Benutzererfahrungen](communication.md) (Artikel)\
[Besprechungen – Benutzererfahrungen](meetings.md) (Artikel)\
[Mobilität – Benutzererfahrungen](mobility.md) (Artikel)\
[Datenschutzsteuerelemente für Produktivitätsergebnis](privacy.md) (Artikel)\
[Teamwork – Erfahrungen mit Personen](teamwork.md) (Artikel)
