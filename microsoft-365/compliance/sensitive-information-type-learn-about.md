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
ms.openlocfilehash: 7e99198e0713a1940f094c3875293b2590f31e3f
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256855"
---
# <a name="learn-about-sensitive-information-types"></a>Weitere Informationen zu Typen vertraulicher Informationen

Das Identifizieren und Klassifizieren vertraulicher Elemente, die der Kontrolle Ihrer Organisation unterliegen, ist der erste Schritt in der [Informationsschutz-Abteilung.](./information-protection.md)  Microsoft 365 bietet drei Möglichkeiten zum Identifizieren von Elementen, sodass sie klassifiziert werden können:

- manuell von Benutzern
- automatische Mustererkennung, z. B. Typen vertraulicher Informationen
- [Maschinelles Lernen](classifier-learn-about.md)

Typen vertraulicher Informationen sind musterbasierte Klassifizierer. Sie erkennen vertrauliche Informationen wie Sozialversicherungs-, Kreditkarten- oder Bankkontonummern, um vertrauliche Elemente zu identifizieren. Siehe [Entitätsdefinitionen für Typen vertraulicher Informationen.](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>Typen vertraulicher Informationen werden in

- [Richtlinien zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md) 
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](retention.md)
- [Insider-Risikomanagement](insider-risk-management.md)
- [Kommunikationscompliance](communication-compliance.md)
- [Richtlinien für die automatische Kennzeichnung](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Grundlegende Teile eines vertraulichen Informationstyps

Jede Entität des Vertraulichen Informationstyps wird durch die folgenden Felder definiert:

- Name: Wie auf den Vertraulichen Informationstyp verwiesen wird
- description: beschreibt, wonach der Typ vertraulicher Informationen sucht
- Muster: Ein Muster definiert, was ein vertraulicher Informationstyp erkennt. Es besteht aus den folgenden Komponenten
    - Primäres Element – das Hauptelement, nach dem der Typ vertraulicher Informationen sucht. Es kann sich um einen **regulären Ausdruck** mit oder ohne Prüfsummenüberprüfung, eine **Schlüsselwortliste,** ein **Schlüsselwortwörterbuch** oder eine **Funktion sein.**
    - Unterstützendes Element – Elemente, die als unterstützende Nachweise dienen und dazu beitragen, das Vertrauen der Übereinstimmung zu erhöhen. Beispiel: Schlüsselwort "SSN" in der Nähe einer SSN-Nummer. Es kann sich um einen regulären Ausdruck mit oder ohne Prüfsummenüberprüfung, Schlüsselwortliste, Schlüsselwortwörterbuch oder Wörterbuch sein.
    - Konfidenzniveau – Konfidenzniveau (hoch, mittel, niedrig) gibt an, wie viele unterstützende Nachweise zusammen mit dem primären Element gefunden wurden. Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Wahrscheinlichkeit, dass ein übereinstimmendes Element die vertraulichen Informationen enthält, nach denen Sie suchen.
    - Näherung – Anzahl der Zeichen zwischen primärem und unterstützendem Element

![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Weitere Informationen zu Vertrauensstufen finden Sie in diesem Video.


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Beispiel für vertraulichen Informationstyp


## <a name="argentina-national-identity-dni-number"></a>Nationale Identität (DNI) für Argentinien

### <a name="format"></a>Format

Acht Ziffern, durch Punkte getrennt

### <a name="pattern"></a>Muster

Acht Ziffern:
- Zwei Ziffern
- ein Punkt
- drei Ziffern
- ein Punkt
- drei Ziffern

### <a name="checksum"></a>Prüfsumme

Nein

### <a name="definition"></a>Definition

Eine DLP-Richtlinie hat mittleres Vertrauen, dass diese Art vertraulicher Informationen erkannt wird, wenn innerhalb einer Näherung von 300 Zeichen:
- Der reguläre Ausdruck Regex_argentina_national_id nach Inhalten sucht, die dem Muster entsprechen.
- Es wird ein Schlüsselwort aus Keyword_argentina_national_id gefunden.

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
- Nationale Identifikationskarte 
- Dni 
- Nationale NIC-Registrierung von Personen 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Weitere Informationen zu Konfidenzniveaus

In einer Entitätsdefinition des Vertraulichen Informationstyps gibt die **Konfidenzstufe** an, wie viel unterstützende Nachweise zusätzlich zum primären Element erkannt werden. Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Wahrscheinlichkeit, dass ein übereinstimmendes Element die vertraulichen Informationen enthält, nach denen Sie suchen. Übereinstimmungen mit einem hohen Konfidenzniveau enthalten beispielsweise mehr unterstützende Nachweise in direkter Nähe des primären Elements, während Übereinstimmungen mit einem niedrigen Konfidenzniveau wenig bis gar keine unterstützenden Nachweise in der nähe enthalten würden. 

Eine hohe Konfidenzstufe gibt die wenigsten falsch positiven Ergebnisse zurück, kann aber zu mehr falsch negativen Ergebnissen führen. Niedrige oder mittlere Konfidenzniveaus geben mehr falsch positive Ergebnisse zurück, aber nur wenige bis null falsch negative Werte.

- **niedrige Konfidenz:** Der Wert von 65, übereinstimmende Elemente enthalten die wenigsten falsch negativen, aber die falsch positiven Ergebnisse. Niedrige Konfidenz gibt alle Übereinstimmungen mit niedriger, mittlerer und hoher Konfidenz zurück.
- **mittlere Konfidenz:** Der Wert von 75, übereinstimmende Elemente enthalten eine durchschnittliche Menge falsch positiver und falsch negativer Ergebnisse. Mittlere Konfidenz gibt alle mittleren und hohen Konfidenzüberstimmungen zurück.  
- **Hohe Konfidenz:** Der Wert von 85, übereinstimmende Elemente enthalten die wenigsten falsch positiven, aber die falsch negativen Werte. Hohe Konfidenz gibt nur Übereinstimmungen mit hoher Konfidenz zurück.  

Sie sollten Muster mit hoher Konfidenzstufe mit niedrigen Zählungen verwenden, z. B. fünf bis zehn, und Muster mit niedriger Konfidenz mit höheren Zählungen, z. B. 20 oder mehr.

> [!NOTE]
> Wenn Sie vorhandene Richtlinien oder benutzerdefinierte Typen vertraulicher Informationen (SITs) mithilfe von nummernbasierten Konfidenzniveaus definiert haben (auch als Genauigkeit bekannt), werden sie automatisch den drei diskreten Konfidenzniveaus zugeordnet. Geringes Vertrauen, mittleres Vertrauen und hohe Vertrauenswürdigkeit in der Benutzeroberfläche des Security @ Compliance Centers.
> - Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierte SIT-Muster mit Konfidenzniveaus zwischen 76 und 100 werden einer hohen Zuverlässigkeit zugeordnet. 
> - Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierte SIT-Muster mit Konfidenzniveaus zwischen 66 und 75 werden mittleren Konfidenzwerten zugeordnet.
> - Alle Richtlinien mit minimaler Genauigkeit oder benutzerdefinierte SIT-Muster mit Konfidenzniveaus, die kleiner oder gleich 65 sind, werden einem niedrigen Konfidenzniveau zugeordnet. 

## <a name="creating-custom-sensitive-information-types"></a>Benutzerdefinierte Typen vertraulicher Informationen erstellen

Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:

- **Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers. Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden. Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).

- **EDM verwenden** Sie können benutzerdefinierte Typen vertraulicher Informationen mit Hilfe der Exact Data Match (EDM)-basierten Klassifizierung einrichten. Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen. Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell. Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen. Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
> Verbesserte Konfidenzniveaus sind für die sofortige Verwendung innerhalb der Verhinderung von Datenverlust für Microsoft 365 Dienste, Microsoft Information Protection für Microsoft 365 Dienste, Kommunikationscompliance, Informationsgovernance und Datensatzverwaltung verfügbar.
> Microsoft 365 Information Protection unterstützt jetzt Doppelbyte-Zeichensatzsprachen für:
> - Chinesisch (vereinfacht)
> - Chinesisch (traditionell)
> - Koreanisch
> - Japanisch
> 
> Diese Unterstützung ist für vertrauliche Informationstypen verfügbar. Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).

> [!TIP]
> Um Muster zu erkennen, die chinesische/japanische Zeichen und einzelne Bytezeichen enthalten, oder um Muster zu erkennen, die Chinesisch/Japanisch und Englisch enthalten, definieren Sie zwei Varianten des Schlüsselworts oder regex. Um beispielsweise ein Schlüsselwort wie "机密的document" zu erkennen, verwenden Sie zwei Varianten des Schlüsselworts. eine mit einem Leerzeichen zwischen dem japanischen und englischen Text und einer anderen ohne Leerzeichen zwischen dem japanischen und dem englischen Text. Daher sollten die Schlüsselwörter, die in der SIT hinzugefügt werden sollen, "机密的 document" und "机密的document" sein. Auf ähnliche Weise sollten zwei Varianten verwendet werden, um einen Ausdruck "プンンンンンピッン2020" zu erkennen; "プンンンンピッン 2020" und "プンンンンピッン2020".
> 
> Stellen Sie beim Erstellen eines regulären Ausdrucks mithilfe eines Doppelbyte-Bindestrichs oder eines doppelten Byte-Punkts sicher, dass beide Zeichen wie ein Trennstrich oder ein Punkt in einem regulären Ausdruck escapet werden. Hier ist ein Beispiel für einen regulären Ausdruck als Referenz:
>    - (?<!\d) ([4][0-9] {3} [ \- ?\-\t]*[0-9]{4}
>
> Es wird empfohlen, die Zeichenfolgenüberstimmung anstelle der Wortüberstimmung in einer Schlüsselwortliste zu verwenden.

## <a name="for-further-information"></a>Weitere Informationen
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps](create-a-custom-sensitive-information-type.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps in PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

Informationen zur Verwendung vertraulicher Informationstypen zur Einhaltung von Datenschutzbestimmungen finden Sie unter [Bereitstellen des Informationsschutzes für Datenschutzbestimmungen mit Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy).

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
