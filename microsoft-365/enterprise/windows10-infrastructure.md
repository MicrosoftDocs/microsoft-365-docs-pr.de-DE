---
title: Windows-10-Enterprise-Infrastruktur für Microsoft 365 Enterprise.
description: Bietet eine ausführliche Anleitung zu den einzelnen Schritten, die im Rahmen von Microsoft 365 Enterprise für die Bereitstellung von Windows 10 Enterprise auf PCs nötig sind.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Windows 10 Enterprise, Bereitstellung
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867563"
---
# <a name="phase-3-windows-10-enterprise"></a>Phase 3: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise enthält Windows 10 Enterprise, die Sie haben die Tools zur mehr und Sicherheit. Windows 10 Enterprise:

- **Ist der Einfachheit integriert** - Umgebung die Leistungsfähigkeit der Cloud zur Reduzierung die Komplexität der Verwaltung von heute's modernen IT-Geräte-Umgebung, unabhängig davon, die Größe.
- **Intelligente Sicherheit** - es ist die sicherste Version von Windows jemals, Funktionen, die entworfen wurden, um eine bessere Zusammenarbeit schützen mit intelligenten Sicherheit Ihrer Organisation.
- Hebt die Sperre **ermöglicht Kreativität und Zusammenarbeit** - Kreativität und Zusammenarbeit produktiv übermitteln auftreten, die Benutzer und Liebe wird die IT.

Sie müssen die verschiedenen Verfahren können Sie das Betriebssystem Windows 10 bereitstellen und wählen Sie die richtige Datei für Ihre Organisation zu verstehen. Je nach Ihrer Microsoft 365 Enterprise-Abonnement gibt es auch Windows 10 Dienste und Features, die Sie benötigen, um Windows 10 optimal konfigurieren.

Windows 10 wird diese strategischen Geschäftsszenarien für Microsoft 365 Enterprise aktiviert:

- Optimale Nutzung von kollektivem Wissen und Fachkenntnissen, indem Mitarbeiter die Möglichkeit erhalten, Dateien, Informationen und Ideen in Ihrer Organisation zu ermitteln, freizugeben und weiterzuentwickeln.
- Sicheres Arbeiten überall und jederzeit von Ihrem Gerät aus, um bei einem flexiblen Arbeitsstil produktiver zu arbeiten
- Beruhigendes Gefühl dank Steuerungen und Sichtbarkeit für branchengeprüfte Konformität mit globalen Standards
- Schützen Ihrer Informationen und Reduzierung des Risikos von Datenverlusten
- Erkennen und Schutz gegen externe Bedrohungen--Monitor Bericht und Analysieren der Aktivität, um umgehend reagieren, um die Sicherheit in der Organisation bereitstellen
- Schützen Sie Ihre Benutzer und ihre Konten
- Unterstützen Ihrer Organisation mit verbessertem Datenschutz und Compliance, um die Datenschutz-Grundverordnung (DSGVO) zu erfüllen
- Auf dem Laufenden bleiben im Zusammenhang mit Desktopsoftware und Geräten, während gleichzeitig Sicherheitsrisiken minimiert und die IT-Effizienz erhöht werden

Weitere Informationen finden Sie unter [Digitale Transformation mit Microsoft 365](http://transform.microsoft.com). 

>[!Note]
>Um Windows 10 Enterprise und Office 365 ProPlus zusammen zu erstellen und auf einen [modernen Desktop](https://www.microsoft.com/microsoft-365/modern-desktop) umzusteigen, gehen Sie zum [Bereitstellungscenter für modernen Desktop](http://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Windows-10-Bereitstellung

Es gibt mehrere Möglichkeiten, die Sie für Ihre Organisation Windows 10 Enterprise bereitstellen können. Hier konzentrieren wir uns auf wie konfigurieren und Bereitstellen einer Windows 10 Enterprise Images über diesen modernen Bereitstellungsszenarien werden können.

| Bereitstellungsszenario | Einsatz |
|:--- |:--- |
| [Verwenden von System Center Configuration Manager als ein direktes upgrade](windows10-deploy-inplaceupgrade.md) | Wählen Sie diese Option, wenn Sie Aktualisieren von Windows 7 müssen oder Windows 8.1 auf die <a href="https://aka.ms/windows-10-release-information" target="_blank">aktuelle Version</a> von Windows 10 Enterprise und Ihre Computern werden derzeit mit <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (aktuelle Zweig)</a>verwaltet. |
| [Verwenden von Windows Autopilot](windows10-deploy-autopilot.md) | Wählen Sie diese Option, wenn Sie neue Windows-Computer einrichten, die Windows 10 Enterprise, Version 1703 oder höher bereits installiert haben. Endbenutzer wird initiiert Setup mit der gewünschten Konfiguration, indem Sie ihre Arbeit eingeben oder Schule Kontoanmeldeinformationen. |

Wenn diese Bereitstellungsszenarien nicht die Anforderungen Ihrer Organisation passen, können Sie erfahren Sie mehr über andere Szenarien und Grundlegendes zu den Funktionen und Beschränkungen jedes Computers in [Windows 10 Bereitstellungsszenarien](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). Sie können auch <a href="https://aka.ms/planforwin10deployment" target="_blank">Planen der Bereitstellung von Windows 10</a> selbst.

Mit diesen Artikeln erfahren Sie mehr über Windows 10:

- [Microsoft 365 Enterprise product page (Microsoft 365 Enterprise-Produktseite)](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Bereitstellen und Aktualisieren von Windows-10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Zusätzliche Dienste und features
Im Rahmen der Bereitstellung von Windows 10 Enterprise können Sie diese zusätzliche Dienste und Features hinzufügen.

### <a name="windows-analytics"></a>Windows Analytics

Windows verwendet Diagnosedaten anzugebende umfangreiche, bearbeitungsfähige hilfreiche Informationen zum Tiefe Einblicke in die Betriebseffizienz und die Integrität der Windows-10-Geräte in Ihrer Umgebung zu erhalten.

* Aktualisieren Sie die Bereitschaft - Upgradebereitschaft helfen Ihnen beim Verschieben in Windows 10 und ständig mit neuen Windows 10 Feature-Updates. 
* Update Compliance - Kompatibilität ist auf der IT-Administrator abgestimmt, möchte einen ganzheitlichen aller ihrer Windows 10 Geräte, ohne die zusätzliche infrastrukturanforderungen zu erhalten.
* Gerät Health - können Sie Geräte Health proaktiv erkennen und Beheben von Problemen, Endbenutzer störenden verwenden.

Weitere Informationen finden Sie unter [Übersicht über die Windows-Analyse](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .

### <a name="windows-security"></a>Windows-Sicherheit

Windows-10 bietet Features zum Schutz gegen Bedrohungen, Hilfe Sie schützen Ihrer Geräte und Hilfe zur Steuerung des Zugriffs. Mit Windows 10 erhalten Sie wichtige Sicherheitsfeatures, die Ihr Gerät rechts vom Anfang zu schützen. Microsoft 365 E3 fügt Sicherheitsfeatures wie Windows Hello für Unternehmen, Windows Defender Anwendung Steuerelement und Windows Information Protection. Mit Microsoft 365 E5 erhalten Sie alle den Schutz von Microsoft 365 E3 Sicherheit plus Cloud-basierten Sicherheitsfunktionen und Windows Defender erweiterte Threat Protection. 

Weitere Informationen zu den Sicherheitsfeatures finden, die Sie mit Windows 10 Enterprise und Get-Anleitungen auf wie Sie können bereitstellen, verwalten, konfigurieren und Problembehandlung bei drei wichtige Ecurity Funktionen erhalten möchten, finden Sie unter [Schritt 5: Bereitstellen von Windows 10 Enterprise Sicherheitsfeatures](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Um Microsoft verkürzt, und erfahren, wie das Unternehmen geplant, bereitgestellt und ist Verwalten von Updates für Windows 10, finden Sie unter:

- [Vorbereiten Ihrer Organisation für eine nahtlose Bereitstellung von Windows 10](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Einführung von Windows als Dienst bei Microsoft](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Bereitstellung von Windows 10 bei Microsoft als direktes Upgrade](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implementieren einer strengen Benutzerauthentifizierung mit Windows Hello for Business](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Bereitstellung von Windows 10: Tipps und Tricks von der Microsoft-IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (Video)
- [Windows Defender ATP hilft bei der Erkennung ausgeklügelter Bedrohungen](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Schützen des modernen Unternehmens mit Windows Defender und Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (Video)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Finden Sie unter wie der Contoso Corporation, ein fiktives aber repräsentative multinationale Unternehmen, [Windows 10 Enterprise bereitgestellt](contoso-win10.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Vorbereiten Ihrer Organisation auf Windows 10 Enterprise](windows10-prepare-your-org.md) |
