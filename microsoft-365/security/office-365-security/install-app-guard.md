---
title: Application Guard für Office 365 für Administratoren
keywords: Application Guard, Schutz, Isolation, isolierter Container, Hardwareisolation
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Rufen Sie die neueste hardwarebasierte Isolation ab. Verhindern Sie, dass aktuelle und neue Angriffe wie Exploits oder bösartige Links die Produktivität der Mitarbeiter und die Unternehmenssicherheit beeinträchtigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39d6a9c3a3c3a5e2c736025a26c22588f9f08bb0
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53055271"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard für Office für Administratoren

**Gilt für:** Word-, Excel- und PowerPoint for Microsoft 365 Windows 10 Enterprise

Microsoft Defender Application Guard für Office (Application Guard für Office) verhindert, dass nicht vertrauenswürdige Dateien auf vertrauenswürdige Ressourcen zugreifen, und schützt Ihr Unternehmen vor neuen und neuen Angriffen. Dieser Artikel führt Administratoren durch das Einrichten von Geräten für eine Vorschau von Application Guard für Office. Es enthält Informationen zu Systemanforderungen und Installationsschritten, um Application Guard für Office auf einem Gerät zu aktivieren.

## <a name="prerequisites"></a>Voraussetzungen

### <a name="minimum-hardware-requirements"></a>Hardware-Mindestanforderungen

* **CPU:** 64-Bit, 4 Kerne (physisch oder virtuell), Virtualisierungserweiterungen (Intel VT-x ODER AMD-V), Core i5-Äquivalent oder höher empfohlen
* **Physischer Speicher:** 8 GB RAM
* **Festplatte:** 10 GB freier Speicherplatz auf dem Systemlaufwerk (SSD empfohlen)

### <a name="minimum-software-requirements"></a>Mindestanforderungen an die Software

* **Windows 10:** Windows 10 Enterprise Edition, Client Build Version 2004 (20H1) Build 19041 oder höher
* **Office**: Office Aktueller Kanal und monatlicher Enterprise Kanal, Buildversion 2011 16.0.13530.10000 oder höher. Es werden sowohl 32-Bit- als auch 64-Bit-Versionen von Office unterstützt.
* **Updatepaket:** Windows 10 kumulatives monatliches Sicherheitsupdate [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Ausführliche Systemanforderungen finden Sie in den [Systemanforderungen für Microsoft Defender Application Guard.](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard) Lesen Sie auch die Handbücher Ihres Computerherstellers zur Aktivierung der Virtualisierungstechnologie.
Weitere Informationen zu Office Updatekanälen finden Sie unter [Übersicht über Updatekanäle für Microsoft 365](/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

* Microsoft 365 E5 oder Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Bereitstellen von Application Guard für Office

### <a name="enable-application-guard-for-office"></a>Aktivieren von Application Guard für Office

1. Laden Sie **Windows 10 kumulativen monatlichen Sicherheitsupdates KB4571756 herunter,** und installieren Sie sie.

2. Wählen Sie **unter Windows** Features Microsoft Defender Application Guard aus, und wählen Sie **OK** aus. Wenn Sie das Application Guard-Feature aktivieren, wird ein Systemneustart angezeigt. Sie können den Neustart jetzt oder nach Schritt 3 durchführen.

   ![Windows Dialogfeld "Features" mit AG](../../media/ag03-deploy.png)

   Das Feature kann auch aktiviert werden, indem der folgende PowerShell-Befehl als Administrator ausgeführt wird:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Suchen Sie **im verwalteten Modus** nach Microsoft Defender Application Guard, einer Gruppenrichtlinie in administrativen Vorlagen für die **Computerkonfiguration Windows Komponenten \\ \\ \\ Microsoft Defender Application Guard**. Aktivieren Sie diese Richtlinie, indem Sie den Wert unter "Optionen" auf **"2"** oder **"3"** festlegen und dann **"OK"** oder **"Anwenden"** auswählen.

   ![Aktivieren von AG im verwalteten Modus](../../media/ag04-deploy.png)

   Stattdessen können Sie die entsprechende CSP-Richtlinie festlegen:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Einstellungen/AllowWindowsDefenderApplicationGuard** <br> Datentyp: **Ganze Zahl** <br> Wert: **2**

4. Starten Sie das System neu.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Festlegen des Diagnose-&-Feedbacks zum Senden vollständiger Daten

> [!NOTE]
> Dies ist nicht erforderlich. Die Konfiguration optionaler Diagnosedaten hilft jedoch bei der Diagnose gemeldeter Probleme.

Mit diesem Schritt wird sichergestellt, dass die zum Identifizieren und Beheben von Problemen erforderlichen Daten Microsoft erreichen. Führen Sie die folgenden Schritte aus, um die Diagnose auf Ihrem Windows Gerät zu aktivieren:

1. Öffnen **Sie Einstellungen** aus dem Startmenü.

   ![Startmenü](../../media/ag05-diagnostic.png)

2. Wählen Sie **in Windows Einstellungen** die Option **"Datenschutz"** aus.

   ![menü Windows Einstellungen](../../media/ag06-diagnostic.png)

3. Wählen Sie unter **"Datenschutz" diagnose & Feedback** aus, und wählen Sie optionale **Diagnosedaten** aus.

   ![Menü "Diagnose und Feedback"](../../media/ag07a-diagnostic.png)

Weitere Informationen zum Konfigurieren Windows Diagnoseeinstellungen finden Sie unter ["Konfigurieren Windows Diagnosedaten in Ihrer Organisation".](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management)

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Vergewissern Sie sich, dass Application Guard für Office aktiviert ist und funktioniert

Bevor Sie bestätigen, dass Application Guard für Office aktiviert ist, starten Sie Word, Excel oder PowerPoint auf einem Gerät, auf dem die Richtlinien bereitgestellt wurden. Stellen Sie sicher, dass Office aktiviert ist. Möglicherweise müssen Sie Ihre Geschäftliche Identität verwenden, um zuerst das Office Produkt zu aktivieren.

Um zu bestätigen, dass Application Guard für Office aktiviert ist, starten Sie Word, Excel oder PowerPoint, und öffnen Sie dann ein nicht vertrauenswürdiges Dokument. Sie können z. B. ein Dokument öffnen, das aus dem Internet heruntergeladen wurde, oder eine E-Mail-Anlage von einer Person außerhalb Ihrer Organisation.

Wenn Sie eine nicht vertrauenswürdige Datei zum ersten Mal öffnen, wird möglicherweise ein Office Begrüßungsbildschirm wie im folgenden Beispiel angezeigt. Sie wird möglicherweise für einige Zeit angezeigt, während Application Guard für Office aktiviert wird und die Datei geöffnet wird. Das anschließende Öffnen nicht vertrauenswürdiger Dateien sollte schneller erfolgen.

![Office-App Begrüßungsbildschirm](../../media/ag08-confirm.png)

Beim Öffnen sollte die Datei einige visuelle Indikatoren anzeigen, dass die Datei in Application Guard für Office geöffnet wurde:

* Eine Legende im Menüband

  ![Dokumentdatei mit kleiner App Guard-Notiz](../../media/ag09-confirm.png)

* Das Anwendungssymbol mit einem Schild in der Taskleiste

  ![Symbol in der Taskleiste](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Konfigurieren von Application Guard für Office

Office unterstützt die folgenden Richtlinien, mit denen Sie die Funktionen von Application Guard für Office konfigurieren können. Diese Richtlinien können über Gruppenrichtlinien oder über den [Office Cloudrichtliniendienst](/DeployOffice/overview-office-cloud-policy-service)konfiguriert werden.


> [!NOTE]
> Durch das Konfigurieren dieser Richtlinien können einige Funktionen für Dateien deaktiviert werden, die in Application Guard für Office geöffnet wurden.

|Richtlinie|Beschreibung|
|---|---|
|Verwenden Sie Application Guard nicht für Office|Durch Aktivieren dieser Richtlinie wird erzwungen, dass Word, Excel und PowerPoint den Isolationscontainer "Geschützte Ansicht" anstelle von Application Guard für Office verwenden. Diese Richtlinie kann verwendet werden, um Application Guard vorübergehend für Office zu deaktivieren, wenn Es Probleme gibt, sie für Microsoft Edge aktiviert zu lassen.|
|Konfigurieren von Application Guard für Office Containervorerstellung|Diese Richtlinie bestimmt, ob Application Guard für Office Container zum Isolieren nicht vertrauenswürdiger Dateien für eine bessere Laufzeitleistung vorkonfiguriert wurde. Wenn Sie diese Einstellung aktivieren, können Sie die Anzahl der Tage angeben, um mit der Vorerstellung eines Containers fortzufahren, oder die Office integrierten heuristischen Vorerstellung des Containers zulassen.
|Kopieren/Einfügen für Office Dokumente, die in Application Guard für Office geöffnet wurden, nicht zulassen|Durch Aktivieren dieser Richtlinie wird verhindert, dass ein Benutzer Inhalte aus einem Dokument kopiert und eingibt, das in Application Guard für Office in ein Dokument außerhalb des Dokuments geöffnet wurde.|
|Deaktivieren der Hardwarebeschleunigung in Application Guard für Office|Diese Richtlinie steuert, ob Application Guard für Office zum Rendern von Grafiken die Hardwarebeschleunigung verwendet. Wenn Sie diese Einstellung aktivieren, verwendet Application Guard für Office softwarebasiertes (CPU)-Rendering und lädt keine Grafiktreiber von Drittanbietern oder interagiert mit verbundener Grafikhardware.
|Deaktivieren des Schutzes nicht unterstützter Dateitypen in Application Guard für Office|Diese Richtlinie steuert, ob Application Guard für Office verhindert, dass nicht unterstützte Dateitypen geöffnet werden, oder ob die Umleitung zur geschützten Ansicht aktiviert wird.
|Deaktivieren des Kamera- und Mikrofonzugriffs für Dokumente, die in Application Guard für Office|Durch Aktivieren dieser Richtlinie wird Office Zugriff auf die Kamera und das Mikrofon in Application Guard für Office entfernt.|
|Einschränken des Druckens von Dokumenten, die in Application Guard für Office geöffnet wurden|Durch Aktivieren dieser Richtlinie werden die Drucker eingeschränkt, auf die ein Benutzer aus einer Datei drucken kann, die in Application Guard für Office geöffnet wurde. Sie können diese Richtlinie beispielsweise verwenden, um Benutzer so zu beschränken, dass sie nur im PDF-Format drucken.|
|Verhindern, dass Benutzer Application Guard zum Office Schutz von Dateien entfernen|Durch Aktivieren dieser Richtlinie wird die Option (innerhalb der Office Anwendungsumgebung) entfernt, Application Guard für Office Schutz zu deaktivieren oder eine Datei außerhalb von Application Guard für Office zu öffnen. <p> **Hinweis:** Benutzer können diese Richtlinie weiterhin umgehen, indem sie die Mark-of-the-Web-Eigenschaft manuell aus der Datei entfernen oder ein Dokument an einen vertrauenswürdigen Speicherort verschieben.|
|

> [!NOTE]
> Die folgenden Richtlinien erfordern, dass sich der Benutzer abmeldet und sich erneut anmeldet, um Windows wirksam zu werden:
>
> * Deaktivieren des Kopierens/Einfügens für Dokumente, die in Application Guard für Office
> * Einschränken des Druckens für Dokumente, die in Application Guard für Office geöffnet wurden
> * Deaktivieren des Kamera- und Mikrofonzugriffs auf Dokumente, die in Application Guard für Office

## <a name="submit-feedback"></a>Feedback senden

### <a name="submit-feedback-via-feedback-hub"></a>Senden von Feedback über den Feedback-Hub

Wenn beim Starten von Application Guard für Office Probleme auftreten, sollten Sie Ihr Feedback über den Feedback-Hub übermitteln:

1. Öffnen Sie die **Feedback-Hub-App,** und melden Sie sich an.

2. Wenn beim Starten von Application Guard ein Fehlerdialogfeld angezeigt wird, wählen Sie im Fehlerdialogfeld **"Bericht an Microsoft"** aus, um eine neue Feedbackübermittlung zu starten. Navigieren Sie andernfalls <https://aka.ms/mdagoffice-fb> zu der richtigen Kategorie für Application Guard, und wählen Sie dann oben rechts **+ &nbsp; "Neues Feedback hinzufügen"** aus.

3. Geben Sie eine Zusammenfassung in das **Feld "Feedback zusammenfassen"** ein, wenn es noch nicht für Sie ausgefüllt ist.

4. Geben Sie eine detaillierte Beschreibung des Aufgetretenen Problems ein, und geben Sie im **Feld "Erläutern" eine detailliertere** Beschreibung ein, und wählen Sie dann **"Weiter"** aus.

5. Wählen Sie die Blase neben **Problem** aus. Stellen Sie sicher, dass die ausgewählte Kategorie **"Sicherheit und \> Datenschutz" Microsoft Defender Application Guard ist – Office** und dann **"Weiter"** auswählen.

6. Wählen Sie **"Neues Feedback"** und dann **"Weiter"** aus.

7. Sammeln Von Ablaufverfolgungen zu dem Problem:

   1. Erweitern Sie die **Kachel "Problem neu erstellen".**

   2. Wenn das Problem auftritt, das während der Ausführung von Application Guard auftritt, öffnen Sie eine Application Guard-Instanz. Durch das Öffnen einer Instanz können zusätzliche Ablaufverfolgungen aus dem Application Guard-Container erfasst werden.

   3. Wählen Sie **"Aufzeichnung starten"** aus, und warten Sie, bis sich die Kachel nicht mehr dreht, und sagen *Sie "Aufzeichnung beenden".*

   4. Reproduzieren Sie das Problem mit Application Guard vollständig. Die Wiederholung kann den Versuch umfassen, eine Application Guard-Instanz zu starten und zu warten, bis sie fehlschlägt, oder das Reproduzieren eines Problems in einer ausgeführten Application Guard-Instanz.

   5. Wählen Sie die Kachel **"Aufzeichnung beenden"** aus.

   6. Lassen Sie alle ausgeführten Application Guard-Instanzen auch einige Minuten nach der Übermittlung geöffnet, damit auch containerdiagnosen erfasst werden können.

8. Fügen Sie alle relevanten Screenshots oder Dateien im Zusammenhang mit dem Problem an.

9. Wählen Sie **Senden** aus.

### <a name="submit-feedback-via-office-customer-voice"></a>Übermitteln von Feedback über Office Customer Voice

Sie können auch Innerhalb Office Feedback senden, wenn das Problem auftritt, wenn Office Dokumente in Application Guard geöffnet werden. Informationen zum Übermitteln von Feedback finden Sie im [Office Insider-Handbuch.](https://insider.office.com/handbook)

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integration in Microsoft Defender für Endpunkt und Microsoft Defender für Office 365

Application Guard für Office ist in Microsoft Defender für Endpunkt integriert, um Überwachung und Warnung bei böswilligen Aktivitäten in der isolierten Umgebung bereitzustellen.

[Tresor Dokumente in Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) ist ein Feature, das Microsoft Defender für Endpunkt verwendet, um Dokumente zu scannen, die in Application Guard für Office geöffnet wurden. Für eine zusätzliche Schutzebene können Benutzer Application Guard erst dann für Office verlassen, wenn die Ergebnisse der Überprüfung ermittelt wurden.

Microsoft Defender für Endpunkt ist eine Sicherheitsplattform, die Unternehmensnetzwerke dabei unterstützt, fortgeschrittene Bedrohungen zu verhindern, zu erkennen, zu untersuchen und darauf zu reagieren. Weitere Informationen zu dieser Plattform finden Sie unter [Microsoft Defender für Endpunkt.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) Weitere Informationen zum Onboarding von Geräten auf dieser Plattform finden Sie unter [Onboarding von Geräten in den Microsoft Defender für Endpunkt-Dienst.](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure)

Sie können Microsoft Defender auch für Office 365 konfigurieren, um mit Defender für Endpunkt zu arbeiten. Weitere Informationen finden Sie unter [Integrieren von Defender für Office 365 in Microsoft Defender für Endpunkt.](integrate-office-365-ti-with-mde.md)

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen

* Application Guard für Office ist ein geschützter Modus, der nicht vertrauenswürdige Dokumente isoliert, sodass sie nicht auf vertrauenswürdige Unternehmensressourcen, ein Intranet, die Identität des Benutzers und beliebige Dateien auf dem Computer zugreifen können. Wenn ein Benutzer versucht, auf ein Feature zuzugreifen, das von einem solchen Zugriff abhängig ist , z. B. das Einfügen eines Bilds aus einer lokalen Datei auf dem Datenträger, schlägt der Zugriff fehl und erzeugt eine Eingabeaufforderung wie im folgenden Beispiel. Damit ein nicht vertrauenswürdiges Dokument auf vertrauenswürdige Ressourcen zugreifen kann, müssen Benutzer den Application Guard-Schutz aus dem Dokument entfernen.

  ![Dialogfeld mit der Meldung, dass diese Funktion nicht verfügbar ist, damit Sie sich schützen können](../../media/ag10-limitations.png)

  > [!NOTE]
  > Weisen Sie Benutzer an, den Schutz nur zu entfernen, wenn sie der Datei und ihrer Quelle vertrauen oder woher sie stammt.

* Aktive Inhalte in Dokumenten wie Makros und ActiveX-Steuerelementen sind in Application Guard für Office deaktiviert. Benutzer müssen den Application Guard-Schutz entfernen, um aktive Inhalte zu aktivieren.

* Nicht vertrauenswürdige Dateien aus Netzwerkfreigaben oder Dateien, die von OneDrive, OneDrive for Business oder SharePoint Online aus einer anderen Organisation freigegeben wurden, werden in Application Guard schreibgeschützt geöffnet. Benutzer können eine lokale Kopie dieser Dateien speichern, um die Arbeit im Container fortzusetzen, oder den Schutz entfernen, um direkt mit der Originaldatei zu arbeiten.

* Dateien, die durch die Verwaltung von Informationsrechten (Information Rights Management, IRM) geschützt sind, werden standardmäßig blockiert. Wenn Benutzer solche Dateien in der geschützten Ansicht öffnen möchten, muss ein Administrator Richtlinieneinstellungen für nicht unterstützte Dateitypen für die Organisation konfigurieren.

* Alle Anpassungen an Office Anwendungen in Application Guard für Office werden nicht beibehalten, nachdem sich ein Benutzer abmeldet und sich erneut anmeldet, oder nachdem das Gerät neu gestartet wurde.

* Nur Barrierefreiheitstools, die das UIA-Framework verwenden, können eine barrierefreie Oberfläche für Dateien bereitstellen, die in Application Guard für Office geöffnet wurden.

* Netzwerkkonnektivität ist für den ersten Start von Application Guard nach der Installation erforderlich. Die Konnektivität ist erforderlich, damit Application Guard die Lizenz überprüft.

* Im Informationsabschnitt des Dokuments zeigt die Eigenschaft *"Last Modified By"* möglicherweise **WDAGUtilityAccount** als Benutzer an. WDAGUtilityAccount ist der anonyme Benutzer, der in Application Guard konfiguriert ist. Die Identität des Desktopbenutzers wird nicht im Application Guard-Container freigegeben.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Leistungsoptimierungen für Application Guard für Office

Dieser Abschnitt bietet eine Übersicht über die Leistungsoptimierungen, die in Application Guard für Office verwendet werden. Anhand dieser Informationen können Administratoren Berichte von Benutzern im Zusammenhang mit der Leistung von Office oder dem Gesamtsystem diagnostizieren, wenn Application Guard aktiviert ist.

Application Guard verwendet einen virtualisierten Container, um nicht vertrauenswürdige Dokumente vom System zu isolieren. Das Erstellen eines Containers und das Einrichten des Application Guard-Containers zum Öffnen Office Dokumente hat einen Leistungsaufwand, der sich negativ auf die Benutzererfahrung auswirken kann, wenn Benutzer ein nicht vertrauenswürdiges Dokument öffnen.

Um Benutzern die erwartete Dateiöffnungserfahrung zu bieten, verwendet Application Guard Logik, um einen Container vorab zu erstellen, wenn die folgende Heuristik auf einem System erfüllt ist: Ein Benutzer hat in den letzten 28 Tagen eine Datei in der geschützten Ansicht oder in Application Guard geöffnet.

Wenn diese Heuristik erfüllt ist, erstellt Office einen Application Guard-Container für den Benutzer, nachdem er sich bei Windows angemeldet hat. Während dieser Vorgang vor der Erstellung ausgeführt wird, kann die Leistung des Systems langsam sein, aber der Effekt wird aufgelöst, sobald der Vorgang abgeschlossen ist.

> [!NOTE]
> Die Hinweise, die für die Heuristik erforderlich sind, um den Container vorab zu erstellen, werden von Office Anwendungen generiert, während ein Benutzer ihn verwendet. Wenn ein Benutzer Office auf einem neuen System installiert, in dem Application Guard aktiviert ist, erstellt Office den Container erst vor dem ersten Öffnen eines nicht vertrauenswürdigen Dokuments auf dem System. Der Benutzer wird feststellen, dass das Öffnen dieser ersten Datei in Application Guard länger dauert.

## <a name="known-issues"></a>Bekannte Probleme

* Wenn Sie Weblinks ( oder ) auswählen, `http` wird der Browser nicht `https` geöffnet.
* Die Standardeinstellung für die Richtlinie zum Schutz vor Kopieren und Einfügen besteht darin, den Zugriff in der Zwischenablage nur auf Text zu aktivieren.
* Die Standardeinstellung für die Schutzrichtlinie für nicht unterstützte Dateitypen besteht darin, das Öffnen nicht vertrauenswürdiger, nicht unterstützter Dateitypen zu blockieren, die verschlüsselt sind oder für die IRM (Information Rights Management) festgelegt ist. Dazu gehören Dateien, die über Microsoft Information Protection Vertraulichkeitsbezeichnungen verfügen, die Verschlüsselung (vertraulich oder streng vertraulich) verwenden.
* CSV- und HTML-Dateien werden derzeit nicht unterstützt.
* Application Guard für Office funktioniert derzeit nicht mit komprimierten NTFS-Volumes. Wenn der Fehler "ERROR_VIRTUAL_DISK_LIMITATION" angezeigt wird, versuchen Sie, die Komprimierung des Volumes aufzuheben.
* Updates für .NET können dazu führen, dass Dateien in Application Guard nicht geöffnet werden. Als Problemumgehung können Benutzer ihr Gerät neu starten, wenn sie auf diesen Fehler stoßen. Erfahren Sie mehr über das Problem beim [Empfangen einer Fehlermeldung beim Versuch, Windows Defender Application Guard oder Windows Sandbox zu öffnen.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
* Weitere Informationen finden Sie unter [häufig gestellte Fragen – Microsoft Defender Application Guard.](/windows/security/threat-protection/microsoft-defender-application-guard/faq-md-app-guard) 
