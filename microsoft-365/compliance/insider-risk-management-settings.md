---
title: Einstellungen für das Insider-Risikomanagement
description: Erfahren Sie mehr über die Einstellungen für das Insider-Risikomanagement in Microsoft 365
keywords: Microsoft 365, Insider-Risikomanagement, Risikomanagement, Compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: dd72ded935b9108e4b2699f5ddb6d320f5c32e69
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841256"
---
# <a name="get-started-with-insider-risk-management-settings"></a>Erste Schritte mit Einstellungen für das Insider-Risikomanagement

Einstellungen für das Insider-Risikomanagement gelten für alle Richtlinien für das Insider-Risikomanagement, unabhängig von der Vorlage, die Sie beim Erstellen einer Richtlinie ausgewählt haben. Die Einstellungen werden über das Steuerelement **Insider-Risiko-Einstellungen** konfiguriert, das sich oben auf allen Registerkarten des Insider-Risikomanagements befindet. Diese Einstellungen steuern Richtlinienkomponenten für die folgenden Bereiche:

- Datenschutz
- Indikatoren
- Richtlinienzeitachsen
- Intelligente Erkennungen
- Exportieren von Warnungen (Vorschau)
- Benutzergruppen mit Priorität (Vorschau)
- Priorität physischer Ressourcen (Vorschau)
- Power Automate-Flüsse (Vorschau)
- Microsoft Teams (Vorschau)

Bevor Sie beginnen und Richtlinien für das Insiderrisikomanagement erstellen, ist es wichtig, diese Einstellungen zu verstehen und die Einstellungsebenen für die Complianceanforderungen Ihrer Organisation am besten zu wählen.

## <a name="privacy"></a>Datenschutz

Der Schutz der Privatsphäre von Benutzern, die über Richtlinienübereinstimmungen verfügen, ist wichtig und kann zur Förderung der Objektivität bei der Überprüfung von Daten und Analysen im Hinblick auf Insider-Risikowarnungen beitragen. Für Benutzer mit einer Übereinstimmung mit einer Richtlinie für Insiderrisiken können Sie eine der folgenden Einstellungen auswählen:

- **Anonymisierte Versionen** von Benutzernamen anzeigen: Namen von Benutzern werden anonymisiert, um zu verhindern, dass Administratoren, Datenermittler und Prüfer sehen, wer Richtlinienwarnungen zugeordnet ist. Zum Beispiel würde ein Benutzer "Grace Taylor" mit einem randomisierten Pseudonym wie "AnonIS8-988" in allen Bereichen des Insider-Risikomanagements erscheinen. Wenn Sie diese Einstellung wählen, werden alle Benutzer mit aktuellen und früheren Richtlinienübereinstimmungen anonymisiert und gelten für alle Richtlinien. Benutzerprofilinformationen in der Warnung zu Insiderrisiken und Falldetails sind bei Auswahl dieser Option nicht verfügbar. Benutzernamen werden jedoch beim Hinzufügen neuer Benutzer zu vorhandenen Richtlinien oder beim Zuweisen von Benutzern zu neuen Richtlinien angezeigt. Wenn Sie diese Einstellung deaktivieren, werden Benutzernamen für alle Benutzer angezeigt, die über aktuelle oder frühere Richtlinien übereinstimmungen verfügen.
- **Anonymisierte Versionen von Benutzernamen** nicht anzeigen: Benutzernamen werden für alle aktuellen und früheren Richtlinien übereinstimmungen für Warnungen und Fälle angezeigt. Benutzerprofilinformationen (Name, Titel, Alias sowie Organisation oder Abteilung) werden für den Benutzer für alle Warnungen und Fälle des Insiderrisikomanagements angezeigt.

![Datenschutzeinstellungen für das Insider-Risikomanagement](../media/insider-risk-settings-privacy.png)

## <a name="indicators"></a>Indikatoren

Richtlinienvorlagen für Insiderrisiken definieren die Art der Risikoaktivitäten, die Sie erkennen und untersuchen möchten. Jede Richtlinienvorlage basiert auf bestimmten Indikatoren, die bestimmten Triggern und Risikoaktivitäten entsprechen. Alle Indikatoren sind standardmäßig deaktiviert, und Sie müssen einen oder mehrere Richtlinienindikatoren auswählen, bevor Sie eine Richtlinie für das Insiderrisikomanagement konfigurieren.

Warnungen werden durch Richtlinien ausgelöst, wenn Benutzer Aktivitäten im Zusammenhang mit Richtlinienindikatoren ausführen, die einen erforderlichen Schwellenwert erreichen. Das Risikomanagement für Insider verwendet zwei Arten von Indikatoren:

- **Auslösen von Ereignissen:** Ereignisse, die bestimmen, ob ein Benutzer für eine Richtlinie für das Insiderrisikomanagement aktiv ist. Wenn ein Benutzer einer Richtlinie für das Insiderrisikomanagement hinzugefügt wird, die kein auslösendes Ereignis hat, wird die Benutzeraktivität nicht von der Richtlinie ausgewertet. Beispielsweise wird Benutzer A einer Richtlinie hinzugefügt, die aus dem Datendiebstahl durch die Richtlinienvorlage "Verlassene Benutzer" erstellt wurde, und die Richtlinie und der Microsoft 365 -Personalconnector sind ordnungsgemäß konfiguriert.  Wenn Benutzer A nicht über ein vom Personalconnector gemeldetes Beendigungsdatum verfügt, werden Benutzer-A-Aktivitäten von dieser Richtlinie für das Insiderrisikomanagement nicht auf Risiken geprüft. Ein weiteres Beispiel für ein auslösendes  Ereignis ist, wenn ein Benutzer bei Verwendung von Richtlinien für Datenlecks eine Warnung mit hoher Schwere hat. 
- **Richtlinienindikatoren:** Indikatoren, die in Richtlinien für das Insiderrisikomanagement enthalten sind, die verwendet werden, um eine Risikobewertung für einen Benutzer im Umfang zu ermitteln. Diese Richtlinienindikatoren werden nur aktiviert, nachdem ein auslösendes Ereignis für einen Benutzer auftritt. Einige Beispiele für Richtlinienindikatoren sind, wenn ein Benutzer Daten in persönliche Cloudspeicherdienste oder tragbare Speichergeräte kopiert oder wenn ein Benutzer interne Dateien und Ordner mit nicht autorisierten externen Parteien teilt.

Richtlinienindikatoren sind in die folgenden Bereiche segmentiert. Sie können die Indikatoren zum Aktivieren und Anpassen der Grenzwerte für Indikatorereignis für jede Indikatorebene auswählen, wenn Sie eine Richtlinie für Insiderrisiken erstellen:

- **Office-Indikatoren:** Dazu gehören Richtlinienindikatoren für SharePoint-Websites, Teams und E-Mail-Nachrichten.
- **Geräteindikatoren:** Dazu gehören Richtlinienindikatoren für Aktivitäten wie das Freigeben von Dateien über das Netzwerk oder für Geräte. Zu den Indikatoren gehören Aktivitäten im Zusammenhang Microsoft Office Dateien, . CSV-Dateien und . PDF-Dateien. Wenn Sie **Geräteindikatoren auswählen,** werden Aktivitäten nur für Geräte mit Windows 10 Build 1809 oder höher verarbeitet. Weitere Informationen zum Konfigurieren von Geräten für die Integration mit Insiderrisiken finden Sie im Abschnitt "Aktivieren von Geräteindikatoren und [integrierten Geräten".](insider-risk-management-settings.md#OnboardDevices)
- **Sicherheitsrichtlinienverletzungsindikator:** Dazu gehören Indikatoren von Microsoft Defender for Endpoint im Zusammenhang mit nicht genehmigten oder schädlichen Softwareinstallationen oder der Umgehung von Sicherheitskontrollen. Um Warnungen im Insider-Risikomanagement zu erhalten, müssen Sie über eine active Defender for Endpoint-Lizenz und die Integration von Insiderrisiken verfügen. Weitere Informationen zum Konfigurieren von Defender for Endpoint für die Integration von Insider-Risikomanagement finden Sie unter ["Konfigurieren erweiterter Features in Microsoft Defender for Endpoint".](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)
- **Risikobewertungen:** Dazu gehört die Erhöhung der Risikobewertung für ungewöhnliche Aktivitäten oder frühere Richtlinienverstöße. Die Aktivierung von Risikobewertungen erhöht die Risikobewertungen und die Wahrscheinlichkeit von Warnungen für diese Arten von Aktivitäten. Risikobewertungen können nur ausgewählt werden, wenn ein oder mehrere Indikatoren ausgewählt sind.

![Einstellungen des Indikators für das Insider-Risikomanagement](../media/insider-risk-settings-indicators.png)

In einigen Fällen können Sie die Indikatoren für Insiderrisikorichtlinien einschränken, die auf Richtlinien für Insiderrisiken in Ihrer Organisation angewendet werden. Sie können die Richtlinienindikatoren für bestimmte Bereiche deaktivieren, indem Sie sie von allen Richtlinien für Insiderrisiken deaktivieren. Triggering events cannot be modified for insider risk policy templates.

Um die Indikatoren für Insiderrisikorichtlinien zu definieren, die in allen Richtlinien für Insiderrisiken aktiviert sind, navigieren Sie zu Indikatoren für Insider-Risikoeinstellungen, und wählen Sie einen oder  >   mehrere Richtlinienindikatoren aus. Die auf der Seite "Indikatoreneinstellungen" ausgewählten Indikatoren können beim Erstellen oder Bearbeiten einer Richtlinie für Insiderrisiken im Richtlinienassistenten nicht einzeln konfiguriert werden.

>[!NOTE]
>Es kann mehrere Stunden dauern, bis neue manuell hinzugefügte Benutzer im Benutzerdashboard **angezeigt werden.** Die Anzeige von Aktivitäten in den letzten 90 Tagen für diese Benutzer kann bis zu 24 Stunden dauern. Um Aktivitäten für manuell hinzugefügte Benutzer anzuzeigen, wählen  Sie den Benutzer im Dashboard "Benutzer" **aus,** und öffnen Sie die Registerkarte "Benutzeraktivität" im Detailbereich.

### <a name="enable-device-indicators-and-onboard-devices"></a>Aktivieren von Geräteindikatoren und integrierten Geräten
<a name="OnboardDevices"> </a>

Um die Überwachung von Risikoaktivitäten auf Geräten zu aktivieren und Richtlinienindikatoren für diese Aktivitäten zu verwenden, müssen Ihre Geräte die folgenden Anforderungen erfüllen, und Sie müssen die folgenden Onboardingschritte ausführen.

#### <a name="step-1-prepare-your-endpoints"></a>Schritt 1: Vorbereiten der Endpunkte

Stellen Sie sicher, dass die Windows 10-Geräte, die Sie für die Berichterstellung im Insider-Risikomanagement planen, diese Anforderungen erfüllen.

1. Muss Windows 10 x64 Build 1809 oder höher ausführen und muss das [Windows 10-Update (OS Build 17763.1075)](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818) vom 20. Februar 2020 installiert haben.
2. Alle Geräte müssen in [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), oder in Azure AD Hybrid eingebunden sein.
3. Installieren Sie den Microsoft Chromium -Edge-Browser auf dem Endpunktgerät, um Aktionen für die Clouduploadaktivität zu überwachen. Weitere Informationen finden Sie unter [Herunterladen des auf Chromium basierenden neuen Microsoft Edge](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).

#### <a name="step-2-onboarding-devices"></a>Schritt 2: Onboarding von Geräten
<a name="OnboardStep2"> </a>

Sie müssen die Geräteüberwachung aktivieren und Ihre Endpunkte integrieren, bevor Sie Insider-Risikomanagement-Aktivitäten auf einem Gerät überwachen können. Beide Aktionen werden im Microsoft 365 Compliance-Portal durchgeführt.

Wenn Sie Geräte integrieren möchten, die noch nicht onboarded wurden, laden Sie das entsprechende Skript herunter und stellen es bereit, wie in den folgenden Schritten beschrieben.

Wenn bereits Geräte in [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/) eingebunden sind, werden sie in der Liste der verwalteten Geräte angezeigt. Führen [Sie Schritt 3 aus:](insider-risk-management-settings.md#OnboardStep3) Wenn Geräte im nächsten Abschnitt in Microsoft Defender for Endpoint onboarded sind.

In diesem Bereitstellungsszenario integrieren Sie Geräte, die noch nicht onboarded wurden, und Sie möchten nur Insiderrisikoaktivitäten auf Windows 10-Geräten überwachen.

1. Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).
2. Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräte-Onboarding** aus.

   > [!NOTE]
   > In der Regel dauert es zwar nur ungefähr eine Minute, bis das Geräte-Onboarding aktiviert ist, warten Sie aber mindestens 30 Minuten, bevor Sie sich an den Microsoft-Support wenden.

3. Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen. Die Liste ist leer, solange keine Geräte eingebunden sind.
4. Wählen Sie **Onboarding** aus, um mit dem Onboarding-Prozess zu beginnen.
5. Wählen Sie in der Liste der Bereitstellungsmethode die Art und Weise aus, wie Sie auf diesen weiteren Geräten bereitstellen möchten, und laden Sie **dann das Paket herunter.** 
6. Führen Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren aus. Über diesen Link gelangen Sie zu einer Zielseite, auf der Sie auf Microsoft Defender für Endpunkt-Verfahren zugreifen können, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:
    - Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien
    - Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager
    - Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten
    - Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts
    - Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)

Sobald der Endpunkt onboardiert ist, sollte er in der Geräteliste angezeigt werden, und der Endpunkt beginnt, Überwachungsprotokolle an das Insider-Risikomanagement zu melden.

> [!NOTE]
> Diese Funktion erfordert eine Lizenz. Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.

#### <a name="step-3-if-you-have-devices-onboarded-into-microsoft-defender-for-endpoint"></a>Schritt 3: Wenn Geräte in Microsoft Defender for Endpoint onboarded sind
<a name="OnboardStep3"> </a>

Wenn Microsoft Defender for Endpoint bereits bereitgestellt ist und Endpunkte vorhanden sind, werden alle diese Endpunkte in der Liste der verwalteten Geräte angezeigt. Sie können neue Geräte weiterhin in das Insider-Risikomanagement integrieren, um die Abdeckung mithilfe des Abschnitts Schritt [2: Onboarding von Geräten zu](insider-risk-management-settings.md#OnboardStep2) erweitern.

1. Öffnen Sie das [Microsoft Compliance Center](https://compliance.microsoft.com).
2. Öffnen Sie die Seite "Einstellungen", und wählen Sie **Geräteüberwachung aktivieren** aus.
3. Wählen Sie **Geräteverwaltung** aus, um die Liste der **Geräte** zu öffnen. Es sollte die Liste der Geräte angezeigt werden, die bereits Berichte für Microsoft Defender für Endpunkt erstellen.
4. Wählen **Sie "Onboarding"** aus, wenn Sie weitere Geräte integrieren müssen.
5. Wählen Sie in der Liste der Bereitstellungsmethode die Art und Weise aus, wie Sie auf diesen weiteren Geräten bereitstellen möchten, und laden Sie dann **das Paket herunter.** 
6. Führen Sie die unter [Onboarding-Tools und -Methoden für Windows 10-Computer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) beschriebenen entsprechenden Verfahren aus. Über diesen Link gelangen Sie zu einer Zielseite, auf der Sie auf Microsoft Defender für Endpunkt-Verfahren zugreifen können, die dem in Schritt 5 ausgewählten Bereitstellungspaket entsprechen:
    - Onboarding von Windows 10-Computern mithilfe von Gruppenrichtlinien
    - Onboarding von Windows-Computern mithilfe von Microsoft Endpoint Configuration Manager
    - Onboarding von Windows 10-Computern mit Tools für die Verwaltung von Mobilgeräten
    - Onboarding von Windows 10-Computern mithilfe eines lokalen Skripts
    - Onboarding von nicht-persistenten Computern einer VD-Infrastruktur (Virtual Desktop)

Sobald der Endpunkt onboardiert ist, sollte  er unter der Tabelle "Geräte" angezeigt werden, und der Endpunkt beginnt mit der Berichterstellung von Überwachungsprotokollen an das Insider-Risikomanagement.

> [!NOTE]
>Diese Funktion erfordert eine Lizenz. Ohne die erforderliche Lizenz werden keine Daten angezeigt und es ist kein Zugriff auf sie möglich.

### <a name="indicator-level-settings-preview"></a>Einstellungen auf Indikatorebene (Vorschau)

Beim Erstellen einer Richtlinie im Richtlinienassistenten können Sie konfigurieren, wie sich die tägliche Anzahl von Risikoereignissen auf die Risikobewertung für Insider-Risikowarnungen beeinflussen soll. Mit diesen Indikatoreinstellungen können Sie steuern, wie sich die Anzahl der Vorkommen von Risikoereignissen in Ihrer Organisation auf die Risikobewertung und folglich auf den zugehörigen Warnungsschweregrad für diese Ereignisse auswirken sollte. Wenn es Ihnen lieber ist, können Sie auch festlegen, dass die von Microsoft empfohlenen Standardereignisschwellenwerte für alle aktivierten Indikatoren erhalten bleiben.

Sie entscheiden sich beispielsweise für die Aktivierung von SharePoint-Indikatoren in den Richtlinieneinstellungen für Insiderrisiken und  das Festlegen benutzerdefinierter Schwellenwerte für SharePoint-Ereignisse, wenn Sie Indikatoren für eine neue Richtlinie für Insiderrisiken konfigurieren. Während Sie im Assistenten für Insider-Risikorichtlinien drei verschiedene tägliche Ereignisebenen für jeden SharePoint-Indikator konfigurieren, um die Risikobewertung für Warnungen im Zusammenhang mit diesen Ereignissen zu beeinflussen.

![Benutzerdefinierte Indikatoreinstellungen für das Insider-Risikomanagement](../media/insider-risk-custom-indicators.png)

Für die erste tägliche Ereignisebene legen Sie den Schwellenwert auf *10* oder mehr Ereignisse pro Tag fest, um eine niedrigere Auswirkung auf die Risikobewertung für die Ereignisse zu erzielen, *20* oder mehr Ereignisse pro Tag für eine mittlere Auswirkung auf die Risikobewertung für die Ereignisse und *30* oder mehr Ereignisse pro Tag eine höhere Auswirkung auf die Risikobewertung für die Ereignisse. Diese Einstellungen bedeuten effektiv:

- Wenn es 1-9 SharePoint-Ereignisse gibt, die nach dem Auslösen des Ereignisses stattfinden, sind risikobewertungen minimal betroffen und würden in der Regel keine Warnung generieren.
- Wenn es 10 bis 19 SharePoint-Ereignisse gibt, die nach einem auslösenden Ereignis stattfinden, ist die Risikobewertung grundsätzlich niedriger, und die Warnungsschweregrade würden in der Regel auf einem niedrigen Niveau liegen.
- Wenn es 20 bis 29 SharePoint-Ereignisse gibt, die nach einem Auslösen stattfinden, ist die Risikobewertung grundsätzlich höher, und der Schweregrad von Warnungen würde sich in der Regel auf einem mittleren Niveau befinden.
- Wenn es 30 oder mehr SharePoint-Ereignisse gibt, die nach einem Auslösen stattfinden, ist die Risikobewertung grundsätzlich höher, und der Schweregrad von Warnungen würde sich in der Regel auf einem hohen Niveau befinden.

## <a name="policy-timeframes"></a>Zeitrahmen für Richtlinien

Mit Hilfe von Zeitrahmen für Richtlinien können Sie vergangene und zukünftige Überprüfungszeiträume definieren, die nach Richtlinienübereinstimmungen auf der Grundlage von Ereignissen und Aktivitäten für die Richtlinienvorlagen zum Insider-Risikomanagement ausgelöst werden. Je nach der von Ihnen verwendeten Richtlinienvorlage stehen die folgenden Zeitrahmen für Richtlinien zur Verfügung:

- **Aktivierungsfenster:** Für alle Richtlinienvorlagen verfügbar, ist das **Aktivierungsfenster** die definierte Anzahl von Tagen, die das Fenster nach einem auslösenden Ereignis aktiviert.  Das Fenster wird für 1 bis 30 Tage aktiviert, nachdem ein auslösendes Ereignis für alle Benutzer auftritt, die der Richtlinie zugewiesen sind. Sie haben beispielsweise eine Richtlinie für das Insiderrisikomanagement  konfiguriert und das Aktivierungsfenster auf 30 Tage festgelegt. Seit der Konfiguration der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis  aktiviert das Aktivierungsfenster, und die Richtlinie ist 30 Tage nach dem Auslösen des Ereignisses für diesen Benutzer aktiv.
- **Erkennung früherer** Aktivitäten: Für alle  Richtlinienvorlagen verfügbar, ist die Erkennung der  letzten Aktivität die definierte Anzahl von Tagen, die das Fenster vor einem auslösenden Ereignis aktiviert. Das Fenster wird für 0 bis 180 Tage aktiviert, bevor für alle Benutzer, die der Richtlinie zugewiesen sind, ein auslösendes Ereignis auftritt. Sie haben beispielsweise eine Richtlinie für das Insiderrisikomanagement  konfiguriert und die Erkennung früherer Aktivitäten auf 90 Tage festgelegt. Seit der Konfiguration der Richtlinie sind mehrere Monate vergangen, und für einen der in der Richtlinie enthaltenen Benutzer tritt ein auslösendes Ereignis ein. Das auslösende Ereignis  aktiviert die Erkennung früherer Aktivitäten, und die Richtlinie sammelt historische Aktivitäten für diesen Benutzer 90 Tage vor dem auslösenden Ereignis.

![Zeitrahmeneinstellungen für das Insider-Risikomanagement](../media/insider-risk-settings-timeframes.png)

## <a name="intelligent-detections"></a>Intelligente Erkennungen

Intelligente Erkennungseinstellungen helfen zu verfeinern, wie die Erkennung riskanter Aktivitäten für Warnungen verarbeitet wird. Unter bestimmten Umständen müssen Sie möglicherweise zu ignorierende Dateitypen definieren, oder Sie möchten eine Erkennungsstufe für Dateien erzwingen, um einen Mindestbalken für Warnungen zu definieren. Wenn Sie anstößige Sprachrichtlinien verwenden, müssen Sie möglicherweise die Erkennungsempfindlichkeit erhöhen oder verringern, um die Anzahl der gemeldeten Richtlinienübereinstimmungen zu kontrollieren. Verwenden Sie diese Einstellungen, um das gesamte Warnungsvolumen, Dateitypausschlüsse, Dateivolumegrenzwerte und die Erkennungsempfindlichkeit für anstößige Sprache zu steuern.

![Einstellungen für intelligente Erkennungen des Insider-Risikomanagements](../media/insider-risk-settings-detections.png)

### <a name="anomaly-detections"></a>Anomalie-Erkennungen

Zu den Anomalie-Erkennungen gehören Einstellungen für Dateityp-Ausschlüsse und Dateivolumen-Begrenzungen.

- **Dateitypausschlüsse:** Um bestimmte Dateitypen von allen Übereinstimmungen mit Insider-Risikomanagement-Richtlinien auszuschließen, geben Sie Dateityperweiterungen durch Kommas getrennt ein. Um beispielsweise bestimmte Arten von Musikdateien von den Richtlinienübereinstimmungen auszuschließen, können Sie *AAC, MP3, WAV, WMA* in das Feld **Dateityp-Ausschlüsse** eingeben. Dateien mit diesen Erweiterungen würden von allen Richtlinien zum Insider-Risikomanagement ignoriert werden.
- **Grenzwert für dateivolume:** Geben Sie die Anzahl der Dateien ein, um eine mindeste Dateiebene zu definieren, bevor Aktivitätswarnungen in den Richtlinien für Insiderrisiken gemeldet werden. Sie würden beispielsweise "10" eingeben, wenn Sie keine Warnungen zu Insiderrisiken generieren möchten, wenn ein Benutzer 10 Dateien oder weniger herunterläutet, selbst wenn die Richtlinien diese Aktivität als Anomalie betrachten.

### <a name="offensive-language-detections"></a>Erkennung anstößiger Sprache

>[!IMPORTANT]
>Ab dem 16. Oktober 2020 können Sie mithilfe dieser Vorlage keine Richtlinien mehr erstellen. Alle aktiven Richtlinien, die diese Vorlage verwenden, funktionieren, bis sie im Januar 2021 endgültig entfernt werden. Die integrierte Klassifizierung für anstößige Sprache, die diese Vorlage unterstützt, wird nicht mehr unterstützt, da sie eine hohe Anzahl falsch positiver Ergebnisse erzeugt hat. Um Risikoprobleme für anstößige Sprache zu beheben, empfehlen wir die Verwendung von Microsoft 365-Richtlinien zur [Kommunikationskonformität.](communication-compliance.md) Weitere Informationen zu integrierten Klassifizierungen finden Sie unter ["Erste Schritte mit trainierbaren Klassifizierungen".](classifier-get-started-with.md)

Um die Empfindlichkeit des Klassifizierers für anstößige Sprache für Richtlinien anzupassen, welche die Vorlage *Anstößige Sprache in E-Mail* verwenden, wählen Sie eine der folgenden Einstellungen aus:

- **Niedrig:** Die niedrigste Vertraulichkeitsstufe mit dem breitesten Bereich für die Erkennung von anstößigen Sprache und Gesinnung. Die Wahrscheinlichkeit falsch positiver Ergebnisse bei anstößigen Sprachübereinstimmungen ist erhöht.
- **Mittel**: Die mittlere Vertraulichkeitsstufe mit einem ausgeglichenen Bereich für die Erkennung von anstößigen Sprache und Gesinnung. Die Wahrscheinlichkeit falsch positiver Ergebnisse bei anstößigen Sprachübereinstimmungen ist durchschnittlich.
- **Hoch:** Die höchste Vertraulichkeitsstufe mit einem schmalen Bereich für die Erkennung von anstößigen Sprache und Gesinnung. Die Wahrscheinlichkeit falsch positiver Ergebnisse bei anstößigen Sprachübereinstimmungen ist niedrig.

### <a name="alert-volume"></a>Warnungsvolumen

Benutzeraktivitäten, die von Richtlinien für Insiderrisiken erkannt werden, erhalten eine bestimmte Risikobewertung, die wiederum den Warnungsschweregrad bestimmt (niedrig, mittel, hoch). Standardmäßig generieren wir eine bestimmte Menge von Warnungen mit niedrigem, mittlerem und hohem Schweregrad, aber Sie können das Volume entsprechend Ihren Anforderungen vergrößern oder verringern. Wählen Sie eine der folgenden Einstellungen aus, um das Volumen der Warnungen für alle Richtlinien für das Insiderrisikomanagement anzupassen:

- **Weniger Warnungen:** Es werden alle Warnungen mit hohem Schweregrad, weniger Warnungen mit mittlerem Schweregrad und keine Warnungen mit niedrigem Schweregrad angezeigt. Diese Einstellungsstufe bedeutet, dass Sie möglicherweise einige echte positive Ergebnisse verpassen.
- **Standardvolume:** Es werden alle Warnungen mit hohem Schweregrad und eine ausgewogene Menge von Warnungen mit mittlerem und niedrigem Schweregrad angezeigt.
- **Weitere Warnungen:** Alle Warnungen mit mittlerem und hohem Schweregrad und Warnungen mit dem größten Schweregrad werden angezeigt. Diese Einstellungsstufe kann zu mehr falsch positiven Ergebnisse führen.

### <a name="microsoft-defender-for-endpoint-preview"></a>Microsoft Defender for Endpoint (Vorschau)

[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ist eine Sicherheitsplattform für Unternehmensendpunkte, die Unternehmensnetzwerken dabei helfen soll, erweiterte Bedrohungen zu verhindern, zu erkennen, zu untersuchen und darauf zu reagieren. Um eine bessere Sichtbarkeit von Sicherheitsverstößen in Ihrer Organisation zu erhalten, können Sie Defender for Endpoint-Warnungen für Aktivitäten importieren und filtern, die in Richtlinien verwendet werden, die aus Richtlinienvorlagen für Sicherheitsverletzungen des Insiderrisikomanagements erstellt wurden.

Abhängig von den Arten von Signalen, die Sie interessieren, können Sie auswählen, ob Sie Warnungen basierend auf dem Triagestatus der Defender for Endpoint-Warnung in das Insider-Risikomanagement importieren möchten. Sie können einen oder mehrere der folgenden Warnungstriagestatus in den globalen Einstellungen definieren, die importiert werden müssen:

- Unbekannt
- Neu
- In Arbeit
- Gelöst

Warnungen von Defender für Endpunkt werden täglich importiert. Je nach dem von Ihnen verwendeten Triagestatus werden möglicherweise mehrere Benutzeraktivitäten für dieselbe Warnung angezeigt, während sich der Triagestatus in Defender for Endpoint ändert.

Wenn Sie beispielsweise "Neu" *,* *"In* Bearbeitung" und *"Gelöst"* für diese Einstellung auswählen, wenn eine Microsoft Defender für Endpunktwarnung generiert wird und der Status *"Neu"* ist, wird eine anfängliche Warnungsaktivität für den Benutzer importiert, der sich im Insiderrisiko befindet. Wenn sich der Triagestatus von Defender für Endpunkt *in "In* Bearbeitung" ändert, wird eine zweite Aktivität für diese Warnung für den Benutzer importiert, der sich im Insiderrisiko befindet. Wenn der endgültige Defender for Endpoint-Triagestatus *"Gelöst"* festgelegt ist, wird eine dritte Aktivität für diese Warnung für den Benutzer importiert, der sich im Insiderrisiko befindet. Diese Funktion ermöglicht es Ermittlern, den Fortschritt der Defender for Endpoint-Warnungen zu verfolgen und den Grad der Sichtbarkeit zu wählen, den ihre Untersuchung erfordert.

>[!IMPORTANT]
>Sie müssen Microsoft Defender für Endpunkt in Ihrer Organisation konfiguriert haben und Defender for Endpoint für die Integration des Insider-Risikomanagements im Defender Security Center aktivieren, um Warnungen zu Sicherheitsverletzungen zu importieren. Weitere Informationen zum Konfigurieren von Defender for Endpoint für die Integration von Insider-Risikomanagement finden Sie unter ["Konfigurieren erweiterter Features in Defender for Endpoint".](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-features\#share-endpoint-alerts-with-microsoft-compliance-center)

### <a name="domains-preview"></a>Domänen (Vorschau)

Mithilfe von Domäneneinstellungen können Sie Risikostufen für die Kommunikation mit bestimmten Domänen definieren. Diese Kommunikation umfasst das Freigeben von Dateien, E-Mail-Nachrichten oder das Herunterladen von Inhalten. Durch Angeben von Domänen in diesen Einstellungen können Sie die Risikobewertung für Aktivitäten erhöhen oder verringern, die mit diesen Domänen stattfinden. Wenn Sie z. B. contoso.com und sales.wingtiptoys.com als zulässige Domänen angeben möchten, geben Sie "contoso.com sales.wingtiptoys.com" in das Feld **"Zulässige Domänen"** ein.

Für jede der folgenden Domäneneinstellungen können Sie bis zu 500 Domänen eingeben:

- **Nicht zulässige Domänen:** Durch die Angabe nicht zulässiger Domänen haben Aktivitäten, die mit diesen Domänen stattfinden, *höhere* Risikobewertungen.
- **Zulässige Domänen:** Durch die Angabe zulässiger Domänen in den Einstellungen  haben Aktivitäten, die mit diesen Domänen stattfinden, niedrigere Risikobewertungen und werden ähnlich behandelt wie interne Organisationsaktivitäten. Beispielsweise werden E-Mail-Aktivitäten an diese Domänen ähnlich analysiert wie interne E-Mail-Aktivitäten.
- **Domänen von Drittanbietern:** Domänen von Drittanbietern sind Domänen, die für geschäftliche Zwecke in Ihrer Organisation verwendet werden, und vertrauliche Inhalte können an diesen Speicherorten gespeichert werden. Wenn Sie eine Drittanbieterdomäne angeben, können Sie Benachrichtigungen über riskante Aktivitäten in diesen Domänen erhalten.

## <a name="export-alerts-preview"></a>Exportieren von Warnungen (Vorschau)

Warnungsinformationen zum Insiderrisikomanagement können über das [Office 365-Verwaltungsaktivitäts-API-Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#security-and-compliance-alerts-schema)in Sicherheitsinformations- und Ereignisverwaltungsdienste (SIEM) exportiert werden. Sie können die Office 365-Verwaltungsaktivitäts-APIs verwenden, um Warnungsinformationen in andere Anwendungen zu exportieren, die Ihre Organisation möglicherweise zum Verwalten oder Aggregieren von Insiderrisikoinformationen verwendet.

So verwenden Sie die APIs zum Überprüfen von Informationen zu Insider-Risikowarnungen:

1. Aktivieren Sie die Unterstützung der Office 365-Verwaltungsaktivitäts-API im **Export von Insider-Risikomanagementeinstellungen.**  >    >   Diese Einstellung ist standardmäßig für Ihre Microsoft 365-Organisation deaktiviert.
2. Filtern Sie die allgemeinen Office 365-Überwachungsaktivitäten nach *SecurityComplianceAlerts*.
3. Filtern *Sie "SecurityComplianceAlerts"* nach der Kategorie *"InsiderRiskManagement".*

![Exportbenachrichtigungseinstellungen für das Insider-Risikomanagement](../media/insider-risk-settings-export.png)

Warnungsinformationen enthalten Informationen aus dem Sicherheits- und Kompatibilitätswarnungsschema und dem allgemeinen Schema der Office 365-Verwaltungsaktivitäts-API.

Die folgenden Felder und Werte werden für Insider-Risikomanagement-Warnungen für das Security & Compliance-Warnungsschema exportiert:

| **Warnungsparameter** | **Beschreibung** |
|:------------------|:----------------|
| AlertType | Der Typ der Warnung ist *"Benutzerdefiniert".*  |
| AlertId | Die GUID der Warnung. Warnungen im Risikomanagement von Insidern können geschaltet werden. Wenn sich der Warnungsstatus ändert, wird ein neues Protokoll mit derselben AlertID generiert. Diese AlertID kann verwendet werden, um Updates für eine Warnung zu korrelieren. |
| Kategorie | Die Kategorie der Warnung ist *InsiderRiskManagement*. Diese Kategorie kann verwendet werden, um zwischen diesen Warnungen und anderen Warnungen zur & A0 zu unterscheiden. |
| Kommentare | Standardkommentare für die Warnung. Werte sind *"Neue Warnung"* (protokolliert, wenn eine Warnung erstellt wird) und *"Warnung aktualisiert"* (protokolliert, wenn eine Warnung aktualisiert wird). Verwenden Sie die AlertID, um Updates für eine Warnung zu korrelieren. |
| Daten | Die Daten für die Warnung enthalten die eindeutige Benutzer-ID, den Benutzerprinzipalnamen sowie Datum und Uhrzeit (UTC), als der Benutzer in einer Richtlinie ausgelöst wurde. |
| Name | Richtlinienname für die Insider-Risikomanagement-Richtlinie, die die Warnung generiert hat. |
| PolicyId | Die GUID der Insider-Risikomanagement-Richtlinie, die die Warnung ausgelöst hat. |
| Severity | Der Schweregrad der Warnung. Die Werte sind *Hoch,* *Mittel* oder *Niedrig.* |
| Source | Die Quelle der Warnung. Der Wert ist *Office 365 Security & Compliance*. |
| Status | Der Status der Warnung. Die Werte sind *aktiv* *(Überprüfung* im Insider-Risiko), *Investigating* *(Bestätigt* im Insider-Risiko), *Gelöst* *(gelöst* im Insider-Risiko), *Abgelehnt* *(in* Insider-Risiko verworfen). |
| Version | Die Version des Sicherheits- und Kompatibilitätsbenachrichtigungsschemas. |

Die folgenden Felder und Werte werden für Insider-Risikomanagement-Warnungen für das allgemeine Schema der [Office 365-Verwaltungsaktivitäts-API exportiert.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)

- UserId
- Id
- RecordType
- CreationTime
- Vorgang
- OrganizationId
- UserType
- UserKey

## <a name="priority-user-groups-preview"></a>Benutzergruppen mit Priorität (Vorschau)

Benutzer in Ihrer Organisation können je nach Position, Zugriffsebene auf vertrauliche Informationen oder Risikoverlauf unterschiedliche Risikostufen haben. Die Priorisierung der Untersuchung und Bewertung der Aktivitäten dieser Benutzer kann Sie vor potenziellen Risiken warnen, die höhere Folgen für Ihre Organisation haben können. Benutzergruppen mit Priorität im Insider-Risikomanagement helfen bei der Definition der Benutzer in Ihrer Organisation, die eine genauere Überprüfung und eine sensiblere Risikobewertung benötigen. In Gekoppelt mit den Sicherheitsrichtlinienverstößen durch Prioritätsbenutzer und Datenlecks durch Richtlinienvorlagen für Benutzer mit Priorität haben Benutzer, die einer Benutzergruppe mit Priorität hinzugefügt wurden, eine höhere Wahrscheinlichkeit von Insider-Risikowarnungen und -Warnungen mit höheren Schweregraden.  

![Einstellungen für Benutzergruppen mit Priorität für das Insider-Risikomanagement](../media/insider-risk-settings-priority-users.png)

Sie müssen z. B. vor Datenlecks für ein streng vertrauliches Projekt schützen, bei dem Benutzer Zugriff auf vertrauliche Informationen haben. Sie können eine Benutzergruppe mit Priorität "Vertrauliche *Projektbenutzer"*  für Benutzer in Ihrer Organisation erstellen, die an diesem Projekt arbeiten. Mithilfe des Richtlinienassistenten und der Richtlinienvorlage für *Datenlecks* nach Priorität erstellen Sie eine neue Richtlinie und weisen der Richtlinie die Benutzergruppe "Vertrauliche *Projektbenutzer"* zu. Aktivitäten, die von der  Richtlinie für Mitglieder der Benutzergruppe "Vertrauliche Projektbenutzer" mit Priorität untersucht werden, sind sensibler für Risiken, und Aktivitäten dieser Benutzer generieren mit höherer Wahrscheinlichkeit eine Warnung und verfügen über Warnungen mit höheren Schweregraden.

### <a name="create-a-priority-user-group"></a>Erstellen einer Benutzergruppe mit Priorität

Zum Erstellen einer neuen Benutzergruppe mit Priorität verwenden Sie Einstellungssteuerelemente in der **Lösung** für das Insider-Risikomanagement im Microsoft 365 Compliance Center. Zum Erstellen einer Benutzergruppe mit Priorität müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder "Administrator für *Insider-Risikomanagement"* sein.

Führen Sie die folgenden Schritte aus, um eine Benutzergruppe mit Priorität zu erstellen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für **Das Insider-Risiko aus.** 
2. Auswählen der **Registerkarte "Priorität von Benutzergruppen"**
3. Wählen Sie **auf der Registerkarte "Priorität Benutzergruppen"** die Option "Benutzergruppe mit Priorität **erstellen"** aus, um den Assistenten zum Erstellen von Gruppen zu starten.
4. Füllen Sie **auf der Seite "Gruppe definieren"** die folgenden Felder aus:
    - **Name (erforderlich):** Geben Sie einen Anzeigenamen für die Benutzergruppe mit Priorität ein. Sie können den Namen der Benutzergruppe mit Priorität nach Abschluss des Assistenten nicht mehr ändern.
    - **Beschreibung (optional):** Geben Sie eine Beschreibung für die Benutzergruppe mit Priorität ein.
5. Wählen Sie **"Weiter"** aus, um fortzufahren.
6. Wählen Sie auf der  Seite "Mitglieder auswählen" die Option "Zu durchsuchende Mitglieder  auswählen" aus, und wählen Sie aus, welche E-Mail-aktivierten Benutzerkonten in der Gruppe enthalten sind, oder aktivieren Sie das Kontrollkästchen "Alle auswählen", um alle Benutzer in Ihrer Organisation der Gruppe hinzuzufügen.  Wählen **Sie "Hinzufügen"** aus, um **fortzufahren, oder "Abbrechen",** um zu schließen, ohne der Gruppe Benutzer hinzuzufügen.
7. Wählen Sie **"Weiter"** aus, um fortzufahren.
8. Überprüfen Sie **auf** der Seite "Überprüfen" die Einstellungen, die Sie für die Benutzergruppe mit Priorität ausgewählt haben. Wählen **Sie "Bearbeiten"** aus, um einen der Gruppenwerte zu ändern, oder wählen Sie **"Senden"** aus, um die Benutzergruppe mit Priorität zu erstellen und zu aktivieren.
9. Wählen Sie auf der Bestätigungsseite **"Fertig"** aus, um den Assistenten zu beenden.

### <a name="update-a-priority-user-group"></a>Aktualisieren einer Benutzergruppe mit Priorität

Um eine vorhandene Benutzergruppe mit Priorität zu aktualisieren, verwenden Sie Einstellungssteuerelemente in der **Lösung** für das Insider-Risikomanagement im Microsoft 365 Compliance Center. Zum Aktualisieren einer Benutzergruppe mit Priorität müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder *"Administrator für Insider-Risikomanagement"* sein.

Führen Sie die folgenden Schritte aus, um eine Benutzergruppe mit Priorität zu bearbeiten:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für **Das Insider-Risiko aus.** 
2. Auswählen der **Registerkarte "Priorität von Benutzergruppen"**
3. Wählen Sie die Benutzergruppe mit Priorität aus, die Sie bearbeiten möchten, und wählen Sie **"Gruppe bearbeiten" aus.**
4. Aktualisieren Sie **auf der Seite "Gruppe definieren"** das Feld "Beschreibung", falls erforderlich. Der Name der Benutzergruppe mit Priorität kann nicht aktualisiert werden. Wählen Sie **"Weiter"** aus, um fortzufahren.
5. Fügen Sie **auf der** Seite "Mitglieder auswählen" der Gruppe neue Mitglieder hinzu, indem Sie das **Steuerelement "Mitglieder auswählen"** verwenden. Um einen Benutzer aus der Gruppe zu entfernen, wählen Sie das "X" neben dem Benutzer aus, den Sie entfernen möchten. Wählen Sie **"Weiter"** aus, um fortzufahren.
6. Überprüfen Sie **auf der** Seite "Überprüfen" die Updateeinstellungen, die Sie für die Benutzergruppe mit Priorität ausgewählt haben. Wählen **Sie "Bearbeiten"** aus, um einen der Gruppenwerte zu ändern, oder wählen Sie **"Senden"** aus, um die Prioritätsbenutzergruppe zu aktualisieren.
7. Wählen Sie auf der Bestätigungsseite **"Fertig"** aus, um den Assistenten zu beenden.

### <a name="delete-a-priority-user-group"></a>Löschen einer Benutzergruppe mit Priorität

Um eine vorhandene Benutzergruppe mit Priorität zu löschen, verwenden Sie Einstellungssteuerelemente in der **Lösung** für das Insider-Risikomanagement im Microsoft 365 Compliance Center. Zum Löschen einer Benutzergruppe mit Priorität müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder *"Administrator für Insider-Risikomanagement"* sein.

>[!IMPORTANT]
>Durch das Löschen einer Benutzergruppe mit Priorität wird sie aus jeder aktiven Richtlinie entfernt, der sie zugewiesen ist. Wenn Sie eine Benutzergruppe mit Priorität löschen, die einer aktiven Richtlinie zugewiesen ist, enthält die Richtlinie keine Benutzer im Gültigkeitsbereich und befindet sich im Leerlauf und erstellt keine Warnungen.

Führen Sie die folgenden Schritte aus, um eine Benutzergruppe mit Priorität zu löschen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für **Das Insider-Risiko aus.** 
2. Auswählen der **Registerkarte "Priorität von Benutzergruppen"**
3. Wählen Sie die Benutzergruppe mit Priorität aus, die Sie bearbeiten möchten, und wählen **Sie im** Dashboardmenü "Löschen" aus.
4. Wählen Sie **im Dialogfeld "Löschen"** **"Ja"** aus, um die Benutzergruppe mit Priorität zu löschen, oder wählen Sie **"Abbrechen"** aus, um zum Dashboard zurückzukehren.

## <a name="priority-physical-assets-preview"></a>Priorität physischer Ressourcen (Vorschau)

Das Identifizieren des Zugriffs auf wichtige physische Ressourcen und das Korrelieren von Zugriffsaktivitäten auf Benutzerereignisse ist eine wichtige Komponente Ihrer Complianceinfrastruktur. Diese physischen Ressourcen stellen Prioritätsstandorte in Ihrer Organisation dar, z. B. Firmengebäude, Rechenzentren oder Serverräume. Aktivitäten mit Insiderrisiken können Benutzern zugeordnet werden, die ungewöhnliche Stunden arbeiten, versuchen, auf diese nicht autorisierten vertraulichen oder sicheren Bereiche zu zugreifen, und Anforderungen für den Zugriff auf bereiche auf hoher Ebene ohne legitime Anforderungen.

Mit aktivierten physischen Ressourcen mit Priorität und konfigurierten Datenkonnektoren für physische [Badging](import-physical-badging-data.md) integriert das Insider-Risikomanagement Signale aus Ihren physischen Kontroll- und Zugriffssystemen in andere Benutzerrisikoaktivitäten. Durch das Untersuchen von Verhaltensmustern in physischen Zugangssystemen und das Korrelieren dieser Aktivitäten mit anderen Insiderrisikoereignissen kann das Insiderrisikomanagement Complianceermittlern und Analysten helfen, fundiertere Reaktionsentscheidungen für Warnungen zu treffen. Der Zugriff auf die physischen Ressourcen mit Priorität wird in Erkenntnissen ermittelt, die sich von dem Zugriff auf Ressourcen ohne Priorität unterscheiden.

Beispielsweise verfügt Ihre Organisation über ein System für Schlechtes für Benutzer, das den physischen Zugriff auf normale Arbeits- und vertrauliche Projektbereiche überwacht und genehmigt. Sie haben mehrere Benutzer, die an einem vertraulichen Projekt arbeiten, und diese Benutzer kehren nach Abschluss des Projekts in andere Bereiche Ihrer Organisation zurück. Da sich das vertrauliche Projekt dem Abschluss nähert, möchten Sie sicherstellen, dass die Projektarbeit vertraulich bleibt und dass der Zugriff auf die Projektbereiche streng kontrolliert wird.

Sie können den Connector für physische Badgingdaten in Microsoft 365 aktivieren, um Zugriffsinformationen aus Ihrem physischen Badgingsystem zu importieren und physische Ressourcen mit Priorität im Insider-Risikomanagement anzugeben. Durch das Importieren von Informationen aus Ihrem System für Denfall und das Korrelieren von Physischen Zugriffsinformationen mit anderen Risikoaktivitäten, die im Insider-Risikomanagement identifiziert werden, stellen Sie fest, dass einer der Benutzer des Projekts nach normalen Arbeitszeiten auf die Projektbüros zutritt und auch große Datenmengen aus dem normalen Arbeitsbereich in einen persönlichen Cloudspeicherdienst exportiert. Diese aktivität des physischen Zugriffs, die der Onlineaktivität zugeordnet ist, kann auf möglichen Datendiebstahl hinweisen, und Complianceermittler und Analysten können entsprechend den Umständen für diesen Benutzer geeignete Maßnahmen ergreifen.

### <a name="configure-priority-physical-assets"></a>Konfigurieren von physischen Ressourcen mit Priorität

Um physische Ressourcen mit Priorität zu konfigurieren, konfigurieren Sie den Connector für physische Badging und verwenden Einstellungssteuerelemente in der **Lösung** für das Insider-Risikomanagement im Microsoft 365 Compliance Center. Zum Konfigurieren von physischen Ressourcen mit Priorität müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder *"Administrator für Insider-Risikomanagement" sein.*

Führen Sie die folgenden Schritte aus, um physische Ressourcen mit Priorität zu konfigurieren:

1. Befolgen Sie die Konfigurationsschritte für das Insider-Risikomanagement im Artikel ["Erste Schritte mit dem Insider-Risikomanagement".](insider-risk-management-configure.md) Stellen Sie in Schritt 3 sicher, dass Sie den Connector für physische Badging konfigurieren.

    >[!IMPORTANT]
    >Damit Richtlinien für das Insiderrisikomanagement Signaldaten im Zusammenhang mit abwesenden und beendeten Benutzern mit Ereignisdaten von Ihren physischen Kontroll- und Zugriffsplattformen verwenden und korrelieren können, müssen Sie auch den Microsoft 365 -HR-Connector konfigurieren. Wenn Sie den Connector für physische Badging aktivieren, ohne den Microsoft 365 -PERSONAL-Connector zu aktivieren, verarbeiten Richtlinien des Insiderrisikomanagements nur Ereignisse für physische Zugriffsaktivitäten für Benutzer in Ihrer Organisation.

2. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für Das **Insiderrisiko**   >  **aus.**
3. Auf der **Seite "Physische** Ressourcenpriorität" können Sie entweder manuell die IDs der physischen Objekte hinzufügen, die Sie auf die Objektereignisse überwachen möchten, die vom Connector für physische Badging importiert wurden, oder einen importieren. CSV-Datei aller IDs physischer Objekte, die vom Connector für physische Badging importiert wurden: a) Wenn Sie IDs physischer Objekte manuell hinzufügen möchten, wählen Sie "Physische Ressourcen mit Priorität hinzufügen" **aus,** geben Sie eine physische Asset-ID ein, und wählen Sie dann "Hinzufügen" **aus.** Geben Sie andere physische Ressourcen-IDs ein, und wählen Sie dann **"Physische** Ressourcen mit Priorität hinzufügen" aus, um alle eingegebenen Ressourcen zu speichern.
    b) So fügen Sie eine Liste der IDs physischer Ressourcen aus einem hinzu CSV-Datei, wählen **Sie "Physische Ressourcen mit Priorität importieren" aus.** Wählen Sie im Dialogfeld "Datei-Explorer" die aus. Csv-Datei, die Sie importieren möchten, und wählen Sie dann **Öffnen** aus. Die IDs der physischen Ressourcen aus dem . Der Liste werden die CSV-Dateien hinzugefügt.
4. Navigieren Sie in den Einstellungen **zur** Registerkarte "Richtlinienindikatoren".
5. Navigieren Sie **auf** der Seite  "Richtlinienindikatoren" zum Abschnitt "Indikatoren für den physischen Zugriff", und aktivieren Sie das Kontrollkästchen für physischen Zugriff nach Beendigung oder Nichtzugriff auf **vertrauliche Ressourcen.**
6. Wählen Sie **"Speichern"** aus, um zu konfigurieren und zu beenden.

### <a name="delete-a-priority-physical-asset"></a>Löschen eines physischen Ressourcens mit Priorität

Um ein vorhandenes physisches Objekt mit Priorität zu löschen, verwenden Sie Einstellungssteuerelemente in der Lösung für das Insider-Risikomanagement im Microsoft 365 Compliance Center. Zum Löschen einer physischen Ressource mit Priorität müssen Sie Mitglied der Rollengruppe "Insider-Risikomanagement" oder "Administrator für Insider-Risikomanagement" sein.

>[!IMPORTANT]
>Durch das Löschen eines physischen Ressourcens mit Priorität wird es aus der Prüfung durch eine aktive Richtlinie entfernt, in die es zuvor eingeschlossen war. Warnungen, die von Aktivitäten generiert werden, die der physischen Ressource mit Priorität zugeordnet sind, werden nicht gelöscht.

Führen Sie die folgenden Schritte aus, um eine physische Ressource mit Priorität zu löschen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für Das **Insiderrisiko**   >  **aus.**
2. Wählen Sie **auf der Seite "Priorität der** physischen Ressourcen" die Ressource aus, die Sie löschen möchten.
3. Wählen **Sie im** Aktionsmenü "Löschen" aus, um das Objekt zu löschen.

## <a name="power-automate-flows-preview"></a>Power Automate-Flüsse (Vorschau)

[Microsoft Power Automate](https://docs.microsoft.com/power-automate/getting-started) ist ein Workflowdienst, der Aktionen in verschiedenen Anwendungen und Diensten automatisiert. Mithilfe von Vorlagenflüssen oder manuellen Erstellungen können Sie allgemeine Aufgaben im Zusammenhang mit diesen Anwendungen und Diensten automatisieren. Wenn Sie Power Automate-Flüsse für das Insider-Risikomanagement aktivieren, können Sie wichtige Aufgaben für Fälle und Benutzer automatisieren. Sie können Power Automate-Flüsse konfigurieren, um Benutzer-, Warnungs- und Fallinformationen abzurufen und diese Informationen mit Beteiligten und anderen Anwendungen zu teilen sowie Aktionen im Insider-Risikomanagement zu automatisieren, z. B. Veröffentlichung in Fallnotizen. Power Automate-Flüsse gelten für Fälle und alle Benutzer, die für eine Richtlinie gelten.

Kunden mit Microsoft 365-Abonnements, die das Insider-Risikomanagement umfassen, benötigen keine zusätzlichen Power Automate-Lizenzen, um die empfohlenen Power Automate-Vorlagen für das Insider-Risikomanagement zu verwenden. Diese Vorlagen können angepasst werden, um Ihre Organisation zu unterstützen und zentrale Szenarien des Insider-Risikomanagements zu abdecken. Wenn Sie premium Power Automate-Features in diesen Vorlagen verwenden, eine benutzerdefinierte Vorlage mit dem Microsoft 365 Compliance Connector erstellen oder Power Automate-Vorlagen für andere Compliancebereiche in Microsoft 365 verwenden, benötigen Sie möglicherweise weitere Power Automate-Lizenzen.

Die folgenden Power Automate-Vorlagen werden Kunden zur Unterstützung der Prozessautomatisierung für Benutzer und Fälle des Insider-Risikomanagements bereitgestellt:

- **Benutzer** benachrichtigen, wenn sie einer Richtlinie für Insiderrisiken hinzugefügt werden: Diese Vorlage ist für Organisationen mit internen Richtlinien, Datenschutz- oder behördlichen Anforderungen, dass Benutzer benachrichtigt werden müssen, wenn sie den Richtlinien für das Insiderrisikomanagement unterliegen. Wenn dieser Fluss für einen Benutzer auf der Benutzerseite konfiguriert und ausgewählt ist, wird Benutzern und ihren Vorgesetzten eine E-Mail-Nachricht gesendet, wenn der Benutzer einer Richtlinie für das Insiderrisikomanagement hinzugefügt wird. Diese Vorlage unterstützt auch das Aktualisieren einer auf einer SharePoint-Website gehosteten SharePoint-Liste, um Details von Benachrichtigungen wie Datum/Uhrzeit und den Nachrichtenempfänger nachverfolgt. Wenn Sie sich für die Anonymisierung von Benutzern **in** den Datenschutzeinstellungen entschieden haben, funktionieren flüsse, die aus dieser Vorlage erstellt werden, nicht wie beabsichtigt, damit der Datenschutz des Benutzers erhalten bleibt. Power Automate-Flüsse, die diese Vorlage verwenden, sind im **Benutzerdashboard verfügbar.**
- Fordern Sie Informationen von der Personalabteilung oder dem Unternehmen zu einem Benutzer **in** einem Insiderrisikofall an: Bei der Untersuchung eines Falls müssen Insiderrisikoanalysten und Ermittler sich möglicherweise an die Personalabteilung oder andere Beteiligte wenden, um den Kontext der Fallaktivitäten zu verstehen. Wenn dieser Fluss für einen Fall konfiguriert und ausgewählt ist, senden Analysten und Ermittler eine E-Mail-Nachricht an personal- und geschäftsbeteiligten, die für diesen Fluss konfiguriert sind. Jedem Empfänger wird eine Nachricht mit vorkonfigurierten oder anpassbaren Antwortoptionen gesendet. Wenn Empfänger eine Antwortoption auswählen, wird die Antwort als Fallnotiz aufgezeichnet und enthält Empfänger- und Datums-/Uhrzeitinformationen. Wenn Sie sich für die Anonymisierung von Benutzern **in** den Datenschutzeinstellungen entschieden haben, funktionieren flüsse, die aus dieser Vorlage erstellt werden, nicht wie beabsichtigt, damit der Datenschutz des Benutzers erhalten bleibt. Power Automate-Flüsse, die diese Vorlage verwenden, sind im **Falldashboard verfügbar.**
- **Vorgesetzter benachrichtigen,** wenn ein Benutzer über eine Warnung zu Insiderrisiken verfügt: Einige Organisationen müssen möglicherweise eine sofortige Verwaltungsbenachrichtigung erhalten, wenn ein Benutzer eine Warnung zum Insider-Risikomanagement hat. Wenn dieser Fluss konfiguriert und ausgewählt ist, wird dem Vorgesetzten für den Fallbenutzer eine E-Mail mit den folgenden Informationen zu allen Fallwarnungen gesendet:
    - Anwendbare Richtlinie für die Warnung
    - Datum/Uhrzeit der Warnung
    - Schweregrad der Warnung

    Der Fluss aktualisiert automatisch die Fallnotizen, dass die Nachricht gesendet und der Fluss aktiviert wurde. Wenn Sie sich für die Anonymisierung von Benutzern **in** den Datenschutzeinstellungen entschieden haben, funktionieren flüsse, die aus dieser Vorlage erstellt werden, nicht wie beabsichtigt, damit der Datenschutz des Benutzers erhalten bleibt. Power Automate-Flüsse, die diese Vorlage verwenden, sind im **Falldashboard verfügbar.**

- **Kalendererinnerung** hinzufügen, um nach einem Insiderrisikofall zu suchen: Diese Vorlage ermöglicht Risikoermittlern und Analysten das Hinzufügen von Kalendererinnerungen für Fälle zu ihrem Office 365 Outlook-Kalender. Dieser Fluss entfällt, dass Benutzer den Insider-Risikomanagement-Workflow beenden oder verlassen müssen, wenn Sie Fälle verarbeiten und Warnungen ausschalten. Wenn dieser Fluss konfiguriert und ausgewählt ist, wird dem Office 365 -Outlook-Kalender für den Benutzer, der den Fluss ausgeführt, eine Erinnerung hinzugefügt. Power Automate-Flüsse, die diese Vorlage verwenden, sind im **Falldashboard verfügbar.**
- Erstellen Sie einen Datensatz für den Insider-Risikofall **in ServiceNow:** Diese Vorlage ist für Organisationen, die ihre "ServiceNow"-Lösung verwenden möchten, um Fälle des Insider-Risikomanagements nachverfolgt.  In einem Fall können Insiderrisikoanalysten und Ermittler einen Datensatz für den Fall in ServiceNow erstellen. Sie können diese Vorlage anpassen, um ausgewählte Felder in ServiceNow basierend auf den Anforderungen Ihrer Organisation zu füllen. Power Automate-Flüsse, die diese Vorlage verwenden, sind im **Falldashboard verfügbar.** Weitere Informationen zu verfügbaren ServiceNow-Feldern finden Sie im [ServiceNow Connector-Referenzartikel.](/connectors/service-now/)

### <a name="create-a-power-automate-flow-from-insider-risk-management-template"></a>Erstellen eines Power Automate-Ablaufs aus der Vorlage für das Insider-Risikomanagement

Um einen Power Automate-Fluss aus einer empfohlenen Vorlage für das Insider-Risikomanagement zu erstellen, verwenden Sie die **Einstellungssteuerelemente** in  der Lösung für  das **Insider-Risikomanagement** im Microsoft 365 Compliance Center oder die Option **"Power** Automate-Flüsse verwalten" aus dem Steuerelement "Automatisieren", wenn Sie direkt in den Dashboards "Fälle" oder "Benutzer" arbeiten.

Zum Erstellen eines Power Automate-Ablaufs im Einstellungsbereich müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder "Administrator für *Insider-Risikomanagement"* sein. Um einen Power Automate-Fluss mit der Option **"Power Automate-Flüsse** verwalten" zu erstellen, müssen Sie Mitglied mindestens einer Rollengruppe für das Insider-Risikomanagement sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss aus einer empfohlenen Vorlage für das Insider-Risikomanagement zu erstellen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](https://compliance.microsoft.com/)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für **Insider-Risiken** aus, die Power Automate flows   >  **verwendet.** Sie können auch  über die Dashboardseiten "Fälle" oder **"Benutzer"** zugreifen, indem Sie **power**  >  **automate manage flows auswählen.**
2. Wählen Sie **auf der Seite "Power Automate-Flüsse"** eine empfohlene Vorlage aus den Vorlagen für das **Insider-Risikomanagement** aus, die Ihnen auf der Seite möglicherweise gefällt.
3. Der Fluss listet die eingebetteten Verbindungen auf, die für den Fluss erforderlich sind, und notiert, ob die Verbindungsstatus verfügbar sind. Aktualisieren Sie bei Bedarf alle Verbindungen, die nicht als verfügbar angezeigt werden. Wählen Sie **"Weiter"** aus.
4. Standardmäßig sind die empfohlenen Flüsse mit den empfohlenen Insider-Risikomanagement- und Microsoft 365-Dienstdatenfeldern vorkonfiguriert, die zum Abschließen der zugewiesenen Aufgabe für den Fluss erforderlich sind. Passen Sie bei Bedarf die  Flusskomponenten mithilfe des Steuerelements "Erweiterte Optionen anzeigen" an und konfigurieren Sie die verfügbaren Eigenschaften für die Flusskomponente.
5. Fügen Sie gegebenenfalls weitere Schritte zum Fluss hinzu, indem Sie die Schaltfläche **"Neuer Schritt"** auswählen. In den meisten Fällen sollte dies für die empfohlenen Standardvorlagen nicht erforderlich sein.
6. Wählen **Sie "Entwurf speichern"** aus, um den Fluss zur weiteren Konfiguration zu speichern, oder wählen Sie **"Speichern"** aus, um die Konfiguration für den Fluss fertig zu legen.
7. Wählen **Sie "Schließen"** aus, um zur **Power Automate-Flussseite zurückzukehren.** Die neue Vorlage wird als Fluss  auf den Registerkarten "Meine  Flüsse" aufgeführt und steht automatisch über das Steuerelement "Automatisieren" zur Verfügung, wenn Sie mit Insider-Risikomanagement-Fällen für den Benutzer arbeiten, der den Fluss erstellt.

>[!IMPORTANT]
>Wenn andere Benutzer in Ihrer Organisation Zugriff auf den Fluss benötigen, muss der Fluss freigegeben werden.

### <a name="create-a-custom-power-automate-flow-for-insider-risk-management"></a>Erstellen eines benutzerdefinierten Power Automate-Ablaufs für das Insider-Risikomanagement

Einige Prozesse und Workflows für Ihre Organisation sind möglicherweise außerhalb der empfohlenen Vorlagen für Insider-Risikomanagement-Fluss, und Sie müssen möglicherweise benutzerdefinierte Power Automate-Flüsse für Bereiche des Insider-Risikomanagements erstellen. Power Automate flows are flexible and support extensive customization, but there are steps that need to be taken to integrate with insider risk management features.

Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Power Automate-Vorlage für das Insider-Risikomanagement zu erstellen:

1. **Überprüfen Sie Ihre Power Automate-Flusslizenz:** Um angepasste Power Automate-Flüsse zu erstellen, die Insider-Risikomanagement-Trigger verwenden, benötigen Sie eine Power Automate-Lizenz. Die empfohlenen Vorlagen für den Insider-Risikomanagement-Fluss erfordern keine zusätzliche Lizenzierung und sind als Teil Ihrer Lizenz für das Insider-Risikomanagement enthalten.
2. **Erstellen Eines automatisierten Ablaufs:** Erstellen Sie einen Fluss, der eine oder mehrere Aufgaben ausführt, nachdem er durch ein Insider-Risikomanagement-Ereignis ausgelöst wurde. Weitere Informationen zum Erstellen eines automatisierten Ablaufs finden Sie unter [Erstellen eines Ablaufs in Power Automate.](https://docs.microsoft.com/power-automate/get-started-logic-flow)
3. **Wählen Sie den Microsoft 365-Compliance-Connector** aus: Suchen Sie nach dem Microsoft 365 Compliance-Connector, und wählen Sie diesen aus. Dieser Connector ermöglicht Auslöser und Aktionen des Insider-Risikomanagements. Weitere Informationen zu Connectors finden Sie im [Übersichtsartikel zur Connectorreferenz.](https://docs.microsoft.com/connectors/connector-reference/)
4. **Wählen Sie Auslöser für das Insider-Risikomanagement** für Ihren Fluss aus: Das Insider-Risikomanagement verfügt über zwei Trigger für benutzerdefinierte Power Automate-Flüsse:
    - **Für einen ausgewählten Fall des Insider-Risikomanagements:** Flüsse mit diesem Auslöser können auf der Dashboardseite für Insider-Risikomanagement-Fälle ausgewählt werden.
    - **Für einen ausgewählten Benutzer des Insider-Risikomanagements:** Flüsse mit diesem Auslöser können auf der Dashboardseite "Benutzer des Insider-Risikomanagements" ausgewählt werden.
5. Wählen Sie Aktionen des Insider-Risikomanagements für Ihren Fluss aus: Sie können aus mehreren Aktionen für das Insider-Risikomanagement wählen, um sie in Ihren benutzerdefinierten Fluss zu enthalten:
    - Warnung zum Insider-Risikomanagement erhalten
    - Insider-Risikomanagement-Fall erhalten
    - Benutzer des Insider-Risikomanagements erhalten
    - Erhalten von Benachrichtigungen zum Risikomanagement von Insidern für einen Fall
    - Hinzufügen einer Fallnotiz für das Insider-Risikomanagement

### <a name="share-a-power-automate-flow"></a>Freigeben eines Power Automate-Ablaufs

Standardmäßig sind von einem Benutzer erstellte Power Automate-Flüsse nur für diesen Benutzer verfügbar. Damit andere Benutzer des Insider-Risikomanagements Zugriff auf einen Fluss haben und einen Fluss verwenden können, muss der Fluss vom Ersteller des Ablaufs freigegeben werden. Um einen Fluss zu teilen, verwenden Sie die Einstellungssteuerelemente in der Lösung für das **Insider-Risikomanagement** im Microsoft 365  Compliance Center oder die Option **"Power Automate-Flüsse** verwalten" aus dem Steuerelement "Automatisieren", wenn Sie direkt auf den Dashboardseiten "Fälle" oder "Benutzer" arbeiten.  Nachdem Sie einen Fluss freigegeben haben, kann jeder, für  den er freigegeben  wurde, in der Dropdownliste "Automatisieren" in den Fall- und Benutzerdashboards auf **den Ablauf zugreifen.**

Um einen Power Automate-Fluss im Einstellungsbereich zu teilen, müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder "Administrator für *Insider-Risikomanagement"* sein. Um einen Power Automate-Fluss mit der Option zum Verwalten von **Power Automate-Flüssen** zu teilen, müssen Sie Mitglied mindestens einer Rollengruppe für das Insider-Risikomanagement sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss zu teilen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für **Insider-Risiken** aus, die Power Automate flows   >  **verwendet.** Sie können auch  über die Dashboardseiten "Fälle" oder **"Benutzer"** zugreifen, indem Sie **power**  >  **automate manage flows auswählen.**
2. Wählen Sie **auf der Seite "Power Automate-Flüsse"** die Registerkarte **"Meine Flüsse"** oder **"Teamabläufe"** aus.
3. Wählen Sie den zu teilende Fluss aus, und wählen Sie dann **im** Menü mit den Flussoptionen "Freigeben" aus.
4. Geben Sie auf der Seite "Flussfreigabe" den Namen des Benutzers oder der Gruppe ein, den Sie als Besitzer für den Fluss hinzufügen möchten.
5. Wählen Sie **im Dialogfeld "Verbindung verwendet"** die Option **"OK"** aus, um zu bestätigen, dass der hinzugefügte Benutzer oder die hinzugefügte Gruppe Vollzugriff auf den Fluss hat.

### <a name="edit-a-power-automate-flow"></a>Bearbeiten eines Power Automate-Ablaufs

Zum Bearbeiten eines Ablaufs verwenden Sie die Einstellungssteuerelemente in der Lösung für das **Insider-Risikomanagement** im  Microsoft 365  Compliance Center oder die Option **"Power Automate-Flüsse** verwalten" aus dem Steuerelement "Automatisieren", wenn Sie direkt in den **Dashboards**"Fälle" oder "Benutzer" arbeiten.

Zum Bearbeiten eines Power Automate-Ablaufs im Einstellungsbereich müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder "Administrator für *Insider-Risikomanagement"* sein. Um einen Power Automate-Fluss mit der Option **"Power Automate-Flüsse** verwalten" zu bearbeiten, müssen Sie Mitglied mindestens einer Rollengruppe für das Insider-Risikomanagement sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss zu bearbeiten:

1. Wechseln Sie [im Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für **Insider-Risiken** aus, die Power Automate flows   >  **verwendet.** Sie können auch  über die Dashboardseiten "Fälle" oder **"Benutzer"** zugreifen, indem Sie **power**  >  **automate manage flows auswählen.**
2. Wählen Sie **auf der Power Automate-Flussseite** einen zu bearbeitende Fluss aus, und wählen Sie **im** Menü "Flusssteuerelement" die Option "Bearbeiten" aus.
3. Wählen Sie **die Auslassungspunkte**  >  **"Einstellungen" aus,** um eine Flusskomponenteneinstellung zu ändern, oder klicken Sie auf   >  **"Löschen",** um eine Flusskomponente zu löschen.
4. Wählen **Sie "Speichern"** und dann **"Schließen"** aus, um die Bearbeitung des Ablaufs zu abschließen.

### <a name="delete-a-power-automate-flow"></a>Löschen eines Power Automate-Ablaufs

Um einen Fluss zu löschen, verwenden Sie die Einstellungssteuerelemente in der Lösung für das **Insider-Risikomanagement** im Microsoft 365 Compliance Center oder die Option **"Power Automate-Flüsse** verwalten" aus dem Steuerelement "Automatisieren", wenn Sie direkt in den **Dashboards**"Fälle" oder "Benutzer" arbeiten.   Wenn ein Fluss gelöscht wird, wird er als Option für alle Benutzer entfernt.

Zum Löschen eines Power Automate-Ablaufs im Einstellungsbereich müssen Sie Mitglied der Rollengruppe *"Insider-Risikomanagement"* oder "Administrator für *Insider-Risikomanagement"* sein. Um einen Power Automate-Fluss mit der Option **"Power Automate-Flüsse** verwalten" zu löschen, müssen Sie Mitglied mindestens einer Rollengruppe für das Insider-Risikomanagement sein.

Führen Sie die folgenden Schritte aus, um einen Power Automate-Fluss zu löschen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu Insider-Risikomanagement, und wählen Sie die Einstellungen für **Insider-Risiken** aus, die Power Automate flows   >  **verwendet.** Sie können auch  über die Dashboardseiten "Fälle" oder **"Benutzer"** zugreifen, indem Sie **power**  >  **automate manage flows auswählen.**
2. Wählen Sie **auf der Seite "Power Automate-Flüsse"** einen zu löschende Fluss aus, und wählen Sie **im** Menü "Flusssteuerung" "Löschen" aus.
3. Wählen Sie im Dialogfeld zur Bestätigung des Löschvorgangs **"Löschen"** aus, um den Fluss zu entfernen, oder wählen Sie **"Abbrechen"** aus, um die Löschaktion zu beenden.

## <a name="microsoft-teams-preview"></a>Microsoft Teams (Vorschau)

Complianceanalysten und Ermittler können Microsoft Teams problemlos für die Zusammenarbeit bei Insider-Risikomanagement-Fällen verwenden. Sie können sich koordinieren und mit anderen Beteiligten in Microsoft Teams kommunizieren, um:

- Koordinieren und Überprüfen von Reaktionsaktivitäten für Fälle in privaten Teams-Kanälen
- Sicheres Freigeben und Speichern von Dateien und Nachweisen im Zusammenhang mit einzelnen Fällen
- Nachverfolgen und Überprüfen der Reaktionsaktivitäten von Analysten und Ermittlern

Nachdem Microsoft Teams für das Insiderrisikomanagement aktiviert wurde, wird jedes Mal, wenn eine Warnung bestätigt und ein Fall erstellt wird, ein dediziertes Microsoft Teams-Team erstellt. Standardmäßig umfasst das Team automatisch alle Mitglieder der Rollengruppen *"Insider Risk Management",* *"Insider Risk Management Analysts"* und *"Insider Risk Management Investigators"* (bis zu 100 anfängliche Benutzer). Weitere Mitwirkende der Organisation können dem Team hinzugefügt werden, nachdem es erstellt wurde. Bei vorhandenen Fällen, die vor der Aktivierung von Microsoft Teams erstellt wurden, können Analysten und Ermittler bei Bedarf ein neues Microsoft Teams-Team erstellen.  Nachdem Sie den zugeordneten Fall im Insider-Risikomanagement aufgelöst haben, wird das Team automatisch archiviert (in ausgeblendet und schreibgeschützt).

Weitere Informationen zur Verwendung von Teams und Kanälen in Microsoft Teams finden Sie unter Übersicht über Teams [und Kanäle in Microsoft Teams.](https://docs.microsoft.com/MicrosoftTeams/teams-channels-overview)

Die Aktivierung der Microsoft Teams-Unterstützung für Fälle ist schnell und einfach zu konfigurieren. Führen Sie die folgenden Schritte aus, um Microsoft Teams für das Insider-Risikomanagement zu aktivieren:

1. Wechseln Sie [im Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu den Insider-Risikomanagement-Insider-Risikoeinstellungen.   >  
2. Wählen Sie die **Registerkarte "Microsoft Teams"** aus.
3. Aktivieren sie die Integration von Microsoft Teams für das Insider-Risikomanagement.
4. Wählen Sie **"Speichern"** aus, um zu konfigurieren und zu beenden.

### <a name="create-a-microsoft-teams-team-for-existing-cases"></a>Erstellen eines Microsoft Teams-Teams für vorhandene Fälle

Wenn Sie die Unterstützung von Microsoft Teams für das Insider-Risikomanagement aktivieren, nachdem Sie bereits Fälle erstellt haben, müssen Sie bei Bedarf manuell ein Team für jeden Fall erstellen. Nach der Aktivierung der Microsoft Teams-Unterstützung in den Einstellungen für das Insider-Risikomanagement erstellen neue Fälle automatisch ein neues Microsoft Teams-Team.

Benutzer benötigen die Berechtigung zum Erstellen von Microsoft 365-Gruppen in Ihrer Organisation, um ein Microsoft Teams-Team aus einem Fall zu erstellen. Weitere Informationen zum Verwalten von Berechtigungen für Microsoft 365-Gruppen finden Sie unter Verwalten, wer [Microsoft 365-Gruppen erstellen kann.](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups)

Um ein Team für einen Fall zu erstellen, verwenden Sie das Steuerelement "Microsoft Team erstellen", wenn Sie direkt in einem vorhandenen Fall arbeiten. Führen Sie die folgenden Schritte aus, um ein neues Team zu erstellen:

1. Wechseln Sie [im Microsoft 365 Compliance Center](htttps://compliance.microsoft.com)zu "Insider-Risikomanagementfälle", und wählen Sie einen   >   vorhandenen Fall aus.
2. Wählen Sie im Menü "Fallaktion" die Option **"Microsoft Team erstellen" aus.**
3. Geben Sie **im Feld "Teamname"** einen Namen für das neue Microsoft Teams-Team ein.
4. Wählen **Sie "Microsoft Team erstellen"** und dann **"Schließen" aus.**

Je nach Anzahl der Benutzer, die Rollengruppen des Insiderrisikomanagements zugewiesen sind, kann es 15 Minuten dauern, bis alle Ermittler und Analysten dem Microsoft Teams-Team für einen Fall hinzugefügt werden.
