---
title: Anpassen der Regeln zur Verringerung der Angriffsfläche
description: Einzeln festgelegte Regeln im Überwachungs-, Blockierungs- oder deaktivierten Modus und Hinzufügen von Dateien und Ordnern, die von Attack Surface Reduction-Regeln ausgeschlossen werden sollten
keywords: Attack Surface Reduction, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsschutz, anpassen, konfigurieren, ausschließen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: c03bc2a61ba2dae1b5db34c6b48d623c58c0c613
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782873"
---
# <a name="customize-attack-surface-reduction-rules"></a>Anpassen der Regeln zur Verringerung der Angriffsfläche

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> Einige Informationen beziehen sich auf Vorabversionen von Produkten, die vor der kommerziellen Veröffentlichung noch erheblich geändert werden können. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

[Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md) helfen, Softwareverhalten zu verhindern, die häufig missbraucht werden, um Ihr Gerät oder Netzwerk zu kompromittieren. Ein Angreifer könnte beispielsweise versuchen, ein nicht signiertes Skript von einem USB-Laufwerk aus auszuführen, oder ein Makro in einem Office Dokument aufruft direkt an die Win32-API. Regeln zur Verringerung der Angriffsfläche können diese Arten riskanter Verhaltensweisen einschränken und die verteidigungsbereitschaft Ihrer Organisation verbessern.

Erfahren Sie, wie Sie Regeln zur Verringerung der Angriffsfläche anpassen, indem [Sie Dateien und Ordner ausschließen](#exclude-files-and-folders) oder der [Benachrichtigungswarnung, die](#customize-the-notification) auf dem Computer eines Benutzers angezeigt wird, benutzerdefinierten Text hinzufügen.

Sie können Regeln zur Verringerung der Angriffsfläche für Geräte festlegen, auf denen eine der folgenden Editionen und Versionen von Windows ausgeführt wird:
- Windows 10 Pro, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährlicher Kanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19) Sie können diese Einstellungen mithilfe von Gruppenrichtlinien- und PowerShell-Konfigurationsdienstanbietern (CSP) für die mobile Geräteverwaltung (Mobile Device Management, MDM) konfigurieren.

## <a name="exclude-files-and-folders"></a>Ausschließen von Dateien und Ordnern

Sie können dateien und Ordner von der Auswertung durch Attack Surface Reduction-Regeln ausschließen. Nach dem Ausschließen wird die Ausführung der Datei auch dann nicht blockiert, wenn eine Regel zur Verringerung der Angriffsfläche erkennt, dass die Datei schädliches Verhalten enthält.

Betrachten Sie beispielsweise die Ransomware-Regel:

Die Ransomware-Regel soll Unternehmenskunden dabei helfen, Risiken von Ransomware-Angriffen zu verringern und gleichzeitig die Geschäftskontinuität zu gewährleisten. Standardmäßig wird die Ransomware-Regel auf der Seite der Vorsicht und zum Schutz vor Dateien, die noch nicht genügend Zuverlässigkeit und Vertrauenswürdigkeit erhalten haben, einen Fehler auslösen. Zur Neubetonierung wird die Ransomware-Regel nur für Dateien ausgelöst, die nicht genügend positive Reputation und Verbreitung auf der Grundlage von Nutzungsmetriken von Millionen unserer Kunden erhalten haben. In der Regel werden die Blöcke selbst aufgelöst, da die "Zuverlässigkeits- und Vertrauenswerte" jeder Datei inkrementell aktualisiert werden, wenn die Nutzung nicht problematisch wird.

In Fällen, in denen Blöcke nicht zeitnah selbst aufgelöst werden, können Kunden – _auf eigenes Risiko_ – entweder den Self-Service-Mechanismus oder eine Auf IOC-basierte "Zulassungsliste"-Funktion (Indicator of Compromise, Kompromissindikator) verwenden, um die Blockierung der Dateien selbst aufzuheben.  

> [!WARNING]
> Durch das Ausschließen oder Aufheben der Blockierung von Dateien oder Ordnern können möglicherweise unsichere Dateien ausgeführt und Ihre Geräte infiziert werden. Das Ausschließen von Dateien oder Ordnern kann den Schutz durch Regeln zur Verringerung der Angriffsfläche erheblich beeinträchtigen. Dateien, die durch eine Regel blockiert worden wären, dürfen ausgeführt werden, und es wird kein Bericht oder Ereignis aufgezeichnet.

Ein Ausschluss gilt für alle Regeln, die Ausschlüsse zulassen. Sie können eine einzelne Datei, einen Ordnerpfad oder den vollqualifizierten Domänennamen für eine Ressource angeben. Sie können einen Ausschluss jedoch nicht auf eine bestimmte Regel beschränken.

Ein Ausschluss wird nur angewendet, wenn die ausgeschlossene Anwendung oder der ausgeschlossene Dienst gestartet wird. Wenn Sie beispielsweise einen Ausschluss für einen Updatedienst hinzufügen, der bereits ausgeführt wird, löst der Updatedienst weiterhin Ereignisse aus, bis der Dienst beendet und neu gestartet wird.

Attack Surface Reduction unterstützt Umgebungsvariablen und Platzhalter. Informationen zur Verwendung von Platzhaltern finden Sie unter [Verwenden von Platzhaltern in den Dateinamen- und Ordnerpfad- oder Erweiterungsausschlusslisten.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
Wenn Probleme mit Regeln auftreten, die Dateien erkennen, von denen Sie glauben, dass sie nicht erkannt werden sollten, verwenden Sie [den Überwachungsmodus, um die Regel zu testen.](evaluate-attack-surface-reduction.md)

| Regelbeschreibung | GUID |
|:----|:----|
| Alle Office-Anwendungen am Erstellen von untergeordneten Prozessen hindern | `D4F940AB-401B-4EFC-AADC-AD5F3C50688A` |
| Ausführung potenziell verborgener Skripts blockieren | `5BEB7EFE-FD9A-4556-801D-275E5FFC04CC` |
| Blockieren von Win32-API-Aufrufen von Office Makro | `92E97FA1-2EDF-4476-BDD6-9DD0B4DDDC7B` |
| Office-Anwendungen am Erstellen ausführbarer Inhalte hindern | `3B576869-A4EC-4529-8536-B80A7769E899` |
| Office-Anwendungen am Einfügen von Code in untergeordnete Prozesse hindern | `75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84` |
| JavaScript und VBScript am Starten heruntergeladener ausführbarer Inhalte hindern | `D3E037E1-3EB8-44C8-A917-57927947596D` |
| Ausführbare Inhalte aus E-Mail-Client und Web-E-Mail blockieren | `BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550` |
| Blockieren der Ausführung ausführbarer Dateien, es sei denn, sie erfüllen verbreitungs-, alters- oder vertrauenswürdige Listenkriterien. | `01443614-cd74-433a-b99e-2ecdc07bfc25` |
| Erweiterten Schutz vor Ransomware verwenden | `c1db55ab-c21a-4637-bb3f-a12568109d35` |
| Diebstahl von Anmeldeinformationen aus dem Subsystem für die lokale Sicherheitsautorität (lsass.exe) blockieren | `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2` |
| Erstellung von Prozessen durch PSExec- und WMI-Befehle blockieren | `d1e49aac-8f56-4280-b9ba-993a6d77406c` |
| Nicht vertrauenswürdige und nicht signierte Prozess, die von USB ausgeführt werden, blockieren | `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4` |
| Verhindern, dass Office Kommunikationsanwendungen untergeordnete Prozesse erstellen | `26190899-1602-49e8-8b27-eb1d0a1ce869` |
| Adobe Reader am Erstellen von untergeordneten Prozessen hindern | `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c` |
| Persistenz durch WMI-Ereignisabonnement blockieren | `e6db77e5-3df2-4cf1-b95a-636979351e5b` |

Weitere Informationen zu den einzelnen Regeln finden Sie im Thema zur Verringerung der [Angriffsfläche.](attack-surface-reduction.md)

### <a name="use-group-policy-to-exclude-files-and-folders"></a>Verwenden von Gruppenrichtlinien zum Ausschließen von Dateien und Ordnern

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](https://technet.microsoft.com/library/cc731212.aspx), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration,** und klicken Sie auf **"Administrative Vorlagen".**

3. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit Guard** Attack Surface  >  **Reduction.**

4. Doppelklicken Sie auf die Einstellung **"Dateien und Pfade von Attack Surface Reduction Rules ausschließen",** und legen Sie die Option auf **"Aktiviert"** fest. Wählen Sie **"Anzeigen"** aus, und geben Sie jede Datei oder jeden Ordner in der Spalte **"Wertname"** ein. Geben Sie 0 in die **Spalte Wert** für jedes Element ein. 

> [!WARNING]
> Verwenden Sie keine Anführungszeichen, da sie weder für die Spalte mit dem **Wertnamen** noch für die **Spalte Value** unterstützt werden.

### <a name="use-powershell-to-exclude-files-and-folders"></a>Verwenden von PowerShell zum Ausschließen von Dateien und Ordnern

1. Geben Sie **PowerShell** im Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **"Als Administrator ausführen"** aus.
2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

Verwenden Sie `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` weiterhin, um der Liste weitere Ordner hinzuzufügen.

> [!IMPORTANT]
> Dient `Add-MpPreference` zum Anfügen oder Hinzufügen von Apps zur Liste. Mithilfe des `Set-MpPreference` Cmdlets wird die vorhandene Liste überschrieben.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>Verwenden von MDM-CSPs zum Ausschließen von Dateien und Ordnern

Verwenden Sie [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.

## <a name="customize-the-notification"></a>Anpassen der Benachrichtigung

Sie können die Benachrichtigung anpassen, wenn eine Regel ausgelöst wird und eine App oder Datei blockiert wird. Weitere Informationen finden Sie im [Artikel Windows-Sicherheit.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center)

## <a name="related-topics"></a>Verwandte Themen

* [Reduzieren von Angriffsflächen mit Regeln zur Verringerung der Angriffsfläche](attack-surface-reduction.md)
* [Aktivieren der Regeln zur Verringerung der Angriffsfläche](enable-attack-surface-reduction.md)
* [Auswerten der Regeln zur Verringerung der Angriffsfläche](evaluate-attack-surface-reduction.md)
* [Häufig gestellte Fragen zur Verringerung der Angriffsfläche](attack-surface-reduction.md)
