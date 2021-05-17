---
title: Anpassen der Regeln zur Verringerung der Angriffsfläche
description: Individuelles Festlegen von Regeln in Überwachungs-, Block- oder deaktivierten Modi und Hinzufügen von Dateien und Ordnern, die von Regeln zur Reduzierung der Angriffsfläche ausgeschlossen werden sollten
keywords: Attack surface reduction, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, customize, configure, exclude
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 52a51b1035f1aa0fb152cf17dc9561cce378d59d
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570351"
---
# <a name="customize-attack-surface-reduction-rules"></a>Anpassen der Regeln zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

[Regeln zur Reduzierung der Angriffsfläche](enable-attack-surface-reduction.md) verhindern Softwareverhalten, das häufig missbraucht wird, um Ihr Gerät oder Netzwerk zu gefährdet. Beispielsweise kann ein Angreifer versuchen, ein nicht signiertes Skript von einem USB-Laufwerk aus auszuführen, oder ein Makro in einem Office direkt an die Win32-API aufrufen lassen. Regeln zur Reduzierung der Angriffsfläche können diese Arten riskanter Verhaltensweisen einschränken und die Defensivhaltung Ihrer Organisation verbessern.

Erfahren Sie, wie Sie Regeln zur Reduzierung [](#customize-the-notification) der Angriffsfläche anpassen, indem Sie Dateien und Ordner ausschließen oder der [Benachrichtigungsbenachrichtigung,](#exclude-files-and-folders) die auf dem Computer eines Benutzers angezeigt wird, benutzerdefinierten Text hinzufügen.

Sie können Regeln zur Reduzierung der Angriffsfläche für Geräte festlegen, auf der eine der folgenden Editionen und Versionen von Windows:
- Windows 10 Pro, Version [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, Version [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19) Sie können Gruppenrichtlinien, PowerShell und #A0 (Mobile Device Management) verwenden, um diese Einstellungen zu konfigurieren.

## <a name="exclude-files-and-folders"></a>Ausschließen von Dateien und Ordnern

Sie können die Auswertung von Dateien und Ordnern durch Regeln zur Reduzierung der Angriffsfläche ausschließen. Nachdem die Datei ausgeschlossen wurde, wird die Ausführung nicht blockiert, auch wenn eine Regel zur Reduzierung der Angriffsfläche erkennt, dass die Datei schädliches Verhalten enthält.

> [!WARNING]
> Dadurch können möglicherweise unsichere Dateien ausgeführt und Ihre Geräte infizieren. Das Ausschließen von Dateien oder Ordnern kann den Schutz durch Regeln zur Reduzierung der Angriffsfläche erheblich reduzieren. Dateien, die durch eine Regel blockiert worden wären, können ausgeführt werden, und es wird kein Bericht oder Ereignis aufgezeichnet.

Ein Ausschluss gilt für alle Regeln, die Ausschlüsse zulassen. Sie können eine einzelne Datei, einen Ordnerpfad oder den vollqualifizierten Domänennamen für eine Ressource angeben. Sie können einen Ausschluss jedoch nicht auf eine bestimmte Regel beschränken.

Ein Ausschluss wird nur angewendet, wenn die ausgeschlossene Anwendung oder der ausgeschlossene Dienst gestartet wird. Wenn Sie beispielsweise einen Ausschluss für einen bereits ausgeführten Updatedienst hinzufügen, löst der Updatedienst weiterhin Ereignisse aus, bis der Dienst beendet und neu gestartet wird.

Die Reduzierung der Angriffsfläche unterstützt Umgebungsvariablen und Platzhalter. Informationen zur Verwendung von Platzhaltern finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder [Erweiterungsausschluss](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).
Wenn Probleme mit Regeln auftreten, die Dateien erkennen, von denen Sie glauben, dass sie nicht erkannt werden sollten, verwenden Sie den Überwachungsmodus, um [die Regel zu testen.](evaluate-attack-surface-reduction.md)

Regelbeschreibung | GUID
-|-|-
Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern | D4F940AB-401B-4EFC-AADC-AD5F3C50688A
Ausführung potenziell verborgener Skripts blockieren | 5BEB7EFE-FD9A-4556-801D-275E5FFC04CC
Blockieren von Win32-API-Aufrufen Office Makros | 92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B
Office-Anwendungen am Erstellen ausführbarer Inhalte hindern | 3B576869-A4EC-4529-8536-B80A7769E899
Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern | 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84
JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern | D3E037E1-3EB8-44C8-A917-57927947596D
Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren | BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550
Blockieren der Ausführung ausführbarer Dateien, es sei denn, sie erfüllen ein Prävalenz-, Alters- oder vertrauenswürdiges Listenkriterium | 01443614-cd74-433a-b99e-2ecdc07bfc25
Erweiterten Schutz vor Ransomware verwenden | c1db55ab-c21a-4637-bb3f-a12568109d35
Diebstahl von Anmeldeinformationen aus dem Subsystem für die lokale Sicherheitsautorität (lsass.exe) blockieren | 9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2
Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren | d1e49aac-8f56-4280-b9ba-993a6d77406c
Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren | b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4
Blockieren Office von Kommunikationsanwendungen am Erstellen untergeordneter Prozesse | 26190899-1602-49e8-8b27-eb1d0a1ce869
Adobe Reader am Erstellen von untergeordneten Prozessen hindern | 7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c
Persistenz durch WMI-Ereignisabonnement blockieren | e6db77e5-3df2-4cf1-b95a-636979351e5b

Details zu [den einzelnen](attack-surface-reduction.md) Regeln finden Sie im Thema Zur Reduzierung der Angriffsfläche.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Verwenden von Gruppenrichtlinien zum Ausschließen von Dateien und Ordnern

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](https://technet.microsoft.com/library/cc731212.aspx), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und klicken Sie auf **Administrative Vorlagen**.

3. Erweitern Sie die **Struktur, Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit Guard** Attack Surface Reduction  >  **.**

4. Doppelklicken Sie auf die Einstellung **Dateien und Pfade von Attack surface reduction Rules** ausschließen, und legen Sie die Option auf Aktiviert **.** Wählen **Sie Anzeigen** aus, und geben Sie jede Datei oder jeden Ordner in der Spalte **Wertname** ein. Geben **Sie 0** in die **Spalte Wert** für jedes Element ein.

> [!WARNING]
> Verwenden Sie keine Anführungszeichen, da sie weder für die Spalte **Wertname** noch für die **Spalte Wert unterstützt** werden.

### <a name="use-powershell-to-exclude-files-and-folders"></a>Verwenden von PowerShell zum Ausschließen von Dateien und Ordnern

1. Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **maustaste Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**
2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Verwenden Sie `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` weiterhin, um der Liste weitere Ordner hinzuzufügen.

> [!IMPORTANT]
> Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste. Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Verwenden von MDM-CSPs zum Ausschließen von Dateien und Ordnern

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.

## <a name="customize-the-notification"></a>Anpassen der Benachrichtigung

Sie können die Benachrichtigung anpassen, wenn eine Regel ausgelöst wird, und eine App oder Datei sperren. Weitere Informationen [finden Windows-Sicherheit](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) Artikel.

## <a name="related-topics"></a>Verwandte Themen

* [Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche](attack-surface-reduction.md)
* [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md)
* [Auswerten der Regeln zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md)
* [FAQ zu Verringerung der Angriffsfläche](attack-surface-reduction.md)
