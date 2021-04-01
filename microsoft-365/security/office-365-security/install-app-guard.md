---
title: Application Guard für Office 365 für Administratoren
keywords: Application Guard, Protection, Isolation, isolierter Container, Hardwareisolation
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
description: Hier erhalten Sie die neueste hardwarebasierte Isolation. Verhindern Sie, dass aktuelle und aufkommende Angriffe wie Exploits oder bösartige Links die Produktivität der Mitarbeiter und die Unternehmenssicherheit beeinträchtigen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d0fa6ad884c6b21457c8359cf82e32e4b8c100ba
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488311"
---
# <a name="application-guard-for-office-for-admins"></a>Application Guard für Office für Administratoren

**Gilt für:** Word, Excel und PowerPoint für Microsoft 365, Windows 10 Enterprise

Microsoft Defender Application Guard für Office (Application Guard für Office) verhindert, dass nicht vertrauenswürdige Dateien auf vertrauenswürdige Ressourcen zugreifen, um Ihr Unternehmen vor neuen und neuen Angriffen zu schützen. Dieser Artikel führt Administratoren durch das Einrichten von Geräten für eine Vorschau von Application Guard für Office. Es enthält Informationen zu Systemanforderungen und Installationsschritten, um Application Guard für Office auf einem Gerät zu aktivieren.

## <a name="prerequisites"></a>Voraussetzungen

### <a name="minimum-hardware-requirements"></a>Mindesthardwareanforderungen

* **CPU:** 64-Bit, 4 Kerne (physisch oder virtuell), Virtualisierungserweiterungen (Intel VT-x ODER AMD-V), Core i5-Äquivalent oder höher empfohlen
* **Physischer Speicher**: 8 GB RAM
* **Festplatte:** 10 GB freier Speicherplatz auf dem Systemlaufwerk (SSD empfohlen)

### <a name="minimum-software-requirements"></a>Mindestanforderungen an die Software

* **Windows 10**: Windows 10 Enterprise Edition, Client Build Version 2004 (20H1) Build 19041 oder höher
* **Office**: Office Current Channel and Monthly Enterprise Channel, Build Version 2011 16.0.13530.10000 oder höher. Sowohl 32-Bit- als auch 64-Bit-Versionen von Office werden unterstützt.
* **Updatepaket**: Kumulatives monatliches Sicherheitsupdate für Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Ausführliche Systemanforderungen finden Sie unter [System requirements for Microsoft Defender Application Guard](/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Lesen Sie auch die Anleitungen ihres Computerherstellers zum Aktivieren der Virtualisierungstechnologie.
Weitere Informationen zu Office-Updatekanälen finden Sie [unter Übersicht über Updatekanäle für Microsoft 365](/deployoffice/overview-update-channels).

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

* Microsoft 365 E5 oder Microsoft 365 E5 Security

## <a name="deploy-application-guard-for-office"></a>Bereitstellen von Application Guard für Office

### <a name="enable-application-guard-for-office"></a>Aktivieren von Application Guard für Office

1. Herunterladen und Installieren **von kumulativen monatlichen Windows 10-Sicherheitsupdates KB4571756**.

2. Wählen **Sie Microsoft Defender Application Guard** unter Windows-Features aus, und wählen Sie OK **aus.** Wenn Sie das Application Guard-Feature aktivieren, wird ein Systemneustart ausgeführt. Sie können jetzt oder nach Schritt 3 einen Neustart durchführen.

   ![Dialogfeld "Windows-Features" mit AG](../../media/ag03-deploy.png)

   Das Feature kann auch durch Ausführen des folgenden PowerShell-Befehls als Administrator aktiviert werden:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Suchen Sie **im verwalteten Modus** nach Microsoft Defender Application Guard , einer Gruppenrichtlinie in **Computerkonfiguration Administrative Vorlagen \\ \\ Windows-Komponenten \\ Microsoft Defender Application Guard**. Aktivieren Sie diese Richtlinie, indem Sie den Wert unter Optionen **als 2** oder **3** festlegen und dann **OK** oder **Anwenden auswählen.**

   ![Aktivieren der AG im verwalteten Modus](../../media/ag04-deploy.png)

   Stattdessen können Sie die entsprechende #A0 festlegen:

   > OMA-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard** <br> Datentyp: **Integer** <br> Wert: **2**

4. Starten Sie das System neu.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Festlegen von Diagnosedaten & Feedback zum Senden vollständiger Daten

> [!NOTE]
> Dies ist nicht erforderlich, das Konfigurieren optionaler Diagnosedaten hilft jedoch, gemeldete Probleme zu diagnostizieren.

Dieser Schritt stellt sicher, dass die daten, die zum Identifizieren und Beheben von Problemen erforderlich sind, Microsoft erreichen. Führen Sie die folgenden Schritte aus, um die Diagnose auf Ihrem Windows-Gerät zu aktivieren:

1. Öffnen **Sie Einstellungen** im Startmenü.

   ![Startmenü](../../media/ag05-diagnostic.png)

2. Wählen **Sie unter Windows-Einstellungen** **die Option Datenschutz aus.**

   ![Menü "Windows-Einstellungen"](../../media/ag06-diagnostic.png)

3. Wählen Sie unter Datenschutz die Option **Diagnose & Feedback aus,** und wählen Sie **Optionale Diagnosedaten aus.**

   ![Diagnose- und Feedbackmenü](../../media/ag07a-diagnostic.png)

Weitere Informationen zum Konfigurieren von Windows-Diagnoseeinstellungen finden Sie unter [Configuring Windows diagnostic data in your organization](/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Bestätigen, dass Application Guard für Office aktiviert und funktioniert

Bevor Sie bestätigen, dass Application Guard für Office aktiviert ist, starten Sie Word, Excel oder PowerPoint auf einem Gerät, auf dem die Richtlinien bereitgestellt wurden. Stellen Sie sicher, dass Office aktiviert ist. Möglicherweise müssen Sie Ihre Arbeitsidentität verwenden, um das Office-Produkt zuerst zu aktivieren.

Um zu bestätigen, dass Application Guard für Office aktiviert ist, starten Sie Word, Excel oder PowerPoint, und öffnen Sie dann ein nicht vertrauenswürdiges Dokument. Sie können beispielsweise ein Dokument öffnen, das aus dem Internet heruntergeladen wurde, oder eine E-Mail-Anlage von einer Person außerhalb Ihrer Organisation öffnen.

Wenn Sie zum ersten Mal eine nicht vertrauenswürdige Datei öffnen, wird möglicherweise ein Office-Begrüßungsbildschirm wie im folgenden Beispiel angezeigt. Es wird möglicherweise einige Zeit angezeigt, während Application Guard für Office aktiviert wird und die Datei geöffnet wird. Nachfolgende Öffnungen nicht vertrauenswürdiger Dateien sollten schneller ausgeführt werden.

![Begrüßungsbildschirm der Office-App](../../media/ag08-confirm.png)

Beim Öffnen sollte die Datei einige visuelle Indikatoren anzeigen, dass die Datei in Application Guard für Office geöffnet wurde:

* Eine Callout im Menüband

  ![Dokumentdatei mit kleinem App Guard-Hinweis](../../media/ag09-confirm.png)

* Das Anwendungssymbol mit einem Schild in der Taskleiste

  ![Symbol in der Taskleiste](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Konfigurieren von Application Guard für Office

Office unterstützt die folgenden Richtlinien, mit denen Sie die Funktionen von Application Guard für Office konfigurieren können. Diese Richtlinien können über Gruppenrichtlinien oder über den [Office-Cloudrichtliniendienst konfiguriert werden.](/DeployOffice/overview-office-cloud-policy-service)
Weitere Informationen finden Sie unter Configuration Set by your administrator by review group policy settings in  **User Configuration Administrative Templates Microsoft Office \\ \\ 2016 \\ Security Settings Trust Center Application \\ \\ Guard**.


> [!NOTE]
> Durch das Konfigurieren dieser Richtlinien können einige Funktionen für Dateien deaktiviert werden, die in Application Guard für Office geöffnet wurden.

|Richtlinie|Beschreibung|
|---|---|
|Application Guard für Office nicht verwenden|Wenn Sie diese Richtlinie aktivieren, müssen Word, Excel und PowerPoint den Isolationscontainer geschützte Ansicht anstelle von Application Guard für Office verwenden. Diese Richtlinie kann verwendet werden, um Application Guard für Office vorübergehend zu deaktivieren, wenn Probleme beim Aktivieren für Microsoft Edge auftreten.|
|Konfigurieren der Vorerstellung von Application Guard für Office-Containern|Diese Richtlinie bestimmt, ob der Application Guard für Office-Container zum Isolieren nicht vertrauenswürdiger Dateien für eine verbesserte Laufzeitleistung vorab erstellt wurde. Wenn Sie diese Einstellung aktivieren, können Sie die Anzahl der Tage angeben, um mit dem Erstellen eines Containers fortzufahren, oder den Container vom office-integrierten heuristischen Vor erstellen zu lassen.
|Kopieren/Einfügen für In Application Guard für Office geöffnete Office-Dokumente nicht zulassen|Wenn Sie diese Richtlinie aktivieren, wird verhindert, dass ein Benutzer Inhalte aus einem Dokument kopiert und einfügen kann, das in Application Guard für Office geöffnet wurde, in ein Dokument, das außerhalb des Dokuments geöffnet wurde.|
|Deaktivieren der Hardwarebeschleunigung in Application Guard für Office|Diese Richtlinie steuert, ob Application Guard für Office die Hardwarebeschleunigung zum Rendern von Grafiken verwendet. Wenn Sie diese Einstellung aktivieren, verwendet Application Guard für Office softwarebasiertes Rendering (CPU) und geladen keine Grafiktreiber von Drittanbietern oder interagiert mit verbundenen Grafikhardware.
|Deaktivieren des Schutzes nicht unterstützter Dateitypen in Application Guard für Office|Diese Richtlinie steuert, ob Application Guard für Office das Öffnen nicht unterstützter Dateitypen blockiert oder ob die Umleitung zur geschützten Ansicht aktiviert wird.
|Deaktivieren des Kamera- und Mikrofonzugriffs für Dokumente, die in Application Guard für Office geöffnet wurden|Wenn Sie diese Richtlinie aktivieren, wird Office der Zugriff auf die Kamera und das Mikrofon in Application Guard for Office entfernt.|
|Einschränken des Druckens von Dokumenten, die in Application Guard für Office geöffnet wurden|Wenn Sie diese Richtlinie aktivieren, werden die Drucker, auf die ein Benutzer aus einer in Application Guard für Office geöffneten Datei drucken kann, begrenzt. Sie können diese Richtlinie beispielsweise verwenden, um Benutzer auf das Drucken in PDF zu beschränken.|
|Verhindern, dass Benutzer Application Guard for Office Protection für Dateien entfernen|Durch Aktivieren dieser Richtlinie wird die Option (innerhalb der Office-Anwendungserfahrung) zum Deaktivieren des Application Guard for Office-Schutzes oder zum Öffnen einer Datei außerhalb von Application Guard für Office entfernt. <p> **Hinweis:** Benutzer können diese Richtlinie weiterhin umgehen, indem sie die Mark-of-the-Web-Eigenschaft manuell aus der Datei entfernen oder ein Dokument an einen vertrauenswürdigen Speicherort verschieben.|
|

> [!NOTE]
> Die folgenden Richtlinien erfordern, dass sich der Benutzer abmeldet und sich erneut bei Windows anmeldet, um wirksam zu werden:
>
> * Kopieren/Einfügen für Dokumente deaktivieren, die in Application Guard für Office geöffnet wurden
> * Einschränken des Druckens für Dokumente, die in Application Guard for Office geöffnet wurden
> * Deaktivieren des Kamera- und Mikrofonzugriffs auf Dokumente, die in Application Guard für Office geöffnet wurden

## <a name="submit-feedback"></a>Feedback senden

### <a name="submit-feedback-via-feedback-hub"></a>Senden von Feedback über den Feedbackhub

Wenn beim Starten von Application Guard für Office Probleme auftreten, werden Sie aufgefordert, Ihr Feedback über den Feedbackhub zu übermitteln:

1. Öffnen Sie die **Feedback Hub-App,** und melden Sie sich an.

2. Wenn beim Starten von Application Guard ein Fehlerdialogfeld angezeigt wird, wählen Sie im Fehlerdialogfeld Bericht an **Microsoft** aus, um eine neue Feedbackübermittlung zu starten. Navigieren Sie andernfalls zu, um die richtige Kategorie für Application Guard auszuwählen, und wählen Sie dann Neues Feedback <https://aka.ms/mdagoffice-fb> **+ &nbsp; hinzufügen** in der nähe der oberen rechten Seite aus.

3. Geben Sie eine Zusammenfassung in das **Feld Feedback zusammenfassen** ein, wenn sie noch nicht für Sie ausgefüllt ist.

4. Geben Sie eine detaillierte Beschreibung des Problems ein, das Sie erfahren haben, und welche Schritte Sie im Feld **Ausführlicher** erklären unternommen haben, und wählen Sie dann **Weiter aus.**

5. Wählen Sie die Blase neben **Problem aus.** Stellen Sie sicher, dass die ausgewählte Kategorie **Sicherheit und Datenschutz Microsoft Defender Application Guard – \> Office** ist, und wählen Sie dann **Weiter aus.**

6. Wählen **Sie Neues Feedback** und dann Weiter **aus.**

7. Sammeln von Ablaufverfolgungen zu dem Problem:

   1. Erweitern Sie die **Kachel Mein Problem neu** erstellen.

   2. Wenn das Problem auftritt, das während der Ausführung von Application Guard auftritt, öffnen Sie eine Application Guard-Instanz. Durch das Öffnen einer Instanz können zusätzliche Ablaufverfolgungen im Application Guard-Container erfasst werden.

   3. Wählen **Sie Aufzeichnung starten** aus, und warten Sie, bis die Kachel nicht mehr dreht, und sagen Sie Aufzeichnung *beenden*.

   4. Reproduzieren Sie das Problem vollständig mit Application Guard. Die Vervielfältigung kann den Versuch umfassen, eine Application Guard-Instanz zu starten und zu warten, bis ein Fehler auftritt, oder die Wiedergabe eines Problems in einer ausgeführten Application Guard-Instanz.

   5. Wählen Sie die **Kachel Aufzeichnung beenden** aus.

   6. Lassen Sie alle ausgeführten Application Guard-Instanzen geöffnet, auch für einige Minuten nach der Übermittlung, damit auch Containerdiagnosen erfasst werden können.

8. Fügen Sie alle relevanten Screenshots oder Dateien an, die mit dem Problem in Zusammenhang stehen.

9. Wählen Sie **Senden** aus.

### <a name="submit-feedback-via-office-customer-voice"></a>Senden von Feedback über Office Customer Voice

Sie können auch Feedback von Office übermitteln, wenn das Problem eintritt, wenn Office-Dokumente in Application Guard geöffnet werden. Informationen zum Übermitteln von Feedback finden Sie im [Office-Insider-Handbuch.](https://insider.office.com/handbook)

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integration in Microsoft Defender for Endpoint und Microsoft Defender für Office 365

Application Guard für Office ist in Microsoft Defender for Endpoint integriert, um Überwachung und Warnung bei bösartigen Aktivitäten in der isolierten Umgebung zu ermöglichen.

[Sichere Dokumente in Microsoft E365 E5](/microsoft-365/security/office-365-security/safe-docs) ist ein Feature, das Microsoft Defender for Endpoint zum Überprüfen von Dokumenten verwendet, die in Application Guard für Office geöffnet wurden. Für eine zusätzliche Schutzebene können Benutzer Application Guard for Office erst verlassen, wenn die Ergebnisse der Überprüfung ermittelt wurden.

Microsoft Defender for Endpoint ist eine Sicherheitsplattform, die Unternehmensnetzwerken dabei helfen soll, erweiterte Bedrohungen zu verhindern, zu erkennen, zu untersuchen und auf sie zu reagieren. Weitere Informationen zu dieser Plattform finden Sie unter [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp). Weitere Informationen zum Onboarding von Geräten auf dieser Plattform finden Sie unter [Onboarding devices to the Microsoft Defender for Endpoint service](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

Sie können Microsoft Defender für Office 365 auch für die Zusammenarbeit mit Defender for Endpoint konfigurieren. Weitere Informationen finden Sie unter [Integrate Defender for Office 365 with Microsoft Defender for Endpoint](integrate-office-365-ti-with-mde.md).

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen

* Application Guard für Office ist ein geschützter Modus, der nicht vertrauenswürdige Dokumente isoliert, sodass sie nicht auf vertrauenswürdige Unternehmensressourcen, ein Intranet, die Identität des Benutzers und beliebige Dateien auf dem Computer zugreifen können. Wenn ein Benutzer versucht, auf ein Feature zu zugreifen, das von einem solchen Zugriff abhängig ist (z. B. das Einfügen eines Bilds aus einer lokalen Datei auf dem Datenträger), führt der Zugriff zu einem Fehler und erzeugt eine Eingabeaufforderung wie im folgenden Beispiel. Damit ein nicht vertrauenswürdiges Dokument auf vertrauenswürdige Ressourcen zugreifen kann, müssen Benutzer den Application Guard-Schutz aus dem Dokument entfernen.

  ![Dialogfeld mit der Aussage, dass dieses Feature nicht verfügbar ist, um Die Sicherheit zu gewährleisten](../../media/ag10-limitations.png)

  > [!NOTE]
  > Raten Sie Benutzern, den Schutz nur zu entfernen, wenn sie der Datei und ihrer Quelle vertrauen oder woher sie stammt.

* Aktive Inhalte in Dokumenten wie Makros ActiveX Steuerelementen sind in Application Guard für Office deaktiviert. Benutzer müssen den Application Guard-Schutz entfernen, um aktive Inhalte zu aktivieren.

* Nicht vertrauenswürdige Dateien aus Netzwerkfreigaben oder Von OneDrive, OneDrive for Business oder SharePoint Online freigegebenen Dateien aus einer anderen Organisation, die in Application Guard als schreibgeschützt geöffnet sind. Benutzer können eine lokale Kopie dieser Dateien speichern, um im Container weiter zu arbeiten, oder den Schutz entfernen, um direkt mit der Ursprünglichen Datei zu arbeiten.

* Dateien, die durch die Verwaltung von Informationsrechten (Information Rights Management, IRM) geschützt sind, werden standardmäßig blockiert. Wenn Benutzer solche Dateien in der geschützten Ansicht öffnen möchten, muss ein Administrator Richtlinieneinstellungen für nicht unterstützte Dateitypen für die Organisation konfigurieren.

* Alle Anpassungen an Office-Anwendungen in Application Guard für Office werden nicht beibehalten, nachdem sich ein Benutzer ab- und erneut anmeldet oder nach dem Neustart des Geräts.

* Nur Barrierefreiheitstools, die das UIA-Framework verwenden, können für Dateien, die in Application Guard für Office geöffnet wurden, eine barrierefreie Benutzererfahrung bieten.

* Die Netzwerkkonnektivität ist für den ersten Start von Application Guard nach der Installation erforderlich. Die Konnektivität ist für Application Guard erforderlich, um die Lizenz zu überprüfen.

* Im Abschnitt "Informationen" des Dokuments zeigt die *Last Modified By-Eigenschaft* **möglicherweise WDAGUtilityAccount** als Benutzer an. WDAGUtilityAccount ist der anonyme Benutzer, der in Application Guard konfiguriert ist. Die Identität des Desktopbenutzers wird nicht im Application Guard-Container freigegeben.

## <a name="performance-optimizations-for-application-guard-for-office"></a>Leistungsoptimierungen für Application Guard für Office

Dieser Abschnitt enthält eine Übersicht über die Leistungsoptimierungen, die in Application Guard für Office verwendet werden. Diese Informationen können Administratoren bei der Diagnose von Berichten von Benutzern im Zusammenhang mit der Leistung von Office oder dem Gesamtsystem helfen, wenn Application Guard aktiviert ist.

Application Guard verwendet einen virtualisierten Container, um nicht vertrauenswürdige Dokumente vom System zu isolieren. Das Erstellen eines Containers und das Einrichten des Application Guard-Containers zum Öffnen von Office-Dokumenten hat einen Leistungsaufwand, der sich negativ auf die Benutzerfreundlichkeit auswirken kann, wenn Benutzer ein nicht vertrauenswürdiges Dokument öffnen.

Um Benutzern die erwartete Dateiöffnungserfahrung zu bieten, verwendet Application Guard Logik, um einen Container vorab zu erstellen, wenn die folgende Heuristik auf einem System erfüllt ist: Ein Benutzer hat in den letzten 28 Tagen eine Datei in der geschützten Ansicht oder in Application Guard geöffnet.

Wenn diese Heuristik erfüllt ist, erstellt Office nach der Anmeldung bei Windows einen Application Guard-Container für den Benutzer. Während dieser Vorgang vor dem Erstellen ausgeführt wird, tritt möglicherweise eine langsame Leistung auf, aber der Effekt wird behoben, sobald der Vorgang abgeschlossen ist.

> [!NOTE]
> Die Hinweise, die für die Heuristik zum Vorab erstellen des Containers erforderlich sind, werden von Office-Anwendungen generiert, wenn sie von einem Benutzer verwendet werden. Wenn ein Benutzer Office auf einem neuen System installiert, auf dem Application Guard aktiviert ist, erstellt Office den Container erst vor dem ersten Öffnen eines nicht vertrauenswürdigen Dokuments auf dem System. Der Benutzer wird feststellen, dass das Öffnen dieser ersten Datei in Application Guard länger dauert.

## <a name="known-issues"></a>Bekannte Probleme

* Wenn Sie Weblinks ( `http` `https` oder ) auswählen, wird der Browser nicht geöffnet.
* Das Pasting von Inhalten oder Bildern im Rich-Text-Format (Rich Text Format, RTF) in Office-Dokumenten, die mit Application Guard geöffnet wurden, wird derzeit nicht unterstützt.
* Die Standardeinstellung für die Schutzrichtlinie für nicht unterstützte Dateitypen besteht im Blockieren des Öffnens nicht vertrauenswürdiger nicht unterstützter Dateitypen der Verwaltung von Informationsrechten (Information Rights Management, IRM), CSV oder HTML.
* Updates für .NET können dazu führen, dass Dateien in Application Guard nicht geöffnet werden. Als Problemumgehung können Benutzer ihr Gerät neu starten, wenn dieser Fehler vor sich geht. Weitere Informationen zum Problem finden Sie unter Empfangen einer Fehlermeldung beim Versuch, Windows Defender [Application Guard oder Windows Sandbox zu öffnen.](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap)
