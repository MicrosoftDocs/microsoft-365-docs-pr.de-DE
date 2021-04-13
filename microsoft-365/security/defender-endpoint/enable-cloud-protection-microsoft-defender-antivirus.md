---
title: Aktivieren des in der Cloud übermittelten Schutzes in Microsoft Defender Antivirus
description: Aktivieren Sie den in der Cloud zugestellten Schutz, um von schnellen und erweiterten Schutzfunktionen zu profitieren.
keywords: Microsoft Defender Antivirus, Antischalware, Sicherheit, Cloud, Beim ersten Blick blockieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: cfaf4563e96568ae26bd990678462836b9202656
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690715"
---
# <a name="turn-on-cloud-delivered-protection"></a>Aktivieren des in der Cloud übermittelten Schutzes

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Der Microsoft Defender Antivirus-Clouddienst ist ein Mechanismus zum Bereitstellen aktualisierten Schutzes für Ihr Netzwerk und Ihre Endpunkte. Obwohl er als Clouddienst bezeichnet wird, handelt es sich nicht nur um den Schutz von Dateien, die in der Cloud gespeichert sind. Stattdessen werden verteilte Ressourcen und maschinelles Lernen verwendet, um Ihren Endpunkten Schutz zu bieten, und dies mit einer Geschwindigkeit, die wesentlich schneller ist als herkömmliche Security Intelligence-Updates.

Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, echtzeitgenauen und intelligenten Schutz zu bieten. Lernen Sie die erweiterten Technologien kennen, die im Kern des [Microsoft Defender for Endpoint-Schutzes der nächsten Generation zu finden sind.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)
![Liste der Microsoft Defender AV-Engines](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Sie können den von Microsoft Defender Antivirus in der Cloud übermittelten Schutz auf verschiedene Weise aktivieren oder deaktivieren:

- Microsoft Intune
- Microsoft Endpoint Configuration Manager
- Gruppenrichtlinien
- PowerShell-Cmdlets.

 Sie können sie auch in einzelnen Clients mit der Windows Security-App aktivieren oder deaktivieren.

Unter [Use Microsoft cloud-delivered protection for](cloud-protection-microsoft-defender-antivirus.md) an overview of Microsoft Defender Antivirus cloud-delivered protection.

Weitere Informationen zu den spezifischen Netzwerkkonnektivitätsanforderungen, um sicherzustellen, dass Ihre Endpunkte eine Verbindung mit dem in der Cloud übermittelten Schutzdienst herstellen können, finden Sie unter [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).

> [!NOTE]
> In Windows 10 gibt es keinen Unterschied zwischen den in diesem Thema beschriebenen **Grundlegenden** und **erweiterten** Berichtsoptionen. Dies ist eine ältere Unterscheidung, und die Auswahl einer der Einstellungen führt zu demselben Grad an cloudbasiertem Schutz. Es gibt keinen Unterschied in der Art oder Menge der freigegebenen Informationen. Weitere Informationen zu den gesammelten Daten finden Sie unter [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a>Aktivieren des in der Cloud übermittelten Schutzes mithilfe von Intune

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.
2. Wählen Sie **im Bereich Start** die Option **Gerätekonfiguration > Profile aus.**
3. Wählen Sie den **Profiltyp** Geräteeinschränkungen aus, den Sie konfigurieren möchten. Wenn Sie einen neuen Profiltyp für **Geräteeinschränkungen** erstellen müssen, lesen Sie [Konfigurieren von Geräteeinschränkungseinstellungen in Microsoft Intune](/intune/device-restrictions-configure).
4. Wählen **Sie Eigenschaften**  >  **Konfigurationseinstellungen aus: Bearbeiten von** Microsoft Defender  >  **Antivirus**.
5. Wählen Sie **auf der Option Cloud-zugestellter Schutz** die Option Aktivieren **aus.**
6. Wählen Sie **im Dropdownmenü Benutzer vor Der Beispielübermittlung** anzeigen die Option **Alle Daten automatisch senden aus.**

Weitere Informationen zu Intune-Geräteprofilen, einschließlich der Erstellung und Konfiguration ihrer Einstellungen, finden Sie unter [Was sind Microsoft Intune-Geräteprofile?](/intune/device-profiles)

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a>Aktivieren des in der Cloud übermittelten Schutzes mithilfe von Microsoft Endpoint Manager

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.
2. Wählen **Sie Endpoint security**  >  **Antivirus** aus.
3. Wählen Sie ein Antivirusprofil aus. (Wenn Sie noch kein Profil haben oder ein neues Profil erstellen möchten, lesen Sie Konfigurieren von Geräteeinschränkungseinstellungen [in Microsoft Intune](/intune/device-restrictions-configure).
4. Wählen Sie **Eigenschaften** aus. Wählen Sie dann neben **Konfigurationseinstellungen** bearbeiten **aus.**
5. Erweitern **Sie den** Cloudschutz, und wählen Sie dann in der Liste der von der Cloud übermittelten **Schutzebenen** eine der folgenden Optionen aus:
    1. **High**: Wendet eine starke Erkennungsstufe an.
    2. **High plus**: Verwendet die **High-Ebene** und wendet zusätzliche Schutzmaßnahmen an (kann sich auf die Clientleistung auswirken).
    3. **Nulltoleranz**: Blockiert alle unbekannten ausführbaren Dateien.
6. Wählen **Sie Überprüfen + Speichern** und dann Speichern **aus.**

Weitere Informationen zum Konfigurieren von Microsoft Endpoint Configuration Manager finden Sie unter [How to create and deploy anmalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a>Aktivieren des in der Cloud übermittelten Schutzes mithilfe von Gruppenrichtlinien

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration**.

3. Wählen Sie **Administrative Vorlagen aus.**

4. Erweitern der Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > MAPS**

5. Doppelklicken Sie auf **Microsoft MAPS beitreten.** Stellen Sie sicher, dass die Option aktiviert ist und auf **Basic MAPS** oder Advanced MAPS **festgelegt ist.** Wählen Sie **OK** aus.

6. Doppelklicken Sie **auf Dateibeispiele senden, wenn eine weitere Analyse erforderlich ist.** Stellen Sie sicher, dass die erste Option auf **Aktiviert festgelegt** ist und dass die anderen Optionen auf eine der folgenden Optionen festgelegt sind:

    1. **Senden sicherer Beispiele** (1)
    2. **Senden aller Beispiele** (3)

        >[!NOTE]
        > Die **Option Sichere Beispiele** senden (1) bedeutet, dass die meisten Beispiele automatisch gesendet werden. Dateien, die wahrscheinlich personenbezogene Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.

        > [!WARNING]
        > Wenn Sie die Option **auf Always Prompt** (0) festlegen, wird der Schutzstatus des Geräts gesenkt. Das Festlegen auf **Nie senden** (2) bedeutet, dass das [Feature "Bei](configure-block-at-first-sight-microsoft-defender-antivirus.md) erster Sicht blockieren" von Microsoft Defender for Endpoint nicht funktioniert.

7. Wählen Sie **OK** aus.

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a>Verwenden von PowerShell-Cmdlets zum Aktivieren des in der Cloud übermittelten Schutzes

Die folgenden Cmdlets können den in der Cloud zugestellten Schutz aktivieren:

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

Weitere Informationen zur Verwendung von PowerShell mit Microsoft Defender Antivirus finden Sie unter [Use PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and run Microsoft Defender Antivirus and Defender [cmdlets](/powershell/module/defender/). [Richtlinien-CSP – Defender](/windows/client-management/mdm/policy-csp-defender) verfügt auch über weitere Informationen speziell zu [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).

>[!NOTE]
> Sie können auch **-SubmitSamplesConsent** auf `SendSafeSamples` (die Standardeinstellung) `NeverSend` oder `AlwaysPrompt` festlegen. Die `SendSafeSamples` Einstellung bedeutet, dass die meisten Beispiele automatisch gesendet werden. Dateien, die wahrscheinlich personenbezogene Informationen enthalten, werden weiterhin aufgefordert und erfordern eine zusätzliche Bestätigung.

>[!WARNING]
> Setting **-SubmitSamplesConsent** to or `NeverSend` will lower the protection level of the `AlwaysPrompt` device. Darüber hinaus bedeutet das Festlegen, dass das Feature "Bei erster Sicht `NeverSend` blockieren" von Microsoft Defender for Endpoint nicht funktioniert. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a>Aktivieren des in der Cloud übermittelten Schutzes mithilfe von Windows Management Instruction (WMI)

Verwenden Sie [ **die Set-Methode** **der MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) für die folgenden Eigenschaften:

```WMI
MAPSReporting
SubmitSamplesConsent
```

Weitere Informationen zu zulässigen Parametern finden Sie [unter Windows Defender WMIv2-APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a>Aktivieren des in der Cloud übermittelten Schutzes auf einzelnen Clients mit der Windows Security-App

> [!NOTE]
> Wenn die Einstellung Lokale Einstellung für die **Berichterstellung** von Microsoft MAPS-Gruppenrichtlinien konfigurieren auf **Deaktiviert** festgelegt ist, ist die cloudbasierte Schutzeinstellung in den **Windows-Einstellungen** ausgegraut und nicht verfügbar. Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen werden, müssen zuerst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.

1. Öffnen Sie die Windows Security-App, indem Sie das Schildsymbol in der Taskleiste auswählen oder im Startmenü nach **Defender suchen.**

2. Wählen Sie **die Kachel &** Bedrohungsschutz (oder das Schildsymbol auf der linken Menüleiste) und dann die Bezeichnung **Virenschutzeinstellungen &** aus:

    ![Screenshot der Bezeichnung & Virenschutzeinstellungen in der Windows Security App](images/defender/wdav-protection-settings-wdsc.png)

3. Vergewissern Sie **sich, dass cloudbasierter Schutz** und **automatische Beispielübermittlung** auf **Ein umgeschaltet werden.**

> [!NOTE]
> Wenn die automatische Beispielübermittlung mit Gruppenrichtlinien konfiguriert wurde, ist die Einstellung ausgegraut und nicht verfügbar.

## <a name="related-articles"></a>Verwandte Artikel

- [Konfigurieren des Timeoutzeitraums für Cloudblocks](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [Konfigurieren von Block bei erster Sicht](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Verwenden von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]
- [Defender-Cmdlets](/powershell/module/defender/)
- [Verwenden des in der Cloud übermittelten Microsoft-Schutzes in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md)
- [Erstellen und Bereitstellen von Antischalwarerichtlinien: Cloudschutzdienst](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)