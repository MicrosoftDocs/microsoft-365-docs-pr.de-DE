---
title: Microsoft Compliance Configuration Analyzer für Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie Microsoft Compliance Configuration Analyzer verwenden, um mit Microsoft Compliance Manager schnell los zu werden.
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122395"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Microsoft Compliance Configuration Analyzer für Compliance Manager (Vorschau)

**In diesem Artikel:** Erfahren Sie, wie Sie das Microsoft Compliance Configure Analyzer-Tool installieren und ausführen, um schnell mit microsoft Compliance Manger zu beginnen.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Übersicht über Microsoft Compliance Configuration Analyzer (MCCA) (Vorschau)

Microsoft Compliance Configuration Analyzer (MCCA) ist ein Vorschautool, mit dem Sie mit [Microsoft Compliance Manager beginnen können.](compliance-manager.md) MCCA ist ein PowerShell-basiertes Hilfsprogramm, das die aktuellen Konfigurationen Ihrer Organisation abruft und anhand der von Microsoft 365 empfohlenen bewährten Methoden überprüft. Diese bewährten Methoden basieren auf einer Reihe von Kontrollen, die wichtige Bestimmungen und Standards für Datenschutz und Datenkontrolle enthalten.

MIT MCCA können Sie schnell erkennen, welche Verbesserungsmaßnahmen im Compliance-Manger für Ihre aktuelle Microsoft 365-Umgebung gelten. Jede von MCCA identifizierte Aktion enthält Empfehlungen für die Implementierung mit direkten Links zum Compliance-Manager und der entsprechenden Lösung, um korrekturmaßnahmen zu ergreifen.

Eine weitere Ressource zum Verständnis von MCCA finden Sie in den [README-Anweisungen auf GitHub.](https://github.com/OfficeDev/MCCA#overview) Diese Seite enthält ausführliche Informationen zu den Voraussetzungen und vollständige Installationsanweisungen. Sie benötigen kein GitHub-Konto, um auf diese Seite zu zugreifen.

**Verfügbarkeit:** MCCA ist für alle Organisationen mit Office 365- und Microsoft 365-Lizenzen und Kunden der US Government Community (GCC) Moderate verfügbar, und es ist geplant, den Dienst auf GCC -High-Kunden zu erweitern.

## <a name="install-mcca-and-run-a-report"></a>Installieren von MCCA und Ausführen eines Berichts

Sie können das Tool MCCA mithilfe von Windows PowerShell. Nachdem Sie das Tool heruntergeladen und installiert haben, müssen Sie diese Schritte nicht wiederholen, um Berichte ausführen zu können. Jedes Mal, wenn Sie MCCA öffnen, werden Sie nach Ihren Anmeldeinformationen gefragt, und es wird ein neuer, aktualisierter Bericht generiert.

#### <a name="step-1-install-windows-powershell"></a>Schritt 1: Installieren Windows PowerShell
Zunächst benötigen Sie das Exchange Online -PowerShell-Modul (v2.0.3 oder höher), das im PowerShell-Katalog verfügbar ist. [Installationsanweisungen erhalten.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>Schritt 2: Installieren von MCCA

Um MCCA zu installieren, verwenden Sie PowerShell im Administratormodus. Führen Sie die folgenden Schritte aus:

1. Wählen Sie die **Windows-Startschaltfläche** aus.
2. Geben **Sie PowerShell** ein, klicken Sie **mit der rechten Maustaste auf Windows PowerShell** und wählen Sie dann **"Als Administrator ausführen" aus.**
1. Geben Sie an der Eingabeaufforderung Folgendes ein:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Schritt 3: Ausführen eines Berichts

Nach der Installation von MCCA können Sie MCCA ausführen und einen Bericht generieren. So führen Sie einen Bericht aus:

1. Öffnen von PowerShell
2. Führen Sie das Cmdlet aus:

    ```powershell
    Get-MCCAReport
    ```
3. Sobald MCCA ausgeführt wird, führt es eine anfängliche Versionsprüfung durch und fordert Anmeldeinformationen an. Melden Sie sich an der Eingabeaufforderung für den Benutzernamen mit Ihrer Microsoft 365-Konto-E-Mail-Adresse an (zeigen Sie die Rollen an, die zum Erstellen von[Berichten berechtigt sind).](#role-based-reporting) Geben Sie dann Ihr Kennwort an der Kennwortaufforderung ein.

Die Generierung des Berichts dauert dann ca. 2 bis 5 Minuten. Wenn sie fertig ist, wird ein Browserfenster geöffnet, in dem Ihr HTML-Bericht angezeigt wird. Jedes Mal, wenn Sie das Tool ausführen, fordert es Ihre Anmeldeinformationen an und generiert einen neuen Bericht. Dieser Bericht wird lokal im folgenden Verzeichnis gespeichert:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Sie können über dieses Verzeichnis auf zuvor generierte Berichte zugreifen.

## <a name="understanding-your-report"></a>Grundlegendes zu Ihrem Bericht

Ihr Bericht spiegelt Daten basierend auf dem Datum und der Uhrzeit wider, zu der er generiert wurde. Der obere Abschnitt enthält Details dazu, wann er generiert wurde, den Namen Ihrer Organisation und die Mandanten-ID.

#### <a name="geolocation-based-reporting"></a>Geolocation-basierte Berichterstellung

Der **Abschnitt** "Hinweis" zeigt, dass Ihr Bericht basierend auf dem geografischen Standort Ihres Mandanten angepasst wird. Die im Tool aufgeführten Empfehlungen sind spezifisch für Ihr Land oder Ihre Region.

Ihre Geolocationauswahl wird verwendet, um vertrauliche Informationstypen (SITs) zu bewerten, die für diesen Geolocation relevant sind, und einen Bericht zu generieren, der an Ihrem Land oder Ihrer Region ausgerichtet ist. Wählen Sie Geolocations basierend auf daten, die Sie in Ihrem Mandanten haben.

Um die Standortinformationen Ihres Berichts zu ändern, müssen Sie einen Geolocation-Eingabeparameter (-Geo) angeben. Sie können einen oder mehrere geografische Standorte auswählen, die für Ihren Mandanten gelten.

Führen Sie anhand der folgenden Anweisungen einen Bericht basierend auf einem bestimmten Speicherort aus:

1. Öffnen von PowerShell
2. Um eine bestimmte Region anzugeben, führen Sie ein Cmdlet mit den Nummern aus der folgenden Tabelle aus, die dem Land oder der Region entsprechen. Geben Sie mehrere Zahlen ein, indem Sie sie durch ein Komma trennen. Beispielsweise wird mit dem folgenden Cmdlet ein angepasster Bericht für Asia-Pacific und Japan ausgeführt:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  Land oder Region | 
  | :------------- | :------------: |
  | 1  | Asien-Pazifik |
  | 2  | Australien |
  | 3  | Kanada |
  | 4  | Europa (ohne Frankreich) /Naher Osten/Afrika |
  | 5  | Frankreich |
  | 6  | Indien |
  | 7  | Japan |
  | 8  | Korea |
  | 9  | Nordamerika (ohne Kanada) |
  | 10  | Südamerika |
  | 11  | Südafrika |
  | 12  | Schweiz |
  | 13  | Vereinigte Arabische Emirate |
  | 14  | Vereinigtes Königreich |


 > [!NOTE]
> Der Bericht enthält immer mcCA unterstützte internationale Typen vertraulicher Informationen wie SWIFT-Code, Kreditkartennummer usw.

#### <a name="role-based-reporting"></a>Rollenbasierte Berichterstellung

Ihr Bericht wird auch basierend auf Ihrer Rolle angepasst.

Die folgende Tabelle zeigt, welche Rollen Zugriff auf welche Abschnitte des Berichts haben. Andere Rollen in Ihrer Organisation (nicht in der folgenden Tabelle aufgeführt) können das Tool möglicherweise nicht ausführen, oder sie führen das Tool aus und haben eingeschränkten Zugriff auf Informationen im Abschlussbericht.

![MCCA – Rollen](../media/compliance-manager-mcca-roles.png "MCCA-Rollen")

Ausnahmen:
1. Der Benutzer kann unabhängig vom Abschnitt "Verwenden von IRM für Exchange Online" keinen Bericht für die IP generieren.
2. Der Benutzer kann unabhängig vom Abschnitt "Verwenden von IRM für Exchange Online" einen Bericht für die IP generieren.
3. Der Benutzer kann unabhängig vom Abschnitt "Aktivieren der Kommunikationskonformität in O365" einen Bericht für IP generieren.
4. Der Benutzer kann unabhängig vom Abschnitt "Aktivieren der Überwachung in Office 365" keinen Bericht für die IP generieren.
5. Der Benutzer kann unabhängig vom Abschnitt "Aktivieren der Überwachung in Office 365" einen Bericht für die IP generieren.

#### <a name="solutions-summary-section"></a>Abschnitt "Lösungszusammenfassung"

Der **Abschnitt "Lösungszusammenfassung"** des Berichts bietet eine Übersicht über Verbesserungsmaßnahmen, die Ihre Organisation im Compliance-Manager ergreifen kann, um Ihre Compliance zu verbessern.

![MCCA – Lösungszusammenfassung](../media/compliance-manager-mcca-solutions.png "Bildschirm "MCCA Solutions Summary"")

MCCA wertet Ihre aktuellen Konfigurationen mit den empfohlenen Verbesserungsmaßnahmen im Compliance-Manager aus. Alle Verbesserungsmaßnahmen, die vom Tool MCCA als handlungserf?nlich identifiziert werden, werden in diesem Abschnitt aufgeführt.

Neben jeder Microsoft-Lösung befinden sich farblich codierte Felder, die die Anzahl der Elemente angeben, die Verbesserungsmaßnahmen im Compliance-Manager entsprechen. Die Aktionen sind in drei Statuszustände aufgeschlüsselt:

- **OK:** Die Aktionen, die die empfohlenen Bedingungen erfüllen und zu diesem Zeitpunkt keine Aufmerksamkeit erfordern
- **Verbesserung:** Aktionen, die Aufmerksamkeit erfordern
- **Empfehlung:** Aktionen, die keine Aufmerksamkeit erfordern, für die wir jedoch bewährte Methoden empfehlen
 
Wählen Sie ein Feld aus, in dem Verbesserungen und Empfehlungen angezeigt werden.

**Elemente mit dem Verbesserungsstatus**

Wählen Sie die Dropdownliste neben der **Verbesserungsbezeichnung** rechts neben der Verbesserungsaktion aus. Es wird eine kurze Zusammenfassung und Details zu Ihren aktuellen Einstellungen und den empfohlenen Verbesserungsmaßnahmen angezeigt. Die Zusammenfassung enthält direkte Links zum Compliance-Manager, die entsprechende Lösung im Microsoft 365 Compliance Center und relevante Dokumentation.

Durch Klicken auf den Link "Compliance-Manager" erhalten Sie eine gefilterte Ansicht aller Verbesserungsmaßnahmen innerhalb dieser Lösung, die Sie noch nicht implementiert haben. Von dort aus können Sie die Anzahl der Punkte sehen, die Sie erreichen können, um Ihre Compliancebewertung zu [erhöhen,](compliance-score-calculation.md)und die Bewertungen, auf die sie angewendet werden, sowie die anwendbaren Bestimmungen und Zertifizierungen.

Für DLP gibt es  eine Schaltfläche "Korrekturskript", mit der Sie ein vorab generiertes PowerShell-Skript basierend auf den empfohlenen Empfehlungen erhalten. Sie können es direkt in Ihre PowerShell-Konsole kopieren und einfügen. Es erstellt eine DLP-Richtlinie im Testmodus.

**Elemente mit Empfehlungsstatus**

Wählen Sie das Dropdown neben der **Empfehlungsbezeichnung** rechts neben der Verbesserungsaktion aus. Es wird eine Zusammenfassung der aktuellen Microsoft 365-Umgebung Ihrer Organisation im Zusammenhang mit der Verbesserungsaktion sowie empfohlene bewährte Methoden angezeigt.

## <a name="resources"></a>Ressourcen

Ausführlichere Informationen zum Installieren, Einrichten und Verwenden von MCCA finden Sie in den [README-Anweisungen](https://github.com/OfficeDev/MCCA#overview) auf GitHub (kein GitHub-Konto erforderlich).

Weitere Informationen zu Windows PowerShell finden Sie unter ["Verwenden der PowerShell-Dokumentation".](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7) Siehe auch [Start Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
