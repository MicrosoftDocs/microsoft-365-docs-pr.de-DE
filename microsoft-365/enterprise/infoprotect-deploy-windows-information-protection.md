---
title: 'Schritt 4: Konfigurieren von Windows Information Protection'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Bereitstellen von Windows Information Protection in Microsoft 365.
ms.openlocfilehash: e32b09c20e86ff927748f7aedd8b8d769e07916e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073561"
---
# <a name="step-4-configure-windows-information-protection"></a>Schritt 4: Konfigurieren von Windows Information Protection

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Da immer mehr persönliche Geräte für Arbeitszwecke verwendet werden, steigt das Risiko, dass Apps und Geräte private Unternehmensdaten preisgeben. Ein Mitarbeiter sendet beispielsweise versehentlich ein Bild eines Marketingplans für ein künftiges Produkt an eine Website für soziale Medien oder speichert eine Datei mit vertraulichen Informationen in seinem öffentlichen Cloudspeicher. 

Windows Information Protection (WIP) bietet Schutz vor dieser Art von Datenlecks auf Windows 10-Geräten. Weitere Informationen finden Sie unter [Schutz Ihrer Unternehmensdaten mit WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip).

In Microsoft 365 Enterprise ist WIP eine Kombination von Windows 10 Enterprise und Microsoft Intune, das in Enterprise Mobility + Security (EMS) in Ihrem Abonnement enthalten ist. 

Gehen Sie folgendermaßen vor, um WIP in Ihrer Organisation mit Microsoft 365 Enterprise bereitzustellen:

1. Registrieren Sie Ihre Windows-Geräte in Intune. Sie hätten dies in [Phase 5: Verwaltung mobiler Geräte](mobility-infrastructure.md) tun sollen.
2. Erstellen Sie eine [Intune-Richtlinie für WIP](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure).
  - Stellen Sie sicher, dass Sie Liste mit geschützten Apps ausgefüllt haben.
  - Wählen Sie Ihre WIP-Schutzebene aus.

Sie können WIP auch mit [System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/overview-create-wip-policy-sccm) verwenden. 

Weitere Informationen finden Sie unter [Bewährte Methoden für WIP]( https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/guidance-and-best-practices-wip).

Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step4) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt


|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[Konfigurieren der Verhinderung von Datenverlust in Office 365](infoprotect-data-loss-prevention.md)|


