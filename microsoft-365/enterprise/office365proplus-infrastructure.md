---
title: 'Phase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Die Schritte zur Bereitstellung der Office 365 Pro Plus-Infrastruktur für Microsoft 365 Enterprise.
ms.openlocfilehash: f20435edc4cdc675d0308774eb493a67723054f4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982766"
---
# <a name="phase-4-office-365-proplus"></a>Phase 4: Office 365 ProPlus

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Dies gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise und Microsoft 365 Education.*

Microsoft 365 Enterprise enthält Office 365 ProPlus, die Abonnementversion von Office. Wie Office 2016 umfasst Office 365 ProPlus alle Office-Anwendungen, und diese Anwendungen sind direkt auf Ihren Clientgeräten installiert sind. Im Gegensatz zu Office 2016 wird Office 365 ProPlus regelmäßig um neue Features erweitert und verfügt über ein benutzerbasiertes Lizenzierungsmodell, mit dem Benutzer Office auf bis zu 5 Geräten installieren können. Weitere Informationen finden Sie unter [Informationen zu Office 365 ProPlus im Unternehmen](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

In dieser Phase stellen Sie Office 365 ProPlus auf Clientgeräten im Rahmen von Microsoft 365 Enterprise bereit. Zusätzlich zu dieser Anleitung empfehlen wir die Verwendung von [Microsoft Fastrack](https://fasttrack.microsoft.com/office) bei der Bereitstellung. 

Wenn Sie bereits Office 365 ProPlus bereitgestellt haben, lesen Sie bitte den Abschnitt zu den [Beendigungskriterien](office365proplus-exit-criteria.md) für diese Phase, um sicherzustellen, dass sie die erforderlichen Kriterien für Microsoft 365 Enterprise erfüllen.

>[!Note]
>Weitere Informationen, um Windows 10 Enterprise und Office 365 ProPlus zusammen zu erstellen, finden Sie unter [Bereitstellungscenter für Desktop](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Schritt 1: Bewerten der Umgebung

Befolgen Sie vor der Bereitstellung von Office 365 ProPlus die Anleitungen unter [Bewerten der Umgebung und Anforderungen für die Bereitstellung von Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). Diese Bewertung umfasst die Systemanforderungen, Details zu Ihren Clientgeräten (z. B. Architekturen und erforderliche Sprachen), Lizenzen, Netzwerkfunktion und Anwendungskompatibilität. Das Abschließen der Bewertung unterstützt Sie bei grundlegender Entscheidungsfindung im Rahmen der Planung Ihrer Bereitstellung.

## <a name="step-2-plan-your-deployment"></a>Schritt 2: Planen der Bereitstellung

Befolgen Sie nach dem Bewerten der Umgebung die Anleitungen unter [Planen der Bereitstellung von Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) zum Erstellen eines Bereitstellungsplans. Dieser Plan enthält die folgenden Entscheidungen: 

- Bereitstellen von Office, darunter das zu verwendende Tool (z. B. System Center Configuration Manager oder Office-Bereitstellungstool) und Ort der Installation von Office
- Verwalten von Updates für Office
- Zu verwendende Updatekanäle (Updatekanäle für Office steuern, wie häufig die Benutzer Updates von Funktionen in ihren Office-Anwendungen erhalten)
- Zu verwendende Office-Installationspakete und -Bereitstellungsgruppen, darunter die zu installierenden Office-Anwendungen und Sprachen für Benutzer

Der Artikel zum [Planen](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) enthält die bewährten Methoden für alle diese Optionen, darunter die Verwaltung der Bereitstellung, Verwaltung der Updates, Definition der Installationspakete und Erstellung von Bereitstellungsgruppen. 

## <a name="step-3-deploy"></a>Schritt 3: Bereitstellen

Wählen Sie basierend auf Ihrem Bereitstellungsplan aus Schritt 2 die Methode für die Bereitstellung aus:

- **[Bereitstellen von Office 365 ProPlus mithilfe von System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Verwalten der Bereitstellung mit Configuration Manager und Herunterladen und Bereitstellen von Office über Verteilungspunkte im Netzwerk

- **[Bereitstellen von Office 365 ProPlus mit dem Office-Bereitstellungstool aus der Cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Verwalten der Bereitstellung mit dem Office-Bereitstellungstool und direktes Installieren von Office über das Office-CDN auf Clientgeräten
 
- **[Bereitstellen von Office 365 ProPlus mit dem Office-Bereitstellungstool aus einer lokalen Datenquelle](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** Verwalten der Bereitstellung mit dem Office-Bereitstellungstool und Herunterladen und Bereitstellen von Office über eine lokale Datenquelle im Netzwerk 

- **[Installieren von Office 365 ProPlus über das Office-Portal](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** Verwalten der Bereitstellung im Office-Portal und direktes Installieren von Office auf Clientgeräten über das Portal durch Benutzer

Viele Organisationen verwenden für unterschiedliche Benutzer eine Kombination aus diesen Optionen. Eine Organisation kann z. B. Configuration Manager verwenden, um Office für die meisten Benutzer bereitzustellen, einer kleinen Gruppe von Mitarbeitern, die nicht häufig mit dem internen Netzwerk verbunden sind, jedoch ermöglichen, Office selbst zu installieren. 

Wenn Ihre Organisation Configuration Manager verwendet, wird empfohlen, ein Upgrade auf Current Branch durchzuführen und auf die aktuelle Version zu aktualisieren. Weitere Informationen finden Sie unter [Welchen Branch von Configuration Manager sollte ich verwenden?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Funktionsweise von Microsoft 365 Enterprise bei Microsoft

Erfahren Sie, wie die Experten bei Microsoft [Updates für Office 365 ProPlus bereitstellen und verwalten](https://www.microsoft.com/de-DE/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Wie Microsoft 365 Enterprise bei Contoso eingesetzt wird

Erfahren Sie, wie die Contoso Corporation, ein fiktives, aber multinationales, repräsentatives Unternehmen [Office 365 ProPlus bereitgestellt hat](contoso-o365pp.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Nächster Schritt

[Beendigungskriterien für die Office 365 ProPlus-Infrastruktur](office365proplus-exit-criteria.md)
