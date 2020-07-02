---
title: 'Schritt 4: Konfigurieren von Windows Information Protection'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Bereitstellen von Windows Information Protection in Microsoft 365.
ms.openlocfilehash: c7b76ef28d41810d6e9e45e98adb7a94cf8ae2f4
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005722"
---
# <a name="step-4-configure-windows-information-protection"></a>Schritt 4: Konfigurieren von Windows Information Protection

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![Phase 6: Schutz von Daten](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Da immer mehr persönliche Geräte für Arbeitszwecke verwendet werden, steigt das Risiko, dass Apps und Geräte private Unternehmensdaten preisgeben. Ein Mitarbeiter sendet beispielsweise versehentlich ein Bild eines Marketingplans für ein künftiges Produkt an eine Website für soziale Medien oder speichert eine Datei mit vertraulichen Informationen in seinem öffentlichen Cloudspeicher. 

Windows Information Protection (WIP) bietet Schutz vor dieser Art von Datenlecks auf Windows 10-Geräten. Weitere Informationen finden Sie unter [Schutz Ihrer Unternehmensdaten mit WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

In Microsoft 365 Enterprise ist WIP eine Kombination von Windows 10 Enterprise und Microsoft Intune, das in Ihrem Abonnement enthalten ist. 

Gehen Sie folgendermaßen vor, um WIP in Ihrer Organisation mit Microsoft 365 Enterprise bereitzustellen:

1. Registrieren Sie Ihre Windows-Geräte in Intune. Sie hätten dies in [Phase 5: Verwaltung mobiler Geräte](mobility-infrastructure.md) tun sollen.

2. Erstellen Sie eine [Intune-Richtlinie für WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).

   -    Stellen Sie sicher, dass Sie Liste mit geschützten Apps ausgefüllt haben.
  
   - Wählen Sie Ihre WIP-Schutzebene aus.

Sie können WIP auch mit dem [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-configmgr) verwenden. 

Weitere Informationen finden Sie unter [Bewährte Methoden für WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).

Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step4) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![Schritt 5](../media/stepnumbers/Step5.png)|[Konfigurieren der Verhinderung von Datenverlust](infoprotect-data-loss-prevention.md)|


