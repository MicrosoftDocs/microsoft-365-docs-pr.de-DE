---
title: Application Guard für Office 365 (Public Preview) für Administratoren
keywords: Anwendungsschutz, Schutz, Isolierung, isolierter Container, Hardware Isolierung
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Holen Sie sich die neuesten hardwarebasierten Isolierungen. Verhindern Sie, dass aktuelle und neue Angriffe wie Exploits oder böswillige Links die Produktivität von Mitarbeitern und die Unternehmenssicherheit beeinträchtigen.
ms.openlocfilehash: c9b31ff91521b6badda31b6eb3202f370769a0fd
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021073"
---
# <a name="application-guard-for-office-public-preview-for-admins"></a>Application Guard für Office (Public Preview) für Administratoren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Gilt für:** Word, Excel und PowerPoint für Microsoft 365, Windows 10 Enterprise

>[!IMPORTANT]
>Einige Informationen beziehen sich auf ein vorab veröffentlichtes Produkt, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann. Microsoft übernimmt mit diesen Informationen keinerlei Gewährleistung, sei sie ausdrücklich oder konkludent.

Microsoft Defender Application Guard für Office (Application Guard für Office) hilft zu verhindern, dass nicht vertrauenswürdige Dateien auf vertrauenswürdige Ressourcen zugreifen, sodass Ihr Unternehmen vor neuen und neu auftretenden Angriffen geschützt ist. In diesem Artikel werden die Administratoren durch das Einrichten von Geräten für eine Vorschau des Application Guard für Office unterwandert. Es enthält Informationen zu Systemanforderungen und Installationsschritten, um Application Guard für Office auf einem Gerät zu aktivieren.

## <a name="prerequisites"></a>Voraussetzungen

### <a name="minimum-hardware-requirements"></a>Minimale Hardwareanforderungen

* **CPU** : 64-Bit, 4 Kerne (physisch oder virtuell), Virtualization Extensions (Intel VT-x oder AMD-V), Core i5 Äquivalent oder höher empfohlen
* **Physischer Arbeitsspeicher** : 8 GB RAM
* **Festplatte** : 10 GB freier Speicherplatz auf dem Systemlaufwerk (SSD empfohlen)

### <a name="minimum-software-requirements"></a>Mindestanforderungen an die Software

* **Windows 10** : Windows 10 Enterprise Edition, Client Build Version 2004 (20H1) Build 19041
* **Office** : Office Beta Channel Build Version 2008 16.0.13212 oder höher
* **Update Paket** : kumulative monatliche Sicherheitsupdates für Windows 10 [KB4571756](https://support.microsoft.com/help/4571756/windows-10-update-KB4571756)

Ausführliche Systemanforderungen finden Sie unter [System Requirements for Microsoft Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/reqs-md-app-guard). Weitere Informationen zu Builds für Office-Insider-Vorschau finden Sie unter [Erste Schritte bei der Bereitstellung von Office-Insider-Builds](https://insider.office.com/business/deploy).

### <a name="licensing-requirements"></a>Lizenzierungsanforderungen

* Microsoft 365 E5 oder Microsoft 365 E5-Sicherheit

## <a name="deploy-application-guard-for-office"></a>Bereitstellen von Application Guard für Office

### <a name="enable-application-guard-for-office"></a>Aktivieren von Application Guard für Office

1. Herunterladen und Installieren von **kumulativen monatlichen Sicherheitsupdates für Windows 10 KB4571756**.

2. Wählen Sie **Microsoft Defender Application Guard** unter Windows-Features aus, und klicken Sie auf **OK**. Durch Aktivieren des Application Guard-Features wird ein Systemneustart aufgefordert. Sie können entscheiden, ob Sie jetzt oder nach Schritt 3 einen Neustart durchführen möchten.

   ![Dialogfeld "Windows-Features" mit AG](../../media/ag03-deploy.png)

   Das Feature kann auch durch Ausführen des folgenden PowerShell-Befehls als Administrator aktiviert werden:

   ```powershell
   Enable-WindowsOptionalFeature -online -FeatureName Windows-Defender-ApplicationGuard
   ```

3. Suchen Sie nach dem Microsoft Defender Application Guard im Managed Mode-Gruppenrichtlinien unter **Computer Configuration \\ Administrative Templates \\ Windows Components \\ Microsoft Defender Application Guard**. Aktivieren Sie diese Richtlinie, indem Sie den Wert unter Optionen als **2** oder **3** festlegen und dann **OK** oder über **nehmen** auswählen.

   ![Aktivieren von AG im verwalteten Modus](../../media/ag04-deploy.png)

   Alternativ können Sie die entsprechende CSP-Richtlinie festlegen:

   Oma-URI: **./Device/Vendor/MSFT/WindowsDefenderApplicationGuard/Settings/AllowWindowsDefenderApplicationGuard**<br/>
   Datentyp: **Integer**<br/>
   Wert: **2**

4. Starten Sie das System neu.

### <a name="set-diagnostics--feedback-to-send-full-data"></a>Festlegen der Diagnose & Feedback zum Senden vollständiger Daten

In diesem Schritt wird sichergestellt, dass die zum Identifizieren und Beheben von Problemen erforderlichen Daten Microsoft erreichen. Führen Sie die folgenden Schritte aus, um die Diagnose auf Ihrem Windows-Gerät zu aktivieren:

1. Öffnen Sie im Startmenü **Einstellungen** .

   ![Startmenü](../../media/ag05-diagnostic.png)

2. Wählen Sie unter **Windows-Einstellungen** die Option **Datenschutz** aus.

   ![Menü "Windows-Einstellungen"](../../media/ag06-diagnostic.png)

3. Wählen Sie unter Datenschutz die Option **Diagnose & Feedback** aus, und wählen Sie **optionale Diagnosedaten** aus.

   ![Diagnose-und Feedback Menü](../../media/ag07a-diagnostic.png)

Weitere Informationen zum Konfigurieren von Windows-Diagnoseeinstellungen finden Sie unter [Konfigurieren von Windows-Diagnosedaten in Ihrer Organisation](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).

### <a name="confirm-that-application-guard-for-office-is-enabled-and-working"></a>Sicherstellen, dass Application Guard für Office aktiviert und funktionsfähig ist

Bevor Sie bestätigen, dass der Application Guard für Office aktiviert ist, starten Sie Word, Excel oder PowerPoint auf einem Gerät, auf dem die Richtlinien bereitgestellt wurden. Stellen Sie sicher, dass Office aktiviert ist. Möglicherweise müssen Sie Ihre Arbeitsidentität verwenden, um das Office-Produkt zuerst zu aktivieren.

Um zu bestätigen, dass Application Guard für Office jetzt aktiviert ist, starten Sie Word, Excel oder PowerPoint, und öffnen Sie ein nicht vertrauenswürdiges Dokument. Sie können beispielsweise ein aus dem Internet heruntergeladenes Dokument oder eine e-Mail-Anlage von einer Person außerhalb Ihrer Organisation öffnen.

Beim ersten Start einer nicht vertrauenswürdigen Datei wird möglicherweise ein Begrüßungsbildschirm für Office wie unten angezeigt. Es kann während einiger Zeit angezeigt werden, während Application Guard für Office aktiviert wird und die Datei geöffnet wird. Die nachfolgenden Starts von nicht vertrauenswürdigen Dateien sollten schneller erfolgen.

![Begrüßungsbildschirm für Office-App](../../media/ag08-confirm.png)

Nach dem Öffnen sollte die Datei einige visuelle Indikatoren anzeigen, die die Datei in Application Guard für Office geöffnet wurde:

* Eine Legende im Menüband

  ![Doc-Datei mit kleinem App-Guard-Hinweis](../../media/ag09-confirm.png)

* Das Anwendungssymbol mit einem Schild in der Taskleiste

  ![Symbol in der Taskleiste](../../media/ag12-limitations.png)

## <a name="configure-application-guard-for-office"></a>Konfigurieren von Application Guard für Office

Office unterstützt die folgenden Richtlinien, damit Sie die Funktionen von Application Guard für Office konfigurieren können. Diese Richtlinien können über Gruppenrichtlinien oder über den Office-Cloud-Richtlinien Dienst konfiguriert werden.

> [!NOTE]
> Diese Richtlinien werden in Kürze verfügbar sein.
> Außerdem kann das Konfigurieren dieser Richtlinien einige Funktionen für Dateien deaktivieren, die in Application Guard für Office geöffnet wurden.

|Richtlinie|Beschreibung|
|---|---|
|Deaktivieren von Application Guard für Office|Durch Aktivieren dieser Richtlinie wird erzwungen, dass Word, Excel und PowerPoint den geschützten Ansichts Isolations Container anstelle von Application Guard für Office verwenden. Diese Richtlinie kann verwendet werden, um den Application Guard für Office vorübergehend zu deaktivieren, wenn Probleme bei der Aktivierung für Edge bestehen.|
|Kopieren/Einfügen für in Application Guard geöffnete Dokumente deaktivieren|Durch Aktivieren dieser Richtlinie wird verhindert, dass ein Benutzer Inhalte aus einem Dokument kopiert und einfügt, das in Application Guard für Office geöffnet wurde, in einem Dokument, das außerhalb des Dokuments geöffnet wurde.|
|Verhindern, dass Benutzer den Anwendungsschutz für Dateien entfernen|Durch Aktivieren dieser Richtlinie wird die Option (innerhalb der Office-Anwendungsumgebung) entfernt, um den Anwendungsschutz zu deaktivieren oder eine Datei außerhalb des Application Guard-Schutzes zu öffnen. <p> **Hinweis:** Benutzer können diese Richtlinie weiterhin umgehen, indem Sie die Eigenschaft "Mark-of-the-Internet" manuell aus der Datei entfernen oder ein Dokument an einen vertrauenswürdigen Speicherort verschieben.|
|Einschränken des Druckens von Dokumenten, die in Application Guard geöffnet wurden|Durch Aktivieren dieser Richtlinie werden Drucker, auf die ein Benutzer drucken kann, aus einer Datei eingeschränkt, die in Application Guard für Office geöffnet wurde. Beispielsweise können Sie diese Richtlinie verwenden, um Benutzer so einzuschränken, dass Sie nur in PDF drucken.|
|Deaktivieren des Kamera-und Mikrofon Zugriffs für in Application Guard geöffnete Dokumente|Durch Aktivieren dieser Richtlinie wird Office-Zugriff auf die Kamera und das Mikrofon in Application Guard für Office entfernt.|
|

> [!NOTE]
> Die folgenden Richtlinien erfordern, dass der Benutzer sich abmeldet und sich erneut an Windows anmeldet, um wirksam zu werden:
>
> * Kopieren/Einfügen für in Application Guard geöffnete Dokumente deaktivieren
> * Einschränken des Druckens für in Application Guard geöffnete Dokumente
> * Deaktivieren des Kamera-und Mic-Zugriffs auf Dokumente, die in Application Guard geöffnet wurden

## <a name="submit-feedback"></a>Feedback senden

### <a name="submit-feedback-via-feedback-hub"></a>Feedback über Feedback-Hub senden

Wenn beim Starten von Application Guard für Office Probleme auftreten, werden Sie aufgefordert, Ihr Feedback über Feedback-Hub zu übermitteln:

1. Öffnen Sie die **Feedback-Hub-App** , und melden Sie sich an.

2. Wenn Sie beim Starten von Application Guard ein Fehlerdialogfeld erhalten, wählen Sie im Dialogfeld Fehler die Option **Bericht an Microsoft** aus, um eine neue Feedback Übermittlung zu starten. Navigieren Sie andernfalls zu, <https://aka.ms/wdagoffice-fb> um die richtige Kategorie für den Anwendungsschutz auszuwählen, und wählen Sie dann **+ Neues Feedback** in der oberen rechten Ecke hinzufügen aus.

3. Füllen Sie das Feld **Feedback zusammenfassen** aus, falls es nicht bereits für Sie ausgefüllt ist.

4. Geben Sie im Feld **EXPLAIN in more Detail** eine ausführliche Beschreibung des Problems ein, das Sie durchgeführt haben, und wählen Sie dann **weiter** aus.

5. Wählen Sie die Blase neben Problem. Stellen Sie sicher, dass es sich bei der ausgewählten Kategorie um **Sicherheit und Datenschutz \> Microsoft Defender Application Guard – Office** handelt, und wählen Sie dann **weiter** aus.

6. Wählen Sie **Neues Feedback** und dann **weiter** aus.

7. Sammeln von Ablaufverfolgungen für das Problem:

   1. Erweitern Sie die Kachel **mein Problem neu erstellen** .

   2. Wenn das auftretende Problem während der Ausführung von Application Guard auftritt, öffnen Sie eine Application Guard-Instanz. Auf diese Weise können zusätzliche Ablaufverfolgungen innerhalb des Application Guard-Containers gesammelt werden.

   3. Wählen Sie **Start Aufzeichnung** und warten Sie, bis die Kachel nicht mehr dreht und sagen Sie die *Aufzeichnung beenden*.

   4. Reproduzieren Sie das Problem mit Application Guard vollständig. Dies umfasst möglicherweise den Versuch, eine Application Guard-Instanz zu starten und zu warten, bis Sie fehlschlägt oder ein Problem in einer ausgeführten Application Guard-Instanz reproduziert.

   5. Wählen Sie die Kachel **Aufzeichnung beenden** aus.

   6. Lassen Sie alle ausgeführten Application Guard-Instanzen/s geöffnet, sogar bis einige Minuten nach der Übermittlung, damit die Container Diagnose auch erfasst werden kann.

8. Fügen Sie relevante Screenshots oder Dateien im Zusammenhang mit dem Problem hinzu.

9. Wählen Sie **Senden** aus.

### <a name="submit-feedback-via-office-customer-voice"></a>Übermitteln von Feedback über die Office-Kundenstimme

Sie können auch Feedback von in Office senden, wenn das Problem auftritt, wenn Office-Dokumente in Application Guard geöffnet werden. Lesen Sie das [Office Insider Handbook](https://insider.office.com/handbook) , um Feedback zu senden.

## <a name="integration-with-microsoft-defender-for-endpoint-and-microsoft-defender-for-office-365"></a>Integration mit Microsoft Defender für Endpoint und Microsoft Defender für Office 365

Application Guard für Office ist in Microsoft Defender for Endpoint integriert, um Überwachung und Warnungen zu böswilligen Aktivitäten in der isolierten Umgebung bereitzustellen.

Microsoft Defender für Endpoint ist eine Sicherheitsplattform, die dazu dient, Unternehmensnetzwerken beim verhindern, erkennen, untersuchen und reagieren auf Erweiterte Bedrohungen zu unterstützen. Weitere Informationen zu dieser Plattform finden Sie auf der Seite [Microsoft Defender for Endpoint](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp) . Erfahren Sie mehr über Onboarding Devices to this Platform on [Bord Devices to the Microsoft Defender for Endpoint Service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure).

Sie können Microsoft Defender auch so konfigurieren, dass Office 365 mit Defender for Endpoint zusammenarbeiten. Siehe [integrieren von Defender für Office 365 mit Microsoft Defender für Endpoint](integrate-office-365-ti-with-wdatp.md).

## <a name="limitations-and-considerations"></a>Einschränkungen und Überlegungen

* Application Guard für Office ist ein eingeschränkter Modus, der nicht vertrauenswürdige Dokumente vom Zugriff auf vertrauenswürdige Unternehmensressourcen, das Intranet, die Identität des Benutzers und beliebige Dateien isoliert, die auf dem Computer vorhanden sind. Wenn ein Benutzer versucht, auf ein Feature zuzugreifen, das eine Abhängigkeit von diesem Zugriff hat, beispielsweise das Einfügen eines Bilds aus einer lokalen Datei auf dem Datenträger, tritt ein Fehler auf und erzeugt eine Eingabeaufforderung wie die folgende. Um einem nicht vertrauenswürdigen Dokument den Zugriff auf vertrauenswürdige Ressourcen zu ermöglichen, müssen Benutzer den Application Guard Protection-Schutz aus dem Dokument entfernen.

  ![Dialog Feld mit dem Hinweis, dass Sie sicherstellen können, dass diese Funktion nicht verfügbar ist](../../media/ag10-limitations.png)

  > [!NOTE]
  > Weisen Sie die Benutzer an, den Schutz nur zu entfernen, wenn Sie der Datei und ihrer Quelle oder woher Sie vertrauen.

* Aktive Inhalte in Dokumenten wie Makros und ActiveX-Steuerelemente sind in Application Guard für Office deaktiviert. Benutzer müssen Application Guard Protection entfernen, um aktive Inhalte zu aktivieren.

* Nicht vertrauenswürdige Dateien, die von Netzwerkfreigaben oder Dateien geöffnet wurden, die von OneDrive, OneDrive für Unternehmen oder SharePoint Online aus einer anderen Organisation freigegeben wurden, sind in Application Guard schreibgeschützt geöffnet. Benutzer können eine lokale Kopie solcher Dateien speichern, um die Arbeit im Container fortzusetzen oder den Schutz zu entfernen, um die ursprüngliche Datei direkt zu bearbeiten.

* Dateien, die durch die Verwaltung von Informationsrechten (Information Rights Management, IRM) geschützt sind, werden weiterhin in der geschützten Ansicht geöffnet.

* Anpassungen an Office-Anwendungen in Application Guard für Office bleiben nicht bestehen, wenn sich ein Benutzer abmeldet und das Gerät erneut startet oder neu startet.

* Nur Barrierefreiheits Tools, die das UIA-Framework verwenden, können eine barrierefreie Umgebung für Dateien bieten, die in Application Guard für Office geöffnet wurden.

* Die Netzwerkkonnektivität ist für den ersten Start von Application Guard nach der Installation erforderlich. Dies ist für Application Guard erforderlich, um die Lizenz zu überprüfen.

* Im Abschnitt Info des Dokuments kann die Eigenschaft *zuletzt geändert von* WDAGUtilityAccount als Benutzer angezeigt werden. Dies ist der anonyme Benutzer, der in Application Guard konfiguriert wurde, da die Identität des Desktop Benutzers nicht innerhalb des Anwendungsschutz Containers freigegeben ist.

## <a name="performance-optimizations-for-application-guard"></a>Leistungsoptimierungen für Application Guard

Dieser Abschnitt enthält eine Übersicht über die Leistungsoptimierungen, die in Application Guard für Office verwendet werden. Mithilfe dieser Informationen können Administratoren Berichte von Benutzern diagnostizieren, die sich auf die Leistung von Office oder das Gesamtsystem beziehen, wenn Application Guard aktiviert ist.

Application Guard verwendet einen virtualisierten Container, um nicht vertrauenswürdige Dokumente außerhalb des Systems zu isolieren. Das Erstellen eines Containers und das Einrichten des Application Guard-Containers zum Öffnen von Office-Dokumenten hat einen Leistungsaufwand, der sich negativ auf die Benutzerfreundlichkeit auswirken kann, wenn Benutzer ein nicht vertrauenswürdiges Dokument öffnen.

Um Benutzern die erwartete Dateiöffnung zur Verfügung zu stellen, verwendet Application Guard die Logik, um einen Container vorab zu erstellen, wenn die folgende Heuristik auf einem System erfüllt ist: ein Benutzer hat in den letzten 28 Tagen eine Datei entweder in der geschützten Ansicht oder in der Anwendungsüberwachung geöffnet.

Wenn diese Heuristik erfüllt ist, erstellt Office vorab einen Application Guard-Container für den Benutzer, nachdem er sich bei Windows angemeldet hat. Wenn dieser Vorgang vor dem Erstellen ausgeführt wird, kann das System eine langsame Leistung erfahren. Dies wird behoben, sobald der Vorgang abgeschlossen ist.

> [!NOTE]
> Die Hinweise, die für die zum vorab erstellen des Containers verwendete Heuristik benötigt werden, werden von Office-Anwendungen generiert, wenn Sie von einem Benutzer verwendet werden. Wenn ein Benutzer Office auf einem neuen System installiert, auf dem Application Guard aktiviert ist, erstellt Office den Container erst nach dem ersten Öffnen eines nicht vertrauenswürdigen Dokuments im System. Der Benutzer wird beobachten, dass diese erste Datei länger dauert, um in Application Guard zu öffnen.

## <a name="known-issues-in-preview"></a>Bekannte Probleme in der Vorschau

* Durch Klicken auf Weblinks ( `http` oder `https` ) wird der Browser nicht geöffnet.
* .Net-Updates bewirken, dass Dateien in Application Guard nicht geöffnet werden. Als Problemumgehung können Benutzer Ihr Gerät beim Auftreten dieses Problems neu starten. Erfahren Sie mehr über das Problem beim [erhalten einer Fehlermeldung, wenn Sie versuchen, Windows Defender Application Guard oder Windows Sandbox zu öffnen](https://support.microsoft.com/help/4575917/receiving-an-error-message-when-attempting-to-open-windows-defender-ap).
