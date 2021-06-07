---
title: Schützen von Sicherheitseinstellungen mit Manipulationsschutz
ms.reviewer: shwjha, hayhov
manager: dansimp
description: Verwenden Sie Manipulationsschutz, um zu verhindern, dass schädliche Apps wichtige Sicherheitseinstellungen ändern.
keywords: Schadsoftware, Defender, Antivirus, Manipulationsschutz
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 05/17/2021
ms.openlocfilehash: 2d212bedf9033b0824d32e7f42afea3944d9ca67
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782813"
---
# <a name="protect-security-settings-with-tamper-protection"></a>Schützen von Sicherheitseinstellungen mit Manipulationsschutz

**Gilt für:**

- [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/)

Der Manipulationsschutz ist für Geräte verfügbar, auf denen eine der folgenden Versionen von Windows ausgeführt wird:

- Windows 10
- Windows Server 2019
- Windows Server, Version 1803 oder höher
- Windows Server 2016

## <a name="overview"></a>Übersicht

Bei einigen Arten von Cyberangriffen versuchen angreifer, Sicherheitsfeatures wie Virenschutz auf Ihren Computern zu deaktivieren. Bad actors like to disable your security features to get easier access to your data, to install malware, or to otherwise exploit your data, identity, and devices. Der Manipulationsschutz trägt dazu bei, diese Art von Dingen zu verhindern.

Mit Manipulationsschutz wird verhindert, dass schädliche Apps Aktionen ausführen, z. B.:

- Deaktivieren des Viren- und Bedrohungsschutzes
- Deaktivieren des Echtzeitschutzes
- Deaktivieren der Verhaltensüberwachung
- Deaktivieren von Antivirus (z. B. IOfficeAntivirus (IOAV))
- Deaktivieren des über die Cloud bereitgestellten Schutzes
- Entfernen von Sicherheitsupdates

### <a name="how-it-works"></a>Funktionsweise

Der Manipulationsschutz sperrt im Wesentlichen Microsoft Defender Antivirus und verhindert, dass Ihre Sicherheitseinstellungen durch Apps und Methoden geändert werden, z. B.:

- Konfigurieren von Einstellungen im Registrierungs-Editor auf Ihrem Windows Gerät
- Ändern von Einstellungen über PowerShell-Cmdlets
- Bearbeiten oder Entfernen von Sicherheitseinstellungen über Gruppenrichtlinien

Der Manipulationsschutz hindert Sie nicht daran, Ihre Sicherheitseinstellungen anzuzeigen. Und der Manipulationsschutz hat keinen Einfluss darauf, wie Antiviren-Apps von Drittanbietern bei der Windows-Sicherheit-App registriert werden. Wenn Ihre Organisation Windows 10 Enterprise E5 verwendet, können einzelne Benutzer die Einstellung für den Manipulationsschutz nicht ändern. In diesen Fällen wird der Manipulationsschutz von Ihrem Sicherheitsteam verwaltet.

### <a name="what-do-you-want-to-do"></a>Was möchten Sie machen?

| So führen Sie diese Aufgabe aus... | Siehe diesen Abschnitt... |
|:---|:---|
| Verwalten des Manipulationsschutzes in Ihrem Mandanten <p>Verwenden der Microsoft Defender Security Center zum Ein- oder Ausschalten des Manipulationsschutzes | [Verwalten des Manipulationsschutzes für Ihre Organisation mithilfe der Microsoft Defender Security Center](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) |
| Optimieren der Manipulationsschutzeinstellungen in Ihrer Organisation <p>Verwenden Sie Intune (Microsoft Endpoint Manager), um den Manipulationsschutz zu aktivieren oder zu deaktivieren. Mit dieser Methode können Sie den Manipulationsschutz für einige oder alle Benutzer konfigurieren. | [Verwalten des Manipulationsschutzes für Ihre Organisation mit Intune](#manage-tamper-protection-for-your-organization-using-intune) |
| Aktivieren (oder Deaktivieren) des Manipulationsschutzes für Ihre Organisation mit Configuration Manager | [Verwalten des Manipulationsschutzes für Ihre Organisation mithilfe von Mandantenanfügung mit Configuration Manager, Version 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006) |
| Ein- oder Ausschalten des Manipulationsschutzes für ein einzelnes Gerät | [Verwalten des Manipulationsschutzes auf einem einzelnen Gerät](#manage-tamper-protection-on-an-individual-device) |
| Anzeigen von Details zu Manipulationsversuchen auf Geräten | [Anzeigen von Informationen zu Manipulationsversuchen](#view-information-about-tampering-attempts) |
| Überprüfen Ihrer Sicherheitsempfehlungen | [Überprüfen von Sicherheitsempfehlungen](#review-your-security-recommendations) |
| Überprüfen der Liste der häufig gestellten Fragen (FAQs) | [Durchsuchen der häufig gestellten Fragen](#view-information-about-tampering-attempts) |

Abhängig von der Methode oder dem Verwaltungstool, das Sie zum Aktivieren des Manipulationsschutzes verwenden, besteht möglicherweise eine Abhängigkeit von MAPS (über die Cloud bereitgestellter Schutz). 

Die folgende Tabelle enthält Details zu den Methoden, Tools und Abhängigkeiten.

| So wird der Manipulationsschutz aktiviert  | Abhängigkeit von MAPS (über die Cloud bereitgestellter Schutz)    |
|:----|:----|
| Microsoft Intune  | Nein |
| Microsoft Endpoint Configuration Manager + Mandantenanfügung  |     Nein  |
| Microsoft Defender Security Center ( [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) )    |     Ja |
| Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) )  |     Ja  |

## <a name="manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center"></a>Verwalten des Manipulationsschutzes für Ihre Organisation mithilfe der Microsoft Defender Security Center

Der Manipulationsschutz kann für Ihren Mandanten mithilfe der Microsoft Defender Security Center ( ) aktiviert oder deaktiviert [https://securitycenter.windows.com](https://securitycenter.windows.com) werden. Beachten Sie hier einige Punkte:

- Derzeit ist die Option zum Verwalten des Manipulationsschutzes im Microsoft Defender Security Center für neue Bereitstellungen standardmäßig aktiviert. Für vorhandene Bereitstellungen steht der Manipulationsschutz auf der Basis der Anmeldung zur Verfügung, mit Plänen, in naher Zukunft die Standardmethode zu aktivieren. (Wenn Sie sich anmelden möchten, wählen Sie im Microsoft Defender Security Center **Einstellungen**  >  **Erweiterte Features**  >  **Manipulationsschutz**.) 

- Wenn Sie die Microsoft Defender Security Center zum Verwalten des Manipulationsschutzes verwenden, müssen Sie intune oder die Methode zum Anfügen von Mandanten nicht verwenden.

- Wenn Sie den Manipulationsschutz im Microsoft Defender Security Center verwalten, wird die Einstellung mandantenweit angewendet und wirkt sich auf alle Ihre Geräte aus, auf denen Windows 10, Windows Server 2016 oder Windows Server 2019 ausgeführt wird. Verwenden Sie [Intune](#manage-tamper-protection-for-your-organization-using-intune) oder [Configuration Manager mit Mandantenanfügung,](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)um den Manipulationsschutz (z. B. Manipulationsschutz für einige Geräte, aber deaktiviert für andere Geräte) zu optimieren.

- Wenn Sie über eine Hybridumgebung verfügen, haben in Intune konfigurierte Manipulationsschutzeinstellungen Vorrang vor einstellungen, die im Microsoft Defender Security Center konfiguriert sind. 

### <a name="requirements-for-managing-tamper-protection-in-the-microsoft-defender-security-center"></a>Anforderungen für die Verwaltung des Manipulationsschutzes in der Microsoft Defender Security Center

- Sie müssen über entsprechende [Berechtigungen](/microsoft-365/security/defender-endpoint/assign-portal-access)verfügen, z. B. globale Administratoren, Sicherheitsadministratoren oder Sicherheitsvorgänge.

- Auf Ihren Windows Geräten muss eine der folgenden Versionen von Windows ausgeführt werden:
   - Windows 10
   - [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
   - Windows Server, Version [1803](/windows/release-health/status-windows-10-1803) oder höher
   - [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016)
   - Weitere Informationen zu Versionen finden Sie unter [Windows 10 Versionsinformationen.](/windows/release-health/release-information)

- Ihre Geräte müssen [in Microsoft Defender für Endpunkt integriert](/microsoft-365/security/defender-endpoint/onboarding)sein.

- Ihre Geräte müssen die Antischadsoftwareplattform version 4.18.2010.7 (oder höher) und die Antischadsoftwaremodul-Version 1.1.17600.5 (oder höher) verwenden. ([Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.)](manage-updates-baselines-microsoft-defender-antivirus.md)

- Der über die [Cloud bereitgestellte Schutz](enable-cloud-protection-microsoft-defender-antivirus.md) muss aktiviert sein.

### <a name="turn-tamper-protection-on-or-off-in-the-microsoft-defender-security-center"></a>Manipulationsschutz im Microsoft Defender Security Center aktivieren (oder deaktivieren) 

![Manipulationsschutz im Microsoft Defender Security Center aktivieren](images/mde-turn-tamperprotect-on.png)

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) und melden Sie sich an.

2. Wählen Sie **Einstellungen** aus.

3. Wechseln Sie zu **"Allgemeine**  >  **erweiterte Features",** und aktivieren Sie dann den Manipulationsschutz.

## <a name="manage-tamper-protection-for-your-organization-using-intune"></a>Verwalten des Manipulationsschutzes für Ihre Organisation mit Intune

Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind und Ihr Abonnement [Intune](/intune/fundamentals/what-is-intune)umfasst, können Sie den Manipulationsschutz für Ihre Organisation im Microsoft Endpoint Manager Admin Center ( ) aktivieren (oder [https://endpoint.microsoft.com](https://endpoint.microsoft.com) deaktivieren). Verwenden Sie Intune, wenn Sie Manipulationsschutzeinstellungen optimieren möchten. Wenn Sie beispielsweise den Manipulationsschutz auf einigen, aber nicht allen Geräten aktivieren möchten, verwenden Sie Intune.

### <a name="requirements-for-managing-tamper-protection-in-intune"></a>Anforderungen für die Verwaltung des Manipulationsschutzes in Intune

- Sie müssen über entsprechende [Berechtigungen](/microsoft-365/security/defender-endpoint/assign-portal-access)verfügen, z. B. globale Administratoren, Sicherheitsadministratoren oder Sicherheitsvorgänge.

- Ihre Organisation verwendet [Intune zum Verwalten von Geräten.](/intune/fundamentals/what-is-device-management) ([Intune-Lizenzen](/intune/fundamentals/licenses) sind erforderlich; Intune ist in Microsoft 365 E5 enthalten.)

- Ihre Windows Geräte müssen Windows 10 Betriebssystem [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019) oder höher ausgeführt werden. (Weitere Informationen zu Releases finden Sie [unter Windows 10 Versionsinformationen.)](/windows/release-health/release-information)

- Sie müssen Windows Sicherheit mit [Security Intelligence](https://www.microsoft.com/wdsi/definitions) verwenden, die auf Version 1.287.60.0 (oder höher) aktualisiert wurde.

- Ihre Geräte müssen die Antischadsoftwareplattform version 4.18.1906.3 (oder höher) und die Antischadsoftware-Modulversion 1.1.15500.X (oder höher) verwenden. ([Verwalten Microsoft Defender Antivirus Updates und Anwenden von Basisplänen.)](manage-updates-baselines-microsoft-defender-antivirus.md)

### <a name="turn-tamper-protection-on-or-off-in-intune"></a>Manipulationsschutz in Intune aktivieren (oder deaktivieren)

![Aktivieren des Manipulationsschutzes mit Intune](images/turnontamperprotect-MEM.png)

1. Wechseln Sie zum [Microsoft Endpoint Manager Admin Center,](https://endpoint.microsoft.com) und melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an.

2. Wählen Sie  >  **Gerätekonfigurationsprofile aus.**

3. Erstellen Sie ein Profil, das die folgenden Einstellungen enthält:
    - **Plattform: Windows 10 und höher**
    - **Profiltyp: Endpunktschutz**
    - **Kategorie: Microsoft Defender Security Center**
    - **Manipulationsschutz: Aktiviert**

4. Weisen Sie das Profil einer oder mehreren Gruppen zu.

### <a name="are-you-using-windows-os-1709-1803-or-1809"></a>Verwenden Sie Windows Betriebssystem 1709, 1803 oder 1809?

Wenn Sie Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803)oder [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)verwenden, wird der **Manipulationsschutz** in der Windows-Sicherheit-App nicht angezeigt. Stattdessen können Sie PowerShell verwenden, um zu bestimmen, ob der Manipulationsschutz aktiviert ist.

#### <a name="use-powershell-to-determine-whether-tamper-protection-is-turned-on"></a>Verwenden von PowerShell, um zu bestimmen, ob der Manipulationsschutz aktiviert ist

1. Öffnen Sie die Windows PowerShell-App.

2. Verwenden Sie das [PowerShell-Cmdlet "Get-MpComputerStatus".](/powershell/module/defender/get-mpcomputerstatus?preserve-view=true&view=win10-ps)

3. Suchen Sie in der Liste der Ergebnisse nach `IsTamperProtected` . (Der Wert *"true"* bedeutet, dass der Manipulationsschutz aktiviert ist.)

## <a name="manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006"></a>Verwalten des Manipulationsschutzes für Ihre Organisation mit Configuration Manager, Version 2006

Wenn Sie [Version 2006 von Configuration Manager](/mem/configmgr/core/plan-design/changes/whats-new-in-version-2006)verwenden, können Sie Manipulationsschutzeinstellungen auf Windows 10, Windows Server 2016 und Windows Server 2019 mithilfe einer Methode namens Tenant *Attach* verwalten. Die Mandantenanfügung ermöglicht es Ihnen, Ihre lokalen Configuration Manager-Geräte im Microsoft Endpoint Manager Admin Center zu synchronisieren und dann Endpunktsicherheitsrichtlinien für lokale Sammlungen & Geräte bereitzustellen.

:::image type="content" source="images/win-security- exp-policy-endpt-security.png" alt-text="Windows-Sicherheit in Endpoint Manager":::

> [!NOTE]
> Das Verfahren kann verwendet werden, um den Manipulationsschutz auf Geräte zu erweitern, auf denen Windows 10 und Windows Server 2019 ausgeführt wird. Überprüfen Sie die voraussetzungen und andere Informationen in den in diesem Verfahren erwähnten Ressourcen.

1. Einrichten von Mandantenanfügung. Weitere Informationen finden Sie [unter Microsoft Endpoint Manager Mandantenanfügung: Gerätesynchronisierung und Geräteaktionen.](/mem/configmgr/tenant-attach/device-sync-actions)

2. Wechseln [Sie](https://go.microsoft.com/fwlink/?linkid=2109431)im Microsoft Endpoint Manager Admin Center zu **Endpoint Security**  >  **Antivirus,** und wählen Sie dann **+ Richtlinie erstellen** aus.<br/> 
   - Wählen Sie in der **Plattformliste** **Windows 10 und Windows Server (ConfigMgr)** aus.  
   - Wählen Sie in der **Profilliste** **Windows-Sicherheit Erfahrung (Vorschau)** aus. <br/>

3. Stellen Sie die Richtlinie für Ihre Gerätesammlung bereit.

### <a name="need-help-with-this-method"></a>Benötigen Sie Hilfe bei dieser Methode? 

Informationen finden Sie in den folgenden Ressourcen:

- [Einstellungen für das Windows-Sicherheit-Erfahrungsprofil in Microsoft Intune](/mem/intune/protect/antivirus-security-experience-windows-settings)
- [Tech Community Blog: Ankündigung des Manipulationsschutzes für Configuration Manager Tenant Attach-Clients](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

## <a name="manage-tamper-protection-on-an-individual-device"></a>Verwalten des Manipulationsschutzes auf einem einzelnen Gerät

> [!NOTE]
> Der Manipulationsschutz blockiert Versuche, Microsoft Defender Antivirus Einstellungen über die Registrierung zu ändern.
>
> Um sicherzustellen, dass der Manipulationsschutz keine Konflikte mit Sicherheitsprodukten von Drittanbietern oder Unternehmensinstallationsskripts zur Änderung dieser Einstellungen verhindert, wechseln Sie zu **Windows-Sicherheit** und aktualisieren **Sie Security Intelligence** auf Version 1.287.60.0 oder höher. (Siehe [Security Intelligence-Updates.)](https://www.microsoft.com/wdsi/definitions)
>
> Nachdem Sie dieses Update vorgenommen haben, schützt der Manipulationsschutz weiterhin Ihre Registrierungseinstellungen und protokolliert Versuche, diese zu ändern, ohne Fehler zurückzugeben.

Wenn Sie ein Privatbenutzer sind oder nicht den von einem Sicherheitsteam verwalteten Einstellungen unterliegen, können Sie die Windows-Sicherheit-App verwenden, um den Manipulationsschutz zu verwalten. Sie müssen über die entsprechenden Administratorberechtigungen auf Ihrem Gerät verfügen, um Sicherheitseinstellungen wie Manipulationsschutz zu ändern.

In der Windows-Sicherheit-App sehen Sie Folgendes:

![In Windows 10 Home aktivierter Manipulationsschutz](images/tamperprotectionturnedon.png)

1. Wählen Sie **"Start"** aus, und beginnen Sie mit der Eingabe von *"Sicherheit".* Wählen Sie in den Suchergebnissen **Windows-Sicherheit** aus.

2. Wählen Sie Die Einstellungen **für viren- & Bedrohungsschutz**  >  **& Bedrohungsschutz** aus.

3. Legen Sie **den Manipulationsschutz** auf **"Ein"** oder **"Aus"** fest.

## <a name="view-information-about-tampering-attempts"></a>Anzeigen von Informationen zu Manipulationsversuchen

Manipulationsversuche deuten in der Regel auf größere Cyberangriffe hin. Schlechte Akteure versuchen, Sicherheitseinstellungen zu ändern, um zu speichern und nicht erkannt zu bleiben. Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie Informationen zu solchen Versuchen anzeigen und dann geeignete Maßnahmen ergreifen, um Bedrohungen zu mindern.

Wenn ein Manipulationsversuch erkannt wird, wird im [Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/portal-overview) ( ) eine Warnung [https://securitycenter.windows.com](https://securitycenter.windows.com) ausgelöst.

![Microsoft Defender Security Center](images/tamperattemptalert.png)

Mit [EDR](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) und [erweiterten Suchfunktionen](/microsoft-365/security/defender-endpoint/advanced-hunting-overview) in Microsoft Defender für Endpunkt kann Ihr Sicherheitsteam solche Versuche untersuchen und behandeln.

## <a name="review-your-security-recommendations"></a>Überprüfen Ihrer Sicherheitsempfehlungen

Der Manipulationsschutz lässt sich in die Funktionen [von Threat & Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) integrieren. [Sicherheitsempfehlungen](/microsoft-365/security/defender-endpoint/tvm-security-recommendation) umfassen das Sicherstellen, dass der Manipulationsschutz aktiviert ist. Sie können z. B. nach *Manipulationen* suchen, wie in der folgenden Abbildung dargestellt:

![Manipulationsschutz führt zu Sicherheitsempfehlungen](/images/securityrecs-tamperprotect.jpg)

In den Ergebnissen können Sie **"Manipulationsschutz aktivieren"** auswählen, um mehr zu erfahren und es zu aktivieren.

![Aktivieren des Manipulationsschutzes](images/tamperprotectsecurityrecos.png)

Weitere Informationen zur Bedrohungs- & Sicherheitsrisikoverwaltung finden Sie unter ["Bedrohungs- & Sicherheitsrisikoverwaltung" in Microsoft Defender Security Center.](/microsoft-365/security/defender-endpoint/tvm-dashboard-insights#threat--vulnerability-management-in-microsoft-defender-security-center)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="to-which-windows-os-versions-is-configuring-tamper-protection-is-applicable"></a>Für welche Windows Betriebssystemversionen die Konfiguration des Manipulationsschutzes gilt?

Windows 10 OS [1709](/windows/release-health/status-windows-10-1709), [1803](/windows/release-health/status-windows-10-1803), [1809](/windows/release-health/status-windows-10-1809-and-windows-server-2019)oder höher zusammen mit [Microsoft Defender für Endpunkt.](/microsoft-365/security/defender-endpoint)

Wenn Sie Configuration Manager, Version 2006, mit Mandantenanfügung verwenden, kann der Manipulationsschutz auf Windows Server 2019 erweitert werden. Siehe ["Mandantenanfügung: Erstellen und Bereitstellen einer Antivirusrichtlinie für Endpunktsicherheit" im Admin Center (Vorschau).](/mem/configmgr/tenant-attach/deploy-antivirus-policy)

### <a name="will-tamper-protection-have-any-impact-on-third-party-antivirus-registration"></a>Hat der Manipulationsschutz Auswirkungen auf die Antivirenregistrierung von Drittanbietern?

Nein. Antivirenangebote von Drittanbietern werden weiterhin bei der Windows-Sicherheit-Anwendung registriert.

### <a name="what-happens-if-microsoft-defender-antivirus-is-not-active-on-a-device"></a>Was geschieht, wenn Microsoft Defender Antivirus nicht auf einem Gerät aktiv ist?

Auf Geräten, die in Microsoft Defender für Endpunkt integriert sind, wird Microsoft Defender Antivirus im passiven Modus ausgeführt. Der Manipulationsschutz schützt weiterhin den Dienst und seine Features. 

### <a name="how-can-i-turn-tamper-protection-onoff"></a>Wie kann ich den Manipulationsschutz aktivieren/deaktivieren?

Wenn Sie ein Privatbenutzer sind, lesen [Sie "Verwalten des Manipulationsschutzes auf einem einzelnen Gerät".](#manage-tamper-protection-on-an-individual-device)

Wenn Sie eine Organisation sind, die [Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint)verwendet, sollten Sie in der Lage sein, den Manipulationsschutz in Intune ähnlich wie bei der Verwaltung anderer Endpunktschutzfeatures zu verwalten. Weitere Informationen finden Sie in den folgenden Abschnitten dieses Artikels: 

- [Verwalten des Manipulationsschutzes mit Intune](#manage-tamper-protection-for-your-organization-using-intune)
- [Verwalten des Manipulationsschutzes mit configuration Manager, Version 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Verwalten des Manipulationsschutzes mithilfe der Microsoft Defender Security Center](#manage-tamper-protection-for-your-organization-using-the-microsoft-defender-security-center) 

### <a name="how-does-configuring-tamper-protection-in-intune-affect-how-i-manage-microsoft-defender-antivirus-through-my-group-policy"></a>Wie wirkt sich die Konfiguration des Manipulationsschutzes in Intune darauf aus, wie ich Microsoft Defender Antivirus über meine Gruppenrichtlinie verwalte?

Ihre reguläre Gruppenrichtlinie gilt nicht für den Manipulationsschutz, und Änderungen an Microsoft Defender Antivirus Einstellungen werden ignoriert, wenn der Manipulationsschutz aktiviert ist. 

### <a name="for-microsoft-defender-for-endpoint-is-configuring-tamper-protection-in-intune-targeted-to-the-entire-organization-only"></a>Konfigurieren Sie für Microsoft Defender für Endpunkt den Manipulationsschutz in Intune nur für die gesamte Organisation?

Die Konfiguration des Manipulationsschutzes in Intune oder Microsoft Endpoint Manager kann auf Ihre gesamte Organisation sowie auf bestimmte Geräte und Benutzergruppen ausgerichtet sein.

### <a name="can-i-configure-tamper-protection-in-microsoft-endpoint-configuration-manager"></a>Kann ich den Manipulationsschutz in Microsoft Endpoint Configuration Manager konfigurieren?

Wenn Sie Tenant Attach verwenden, können Sie Microsoft Endpoint Configuration Manager verwenden. Informationen finden Sie in den folgenden Ressourcen:
- [Verwalten des Manipulationsschutzes für Ihre Organisation mit Configuration Manager, Version 2006](#manage-tamper-protection-for-your-organization-with-configuration-manager-version-2006)
- [Tech Community Blog: Ankündigung des Manipulationsschutzes für Configuration Manager Tenant Attach-Clients](https://techcommunity.microsoft.com/t5/microsoft-endpoint-manager-blog/announcing-tamper-protection-for-configuration-manager-tenant/ba-p/1700246#.X3QLR5Ziqq8.linkedin)

### <a name="i-have-the-windows-e3-enrollment-can-i-use-configuring-tamper-protection-in-intune"></a>Ich habe die Windows E3-Registrierung. Kann ich den Manipulationsschutz in Intune konfigurieren?

Derzeit ist die Konfiguration des Manipulationsschutzes in Intune nur für Kunden verfügbar, die [Über Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint)verfügen.

### <a name="what-happens-if-i-try-to-change-microsoft-defender-for-endpoint-settings-in-intune-microsoft-endpoint-configuration-manager-and-windows-management-instrumentation-when-tamper-protection-is-enabled-on-a-device"></a>Was geschieht, wenn ich versuche, die Microsoft Defender für Endpunkt-Einstellungen in Intune, Microsoft Endpoint Configuration Manager und Windows-Verwaltungsinstrumentation zu ändern, wenn der Manipulationsschutz auf einem Gerät aktiviert ist?

Sie können die Features, die durch Manipulationsschutz geschützt sind, nicht ändern. solche Änderungsanforderungen werden ignoriert.

### <a name="im-an-enterprise-customer-can-local-admins-change-tamper-protection-on-their-devices"></a>Ich bin ein Enterprise-Kunde. Können lokale Administratoren den Manipulationsschutz auf ihren Geräten ändern?

Nein. Lokale Administratoren können die Einstellungen für den Manipulationsschutz nicht ändern oder ändern.

### <a name="what-happens-if-my-device-is-onboarded-with-microsoft-defender-for-endpoint-and-then-goes-into-an-off-boarded-state"></a>Was geschieht, wenn mein Gerät in Microsoft Defender für Endpunkt integriert ist und dann in einen off-boarded-Zustand wechselt?

Wenn ein Gerät aus Microsoft Defender für Endpunkt aus dem Board entfernt ist, ist der Manipulationsschutz aktiviert, was der Standardzustand für nicht verwaltete Geräte ist. 

### <a name="will-there-be-an-alert-about-tamper-protection-status-changing-in-the-microsoft-defender-security-center"></a>Wird eine Warnung zum Status des Manipulationsschutzes im Microsoft Defender Security Center angezeigt?

Ja. Die Warnung wird [https://securitycenter.microsoft.com](https://securitycenter.microsoft.com) unter **Warnungen** angezeigt.

Ihr Sicherheitsteam kann auch Suchabfragen verwenden, z. B. das folgende Beispiel:

`DeviceAlertEvents | where Title == "Tamper Protection bypass"`

[Anzeigen von Informationen zu Manipulationsversuchen.](#view-information-about-tampering-attempts)

## <a name="see-also"></a>Siehe auch

[Schützen Windows PCs mit Endpoint Protection für Microsoft Intune](/intune/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)

[Übersicht über Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint)

[Noch besser zusammen: Microsoft Defender Antivirus und Microsoft Defender für Endpunkt](why-use-microsoft-defender-antivirus.md)