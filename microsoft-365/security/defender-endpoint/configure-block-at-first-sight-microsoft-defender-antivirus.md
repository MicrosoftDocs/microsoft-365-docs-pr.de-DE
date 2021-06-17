---
title: Aktivieren von „Beim ersten Sichten blockieren“ zum Erkennen von Schadsoftware innerhalb von Sekunden
description: Aktivieren Sie das Feature „Beim ersten Sichten blockieren“, um Schadsoftware innert Sekunden zu erkennen und zu blockieren.
keywords: scannen, beim ersten Sichten blockieren, Schadsoftware, erstes Erkennen, Cloud, Defender, Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/15/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 3a5f766e21afcb29d3503345a49637061b5f0e38
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2021
ms.locfileid: "52964700"
---
# <a name="turn-on-block-at-first-sight"></a>Aktivieren von „Beim ersten Sichten blockieren“

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Dieser Artikel beschreibt ein Antivirus-/Antimalware-Feature, die als „Beim ersten Sichten blockieren“ bekannt ist, und er beschreibt, wie Sie „Beim ersten Sichten blockieren“ für Ihre Organisation aktivieren. 

> [!TIP]
> Dieser Artikel ist für Unternehmensadministratoren und IT-Profis gedacht, welche die Sicherheitseinstellungen für Organisationen verwalten. Wenn Sie kein Unternehmensadministrator oder IT-Profi sind, aber Fragen bezüglich „Beim ersten Sichten blockieren“ haben, lesen Sie den Abschnitt [Kein Unternehmensadministrator oder IT-Profi?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>Was ist „Beim ersten Sichten blockieren“?

„Beim ersten Sichten blockieren“ ist ein Bedrohungsschutzfeature der nächsten Generation, das neue Malware erkennt und sie innerhalb von Sekunden blockiert. „Beim ersten Sichten blockieren“ ist aktiviert, wenn gewisse Sicherheitseinstellungen aktiviert sind. Dazu zählen die folgenden Einstellungen:

- Aus der Cloud bereitgestellter Schutz; 
- Ein angegebenes Zeitlimit für die Stichprobenübermittlung (z. B. 50 Sekunden); und 
- Eine Dateiblockierungsstufe von „hoch“. 

In den meisten Unternehmensorganisationen werden die Einstellungen, die für das Aktivieren von „Beim ersten Sichten blockieren“ benötigt werden, mit Microsoft Defender Antivirus-Bereitstellungen konfiguriert. 

## <a name="how-it-works"></a>So funktioniert es

Wenn Microsoft Defender Antivirus eine verdächtige, aber nicht erkannte Datei findet, wird unser Back-End für Cloudschutz abgefragt. Das Cloud-Back-End wendet Heuristiken, maschinelles Lernen und automatisiertes Analysieren der Datei an, um festzustellen, ob die Dateien bösartig oder keine Bedrohung sind.

Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Präventionstechnologien, um präzisen, intelligenten und Echtzeit-Schutz zu bieten. 

![Liste der Microsoft Defender Antiviren-Module](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Weitere Informationen finden Sie unter [(Blog) Lernen Sie die fortschrittlichen Technologien kennen, die den Kern des Schutzes der nächsten Generation für Microsoft Defender für Endpunkt bilden](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Einige Dinge, die man über „Beim ersten Sichten blockieren“ wissen sollte

- In Windows 10, Version 1803, können mit „Beim ersten Sichten blockieren“ nicht portable ausführbare Dateien (wie JS, VBS oder Makros) und ausführbare Dateien blockiert werden.

- Das Feature „Beim ersten Sichten blockieren“ nutzt das Back-End für Cloudschutz nur für ausführbare und nicht portable ausführbare Dateien, die aus dem Internet heruntergeladen wurden oder aus der Internetzone stammen. Ein Hashwert der EXE-Datei wird über das Cloud-Back-End überprüft, um zu ermitteln, ob es sich um eine zuvor nicht erkannte Datei handelt.

- Wenn das Cloud-Back-End keinen Entscheid fällen kann, sperrt Microsoft Defender Antivirus die Datei und lädt eine Kopie in die Cloud hoch. Die Cloud führt weitere Analysen durch, um zu einer Entscheidung zu kommen, bevor entweder die Datei ausgeführt werden darf, oder bei jedem zukünftigen Auftreten blockiert wird, je nachdem, ob die Datei als bösartig oder als keine Bedrohung eingestuft wurde.

- In vielen Fällen kann dieser Prozess die Reaktionszeit auf neue Schadsoftware von Stunden auf Sekunden reduzieren.

- Sie können [angeben, wie lange die Ausführung einer Datei verhindert werden soll](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md), während der cloudbasierte Schutzdienst die Datei analysiert. Sie können auch [die Nachricht auf den Desktops des Benutzers anpassen](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md), wenn eine Datei blockiert ist. Sie können den Firmennamen, die Kontaktinformationen und die Nachrichten-URL ändern.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Aktivieren von „Beim ersten Sichten blockieren“ mit Microsoft Intune

> [!TIP]
> Microsoft Intune ist jetzt Bestandteil von Microsoft Endpoint Manager.

1. Navigieren Sie im Microsoft Endpoint Manager-Admin Center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) zu **Geräte** > **Konfigurationsprofile**.

2. Wählen oder erstellen Sie ein Profil mit dem Profiltyp **Geräteeinschränkungen**.

3. Setzen oder bestätigen Sie in den **Konfigurationseinstellungen** des Profils für die Geräteeinschränkungen die folgenden Einstellungen unter **Microsoft Defender Antivirus**:

   - **Aus der Cloud bereitgestellter Schutz**: Aktiviert
   - **Dateiblockierungsstufe**: Hoch
   - **Zeitverlängerung für Dateiüberprüfung durch die Cloud**: 50
   - **Benutzer vor Stichprobenübermittlung auffordern**: Alle Daten ohne Aufforderung senden

   ![Intune-Konfiguration](images/defender/intune-block-at-first-sight.png)

4. Speichern Sie Ihre Einstellungen.

> [!TIP]
> - Das Festlegen der Dateiblockierungsstufe auf **Hoch** wendet eine starke Erkennungsleistung an. Im unwahrscheinlichen Fall, dass die Dateisperrung zu einer falsch positiven Erkennung legitimer Dateien führt, kann Ihr Sicherheitsteam [in Quarantäne gestellten Dateien wiederherstellen](./restore-quarantined-files-microsoft-defender-antivirus.md).
> - Weitere Informationen zum Konfigurieren von Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter [Konfigurieren von Einstellungen für Geräteeinschränkungen in Microsoft Intune](/intune/device-restrictions-configure).
> - Eine Liste der Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter [Einstellungen für Geräteeinschränkungen für Windows 10 (und neuer) in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Aktivieren von „Beim ersten Sichten blockieren“ mit Microsoft Endpoint Manager

> [!TIP]
> Wenn Sie den Microsoft Endpoint Configuration Manager suchen, finden Sie ihn jetzt als Teil von Microsoft Endpoint Manager.

1. Im Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) gehen sie zu **Endpunktsicherheit** > **Antivirus**.

2. Wählen Sie eine bestehende Richtlinie aus, oder erstellen Sie eine neue Richtlinie mit dem Profiltyp **Microsoft Defender Antivirus**.

3. Legen Sie die folgenden Konfigurationseinstellungen fest, oder bestätigen Sie diese:

   - **Aus der Cloud bereitgestellten Schutz aktivieren**: Ja
   - **Aus der Cloud bereitgestellte Schutzstufe**: Hoch
   - **Defender Cloud – erweitertes Zeitlimit in Sekunden**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="„Beim ersten Sichten blockieren“ in Endpoint Manager":::

4. Wenden Sie das Microsoft Defender Antivirus-Profil auf eine Gruppe an, wie z. B. **Alle Benutzer**, **Alle Geräte** oder **Alle Benutzer und Geräte**.

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Aktivieren von „Beim ersten Sichten blockieren“ mit der Gruppenrichtlinie

> [!NOTE]
> Wir empfehlen, Intune oder Microsoft Endpoint Manager zu verwenden, um „Beim ersten Sichten blockieren“ zu aktivieren. 

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus. 

2. Gehen Sie mithilfe des **Gruppenrichtlinien-Verwaltungseditors** zu **Computer-Konfiguration** > **Administrative Vorlagen** > **Windows-Komponenten** > **Microsoft Defender Antivirus** > **MAPS**. 

3. Doppelklicken Sie im Abschnitt MAPS auf **Konfigurieren des Features „Beim ersten Sichten blockieren“**, legen Sie es auf **Aktiviert** fest, und wählen Sie dann **OK** aus.

    > [!IMPORTANT]
    > Das Festlegen auf **Immer auffordern (0)** wird den Schutzzustand des Geräts verringern. Das Festlegen auf **Niemals senden (2)** bedeutet, dass „Beim ersten Sichten blockieren“ nicht funktioniert.

4. Doppelklicken Sie im Abschnitt MAPS auf **Dateistichproben senden, wenn eine weitere Analyse erforderlich ist**, und legen Sie dies auf **Aktiviert** fest. Wählen Sie unter **Dateistichproben senden, wenn eine weitere Analyse erforderlich ist** die Option **Alle Stichproben senden** aus und dann **OK**.

5. Stellen Sie Ihr Gruppenrichtlinien-Objekt erneut in Ihrem Netzwerk bereit, so wie Sie dies normalerweise tun.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Bestätigen der Aktivierung von „Beim ersten Sichten blockieren“ auf einzelnen Clientgeräten

Mit der Windows-Sicherheit-App können Sie überprüfen, ob „Beim ersten Sichten blockieren“ auf einzelnen Clientgeräten aktiviert ist. Die Option „Beim ersten Sichten blockieren“ wird automatisch aktiviert, solange **Aus der Cloud bereitgestellter Schutz** und **Automatische Übermittlung von Stichproben** beide aktiviert sind.

1. Öffnen Sie die Windows-Sicherheit-App.

2. Wählen Sie **Viren- & Bedrohungsschutz** und dann unter **Einstellungen für Viren- & Bedrohungsschutz** die Option **Einstellungen verwalten** aus.

   ![Screenshot der Bezeichnung für die Einstellungen des Viren- und Bedrohungsschutzes in der Windows-Sicherheit-App](images/defender/wdav-protection-settings-wdsc.png)

3. Bestätigen Sie, dass **Aus der Cloud bereitgestellter Schutz** und **Automatische Übermittlung von Stichproben** beide aktiviert sind.

> [!NOTE]
> - Wenn die erforderlichen Einstellungen konfiguriert sind und mithilfe von Gruppenrichtlinien bereitgestellt werden, sind die Einstellungen in diesem Abschnitt grau hinterlegt und stehen auf einzelnen Endpunkten nicht zur Verfügung. 
> - Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen wurden, müssen zunächst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.

## <a name="validate-block-at-first-sight-is-working"></a>Validieren, dass „Beim ersten Sichten blockieren“ funktioniert

Um zu validieren, ob das Feature funktioniert, laden Sie die [Beispieldatei „Beim ersten Sichten blockieren“](https://demo.wd.microsoft.com/Page/BAFS) herunter. Zum Herunterladen der Datei benötigen Sie ein Konto in Azure AD, dem entweder die Rolle „Sicherheitsadministrator“ oder „Globaler Administrator“ zugewiesen ist.

Um zu validieren, ob der Cloud-aktivierte Schutz funktioniert, folgen Sie der Anleitung in [Validieren der Verbindungen zwischen Ihrem Netzwerk und der Cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud). 

## <a name="turn-off-block-at-first-sight"></a>Deaktivieren von „Beim ersten Sichten blockieren“

> [!CAUTION]
> Das Deaktivieren der Option „Beim ersten Sichten blockieren“ wird den Schutzstatus Ihres Geräts / Ihrer Geräte und Ihres Netzwerks verringern.

Sie könnten „Beim ersten Sichten blockieren“ deaktivieren, wenn Sie die erforderlichen Einstellungen beibehalten möchten, ohne die Schutzeinstellung „Beim ersten Sichten blockieren“ tatsächlich zu verwenden. Sie könnten „Beim ersten Sichten blockieren“ temporär deaktivieren, um zu sehen, wie sich dieses Feature auf Ihr Netzwerk auswirkt. Wir empfehlen jedoch nicht, den Schutz von „Beim ersten Sichten blockieren“ permanent zu deaktivieren.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Deaktivieren von „Beim ersten Sichten blockieren“ mit Microsoft Endpoint Manager

1. Gehen Sie zum Microsoft Endpoint Manager Admin Center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) und melden Sie sich an.

2. Gehen Sie zu **Endpunktsicherheit** > **Antivirus**, und wählen Sie dann Ihre Microsoft Defender Antivirus-Richtlinie aus.

3. Wählen Sie unter **Verwalten** die Option **Eigenschaften** aus.

4. Wählen Sie direkt neben **Konfigurationseinstellungen** die Option **Bearbeiten** aus.

5. Ändern Sie eine oder mehrere der folgenden Einstellungen:

   - Legen Sie **Aus der Cloud bereitgestellter Schutz aktivieren** auf **Nein** oder **Nicht konfiguriert** fest.
   - Legen Sie **Aus der Cloud bereitgestellte Schutzebene** auf **Nicht konfiguriert** fest.
   - Deaktivieren Sie das Kontrollkästchen **Defender Cloud – erweitertes Zeitlimit in Sekunden**.

6. Überprüfen und Speichern Sie Ihre Einstellungen.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Deaktivieren von „Beim ersten Sichten blockieren“ mit der Gruppenrichtlinie

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann **Bearbeiten** aus.

2. Gehen Sie mithilfe des **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.

3. Erweitern Sie die Struktur bis zu **Windows-Komponenten** > **Microsoft Defender Antivirus** > **MAPS**.

4. Doppelklicken Sie auf **Konfigurieren des Features „Beim ersten Sichten blockieren“**, und legen Sie die Option auf **Deaktiviert** fest.

    > [!NOTE]
    > Das Deaktivieren von „Beim ersten Sichten blockieren“ deaktiviert oder verändert die erforderlichen Gruppenrichtlinien nicht.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Kein Unternehmensadministrator oder IT-Profi?

Wenn Sie kein Unternehmensadministrator oder IT-Profi sind, aber Fragen bezüglich „Beim ersten Sichten blockieren“ haben, dann ist dieser Abschnitt für Sie. „Beim ersten Sichten blockieren“ ist ein Bedrohungsschutzfeature, das neue Malware erkennt und sie innerhalb von Sekunden blockiert. Obwohl es keine spezifische Einstellung gibt, die „Beim ersten Sichten blockieren“ genannt wird, wird das Feature aktiviert, wenn gewisse Einstellungen auf Ihrem Gerät konfiguriert sind.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>So aktivieren oder deaktivieren Sie „Beim ersten Sichten blockieren“ auf Ihrem eigenen Gerät

Wenn Sie ein persönliches Gerät haben, das nicht von einer Organisation verwaltet wird, dann fragen Sie sich möglicherweise, wie Sie „Beim ersten Sichten blockieren“ aktivieren oder deaktivieren können. Sie können die Windows-Sicherheit-App verwenden, um „Beim ersten Sichten blockieren“ zu verwalten.

1. Öffnen Sie auf Ihrem Windows 10-Computer die Windows-Sicherheit-App.

2. Wählen Sie **Viren- und Bedrohungsschutz** aus.

3. Wählen Sie unter **Einstellungen für Viren- & Bedrohungsschutz** die Option **Einstellungen verwalten** aus.

4. Führen Sie einen der folgenden Schritte aus:

   - Um „Beim ersten Sichten blockieren“ zu aktivieren, stellen Sie sicher, dass sowohl **Aus der Cloud bereitgestellter Schutz** wie auch **Automatische Übermittlung von Stichproben** aktiviert sind.

   - Um „Beim ersten Sichten blockieren“ zu deaktivieren, deaktivieren Sie **Aus der Cloud bereitgestellter Schutz** oder **Automatische Übermittlung von Stichproben**. <br/>
    
     > [!CAUTION]
     > Das Deaktivieren von „Beim ersten Sichten blockieren“ verringert die Schutzebene für Ihr Gerät. Wir empfehlen nicht, „Beim ersten Sichten blockieren“ permanent zu deaktivieren. 


## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Aus der Cloud bereitgestellten Schutz aktivieren](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Mit Windows-Sicherheit geschützt bleiben](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
