---
title: Windows 10 Enterprise-Infrastruktur für Microsoft 365 Enterprise
description: Bietet eine ausführliche Anleitung zu den einzelnen Schritten, die im Rahmen von Microsoft 365 Enterprise für die Bereitstellung von Windows 10 Enterprise auf PCs nötig sind.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365-Dokumentation, Windows 10 Enterprise, Bereitstellung
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 88517c6b8de95c54ee9a2e47d4545266eb198249
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289435"
---
# <a name="phase-3-windows-10-enterprise"></a>Phase 3: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise umfasst Windows 10 Enterprise, mit denen Sie mehr tun und sicher bleiben können. Windows 10 Enterprise:

- **Ist für die Einfachheit integriert** – nutzen Sie die Leistungsfähigkeit der Cloud, um die Komplexität der modernen IT-Geräteumgebung zu reduzieren, unabhängig von der Größe.
- **Intelligente Sicherheit** – es ist die sicherste Windows-Freigabe mit intelligenten Sicherheitsfunktionen, die zusammenarbeiten, um Ihre Organisation besser zu schützen.
- **Ermöglicht Kreativität und Teamarbeit** – entsperrt Kreativität und Teamarbeit, um die produktivste Erfahrung bereitzustellen, die sowohl Benutzer als auch Sie lieben werden.

Sie müssen die verschiedenen Möglichkeiten kennen, wie Sie das Windows 10-Betriebssystem bereitstellen können, und die richtige für Ihre Organisation auswählen. Je nach Microsoft 365 Enterprise-Abonnement gibt es auch Windows 10-Dienste und Sicherheitsfeatures, die Sie konfigurieren müssen, um Windows 10 optimal nutzen zu können.

Windows 10 ermöglicht die folgenden strategischen Geschäftsszenarien für Microsoft 365 Enterprise:

- Optimale Nutzung von kollektivem Wissen und Fachkenntnissen, indem Mitarbeiter die Möglichkeit erhalten, Dateien, Informationen und Ideen in Ihrer Organisation zu ermitteln, freizugeben und weiterzuentwickeln.
- Sicheres Arbeiten überall und jederzeit von Ihrem Gerät aus, um bei einem flexiblen Arbeitsstil produktiver zu arbeiten
- Beruhigendes Gefühl dank Steuerungen und Sichtbarkeit für branchengeprüfte Konformität mit globalen Standards
- Schützen Ihrer Informationen und Reduzierung des Risikos von Datenverlusten
- Ermittlung und Schutz vor externen Bedrohungen – Überwachung, Bericht und Analyse der Aktivität, um die Sicherheit der Organisation zu gewährleisten
- Schützen der Benutzer und ihrer Konten
- Unterstützen Ihrer Organisation mit verbessertem Datenschutz und Compliance, um die Datenschutz-Grundverordnung (DSGVO) zu erfüllen
- Auf dem Laufenden bleiben im Zusammenhang mit Desktopsoftware und Geräten, während gleichzeitig Sicherheitsrisiken minimiert und die IT-Effizienz erhöht werden

Weitere Informationen finden Sie unter [Digitale Transformation mit Microsoft 365](http://transform.microsoft.com). 

>[!Note]
>Um Windows 10 Enterprise und Office 365 ProPlus zusammen zu erstellen und auf einen [modernen Desktop](https://www.microsoft.com/microsoft-365/modern-desktop) umzusteigen, gehen Sie zum [Bereitstellungscenter für modernen Desktop](http://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Windows 10-Bereitstellung

Es gibt mehrere Möglichkeiten, um Windows 10 Enterprise für Ihre Organisation bereitzustellen. Hier konzentrieren wir uns auf die Konfiguration und Bereitstellungeines Windows 10 Enterprise-Images mithilfe dieser modernen Bereitstellungsszenarien.

| Bereitstellungsszenario | Zeitpunkt der Verwendung |
|:--- |:--- |
| [Verwenden von System Center Configuration Manager als direktes Upgrade](windows10-deploy-inplaceupgrade.md) | Wählen Sie diese Option aus, wenn Sie Windows 7-oder Windows 8,1-Computer auf die <a href="https://aka.ms/windows-10-release-information" target="_blank">aktuelle Version</a> von Windows 10 Enterprise aktualisieren müssen und ihre Computer derzeit mit <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current Branch)</a>verwaltet werden. |
| [Verwenden von Windows Autopilot](windows10-deploy-autopilot.md) | Wählen Sie diese Option aus, wenn Sie neue Windows-Computer mit Windows 10 Enterprise, Version 1703 oder höher vorinstalliert einrichten. Endbenutzer initiieren Setup mithilfe der gewünschten Konfiguration, indem Sie die Anmeldeinformationen Ihres Geschäfts-oder Schul Kontos eingeben. |

Wenn diese Bereitstellungsszenarien nicht den Anforderungen Ihrer Organisation entsprechen, können Sie sich über andere Szenarien informieren und die Funktionen und Einschränkungen jeder in [Windows 10-Bereitstellungsszenarien](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)verstehen. Sie können die <a href="https://aka.ms/planforwin10deployment" target="_blank">Bereitstellung von Windows 10</a> auch selbst planen.

Weitere Informationen zu Windows 10 finden Sie in den folgenden Artikeln:

- [Microsoft 365 Enterprise product page (Microsoft 365 Enterprise-Produktseite)](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Bereitstellen und Aktualisieren von Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Zusätzliche Dienste und Features
Im Rahmen der Bereitstellung von Windows 10 Enterprise können Sie diese zusätzlichen Dienste und Features hinzufügen.

### <a name="windows-analytics"></a>Windows Analytics

Windows verwendet Diagnosedaten, um umfangreiche, umsetzbare Informationen bereitzustellen, mit denen Sie Tiefe Einblicke in die Betriebseffizienz und die Integrität von Windows 10-Geräten in Ihrer Umgebung erhalten.

* Upgrade-Bereitschaft-Upgrade-Bereitschaft hilft Ihnen beim Wechseln zu Windows 10 und bei neuen Windows 10-Feature-Updates. 
* Update Compliance-Update Compliance ist für IT-Administratoren gedacht, die eine ganzheitliche Ansicht aller Windows 10-Geräte ohne zusätzliche Infrastrukturanforderungen erhalten möchten.
* Geräte Integrität: Sie können die Geräte Integrität verwenden, um die Auswirkungen auf die Endbenutzer proaktiv zu erfassen und zu beheben.

Weitere Informationen finden Sie unter [Übersicht über Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .

### <a name="windows-security"></a>Windows-Sicherheit

Windows 10 bietet Funktionen zum Schutz vor Bedrohungen, zur Sicherung Ihrer Geräte und zur Hilfe bei der Zugriffssteuerung. Mit Windows 10 erhalten Sie wichtige Sicherheitsfunktionen, die Ihr Gerät von Anfang an schützen. Microsoft 365 E3 fügt Sicherheitsfeatures wie Windows Hello for Business, Windows Defender-Anwendungssteuerung und Windows Information Protection hinzu. Mit Microsoft 365 E5 erhalten Sie den Schutz vor Microsoft 365 E3 Security Plus Cloud-basierte Sicherheitsfunktionen und Windows Defender Advanced Threat Protection. 

Weitere Informationen zu den Sicherheitsfeatures, die Sie mit Windows 10 Enterprise erhalten, und Anleitungen zur Bereitstellung, Verwaltung, Konfiguration und Problembehandlung von drei wichtigen ecurity-Features finden Sie unter [Schritt 5: Deploy Windows 10 Enterprise Security Features](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Informationen zur Planung und Bereitstellung von Updates für Windows 10 finden Sie unter:

- [Vorbereiten Ihrer Organisation für eine nahtlose Bereitstellung von Windows 10](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Einführung von Windows als Dienst bei Microsoft](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Bereitstellung von Windows 10 bei Microsoft als direktes Upgrade](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implementieren einer strengen Benutzerauthentifizierung mit Windows Hello for Business](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Bereitstellung von Windows 10: Tipps und Tricks von der Microsoft-IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (Video)
- [Windows Defender ATP hilft bei der Erkennung ausgeklügelter Bedrohungen](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Schützen des modernen Unternehmens mit Windows Defender und Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (Video)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Sehen Sie sich an, wie die Contoso Corporation, ein fiktives, aber repräsentatives Multi-nationales Unternehmen, [Windows 10 Enterprise bereitgestellt](contoso-win10.md)hat.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Vorbereiten Ihrer Organisation auf Windows 10 Enterprise](windows10-prepare-your-org.md) |
