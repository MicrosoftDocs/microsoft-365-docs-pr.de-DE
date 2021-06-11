---
title: Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt
description: Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse in Microsoft Defender für Endpunkt behandeln.
keywords: Antivirus, Ausnahme, Ausschluss, Microsoft Defender für Endpunkt, falsch positiv, falsch negativ, blockierte Datei, blockierte URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
- m365solution-scenario
- m365scenario-fpfn
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs, yonghree, jcedola
ms.custom: FPFN
ms.openlocfilehash: 1cd29c3a631334ee3a2791cca3c7ac1c83a1692f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903828"
---
# <a name="address-false-positivesnegatives-in-microsoft-defender-for-endpoint"></a>Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146806)

In Endpunktschutzlösungen ist ein falsch positives Ergebnis eine Entität, z. B. eine Datei oder ein Prozess, die erkannt und als bösartig identifiziert wurde, obwohl die Entität keine Bedrohung ist. Ein falsch negativer Wert ist eine Entität, die nicht als Bedrohung erkannt wurde, obwohl sie tatsächlich bösartig ist. Falsch positive/negative Ergebnisse können bei jeder Bedrohungsschutzlösung auftreten, einschließlich [Microsoft Defender für Endpunkt.](microsoft-defender-endpoint.md)

![Definition von falsch positiven und negativen Ergebnissen in Defender für Endpunkt](images/false-positives-overview.png)

Glücklicherweise können Schritte unternommen werden, um diese Art von Problemen zu beheben und zu reduzieren. Wenn Sie falsch positive/negative Ergebnisse in [Microsoft 365 Defender](microsoft-defender-security-center.md) (früher Microsoft Defender Security Center) sehen, können Ihre Sicherheitsvorgänge mithilfe des folgenden Prozesses Maßnahmen ergreifen, um sie zu beheben:

1.  [Überprüfen und Klassifizieren von Warnungen](#part-1-review-and-classify-alerts) 
2.  [Überprüfen von Abhilfemaßnahmen, die durchgeführt wurden](#part-2-review-remediation-actions)
3.  [Überprüfen und Definieren von Ausschlüssen](#part-3-review-or-define-exclusions)
4.  [Übermitteln einer Entität zur Analyse](#part-4-submit-a-file-for-analysis)
5.  [Überprüfen und Anpassen Ihrer Einstellungen für den Bedrohungsschutz](#part-5-review-and-adjust-your-threat-protection-settings)

Sie können Hilfe erhalten, wenn Sie nach ausführung der in diesem Artikel beschriebenen Aufgaben weiterhin Probleme mit falsch positiven/negativen Ergebnissen haben. Benötigen [Sie weiterhin Hilfe?](#still-need-help)

![Schritte zum Beheben falsch positiver und negativer Ergebnisse](images/false-positives-step-diagram.png)

> [!NOTE]
> Dieser Artikel dient als Leitfaden für Sicherheitsoperatoren und Sicherheitsadministratoren, die [Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md)verwenden.

## <a name="part-1-review-and-classify-alerts"></a>Teil 1: Überprüfen und Klassifizieren von Warnungen

Wenn eine [Warnung](alerts.md) angezeigt wird, die ausgelöst wurde, weil etwas als bösartig oder verdächtig erkannt wurde, das nicht hätte sein sollen, können Sie die Warnung für diese Entität unterdrücken. Sie können auch Warnungen unterdrücken, die nicht notwendigerweise falsch positive Ergebnisse sind, aber unwichtig sind. Es wird empfohlen, warnungen auch zu klassifizieren. 

Die Verwaltung Ihrer Warnungen und das Klassifizieren von wahr/falsch positiven Ergebnissen hilft, Ihre Bedrohungsschutzlösung zu trainieren, und kann die Anzahl falsch positiver oder falsch negativer Ergebnisse im Laufe der Zeit reduzieren. Diese Schritte tragen auch dazu bei, Rauschen in Ihrem Dashboard für Sicherheitsvorgänge zu reduzieren, sodass sich Ihr Sicherheitsteam auf Arbeitsaufgaben mit höherer Priorität konzentrieren kann.

### <a name="determine-whether-an-alert-is-accurate"></a>Ermitteln, ob eine Warnung korrekt ist

Bevor Sie eine Warnung klassifizieren oder unterdrücken, bestimmen Sie, ob die Warnung korrekt, falsch positiv oder gutartig ist.

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **warnungswarteschlange** aus.

3. Wählen Sie eine Warnung aus, um weitere Details zur Warnung zu erhalten. (Siehe ["Warnungen in Microsoft Defender für Endpunkt](review-alerts.md)überprüfen".)

4. Führen Sie je nach Warnungsstatus die in der folgenden Tabelle beschriebenen Schritte aus: 

| Warnungsstatus | Vorgehensweise |
|:---|:---|
| Die Warnung ist korrekt. | Weisen Sie die Warnung zu, und [untersuchen Sie sie](investigate-alerts.md) weiter. |
| Die Warnung ist ein falsch positives Ergebnis. | 1. [Klassifizieren Sie die Warnung](#classify-an-alert) als falsch positives Ergebnis. <br/>2. [Die Warnung unterdrücken.](#suppress-an-alert) <br/> 3. [Erstellen Sie einen Indikator](#indicators-for-microsoft-defender-for-endpoint) für Microsoft Defender für Endpunkt. <br/> 4. [Übermitteln Sie eine Datei zur Analyse an Microsoft.](#part-4-submit-a-file-for-analysis) |
| Die Warnung ist korrekt, aber gutartig (unwichtig) | [Klassifizieren Sie die Warnung](#classify-an-alert) als wahr positives Ergebnis, und [unterdrücken Sie die Warnung.](#suppress-an-alert) |

### <a name="classify-an-alert"></a>Klassifizieren einer Warnung

Warnungen können im Microsoft 365 Defender als falsch positive ergebnisse oder als wahr positive Ergebnisse klassifiziert werden. Das Klassifizieren von Warnungen hilft beim Trainieren von Microsoft Defender für Endpunkt, sodass im Laufe der Zeit mehr echte Warnungen und weniger falsche Warnungen angezeigt werden.

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **"Warnungswarteschlange"** aus, und wählen Sie dann eine Warnung aus.

3. Wählen Sie für die ausgewählte Warnung die Warnung **"Aktionen**  >  **verwalten" aus.** Ein Flyoutbereich wird geöffnet.

4. Wählen Sie im Abschnitt **"Warnung verwalten"** entweder **"True"** oder **"False" aus.** (Verwenden Sie **die "False"-Warnung,** um ein falsch positives Ergebnis zu klassifizieren.)

> [!TIP]
> Weitere Informationen zum Unterdrücken von Warnungen finden Sie unter [Verwalten von Microsoft Defender für Endpunkt-Warnungen.](/microsoft-365/security/defender-endpoint/manage-alerts) Wenn Ihre Organisation einen SIEM-Server (Security Information and Event Management) verwendet, müssen Sie auch dort eine Unterdrückungsregel definieren. 

### <a name="suppress-an-alert"></a>Unterdrücken einer Warnung

Wenn Sie Warnungen haben, bei denen es sich entweder um falsch positive Ergebnisse oder um echte positive Ergebnisse handelt, aber für unwichtige Ereignisse, können Sie diese Warnungen im Microsoft 365 Defender unterdrücken. Das Unterdrücken von Warnungen trägt dazu bei, Rauschen im Dashboard ihres Sicherheitsbetriebs zu reduzieren. 

1. Wechseln Sie zum Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie im Navigationsbereich **warnungswarteschlange** aus.

3. Wählen Sie eine Warnung aus, die Sie unterdrücken möchten, um den **Detailbereich** zu öffnen.

4. Wählen Sie im **Detailbereich** die Auslassungszeichen (**...**) aus, und erstellen Sie dann **eine Unterdrückungsregel.**

5. Geben Sie alle Einstellungen für die Unterdrückungsregel an, und wählen Sie dann **Speichern** aus.

> [!TIP]
> Benötigen Sie Hilfe bei Unterdrückungsregeln? Siehe ["Warnung unterdrücken" und Erstellen einer neuen Unterdrückungsregel.](/microsoft-365/security/defender-endpoint/manage-alerts#suppress-an-alert-and-create-a-new-suppression-rule)

## <a name="part-2-review-remediation-actions"></a>Teil 2: Überprüfen von Korrekturmaßnahmen

[Abhilfemaßnahmen,](manage-auto-investigation.md#remediation-actions)z. B. das Senden einer Datei in Quarantäne oder das Beenden eines Prozesses, werden für Entitäten (z. B. Dateien) ausgeführt, die als Bedrohungen erkannt werden. Verschiedene Arten von Korrekturmaßnahmen erfolgen automatisch durch automatische Untersuchung und Microsoft Defender Antivirus:   
- Isolieren einer Datei
- Entfernen eines Registrierungsschlüssels
- Beenden eines Prozesses
- Beenden eines Diensts
- Deaktivieren eines Treibers
- Entfernen einer geplanten Aufgabe

Andere Aktionen, z. B. das Starten eines Antivirenscans oder das Sammeln eines Untersuchungspakets, erfolgen manuell oder über [Live Response.](live-response.md) Aktionen, die über Live Response ausgeführt werden, können nicht rückgängig gemacht werden.

Nachdem Sie Ihre Warnungen überprüft haben, besteht der nächste Schritt darin, Korrekturmaßnahmen zu [überprüfen.](manage-auto-investigation.md) Wenn aufgrund falsch positiver Ergebnisse Aktionen ausgeführt wurden, können Sie die meisten Arten von Korrekturaktionen rückgängig machen. Insbesondere können Sie folgende Aktionen ausführen:

- [Wiederherstellen einer isolierten Datei aus dem Info-Center](#restore-a-quarantined-file-from-the-action-center)
- [Mehrere Aktionen gleichzeitig rückgängigmachen](#undo-multiple-actions-at-one-time)
- [Entfernen Sie eine Datei aus der Quarantäne auf mehreren Geräten.](#remove-a-file-from-quarantine-across-multiple-devices)  und 
- [Datei aus der Quarantäne wiederherstellen](#restore-file-from-quarantine)

Wenn Sie mit dem Überprüfen und Rückgängigmachen von Aktionen fertig sind, die als Ergebnis falsch positiver Ergebnisse ausgeführt wurden, fahren Sie mit der [Überprüfung oder Definition von Ausschlüssen](#part-3-review-or-define-exclusions)fort.

### <a name="review-completed-actions"></a>Überprüfen abgeschlossener Aktionen

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an. 

2. Wählen Sie die Registerkarte **"Verlauf",** um eine Liste der ausgeführten Aktionen anzuzeigen.  

3. Wählen Sie ein Element aus, um weitere Details zu der durchgeführten Korrekturaktion anzuzeigen.

### <a name="restore-a-quarantined-file-from-the-action-center"></a>Wiederherstellen einer isolierten Datei aus dem Info-Center

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an. 

2. Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie rückgängig machen möchten.

3. Wählen Sie im Flyoutbereich **"Rückgängig"** aus. Wenn die Aktion mit dieser Methode nicht rückgängig sein kann, wird keine Schaltfläche **"Rückgängig"** angezeigt. (Weitere Informationen finden Sie unter ["Abgeschlossene Aktionen rückgängig](manage-auto-investigation.md#undo-completed-actions)machen".)

### <a name="undo-multiple-actions-at-one-time"></a>Mehrere Aktionen gleichzeitig rückgängigmachen

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an. 

2. Wählen Sie auf der Registerkarte **"Verlauf"** die Aktionen aus, die Sie rückgängig machen möchten.

3. Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig"** aus.

### <a name="remove-a-file-from-quarantine-across-multiple-devices"></a>Entfernen einer Datei aus der Quarantäne auf mehreren Geräten 

> [!div class="mx-imgBorder"]
> ![Quarantänedatei](images/autoir-quarantine-file-1.png)

1. Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an. 

2. Wählen Sie auf der Registerkarte **"Verlauf"** eine Datei mit dem Aktionstyp **"Quarantänedatei"** aus.

3. Klicken Sie im Bereich auf der rechten Seite des **Bildschirms auf X weitere Instanzen dieser Datei anwenden,** und wählen Sie dann **Rückgängig** aus.

### <a name="restore-file-from-quarantine"></a>Datei aus der Quarantäne wiederherstellen

Sie können ein Rollback ausführen und eine Datei aus der Quarantäne entfernen, wenn Sie nach einer Untersuchung festgestellt haben, dass sie sauber ist. Führen Sie den folgenden Befehl auf jedem Gerät aus, auf dem die Datei unter Quarantäne gestellt wurde.

1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechten auf dem Gerät:

   1. Wechseln Sie zu **Start**, und geben Sie _cmd_ ein.

   1. Klicken Sie mit der rechten Maustaste auf **die Eingabeaufforderung,** und wählen Sie **"Als Administrator ausführen"** aus.

2. Geben Sie den folgenden Befehl ein, und drücken Sie die **EINGABETASTE:**

    ```console
    "ProgramFiles%\Windows Defender\MpCmdRun.exe" –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
    ```

    > [!IMPORTANT]
    > In einigen Szenarien wird **der ThreatName** möglicherweise als `EUS:Win32/
      CustomEnterpriseBlock!cl` . Defender für Endpunkt stellt alle benutzerdefinierten blockierten Dateien wieder her, die in den letzten 30 Tagen auf diesem Gerät unter Quarantäne gestellt wurden.
    > Eine Datei, die als potenzielle Netzwerkgefährdung unter Quarantäne gestellt wurde, kann möglicherweise nicht wiederhergestellt werden. Wenn ein Benutzer versucht, die Datei nach der Quarantäne wiederherzustellen, kann auf diese Datei möglicherweise nicht zugegriffen werden. Dies kann darauf zurückzuführen sein, dass das System nicht mehr über Netzwerkanmeldeinformationen für den Zugriff auf die Datei verfügt. In der Regel ist dies ein Ergebnis einer temporären Anmeldung bei einem System oder freigegebenen Ordner, und die Zugriffstoken sind abgelaufen.

3. Klicken Sie im Bereich auf der rechten Seite des **Bildschirms auf X weitere Instanzen dieser Datei anwenden,** und wählen Sie dann **Rückgängig** aus. 

## <a name="part-3-review-or-define-exclusions"></a>Teil 3: Überprüfen oder Definieren von Ausschlüssen

Ein Ausschluss ist eine Entität, z. B. eine Datei oder URL, die Sie als Ausnahme für Korrekturaktionen angeben. Die ausgeschlossene Entität kann weiterhin erkannt werden, es werden jedoch keine Korrekturaktionen für diese Entität ausgeführt. Das heißt, die erkannte Datei oder der erkannte Prozess wird von Microsoft Defender für Endpunkt nicht angehalten, in Quarantäne gestellt, entfernt oder anderweitig geändert. 

Führen Sie die folgenden Aufgaben aus, um Ausschlüsse in Microsoft Defender für Endpunkt zu definieren:
- [Definieren von Ausschlüssen für Microsoft Defender Antivirus](#exclusions-for-microsoft-defender-antivirus)
- [Erstellen von "Zulassen"-Indikatoren für Microsoft Defender für Endpunkt](#indicators-for-microsoft-defender-for-endpoint)

> [!NOTE]
> Microsoft Defender Antivirus Ausschlüsse gelten nur für den Virenschutz, nicht für andere Microsoft Defender für Endpunkt-Funktionen. Um Dateien allgemein auszuschließen, verwenden Sie Ausschlüsse für Microsoft Defender Antivirus und [benutzerdefinierte Indikatoren](/microsoft-365/security/defender-endpoint/manage-indicators) für Microsoft Defender für Endpunkt.

In den Verfahren in diesem Abschnitt wird beschrieben, wie Ausschlüsse und Indikatoren definiert werden.

### <a name="exclusions-for-microsoft-defender-antivirus"></a>Ausschlüsse für Microsoft Defender Antivirus

Im Allgemeinen sollten Sie keine Ausschlüsse für Microsoft Defender Antivirus definieren müssen. Stellen Sie sicher, dass Sie Ausschlüsse sparsam definieren und nur die Dateien, Ordner, Prozesse und vom Prozess geöffneten Dateien einschließen, die zu falsch positiven Ergebnissen führen. Stellen Sie außerdem sicher, dass Sie Ihre definierten Ausschlüsse regelmäßig überprüfen. Es wird empfohlen, [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) zu verwenden, um Antivirenausschlüsse zu definieren oder zu bearbeiten. Sie können jedoch andere Methoden verwenden, z. B. [Gruppenrichtlinien](/azure/active-directory-domain-services/manage-group-policy) (siehe [Verwalten von Microsoft Defender für Endpunkt).](manage-atp-post-migration.md)

> [!TIP]
> Benötigen Sie Hilfe bei Antivirenausschlüssen? Weitere Informationen finden Sie unter [Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus Scans.](configure-exclusions-microsoft-defender-antivirus.md)

#### <a name="use-microsoft-endpoint-manager-to-manage-antivirus-exclusions-for-existing-policies"></a>Verwenden von Microsoft Endpoint Manager zum Verwalten von Antivirenausschlüssen (für vorhandene Richtlinien)

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **Endpoint Security**  >  **Antivirus** aus, und wählen Sie dann eine vorhandene Richtlinie aus. (Wenn Sie nicht über eine vorhandene Richtlinie verfügen oder eine neue Richtlinie erstellen möchten, fahren Sie mit [dem nächsten Verfahren fort).](#use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions)

3. Wählen Sie **"Eigenschaften"** und neben den **Konfigurationseinstellungen** die Option **"Bearbeiten"** aus.

4. Erweitern Sie **Microsoft Defender Antivirus Ausschlüsse,** und geben Sie dann Ihre Ausschlüsse an.

5. Wählen Sie **"Überprüfen" und "Speichern"** und dann **"Speichern"** aus.

#### <a name="use-microsoft-endpoint-manager-to-create-a-new-antivirus-policy-with-exclusions"></a>Verwenden von Microsoft Endpoint Manager zum Erstellen einer neuen Antivirenrichtlinie mit Ausschlüssen

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **Endpunktsicherheit**  >  **Antivirus**  >  **+ Richtlinie erstellen** aus. 

3. Wählen Sie eine Plattform aus (z. **B. Windows 10 und höher,** **macOS** oder **Windows 10 und Windows Server).**

4. Wählen Sie für **"Profil"** **Microsoft Defender Antivirus Ausschlüsse aus,** und wählen Sie dann **"Erstellen"** aus.

5. Geben Sie einen Namen und eine Beschreibung für das Profil an, und klicken Sie dann auf **"Weiter".**

6. Geben Sie auf der Registerkarte **"Konfigurationseinstellungen"** Die Antivirusausschlüsse an, und wählen Sie dann **"Weiter"** aus.

7. Wenn Sie bereichsbezogene Tags in Ihrer Organisation verwenden, geben Sie auf der Registerkarte **"Bereichstags"** Bereichstags für die Richtlinie an, die Sie erstellen. (Siehe [Bereichstags.)](/mem/intune/fundamentals/scope-tags)

8. Geben Sie auf der Registerkarte **"Zuordnungen"** die Benutzer und Gruppen an, auf die Ihre Richtlinie angewendet werden soll, und wählen Sie dann **"Weiter"** aus. (Wenn Sie Hilfe bei Aufgaben benötigen, lesen [Sie "Zuweisen von Benutzer- und Geräteprofilen" in Microsoft Intune.)](/mem/intune/configuration/device-profile-assign)

9. Überprüfen Sie auf der Registerkarte **"Überprüfen + Erstellen"** die Einstellungen, und wählen Sie dann **"Erstellen"** aus.

### <a name="indicators-for-microsoft-defender-for-endpoint"></a>Indikatoren für Microsoft Defender für Endpunkt

[Indikatoren](/microsoft-365/security/defender-endpoint/manage-indicators) (insbesondere Gefährdungsindikatoren oder IoCs) ermöglichen Es Ihrem Sicherheitsteam, die Erkennung, Verhinderung und den Ausschluss von Entitäten zu definieren. Sie können beispielsweise bestimmte Dateien angeben, die in Überprüfungen und Korrekturaktionen in Microsoft Defender für Endpunkt weggelassen werden sollen. Oder Indikatoren können verwendet werden, um Warnungen für bestimmte Dateien, IP-Adressen oder URLs zu generieren.

Um Entitäten als Ausschlüsse für Microsoft Defender für Endpunkt anzugeben, erstellen Sie "Zulassen"-Indikatoren für diese Entitäten. Solche "Zulassen"-Indikatoren in Microsoft Defender für Endpunkt gelten für den Schutz der [nächsten Generation,](microsoft-defender-antivirus-in-windows-10.md) [EDR](overview-endpoint-detection-response.md)und [die automatisierte Untersuchung & Korrektur.](/microsoft-365/security/defender-endpoint/automated-investigations)

"Zulassen"-Indikatoren können für Folgendes erstellt werden:

- [Files](#indicators-for-files)
- [IP-Adressen, URLs und Domänen](#indicators-for-ip-addresses-urls-or-domains)
- [Anwendungszertifikate](#indicators-for-application-certificates)

![Diagramm für Indikatortypen](images/false-positives-indicators.png)

#### <a name="indicators-for-files"></a>Indikatoren für Dateien

Wenn Sie [einen "Zulassen"-Indikator für eine Datei erstellen, z.](/microsoft-365/security/defender-endpoint/indicator-file)B. eine ausführbare Datei, verhindert dies, dass Dateien, die Ihre Organisation verwendet, blockiert werden. Dateien können portierbare ausführbare Dateien (PORTABLE Executable, PE) enthalten, `.exe` `.dll` z. B. Dateien. 

Bevor Sie Indikatoren für Dateien erstellen, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:
- Microsoft Defender Antivirus mit aktivierter cloudbasiertem Schutz konfiguriert ist (siehe [Verwalten des cloudbasierten Schutzes)](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)
- Antischadsoftware-Clientversion ist 4.18.1901.x oder höher 
- Geräte werden Windows 10, Version 1703 oder höher, ausgeführt. Windows Server 2016; oder Windows Server 2019 
- Das [Feature "Blockieren" oder "Zulassen" ist aktiviert](/microsoft-365/security/defender-endpoint/advanced-features) 

#### <a name="indicators-for-ip-addresses-urls-or-domains"></a>Indikatoren für IP-Adressen, URLs oder Domänen

Wenn Sie [einen "Zulassen"-Indikator für eine IP-Adresse, URL oder Domäne erstellen,](/microsoft-365/security/defender-endpoint/indicator-ip-domain)verhindert dies, dass die von Ihrer Organisation verwendeten Websites oder IP-Adressen blockiert werden.

Bevor Sie Indikatoren für IP-Adressen, URLs oder Domänen erstellen, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:
- Der Netzwerkschutz in Defender für Endpunkt ist im Blockierungsmodus aktiviert (siehe [Netzwerkschutz aktivieren)](/microsoft-365/security/defender-endpoint/enable-network-protection)
- Antischadsoftware-Clientversion ist 4.18.1906.x oder höher 
- Geräte werden Windows 10, Version 1709 oder höher, ausgeführt. 

Benutzerdefinierte Netzwerkindikatoren sind im [Microsoft 365 Defender](microsoft-defender-security-center.md)aktiviert. Weitere Informationen finden Sie unter ["Erweiterte Features".](/microsoft-365/security/defender-endpoint/advanced-features)

#### <a name="indicators-for-application-certificates"></a>Indikatoren für Anwendungszertifikate 

Wenn Sie [einen "Zulassen"-Indikator für ein Anwendungszertifikat erstellen,](/microsoft-365/security/defender-endpoint/indicator-certificates)verhindert dies, dass Anwendungen, wie z. B. intern entwickelte Anwendungen, die Ihre Organisation verwendet, blockiert werden. `.CER` oder `.PEM` Dateierweiterungen werden unterstützt.   

Bevor Sie Indikatoren für Anwendungszertifikate erstellen, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:

- Microsoft Defender Antivirus mit aktivierter cloudbasiertem Schutz konfiguriert ist (siehe [Verwalten des cloudbasierten Schutzes)](deploy-manage-report-microsoft-defender-antivirus.md)
- Antischadsoftware-Clientversion ist 4.18.1901.x oder höher 
- Geräte werden Windows 10, Version 1703 oder höher, ausgeführt. Windows Server 2016; oder Windows Server 2019 
- Viren- und Bedrohungsschutzdefinitionen sind auf dem neuesten Stand  

> [!TIP]
> Wenn Sie Indikatoren erstellen, können Sie sie nacheinander definieren oder mehrere Elemente gleichzeitig importieren. Beachten Sie, dass für einen einzelnen Mandanten ein Grenzwert von 15.000 Indikatoren gilt. Möglicherweise müssen Sie zuerst bestimmte Details erfassen, z. B. Dateihashinformationen. Überprüfen Sie unbedingt die Voraussetzungen, bevor Sie [Indikatoren erstellen.](manage-indicators.md) 

## <a name="part-4-submit-a-file-for-analysis"></a>Teil 4: Übermitteln einer Datei zur Analyse

Sie können Entitäten wie Dateien und dateilose Erkennungen zur Analyse an Microsoft übermitteln. Microsoft-Sicherheitsexperten analysieren alle Übermittlungen, und ihre Ergebnisse helfen, Microsoft Defender für Endpunkt-Bedrohungsschutzfunktionen zu informieren. Wenn Sie sich auf der Übermittlungswebsite anmelden, können Sie Ihre Übermittlungen nachverfolgen.

### <a name="submit-a-file-for-analysis"></a>Übermitteln einer Datei zur Analyse

Wenn Sie über eine Datei verfügen, die fälschlicherweise als bösartig erkannt oder verpasst wurde, führen Sie die folgenden Schritte aus, um die Datei zur Analyse zu übermitteln.

1. Überprüfen Sie die Hier aufgeführten Richtlinien: [Übermitteln von Dateien zur Analyse.](/windows/security/threat-protection/intelligence/submission-guide)

2. Besuchen Sie die Microsoft Security Intelligence-Übermittlungswebsite ( [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) ), und übermitteln Sie Ihre Dateien.

### <a name="submit-a-fileless-detection-for-analysis"></a>Übermitteln einer dateilosen Erkennung für die Analyse

Wenn aufgrund des Verhaltens etwas als Schadsoftware erkannt wurde und Sie keine Datei haben, können Sie Ihre `Mpsupport.cab` Datei zur Analyse übermitteln. Sie können die *.cab-Datei* mit dem Tool microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) auf Windows 10 abrufen.

1.  Wechseln Sie zu ` C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` , und führen Sie es dann als Administrator `MpCmdRun.exe` aus.

2.  Geben Sie `mpcmdrun.exe -GetFiles` ein, und drücken Sie dann die **EINGABETASTE.**
   Es wird eine .cab Datei generiert, die verschiedene Diagnoseprotokolle enthält. Der Speicherort der Datei wird in der Ausgabe der Eingabeaufforderung angegeben. Standardmäßig lautet der Speicherort `C:\ProgramData\Microsoft\Microsoft Defender\Support\MpSupportFiles.cab` .

3.  Überprüfen Sie die Hier aufgeführten Richtlinien: [Übermitteln von Dateien zur Analyse.](/windows/security/threat-protection/intelligence/submission-guide)

4.  Besuchen Sie die Microsoft Security Intelligence-Übermittlungswebsite ( [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) ), und übermitteln Sie Ihre .cab Dateien.

### <a name="what-happens-after-a-file-is-submitted"></a>Was geschieht nach dem Übermitteln einer Datei?

Ihre Übermittlung wird sofort von unseren Systemen gescannt, um Ihnen die neueste Entscheidung zu liefern, noch bevor ein Analyst mit der Bearbeitung Ihres Falls beginnt. Es ist möglich, dass eine Datei bereits von einem Analysten übermittelt und verarbeitet wurde. In diesen Fällen erfolgt eine schnelle Ermittlung.

Für Übermittlungen, die noch nicht verarbeitet wurden, werden sie für die Analyse wie folgt priorisiert:

- Weit verbreitete Dateien mit dem Potenzial, sich auf eine große Anzahl von Computern zu auswirken, haben eine höhere Priorität.
- Authentifizierte Kunden, insbesondere Unternehmenskunden mit gültigen [SOFTWARE Assurance-IDs (CDDs),](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)haben eine höhere Priorität.
- Übermittlungen, die von SAID-Haltern als hohe Priorität gekennzeichnet sind, werden sofort beachtet.

Um nach Updates für Ihre Übermittlung zu suchen, melden Sie sich auf der [Microsoft Security Intelligence Übermittlungswebsite](https://www.microsoft.com/wdsi/filesubmission)an. 

> [!TIP]
> Weitere Informationen finden Sie unter ["Übermitteln von Dateien zur Analyse".](/windows/security/threat-protection/intelligence/submission-guide#how-does-microsoft-prioritize-submissions)

## <a name="part-5-review-and-adjust-your-threat-protection-settings"></a>Teil 5: Überprüfen und Anpassen Ihrer Einstellungen für den Bedrohungsschutz

Microsoft Defender für Endpunkt bietet eine Vielzahl von Optionen, einschließlich der Möglichkeit, Einstellungen für verschiedene Features und Funktionen zu optimieren. Wenn Sie zahlreiche falsch positive Ergebnisse erhalten, überprüfen Sie die Einstellungen für den Bedrohungsschutz Ihrer Organisation. Möglicherweise müssen Sie einige Anpassungen an folgenden Stellen vornehmen:

- [Über die Cloud bereitgestellter Schutz](#cloud-delivered-protection)
- [Korrektur für potenziell unerwünschte Anwendungen](#remediation-for-potentially-unwanted-applications)
- [Automatisierte Untersuchung und Korrektur](#automated-investigation-and-remediation)

### <a name="cloud-delivered-protection"></a>Aus der Cloud gelieferter Schutz

Überprüfen Sie ihre über die Cloud bereitgestellte Schutzebene auf Microsoft Defender Antivirus. Standardmäßig ist der über die Cloud bereitgestellte Schutz auf **"Nicht konfiguriert"** festgelegt, was einem normalen Schutzniveau für die meisten Organisationen entspricht. Wenn Der über die Cloud bereitgestellte Schutz auf **"Hoch",** **"Hoch +**" oder **"Null"** festgelegt ist, kann es vorkommen, dass eine höhere Anzahl falsch positiver Ergebnisse auftritt.

> [!TIP]
> Weitere Informationen zum Konfigurieren des über die Cloud bereitgestellten Schutzes finden Sie unter Angeben der über [die Cloud bereitgestellten Schutzebene.](/windows/security/threat-protection/microsoft-defender-antivirus/specify-cloud-protection-level-microsoft-defender-antivirus)

Es wird empfohlen, [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) zu verwenden, um Ihre über die Cloud bereitgestellten Schutzeinstellungen zu bearbeiten oder festzulegen. Sie können jedoch andere Methoden verwenden, z. B. [Gruppenrichtlinien](/azure/active-directory-domain-services/manage-group-policy) (siehe [Verwalten von Microsoft Defender für Endpunkt).](manage-atp-post-migration.md)

#### <a name="use-microsoft-endpoint-manager-to-review-and-edit-cloud-delivered-protection-settings-for-existing-policies"></a>Verwenden von Microsoft Endpoint Manager zum Überprüfen und Bearbeiten von über die Cloud bereitgestellten Schutzeinstellungen (für vorhandene Richtlinien)

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **Endpunktsicherheits-Antivirus**  >   aus, und wählen Sie dann eine vorhandene Richtlinie aus. (Wenn Sie nicht über eine vorhandene Richtlinie verfügen oder eine neue Richtlinie erstellen möchten, fahren Sie mit [dem nächsten Verfahren fort).](#use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy)

3. Wählen Sie unter **"Verwalten"** die Option **"Eigenschaften"** aus. Wählen Sie dann neben den **Konfigurationseinstellungen** **"Bearbeiten"** aus.

4. Erweitern Sie **cloudbasierten Schutz,** und überprüfen Sie Ihre aktuelle Einstellung in der Zeile zur Über die **Cloud bereitgestellten Schutzebene.** Wir empfehlen, den über die Cloud bereitgestellten Schutz auf **"Nicht konfiguriert"** festzulegen, was starken Schutz bietet und gleichzeitig die Wahrscheinlichkeit verringert, dass falsch positive Ergebnisse auftreten.

5. Wählen Sie **"Überprüfen" + "Speichern"** und dann **"Speichern"** aus.

#### <a name="use-microsoft-endpoint-manager-to-set-cloud-delivered-protection-settings-for-a-new-policy"></a>Verwenden von Microsoft Endpoint Manager zum Festlegen von über die Cloud bereitgestellten Schutzeinstellungen (für eine neue Richtlinie)

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie **Endpunktsicherheit**  >  **Antivirus**  >  **+ Richtlinie erstellen** aus.

3. Wählen Sie für **"Plattform"** eine Option aus, und wählen Sie dann für **"Profil"** **Antivirus** oder **Microsoft Defender Antivirus** aus (die spezifische Option hängt davon ab, was Sie für **die Plattform** ausgewählt haben.) Klicken Sie dann auf **"Erstellen".**

4. Geben Sie auf der Registerkarte **"Grundlagen"** einen Namen und eine Beschreibung für die Richtlinie an. Wählen Sie dann **Weiter** aus.

5. Erweitern Sie auf der Registerkarte **"Konfigurationseinstellungen"** den **Cloudschutz,** und geben Sie die folgenden Einstellungen an:
   - Aktivieren Sie den über die **Cloud bereitgestellten Schutz** auf **"Ja".**
   - Legen Sie **Aus der Cloud bereitgestellte Schutzebene** auf **Nicht konfiguriert** fest. (Diese Stufe bietet standardmäßig ein starkes Schutzniveau, während gleichzeitig die Wahrscheinlichkeit verringert wird, dass falsch positive Ergebnisse angezeigt werden.)

6. Wenn Sie bereichsbezogene Tags in Ihrer Organisation verwenden, geben Sie auf der Registerkarte **"Bereichstags"** Bereichstags für die Richtlinie an. (Siehe [Bereichstags.)](/mem/intune/fundamentals/scope-tags)

7. Geben Sie auf der Registerkarte **"Zuordnungen"** die Benutzer und Gruppen an, auf die Ihre Richtlinie angewendet werden soll, und wählen Sie dann **"Weiter"** aus. (Wenn Sie Hilfe bei Aufgaben benötigen, lesen [Sie "Zuweisen von Benutzer- und Geräteprofilen" in Microsoft Intune.)](/mem/intune/configuration/device-profile-assign)

8. Überprüfen Sie auf der Registerkarte **"Überprüfen + Erstellen"** die Einstellungen, und wählen Sie dann **"Erstellen"** aus.  

### <a name="remediation-for-potentially-unwanted-applications"></a>Korrektur für potenziell unerwünschte Anwendungen

Potenziell unerwünschte Anwendungen (PUA) sind eine Kategorie von Software, die dazu führen kann, dass Geräte langsam ausgeführt werden, unerwartete Anzeigen anzeigen oder andere Software installieren, die unerwartet oder unerwünscht sein kann. Beispiele für PUA sind Werbungssoftware, Bündeln von Software und Software zur Umgehung, die sich anders verhält als Sicherheitsprodukte. Obwohl PUA nicht als Schadsoftware betrachtet wird, sind einige Arten von Software PUA basierend auf ihrem Verhalten und ihrem Ruf.

> [!TIP]
> Weitere Informationen zu PUA finden Sie unter [Erkennen und Blockieren potenziell unerwünschter Anwendungen.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
 
Abhängig von den Apps, die Ihre Organisation verwendet, erhalten Sie möglicherweise aufgrund Ihrer PUA-Schutzeinstellungen falsch positive Ergebnisse. Erwägen Sie bei Bedarf, den PUA-Schutz für eine Weile im Überwachungsmodus auszuführen, oder wenden Sie PUA-Schutz auf eine Teilmenge der Geräte in Ihrer Organisation an. DER PUA-Schutz kann für den Microsoft Edge Browser und für Microsoft Defender Antivirus konfiguriert werden.

Es wird empfohlen, [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) zum Bearbeiten oder Festlegen von PUA-Schutzeinstellungen zu verwenden. Sie können jedoch andere Methoden verwenden, z. B. [Gruppenrichtlinien](/azure/active-directory-domain-services/manage-group-policy) (siehe [Verwalten von Microsoft Defender für Endpunkt).](manage-atp-post-migration.md)

#### <a name="use-microsoft-endpoint-manager-to-edit-pua-protection-for-existing-configuration-profiles"></a>Verwenden von Microsoft Endpoint Manager zum Bearbeiten des PUA-Schutzes (für vorhandene Konfigurationsprofile)

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie  >  **Gerätekonfigurationsprofile** aus, und wählen Sie dann eine vorhandene Richtlinie aus. (Wenn Sie keine vorhandene Richtlinie haben oder eine neue Richtlinie erstellen möchten, fahren Sie mit [dem nächsten Verfahren fort.)](#use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile)

3. Wählen Sie unter **"Verwalten"** die Option **"Eigenschaften"** und dann neben **"Konfigurationseinstellungen"** die Option **"Bearbeiten"** aus.

4. Scrollen Sie auf der Registerkarte **"Konfigurationseinstellungen"** nach unten, und erweitern **Sie Microsoft Defender Antivirus**.

5. Legen **Sie "Erkennen potenziell unerwünschter Anwendungen"** auf **"Überwachen"** fest. (Sie können es deaktivieren, aber mithilfe des Überwachungsmodus können Sie Erkennungen sehen.)

6. Wählen Sie **"Überprüfen" und "Speichern"** und dann **"Speichern"** aus.

#### <a name="use-microsoft-endpoint-manager-to-set-pua-protection-for-a-new-configuration-profile"></a>Verwenden Microsoft Endpoint Manager zum Festlegen des PUA-Schutzes (für ein neues Konfigurationsprofil)

1. Wechseln Sie zum Microsoft Endpoint Manager Admin Center ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie  >  **Gerätekonfigurationsprofile**  >  **+ Profil erstellen** aus.

3. Wählen Sie für die **Plattform** **Windows 10 und höher aus,** und wählen Sie für **Profil** **Geräteeinschränkungen** aus.

4. Geben Sie auf der Registerkarte **"Grundlagen"** einen Namen und eine Beschreibung für Ihre Richtlinie an. Wählen Sie dann **Weiter** aus.

5. Scrollen Sie auf der Registerkarte **"Konfigurationseinstellungen"** nach unten, und erweitern **Sie Microsoft Defender Antivirus**.

6. Legen **Sie "Erkennen potenziell unerwünschter Anwendungen"** auf **"Überwachung"** fest, und wählen Sie dann **"Weiter"** aus. (Sie können den PUA-Schutz deaktivieren, aber im Überwachungsmodus können Sie Erkennungen sehen.)

7. Geben Sie auf der Registerkarte **"Zuordnungen"** die Benutzer und Gruppen an, auf die Ihre Richtlinie angewendet werden soll, und wählen Sie dann **"Weiter"** aus. (Wenn Sie Hilfe bei Aufgaben benötigen, lesen [Sie "Zuweisen von Benutzer- und Geräteprofilen" in Microsoft Intune.)](/mem/intune/configuration/device-profile-assign)

8. Geben Sie auf der Registerkarte **"Anwendbarkeitsregeln"** die Betriebssystemeditionen oder -versionen an, die in die Richtlinie aufgenommen oder von dieser ausgeschlossen werden sollen. Beispielsweise können Sie festlegen, dass die Richtlinie auf alle Geräte angewendet werden soll, wobei bestimmte Editionen von Windows 10. Wählen Sie dann **Weiter** aus.

9. Überprüfen Und erstellen Sie auf der Registerkarte **"Überprüfen"** Ihre Einstellungen, und wählen Sie dann **"Erstellen"** aus.

### <a name="automated-investigation-and-remediation"></a>Automatische Untersuchung und Reaktion

Air-Funktionen [(Automated Investigation and Remediation)](automated-investigations.md) sind darauf ausgelegt, Warnungen zu untersuchen und sofortige Maßnahmen zur Behebung von Verstößen zu ergreifen. Wenn Warnungen ausgelöst werden und eine automatisierte Untersuchung ausgeführt wird, wird für jeden untersuchten Nachweis eine Bewertung generiert. Bewertungen können *bösartig,* *verdächtig* oder *keine Bedrohungen gefunden* werden. 

Abhängig vom [Grad der Automatisierung](/microsoft-365/security/defender-endpoint/automation-levels) für Ihre Organisation und anderen Sicherheitseinstellungen werden Korrekturmaßnahmen für Artefakte ausgeführt, die als *bösartig* oder *verdächtig* eingestuft werden. In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. in anderen Fällen werden Korrekturmaßnahmen manuell oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt. 

- [Weitere Informationen zu Automatisierungsebenen;](/microsoft-365/security/defender-endpoint/automation-levels) Und dann 
- [Konfigurieren von AIR-Funktionen in Defender für Endpunkt.](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation)

> [!IMPORTANT]
> Es wird empfohlen, *die vollständige Automatisierung* für die automatisierte Untersuchung und Behebung zu verwenden. Deaktivieren Sie diese Funktionen nicht aufgrund eines falsch positiven Ergebnisses. Verwenden Sie stattdessen ["Zulassen"-Indikatoren, um Ausnahmen zu definieren,](#indicators-for-microsoft-defender-for-endpoint)und halten Sie die automatische Untersuchung und Korrektur so fest, dass die entsprechenden Aktionen automatisch ausgeführt werden. Wenn [Sie diese Anleitung befolgen,](automation-levels.md#levels-of-automation) können Sie die Anzahl der Warnungen reduzieren, die Ihr Sicherheitsteam behandeln muss. 

## <a name="still-need-help"></a>Benötigen Sie weitere Hilfe?

Wenn Sie alle Schritte in diesem Artikel durchgearbeitet haben und weiterhin Hilfe benötigen, wenden Sie sich an den technischen Support.

1. Wechseln Sie zum Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie in der oberen rechten Ecke das Fragezeichen (**?**), und wählen Sie dann **Microsoft-Support** aus.

3. Beschreiben Sie im Fenster des **Support-Assistenten** Ihr Problem, und senden Sie dann Ihre Nachricht. Von dort aus können Sie eine Serviceanfrage öffnen.  

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft Defender für Endpunkt](manage-atp-post-migration.md)

[Übersicht über Microsoft 365 Defender-Portal](/microsoft-365/security/defender-endpoint/use) 
