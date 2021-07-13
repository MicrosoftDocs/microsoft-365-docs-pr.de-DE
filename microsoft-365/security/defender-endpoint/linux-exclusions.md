---
title: Konfigurieren und Validieren von Ausschlüssen für Microsoft Defender für Endpunkt unter Linux
description: Bereitstellen und Überprüfen von Ausschlüssen für Microsoft Defender für Endpunkt unter Linux. Ausschlüsse können für Dateien, Ordner und Prozesse festgelegt werden.
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, Linux, Ausschlüsse, Scans, Antivirus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: b55572509e9837f2858f96b01a13fbf259b2b770
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393787"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-on-linux"></a>Konfigurieren und Validieren von Ausschlüssen für Microsoft Defender für Endpunkt unter Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Dieser Artikel enthält Informationen zum Definieren von Ausschlüssen, die für Scans bei Bedarf gelten, sowie zum Echtzeitschutz und zur Überwachung.

> [!IMPORTANT]
> Die in diesem Artikel beschriebenen Ausschlüsse gelten nicht für andere Defender für Endpunkt unter Linux-Funktionen, einschließlich EDR (EDR). Dateien, die Sie mithilfe der in diesem Artikel beschriebenen Methoden ausschließen, können weiterhin EDR Warnungen und andere Erkennungen auslösen.

Sie können bestimmte Dateien, Ordner, Prozesse und vom Prozess geöffnete Dateien von Defender für Endpunkt bei Linux-Scans ausschließen.

Ausschlüsse können nützlich sein, um falsche Erkennungen von Dateien oder Software zu vermeiden, die für Ihre Organisation eindeutig oder angepasst sind. Sie können auch nützlich sein, um Leistungsprobleme zu beheben, die von Defender für Endpunkt unter Linux verursacht werden.

> [!WARNING]
> Durch das Definieren von Ausschlüssen wird der von Defender für Endpunkt unter Linux angebotene Schutz verringert. Sie sollten immer die Risiken auswerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von denen Sie sicher sind, dass sie nicht bösartig sind.

## <a name="supported-exclusion-types"></a>Unterstützte Ausschlusstypen

In der folgenden Tabelle sind die ausschlusstypen aufgeführt, die von Defender für Endpunkt unter Linux unterstützt werden.

Ausschluss | Definition | Beispiele
---|---|---
Dateierweiterung | Alle Dateien mit der Erweiterung an beliebiger Stelle auf dem Gerät | `.test`
Datei | Eine bestimmte Datei, die durch den vollständigen Pfad identifiziert wird | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
Ordner | Alle Dateien unter dem angegebenen Ordner (rekursiv) | `/var/log/`<br/>`/var/*/`
Prozess | Ein bestimmter Prozess (angegeben durch den vollständigen Pfad oder Dateinamen) und alle geöffneten Dateien | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> Die oben genannten Pfade müssen feste Verknüpfungen und keine symbolischen Verknüpfungen sein, damit sie erfolgreich ausgeschlossen werden können. Sie können überprüfen, ob ein Pfad eine symbolische Verknüpfung ist, indem Sie `file <path-name>` ausführen.

Datei-, Ordner- und Prozessausschlüsse unterstützen die folgenden Platzhalter:

Platzhalter | Beschreibung | Beispiel | Übereinstimmungen | Stimmt nicht überein
---|---|---|---|---
\* |    Gleicht eine beliebige Anzahl von Zeichen ab, einschließlich keines (beachten Sie, dass bei Verwendung dieses Platzhalters innerhalb eines Pfads nur ein Ordner ersetzt wird). | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
? | Gleicht ein beliebiges einzelnes Zeichen ab | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a>So konfigurieren Sie die Liste der Ausschlüsse

### <a name="from-the-management-console"></a>Aus der Verwaltungskonsole

Weitere Informationen zum Konfigurieren von Ausschlüssen aus Deringen, Ansible oder einer anderen Verwaltungskonsole finden Sie unter [Festlegen von Einstellungen für Defender für Endpunkt unter Linux.](linux-preferences.md)

### <a name="from-the-command-line"></a>Über die Befehlszeile

Führen Sie den folgenden Befehl aus, um die verfügbaren Optionen zum Verwalten von Ausschlüssen anzuzeigen:

```bash
mdatp exclusion
```

> [!TIP]
> Wenn Sie Ausschlüsse mit Platzhaltern konfigurieren, schließen Sie den Parameter in doppelte Anführungszeichen ein, um Globbing zu verhindern.

Beispiele:

- Fügen Sie einen Ausschluss für eine Dateierweiterung hinzu:

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- Fügen Sie einen Ausschluss für eine Datei hinzu:

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- Fügen Sie einen Ausschluss für einen Ordner hinzu:

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- Fügen Sie einen Ausschluss für einen zweiten Ordner hinzu:

    ```bash
    mdatp exclusion folder add --path /var/log/
    mdatp exclusion folder add --path /other/folder
    ```
    ```Output
    Folder exclusion configured successfully
    ```


- Fügen Sie einen Ausschluss für einen Ordner mit einem Platzhalter hinzu:

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > Dadurch werden nur Pfade eine Ebene unter */var/* ausgeschlossen, aber keine Ordner, die tiefer verschachtelt sind; Beispiel: */var/this-subfolder/but-not-this-subfolder*.
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > Dadurch werden alle Pfade ausgeschlossen, deren übergeordnetes Element */var/* ist; Beispiel: */var/this-subfolder/and-this-subfolder-as-well*.

    ```Output
    Folder exclusion configured successfully
    ```

- Fügen Sie einen Ausschluss für einen Prozess hinzu:

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```


- Fügen Sie einen Ausschluss für einen zweiten Prozess hinzu:

    ```bash
    mdatp exclusion process add --name cat
    mdatp exclusion process add --name dog
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>Überprüfen von Ausschlusslisten mit der EICAR-Testdatei

Sie können überprüfen, ob Ihre Ausschlusslisten funktionieren, indem `curl` Sie eine Testdatei herunterladen.

Ersetzen Sie im folgenden Bash-Codeausschnitt `test.txt` durch eine Datei, die Ihren Ausschlussregeln entspricht. Wenn Sie die Erweiterung beispielsweise ausgeschlossen `.testing` haben, ersetzen Sie `test.txt` sie durch `test.testing` . Wenn Sie einen Pfad testen, stellen Sie sicher, dass Sie den Befehl innerhalb dieses Pfads ausführen.

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

Wenn Defender für Endpunkt unter Linux Schadsoftware meldet, funktioniert die Regel nicht. Wenn kein Bericht über Schadsoftware vorhanden ist und die heruntergeladene Datei vorhanden ist, funktioniert der Ausschluss. Sie können die Datei öffnen, um zu bestätigen, dass der Inhalt mit dem identisch ist, was auf der [EICAR-Testdateiwebsite](http://2016.eicar.org/86-0-Intended-use.html)beschrieben wird.

Wenn Sie keinen Internetzugriff haben, können Sie Eine eigene EICAR-Testdatei erstellen. Schreiben Sie die EICAR-Zeichenfolge in eine neue Textdatei mit dem folgenden Bash-Befehl:

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

Sie können die Zeichenfolge auch in eine leere Textdatei kopieren und versuchen, sie mit dem Dateinamen oder in dem Ordner zu speichern, den Sie ausschließen möchten.

## <a name="allow-threats"></a>Zulassen von Bedrohungen

Neben dem Ausschließen bestimmter Inhalte von der Überprüfung können Sie das Produkt auch so konfigurieren, dass einige Klassen von Bedrohungen (durch den Bedrohungsnamen identifiziert) nicht erkannt werden. Seien Sie vorsichtig, wenn Sie diese Funktionalität verwenden, da ihr Gerät dadurch ungeschützter ist.

Führen Sie den folgenden Befehl aus, um der Liste zugelassener Bedrohungen einen Bedrohungsnamen hinzuzufügen:

```bash
mdatp threat allowed add --name [threat-name]
```

Der bedrohungsname, der einer Erkennung auf Ihrem Gerät zugeordnet ist, kann mit dem folgenden Befehl abgerufen werden:

```bash
mdatp threat list
```

Führen Sie z. B. den folgenden Befehl aus, um der Liste zugelassener Elemente (der der `EICAR-Test-File (not a virus)` EICAR-Erkennung zugeordnete Bedrohungsname) hinzuzufügen:

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
