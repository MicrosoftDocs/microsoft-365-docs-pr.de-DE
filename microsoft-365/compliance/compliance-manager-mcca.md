---
title: Microsoft Compliance Configuration Analyzer for Compliance Manager
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
description: Erfahren Sie, wie Sie Microsoft Compliance Configuration Analyzer verwenden, um mit Microsoft Compliance Manager schnell in Betrieb zu gehen.
ms.openlocfilehash: 5d74d9980daf7f6ff7f013578cb11be83d18948e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244636"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Microsoft Compliance Configuration Analyzer for Compliance Manager (Vorschau)

**In diesem Artikel:** Erfahren Sie, wie Sie das Microsoft Compliance Configure Analyzer-Tool installieren und ausführen, um schnell mit Microsoft Compliance Manger zu beginnen.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Übersicht über Microsoft Compliance Configuration Analyzer (MCCA) (Vorschau)

Die Microsoft Compliance Configuration Analyzer (MCCA) ist ein Vorschautool, mit dem Sie mit [Microsoft Compliance Manager beginnen können.](compliance-manager.md) MCCA ist ein PowerShell-basiertes Hilfsprogramm, das die aktuellen Konfigurationen Ihrer Organisation abruft und anhand der empfohlenen Microsoft 365 überprüft. Diese bewährten Methoden basieren auf einer Reihe von Kontrollen, die wichtige Vorschriften und Standards für Datenschutz und Datenkontrolle enthalten.

MCCA kann Ihnen dabei helfen, schnell zu erkennen, welche Verbesserungsmaßnahmen im Compliance Manager für Ihre aktuelle Umgebung Microsoft 365 sind. Jede von MCCA identifizierte Aktion gibt Ihnen Empfehlungen für die Implementierung, mit direkten Links zum Compliance Manager und der entsprechenden Lösung, um Korrekturmaßnahmen zu ergreifen.

Eine weitere Ressource zum Verständnis von MCCA ist der Besuch der [README-Anweisungen auf GitHub.](https://github.com/OfficeDev/MCCA#overview) Diese Seite enthält detaillierte Informationen zu den Voraussetzungen und enthält vollständige Installationsanweisungen. Sie benötigen kein GitHub, um auf diese Seite zu zugreifen.

**Verfügbarkeit**: MCCA ist für alle Organisationen mit Office 365- und Microsoft 365-Lizenzen und Kunden des US Government Community (GCC) Moderate, GCC High und Department of Defense (DoD) verfügbar.

## <a name="install-mcca-and-run-a-report"></a>Installieren von MCCA und Ausführen eines Berichts

Sie können das MCCA-Tool mithilfe von Windows PowerShell. Nachdem Sie das Tool heruntergeladen und installiert haben, müssen Sie diese Schritte nicht wiederholen, um Berichte ausführen zu können. Jedes Mal, wenn Sie MCCA öffnen, werden Sie nach Ihren Anmeldeinformationen gefragt, und es wird ein neuer, aktualisierter Bericht generiert.

#### <a name="step-1-install-windows-powershell"></a>Schritt 1: Installieren Windows PowerShell
Zu Beginn benötigen Sie das Exchange Online PowerShell-Modul (v2.0.3 oder höher), das im PowerShell-Katalog verfügbar ist. [Installationsanweisungen erhalten](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).

#### <a name="step-2-install-mcca"></a>Schritt 2: Installieren von MCCA

Um MCCA zu installieren, verwenden Sie zunächst PowerShell im Administratormodus. Führen Sie die folgenden Schritte aus:

1. Wählen Sie die Windows **Startschaltfläche** aus.
2. Geben **Sie PowerShell ein,** klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie dann Als Administrator ausführen **aus.**
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

   Wenn Sie ein GCC Kunden sind, müssen Sie einen zusätzlichen Eingabeparameter angeben, um den Bericht ausführen zu können:

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. Sobald MCCA ausgeführt wird, wird eine erste Version überprüft und nach Anmeldeinformationen gefragt. Melden Sie sich an der Eingabeaufforderung für den Benutzernamen mit Ihrer Microsoft 365 E-Mail-Adresse ihres Kontos an ( zeigen Sie die Zum Erstellen von Berichten berechtigten Rollen[an).](#role-based-reporting) Geben Sie dann Ihr Kennwort an der Kennwortaufforderung ein.

Der Bericht dauert dann ca. 2 bis 5 Minuten. Wenn sie fertig ist, wird ein Browserfenster geöffnet und Ihr HTML-Bericht angezeigt. Jedes Mal, wenn Sie das Tool ausführen, werden Ihre Anmeldeinformationen gefragt und ein neuer Bericht generiert. Dieser Bericht wird lokal im folgenden Verzeichnis gespeichert:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Sie können auf zuvor generierte Berichte aus diesem Verzeichnis zugreifen.

## <a name="understanding-your-report"></a>Grundlegendes zu Ihrem Bericht

Ihr Bericht spiegelt Daten basierend auf dem Datum und der Uhrzeit wider, zu der er generiert wurde. Der obere Abschnitt enthält Details dazu, wann sie generiert wurde, Ihren Organisationsnamen und die Mandanten-ID.

#### <a name="geolocation-based-reporting"></a>Geolocationbasierte Berichterstellung

Der **Abschnitt Note** zeigt, dass Ihr Bericht basierend auf dem geografischen Standort Ihres Mandanten angepasst wird. Empfehlungen, die im Tool aufgeführt sind, ist für Ihr Land oder Ihre Region spezifisch.

Ihre Geolocationauswahl wird verwendet, um typen von vertraulichen Informationen (SENSITIVE Information Types, SITs) zu bewerten, die für diese Geolocation relevant sind, und einen Bericht zu generieren, der an Ihrem Land oder Ihrer Region ausgerichtet ist. Wählen Sie Geolocations basierend auf Daten aus, die Sie in Ihrem Mandanten haben.

Um die Standortinformationen Ihres Berichts zu ändern, müssen Sie einen Eingabeparameter für geolocation (-Geo) angeben. Sie können entweder einen oder mehrere geolocations auswählen, die für Ihren Mandanten gelten.

Führen Sie die folgenden Anweisungen aus, um einen Bericht basierend auf einem bestimmten Speicherort ausführen zu können:

1. Öffnen von PowerShell
2. Um eine bestimmte Region anzugeben, führen Sie ein Cmdlet mit den Zahlen aus der folgenden Tabelle aus, die dem Land oder der Region entsprechen. Geben Sie mehrere Zahlen ein, indem Sie sie durch ein Komma trennen. Mit dem cmdlet unten wird beispielsweise ein angepasster Bericht für Asia-Pacific und Japan ausgeführt:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  Land oder Region | 
  | :------------- | :------------: |
  | 1 | Asien-Pazifik |
  | 2 | Australien |
  | 3 | Kanada |
  | 4  | Europa (ohne Frankreich) / Naher Osten /Afrika |
  | 5  | Frankreich |
  | 6  | Indien |
  | 7  | Japan |
  | 8  | Korea |
  | 9  | Nordamerika (ohne Kanada) |
  | 10 | Südamerika |
  | 11 | Südafrika |
  | 12  | Schweiz |
  | 13 | Vereinigte Arabische Emirate |
  | 14  | Vereinigtes Königreich |


 > [!NOTE]
> Der Bericht enthält immer MCCA unterstützte internationale Typen vertraulicher Informationen wie SWIFT-Code, Kreditkartennummer usw.

#### <a name="role-based-reporting"></a>Rollenbasierte Berichterstellung

Ihr Bericht wird auch basierend auf Ihrer Rolle angepasst.

Die folgende Tabelle zeigt, welche Rollen Zugriff auf welche Abschnitte des Berichts haben. Andere Rollen in Ihrer Organisation (nicht in der folgenden Tabelle aufgeführt) können das Tool möglicherweise nicht ausführen, oder sie führen das Tool aus und haben eingeschränkten Zugriff auf Informationen im Abschlussbericht.

![MCCA – Rollen](../media/compliance-manager-mcca-roles.png "MCCA-Rollen")

Ausnahmen:
1. Benutzer können keinen Bericht für IP generieren, abgesehen vom Abschnitt "Verwenden von IRM für Exchange Online".
2. Benutzer können den Bericht für IP außerhalb des Abschnitts "Verwenden von IRM für Exchange Online" generieren.
3. Benutzer können unabhängig vom Abschnitt "Kommunikationskonformität in O365 aktivieren" berichte für IP generieren.
4. Benutzer können keinen Bericht für IP generieren, abgesehen vom Abschnitt "Überwachung in Office 365 aktivieren".
5. Benutzer können einen Bericht für IP generieren, abgesehen vom Abschnitt "Überwachung in Office 365 aktivieren".

#### <a name="solutions-summary-section"></a>Abschnitt "Lösungszusammenfassung"

Im **Abschnitt Lösungszusammenfassung** des Berichts finden Sie eine Übersicht über Verbesserungsmaßnahmen, die Ihre Organisation im Compliance Manager ergreifen kann, um Ihre Compliancehaltung zu verbessern.

![MCCA – Lösungszusammenfassung](../media/compliance-manager-mcca-solutions.png "Zusammenfassungsbildschirm für MCCA-Lösungen")

MCCA wertet Ihre aktuellen Konfigurationen mit den empfohlenen Verbesserungsmaßnahmen im Compliance Manager aus. Alle Verbesserungsmaßnahmen, die vom MCCA-Tool als aufmerksamkeitserregend identifiziert werden, werden in diesem Abschnitt aufgeführt.

Neben jeder Microsoft-Lösung befinden sich farblich codierte Felder, die die Anzahl der Elemente angeben, die Verbesserungsmaßnahmen im Compliance-Manager entsprechen. Die Aktionen sind in drei Statuszustände aufgeschlüsselt:

- **OK**: Die Aktionen, die die empfohlenen Bedingungen erfüllen und zurzeit keine Aufmerksamkeit benötigen
- **Verbesserung**: Aktionen, die Aufmerksamkeit erfordern
- **Empfehlung**: Aktionen, die keine Aufmerksamkeit erfordern, für die wir jedoch bewährte Methoden empfehlen
 
Wählen Sie ein Feld aus, um Verbesserungen und Empfehlungen anzeigen zu können.

**Elemente mit dem Verbesserungsstatus**

Wählen Sie das Dropdown neben der **Bezeichnung Verbesserung** rechts neben der Verbesserungsaktion aus. Sie sehen eine kurze Zusammenfassung und Details zu Ihren aktuellen Einstellungen und den empfohlenen Verbesserungsmaßnahmen. Die Zusammenfassung enthält direkte Links zum Compliance Manager, die entsprechende Lösung im Microsoft 365 Compliance Center und relevante Dokumentation.

Durch Klicken auf den Link Compliance-Manager erhalten Sie eine gefilterte Ansicht aller Verbesserungsmaßnahmen innerhalb dieser Lösung, die Sie noch nicht implementiert haben. Von dort aus können Sie die Anzahl der Punkte sehen, die Sie erreichen können, um Ihre Compliancebewertung zu [erhöhen,](compliance-score-calculation.md)und die Bewertungen, auf die sie angewendet werden, sowie die anwendbaren Vorschriften und Zertifizierungen.

Für DLP gibt es eine Schaltfläche **"Korrekturskript",** mit der Sie ein vorab generiertes PowerShell-Skript basierend auf den empfohlenen Empfehlungen erhalten. Sie können sie direkt in Ihre PowerShell-Konsole kopieren und einfügen. Es erstellt eine DLP-Richtlinie im Testmodus

**Elemente mit Empfehlungsstatus**

Wählen Sie das Dropdown neben der **Empfehlungsbezeichnung** rechts neben der Verbesserungsaktion aus. Es wird eine Zusammenfassung der aktuellen Umgebung Microsoft 365 Ihrer Organisation im Zusammenhang mit der Verbesserungsaktion sowie empfohlene bewährte Methoden angezeigt.

## <a name="resources"></a>Ressourcen

Ausführlichere Informationen zum Installieren, Einrichten und Verwenden von MCCA finden Sie in den [README-Anweisungen](https://github.com/OfficeDev/MCCA#overview) zu GitHub (kein GitHub erforderlich).

Weitere Informationen zu Windows PowerShell finden Sie unter [Verwenden der PowerShell-Dokumentation](/powershell/scripting/how-to-use-docs?view=powershell-7). Siehe auch [Starten Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
