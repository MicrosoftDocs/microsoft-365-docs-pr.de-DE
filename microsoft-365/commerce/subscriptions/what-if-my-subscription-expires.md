---
title: Was geschieht beim Ablauf meines Abonnements mit meinen Daten? Kann darauf noch zugegriffen werden?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Hier erfahren Sie, was mit Ihren Daten geschieht, wenn Ihr Microsoft 365-Abonnement abläuft, deaktiviert wird oder Sie es kündigen.
ms.date: 04/08/2021
ms.openlocfilehash: f226514078a9f6d6bc1f4761269e2740300ef88d
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326798"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Was geschieht mit meinen Daten und dem Zugriff darauf, wenn mein Microsoft 365 Business-Abonnement endet?

Wenn Ihr Abonnement endet – weil es entweder abläuft oder Sie es zu kündigen beschließen – durchläuft Ihr Zugriff auf Microsoft 365-Dienste, -Anwendungen und -Kundendaten mehrere Stadien, bevor das Abonnement vollständig deaktiviert oder *gelöscht* wird. Wenn Ihnen dieser Ablauf bewusst ist, sind Sie besser gerüstet, um das Abonnement auf einen aktiven Status zurückzusetzen, bevor es zu spät ist. Andererseits wissen Sie, dass Sie Ihre Daten vor dem Verlassen von Microsoft 365 unbedingt sichern sollten, bevor sie endgültig gelöscht werden.

Lesen Sie diese wichtigen Informationen, bevor Sie sich mit dem [Microsoft 365-Support](../../business-video/get-help-support.md) in Verbindung setzen.
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Was geschieht beim Ablauf eines Abonnements mit den Daten?

- Wenn Ihr Abonnement abläuft, durchläuft es die folgenden Stadien: Abgelaufen / Deaktiviert / Gelöscht. Das Stadium "Abgelaufen" beginnt sofort, nachdem das Abonnement sein Enddatum erreicht hat.
- Wenn Sie die wiederkehrende Abrechnung für Ihr Jahresabonnement deaktivieren, durchläuft dieses die gleichen Stadien wie ein abgelaufenes Abonnement. Das erste Stadium beginnt am Erneuerungsdatum des Jahresabonnements und nicht ab dem Datum, an dem Sie die wiederkehrende Abrechnung für das Abonnement deaktiviert haben.
- Wenn Sie Ihr Monatsabonnement kündigen, wird es sofort (zum Zeitpunkt der Kündigung) deaktiviert. Dies bedeutet, dass Ihre Benutzer sofort den Zugriff auf die Microsoft 365-Ressourcen verlieren und für die nächsten 90 Tage nur Administratoren auf die Daten zugreifen können.

Die nachstehende Abbildung veranschaulicht, womit zu rechnen ist, wenn ein bezahltes Microsoft 365 Business-Abonnement abläuft.

| Aktiv | Abgelaufen <br/>(30 Tage lang\*) | Deaktiviert <br/>(90 Tage lang\*) | Gelöscht |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Daten für alle zugänglich*                                               | *Daten für alle zugänglich*                                                     | *Daten nur für Administratoren zugänglich*                                             | **Daten werden gelöscht<br/>Azure Active Directory wird entfernt, wenn nicht von anderen Diensten verwendet.** |
| Die Benutzer haben normalen Zugriff auf Microsoft 365, Dateien und Anwendungen.   | Die Benutzer haben normalen Zugriff auf Microsoft 365, Dateien und Anwendungen.              | Die Benutzer können nicht auf Microsoft 365, Dateien oder Anwendungen zugreifen.                        | Die Benutzer können nicht auf Microsoft 365, Dateien oder Anwendungen zugreifen.                                     |
| Administratoren haben normalen Zugriff auf Microsoft 365, Daten und Office-Anwendungen. | Administratoren können auf das Admin Center zugreifen.                                           | Administratoren können auf das Admin Center zugreifen, aber Benutzern keine Lizenzen zuweisen.       | Administratoren können auf das Admin Center zugreifen, um andere Abonnements zu kaufen und zu verwalten.             |
|                                                                        | Globale oder Abrechnungsadministratoren können das Abonnement im Admin Center reaktivieren. | Globale oder Abrechnungsadministratoren können das Abonnement im Admin Center reaktivieren. |                                                                                           |

*Gilt für die meisten Angebote, in den meisten Ländern und Regionen.
  
> [!NOTE]
> **Was sind "Kundendaten"?** Der Begriff "Kundendaten" bezieht sich gemäß Definition in den [Microsoft Online Service-Lizenzbedingungen](https://go.microsoft.com/fwlink/p/?LinkId=613649) auf alle Daten, einschließlich aller Text-, Audio- und Bilddateien, die Microsoft vom Kunden oder in dessen Auftrag durch seine Nutzung der Microsoft 365-Dienste bereitgestellt werden. Weitere Informationen zum Schutz von Kundendaten finden Sie unter [Erste Schritte mit dem Microsoft Service Trust-Portal](../../compliance/get-started-with-service-trust-portal.md).

## <a name="what-happens-if-i-cancel-a-subscription"></a>Was geschieht, wenn ich ein Abonnement kündige?

Wenn Sie Ihr Abonnement vor dem Laufzeit-Enddatum kündigen, wird das "Abgelaufen"-Stadium übersprungen, und es beginnt sofort das Stadium "Deaktiviert", das bei den meisten Abonnements, in den meisten Ländern und Regionen, 90 Tage dauert. Es empfiehlt sich, [Ihre Daten vor der Kündigung zu sichern](back-up-data-before-switching-plans.md). Allerdings können Sie als Administrator während des Stadiums "Deaktiviert" weiterhin auf die Daten Ihrer Organisation zugreifen und sie sichern. Alle Kundendaten, die Sie zurücklassen, werden möglicherweise nach 90 Tagen, spätestens aber 180 Tage nach der Kündigung gelöscht.
  
Dies können Sie für sich und Ihre Benutzer erwarten, wenn Sie ein Abonnement kündigen:
  
- **Administratorzugriff**: Administratoren können sich weiterhin anmelden, auf das Admin Center zugreifen und andere Abonnements nach Bedarf kaufen. Als globaler Administrator oder Rechnungsadministrator haben Sie 90 Tage Zeit, um [das Abonnement zu reaktivieren](reactivate-your-subscription.md), wobei alle Daten erhalten bleiben.

- **Benutzerzugriff:** Ihre Benutzer können keine Dienste wie OneDrive for Business nutzen oder auf Kundendaten zugreifen – beispielsweise E-Mails oder Dokumente auf Teamwebsites. Office-Anwendungen wie Word und Excel wechseln schließlich in einen schreibgeschützten Modus mit eingeschränkter Funktionalität, und die Benachrichtigung [Nicht lizenziertes Produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) wird angezeigt.

Wenn Sie sich über das Kündigen informieren möchten, lesen Sie [Kündigen Ihres Abonnements](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Wenn Sie möchten, dass Ihre Abonnementdaten vor Ablauf des typischen "Deaktiviert"-Stadiums gelöscht werden, können Sie [Ihr Konto schließen](../close-your-account.md).
  
> [!NOTE]
> Wenn Sie ein Abonnement explizit löschen, dann überspringt es die Phasen "Abgelaufen" und "Deaktiviert" und die SharePoint Online-Daten und -Inhalte, einschließlich OneDrive, werden sofort gelöscht.

## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Welche Möglichkeiten habe ich, wenn mein Abonnement bald abläuft?

Während ein Abonnement aktiv ist, haben Sie und Ihre Endbenutzer normalen Zugriff auf Ihre Daten, Dienste wie E-Mail und OneDrive for Business sowie Office-Anwendungen. Als Administrator erhalten Sie eine Reihe von Benachrichtigungen per E-Mail und im Admin Center, wenn sich Ihr Abonnement dem Ablaufdatum nähert.
  
Bevor das Abonnement tatsächlich sein Laufzeit-Enddatum erreicht, haben Sie ein paar Möglichkeiten:
  
- **Aktivieren der wiederkehrenden Abrechnung für das Abonnement**
  - Wenn die **wiederkehrende Abrechnung** bereits aktiviert ist, müssen Sie nichts tun. Ihr Abonnement wird automatisch abgerechnet, und Ihnen wird – je nach Ihrer aktuellen Zahlungshäufigkeit – ein weiteres Jahr oder ein weiterer Monat in Rechnung gestellt. Wenn Sie die **wiederkehrende Abrechnung** aus irgendeinem Grund deaktiviert haben, [können Sie sie jederzeit wieder aktivieren](renew-your-subscription.md).
  - Wenn Sie Microsoft 365 Apps for Business mit einer Prepaidkarte erworben haben, können Sie die [wiederkehrende Abrechnung für Ihr Abonnement aktivieren](renew-your-subscription.md).
  - Wenn Sie ein Open-Volumenlizenzkunde mit einem im Voraus bezahlten Jahresabonnement sind, wenden Sie sich an Ihren Partner, um einen neuen Product Key zu erwerben. Sie erhalten dann per E-Mail Anweisungen zum Aktivieren Ihres Product Keys im [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). Informationen zum Suchen nach einem neuen Partner oder dem Partner, mit dem Sie in der Vergangenheit zusammengearbeitet haben, finden Sie unter [Suchen nach Ihrem Partner oder Händler](../../admin/manage/find-your-partner-or-reseller.md).
  - Wenn Sie Microsoft 365 Apps for Business verwenden, lesen Sie [Verwalten der wiederkehrenden Abrechnung für Ihr Abonnement](renew-your-subscription.md).
- **Das Abonnement ablaufen lassen**
  - Wenn Sie per Kreditkarte oder Rechnung bezahlen und Ihr Abonnement nicht verlängern möchten, [deaktivieren Sie die wiederkehrende Abrechnung](renew-your-subscription.md). Ihr Abonnement läuft am Ablaufdatum ab, und Sie können alle in diesem Zusammenhang empfangenen E-Mail-Benachrichtigungen ignorieren.
  - Wenn Sie ein Open-Volumenlizenzkunde sind, der mit einem Partner zusammenarbeitet, können Sie Ihr Abonnement ablaufen lassen, indem Sie keine Maßnahme ergreifen.
  - Wenn Sie ein Microsoft 365 Business Standard-Kunde sind und Ihr Abonnement im Voraus bezahlt und mit einem Product Key aktiviert haben, können Sie Ihr Abonnement ablaufen lassen, ohne eine Maßnahme zu ergreifen.
- **Kündigen Sie vor Ablauf des Abonnements.** Weitere Informationen hierzu finden Sie unter [Kündigen Ihres Abonnements](cancel-your-subscription.md).

## <a name="what-happens-after-my-subscription-expires"></a>Was geschieht nach Ablauf meines Abonnements?

Wenn Sie Ihr Abonnement ablaufen lassen, durchläuft es mehrere Zustände, bevor es schließlich gelöscht wird. Dies gibt Ihnen als Administrator Zeit, es zu reaktivieren, wenn Sie den Dienst fortsetzen möchten, oder Ihre Daten zu sichern, wenn Sie entscheiden, dass Sie das Abonnement nicht mehr möchten.
  
Nachstehend wird aufgeführt, womit im jeweiligen Stadium Ihres Abonnements zu rechnen ist.
  
### <a name="state-expired"></a>Status: Abgelaufen

**Was Sie erwarten können:** Das Stadium "Abgelaufen" dauert bei den meisten Abonnements, einschließlich über [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298) erworbene Abonnements, in den meisten Ländern und Regionen 30 Tage. Für Produkte mit Volumenlizenzierung, außer Microsoft Open, dauert das Stadium „Abgelaufen“ 90 Tage.

Bei diesem Status können die Benutzer ganz normal auf das Microsoft 365-Portal, Office-Anwendungen und Dienste wie E-Mail und SharePoint Online zugreifen.
  
Sie selbst als Administrator können weiterhin auf das Admin Center zugreifen. Keine Sorge – globale oder Abrechnungsadministratoren können [das Abonnement reaktivieren](reactivate-your-subscription.md) und Microsoft 365 weiterhin verwenden. Wenn Sie das Abonnement nicht reaktivieren, denken Sie daran, [Ihre Daten zu sichern](back-up-data-before-switching-plans.md).
  
### <a name="state-disabled"></a>Status: Deaktiviert

**Was Sie erwarten können:** Wenn Sie Ihr Abonnement während des Status "Abgelaufen" nicht reaktivieren, beginnt der Status "Deaktiviert", der bei den meisten Abonnements, in den meisten Ländern und Regionen, 90 Tage dauert. Für Produkte mit Volumenlizenzierung dauert das Stadium „Deaktiviert“ 30 Tage.

In diesem Status wird Ihr Zugriff erheblich verringert. Ihre Benutzer können sich nicht anmelden oder auf Dienste wie E-Mail oder SharePoint Online zugreifen. Office-Anwendungen wechseln schließlich in einen schreibgeschützten Modus mit eingeschränkter Funktionalität, und die Benachrichtigung [Nicht lizenziertes Produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) wird angezeigt. Sie selbst können sich weiterhin anmelden und auf das Admin Center zugreifen, aber Benutzern keine Lizenzen hinzufügen. Ihre Kundendaten, einschließlich aller Benutzerdaten, E-Mails und Dateien auf Teamwebsites, stehen nur Ihnen und anderen Administratoren zur Verfügung.

Als globaler Administrator oder Abechnungsadministrator können Sie [das Abonnement reaktivieren](reactivate-your-subscription.md) und Microsoft 365 weiterhin verwenden, wobei alle Ihre Kundendaten erhalten geblieben sind. Wenn Sie beschließen, das Abonnement nicht zu reaktivieren, denken Sie daran, [Ihre Daten zu sichern](back-up-data-before-switching-plans.md).

### <a name="state-deleted"></a>Status: Gelöscht
  
**Was Sie erwarten können:** Wenn Sie Ihr Abonnement nicht reaktivieren, während die Nachfrist läuft oder es deaktiviert ist, wird es gelöscht.
  
Admins und Benutzer haben keinen Zugriff mehr auf die Dienste oder Office-Anwendungen, die mit dem Abonnement geliefert wurden. Alle Daten der Kunden – von Benutzerdaten über Dokumente bis hin zu E-Mails – werden dauerhaft gelöscht und sind nicht wiederherstellbar.
  
Zu diesem Zeitpunkt können Sie das Abonnement nicht mehr reaktivieren. Als globaler Administrator oder Rechnungsadministrator können Sie jedoch weiterhin auf das Admin Center zugreifen, um andere Abonnements zu verwalten oder neue Abonnements zu erwerben, die Sie für Ihre geschäftlichen Anforderungen benötigen.
  
> [!NOTE]
>
> - Durch Hinzufügen eines neuen Abonnements desselben Typs wie das Abonnement, das gelöscht wurde, werden die diesem Abonnement zuvor zugeordneten Daten nicht wiederhergestellt.
> - Wenn eine CSP-Lizenz ausgesetzt wird, besteht kein Stadium „Abgelaufen“ von 30 Tagen, und Dienste werden sofort deaktiviert. Daten werden nach 90 Tagen gelöscht, wenn der Mandant nicht durch Hinzufügen einer neuen Lizenz reaktiviert wird.

### <a name="what-happens-when-my-trial-ends"></a>Was geschieht, wenn meine Testversion endet?

Wenn Ihre Testphase endet, können Sie Microsoft 365 nicht mehr kostenlos nutzen. Sie haben ein paar Möglichkeiten:

- **Microsoft 365 kaufen.** Wenn Ihre Testversion abläuft, beginnt das Stadium „Abgelaufen“. So erhalten Sie (bei den meisten Testversionen, in den meisten Ländern und Regionen) weitere 30 Tage zum Kauf von Microsoft 365. Wenn Sie Ihre Testversion in ein kostenpflichtiges Abonnement umwandeln möchten, lesen Sie [Erwerb eines Abonnements aus Ihrer kostenlosen Testversion](../try-or-buy-microsoft-365.md#buy-a-subscription-from-your-free-trial).
- **Verlängern Sie Ihre Testversion.** Benötigen Sie mehr Zeit zum Beurteilen von Microsoft 365? In bestimmten Fällen können Sie [Ihre Testversion verlängern](../extend-your-trial.md).
- **Die Testversion kündigen oder ablaufen lassen.** Wenn Sie sich beschließen, Microsoft 365 nicht zu kaufen, können Sie Ihre Testversion ablaufen lassen oder [kündigen](cancel-your-subscription.md). Sichern Sie alle Daten, die Sie behalten möchten. Kurz nach Ablauf des 30 Tage andauernden Stadiums „Abgelaufen“ werden die Informationen Ihres Testkontos und alle Daten endgültig gelöscht.

> [!NOTE]
>
> Die Informationen auf dieser Seite unterliegen der [Microsoft Policy Disclaimer and Change Notice](https://go.microsoft.com/fwlink/p/?LinkId=613651) (Microsoft-Richtlinie für Haftungsausschluss und Änderungsmitteilung). Kehren Sie regelmäßig zu dieser Website zurück, um über Änderungen auf dem Laufenden zu bleiben.

## <a name="related-content"></a>Verwandte Inhalte

[Kündigen Ihres Abonnements](./cancel-your-subscription.md) (Artikel)\
[Verlängern von Microsoft 365 Business](./renew-your-subscription.md) (Artikel)\
[Reaktivieren Ihres Abonnements](./reactivate-your-subscription.md) (Artikel)
