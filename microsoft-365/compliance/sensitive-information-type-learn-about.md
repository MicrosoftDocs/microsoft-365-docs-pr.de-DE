---
title: Informationen zu Typen vertraulicher Informationen
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
ms.openlocfilehash: 896a529d67faddb45b2672ca077f5a8e3b19827e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49933081"
---
# <a name="learn-about-sensitive-information-types"></a>Informationen zu Typen vertraulicher Informationen

Das Identifizieren und Klassifizieren vertraulicher Elemente, die von Ihren Organisationen kontrolliert werden, ist der erste Schritt in der Information [Protection-Teilung.](protect-information.md)  Microsoft 365 bietet drei Möglichkeiten zum Identifizieren von Elementen, sodass sie klassifiziert werden können:

- manuell von Benutzern
- Automatisierte Mustererkennung, wie vertrauliche Informationstypen
- [Machine Learning](classifier-learn-about.md)

Vertrauliche Informationstypen sind musterbasierte Klassifizierungen. Sie erkennen vertrauliche Informationen wie Sozialversicherungs-, Kreditkarten- oder Bankkontonummern, um vertrauliche Elemente zu identifizieren. Weitere Informationen finden Sie unter Entitätsdefinitionen für Typen [vertraulicher Informationen.](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>Typen vertraulicher Informationen werden in

- [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md) 
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](retention.md)
- [Kommunikationscompliance](communication-compliance.md)
- [Richtlinien für die automatische Kennzeichnung](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Grundlegende Teile eines vertraulichen Informationstyps

Jede Entität für vertrauliche Informationstypen wird durch die folgenden Felder definiert:

- name: how the sensitive information type isreferred to
- description: beschreibt, wo nach dem Typ vertraulicher Informationen gesucht wird
- muster: Ein Muster definiert, was ein vertraulicher Informationstyp erkennt. Sie besteht aus den folgenden Komponenten:
    - Primäres Element – das Hauptelement, nach dem der Typ vertraulicher Informationen sucht. Es kann sich um einen regulären **Ausdruck** mit oder ohne Prüfsummenüberprüfung, eine **Schlüsselwortliste,** ein **Schlüsselwortwörterbuch** oder eine Funktion **sein.**
    - Unterstützendes Element – Elemente, die als unterstützende Nachweise fungieren, die dazu beitragen, die Konfidenz der Übereinstimmung zu erhöhen. Beispiel: Schlüsselwort "SSN" in der Nähe einer SSN-Nummer. Dabei kann es sich um einen regulären Ausdruck mit oder ohne Prüfsummenüberprüfung, Stichwortliste und Schlüsselwortverzeichnis sein.
    - Konfidenzniveau – Die Konfidenzniveaus (hoch, mittel, niedrig) geben an, wie viele unterstützende Nachweise zusammen mit dem primären Element erkannt wurden. Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Konfidenz, dass ein übereinstimmende Element die vertraulichen Informationen enthält, die Sie suchen.
    - Näherung – Anzahl der Zeichen zwischen primärem und unterstützendem Element

![Diagramm von bestätigenden Nachweisen und Näherungsfenster](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Weitere Informationen zu Vertrauensebenen finden Sie in diesem Video.


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Beispiel für vertraulichen Informationstyp


## <a name="argentina-national-identity-dni-number"></a>Argentinien – Nationale Identitätsnummer (DNI)

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

Eine DLP-Richtlinie hat mittlere Vertrauen, dass diese Art von vertraulichen Informationen erkannt wurde, wenn innerhalb von 300 Zeichen:
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
- Identität 
- Identification National Identity Card 
- DNI 
- Nationales NIC-Personenregistrierungsregister 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Weitere Informationen zu Konfidenzstufen

In einer Entitätsdefinition für vertrauliche Informationstypen spiegelt die Konfidenzstufe **wider,** wie viele unterstützende Nachweise zusätzlich zum primären Element erkannt werden. Je mehr unterstützende Nachweise ein Element enthält, desto höher ist die Konfidenz, dass ein übereinstimmende Element die vertraulichen Informationen enthält, die Sie suchen. Übereinstimmungen mit einem hohen Konfidenzniveau enthalten beispielsweise mehr unterstützende Nachweise in der Nähe des primären Elements, während Übereinstimmungen mit einem niedrigen Konfidenzniveau nur wenig bis keine unterstützenden Nachweise in unmittelbarer Nähe enthalten würden. 

Ein hoher Konfidenzniveau gibt die wenigsten falsch positiven Ergebnisse zurück, kann jedoch zu mehr falsch negativen Ergebnisse führen. Niedrige oder mittlere Konfidenzstufen geben mehr falsch positive Ergebnisse zurück, aber nur wenige bis null falsch negative Ergebnisse.

- **niedrige Konfidenz:** Wert 65, übereinstimmende Elemente enthalten die wenigsten falsch negativen Ergebnisse, aber die meisten falsch positiven Ergebnisse.  
- **mittlere Konfidenz:** Wert 75, übereinstimmende Elemente enthalten eine durchschnittliche Menge falsch positiver und falsch negativer Ergebnisse.  
- **hohe Konfidenz:** Wert 85, übereinstimmende Elemente enthalten die wenigsten falsch positiven Ergebnisse, aber die meisten falsch negativen Ergebnisse.  

Sie sollten Muster mit hoher Vertrauensebene mit geringer Anzahl verwenden, z. B. 5 bis 10, und Muster mit niedriger Konfidenz mit höherer Anzahl, z. B. 20 oder mehr.

## <a name="creating-custom-sensitive-information-types"></a>Benutzerdefinierte Typen vertraulicher Informationen erstellen

Zum Erstellen von benutzerdefinierten Typen für vertrauliche Informationen im Security & Compliance Center stehen Ihnen mehrere Optionen zur Verfügung:

- **Verwenden der Benutzeroberfläche** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit der Benutzeroberfläche des Security & Compliance Centers. Mit dieser Methode können Sie reguläre Ausdrücke, Schlüsselwörter und Schlüsselwörterbücher verwenden. Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen](create-a-custom-sensitive-information-type.md).

- **EDM verwenden** Sie können benutzerdefinierte Typen vertraulicher Informationen mit Hilfe der Exact Data Match (EDM)-basierten Klassifizierung einrichten. Mit dieser Methode können Sie anhand einer sicheren Datenbank, die sie regelmäßig aktualisieren können, einen dynamischen Typ vertraulicher Informationen erstellen. Mehr Informationen unter[Erstellen eines benutzerdefinierten Typs vertraulicher Informationen mit genauer Datenübereinstimmungsklassifizierung](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).

- **Verwenden von PowerShell** Erstellen Sie benutzerdefinierte Typen vertraulicher Informationen mit PowerShell. Diese Methode ist zwar komplexer als die Verwendung der Benutzeroberfläche, Sie haben aber mehr Konfigurationsoptionen. Mehr Informationen unter [Erstellen eines benutzerdefinierten Typs vertraulicher Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
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