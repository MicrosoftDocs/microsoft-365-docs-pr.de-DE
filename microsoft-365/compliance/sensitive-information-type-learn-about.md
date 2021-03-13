---
title: Weitere Informationen zu Typen vertraulicher Informationen
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: 13dee9d5744639149960a16adcf36b7ebe5718f7
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766400"
---
# <a name="learn-about-sensitive-information-types"></a>Weitere Informationen zu Typen vertraulicher Informationen

Das Identifizieren und Klassifizieren vertraulicher Elemente, die sich unter der Kontrolle Ihrer Organisation befinden, ist der erste Schritt in der [Information Protection-Disziplin.](protect-information.md)  Microsoft 365 bietet drei Möglichkeiten zum Identifizieren von Elementen, sodass sie klassifiziert werden können:

- manuell von Benutzern
- Automatische Mustererkennung, wie vertrauliche Informationstypen
- [maschinelles Lernen](classifier-learn-about.md)

Typen vertraulicher Informationen sind musterbasierte Klassifizierungen. Sie erkennen vertrauliche Informationen wie soziale Sicherheit, Kreditkarten- oder Bankkontonummern, um vertrauliche Elemente zu identifizieren. Weitere Informationen finden Sie unter [Entitätsdefinitionen](sensitive-information-type-entity-definitions.md) für Typen vertraulicher Informationen.

## <a name="sensitive-information-types-are-used-in"></a>Typen vertraulicher Informationen werden in

- [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md) 
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](retention.md)
- [Kommunikationscompliance](communication-compliance.md)
- [Richtlinien für die automatische Kennzeichnung](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Grundlegende Teile eines vertraulichen Informationstyps

Jede Entität vom Typ vertraulicher Informationen wird durch die folgenden Felder definiert:

- Name: So wird auf den Typ vertraulicher Informationen verwiesen
- description: beschreibt, wofür der Typ vertraulicher Informationen gesucht wird
- pattern: Ein Muster definiert, was ein vertraulicher Informationstyp erkennt. Es besteht aus den folgenden Komponenten
    - Primäres Element – das Hauptelement, nach dem der Typ vertraulicher Informationen sucht. Es kann sich um einen **regulären Ausdruck** mit oder ohne Prüfsummenüberprüfung, eine Schlüsselwortliste, ein  **Schlüsselwortwörterbuch** oder eine Funktion **sein.**
    - Unterstützendes Element – Elemente, die als unterstützende Nachweise fungieren, die dazu beitragen, das Vertrauen der Übereinstimmung zu erhöhen. Beispiel: Schlüsselwort "SSN" in der Nähe einer SSN-Nummer. Es kann ein regulärer Ausdruck mit oder ohne Prüfsummenüberprüfung, Stichwortliste, Schlüsselwortwörterbuch sein.
    - Konfidenzstufe – Konfidenzstufen (hoch, mittel, niedrig) spiegeln wider, wie viele unterstützende Nachweise zusammen mit dem primären Element erkannt wurden. Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Sicherheit, dass ein übereinstimmendes Element die von Ihnen gesuchten vertraulichen Informationen enthält.
    - Näherung – Anzahl der Zeichen zwischen primärem und unterstützendem Element

![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Weitere Informationen zu Vertrauensebenen finden Sie in diesem Video.


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Beispieltyp für vertrauliche Informationen


## <a name="argentina-national-identity-dni-number"></a>Nationale Identität (DNI) (Argentina National Identity)

### <a name="format"></a>Format

Acht Ziffern, durch Punkte getrennt

### <a name="pattern"></a>Muster

Acht Ziffern:
- zwei Ziffern
- ein Zeitraum
- drei Ziffern
- ein Zeitraum
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittlere Sicherheit, dass sie diese Art vertraulicher Informationen erkannt hat, wenn innerhalb einer Nähe von 300 Zeichen:
- Der reguläre Ausdruck Regex_argentina_national_id findet Inhalte, die dem Muster entsprechen.
- Ein Schlüsselwort aus Keyword_argentina_national_id gefunden.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Schlüsselwörter

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Argentina National Identity number 
- Identity 
- Identifikation der nationalen Identitätskarte 
- DNI 
- Nationales NIC-Personenregister 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Weitere Informationen zu Konfidenzstufen

In einer Entitätsdefinition für vertrauliche **Informationstypen** gibt die Konfidenzstufe an, wie viele unterstützende Nachweise zusätzlich zum primären Element erkannt werden. Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Sicherheit, dass ein übereinstimmendes Element die von Ihnen gesuchten vertraulichen Informationen enthält. Beispielsweise enthalten Übereinstimmungen mit einem hohen Konfidenzniveau mehr nachweisende Nachweise in unmittelbarer Nähe des primären Elements, während Übereinstimmungen mit einem niedrigen Konfidenzniveau nur wenig bis keine Nachweise in unmittelbarer Nähe enthalten würden. 

Ein hohes Konfidenzniveau gibt die wenigsten falsch positiven Ergebnisse zurück, kann jedoch zu weiteren falsch negativen Folgen führen. Niedrige oder mittlere Konfidenzstufen geben mehr falsch positive Werte zurück, aber nur wenige bis null falsch negative Werte.

- **niedrige Konfidenz**: Der Wert von 65, übereinstimmende Elemente enthalten die wenigsten falsch negativen, aber die meisten falsch positiven Ergebnisse. Niedrige Konfidenz gibt alle Übereinstimmungen mit niedriger, mittlerer und hoher Konfidenz zurück.
- **mittlere Konfidenz**: Der Wert von 75, übereinstimmende Elemente enthalten eine durchschnittliche Menge falsch positiver und falsch negativer Werte. Mittlere Konfidenz gibt alle übereinstimmungen mit mittlerer und hoher Vertrauenssicherheit zurück.  
- **hohe Konfidenz**: Der Wert von 85, übereinstimmende Elemente enthalten die wenigsten falsch positiven, aber die meisten falsch negativen. Hohe Vertrauenssicherheit gibt nur Übereinstimmungen mit hoher Vertrauenssicherheit zurück.  

Sie sollten Muster mit hoher Konfidenzstufe mit niedrigen Zählungen(z. B. fünf bis zehn) und niedrigen Konfidenzmustern mit höheren Zählungen (z. B. 20 oder mehr) verwenden.

> [!NOTE]
> Wenn Sie vorhandene Richtlinien oder benutzerdefinierte Typen vertraulicher Informationen (SITs) mithilfe von zahlenbasierten Konfidenzstufen (auch als Genauigkeit bekannt) definiert haben, werden sie automatisch den drei diskreten Zuverlässigkeitsstufen zugeordnet. geringes Vertrauen, mittleres Vertrauen und hohe Vertrauenssicherheit auf der Benutzeroberfläche des Security @ Compliance Center.
> - Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierten SIT-Mustern mit Konfidenzstufen zwischen 76 und 100 werden einer hohen Zuverlässigkeit zugeordnet. 
> - Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierten SIT-Mustern mit Konfidenzstufen zwischen 66 und 75 werden mittlerer Zuverlässigkeit zugeordnet.
> - Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierten SIT-Mustern mit Konfidenzstufen kleiner oder gleich 65 werden einer niedrigen Zuverlässigkeit zugeordnet. 

## <a name="creating-custom-sensitive-information-types"></a>Benutzerdefinierte Typen vertraulicher Informationen erstellen

Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:

- **Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers. Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden. Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).

- **EDM verwenden** Sie können benutzerdefinierte Typen vertraulicher Informationen mit Hilfe der Exact Data Match (EDM)-basierten Klassifizierung einrichten. Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen. Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell. Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen. Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
> Verbesserte Vertrauensebenen stehen für die sofortige Verwendung in der Verhinderung von Datenverlust für Microsoft 365-Dienste, Microsoft Information Protection für Microsoft 365-Dienste, Kommunikationskonformität, Informations-Governance und Datensatzverwaltung zur Verfügung.

> Microsoft 365 Information Protection unterstützt jetzt in der Vorschau Doppelbyte-Zeichensatz-Sprachen für:
> - Chinesisch (vereinfacht)
> - Chinesisch (traditionell)
> - Koreanisch
> - Japanisch

>Diese Unterstützung ist für vertrauliche Informationstypen verfügbar. Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).

## <a name="for-further-information"></a>Weitere Informationen
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps in PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
