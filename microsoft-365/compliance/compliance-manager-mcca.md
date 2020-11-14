---
title: Microsoft Compliance Configuration Analyzer für Compliance-Manager
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
description: Hier erfahren Sie, wie Sie Microsoft Compliance Configuration Analyzer verwenden, um mit Microsoft Compliance Manager schnell aufzutreten und zu starten.
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49072004"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a>Microsoft Compliance Configuration Analyzer für Compliance-Manager

**In diesem Artikel:** In diesem Artikel erfahren Sie, wie Sie das Microsoft Compliance configure Analyzer-Tool installieren und ausführen, damit Sie schnell mit Microsoft Compliance-Manager beginnen können.

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a>Microsoft Compliance Configuration Analyzer (MCCA) (Übersicht)

Der Microsoft Compliance Configuration Analyzer (MCCA) ist ein Tool, mit dem Sie die ersten Schritte mit dem [Microsoft Compliance-Manager](compliance-manager.md)beginnen können. MCCA ist ein PowerShell-basiertes Dienstprogramm, das die aktuellen Konfigurationen Ihres Unternehmens abruft und diese gegen die empfohlenen bewährten Methoden von Microsoft 365 überprüft. Diese bewährten Methoden basieren auf einer Reihe von Steuerelementen, die wichtige Regeln und Standards für den Datenschutz und die Datensteuerung enthalten.

Mithilfe von MCCA können Sie schnell erkennen, welche Verbesserungs Aktionen in Compliance Manger für Ihre aktuelle Microsoft 365-Umgebung gelten. Jede von MCCA identifizierte Aktion gibt Ihnen Empfehlungen für die Implementierung, mit direkten Links zum Compliance-Manager und der entsprechenden Lösung, um mit der Korrekturmaßnahmen zu beginnen.

Eine zusätzliche Ressource für das Verständnis von MCCA finden Sie in der [Readme-Anleitung auf GitHub](https://github.com/OfficeDev/MCCA#overview). Diese Seite enthält detaillierte Informationen zu den Voraussetzungen und bietet vollständige Installationsanweisungen. Für den Zugriff auf diese Seite benötigen Sie kein GitHub-Konto.

## <a name="install-mcca-and-run-a-report"></a>Installieren von MCCA und Ausführen eines Berichts

Sie können das MCCA-Tool mit Windows PowerShell installieren. Nachdem Sie das Tool heruntergeladen und installiert haben, müssen Sie diese Schritte nicht wiederholen, um Berichte auszuführen. Jedes Mal, wenn Sie MCCA öffnen, werden Sie aufgefordert, Ihre Anmeldeinformationen einzugeben, und es wird ein neuer, aktualisierter Bericht erstellt.

#### <a name="step-1-install-windows-powershell"></a>Schritt 1: Installieren von Windows PowerShell
Zunächst benötigen Sie das Exchange Online PowerShell-Modul (v 2.0.3 oder höher), das im PowerShell-Katalog zur Verfügung steht. [Hier erhalten Sie Installationsanweisungen](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).

#### <a name="step-2-install-mcca"></a>Schritt 2: Installieren von Mcca

Um MCCA zu installieren, beginnen Sie mit PowerShell im Administratormodus. Führen Sie die folgenden Schritte aus:

1. Klicken Sie auf die Schaltfläche Windows- **Start** .
2. Geben Sie **PowerShell** ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell** , und wählen Sie dann **als Administrator ausführen** aus.
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
3. Nachdem MCCA ausgeführt wurde, wird die erste Version überprüft und nach Anmeldeinformationen gefragt. Melden Sie sich an der Eingabeaufforderung für den Benutzernamen mit der e-Mail-Adresse Ihres Microsoft 365-Kontos an ([sehen Sie sich die Rollen an, die zum Erstellen von Berichten berechtigt](#role-based-reporting)sind). Geben Sie dann Ihr Kennwort an der Eingabeaufforderung ein.

Der Bericht dauert dann etwa 2-5 Minuten, um zu generieren. Anschließend wird ein Browserfenster geöffnet, in dem der HTML-Bericht angezeigt wird. Jedes Mal, wenn Sie das Tool ausführen, werden Sie aufgefordert, Ihre Anmeldeinformationen einzugeben und einen neuen Bericht zu erstellen. Dieser Bericht wird lokal im folgenden Verzeichnis gespeichert:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Sie können über dieses Verzeichnis auf zuvor generierte Berichte zugreifen.

## <a name="understanding-your-report"></a>Grundlegendes zum Bericht

Der Bericht reflektiert Daten basierend auf dem Datum und der Uhrzeit, zu der er generiert wurde. Der obere Abschnitt enthält Details zum Zeitpunkt der Generierung, den Namen Ihrer Organisation und die Mandanten-ID.

#### <a name="geolocation-based-reporting"></a>Geolocation-basiertes Reporting

Der Abschnitt **Hinweis** zeigt, dass der Bericht basierend auf dem geografischen Standort Ihres Mandanten angepasst wird. Die im Tool aufgeführten Empfehlungen sind spezifisch für Ihr Land oder Ihre Region.

Ihre Geolocation-Auswahl wird verwendet, um vertrauliche Informationstypen (Sitzbereiche) zu bewerten, die für diese Geolocation relevant sind, und einen Bericht zu generieren, der an Ihrem Land oder Ihrer Region ausgerichtet ist. Wählen Sie geolokationen basierend auf Daten aus, die Sie in Ihrem Mandanten haben.

Um die Standortinformationen Ihres Berichts zu ändern, müssen Sie einen Geolocation (-GEO)-Eingabeparameter angeben. Sie können entweder einen oder mehrere geolokationen auswählen, die für Ihren Mandanten gelten.

Befolgen Sie diese Anweisungen, um einen Bericht basierend auf einem bestimmten Speicherort auszuführen:

1. Öffnen von PowerShell
2. Um eine bestimmte Region anzugeben, führen Sie ein Cmdlet mit den Zahlen aus der Tabelle unten aus, die dem Land oder der Region entsprechen. Geben Sie mehrere Zahlen ein, indem Sie Sie durch ein Komma voneinander trennen. Mit dem folgenden Cmdlet wird beispielsweise ein benutzerdefinierter Bericht für Asia-Pacific und Japan ausgeführt:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  Land oder Region | 
  | :------------- | :------------: |
  | 1  | Asien-Pazifik |
  | 2  | Australien |
  | 3 | Kanada |
  | 4  | Europa (ohne Frankreich)/Naher Osten/Afrika |
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
> Der Bericht enthält immer MCCA unterstützte internationale vertrauliche Informationstypen wie SWIFT-Code, Kreditkartennummer usw.

#### <a name="role-based-reporting"></a>Rollenbasierte Berichterstellung

Der Bericht wird auch basierend auf ihrer Rolle angepasst.

Die folgende Tabelle zeigt, welche Rollen Zugriff auf welche Abschnitte des Berichts haben. Andere Rollen in Ihrer Organisation (in der Tabelle unten nicht aufgeführt) können das Tool möglicherweise nicht ausführen, oder das Tool kann ausgeführt werden und nur begrenzten Zugriff auf Informationen im Abschlussbericht haben.

![MCCA-Rollen](../media/compliance-manager-mcca-roles.png "MCCA-Rollen")

Ausnahmen:
1. Der Benutzer kann keinen Bericht für IP erstellen, abgesehen von "IRM für Exchange Online verwenden"-Abschnitt.
2. Der Benutzer ist in der Lage, einen Bericht für IP zu generieren, abgesehen vom Abschnitt "Verwenden von IRM für Exchange Online".
3. Der Benutzer ist in der Lage, einen Bericht für IP zu generieren, abgesehen vom Abschnitt "Kommunikation Compliance in O365 aktivieren".
4. Der Benutzer kann im Abschnitt "Überwachung in Office 365 aktivieren" keinen Bericht für IP erstellen.
5. Der Benutzer ist in der Lage, einen Bericht für IP zu erstellen, abgesehen vom Abschnitt "Überwachung in Office 365 aktivieren".

#### <a name="solutions-summary-section"></a>Abschnitt "Lösungszusammenfassung"

Der Abschnitt " **Lösungszusammenfassung** " des Berichts enthält eine Übersicht über die Verbesserungs Aktionen, die Ihre Organisation im Compliance-Manager ausführen kann, um die Compliance-Position zu verbessern.

![Zusammenfassung der MCCA-Lösungen](../media/compliance-manager-mcca-solutions.png "Zusammenfassungsbildschirm für MCCA-Lösungen")

MCCA wertet ihre aktuellen Konfigurationen anhand der empfohlenen Verbesserungs Aktionen im Compliance-Manager aus. In diesem Abschnitt werden alle Verbesserungs Aktionen aufgelistet, die vom MCCA-Tool als Aufmerksamkeits bedürftig identifiziert werden.

Neben jeder Microsoft-Lösung befinden sich farbcodierte Felder, die die Anzahl der Elemente anzeigen, die den Verbesserungs Aktionen im Compliance-Manager entsprechen. Die Aktionen werden in drei Statuszustände aufgeteilt:

- **OK** : die Aktionen, die den empfohlenen Bedingungen entsprechen und zu diesem Zeitpunkt keine Aufmerksamkeit benötigen
- **Verbesserung** : Aktionen, die Aufmerksamkeit erfordern
- **Empfehlung** : Aktionen, für die keine Aufmerksamkeit erforderlich ist, für die jedoch bewährte Methoden empfohlen werden
 
Wählen Sie ein Feld aus, um Verbesserungen und Empfehlungen anzuzeigen.

**Elemente mit dem Verbesserungs Status**

Wählen Sie das Dropdownfeld neben der **Verbesserungs** Bezeichnung rechts neben der Verbesserungs Aktion aus. Sie sehen eine kurze Zusammenfassung und Details zu Ihren aktuellen Einstellungen und den empfohlenen Verbesserungs Aktionen. Die Zusammenfassung umfasst direkte Links in Compliance-Manager, die entsprechende Lösung im Microsoft 365 Compliance Center und relevante Dokumentation.

Durch Klicken auf den Link Compliance-Manager gelangen Sie zu einer gefilterten Ansicht aller Verbesserungs Aktionen innerhalb dieser Lösung, die Sie noch nicht implementiert haben. Von dort aus können Sie die Anzahl der Punkte anzeigen, die Sie erreichen können, um Ihre [Konformitäts](compliance-score-calculation.md)Bewertung zu verbessern, sowie die Bewertungen, die Sie anwenden, sowie die anwendbaren Vorschriften und Zertifizierungen.

Für DLP gibt es eine Schaltfläche " **Korrektur Skript** ", mit der Sie ein vorab generiertes PowerShell-Skript basierend auf den empfohlenen Funktionen erhalten. Sie können Sie direkt in Ihre PowerShell-Konsole kopieren und einfügen. Im Testmodus wird eine DLP-Richtlinie erstellt.

**Elemente mit Empfehlungs Status**

Wählen Sie das Dropdownfeld neben der **Empfehlungs** Bezeichnung rechts neben der Verbesserungs Aktion aus. Eine Zusammenfassung der aktuellen Microsoft 365-Umgebung Ihrer Organisation im Zusammenhang mit der Verbesserungs Aktion sowie empfohlene bewährte Methoden werden angezeigt.

## <a name="resources"></a>Ressourcen

Ausführlichere Informationen zum Installieren, einrichten und Verwenden von MCCA finden Sie in der [Readme-Anleitung auf GitHub](https://github.com/OfficeDev/MCCA#overview) (kein GitHub-Konto erforderlich).

Für weitere Informationen zu Windows PowerShell beginnen Sie mit [der Verwendung der PowerShell-Dokumentation](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7). Siehe auch [Start Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
