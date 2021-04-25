---
title: Neues in Microsoft Defender for Endpoint auf Mac
description: Erfahren Sie mehr über die wichtigsten Änderungen für frühere Versionen von Microsoft Defender for Endpoint auf Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, macos, whatsnew
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a1e07ac2e2e544605f04e9090177004db64d2f04
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2021
ms.locfileid: "51994997"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Neues in Microsoft Defender for Endpoint auf Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> Unter macOS 11 (Big Sur) erfordert Microsoft Defender for Endpoint zusätzliche Konfigurationsprofile. Wenn Sie ein vorhandenes Kunden-Upgrade von früheren Versionen von macOS sind, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die auf dieser [Seite aufgeführt sind.](mac-sysext-policies.md)

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- Fix, um den Ablauf des Apple-Zertifikats für macOS Catalina und früher zu verwenden. Mit diesem Fix wird die & (Vulnerability Management, TVM) von Bedrohungen wiederhergestellt.

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender for Endpoint auf macOS ist jetzt in der Vorschau für Us Government-Kunden verfügbar. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint for US Government customers](gov.md).
- Leistungsverbesserungen (insbesondere für die Situation, in der die & verwendet wird) & Fehlerbehebungen.

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können. Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> Die alte Befehlszeilentoolsyntax ist mit dieser Version veraltet. Informationen zur neuen Syntax finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).

- Es wurde ein neuer Befehlszeilenschalter hinzugefügt, um die Netzwerkerweiterung zu deaktivieren: `mdatp system-extension network-filter disable` . Dieser Befehl kann hilfreich sein, um Netzwerkprobleme zu beheben, die mit Microsoft Defender for Endpoint auf Dem Mac in Zusammenhang stehen könnten.
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Fehlerbehebungen

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Verbesserte Zuverlässigkeit des Agents bei der Ausführung unter macOS 11 Big Sur
- Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Bedingungen wurden entfernt, als Microsoft Defender for Endpoint einen macOS 11 (Big Sur)-Fehler auslöste, der sich in einer Kernelpanik manifestierte.
- Behebung eines Speicherverlusts in der Endpunktsicherheitssystemerweiterung bei der Ausführung auf mac 11 (Big Sur)
- Fehlerbehebungen

## <a name="1011072"></a>101.10.72

- Fehlerbehebungen

## <a name="1010961"></a>101.09.61

- Neue verwaltete Einstellung zum Deaktivieren der Option [zum Senden von Feedback hinzugefügt](mac-preferences.md#show--hide-option-to-send-feedback)
- Das Statusmenüsymbol zeigt jetzt einen fehlerfreien Status an, wenn die Produkteinstellungen verwaltet werden. Zuvor wurde im Statusmenüsymbol ein Warnungs- oder Fehlerstatus angezeigt, obwohl die Produkteinstellungen vom Administrator verwaltet wurden.
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010950"></a>101.09.50

- Diese Produktversion wurde unter macOS Big Sur 11 Beta 9 überprüft.

- Die neue Syntax für `mdatp` das Befehlszeilentool ist jetzt die Standardsyntax. Weitere Informationen zur neuen Syntax finden Sie unter [Ressourcen für Microsoft Defender for Endpoint auf macOS.](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > Die alte Befehlszeilentoolsyntax wird am **1. Januar 2021** aus dem Produkt entfernt.

- Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010949"></a>101.09.49

- Verbesserungen der Benutzeroberfläche zur Unterscheidung von Vom IT-Administrator verwalteten Ausschlüssen und vom lokalen Benutzer definierten Ausschlüssen
- Verbesserte CPU-Auslastung bei Bedarfsscans
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010723"></a>101.07.23

- Neue Felder zur Ausgabe von hinzugefügt, um den Status des passiven Modus und die `mdatp --health` EDR-Gruppen-ID zu überprüfen

  > [!NOTE]
  > `mdatp --health` wird in einem `mdatp health` zukünftigen Produktupdate ersetzt.

- Fehler behoben, bei dem die automatische Beispielübermittlung auf der Benutzeroberfläche nicht als verwaltet gekennzeichnet wurde
- Neue Einstellungen zum Steuern der Aufbewahrung von Elementen im Antivirusscanverlauf hinzugefügt. Sie können jetzt [die Anzahl der](mac-preferences.md#antivirus-scan-history-retention-in-days) Tage angeben, die Elemente im Überprüfungsverlauf beibehalten werden sollen, und die maximale Anzahl von Elementen im [Scanverlauf angeben.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Fehlerbehebungen

## <a name="1010663"></a>101.06.63

- Es wurde eine Leistungsregression behoben, die in Version eingeführt `101.05.17` wurde. Die Regression wurde mit dem Fix eingeführt, um die Kernelpaniken zu beseitigen, die einige Kunden beim Zugriff auf SMB-Freigaben beobachtet haben. Wir haben diese Codeänderung wiederhergestellt und untersuchen alternative Möglichkeiten, um die Kernelpaniken zu beseitigen.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> Wir arbeiten an einer neuen und erweiterten Syntax für das `mdatp` Befehlszeilentool. Die neue Syntax ist derzeit die Standardeinstellung in den Kanälen Insider Fast und Insider Slow Update. Wir empfehlen Ihnen, sich mit dieser neuen Syntax vertraut zu machen.
> 
> Wir werden die alte Syntax parallel zur neuen Syntax weiterhin unterstützen und in den kommenden Monaten mehr Kommunikation rund um den Veralteten Plan für die alte Syntax bereitstellen.

- Es wurde eine Kernelpanik behoben, die manchmal beim Zugriff auf SMB-Dateifreigaben aufgetreten ist
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010516"></a>101.05.16

- Verbesserungen bei der Schnellscanlogik, um die Anzahl der gescannten Dateien erheblich zu reduzieren
- Unterstützung [für die automatische Vervollständigung](mac-resources.md#how-to-enable-autocompletion) für das Befehlszeilentool hinzugefügt
- Fehlerbehebungen

## <a name="1010312"></a>101.03.12

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010154"></a>101.01.54

- Verbesserungen bei der Kompatibilität mit dem Zeitcomputer
- Verbesserungen bei der Barrierefreiheit
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010031"></a>101.00.31

- Verbesserte [Produkt-Onboarding-Erfahrung für Intune-Benutzer](https://docs.microsoft.com/mem/intune/apps/apps-advanced-threat-protection-macos)
- [Antivirusausschlüsse unterstützen jetzt Platzhalter](mac-exclusions.md#supported-exclusion-types)
- Die Möglichkeit zum Auslösen von Antivirenscans aus dem kontextbezogenen MacOS-Menü wurde hinzugefügt. Sie können nun mit der rechten Maustaste auf eine Datei oder einen Ordner im Finder klicken und **mit Microsoft Defender for Endpoint scannen auswählen.**
- In-Place-Produktabstufungen werden nun vom Installationsprogramm explizit nicht mehr zugelassen. Wenn Sie ein Downgrade benötigen, deinstallieren Sie zuerst die vorhandene Version, und konfigurieren Sie Ihr Gerät neu.
- Weitere Leistungsverbesserungen & Fehlerbehebungen

## <a name="1009027"></a>100.90.27

- Sie können jetzt [einen Updatekanal](mac-updates.md#set-the-channel-name) für Microsoft Defender for Endpoint unter macOS festlegen, der sich vom systemweiten Updatekanal ab unterscheiden kann.
- Symbol für neues Produkt
- Weitere Verbesserungen bei der Benutzeroberfläche
- Fehlerbehebungen

## <a name="1008692"></a>100.86.92

- Verbesserungen bei der Kompatibilität mit dem Zeitcomputer
- Es wurde ein Problem behoben, bei dem das Produkt während der Deinstallation manchmal nicht alle Dateien `/Library/Application Support/Microsoft/Defender` unter bereinigen konnte.
- Reduzierte CPU-Auslastung des Produkts, wenn Microsoft-Produkte über Microsoft AutoUpdate aktualisiert werden
- Weitere Leistungsverbesserungen & Fehlerbehebungen

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> Um den vollständigsten Schutz für Ihre macOS-Geräte sicherzustellen und in Übereinstimmung mit Apple die Bereitstellung von systemeigenen MacOS-Sicherheitsupdates für Betriebssystemversionen zu beenden, die älter als [aktuell – 2] sind, werden MDATP für #A0 und -Updates unter macOS Sierra [10.12] nicht mehr unterstützt. MDATP für Mac-Updates und -Verbesserungen werden auf Geräten mit den Versionen Catalina [10.15], Mojave [10.14] und High Sierra [10.13] bereitgestellt. 
>
> Wenn Sie MDATP für Mac bereits auf Ihren Sierra [10.12]-Geräten bereitgestellt haben, aktualisieren Sie bitte auf die neueste macOS-Version, um risiken des Verlusts von Schutz zu vermeiden.

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1008373"></a>100.83.73

- Weitere Steuerelemente für IT-Administratoren zur Verwaltung von Ausschlüssen, zur [Verwaltung](mac-preferences.md#threat-type-settings-merge-policy)von [Bedrohungstypeinstellungen](mac-preferences.md#exclusion-merge-policy)und nicht zulässigen [Bedrohungsaktionen hinzugefügt](mac-preferences.md#disallowed-threat-actions)
- Wenn der vollständige Festplattenzugriff auf dem Gerät nicht aktiviert ist, wird jetzt im Statusmenü eine Warnung angezeigt.
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1008260"></a>100.82.60

- Es wurde ein Problem behoben, bei dem das Produkt nach einem Definitionsupdate nicht gestartet werden kann.

## <a name="1008042"></a>100.80.42

- Fehlerbehebungen

## <a name="1007942"></a>100.79.42

- Es wurde ein Problem behoben, bei dem Microsoft Defender for Endpoint auf Dem Mac manchmal mit dem Zeitcomputer ins Spiel kam.
- Neue Option zum Befehlszeilenprogramm zum Testen der Konnektivität mit dem Back-End-Dienst hinzugefügt
  ```bash
  mdatp connectivity test
  ```
- Möglichkeit zum Anzeigen des vollständigen Bedrohungsverlaufs auf der Benutzeroberfläche hinzugefügt (kann über die Ansicht **Schutzverlauf zugegriffen** werden)
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1007215"></a>100.72.15

- Fehlerbehebungen

## <a name="1007099"></a>100.70.99

- Es wurde ein Problem behoben, das sich auf die Fähigkeit einiger Benutzer aus wirkt, ein Upgrade auf macOS Catalina zu ermöglichen, wenn der Echtzeitschutz aktiviert ist. Dieses sporadische Problem wurde durch sperrende Dateien von Microsoft Defender for Endpoint innerhalb des Catalina-Upgradepakets verursacht, während sie auf Bedrohungen gescannt wurden, was zu Fehlern in der Upgradesequenz führte.

## <a name="1006899"></a>100.68.99

- Die Möglichkeit zum Konfigurieren der Antivirenfunktionen für die Ausführung im [passiven Modus wurde hinzugefügt.](mac-preferences.md#enable--disable-passive-mode)
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1006528"></a>100.65.28

- Unterstützung für macOS Catalina hinzugefügt

  > [!CAUTION]
  > macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzverbesserungen. Ab dieser Version können Anwendungen standardmäßig ohne ausdrückliche Zustimmung nicht auf bestimmte Speicherorte auf dem Datenträger zugreifen (z. B. Dokumente, Downloads, Desktop usw.). In Ermangelung dieser Zustimmung kann Microsoft Defender for Endpoint Ihr Gerät nicht vollständig schützen.
  >
  > Der Mechanismus für die Erteilung dieser Zustimmung hängt davon ab, wie Sie Microsoft Defender for Endpoint bereitgestellt haben:
  >
  > - Manuelle Bereitstellungen finden Sie in den aktualisierten Anweisungen im [Thema Manuelle](mac-install-manually.md#how-to-allow-full-disk-access) Bereitstellung.
  > - Informationen zu verwalteten Bereitstellungen finden Sie in den aktualisierten Anweisungen in den [Themen JAMF-basierte](mac-install-with-jamf.md) Bereitstellung und [Microsoft Intune-basierte Bereitstellung.](mac-install-with-intune.md#create-system-configuration-profiles)

- Leistungsverbesserungen & Fehlerbehebungen
