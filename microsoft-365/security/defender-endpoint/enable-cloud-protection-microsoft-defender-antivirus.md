---
title: Aktivieren des über die Cloud bereitgestellten Schutzes in Microsoft Defender Antivirus
description: Aktivieren Sie den über die Cloud bereitgestellten Schutz, um von schnellen und erweiterten Schutzfunktionen zu profitieren.
keywords: Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Cloud, bei erster Anzeige blockieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.date: 06/17/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 694c09c5136f874550fa4a47586f3268ee2d0833
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007182"
---
# <a name="turn-on-cloud-delivered-protection"></a>Über die Cloud bereitgestellten Netzwerkschutz aktivieren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Der Microsoft Defender Antivirus Clouddienst ist ein Mechanismus zum Bereitstellen eines aktualisierten Schutzes für Ihr Netzwerk und Ihre Endpunkte. Obwohl er als Clouddienst bezeichnet wird, ist er nicht nur Schutz für Dateien, die in der Cloud gespeichert sind. Stattdessen werden verteilte Ressourcen und maschinelles Lernen verwendet, um Schutz für Ihre Endpunkte in einer Geschwindigkeit bereitzustellen, die viel schneller als herkömmliche Security Intelligence-Updates ist.

Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, echtzeitbasierten und intelligenten Schutz zu bieten. [Lernen Sie die fortschrittlichen Technologien](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)kennen, die den Kern des Schutzes der nächsten Generation von Microsoft Defender für Endpunkt darstellen.

Sie können Microsoft Defender Antivirus über die Cloud bereitgestellten Schutz auf verschiedene Arten aktivieren oder deaktivieren:

- Microsoft Intune
- Microsoft Endpoint Manager
- Gruppenrichtlinien
- PowerShell-Cmdlets.

 Sie können sie auch in einzelnen Clients mit der Windows-Sicherheit-App aktivieren oder deaktivieren.

Eine Übersicht über Microsoft Defender Antivirus über die Cloud bereitgestellten Schutz finden Sie unter ["Über](cloud-protection-microsoft-defender-antivirus.md) die Cloud bereitgestellten Schutz von Microsoft".

Weitere Informationen zu den spezifischen Anforderungen an die Netzwerkkonnektivität, um sicherzustellen, dass Ihre Endpunkte eine Verbindung mit dem über die Cloud bereitgestellten Schutzdienst herstellen können, finden Sie unter [Konfigurieren und Überprüfen von Netzwerkverbindungen.](configure-network-connections-microsoft-defender-antivirus.md)

> [!NOTE]
> In Windows 10 gibt es keinen Unterschied zwischen **den** in diesem Thema beschriebenen grundlegenden und **erweiterten** Berichtsoptionen. Dies ist eine veraltete Unterscheidung, und die Auswahl einer der beiden Einstellungen führt zu dem gleichen Maß an über die Cloud bereitgestelltem Schutz. Es gibt keinen Unterschied hinsichtlich des Typs oder der Menge der informationen, die freigegeben werden. Weitere Informationen dazu, was wir sammeln, finden Sie in den [Microsoft-Datenschutzbestimmungen.](https://go.microsoft.com/fwlink/?linkid=521839)

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Verwenden von Intune zum Aktivieren des über die Cloud bereitgestellten Schutzes

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie im **Bereich "Start"** die **Gerätekonfiguration > Profile aus.**

3. Wählen Sie den **Profiltyp "Geräteeinschränkungen"** aus, den Sie konfigurieren möchten. Wenn Sie einen neuen Profiltyp für **Geräteeinschränkungen** erstellen müssen, lesen Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune.](/intune/device-restrictions-configure)

4. Wählen Sie  >  **Eigenschaftenkonfigurationseinstellungen aus: Bearbeiten**  >  **Microsoft Defender Antivirus**.

5. Wählen Sie im switch **"Cloud-delivered protection"** die Option **"Aktivieren"** aus.

6. Wählen Sie in der **Dropdownliste "Benutzer vor Beispielübermittlung auffordern"** die Option **"Alle Daten automatisch senden"** aus.

Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter [Was sind Microsoft Intune Geräteprofile?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Verwenden von Microsoft Endpoint Manager zum Aktivieren des über die Cloud bereitgestellten Schutzes

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **Endpunktsicherheits-Antivirus**  >  aus.

3. Wählen Sie ein Antivirusprofil aus. (Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune.](/intune/device-restrictions-configure)

4. Wählen Sie **Eigenschaften** aus. Wählen Sie dann neben den **Konfigurationseinstellungen** **"Bearbeiten"** aus.

5. Erweitern Sie den **Cloudschutz,** und wählen Sie dann in der Liste der über die **Cloud bereitgestellten Schutzebene** eine der folgenden Optionen aus:
   - **Hoch:** Wendet eine starke Erkennungsstufe an.
   - **Hoch plus:** Verwendet die **Stufe "High"** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).
   - **Nulltoleranz:** Blockiert alle unbekannten ausführbaren Dateien.

6. Wählen Sie **"Überprüfen" + "Speichern"** und dann **"Speichern"** aus.

Weitere Informationen zum Konfigurieren von Microsoft Endpoint Configuration Manager finden Sie unter [Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Verwenden von Gruppenrichtlinien zum Aktivieren des über die Cloud bereitgestellten Schutzes

1. Öffnen Sie auf Ihrem Gerät für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.

2. Wechseln Sie im **Gruppenrichtlinienverwaltungs-Editor** zur **Computerkonfiguration.**

3. Wählen Sie **Administrative Vorlagen** aus.

4. Erweitern Sie die Struktur, um **komponenten > Microsoft Defender Antivirus > MAPS zu Windows**

5. Doppelklicken Sie auf **"Microsoft MAPS beitreten".** Stellen Sie sicher, dass die Option aktiviert ist, und legen Sie sie auf **Basic MAPS** oder **Advanced MAPS** fest. Wählen Sie **OK** aus.

6. Doppelklicken Sie auf **Dateibeispiele senden, wenn eine weitere Analyse erforderlich ist.** Stellen Sie sicher, dass die erste Option auf "Aktiviert" und die anderen Optionen auf **"Aktiviert"** festgelegt sind:

    1. **Sichere Beispiele senden** (1)
    2. **Senden aller Beispiele** (3)

        >[!NOTE]
        > Die Option **"Sichere Beispiele** senden" (1) bedeutet, dass die meisten Beispiele automatisch gesendet werden. Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.
        > Wenn Sie die Option auf **"Immer auffordern"** (0) festlegen, wird der Schutzstatus des Geräts verringert. Das Festlegen auf **"Nie senden"** (2) bedeutet, dass das Feature ["Bei erster Anzeige blockieren"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender für Endpunkt nicht funktioniert.

7. Wählen Sie **OK** aus.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Verwenden von PowerShell-Cmdlets zum Aktivieren des über die Cloud bereitgestellten Schutzes

Die folgenden Cmdlets können den über die Cloud bereitgestellten Schutz aktivieren:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Verwenden von PowerShell-Cmdlets zum Konfigurieren und Ausführen Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) und [Defender-Cmdlets.](/powershell/module/defender/) [Policy CSP – Defender](/windows/client-management/mdm/policy-csp-defender) verfügt auch über weitere Informationen speziell zu [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Sie können auch **"-SubmitSamplesConsent"** `SendSafeSamples` (Standardeinstellung) `NeverSend` oder `AlwaysPrompt` festlegen. Die `SendSafeSamples` Einstellung bedeutet, dass die meisten Beispiele automatisch gesendet werden. Dateien, die wahrscheinlich persönliche Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.

>[!WARNING]
> Setting **-SubmitSamplesConsent** to `NeverSend` or will lower the protection level of the `AlwaysPrompt` device. Darüber hinaus bedeutet das Festlegen, `NeverSend` dass das Feature ["Bei erster Anzeige blockieren"](configure-block-at-first-sight-microsoft-defender-antivirus.md) von Microsoft Defender für Endpunkt nicht funktioniert.

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Verwenden Windows Management Instruction (WMI) zum Aktivieren des über die Cloud bereitgestellten Schutzes

Verwenden Sie die [ **Set-Methode** der **MSFT_MpPreference-Klasse**](/previous-versions/windows/desktop/defender/set-msft-mppreference) für die folgenden Eigenschaften:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Weitere Informationen zu zulässigen Parametern finden Sie unter [Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Aktivieren des über die Cloud bereitgestellten Schutzes auf einzelnen Clients mit der Windows-Sicherheit-App

> [!NOTE]
> Wenn die **Außerkraftsetzung** der lokalen Einstellung konfigurieren für die Meldung der Gruppenrichtlinieneinstellung von Microsoft MAPS auf **"Deaktiviert"** festgelegt ist, ist die **cloudbasierte Schutzeinstellung** in Windows Einstellungen abgeblendet und nicht verfügbar. Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.

1. Öffnen Sie die Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen oder das Startmenü nach **Defender** durchsuchen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) und dann die Bezeichnung **"Viren & Bedrohungsschutzeinstellungen"** aus:

    :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Screenshot der Einstellungen für den Viren- & Bedrohungsschutz":::

3. Vergewissern Sie sich, dass **cloudbasierter Schutz** und **automatische Beispielübermittlung** auf **"Ein"** umgestellt sind.

> [!NOTE]
> Wenn die automatische Beispielübermittlung mit der Gruppenrichtlinie konfiguriert wurde, ist die Einstellung abgeblendet und nicht verfügbar.

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren des Timeoutzeitraums für Cloudblockierung](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Konfigurieren von "Bei erster Anzeige blockieren"](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Schützen Windows PCs mit Endpoint Protection für Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Defender-Cmdlets](/powershell/module/defender/)
- [Verwenden des über die Cloud bereitgestellten Microsoft-Schutzes in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)
- [Erstellen und Bereitstellen von Antischadsoftwarerichtlinien: Cloud-Schutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
