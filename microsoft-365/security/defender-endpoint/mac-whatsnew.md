---
title: Neuigkeiten in Microsoft Defender für Endpunkt auf dem Mac
description: Erfahren Sie mehr über die wichtigsten Änderungen für frühere Versionen von Microsoft Defender für Endpunkt auf dem Mac.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Mac, Installation, macos, whatsnew
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
ms.openlocfilehash: 841f22421ac81ba447dad70a68c4c7bc95605b16
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363895"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-mac"></a>Neuigkeiten in Microsoft Defender für Endpunkt auf dem Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!IMPORTANT]
> Unter macOS 11 (Big Sur) erfordert Microsoft Defender für Endpunkt zusätzliche Konfigurationsprofile. Wenn Sie bereits ein Kundenupdate von früheren Versionen von macOS durchführen, stellen Sie sicher, dass Sie die zusätzlichen Konfigurationsprofile bereitstellen, die auf [dieser Seite](mac-sysext-policies.md)aufgeführt sind.

## <a name="1013420-20121051134200"></a>101.34.20 (20.121051.13420.0)

- [Die Gerätesteuerung für macOS](mac-device-control-overview.md) ist jetzt allgemein verfügbar.
- Es wurde ein Problem behoben, bei dem ein Schnellscan nicht über das Statusmenü unter macOS 11 (Big Sur) gestartet werden konnte.
- Andere Fehlerbehebungen

## <a name="1013269-20121042132690"></a>101.32.69 (20.121042.13269.0)

- Es wurde ein Problem behoben, bei dem der gleichzeitige Zugriff auf die Schlüsselkette von Microsoft Defender für Endpunkt und anderen Anwendungen zu einer Beschädigung der Schlüsselkette führen kann.

## <a name="1012964-20121042129640"></a>101.29.64 (20.121042.12964.0)

- Ab dieser Version werden Bedrohungen, die während von Bedarfs-Antivirusscans erkannt werden, die über den Befehlszeilenclient ausgelöst werden, automatisch behoben. Bedrohungen, die während überprüfungen erkannt werden, die über die Benutzeroberfläche ausgelöst werden, erfordern weiterhin manuelle Maßnahmen.
- `mdatp diagnostic real-time-protection-statistics` Unterstützt jetzt zwei zusätzliche Switches:
  - `--sort`: sortiert die Ausgabe absteigend nach der Gesamtzahl der gescannten Dateien.
  - `--top N`: zeigt die obersten N-Ergebnisse an (funktioniert nur, wenn `--sort` auch angegeben)
- Leistungsverbesserungen (insbesondere bei Verwendung von YARN) & Fehlerbehebungen

## <a name="1012750-20121022127500"></a>101.27.50 (20.121022.12750.0)

- Behebung, um den Ablauf des Apple-Zertifikats für macOS- und frühere Versionen zu berücksichtigen. Dieser Fix stellt die Funktionen von Threat & Vulnerability Management (TVM) wieder her.

## <a name="1012569-20121022125690"></a>101.25.69 (20.121022.12569.0)

- Microsoft Defender für Endpunkt unter macOS ist jetzt in der Vorschau für Us Government-Kunden verfügbar. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt für US Government-Kunden.](gov.md)
- Leistungsverbesserungen (speziell für die Situation, in der die XCode Simulator-App verwendet wird) & Fehlerbehebungen.

## <a name="1012364-20121021123640"></a>101.23.64 (20.121021.12364.0)

- Dem Befehlszeilentool wurde eine neue Option zum Anzeigen von Informationen zum letzten On-Demand-Scan hinzugefügt. Um Informationen zum letzten On-Demand-Scan anzuzeigen, führen Sie `mdatp health --details antivirus`
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1012279-20121012122790"></a>101.22.79 (20.121012.12279.0)

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011988-20121011119880"></a>101.19.88 (20.121011.11988.0)

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011948-20120121119480"></a>101.19.48 (20.120121.11948.0)

> [!NOTE]
> Die syntax des alten Befehlszeilentools ist mit dieser Version veraltet. Informationen zur neuen Syntax finden Sie unter [Resources](mac-resources.md#configuring-from-the-command-line).

- Es wurde ein neuer Befehlszeilenschalter hinzugefügt, um die Netzwerkerweiterung zu deaktivieren: `mdatp system-extension network-filter disable` . Dieser Befehl kann hilfreich sein, um Netzwerkprobleme zu beheben, die im Zusammenhang mit Microsoft Defender für Endpunkt auf dem Mac stehen könnten.
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011921-20120101119210"></a>101.19.21 (20.120101.11921.0)

- Fehlerbehebungen

## <a name="1011526-20120102115260"></a>101.15.26 (20.120102.11526.0)

- Verbesserte Zuverlässigkeit des Agents bei der Ausführung unter macOS 11 Big Sur
- Ein neuer Befehlszeilenschalter ( `--ignore-exclusions` ) wurde hinzugefügt, um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1011375-20120101113750"></a>101.13.75 (20.120101.11375.0)

- Bedingungen entfernt, bei denen Microsoft Defender für Endpunkt einen MacOS 11(Big Sur)-Fehler auslöste, der sich in einer Kernel-Panze manifestiert
- Es wurde ein Speicherverlust in der Endpoint Security-Systemerweiterung behoben, wenn sie auf Mac 11 (Big Sur) ausgeführt wurde.
- Fehlerbehebungen

## <a name="1011072"></a>101.10.72

- Fehlerbehebungen

## <a name="1010961"></a>101.09.61

- Neue verwaltete Einstellung zum [Deaktivieren der Option zum Senden](mac-preferences.md#show--hide-option-to-send-feedback) von Feedback hinzugefügt
- Das Statusmenüsymbol zeigt jetzt einen fehlerfreien Status an, wenn die Produkteinstellungen verwaltet werden. Zuvor wurde auf dem Statusmenüsymbol ein Warnungs- oder Fehlerstatus angezeigt, obwohl die Produkteinstellungen vom Administrator verwaltet wurden.
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010950"></a>101.09.50

- Diese Produktversion wurde unter macOS Big Sur 11 Beta 9 überprüft.

- Die neue Syntax für das `mdatp` Befehlszeilentool ist jetzt die Standardsyntax. Weitere Informationen zur neuen Syntax finden Sie unter [Ressourcen für Microsoft Defender für Endpunkt unter macOS](mac-resources.md#configuring-from-the-command-line)

  > [!NOTE]
  > Die alte Befehlszeilentoolsyntax wird am **1. Januar 2021** aus dem Produkt entfernt.

- Erweitert `mdatp diagnostic create` mit einem neuen Parameter ( ), der das Speichern der `--path [directory]` Diagnoseprotokolle in einem anderen Verzeichnis ermöglicht
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010949"></a>101.09.49

- Verbesserungen der Benutzeroberfläche zur Unterscheidung von Ausschlüssen, die vom IT-Administrator verwaltet werden, und Ausschlüssen, die vom lokalen Benutzer definiert sind
- Verbesserte CPU-Auslastung bei Bedarfsscans
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010723"></a>101.07.23

- Neue Felder zur Ausgabe zur `mdatp --health` Überprüfung des Status des passiven Modus und der EDR Gruppen-ID hinzugefügt

  > [!NOTE]
  > `mdatp --health` wird `mdatp health` in einem zukünftigen Produktupdate ersetzt.

- Ein Fehler wurde behoben, bei dem die automatische Beispielübermittlung auf der Benutzeroberfläche nicht als verwaltet gekennzeichnet wurde.
- Neue Einstellungen zum Steuern der Aufbewahrung von Elementen im Antivirusscanverlauf hinzugefügt. Sie können jetzt [die Anzahl der Tage angeben, die Elemente im Scanverlauf aufbewahrt](mac-preferences.md#antivirus-scan-history-retention-in-days) werden sollen, und die maximale Anzahl von Elementen im [Scanverlauf angeben.](mac-preferences.md#maximum-number-of-items-in-the-antivirus-scan-history)
- Fehlerbehebungen

## <a name="1010663"></a>101.06.63

- Es wurde eine in Version eingeführte Leistungsregression `101.05.17` behoben. Die Regression wurde mit dem Fix eingeführt, um die Kernel-Pannen zu beseitigen, die einige Kunden beim Zugriff auf SMB-Freigaben beobachtet haben. Wir haben diese Codeänderung rückgängig gemacht und untersuchen alternative Möglichkeiten, die Kernel-Pannen zu beseitigen.

## <a name="1010517"></a>101.05.17

> [!IMPORTANT]
> Wir arbeiten an einer neuen und erweiterten Syntax für das `mdatp` Befehlszeilentool. Die neue Syntax ist derzeit die Standardeinstellung in den Updatekanälen "Insider Fast" und "Insider Slow". Wir empfehlen Ihnen, sich mit dieser neuen Syntax zu verblassen.
> 
> Wir werden die alte Syntax weiterhin parallel zur neuen Syntax unterstützen und in den kommenden Monaten mehr Kommunikation über den Veraltetsplan für die alte Syntax bereitstellen.

- Eine Kernel-Pannenreaktion wurde behoben, die manchmal beim Zugriff auf SMB-Dateifreigaben aufgetreten ist
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010516"></a>101.05.16

- Verbesserungen an der Schnellscanlogik, um die Anzahl der gescannten Dateien erheblich zu reduzieren
- Unterstützung der [automatischen Kompletion](mac-resources.md#how-to-enable-autocompletion) für das Befehlszeilentool hinzugefügt
- Fehlerbehebungen

## <a name="1010312"></a>101.03.12

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010154"></a>101.01.54

- Verbesserungen bei der Kompatibilität mit dem Zeitcomputer
- Verbesserungen bei der Barrierefreiheit
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1010031"></a>101.00.31

- Verbesserte [Produkt-Onboarding-Erfahrung für Intune-Benutzer](/mem/intune/apps/apps-advanced-threat-protection-macos)
- [Antivirusausschlüsse unterstützen jetzt Platzhalter](mac-exclusions.md#supported-exclusion-types)
- Es wurde die Möglichkeit hinzugefügt, Antivirenscans aus dem Kontextmenü von macOS auszulösen. Sie können jetzt mit der rechten Maustaste auf eine Datei oder einen Ordner im Finder klicken und **"Mit Microsoft Defender für Endpunkt scannen"** auswählen.
- Direkte Produkt-Downgrades sind jetzt explizit vom Installationsprogramm nicht zulässig. Wenn Sie ein Downgrade ausführen müssen, deinstallieren Sie zuerst die vorhandene Version, und konfigurieren Sie Ihr Gerät neu.
- Weitere Leistungsverbesserungen & Fehlerbehebungen

## <a name="1009027"></a>100.90.27

- Sie können jetzt [einen Updatekanal](mac-updates.md#set-the-channel-name) für Microsoft Defender für Endpunkt unter macOS festlegen, der sich vom systemweiten Updatekanal unterscheidet.
- Symbol "Neues Produkt"
- Weitere Verbesserungen der Benutzererfahrung
- Fehlerbehebungen

## <a name="1008692"></a>100.86.92

- Verbesserungen bei der Kompatibilität mit dem Zeitcomputer
- Es wurde ein Problem behoben, bei dem das Produkt manchmal nicht alle Dateien während der Deinstallation säuberte. `/Library/Application Support/Microsoft/Defender`
- Verringerte die CPU-Auslastung des Produkts, wenn Microsoft-Produkte über Microsoft AutoUpdate aktualisiert werden
- Weitere Leistungsverbesserungen & Fehlerbehebungen

## <a name="1008691"></a>100.86.91

> [!CAUTION]
> Um den umfassendsten Schutz für Ihre macOS-Geräte sicherzustellen und in Übereinstimmung mit Apple die Bereitstellung von nativen MacOS-Sicherheitsupdates an ältere Betriebssystemversionen als [aktuell – 2] zu beenden, werden MDATP für Mac-Bereitstellungen und Updates unter macOS Sierra [10.12] nicht mehr unterstützt. MDATP für Mac-Updates und -Verbesserungen werden an Geräte bereitgestellt, auf denen die Versionen "Sierra" [10.15], "Mojave" [10.14] und "High Sierra" [10.13] ausgeführt werden. 
>
> Wenn Sie MDATP für Mac bereits auf Ihren Sierra [10.12]-Geräten bereitgestellt haben, aktualisieren Sie bitte auf die neueste macOS-Version, um das Risiko zu vermeiden, dass der Schutz verloren geht.

- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1008373"></a>100.83.73

- Weitere Steuerelemente für IT-Administratoren im Zusammenhang mit [der Verwaltung von Ausschlüssen,](mac-preferences.md#exclusion-merge-policy)der Verwaltung von Einstellungen für [den Bedrohungstyp](mac-preferences.md#threat-type-settings-merge-policy)und [nicht zulässigen Bedrohungsaktionen](mac-preferences.md#disallowed-threat-actions) hinzugefügt
- Wenn der vollständige Datenträgerzugriff auf dem Gerät nicht aktiviert ist, wird jetzt eine Warnung im Statusmenü angezeigt.
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1008260"></a>100.82.60

- Es wurde ein Problem behoben, bei dem das Produkt nach einem Definitionsupdate nicht gestartet werden kann.

## <a name="1008042"></a>100.80.42

- Fehlerbehebungen

## <a name="1007942"></a>100.79.42

- Es wurde ein Problem behoben, bei dem Microsoft Defender für Endpunkt auf dem Mac manchmal den Zeitcomputer beeinträchtigte.
- Zum Testen der Konnektivität mit dem Back-End-Dienst wurde dem Befehlszeilenprogramm ein neuer Switch hinzugefügt.
  ```bash
  mdatp connectivity test
  ```
- Es wurde die Möglichkeit hinzugefügt, den vollständigen Bedrohungsverlauf auf der Benutzeroberfläche anzuzeigen (auf sie kann über die **Schutzverlaufsansicht** zugegriffen werden)
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1007215"></a>100.72.15

- Fehlerbehebungen

## <a name="1007099"></a>100.70.99

- Es wurde ein Problem behoben, das sich darauf auswirkte, dass einige Benutzer ein Upgrade auf macOS- Und-Unterklasse durchführen konnten, wenn der Echtzeitschutz aktiviert ist. Dieses sporadische Problem wurde dadurch verursacht, dass Microsoft Defender für Endpunkt Dateien innerhalb des Upgradepakets von Workstation sperrt, während sie auf Bedrohungen geprüft werden, was zu Fehlern in der Upgradesequenz geführt hat.

## <a name="1006899"></a>100.68.99

- Die Möglichkeit zum Konfigurieren der Antivirusfunktionalität für die Ausführung im [passiven Modus](mac-preferences.md#enable--disable-passive-mode) wurde hinzugefügt.
- Leistungsverbesserungen & Fehlerbehebungen

## <a name="1006528"></a>100.65.28

- Unterstützung für macOS Maze hinzugefügt

  > [!CAUTION]
  > macOS 10.15 (Catalina) enthält neue Sicherheits- und Datenschutzerweiterungen. Ab dieser Version sind Anwendungen standardmäßig nicht in der Lage, ohne ausdrückliche Zustimmung auf bestimmte Speicherorte auf dem Disk zuzugreifen (wie Dokumente, Downloads, Desktop usw.). Wenn diese Zustimmung nicht vorhanden ist, kann Microsoft Defender für Endpunkt Ihr Gerät nicht vollständig schützen.
  >
  > Der Mechanismus für die Erteilung dieser Zustimmung hängt davon ab, wie Sie Microsoft Defender für Endpunkt bereitgestellt haben:
  >
  > - Informationen zu manuellen Bereitstellungen finden Sie in den aktualisierten Anweisungen im Thema ["Manuelle Bereitstellung".](mac-install-manually.md#how-to-allow-full-disk-access)
  > - Informationen zu verwalteten Bereitstellungen finden Sie in den aktualisierten Anweisungen in den Themen zur [JAMF-basierten Bereitstellung](mac-install-with-jamf.md) und [Microsoft Intune-basierten Bereitstellung.](mac-install-with-intune.md#create-system-configuration-profiles)

- Leistungsverbesserungen & Fehlerbehebungen
