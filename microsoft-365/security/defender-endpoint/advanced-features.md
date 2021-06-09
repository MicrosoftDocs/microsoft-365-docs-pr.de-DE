---
title: Konfigurieren erweiterter Features in Microsoft Defender für Endpunkt
description: Aktivieren Sie erweiterte Features wie das Blockieren von Dateien in Microsoft Defender für Endpunkt.
keywords: Erweiterte Features, Einstellungen, Datei blockieren, automatische Untersuchung, automatische Auflösung, Skype, Microsoft Defender für Identität, Office 365, Azure Information Protection, Intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 7fd9ec25c21b2d70238bd5b0d6b58b60731088ea
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845474"
---
# <a name="configure-advanced-features-in-defender-for-endpoint"></a>Konfigurieren erweiterter Features in Defender für Endpunkt

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedfeats-abovefoldlink)

Je nach den von Ihnen verwendeten Microsoft-Sicherheitsprodukten sind möglicherweise einige erweiterte Features verfügbar, mit denen Sie Defender für Endpunkt integrieren können.

## <a name="enable-advanced-features"></a>Aktivieren erweiterter Features

1. Wählen Sie im Navigationsbereich **"Einstellungen einrichten**  >  **Erweiterte Features"** aus.
2. Wählen Sie das erweiterte Feature aus, das Sie konfigurieren möchten, und schalten Sie die Einstellung zwischen **"Ein"** und **"Aus".**
3. Klicken Sie auf **"Einstellungen speichern".**

Verwenden Sie die folgenden erweiterten Features, um sich besser vor potenziell schädlichen Dateien zu schützen und während Sicherheitsuntersuchungen bessere Einblicke zu erhalten.

## <a name="automated-investigation"></a>Automatisierte Untersuchung

Aktivieren Sie dieses Feature, um die Automatisierten Untersuchungs- und Wartungsfeatures des Diensts zu nutzen. Weitere Informationen finden Sie unter ["Automatisierte Untersuchung".](automated-investigations.md)

## <a name="live-response"></a>Live-Antwort

Aktivieren Sie dieses Feature, damit Benutzer mit den entsprechenden Berechtigungen eine Liveantwortsitzung auf Geräten starten können.

Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)

## <a name="live-response-for-servers"></a>Liveantwort für Server
Aktivieren Sie dieses Feature, damit Benutzer mit den entsprechenden Berechtigungen eine Liveantwortsitzung auf Servern starten können.

Weitere Informationen zu Rollenzuweisungen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)


## <a name="live-response-unsigned-script-execution"></a>Ausführung nicht signierter Skripts für Liveantworten

Wenn Sie dieses Feature aktivieren, können Sie nicht signierte Skripts in einer Liveantwortsitzung ausführen.

## <a name="always-remediate-pua"></a>PuA immer korrigieren
Potenziell unerwünschte Anwendungen (PUA) sind eine Kategorie von Software, die dazu führen kann, dass Ihr Computer langsam ausgeführt wird, unerwartete Anzeigen anzeigt oder im schlechtesten Fall andere Software installiert, die unerwartet oder unerwünscht sein kann. 

Aktivieren Sie dieses Feature, damit potenziell unerwünschte Anwendungen (PUA) auf allen Geräten in Ihrem Mandanten behoben werden, auch wenn der PUA-Schutz auf den Geräten nicht konfiguriert ist. Dadurch werden Benutzer vor der versehentlichen Installation unerwünschter Anwendungen auf ihrem Gerät geschützt. Wenn die Korrektur deaktiviert ist, hängt sie von der Gerätekonfiguration ab. 


## <a name="restrict-correlation-to-within-scoped-device-groups"></a>Beschränken der Korrelation auf bereichsbezogene Gerätegruppen
Diese Konfiguration kann für Szenarien verwendet werden, in denen lokale SOC-Vorgänge Warnungskorrelationen nur auf Gerätegruppen beschränken möchten, auf die sie zugreifen können. Wenn Sie diese Einstellung aktivieren, wird ein Vorfall, der aus Warnungen besteht, die geräteübergreifend auftreten, nicht mehr als einzelner Vorfall betrachtet. Der lokale SOC kann dann maßnahmen gegen den Vorfall ergreifen, da er Zugriff auf eine der beteiligten Gerätegruppen hat. Globale SOC sieht jedoch mehrere unterschiedliche Vorfälle nach Gerätegruppe anstelle eines Vorfalls. Es wird nicht empfohlen, diese Einstellung zu aktivieren, es sei denn, dadurch werden die Vorteile der Vorfallkorrelation in der gesamten Organisation zunichtet.
>[!NOTE]
>Das Ändern dieser Einstellung wirkt sich nur auf zukünftige Warnungskorrelationen aus.

## <a name="enable-edr-in-block-mode"></a>Aktivieren EDR im Blockierungsmodus
Endpunkterkennung und -reaktion (EDR) im Blockierungsmodus bieten Schutz vor bösartigen Artefakten, auch wenn Microsoft Defender Antivirus im passiven Modus ausgeführt wird. Wenn sie aktiviert ist, blockiert EDR im Blockierungsmodus bösartige Artefakte oder Verhaltensweisen, die auf einem Gerät erkannt werden. EDR im Blockierungsmodus funktioniert im Hintergrund, um böswillige Artefakte zu beheben, die nach der Verletzung erkannt werden.


## <a name="autoresolve-remediated-alerts"></a>Autoresolve remediierte Warnungen

Für Mandanten, die auf oder nach Windows 10, Version 1809, erstellt wurden, ist die Funktion für automatische Untersuchung und Behebung standardmäßig so konfiguriert, dass Warnungen aufgelöst werden, bei denen der Status des automatisierten Analyseergebnisses "Keine Bedrohungen gefunden" oder "Behoben" ist.  Wenn Warnungen nicht automatisch aufgelöst werden sollen, müssen Sie das Feature manuell deaktivieren.

> [!TIP]
> Für Mandanten, die vor dieser Version erstellt wurden, müssen Sie dieses Feature auf der Seite ["Erweiterte Features"](https://securitycenter.windows.com/preferences2/integration) manuell aktivieren.

> [!NOTE]
>
> - Das Ergebnis der Automatischen Auflösungsaktion kann die Berechnung der Geräterisikostufe beeinflussen, die auf den aktiven Warnungen auf einem Gerät basiert.
> - Wenn ein Sicherheitsbetriebsanalyst den Status einer Warnung manuell auf "In Bearbeitung" oder "Aufgelöst" festlegt, überschreibt die Funktion für die automatische Auflösung diese nicht.

## <a name="allow-or-block-file"></a>Datei zulassen oder blockieren

Das Blockieren ist nur verfügbar, wenn Ihre Organisation die folgenden Anforderungen erfüllt:

- Verwendet Microsoft Defender Antivirus als aktive Antischadsoftwarelösung und
- Das cloudbasierte Schutzfeature ist aktiviert.

Mit diesem Feature können Sie potenziell schädliche Dateien in Ihrem Netzwerk blockieren. Durch das Blockieren einer Datei wird verhindert, dass sie auf Geräten in Ihrer Organisation gelesen, geschrieben oder ausgeführt wird.

So aktivieren **Sie "Zulassen" oder "Blockieren"** von Dateien:

1. Wählen Sie im Navigationsbereich **Einstellungen**  >  **Erweiterten Features**  >  **"Datei zulassen oder blockieren"** aus.

1. Umschalten der Einstellung zwischen **"Ein"** und **"Aus".**

    ![Abbildung der erweiterten Einstellungen für das Feature zum Blockieren von Dateien](images/atp-preferences-setup.png)

1. Wählen Sie **"Einstellungen speichern"** am unteren Rand der Seite aus.

Nachdem Sie dieses Feature aktiviert haben, können Sie Dateien über die Registerkarte **"Indikator hinzufügen"** auf der Profilseite einer Datei [blockieren.](respond-file-alerts.md#allow-or-block-file)

## <a name="custom-network-indicators"></a>Benutzerdefinierte Netzwerkindikatoren

Wenn Sie dieses Feature aktivieren, können Sie Indikatoren für IP-Adressen, Domänen oder URLs erstellen, die bestimmen, ob sie basierend auf Ihrer benutzerdefinierten Indikatorliste zugelassen oder blockiert werden.

Um dieses Feature verwenden zu können, müssen Geräte Windows 10 Version 1709 oder höher ausgeführt werden. Sie sollten auch über Netzwerkschutz im Blockierungsmodus und Version 4.18.1906.3 oder höher der Antischadsoftwareplattform [verfügen, siehe KB 4052623.](https://go.microsoft.com/fwlink/?linkid=2099834)

Weitere Informationen finden Sie unter [Verwalten von Indikatoren.](manage-indicators.md)

> [!NOTE]
> Der Netzwerkschutz nutzt Reputationsdienste, die Anforderungen an Orten verarbeiten, die sich möglicherweise außerhalb des Speicherorts befinden, den Sie für Ihre Defender für Endpunkt-Daten ausgewählt haben.

## <a name="tamper-protection"></a>Manipulationsschutz
Bei einigen Arten von Cyberangriffen versuchen angreifer, Sicherheitsfeatures wie Virenschutz auf Ihren Computern zu deaktivieren. Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices.

Der Manipulationsschutz sperrt im Wesentlichen Microsoft Defender Antivirus und verhindert, dass Ihre Sicherheitseinstellungen über Apps und Methoden geändert werden.

Dieses Feature ist verfügbar, wenn Ihre Organisation Microsoft Defender Antivirus verwendet und der cloudbasierte Schutz aktiviert ist. Weitere Informationen finden Sie unter Verwenden von Technologien der nächsten Generation in Microsoft Defender Antivirus über über [die Cloud bereitgestellten Schutz.](cloud-protection-microsoft-defender-antivirus.md)

Lassen Sie den Manipulationsschutz aktiviert, um unerwünschte Änderungen an Ihrer Sicherheitslösung und den wesentlichen Features zu verhindern.


## <a name="show-user-details"></a>Anzeigen von Benutzerdetails

Aktivieren Sie dieses Feature, damit Sie benutzerdetails anzeigen können, die in Azure Active Directory gespeichert sind. Details umfassen das Bild, den Namen, den Titel und die Abteilungsinformationen eines Benutzers bei der Untersuchung von Benutzerkontoentitäten. Informationen zum Benutzerkonto finden Sie in den folgenden Ansichten:

- Dashboard für Sicherheitsvorgänge
- Warnungswarteschlange
- Seite "Gerätedetails"

Weitere Informationen finden Sie unter [Untersuchen eines Benutzerkontos.](investigate-user.md)


## <a name="skype-for-business-integration"></a>integration von Skype for Business

Wenn Sie die Skype for Business Integration aktivieren, können Sie mit Benutzern über Skype for Business, E-Mail oder Telefon kommunizieren. Dies kann nützlich sein, wenn Sie mit dem Benutzer kommunizieren und Risiken mindern müssen.

> [!NOTE]
> Wenn ein Gerät vom Netzwerk isoliert wird, gibt es ein Popup, in dem Sie auswählen können, Outlook und Skype Kommunikation zu aktivieren, die die Kommunikation mit dem Benutzer ermöglicht, während er vom Netzwerk getrennt ist. Diese Einstellung gilt für Skype und Outlook Kommunikation, wenn sich Geräte im Isolationsmodus befinden.

## <a name="microsoft-defender-for-identity-integration"></a>Microsoft Defender for Identity-Integration

Die Integration in Microsoft Defender for Identity ermöglicht es Ihnen, direkt in ein anderes Microsoft Identity-Sicherheitsprodukt zu pivotieren. Microsoft Defender for Identity ergänzt eine Untersuchung mit zusätzlichen Erkenntnissen über ein verdächtiges kompromittiertes Konto und verwandte Ressourcen. Wenn Sie dieses Feature aktivieren, erweitern Sie die gerätebasierte Untersuchungsfunktion, indem Sie aus einer bestimmten Sicht über das Netzwerk pivotieren.

> [!NOTE]
> Sie benötigen die entsprechende Lizenz, um dieses Feature zu aktivieren.

## <a name="office-365-threat-intelligence-connection"></a>Office 365 Threat Intelligence-Verbindung

Dieses Feature ist nur verfügbar, wenn Sie über ein aktives Office 365 E5 oder das Threat Intelligence-Add-On verfügen. Weitere Informationen finden Sie auf der Office 365 Enterprise E5-Produktseite.

Wenn Sie dieses Feature aktivieren, können Sie Daten aus Microsoft Defender für Office 365 in Microsoft Defender Security Center integrieren, um eine umfassende Sicherheitsuntersuchung für Office 365 Postfächer und Windows Geräte durchzuführen.

> [!NOTE]
> Sie benötigen die entsprechende Lizenz, um dieses Feature zu aktivieren.

Um kontextbezogene Geräteintegration in Office 365 Threat Intelligence zu erhalten, müssen Sie die Defender für Endpunkt-Einstellungen im Security & Compliance-Dashboard aktivieren. Weitere Informationen finden Sie unter [Untersuchung und Reaktion auf Bedrohungen.](/microsoft-365/security/office-365-security/office-365-ti)

## <a name="microsoft-threat-experts---targeted-attack-notifications"></a>Microsoft-Bedrohungsexperten – Benachrichtigungen über gezielte Angriffe

Von den beiden Microsoft Threat Expert-Komponenten ist die Benachrichtigung über gezielte Angriffe allgemein verfügbar. Die Funktion "Experten nach Bedarf" befindet sich noch in der Vorschau. Sie können die Funktion "Experten bei Bedarf" nur verwenden, wenn Sie sich für die Vorschau angemeldet haben und Ihre Anwendung genehmigt wurde. Sie können benutzerorientierte Angriffsbenachrichtigungen von Microsoft-Bedrohungsexperten über das Warnungsdashboard Ihres Defender für Endpunkt-Portals und per E-Mail erhalten, wenn Sie es konfigurieren.

> [!NOTE]
> Die Microsoft-Bedrohungsexperten-Funktion in Defender für Endpunkt ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)verfügbar.
## <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security

Wenn Sie diese Einstellung aktivieren, werden Die Signale von Defender für Endpunkt an Microsoft Cloud App Security weitergeleitet, um einen tieferen Einblick in die Nutzung von Cloudanwendungen zu bieten. Weitergeleitete Daten werden am selben Speicherort wie Ihre Cloud App Security-Daten gespeichert und verarbeitet.

> [!NOTE]
> Dieses Feature ist mit einer E5-Lizenz für [Enterprise Mobility + Security](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) auf Geräten verfügbar, auf denen Windows 10 ausgeführt wird. Version 1709 (BS Build 16299.1085 mit [KB4493441](https://support.microsoft.com/help/4493441)), Windows 10, Version 1803 (Betriebssystembuild 17134.704 mit [KB4493464](https://support.microsoft.com/help/4493464)), Windows 10, Version 1809 (Betriebssystembuild 17763.379 mit [KB4489899)](https://support.microsoft.com/help/4489899)oder höher Windows 10 Versionen.

## <a name="microsoft-secure-score"></a>Microsoft-Sicherheitsbewertung

Leitet Microsoft Defender für Endpunkt-Signale an die Microsoft-Sicherheitsbewertung im Microsoft 365 Security Center weiter. Wenn Sie dieses Feature aktivieren, erhält Microsoft Secure Score Einen Einblick in den Sicherheitsstatus des Geräts. Weitergeleitete Daten werden am selben Speicherort wie Ihre Microsoft-Sicherheitsbewertungsdaten gespeichert und verarbeitet.


### <a name="enable-the-microsoft-defender-for-endpoint-integration-from-the-microsoft-defender-for-identity-portal"></a>Aktivieren der Microsoft Defender für Endpunkt-Integration über das Microsoft Defender for Identity-Portal

Um die kontextbezogene Geräteintegration in Microsoft Defender for Identity zu erhalten, müssen Sie das Feature auch im Microsoft Defender for Identity-Portal aktivieren.

1. Melden Sie sich beim [Microsoft Defender for Identity-Portal](https://portal.atp.azure.com/) mit der Rolle "Globaler Administrator" oder "Sicherheitsadministrator" an.

2. Klicken Sie auf **"Instanz erstellen".**

3. Setzen Sie die Integrationseinstellung auf **"Ein",** und klicken Sie auf **"Speichern".**

Nach Abschluss der Integrationsschritte auf beiden Portalen können Sie relevante Warnungen auf der Seite mit den Gerätedetails oder benutzerdetails anzeigen.

## <a name="web-content-filtering"></a>Internet-Inhaltsfilterung
Blockieren Sie den Zugriff auf Websites, die unerwünschte Inhalte enthalten, und verfolgen Sie Webaktivitäten in allen Domänen. Erstellen Sie eine [Webinhaltsfilterrichtlinie,](https://security.microsoft.com/preferences2/web_content_filtering_policy)um die zu blockierenden Webinhaltskategorien anzugeben. Stellen Sie sicher, dass Der Netzwerkschutz im Blockierungsmodus vorhanden ist, wenn Sie die [Microsoft Defender für Endpunkt-Sicherheitsgrundwerte](https://devicemanagement.microsoft.com/#blade/Microsoft_Intune_Workflows/SecurityBaselineSummaryMenu/overview/templateType/2)bereitstellen.


## <a name="share-endpoint-alerts-with-microsoft-compliance-center"></a>Freigeben von Endpunktwarnungen mit dem Microsoft Compliance Center
Leitet Endpunktsicherheitswarnungen und deren Triagestatus an das Microsoft Compliance Center weiter, sodass Sie Richtlinien für das Insider-Risikomanagement mit Warnungen verbessern und interne Risiken beheben können, bevor sie Schaden verursachen. Weitergeleitete Daten werden am selben Speicherort wie Ihre Office 365-Daten verarbeitet und gespeichert.

Nach der Konfiguration der [Indikatoren für Sicherheitsrichtlinienverstöße](/microsoft-365/compliance/insider-risk-management-settings#indicators) in den Einstellungen für das Insider-Risikomanagement werden Defender für Endpunkt-Warnungen mit dem Insider-Risikomanagement für die entsprechenden Benutzer geteilt.



## <a name="microsoft-intune-connection"></a>Microsoft Intune Verbindung

Defender für Endpunkt kann in [Microsoft Intune](/intune/what-is-intune) integriert werden, um den [risikobasierten bedingten Zugriff](/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune)auf Geräte zu ermöglichen. Wenn Sie [dieses Feature aktivieren,](configure-conditional-access.md)können Sie Defender für Endpunkt-Geräteinformationen für Intune freigeben, wodurch die Richtlinienerzwingung verbessert wird.

> [!IMPORTANT]
> Sie müssen die Integration in Intune und Defender für Endpunkt aktivieren, um dieses Feature zu verwenden. Weitere Informationen zu bestimmten Schritten finden Sie unter [Konfigurieren des bedingten Zugriffs in Defender für Endpunkt.](configure-conditional-access.md)

Dieses Feature ist nur verfügbar, wenn Sie über Folgendes verfügen:

- Ein lizenzierter Mandant für Enterprise Mobility + Security E3 und Windows E5 (oder Microsoft 365 Enterprise E5)
- Eine aktive Microsoft Intune-Umgebung mit intune-verwalteten Windows 10 Geräten, die [in Azure AD eingebunden sind.](/azure/active-directory/devices/concept-azure-ad-join/)


### <a name="conditional-access-policy"></a>Richtlinie für bedingten Zugriff

Wenn Sie die Intune-Integration aktivieren, erstellt Intune automatisch eine klassische Richtlinie für bedingten Zugriff (Conditional Access, CA). Diese klassische Zertifizierungsstellenrichtlinie ist eine Voraussetzung für das Einrichten von Statusberichten für Intune. Sie sollte nicht gelöscht werden.

> [!NOTE]
> Die von Intune erstellte klassische Zertifizierungsstellenrichtlinie unterscheidet sich von modernen Richtlinien für [bedingten Zugriff,](/azure/active-directory/conditional-access/overview/)die zum Konfigurieren von Endpunkten verwendet werden.


## <a name="device-discovery"></a>Geräteermittlung
Hilft Ihnen, nicht verwaltete Geräte zu finden, die mit Ihrem Unternehmensnetzwerk verbunden sind, ohne dass zusätzliche Appliances oder umständliche Prozessänderungen erforderlich sind. Mithilfe von integrierten Geräten können Sie nicht verwaltete Geräte in Ihrem Netzwerk finden und Sicherheitsrisiken und Risiken bewerten. Weitere Informationen finden Sie unter [Device Discovery](device-discovery.md).

> [!NOTE]
> Sie können immer Filter anwenden, um nicht verwaltete Geräte aus der Gerätebestandsliste auszuschließen. Sie können auch die Spalte "Onboardingstatus" in API-Abfragen verwenden, um nicht verwaltete Geräte herauszufiltern. 

## <a name="preview-features"></a>Vorschaufeatures

Erfahren Sie mehr über die neuen Features in der Defender für Endpunkt-Vorschauversion. Probieren Sie bevorstehende Features aus, indem Sie die Vorschau aktivieren.

Sie haben Zugriff auf anstehende Features, zu denen Sie Feedback geben können, um die Gesamterfahrung zu verbessern, bevor Features allgemein verfügbar sind.




## <a name="related-topics"></a>Verwandte Themen

- [Aktualisieren der Einstellungen für die Datenaufbewahrung](data-retention-settings.md)
- [Warnungsbenachrichtigungen konfigurieren](configure-email-notifications.md)
