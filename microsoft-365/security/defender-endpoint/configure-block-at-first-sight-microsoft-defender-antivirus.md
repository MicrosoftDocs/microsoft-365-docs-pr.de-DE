---
title: Aktivieren von "Bei erster Sicht blockieren", um Schadsoftware in Sekunden zu erkennen
description: Aktivieren Sie das Feature "Beim ersten Blick blockieren", um Schadsoftware innerhalb von Sekunden zu erkennen und zu blockieren.
keywords: Scannen, Beim ersten Blick blockieren, Schadsoftware, erster Blick, Cloud, Verteidiger, Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079203"
---
# <a name="turn-on-block-at-first-sight"></a>Aktivieren von „Bei erster Anzeige blockieren“

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

In diesem Artikel wird ein Antiviren-/Antischalwarefeature beschrieben, das als "Bei erster Augen blockieren" bezeichnet wird, und es wird beschrieben, wie Sie die Sperre beim ersten Blick für Ihre Organisation aktivieren. 

> [!TIP]
> Dieser Artikel richtet sich an Unternehmensadministratoren und IT-Profis, die Sicherheitseinstellungen für Organisationen verwalten. Wenn Sie kein Enteprise-Administrator oder IT-Pro sind, aber Fragen zum Blockieren auf den ersten Blick haben, finden Sie weitere Informationen unter [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).

## <a name="what-is-block-at-first-sight"></a>Was ist "Beim ersten Blick blockieren"?

Beim ersten Blick blockieren ist ein Bedrohungsschutzfeature des Schutzes der nächsten Generation, das neue Schadsoftware erkennt und innerhalb von Sekunden blockiert. Beim ersten Blick blockieren ist aktiviert, wenn bestimmte Sicherheitseinstellungen aktiviert sind. Zu diesen Einstellungen gehören:

- In der Cloud zugestellter Schutz; 
- Ein angegebenes Zeitlimit für die Beispielübermittlung (z. B. 50 Sekunden); und 
- Eine Hohe Dateiblockierungsstufe. 

In den meisten Unternehmensorganisationen sind die Einstellungen, die zum Aktivieren von "Block at first sight" erforderlich sind, mit Microsoft Defender Antivirus-Bereitstellungen konfiguriert. 

## <a name="how-it-works"></a>Funktionsweise

Wenn Microsoft Defender Antivirus auf eine verdächtige, aber nicht erkannte Datei trifft, fragt es unser Cloud protection-Back-End ab. Das Cloud-Back-End wendet Heuristik, maschinelles Lernen und eine automatisierte Analyse der Datei an, um zu bestimmen, ob die Dateien schädlich sind oder nicht.

Microsoft Defender Antivirus verwendet mehrere Erkennungs- und Verhinderungstechnologien, um präzisen, intelligenten und Echtzeitschutz zu bieten. 

![Liste der Microsoft Defender AV-Engines](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> Weitere Informationen finden Sie in diesem Blog: Erfahren Sie mehr über die erweiterten Technologien im Kern des [Microsoft Defender for Endpoint-Schutzes der nächsten Generation.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)

## <a name="a-few-things-to-know-about-block-at-first-sight"></a>Einige Dinge, die Sie beim ersten Blick zu blockieren wissen sollten

- In Windows 10, Version 1803 oder höher, kann block at first sight nicht tragbare ausführbare Dateien (z. B. JS, VBS oder Makros) und ausführbare Dateien blockieren.

- Block at first sight verwendet nur das Cloud protection-Back-End für ausführbare Dateien und nicht tragbare ausführbare Dateien, die aus dem Internet heruntergeladen werden oder aus der Internetzone stammen. Ein Hashwert der #A0 wird über das Cloud-Back-End überprüft, um zu ermitteln, ob es sich bei der Datei um eine zuvor nicht erkannte Datei handelt.

- Wenn das Cloud-Back-End keine Bestimmung treffen kann, sperrt Microsoft Defender Antivirus die Datei und lädt eine Kopie in die Cloud hoch. Die Cloud führt mehr Analysen durch, um eine Bestimmung zu erreichen, bevor die Datei ausgeführt werden kann, oder blockiert sie in allen zukünftigen Zusammentreffen, je nachdem, ob die Datei als schädlich oder nicht als Bedrohung ermittelt wird.

- In vielen Fällen kann dieser Prozess die Reaktionszeit für neue Schadsoftware von Stunden auf Sekunden reduzieren.

- Sie können [angeben, wie lange](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) die Ausführung einer Datei verhindert werden soll, während der cloudbasierte Schutzdienst die Datei analysiert. Außerdem können Sie [die Nachricht anpassen,](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) die auf den Desktops der Benutzer angezeigt wird, wenn eine Datei blockiert wird. Sie können den Firmennamen, die Kontaktinformationen und die Nachrichten-URL ändern.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Aktivieren von "Bei erster Sicht blockieren" mit Microsoft Intune

> [!TIP]
> Microsoft Intune ist jetzt Teil von Microsoft Endpoint Manager.

1. Navigieren Sie im Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) zu   >  **Gerätekonfigurationsprofile**.

2. Wählen Oder erstellen Sie ein Profil mithilfe des **Profiltyps Geräteeinschränkungen.**

3. Legen Sie **in den Konfigurationseinstellungen** für das Profil Geräteeinschränkungen die folgenden Einstellungen unter Microsoft Defender Antivirus ein oder **bestätigen Sie sie:**

   - **In der Cloud zugestellter Schutz:** Aktiviert
   - **Dateiblockierstufe**: Hoch
   - **Zeiterweiterung für die Dateiprüfung in der Cloud**: 50
   - **Benutzer vor der Beispielübermittlung anforderen:** Alle Daten ohne Aufforderung senden

   ![Intune-Konfiguration](images/defender/intune-block-at-first-sight.png)

4. Speichern Sie Ihre Einstellungen.

> [!TIP]
> - Wenn Sie die Dateiblockierstufe auf **Hoch festlegen,** wird eine starke Erkennungsstufe angewendet. In dem unwahrscheinlichen Fall, dass das Blockieren von Dateien zu einer falsch positiven Erkennung legitimer Dateien führt, kann Ihr Sicherheitsteam [isolierte Dateien wiederherstellen.](./restore-quarantined-files-microsoft-defender-antivirus.md)
> - Weitere Informationen zum Konfigurieren von Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).
> - Eine Liste der Microsoft Defender Antivirus-Geräteeinschränkungen in Intune finden Sie unter Geräteeinschränkung für [Windows 10 (und neuere)](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)Einstellungen in Intune .

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Aktivieren von "Bei erster Sicht blockieren" mit Microsoft Endpoint Manager

> [!TIP]
> Wenn Sie nach Microsoft Endpoint Configuration Manager suchen, ist er jetzt Teil von Microsoft Endpoint Manager.

1. Wechseln Sie in Microsoft Endpoint Manager ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) zu Endpoint **security**  >  **Antivirus**.

2. Wählen Sie eine vorhandene Richtlinie aus, oder erstellen Sie eine neue Richtlinie mithilfe des Microsoft Defender Antivirus-Profiltyps. 

3. Legen Sie die folgenden Konfigurationseinstellungen ein oder bestätigen Sie sie:

   - **Aktivieren des in der Cloud zugestellten Schutzes**: Ja
   - **In der Cloud zugestellte Schutzstufe**: Hoch
   - **Erweitertes Timeout der Defender Cloud in Sekunden**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Blockieren von Einstellungen beim ersten Blick im Endpoint Manager":::

4. Wenden Sie das Microsoft Defender Antivirus-Profil auf eine Gruppe an, z. B. **Alle** Benutzer , **Alle Geräte** oder **Alle Benutzer und Geräte.**

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>Aktivieren von "Bei erster Sicht blockieren" mit Gruppenrichtlinie

> [!NOTE]
> Es wird empfohlen, Intune oder Microsoft Endpoint Manager zu verwenden, um block bei erster Sicht zu aktivieren. 

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.** 

2. Wechseln Sie **mithilfe des Gruppenrichtlinienverwaltungs-Editors** zu **Computerkonfiguration**  >  **Administrative Vorlagen**  >  **Windows-Komponenten** Microsoft Defender  >  **Antivirus**  >  **MAPS**. 

3. Doppelklicken Sie im Abschnitt MAPS auf Konfigurieren des Features **"Bei** erster Sicht blockieren", und legen Sie es auf **Aktiviert**, und wählen Sie dann **OK aus.**

    > [!IMPORTANT]
    > Wenn Sie **auf Immer-Eingabeaufforderung (0)** festlegen, wird der Schutzstatus des Geräts gesenkt. Das Festlegen auf **Nie senden (2)** bedeutet, dass block at first sight nicht funktioniert.

4. Doppelklicken Sie im Abschnitt MAPS auf Dateibeispiele senden, wenn eine weitere Analyse erforderlich **ist,** und legen Sie sie auf **Aktiviert .** Wählen **Sie unter Senden von Dateibeispielen, wenn eine weitere** Analyse erforderlich ist, Die Option Alle Beispiele **senden** aus, und wählen Sie dann **OK aus.**

5. Stellen Sie Ihr Gruppenrichtlinienobjekt wie üblich in Ihrem Netzwerk erneut zur Bereitstellung ein.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a>Bestätigen, dass auf einzelnen Clientgeräten die Option "Beim ersten Blick blockieren" aktiviert ist

Sie können mithilfe der Windows Security-App bestätigen, dass die Sperre beim ersten Blick auf einzelnen Clientgeräten aktiviert ist. Beim ersten Blick blockieren wird automatisch aktiviert, solange **der von der Cloud** übermittelte Schutz und die automatische **Beispielübermittlung** aktiviert sind.

1. Öffnen Sie die Windows Security-App.

2. Wählen **Sie viren & Bedrohungsschutz** aus, und wählen Sie dann unter Einstellungen **&** Virenschutz die Option Einstellungen **verwalten aus.**

   ![Screenshot der Bezeichnung & Virenschutzeinstellungen in der Windows Security App](images/defender/wdav-protection-settings-wdsc.png)

3. Vergewissern Sie sich, dass der von **der Cloud übermittelte Schutz** und die automatische **Beispielübermittlung** aktiviert sind.

> [!NOTE]
> - Wenn die erforderlichen Einstellungen mithilfe von Gruppenrichtlinien konfiguriert und bereitgestellt werden, sind die in diesem Abschnitt beschriebenen Einstellungen ausgegraut und für die Verwendung auf einzelnen Endpunkten nicht verfügbar. 
> - Änderungen, die über ein Gruppenrichtlinienobjekt vorgenommen werden, müssen zuerst auf einzelnen Endpunkten bereitgestellt werden, bevor die Einstellung in den Windows-Einstellungen aktualisiert wird.

## <a name="validate-block-at-first-sight-is-working"></a>Überprüfen, ob block at first sight funktioniert

Um zu überprüfen, ob das Feature funktioniert, befolgen Sie die Anweisungen unter Überprüfen von Verbindungen [zwischen Ihrem Netzwerk und der Cloud.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)

## <a name="turn-off-block-at-first-sight"></a>Deaktivieren des Blocks bei erster Sicht

> [!CAUTION]
> Wenn Sie die Sperre beim ersten Blick deaktivieren, wird der Schutzstatus Ihrer Geräte und Ihres Netzwerks gesenkt.

Wenn Sie die erforderlichen Einstellungen beibehalten möchten, ohne den Schutz beim ersten Blick tatsächlich zu verwenden, können Sie die Blockierung auf den ersten Blick deaktivieren. Sie können die Sperre bei erster Sicht vorübergehend deaktivieren, um zu sehen, wie sich dieses Feature auf Ihr Netzwerk auswirkt. Es wird jedoch nicht empfohlen, den Sperrungsschutz beim ersten Blick dauerhaft zu deaktivieren.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Deaktivieren der Sperre beim ersten Blick mit Microsoft Endpoint Manager

1. Wechseln Sie zu Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) und melden Sie sich an.

2. Wechseln Sie **zu Endpoint Security**  >  **Antivirus,** und wählen Sie dann Ihre Microsoft Defender Antivirus-Richtlinie aus.

3. Wählen **Sie unter Verwalten** die Option Eigenschaften **aus.**

4. Wählen Sie **neben Konfigurationseinstellungen** bearbeiten **aus.**

5. Ändern Sie eine oder mehrere der folgenden Einstellungen:

   - Legen **Sie Den in der Cloud übermittelten Schutz auf** **Nein** oder Nicht **konfiguriert ein.**
   - Legen **Sie in der Cloud zugestellte Schutzstufe** auf Nicht **konfiguriert.**
   - Aktivieren Sie das Kontrollkästchen für **erweitertes Defender Cloud-Timeout in Sekunden**.

6. Überprüfen und speichern Sie Ihre Einstellungen.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>Deaktivieren der Sperre bei erster Sicht mit Gruppenrichtlinie

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann Bearbeiten **aus.**

2. Wechseln Sie **mit dem Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**

3. Erweitern Sie die Struktur über **die Windows-Komponenten**  >  **Microsoft Defender Antivirus**  >  **MAPS**.

4. Doppelklicken Sie **auf Konfigurieren des Features "Bei** erster Sicht blockieren", und legen Sie die Option auf **Deaktiviert .**

    > [!NOTE]
    > Durch das Deaktivieren von Block beim ersten Blick werden die erforderlichen Gruppenrichtlinien nicht deaktiviert oder geändert.

## <a name="not-an-enterprise-admin-or-it-pro"></a>Kein Unternehmensadministrator oder IT-Pro?

Wenn Sie kein Unternehmensadministrator oder IT-Pro sind, aber Fragen zum Blockieren auf den ersten Blick haben, ist dieser Abschnitt für Sie da. Beim ersten Blick blockieren ist ein Feature zum Schutz vor Bedrohungen, das Schadsoftware innerhalb von Sekunden erkennt und blockiert. Obwohl es keine bestimmte Einstellung namens "Bei erster Sicht blockieren" gibt, ist das Feature aktiviert, wenn bestimmte Einstellungen auf Ihrem Gerät konfiguriert sind.

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a>So verwalten Sie block at first sight on or off auf Ihrem eigenen Gerät

Wenn Sie über ein persönliches Gerät verfügen, das nicht von einer Organisation verwaltet wird, fragen Sie sich möglicherweise, wie Sie die Sperre beim ersten Blick ein- oder ausschalten. Sie können die Windows Security-App verwenden, um den Block auf den ersten Blick zu verwalten.

1. Öffnen Sie auf Ihrem Windows 10-Computer die Windows Security-App.

2. Wählen **Sie Virenschutz & Bedrohungsschutz aus.**

3. Wählen **Sie unter & Bedrohungsschutzeinstellungen** die Option Einstellungen verwalten **aus.**

4. Gehen Sie wie folgt vor:

   - Stellen Sie sicher, dass sowohl der in der  **Cloud** zugestellte Schutz als auch die automatische Beispielübermittlung aktiviert sind, um das Blockieren beim ersten Blick zu aktivieren.

   - Deaktivieren Sie den Cloud-zugestellten Schutz oder die **automatische** Beispielübermittlung, um das Blockieren beim ersten Blick **zu deaktivieren.** <br/>
    
     > [!CAUTION]
     > Wenn Sie den Block auf den ersten Blick deaktivieren, wird das Schutzniveau für Ihr Gerät gesenkt. Es wird nicht empfohlen, den Block beim ersten Blick dauerhaft zu deaktivieren. 


## <a name="see-also"></a>Siehe auch

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Aktivieren des in der Cloud übermittelten Schutzes](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Bleiben Sie mit Windows Security geschützt](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)