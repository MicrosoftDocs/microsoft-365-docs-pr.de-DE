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
ms.date: 08/28/2019
ms.author: greglin
ms.openlocfilehash: 147dd0ec0276d685177ae389092ec18ace0d7bed
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831688"
---
# <a name="phase-3-windows-10-enterprise"></a>Phase 3: Windows 10 Enterprise

![Phase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise umfasst Windows 10 Enterprise, das Ihnen die Tools bietet, um mehr zu tun und sicher zu bleiben. Windows 10 Enterprise:

- **Ist zur Vereinfachung integriert** – nutzen Sie die Leistungsfähigkeit der Cloud, um die Komplexität der modernen IT-Geräteumgebung, unabhängig von der Größe, zu reduzieren.
- **Verfügt über eine intelligente Sicherheit** , die die sicherste Version von Windows überhaupt ist, mit intelligenten Sicherheitsfunktionen, die zusammenarbeiten, um Ihre Organisation besser zu schützen.
- **Ermöglicht Kreativität und Teamarbeit** – entsperrt Kreativität und Teamarbeit, um die produktivste Erfahrung zu liefern, die die Benutzer und die IT lieben werden.

Sie müssen die verschiedenen Möglichkeiten kennen, wie Sie das Betriebssystem Windows 10 bereitstellen und das richtige für Ihre Organisation auswählen können. Je nach Ihrem Microsoft 365 Enterprise-Abonnement gibt es auch Windows 10-Dienste und Sicherheitsfeatures, die Sie konfigurieren müssen, um Windows 10 optimal nutzen zu können.

>[!Note]
>Um Windows 10 Enterprise und Office 365 ProPlus zusammen zu erstellen und auf einen [modernen Desktop](https://www.microsoft.com/microsoft-365/modern-desktop) umzusteigen, gehen Sie zum [Bereitstellungscenter für modernen Desktop](https://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Windows 10-Bereitstellung

Es gibt mehrere Möglichkeiten, wie Sie Windows 10 Enterprise für Ihre Organisation bereitstellen können. Hier konzentrieren wir uns darauf, wie Sie ein Windows 10 Enterprise-Image über diese modernen Bereitstellungsszenarien konfigurieren und bereitstellen können.

| Bereitstellungsszenario | Verwendungszweck |
|:--- |:--- |
| [Verwenden von Microsoft Endpoint Configuration Manager als direktes Upgrade](windows10-deploy-inplaceupgrade.md) | Wählen Sie diese Option aus, wenn Sie Windows 7 oder Windows 8.1 Computer auf die <a href="https://aka.ms/windows-10-release-information" target="_blank">aktuelle Version</a> von Windows 10 Enterprise aktualisieren müssen und ihre Computer derzeit mit <a href="https://aka.ms/introtosccm" target="_blank">Configuration Manager (Current Branch)</a>verwaltet werden. |
| [Verwenden von Windows Autopilot](windows10-deploy-autopilot.md) | Wählen Sie diese Option aus, wenn Sie neue Windows-Computer einrichten, auf denen Windows 10 Enterprise, Version 1703 oder höher, bereits vorinstalliert ist. Endbenutzer initiieren das Setup mithilfe Ihrer gewünschten Konfiguration, indem Sie die Anmeldeinformationen für Ihr Büro oder Ihr Schulkonto eingeben. |

Wenn diese Bereitstellungsszenarien nicht den Anforderungen Ihrer Organisation entsprechen, können Sie sich über andere Szenarien informieren und die Möglichkeiten und Einschränkungen der einzelnen [Windows 10-Bereitstellungsszenarien](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)kennen. Sie können <a href="https://aka.ms/planforwin10deployment" target="_blank">die Bereitstellung von Windows 10 auch selbst planen</a>.

Weitere Informationen zu Windows 10 finden Sie in den folgenden Artikeln:

- [Microsoft 365 Enterprise product page (Microsoft 365 Enterprise-Produktseite)](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Bereitstellen und Aktualisieren von Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Zusätzliche Dienste und Features
Im Rahmen der Bereitstellung von Windows 10 Enterprise können Sie diese zusätzlichen Dienste und Features hinzufügen.

### <a name="windows-analytics"></a>Windows Analytics

Windows verwendet Diagnosedaten, um umfangreiche, umsetzbare Informationen bereitzustellen, mit denen Sie Tiefe Einblicke in die betriebliche Effizienz und die Integrität von Windows 10-Geräten in Ihrer Umgebung erhalten.

* Update Bereitschaft – die Bereitschaft zur Aktualisierung hilft Ihnen, zu Windows 10 zu wechseln und mit neuen Windows 10-Feature-Updates auf dem neuesten Stand zu bleiben. 
* Update Compliance – Update Compliance richtet sich an den IT-Administrator, der eine ganzheitliche Ansicht aller Windows 10-Geräte ohne zusätzliche Infrastrukturanforderungen erhalten möchte.
* Geräte Integrität: Sie können die Geräte Integrität verwenden, um Auswirkungen auf Endbenutzer Probleme proaktiv zu erkennen und zu beheben.

Weitere Informationen finden Sie unter [Übersicht über Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .

### <a name="windows-security"></a>Windows-Sicherheit

Windows 10 bietet Funktionen zum Schutz vor Bedrohungen, zur Sicherung Ihrer Geräte und zur Hilfe bei der Zugriffssteuerung. Mit Windows 10 erhalten Sie wichtige Sicherheitsfeatures, die Ihr Gerät von Anfang an schützen. Microsoft 365 E3 fügt Sicherheitsfeatures wie Windows Hello for Business, Windows Defender Application Control und Windows Information Protection hinzu. Mit Microsoft 365 E5 erhalten Sie den gesamten Schutz vor Microsoft 365 E3 Security Plus Cloud-basierten Sicherheitsfeatures und Microsoft Defender Advanced Threat Protection. 

Weitere Informationen zu den Sicherheitsfeatures, die Sie mit Windows 10 Enterprise erhalten, finden Sie unter [Schritt 5: Bereitstellen von Windows 10 Enterprise-Sicherheits](windows10-enable-security-features.md)Features, um die Bereitstellung, Verwaltung, Konfiguration und Problembehandlung für drei wichtige Sicherheitsfeatures zu erhalten.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Werfen Sie einen Blick in Microsoft, und erfahren Sie, wie das Unternehmen [Windows 10 Enterprise bereitgestellt hat und die starke Authentifizierung, InTune und Microsoft Defender ATP verwendet](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Sehen Sie sich an, wie die Contoso Corporation, ein fiktives, aber repräsentatives multinationales Unternehmen, [Windows 10 Enterprise bereitgestellt](contoso-win10.md)hat.

![Die Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 1](./media/stepnumbers/Step1.png)| [Vorbereiten Ihrer Organisation auf Windows 10 Enterprise](windows10-prepare-your-org.md) |
