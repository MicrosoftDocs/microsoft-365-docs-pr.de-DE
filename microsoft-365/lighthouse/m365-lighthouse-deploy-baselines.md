---
title: Bereitstellen von Microsoft 365 Lighthouse Basisplänen
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Informationen zum Bereitstellen von Microsoft 365 Lighthouse Basisplänen für verwaltete Dienstanbieter (Managed Service Providers, MSPs), die Microsoft 365 Lighthouse verwenden.
ms.openlocfilehash: 0bda7edec2a200e51e734db64e2b703a027e57bb
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395194"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Bereitstellen von Microsoft 365 Lighthouse Basisplänen 

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die [Anforderungen](m365-lighthouse-requirements.md)erfüllen. Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse Basisplänen können Sie standardmäßige verwaltete Mandantenkonfigurationen bereitstellen, um Mandantenbenutzer, -geräte und -daten zu schützen. Es gibt sechs Standardbasislinienkonfigurationen, die standardmäßig mit Microsoft 365 Lighthouse bereitgestellt werden:

- MFA für Administratoren anfordern
- MFA für Endbenutzer anfordern
- Blockieren der Legacyauthentifizierung
- Einrichten der Geräteregistrierung in Microsoft Endpoint Manager – Azure AD-Beitritt
- Konfigurieren der Defender-Antivirenrichtlinie für Windows Geräte
- Konfigurieren der Compliancerichtlinie für Windows Geräte

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Stellen Sie sicher, dass Sie und Ihre Kundenmandanten die Anforderungen erfüllen, die in den [Anforderungen für Microsoft 365 Lighthouse](m365-lighthouse-requirements.md)aufgeführt sind.

## <a name="learn-more-about-the-default-baseline"></a>Weitere Informationen zur Standardbasislinie

Wählen Sie im linken Navigationsbereich **Baselines** aus, um die Baselines-Seite zu öffnen. Sie werden sehen, dass die Standardbasislinie bereits zur Standardmandantengruppe (alle Mandanten) hinzugefügt wurde. Wählen Sie zum Anzeigen der Standardbasislinienkonfigurationen die **Baseline anzeigen** aus, um die Standardbasisplanseite zu öffnen. Die Konfigurationen werden als Bereitstellungsschritte aufgeführt. Wählen Sie einen der Bereitstellungsschritte aus, um Bereitstellungsdetails und Auswirkungen auf die Benutzer anzuzeigen.

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="Screenshot der Standardmäßigen Basisplanseite.>.":::

## <a name="deploy-a-baseline-configuration"></a>Bereitstellen einer Basiskonfiguration  

1. Wählen Sie auf der linken **Navigationsseite Mandanten** aus, um eine Liste Ihrer integrierten Mandanten anzuzeigen.

2. Wählen Sie den Mandanten aus, für den Sie die Basiskonfiguration bereitstellen möchten.

3. Wählen Sie die Registerkarte **"Bereitstellungsplan"** aus, um alle Bereitstellungsschritte aus der Basislinie anzuzeigen, die dem Bereitstellungsplan des Mandanten hinzugefügt wurden.

4. Wählen Sie einen Bereitstellungsschritt aus, um die Seite "Bereitstellungsschritt" zu öffnen.

5. Wählen Sie **"Übernehmen"** aus, um den ausgewählten Bereitstellungsschritt auf den Mandanten anzuwenden. Wenn der Bereitstellungsschritt "Diese Aktion erfordert einen manuellen Schritt" angibt, müssen Sie den manuellen Schritt abschließen, damit der Bereitstellungsschritt ordnungsgemäß angewendet wird.

## <a name="related-content"></a>Verwandte Inhalte

[Übersicht über die Verwendung von Basisplänen zur Bereitstellung standardmäßiger Mandantenkonfigurationen](m365-lighthouse-deploying-standard-tenant-configurations-overview.md) (Artikel)\
[faq zu Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (Artikel)