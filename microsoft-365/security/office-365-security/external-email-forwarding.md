---
title: Konfigurieren und Steuern der externen e-Mail-Weiterleitung, automatische Weiterleitung, 5.7.520 Zugriff verweigert, externe Weiterleitung deaktivieren, Ihr Administrator hat externe Weiterleitung deaktiviert, ausgehende Anti-Spam-Richtlinie
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: f729aa816caf8fb07499037ee27fbfc37b7205b3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202879"
---
# <a name="configuring-external-email-forwarding-in-office-365"></a>Konfigurieren der externen e-Mail-Weiterleitung in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Die externe Weiterleitung wird von der *ausgehenden Anti-Spam-Richtlinie* gesteuert und auf der Grundlage der konfigurierten Einstellung auf Benutzer beschränkt. Derzeit werden 3 Einstellungen unterstützt:

- **Automatic** – in diesem Modus ist das System für die Entscheidung zuständig, ob eine weitergeleitete Nachricht zulässig ist oder nicht.  Dies ist der Standardmodus, und in diesem Modus wird das System die automatische externe Weiterleitung blockieren.

- **On** – automatische externe Weiterleitung ist zulässig und nicht eingeschränkt.

- **Off** – die automatische externe Weiterleitung ist deaktiviert und führt zu einem Unzustellbarkeitsbericht (Non-Delivery Report, NDR) an den Endbenutzer.

Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Configure outbound Spam Filtering in EoP](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true) .

> [!NOTE]
> Durch das Deaktivieren der automatischen Weiterleitung werden auch Posteingangsregeln dsable, die Nachrichten an externe Adressen umleiten.

## <a name="controlling-external-email-forwarding"></a>Steuern der externen e-Mail-Weiterleitung

Als Administrator einer Organisation haben Sie möglicherweise Unternehmens-Anforderungen zum einschränken oder Steuern, wer e-Mails mithilfe von Posteingangsregeln oder SMTP-Weiterleitung außerhalb der Organisation automatisch weiterleiten kann. Die e-Mail-Weiterleitung kann ein nützliches Feature sein, kann aber auch durch die potenzielle Offenlegung von Informationen ein Risiko darstellen, auch durch Bereitstellen von Informationen für Angreifer, die zum Angriff auf die Organisation oder Ihre Partner genutzt werden können.

Office 365 lässt keine automatische externe Weiterleitung von Posteingangsregeln oder Mail Box-Konfiguration zu, die eine sichere Standardrichtlinie bereitstellt. Der Administrator kann diese Einstellungen jedoch für alle oder einige Benutzer in der Organisation ändern. Das Weiterleiten von Nachrichten zwischen internen Benutzern ist von einer solchen Änderung nicht betroffen.

> [!NOTE]
> Das Deaktivieren der automatischen Weiterleitung an externe Adressen in Office 365 wird in Phasen mit Details, die über [Nachrichten Center](https://admin.microsoft.com/Adminportal/Home?source=applauncher&ref=/MessageCenter) -Beiträge mitgeteilt werden, ausgeführt. Um Administratoren bei der Vorbereitung auf diese Änderungen zu unterstützen, müssen Sie die Richtlinien vor der Zeit ändern, um sicherzustellen, dass Ihre Benutzer keine Unterbrechung finden.

Weitere Informationen zu Benutzern, die die automatische Weiterleitung (Posteingangsregeln oder SMTP-Weiterleitung) in Ihrer Organisation verwenden, finden Sie im [Bericht automatisch weitergeleitete Nachrichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report?view=o365-worldwide&preserve-view=true).

## <a name="how-does-this-policy-work-with-other-automatic-forwarding-controls"></a>Wie funktioniert diese Richtlinie mit anderen automatischen Weiterleitungs Steuerelementen?

Als Administrator verfügen Sie möglicherweise bereits über andere Arten von Steuerelementen, wie das Blockieren der automatischen Weiterleitung in [Remotedomänen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) und die Verwendung einer Exchange-Transport Regel (ETR). Beide Steuerelemente sind unabhängig von dieser Funktion, beispielsweise wenn Sie die automatische Weiterleitung für eine Remotedomäne zulassen, die automatische Weiterleitung jedoch über die ausgehende Spam Richtlinie blockieren, wird das Ergebnis sein, dass die automatisch weitergeleitete Nachricht blockiert wird. Wenn Sie die automatische Weiterleitung in der ausgehenden Spam Richtlinie zulassen, Sie jedoch in einer ETR-oder Remotedomäne blockieren, wird die Nachricht durch eines dieser Steuerelemente blockiert. So können Sie beispielsweise die automatische Weiterleitung in der ausgehenden Spam Richtlinie zulassen und Remotedomänen verwenden, um die Domänen zu steuern, an die Benutzer Nachrichten automatisch weiterleiten können.


## <a name="the-blocked-email-forwarding-message"></a>Die Nachricht für blockierte e-Mail-Weiterleitung

Wenn eine Nachricht als automatisch weitergeleitet erkannt wird und die Organisationsrichtlinie diese Aktivität *blockiert* , wird ein **Unzustellbarkeitsbericht (Non-Delivery Report, NDR)** zurück an den Endbenutzer generiert. Der Bericht zeigt an, dass die Nachricht nicht zugestellt wurde. Der NDR weist das folgende Format auf: 

`5.7.520 Access Denied – Your administrator has disabled external forwarding – AS(XXXX)`
