---
title: Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender ATP für Mac
description: Bereitstellen und Überprüfen von Ausschlüssen für Microsoft Defender ATP für Mac. Ausschlüsse können für Dateien, Ordner und Prozesse festgelegt werden.
keywords: microsoft, defender, atp, mac, exclusions, scans, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.openlocfilehash: 2281fccfb97d38dbdc218799b087290433deff30
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764157"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-macos"></a>Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender for Endpoint unter macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Dieser Artikel enthält Informationen zum Definieren von Ausschlüssen, die für Scans bei Bedarf gelten, sowie Zum Schutz und Überwachung in Echtzeit.

>[!IMPORTANT]
>Die in diesem Artikel beschriebenen Ausschlüsse gelten nicht für andere Defender for Endpoint auf Mac-Funktionen, einschließlich Endpunkterkennung und -reaktion (EDR). Dateien, die Sie mithilfe der in diesem Artikel beschriebenen Methoden ausschließen, können weiterhin EDR-Warnungen und andere Erkennungen auslösen.

Sie können bestimmte Dateien, Ordner, Prozesse und prozessgeladene Dateien aus Defender for Endpoint auf Mac-Scans ausschließen.

Ausschlüsse können hilfreich sein, um fehlerhafte Erkennungen für Dateien oder Software zu vermeiden, die eindeutig oder an Ihre Organisation angepasst sind. Sie können auch hilfreich sein, um Leistungsprobleme zu mildern, die von Defender for Endpoint auf Dem Mac verursacht werden.

>[!WARNING]
>Durch das Definieren von Ausschlüssen wird der von Defender for Endpoint auf Dem Mac gebotene Schutz gesenkt. Sie sollten immer die Risiken bewerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von deren Ausführung Sie sicher sind, dass sie nicht bösartig sind.

## <a name="supported-exclusion-types"></a>Unterstützte Ausschlusstypen

In der folgenden Tabelle sind die Ausschlusstypen aufgeführt, die von Defender for Endpoint auf Dem Mac unterstützt werden.

Ausschluss | Definition | Beispiele
---|---|---
Dateierweiterung | Alle Dateien mit der Erweiterung, überall auf dem Computer | `.test`
Datei | Eine bestimmte Datei, die durch den vollständigen Pfad identifiziert wird | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Ordner | Alle Dateien unter dem angegebenen Ordner (rekursiv) | `/var/log/`<br/>`/var/*/`
Prozess | Ein bestimmter Prozess (entweder durch den vollständigen Pfad oder Dateinamen angegeben) und alle dateien, die von diesem geöffnet werden | `/bin/cat`<br/>`cat`<br/>`c?t`

Datei-, Ordner- und Prozessausschlüsse unterstützen die folgenden Platzhalter:

Platzhalter | Beschreibung | Beispiel | Übereinstimmungen | Nicht übereinstimmend
---|---|---|---|---
\* |    Entspricht einer beliebigen Anzahl beliebiger Zeichen, einschließlich keines (beachten Sie, dass dieser Platzhalter nur einen Ordner ersetzt, wenn er innerhalb eines Pfads verwendet wird) | `/var/*/*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | Entspricht einem beliebigen einzelnen Zeichen | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

>[!NOTE]
>Das Produkt versucht, firmlinks beim Auswerten von Ausschlüssen zu beheben. Die Auflösung von Firmlink funktioniert nicht, wenn der Ausschluss Platzhalter enthält oder die Zieldatei (auf dem `Data` Volume) nicht vorhanden ist.

## <a name="how-to-configure-the-list-of-exclusions"></a>Konfigurieren der Liste der Ausschlüsse

### <a name="from-the-management-console"></a>Über die Verwaltungskonsole

Weitere Informationen zum Konfigurieren von Ausschlüssen aus JAMF, Intune oder einer anderen Verwaltungskonsole finden Sie unter [Set preferences for Defender for Endpoint on Mac](mac-preferences.md).

### <a name="from-the-user-interface"></a>Über die Benutzeroberfläche

Öffnen Sie die Defender for Endpoint-Anwendung, und navigieren Sie zu Einstellungen **verwalten** Hinzufügen oder Entfernen von  >  **Ausschluss...**, wie im folgenden Screenshot gezeigt:

![Screenshot "Verwalten von Ausschlüssen"](images/mdatp-37-exclusions.png)

Wählen Sie den Typ des Ausschlusses aus, den Sie hinzufügen möchten, und folgen Sie den Eingabeaufforderungen.

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Überprüfen von Ausschlusslisten mit der EICAR-Testdatei

Sie können überprüfen, ob Ihre Ausschlusslisten funktionieren, indem Sie `curl` eine Testdatei herunterladen.

Ersetzen Sie im folgenden Bash-Codeausschnitt durch eine Datei, die `test.txt` Ihren Ausschlussregeln entspricht. Wenn Sie beispielsweise die Erweiterung ausgeschlossen `.testing` haben, ersetzen Sie `test.txt` durch `test.testing` . Wenn Sie einen Pfad testen, stellen Sie sicher, dass Sie den Befehl innerhalb dieses Pfads ausführen.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Wenn Defender for Endpoint auf Mac Schadsoftware meldet, funktioniert die Regel nicht. Wenn kein Bericht über Schadsoftware vorhanden ist und die heruntergeladene Datei vorhanden ist, funktioniert der Ausschluss. Sie können die Datei öffnen, um zu bestätigen, dass der Inhalt mit den auf der [EICAR-Testdateiwebsite beschriebenen Inhalten identisch ist.](http://2016.eicar.org/86-0-Intended-use.html)

Wenn Sie keinen Internetzugriff haben, können Sie eine eigene EICAR-Testdatei erstellen. Schreiben Sie die EICAR-Zeichenfolge mit dem folgenden Bash-Befehl in eine neue Textdatei:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

Sie können die Zeichenfolge auch in eine leere Textdatei kopieren und versuchen, sie mit dem Dateinamen oder in dem Ordner zu speichern, den Sie ausschließen möchten.

## <a name="allow-threats"></a>Zulassen von Bedrohungen

Zusätzlich zum Ausschließen bestimmter Inhalte, die gescannt werden, können Sie das Produkt auch so konfigurieren, dass einige Klassen von Bedrohungen (identifiziert durch den Bedrohungsnamen) nicht erkannt werden. Bei der Verwendung dieser Funktionalität sollten Sie Vorsichtigkeit walten lassen, da ihr Gerät nicht geschützt werden kann.

Führen Sie den folgenden Befehl aus, um der liste der zulässigen Bedrohungen einen Bedrohungsnamen hinzuzufügen:

```bash
mdatp threat allowed add --name [threat-name]
```

Der Bedrohungsname, der einer Erkennung auf Ihrem Gerät zugeordnet ist, kann mithilfe des folgenden Befehls ermittelt werden:

```bash
mdatp threat list
```

Führen Sie beispielsweise den folgenden Befehl aus, um der liste zulässigen Liste (der der `EICAR-Test-File (not a virus)` EICAR-Erkennung zugeordnete Bedrohungsname) hinzuzufügen:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
