---
title: Was geschieht beim Ablauf meines Abonnements mit meinen Daten? Kann ich darauf noch zugreifen?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 4436582f-211a-45ec-b72e-33647f97d8a3
description: Erfahren Sie, was mit Ihren Daten geschieht, wenn Ihr Microsoft 365 for Business-Abonnement abläuft, deaktiviert ist oder wenn Sie kündigen.
ms.openlocfilehash: 2852d2fc301d71131a0adb1c277974e2303dd395
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016077"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Was geschieht mit meinen Daten und dem Zugriff, wenn mein Microsoft 365 for Business-Abonnement endet?

Wenn Ihr Abonnement endet – entweder weil es abläuft oder weil Sie sich entscheiden, den Vorgang abzubrechen – wird der Zugriff auf Microsoft 365-Dienste,-Anwendungen und-Kundendaten in mehreren Status durchlaufen, bevor das Abonnement vollständig deaktiviert oder nicht mehr *bereit*gestellt wird. Wenn Sie sich dieser Progression bewusst sind, können Sie Ihr Abonnement besser in einen aktiven Zustand zurückversetzen, bevor es zu spät ist, oder-wenn Sie Microsoft 365 verlassen-Ihre Daten sichern, bevor Sie endgültig gelöscht werden.

Lesen Sie diese wichtigen Informationen, bevor Sie sich an den [Microsoft 365-Support](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)wenden.
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Was geschieht mit Daten, wenn ein Abonnement abläuft? 

- Wenn Ihr Abonnement abläuft, wird die folgende Phase durchlaufen: abgelaufen/deaktiviert/nicht verfügbar. Die abgelaufene Phase beginnt unmittelbar nach Erreichen des Enddatums des Abonnements.
- Wenn Sie die wiederkehrende Abrechnung für Ihr Jahresabonnement deaktivieren, wird die gleiche Phase wie ein abgelaufenes Abonnement durchlaufen. Die erste Phase beginnt mit dem Jahrestag des jährlichen Abonnements, nicht ab dem Datum, an dem Sie die Einstellung für die wiederkehrende Abrechnung des Abonnements deaktiviert haben.
- Wenn Sie Ihr monatliches Abonnement kündigen, ist es sofort (zum Zeitpunkt der Stornierung) deaktiviert. Dies bedeutet, dass Ihre Benutzer sofort den Zugriff auf die Microsoft 365-Objekte verlieren und nur Administratoren Zugriff auf die Daten für die nächsten 90 Tage haben.

In der folgenden Tabelle wird erklärt, was Sie erwarten können, wenn ein bezahltes Microsoft 365 for Business-Abonnement abläuft.

| **Active**                                                             | **Abgelaufen <br/> (30 Tage \* )**                                                | **Deaktiviert <br/> (90 Tage \* )**                                               | **Nicht Bereitgestellt**                                                                         |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Für alle zugängliche Daten*                                               | *Für alle zugängliche Daten*                                                     | *Nur für Administratoren zugängliche Daten*                                             | **Gelöschte Daten <br/> Azure Active Directory wird entfernt, wenn Sie nicht von anderen Diensten verwendet werden** |
| Benutzer haben normalen Zugriff auf Microsoft 365-, Daten-und Office-Anwendungen  | Benutzer haben normalen Zugriff auf Microsoft 365, Dateien und Anwendungen              | Benutzer können nicht auf Microsoft 365, Dateien oder Anwendungen zugreifen                        | Benutzer können nicht auf Microsoft 365, Dateien oder Anwendungen zugreifen                                     |
| Administratoren haben normalen Zugriff auf Microsoft 365-, Daten-und Office-Anwendungen | Administratoren können auf das Admin Center zugreifen                                           | Administratoren können auf das Admin Center zugreifen, aber Benutzern keine Lizenzen zuweisen       | Administratoren können auf das Admin Center zugreifen, um andere Abonnements zu erwerben und zu verwalten.             |
|                                                                        | Globale oder Abrechnungs Administratoren können das Abonnement im Admin Center reaktivieren. | Globale oder Abrechnungs Administratoren können das Abonnement im Admin Center reaktivieren. |                                                                                           |

* Für die meisten Angebote in den meisten Ländern und Regionen.
  
> [!NOTE]
> **Was sind "Kundendaten"?** Kundendaten, wie in den [Microsoft Online Service Terms](https://go.microsoft.com/fwlink/p/?LinkId=613649)definiert, bezieht sich auf alle Daten, einschließlich aller Text-, Sound-oder Bilddateien, die Microsoft von oder im Namen des Kunden über die Verwendung von Microsoft 365-Diensten durch den Kunden bereitgestellt werden. Weitere Informationen zum Schutz von Kundendaten finden Sie unter [Erste Schritte mit dem Microsoft-Dienst Vertrauensstellungs Portal](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-service-trust-portal).

## <a name="what-happens-if-i-cancel-a-subscription"></a>Was geschieht, wenn ich ein Abonnement kündige?

Wenn Sie Ihr Abonnement vor dem Ende des Termins kündigen, überspringt das Abonnement den Status "abgelaufen" und wechselt direkt in den Status "deaktiviert" (90 Tage für die meisten Abonnements) in den meisten Ländern und Regionen. Es wird empfohlen, dass Sie [Ihre Daten](back-up-data-before-switching-plans.md) vor dem Abbruch sichern, aber als Administrator können Sie weiterhin auf Daten für Ihre Organisation zugreifen und diese sichern, solange Sie sich im Status "deaktiviert" befinden. Alle Kundendaten, die Sie zurücklassen, werden möglicherweise nach 90 Tagen, spätestens aber 180 Tage nach der Kündigung gelöscht.
  
Dies können Sie für sich und Ihre Benutzer erwarten, wenn Sie ein Abonnement kündigen:
  
- **Administratorzugriff**: Administratoren können sich weiterhin anmelden, auf das Admin Center zugreifen und andere Abonnements nach Bedarf kaufen. Als globaler Administrator oder Rechnungsadministrator haben Sie 90 Tage Zeit, um [das Abonnement zu reaktivieren](reactivate-your-subscription.md), wobei alle Daten erhalten bleiben.

- **Benutzer Zugriff** Ihre Benutzer können keine Dienste wie OneDrive für Unternehmen verwenden oder auf Kundendaten zugreifen – beispielsweise e-Mails oder Dokumente auf Teamwebsites. Office-Anwendungen wie Word und Excel wechseln schließlich in einen schreibgeschützten Modus mit eingeschränkter Funktionalität, und die Benachrichtigung [Nicht lizenziertes Produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) wird angezeigt.

Informationen zum Abbrechen finden Sie unter [kündigen Ihres Abonnements](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Wenn Sie möchten, dass Ihre Abonnementdaten gelöscht werden, bevor der typische deaktivierte Zeitraum abgelaufen ist, können Sie [Ihr Konto schließen](../close-your-account.md).
  
## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Welche Möglichkeiten habe ich, wenn mein Abonnement bald abläuft?

Während ein Abonnement aktiv ist, haben Sie und Ihre Endbenutzer normalen Zugriff auf Ihre Daten, Dienste wie e-Mail und OneDrive für Unternehmen und Office-Anwendungen. Als Administrator erhalten Sie eine Reihe von Benachrichtigungen per e-Mail und im Admin Center, wenn Ihr Abonnement seinem Ablaufdatum nahe kommt.
  
Bevor das Abonnement tatsächlich sein Ablaufdatum erreicht, haben Sie ein paar Möglichkeiten:

::: moniker range="o365-worldwide"
  
- **Aktivieren Sie wiederkehrende Abrechnung für das Abonnement.**

  - Wenn die **wiederkehrende Abrechnung** bereits aktiviert ist, müssen Sie keine Aktion durchführen. Ihr Abonnement wird automatisch in Rechnung gestellt, und je nach ihrer aktuellen Zahlungshäufigkeit werden Sie für ein weiteres Jahr oder einen weiteren Monat belastet. Wenn Sie aus irgendeinem Grund **wiederkehrende Abrechnung** deaktiviert haben, können Sie immer [wiederkehrende Abrechnung wieder aktivieren](renew-your-subscription.md).

  - Wenn Sie Microsoft 365 apps for Business mit einer Prepaid-Karte erworben haben, können Sie die [wiederkehrende Abrechnung](renew-your-subscription.md) für Ihr Abonnement aktivieren.

  - Wenn Sie ein offener Volumenlizenzkunde mit einem Prepaid-Abonnement mit einem Jahr sind, wenden Sie sich an Ihren Partner, um einen neuen Product Key zu erwerben. Sie erhalten per E-Mail Anweisungen zum Aktivieren Ihres Product Keys im [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). Informationen zum Auffinden eines neuen Partners oder des Partners, mit dem Sie in der Vergangenheit zusammengearbeitet haben, finden Sie unter [Suchen Ihres Partners oder Händlers](../../admin/manage/find-your-partner-or-reseller.md).

  - Wenn Sie Microsoft 365 Apps für Unternehmen haben, finden Sie weitere Informationen unter [Manage wiederkehrende Abrechnung für Ihr Abonnement](renew-your-subscription.md).

- **Lassen Sie das Abonnement ablaufen.**

  - Wenn Sie mit Kreditkarte oder Rechnung bezahlen und Ihr Abonnement nicht fortsetzen möchten, schalten Sie [wiederkehrende Abrechnung aus](renew-your-subscription.md). Ihr Abonnement endet mit dem Ablaufdatum, und Sie können alle zugehörigen e-Mail-Benachrichtigungen ignorieren.

  - Wenn Sie ein offener Volumenlizenzkunde sind, der mit einem Partner zusammenarbeitet, können Sie Ihr Abonnement ablaufen lassen, indem Sie keine Aktion durch nehmen.

  - Wenn Sie ein Office 365 Small Business Premiumer Kunde sind und Office 365 voraus bezahlt haben und ihn mit einem Product Key aktiviert haben, können Sie Ihr Abonnement ablaufen lassen, indem Sie keine Aktion durch nehmen.

- **Kündigen Sie vor Ablauf des Abonnements.** Ausführliche Informationen finden Sie unter [kündigen Ihres Abonnements](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-germany"
  
- **Verwalten der wiederkehrenden Abrechnung für das Abonnement.**

  - Wenn die **wiederkehrende Abrechnung** bereits aktiviert ist, müssen Sie keine Aktion durchführen. Ihr Abonnement wird automatisch abgerechnet, und Ihnen wird – je nach Ihrer aktuellen Zahlungshäufigkeit – ein weiteres Jahr oder ein weiterer Monat in Rechnung gestellt. Wenn Sie aus irgendeinem Grund **wiederkehrende Abrechnung** deaktiviert haben, können Sie immer [wiederkehrende Abrechnung wieder aktivieren](renew-your-subscription.md).

  - Wenn Sie Microsoft 365 apps for Business mit einer Prepaid-Karte erworben haben, können Sie die [wiederkehrende Abrechnung](renew-your-subscription.md) für Ihr Abonnement aktivieren.

  - Wenn Sie ein offener Volumenlizenzkunde mit einem Prepaid-Abonnement mit einem Jahr sind, wenden Sie sich an Ihren Partner, um einen neuen Product Key zu erwerben. Sie erhalten per E-Mail Anweisungen zum Aktivieren Ihres Product Keys im [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). Informationen zum Auffinden eines neuen Partners oder des Partners, mit dem Sie in der Vergangenheit zusammengearbeitet haben, finden Sie unter [Suchen Ihres Partners oder Händlers](../../admin/manage/find-your-partner-or-reseller.md).

  - Wenn Sie Microsoft 365 Apps für Unternehmen haben, lesen Sie [Erneuern Ihres Abonnements](renew-your-subscription.md).

- **Lassen Sie das Abonnement ablaufen.**

  - Wenn Sie mit Kreditkarte oder Rechnung bezahlen und Ihr Abonnement nicht fortsetzen möchten, schalten Sie [wiederkehrende Abrechnung aus](renew-your-subscription.md). Ihr Abonnement läuft am Ablaufdatum ab, und Sie können alle in diesem Zusammenhang empfangenen E-Mail-Benachrichtigungen ignorieren.

  - Wenn Sie ein offener Volumenlizenzkunde sind, der mit einem Partner zusammenarbeitet, können Sie Ihr Abonnement ablaufen lassen, indem Sie keine Aktion durch nehmen.

  - Wenn Sie ein Office 365 Small Business Premiumer Kunde sind und Office 365 voraus bezahlt haben und ihn mit einem Product Key aktiviert haben, können Sie Ihr Abonnement ablaufen lassen, indem Sie keine Aktion durch nehmen.

- **Kündigen Sie vor Ablauf des Abonnements.** Ausführliche Informationen finden Sie unter [kündigen Ihres Abonnements](cancel-your-subscription.md).
  
::: moniker-end

::: moniker range="o365-21vianet"
  
- **Verlängern Sie das Abonnement.** Wenn die **wiederkehrende Abrechnung** bereits aktiviert ist, müssen Sie keine Aktion durchführen. Ihr Abonnement wird automatisch abgerechnet, und Ihnen wird – je nach Ihrer aktuellen Zahlungshäufigkeit – ein weiteres Jahr oder ein weiterer Monat in Rechnung gestellt. Wenn Sie aus irgendeinem Grund **wiederkehrende Abrechnung** deaktiviert haben, können Sie immer [wiederkehrende Abrechnung wieder aktivieren](renew-your-subscription.md).

- **Lassen Sie das Abonnement ablaufen.** Wenn Sie mit Kreditkarte oder Rechnung bezahlen und Ihr Abonnement nicht fortsetzen möchten, schalten Sie [wiederkehrende Abrechnung aus](renew-your-subscription.md). Ihr Abonnement läuft am Ablaufdatum ab, und Sie können alle in diesem Zusammenhang empfangenen E-Mail-Benachrichtigungen ignorieren.

- **Kündigen Sie vor Ablauf des Abonnements.** Ausführliche Informationen finden Sie unter [kündigen Ihres Abonnements](cancel-your-subscription.md).

::: moniker-end

## <a name="what-happens-after-my-subscription-expires"></a>Was geschieht nach Ablauf meines Abonnements?
Wenn Sie Ihr Abonnement ablaufen lassen, durchläuft es mehrere Status, bevor es endgültig gelöscht wird. Auf diese Weise können Sie als Administrator Zeit zum erneuten Aktivieren, wenn Sie den Dienst fortsetzen möchten, oder um Ihre Daten zu sichern, wenn Sie entscheiden, dass das Abonnement nicht mehr gewünscht wird.
  
Nachstehend wird aufgeführt, was Sie im jeweiligen Status Ihres Abonnements erwarten können.
  
### <a name="state-expired"></a>Status: abgelaufen
  
::: moniker range="o365-worldwide"

 **What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions. For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.

::: moniker-end

::: moniker range="o365-germany"

 **What to expect:** The expired state lasts for 30 days for most subscriptions, including subscriptions purchased through [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), in most countries and regions. For Volume Licensing products, except for Microsoft Open, the expired state lasts 90 days.

::: moniker-end

::: moniker range="o365-21vianet"

 **Was Sie erwarten können:** Der Status "Abgelaufen" dauert bei den meisten Abonnements, in den meisten Ländern und Regionen, 30 Tage.

::: moniker-end

In diesem Zustand haben Benutzer normalen Zugriff auf das Microsoft 365-Portal, Office-Anwendungen und Dienste wie e-Mail und SharePoint Online.
  
Als Administrator haben Sie weiterhin Zugriff auf das Admin Center. Keine Sorge – globale oder Abrechnungs Administratoren können [das Abonnement reaktivieren](reactivate-your-subscription.md) und Microsoft 365 weiterhin verwenden. Wenn Sie nicht reaktivieren, [Sichern Sie die Daten](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Status: deaktiviert
  
::: moniker range="o365-worldwide"

 **What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions. For Volume Licensing products, the disabled state lasts 30 days.

::: moniker-end

::: moniker range="o365-germany"

 **What to expect:** If you don't reactivate your subscription while it is in the expired state, it moves into a disabled state, which lasts for 90 days for most subscriptions, in most countries and regions. For Volume Licensing products, the disabled state lasts 30 days.

::: moniker-end

::: moniker range="o365-21vianet"

 **Was Sie erwarten können:** Wenn Sie Ihr Abonnement während des Status "Abgelaufen" nicht reaktivieren, beginnt der Status "Deaktiviert", der bei den meisten Abonnements, in den meisten Ländern und Regionen, 90 Tage dauert.

::: moniker-end

::: moniker range="o365-worldwide"

In diesem Status wird Ihr Zugriff erheblich verringert. Ihre Benutzer können sich nicht anmelden oder auf Dienste wie e-Mail oder SharePoint Online zugreifen. Office-Anwendungen wechseln schließlich in einen schreibgeschützten Modus mit eingeschränkter Funktionalität, und die Benachrichtigung [Nicht lizenziertes Produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) wird angezeigt. Sie können sich weiterhin anmelden und zum Admin Center gelangen, Benutzern jedoch keine Lizenzen zuweisen. Ihre Kundendaten, einschließlich aller Benutzerdaten, E-Mails und Dateien auf Teamwebsites, stehen nur Ihnen und anderen Administratoren zur Verfügung.

::: moniker-end

Als globaler oder abrechnungsadministrator können Sie [das Abonnement reaktivieren](reactivate-your-subscription.md) und Microsoft 365 weiterhin verwenden, wobei alle Ihre Kundendaten intakt sind. Wenn Sie sich für eine erneute Aktivierung entscheiden, [Sichern Sie die Daten](back-up-data-before-switching-plans.md).

### <a name="state-deprovisioned"></a>State: unprovisioned
  
 **Was Sie erwarten können:** Wenn Sie Ihr Abonnement nicht reaktivieren, während die Nachfrist läuft oder es deaktiviert ist, wird seine Bereitstellung aufgehoben.
  
Administratoren und Benutzer können nicht mehr auf die im Abonnement enthaltenen Dienste oder Office-Anwendungen zugreifen. Alle Kundendaten – von Benutzerdaten zu Dokumenten und e-Mails – werden endgültig gelöscht und können nicht wiederhergestellt werden.
  
Zu diesem Zeitpunkt können Sie das Abonnement nicht mehr reaktivieren. Allerdings können Sie als globaler oder abrechnungsadministrator weiterhin auf das Admin Center zugreifen, um andere Abonnements zu verwalten, oder um neue Abonnements zu erwerben, um Ihre geschäftlichen Anforderungen zu erfüllen.
  
> [!NOTE]
> Durch Hinzufügen eines neuen Abonnements desselben Typs wie das Abonnement, dessen Bereitstellung aufgehoben wurde, werden die diesem Abonnement zugeordneten Daten nicht wiederhergestellt.

### <a name="what-happens-when-my-trial-ends"></a>Was geschieht, wenn meine Testversion endet?

Wenn Ihre Testversion beendet ist, können Sie Microsoft 365 nicht kostenlos weiter verwenden. Es gibt ein paar Möglichkeiten:

::: moniker range="o365-worldwide"
- **Kaufen Sie Microsoft 365.** Wenn Ihre Testversion abläuft, wird Sie in eine Kulanz Phase verschoben, sodass Sie weitere 30 Tage (für die meisten Länder und Regionen) Microsoft 365 erwerben können. Informationen zum Konvertieren Ihrer Testversion in ein kostenpflichtiges Abonnement finden Sie unter [kaufen Ihrer Testversion von Microsoft 365 for Business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-germany"
- **Kaufen Sie Microsoft 365.** Wenn Ihre Testversion abläuft, wird Sie in eine Kulanz Phase verschoben, sodass Sie weitere 30 Tage (für die meisten Länder und Regionen) Microsoft 365 erwerben können. Informationen zum Konvertieren Ihrer Testversion in ein kostenpflichtiges Abonnement finden Sie unter [kaufen Ihrer Testversion von Microsoft 365 for Business](../buy-a-subscription-from-your-free-trial.md).

::: moniker-end

::: moniker range="o365-21vianet"
- **Office 365 kaufen.** Wenn Ihre Testversion abläuft, wird Sie in eine Kulanz Phase verschoben, sodass Sie weitere 30 Tage (für die meisten Länder und Regionen) Office 365 erwerben können. Wenn Sie Ihre Testversion in ein kostenpflichtiges Abonnement umwandeln möchten, lesen Sie [Buy or try subscriptions for Office 365 operated by 21Vianet](../../admin/services-in-china/buy-or-try-subscriptions.md).

::: moniker-end

- **Verlängern Sie Ihre Testversion.** Benötigen Sie mehr Zeit zum Auswerten von Microsoft 365? In bestimmten Fällen können Sie [Ihre Testversion verlängern](../extend-your-trial.md).

- **Kündigen Sie die Testversion, oder lassen Sie sie ablaufen.** Wenn Sie sich entschließen, Microsoft 365 zu kaufen, können Sie Ihre Testversion ablaufen lassen oder [stornieren](cancel-your-subscription.md). Sichern Sie alle Daten, die Sie behalten möchten. Kurz nach Ablauf der 30-Tage-Nachfrist werden die Informationen Ihres Testkontos und alle Daten endgültig gelöscht.

> [!NOTE]
> Die Informationen auf dieser Seite unterliegen der [Microsoft Policy Disclaimer and Change Notice](https://go.microsoft.com/fwlink/p/?LinkId=613651) (Microsoft-Richtlinie für Haftungsausschluss und Änderungsmitteilung). Kehren Sie regelmäßig zu dieser Website zurück, um Änderungen zu überprüfen.

## <a name="related-articles"></a>Verwandte Artikel 

[Kündigen Ihres Abonnements](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/cancel-your-subscription)

[Verlängern von Microsoft 365 Business](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/renew-your-subscription)

[Verlängern oder Reaktivieren Ihres Abonnements](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/reactivate-your-subscription)