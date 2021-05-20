---
title: Aktivieren Sie den von der Cloud bereitgestellten Schutz in Microsoft Defender Antivirus
description: Schalten Sie den von der Cloud bereitgestellten Schutz ein, um von schnellen und erweiterten Schutzfunktionen zu profitieren.
keywords: Microsoft Defender Antivirus, Antimalware, Sicherheit, Cloud, Block auf den ersten Blick
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572057"
---
# <a name="turn-on-cloud-delivered-protection"></a>Über die Cloud bereitgestellten Netzwerkschutz aktivieren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus, mit dem Sie aktualisierten Schutz für Ihr Netzwerk und Ihre Endpunkte bereitstellen können. Obwohl es als Cloud-Dienst bezeichnet wird, ist es nicht einfach Schutz für Dateien, die in der Cloud gespeichert sind; Stattdessen werden verteilte Ressourcen und maschinelles Lernen verwendet, um Ihre Endpunkte mit einer Rate zu schützen, die viel schneller ist als herkömmliche Sicherheitsintelligenzaktualisierungen.

Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Präventionstechnologien, um präzisen, Echtzeit- und intelligenten Schutz zu bieten. [Lernen Sie die fortschrittlichen Technologien kennen, die im Kern von Microsoft Defender for Endpoint-Schutz der nächsten Generation stehen.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

Sie können Microsoft Defender Antivirus Cloud-geschützten Schutz auf verschiedene Arten ein- oder ausschalten:

- Microsoft Intune
- Microsoft Endpoint Manager
- Gruppenrichtlinien
- PowerShell Cmdlets.

 Sie können es auch in einzelnen Clients mit der Windows-Sicherheit App ein- oder ausschalten.

Eine Übersicht über Microsoft Defender Antivirus von der Cloud bereitgestellten Schutz finden Sie unter Verwenden des von Microsoft bereitgestellten Schutzes in [der Microsoft-Cloud.](cloud-protection-microsoft-defender-antivirus.md)

Weitere Informationen zu den spezifischen Anforderungen an die Netzwerkkonnektivität, um sicherzustellen, dass Ihre Endpunkte eine Verbindung mit dem in der Cloud bereitgestellten Schutzdienst herstellen können, finden Sie unter Konfigurieren und Überprüfen von [Netzwerkverbindungen](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> In Windows 10 gibt es keinen Unterschied zwischen den in diesem Thema beschriebenen Optionen **für die grundlegende** und **erweiterte** Berichterstattung. Dies ist eine ältere Unterscheidung, und die Auswahl einer der beiden Einstellungen führt zu demselben Schutzniveau, das von der Cloud bereitgestellt wird. Es gibt keinen Unterschied in der Art oder Menge der freigegebenen Informationen. Weitere Informationen zu dem, was wir sammeln, finden Sie in der [Microsoft-Datenschutzerklärung](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Verwenden sie Intune, um den von der Cloud bereitgestellten Schutz zu aktivieren

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.

2. Wählen Sie im **Fenster Startseite** die Option **Gerätekonfiguration > Profile aus.**

3. Wählen Sie den Profiltyp **"Geräteeinschränkungen" aus, den** Sie konfigurieren möchten. Wenn Sie einen neuen **Profiltyp** für Geräteeinschränkungen erstellen müssen, finden Sie weitere Informationen unter Konfigurieren der [Geräteeinschränkungseinstellungen in Microsoft Intune](/intune/device-restrictions-configure).

4.   >  **Eigenschaftenkonfigurationseinstellungen auswählen: Bearbeiten**  >  **Microsoft Defender Antivirus**.

5. Wählen Sie auf dem Von der **Cloud bereitgestellten Schutzschalter** Aktivieren die Option **Aktivieren** aus.

6. Wählen Sie in der Dropdownliste **"Anfordern" vor der Beispielübermittlung** die Option **Alle Daten automatisch senden** aus.

Weitere Informationen zu Intune-Geräteprofilen, z. B. zum Erstellen und Konfigurieren ihrer Einstellungen, finden Sie unter [Was sind Microsoft Intune Geräteprofile?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Verwenden Sie Microsoft Endpoint Manager, um den von der Cloud bereitgestellten Schutz zu aktivieren

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.

2. Wählen Sie **Endpoint security**  >  **Antivirus**.

3. Wählen Sie ein Antivirenprofil aus. (Wenn Sie noch keines haben oder ein neues Profil erstellen möchten, finden Sie weitere Informationen unter Konfigurieren der [Geräteeinschränkungseinstellungen in Microsoft Intune](/intune/device-restrictions-configure).

4. Wählen Sie **Eigenschaften** aus. Wählen Sie dann neben **den Konfigurationseinstellungen** **bearbeiten** aus.

5. Erweitern Sie den **Cloud-Schutz**, und wählen Sie dann in der Liste der **bereitgestellten Schutzebenen** in der Cloud bereitgestellten Option eine der folgenden Optionen aus:
   - **Hoch**: Wendet ein starkes Erkennungsniveau an.
   - **High plus**: Verwendet das **High** Level und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Kundenleistung auswirken).
   - **Nulltoleranz**: Blockiert alle unbekannten ausführbaren Dateien.

6. Wählen Sie **Überprüfen + Speichern**, und wählen Sie **speichern**.

Weitere Informationen zum Konfigurieren von Microsoft Endpoint Configuration Manager finden Sie unter [Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Verwenden von Gruppenrichtlinien zum Aktivieren des von der Cloud bereitgestellten Schutzes

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten aus.**

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Wählen Sie **Administrative Vorlagen** aus.

4. Erweitern Sie die Struktur, um **Komponenten > Microsoft Defender Antivirus > MAPS** zu Windows

5. Doppelklicken Sie auf **Microsoft MAPS beitreten**. Stellen Sie sicher, dass die Option aktiviert ist und auf **Basic MAPS** oder **Advanced MAPS** festgelegt ist. Klicken Sie auf **OK**.

6. Doppelklicken Sie auf **Dateibeispiele senden, wenn weitere Analysen erforderlich sind**. Stellen Sie sicher, dass die erste Option auf **Aktiviert** und die anderen Optionen auf folgende Optionen festgelegt sind:

    1. **Sichere Proben versenden** (1)
    2. **Senden Sie alle Proben** (3)

        >[!NOTE]
        > Die Option **Sichere Proben senden** (1) bedeutet, dass die meisten Proben automatisch gesendet werden. Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.
        > Wenn Sie die Option **auf Immer Eingabeaufforderung** (0) setzen, wird der Schutzstatus des Geräts verringert. Wenn Sie es auf **Nie senden** (2) setzen, funktioniert die [Funktion "Blockieren beim ersten Blick"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender for Endpoint nicht.

7. Klicken Sie auf **OK**.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Verwenden Von PowerShell-Cmdlets zum Aktivieren des von der Cloud bereitgestellten Schutzes

Die folgenden Cmdlets können den von der Cloud bereitgestellten Schutz aktivieren:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus- und](use-powershell-cmdlets-microsoft-defender-antivirus.md) [Defender-Cmdlets](/powershell/module/defender/). [Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) hat auch mehr Informationen speziell auf [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Sie können auch **-SubmitSamplesConsent** auf `SendSafeSamples` (die Standardeinstellung), `NeverSend` oder `AlwaysPrompt` festlegen. Die `SendSafeSamples` Einstellung bedeutet, dass die meisten Samples automatisch gesendet werden. Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.

>[!WARNING]
> Einstellung **-SubmitSamplesConsent** auf `NeverSend` oder senkt die `AlwaysPrompt` Schutzstufe des Geräts. Außerdem bedeutet das Festlegen, `NeverSend` dass die [Funktion "Blockieren beim ersten Blick"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender for Endpoint nicht funktioniert.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Verwenden sie Windows Management Instruction (WMI), um den von der Cloud bereitgestellten Schutz zu aktivieren

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/defender/set-msft-mppreference) für die folgenden Eigenschaften:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Weitere Informationen zu zulässigen Parametern finden Sie [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Aktivieren Sie den von der Cloud bereitgestellten Schutz für einzelne Clients mit der Windows-Sicherheit-App

> [!NOTE]
> Wenn die Einstellung Lokale Einstellung Konfigurieren **für den Bericht von Microsoft MAPS** Group Policy auf **Deaktiviert** festgelegt ist, ist die **Cloud-basierte Schutzeinstellung** in Windows Einstellungen ausgegraut und nicht verfügbar. Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.

1. Öffnen Sie die Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen oder im Startmenü nach **Defender** suchen.

2. Wählen Sie die **Virus & Bedrohungsschutzkachel** (oder das Schildsymbol in der linken Menüleiste) und dann die Bezeichnung **Virus & Bedrohungsschutzeinstellungen** aus:

    ![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

3. Vergewissern Sie sich, dass **Cloud-basierter Schutz** und **automatische Beispielübermittlung** auf **Ein** geschaltet werden.

> [!NOTE]
> Wenn die automatische Beispielübermittlung mit Gruppenrichtlinien konfiguriert wurde, ist die Einstellung ausgegraut und nicht verfügbar.

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren des Timeoutzeitraums für Cloudblockierung](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Block auf den ersten Blick konfigurieren](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Schützen Sie Windows PCs mit Endpoint Protection für Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Defender Cmdlets](/powershell/module/defender/)
- [Verwenden sie den von Microsoft Cloud bereitgestellten Schutz in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)
- [Erstellen und Bereitstellen von Antischadsoftware-Richtlinien: Cloud-Schutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
