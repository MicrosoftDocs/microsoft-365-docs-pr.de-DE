---
title: Microsoft Compliance Configuration Analyzer für Compliance-Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Verstehen Sie, wie Sie Microsoft Compliance Configuration Analyzer verwenden, um schnell mit Microsoft Compliance Manager zu beginnen.
ms.openlocfilehash: 7652a53e0d63e52d92e0d0506207c28f67459029
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287053"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Microsoft Compliance Configuration Analyzer for Compliance Manager (Vorschau)

**In diesem Artikel:** Erfahren Sie, wie Sie das Tool "Microsoft Compliance Configure Analyzer" installieren und ausführen, um schnell mit Microsoft Compliance Manger zu beginnen.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Übersicht über Microsoft Compliance Configuration Analyzer (MCCA) (Vorschau)

Microsoft Compliance Configuration Analyzer (MCCA) ist ein Vorschautool, das Ihnen bei den ersten Schritten mit [Microsoft Compliance Manager](compliance-manager.md)helfen kann. MCCA ist ein PowerShell-basiertes Hilfsprogramm, das die aktuellen Konfigurationen Ihrer Organisation abruft und anhand Microsoft 365 empfohlenen bewährten Methoden überprüft. Diese bewährten Methoden basieren auf einer Reihe von Steuerelementen, die wichtige Vorschriften und Standards für Datenschutz und Datengovernance umfassen.

MCCA kann Ihnen helfen, schnell zu sehen, welche Verbesserungsmaßnahmen im Compliance-Manager für Ihre aktuelle Microsoft 365 umgebung gelten. Jede von MCCA identifizierte Aktion gibt Ihnen Empfehlungen für die Implementierung mit direkten Links zum Compliance-Manager und der entsprechenden Lösung, um korrekturmaßnahmen zu ergreifen.

Eine weitere Ressource zum Verständnis von MCCA finden Sie in den [README-Anweisungen auf GitHub](https://github.com/OfficeDev/MCCA#overview). Auf dieser Seite finden Sie ausführliche Informationen zu den erforderlichen Komponenten und vollständige Installationsanweisungen. Sie benötigen kein GitHub Konto, um auf diese Seite zugreifen zu können.

**Verfügbarkeit:** MCCA ist für alle Organisationen mit Office 365- und Microsoft 365 lizenzen sowie Kunden von US Government Community (GCC) Moderate, GCC High und Department of Defense (DoD) verfügbar.

## <a name="install-mcca-and-run-a-report"></a>Installieren von MCCA und Ausführen eines Berichts

Sie können das MCCA-Tool mit Windows PowerShell installieren. Nachdem Sie das Tool heruntergeladen und installiert haben, müssen Sie diese Schritte nicht wiederholen, um Berichte auszuführen. Jedes Mal, wenn Sie MCCA öffnen, werden Sie nach Ihren Anmeldeinformationen gefragt, und es wird ein neuer, aktualisierter Bericht generiert.

#### <a name="step-1-install-windows-powershell"></a>Schritt 1: Installieren Windows PowerShell
Zunächst benötigen Sie das Exchange Online PowerShell-Modul (v2.0.3 oder höher), das im PowerShell-Katalog verfügbar ist. [Rufen Sie Installationsanweisungen ab.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>Schritt 2: Installieren von MCCA

Um MCCA zu installieren, verwenden Sie zunächst PowerShell im Administratormodus. Führen Sie die folgenden Schritte aus:

1. Wählen Sie die Schaltfläche Windows **Start** aus.
2. Geben Sie **PowerShell** ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie dann **als Administrator ausführen** aus.
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

   Wenn Sie ein GCC High-Kunde sind, müssen Sie einen zusätzlichen Eingabeparameter angeben, um den Bericht auszuführen:

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. Sobald MCCA ausgeführt wird, führt er eine anfängliche Versionsprüfung durch und fragt nach Anmeldeinformationen. Melden Sie sich an der Eingabeaufforderung des Benutzernamens mit Ihrer Microsoft 365 Konto-E-Mail-Adresse an ([zeigen Sie die Rollen an, die berechtigt sind, Berichte zu erstellen).](#role-based-reporting) Geben Sie dann Ihr Kennwort an der Eingabeaufforderung für das Kennwort ein.

Der Bericht dauert dann ca. 2-5 Minuten, bis er generiert wird. Wenn sie fertig ist, wird ein Browserfenster geöffnet, in dem Ihr HTML-Bericht angezeigt wird. Jedes Mal, wenn Sie das Tool ausführen, werden Ihre Anmeldeinformationen angefordert und ein neuer Bericht generiert. Dieser Bericht wird lokal im folgenden Verzeichnis gespeichert:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Sie können aus diesem Verzeichnis auf zuvor generierte Berichte zugreifen.

## <a name="understanding-your-report"></a>Grundlegendes zu Ihrem Bericht

Ihr Bericht gibt Daten basierend auf dem Datum und der Uhrzeit der Generierung wieder. Der oberste Abschnitt enthält Details zum Zeitpunkt der Erstellung, zum Organisationsnamen und zur Mandanten-ID.

#### <a name="geolocation-based-reporting"></a>Geolocation-basierte Berichterstellung

Der **Abschnitt "Hinweis"** zeigt, dass Ihr Bericht basierend auf dem geografischen Standort Ihres Mandanten angepasst wird. Empfehlungen, die im Tool aufgeführt sind, sind spezifisch für Ihr Land oder Ihre Region.

Ihre Geolocation-Auswahl wird verwendet, um vertrauliche Informationstypen (SITs) zu bewerten, die für diesen Geolocation relevant sind, und um einen Bericht zu erstellen, der ihrem Land oder Ihrer Region entspricht. Wählen Sie Geolocations basierend auf daten, die Sie in Ihrem Mandanten haben.

Um die Standortinformationen Ihres Berichts zu ändern, müssen Sie einen Geolocation(-Geo)-Eingabeparameter angeben. Sie können einen oder mehrere Geolocations auswählen, die für Ihren Mandanten gelten.

Befolgen Sie die folgenden Anweisungen, um einen Bericht basierend auf einem bestimmten Speicherort auszuführen:

1. Öffnen von PowerShell
2. Um eine bestimmte Region anzugeben, führen Sie ein Cmdlet mithilfe der Nummern aus der folgenden Tabelle aus, die dem Land oder der Region entsprechen. Geben Sie mehrere Zahlen ein, indem Sie sie durch ein Komma trennen. Das folgende Cmdlet führt beispielsweise einen angepassten Bericht für Asia-Pacific und Japan aus:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  Land oder Region | 
  | :------------- | :------------: |
  | 1 | Asien-Pazifik |
  | 2 | Australien |
  | 3 | Kanada |
  | 4  | Europa (ohne Frankreich) / Naher Osten/Afrika |
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
> Der Bericht enthält immer von MCCA unterstützte internationale typen vertraulicher Informationen wie SWIFT-Code, Kreditkartennummer usw.

#### <a name="role-based-reporting"></a>Rollenbasierte Berichterstellung

Ihr Bericht wird auch basierend auf Ihrer Rolle angepasst.

Die folgende Tabelle zeigt, welche Rollen Zugriff auf welche Abschnitte des Berichts haben. Andere Rollen in Ihrer Organisation (die nicht in der folgenden Tabelle aufgeführt sind) können das Tool möglicherweise nicht ausführen, oder sie können das Tool ausführen und haben eingeschränkten Zugriff auf Informationen im Abschlussbericht.

![MCCA – Rollen](../media/compliance-manager-mcca-roles.png "MCCA-Rollen")

Ausnahmen:
1. Benutzer können keinen Bericht für die IP-Adresse außerhalb des Abschnitts "IRM für Exchange Online verwenden" generieren.
2. Benutzer können unabhängig vom Abschnitt "IRM für Exchange Online verwenden" einen Bericht für ip generieren.
3. Benutzer können unabhängig vom Abschnitt "Kommunikationscompliance in O365 aktivieren" einen Bericht für IP generieren.
4. Benutzer können keinen Bericht für IP außerhalb des Abschnitts "Überwachung in Office 365 aktivieren" generieren.
5. Benutzer können unabhängig vom Abschnitt "Überwachung in Office 365 aktivieren" einen Bericht für ip generieren.

#### <a name="solutions-summary-section"></a>Zusammenfassungsabschnitt "Lösungen"

Der Abschnitt **"Lösungszusammenfassung"** des Berichts bietet einen Überblick über Verbesserungsmaßnahmen, die Ihre Organisation im Compliance-Manager ergreifen kann, um Ihren Compliancestatus zu verbessern.

![MCCA – Lösungszusammenfassung](../media/compliance-manager-mcca-solutions.png "Zusammenfassungsbildschirm für MCCA-Lösungen")

MCCA wertet Ihre aktuellen Konfigurationen anhand der empfohlenen Verbesserungsmaßnahmen im Compliance-Manager aus. Alle Verbesserungsmaßnahmen, die vom MCCA-Tool als aufmerksamkeitsnotwendigend identifiziert werden, werden in diesem Abschnitt aufgeführt.

Neben jeder Microsoft-Lösung befinden sich farbcodierte Felder, die die Anzahl der Elemente angeben, die Verbesserungsmaßnahmen im Compliance-Manager entsprechen. Die Aktionen sind in drei Statuszustände unterteilt:

- **OK:** Die Aktionen, die die empfohlenen Bedingungen erfüllen und derzeit keine Aufmerksamkeit erfordern
- **Verbesserung:** Aktionen, die Aufmerksamkeit erfordern
- **Empfehlung:** Aktionen, die keine Aufmerksamkeit erfordern, für die wir jedoch bewährte Methoden empfehlen
 
Aktivieren Sie ein Kontrollkästchen, um Verbesserungen und Empfehlungen anzuzeigen.

**Elemente mit dem Verbesserungsstatus**

Wählen Sie die Dropdownliste neben der Bezeichnung **"Verbesserung"** rechts neben der Verbesserungsmaßnahme aus. Sie sehen eine kurze Zusammenfassung und Details zu Ihren aktuellen Einstellungen und den empfohlenen Verbesserungsmaßnahmen. Die Zusammenfassung enthält direkte Links zum Compliance-Manager, die zutreffende Lösung in der Microsoft 365 Compliance Center und die relevante Dokumentation.

Wenn Sie auf den Compliance-Manager-Link klicken, gelangen Sie zu einer gefilterten Ansicht aller Verbesserungsmaßnahmen innerhalb dieser Lösung, die Sie noch nicht implementiert haben. Von dort aus können Sie die Anzahl der Punkte sehen, die Sie erreichen können, um Ihre [Compliancebewertung](compliance-score-calculation.md)zu erhöhen, und die Bewertungen, auf die sie angewendet werden, sowie die geltenden Vorschriften und Zertifizierungen.

Für DLP gibt es eine Schaltfläche zum Beheben von **Skripts,** mit der Sie ein vorab generiertes PowerShell-Skript basierend auf den empfohlenen Anweisungen erhalten. Sie können es direkt in Ihre PowerShell-Konsole kopieren und einfügen. Es wird eine DLP-Richtlinie im Testmodus erstellt.

**Elemente mit Empfehlungsstatus**

Wählen Sie die Dropdownliste neben der **Bezeichnung "Empfehlung"** rechts neben der Verbesserungsmaßnahme aus. Sie sehen eine Zusammenfassung der aktuellen Microsoft 365 Umgebung Ihrer Organisation im Zusammenhang mit der Verbesserungsmaßnahme sowie empfohlene bewährte Methoden.

## <a name="resources"></a>Ressourcen

Ausführlichere Informationen zum Installieren, Einrichten und Verwenden von MCCA finden Sie in den [README-Anweisungen zu GitHub](https://github.com/OfficeDev/MCCA#overview) (kein GitHub Konto erforderlich).

Weitere Informationen zu Windows PowerShell finden Sie unter [Verwendung der PowerShell-Dokumentation.](/powershell/scripting/how-to-use-docs) Siehe auch [Start Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell).
