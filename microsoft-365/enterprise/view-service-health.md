---
title: Überprüfen des Microsoft 365-Dienststatus
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365P_ServiceHealthModern
- O365M_ServiceHealthModern
- O365E_ViewStatusServices
- O365E_ServiceHealthModern
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- BCS160
- IWA160
ms.assetid: 932ad3ad-533c-418a-b938-6e44e8bc33b0
description: Zeigen Sie den Integritätsstatus von Microsoft 365 Diensten an, bevor Sie den Support anrufen, um festzustellen, ob eine aktive Dienstunterbrechung vorliegt.
ms.openlocfilehash: 28ec578fa0f2321c459284519be62e6e8448b4a5
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842038"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Überprüfen des Microsoft 365-Dienststatus

[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

Sie können den Status Ihrer Microsoft-Dienste, einschließlich Office im Web, Yammer, Microsoft Dynamics CRM und Clouddienste für die Verwaltung mobiler Geräte, auf der Seite **"Dienstintegrität"** im [Microsoft 365 Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)anzeigen. Wenn bei einem Clouddienst Probleme auftreten, können Sie den Dienststatus überprüfen, um festzustellen, ob es sich um ein bekanntes Problem handelt, für das bereits an einer Lösung gearbeitet wird, bevor Sie den Support anrufen oder Zeit für die Problembehandlung aufwenden.

Wenn Sie sich nicht beim Admin Center anmelden können, können Sie die [Dienststatusseite](https://status.office365.com) verwenden, um nach bekannten Problemen zu suchen, die Sie daran hindern, sich bei Ihrem Mandanten anzumelden.  Registrieren Sie sich auch, um uns bei [@MSFT365status](https://twitter.com/MSFT365Status) auf Twitter zu folgen, um Informationen zu bestimmten Ereignissen anzuzeigen.

## <a name="how-to-check-service-health"></a>Überprüfen des Dienststatus

1. Wechseln Sie zum Microsoft 365 Admin Center, [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) und melden Sie sich mit einem Administratorkonto an.

    > [!NOTE]
    > Personen, denen die Administratorrolle "Globaler Administrator" oder "Dienstsupport" zugewiesen ist, können den Dienststatus anzeigen. Damit Exchange-, SharePoint- und Skype for Business-Administratoren den Dienststatus anzeigen können, muss ihnen auch die Rolle des Dienstadministrators zugewiesen sein. Weitere Informationen zu Rollen, die den Dienststatus anzeigen können, finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).

2. Wenn Sie das neue Admin Center nicht verwenden, wählen Sie auf der **Startseite** in der oberen rechten Ecke die Umschaltfläche **"Neues Admin Center testen"** aus.

3. Zum Anzeigen des Dienststatus wechseln Sie im Admin Center zu **Status** > **Dienststatus**, oder wählen Sie auf dem **Startdashboard** die Karte **Dienststatus** aus. Die Dashboardkarte gibt an, ob ein Problem mit einem aktiven Dienst vorliegt, und stellt einen Link zur Seite mit Details zum **Dienststatus** bereit.

4. Der Status der einzelnen Clouddienste wird auf der Seite **Dienstatus** in einem Tabellenformat angezeigt.

   ![Ansicht der aktuellen Probleme unter "Dienststatus"](../media/service-health-all-services.png)

Auf der Registerkarte **Alle Dienste** (Standardansicht) werden alle Dienste und ihr aktueller Status angezeigt. Ein Symbol und die Spalte **Status** geben den Status jedes Diensts an.

Wenn Sie die Ansicht nach Diensten filtern möchten, die aktuell einen Vorfall aufweisen, wählen Sie die Registerkarte **Vorfälle** oben auf der Seite aus. Bei Auswahl der Registerkarte **Empfehlungen** werden nur Dienste angezeigt, für die derzeit eine Empfehlung angegeben ist.

Auf der Registerkarte **Verlauf** wird der Verlauf von Vorfällen und Empfehlungen angezeigt, die aufgelöst wurden.

Wenn ein Problem mit einem Microsoft 365 Dienst auftritt und sie nicht auf der Seite **"Dienstintegrität"** aufgeführt wird, teilen Sie uns dies mit, indem Sie **"Problem melden"** auswählen und das kurze Formular ausfüllen. Wir sehen uns verwandte Daten und Berichte aus anderen Organisationen an, um zu sehen, wie weit das Problem verbreitet ist und ob es von unserem Dienst stammt. Wenn dies der Fall ist, fügen wir sie als neuen Vorfall oder eine Empfehlung auf der Seite **"Dienststatus"** hinzu, auf der Sie die Lösung nachverfolgen können. Wenn sie nicht innerhalb von ca. 30 Minuten in der Liste angezeigt wird, sollten Sie sich an den Support wenden, um das Problem zu beheben.

Um Ihre Ansicht anzupassen, welche Dienste im Dashboard angezeigt werden, wählen Sie **"Benutzerdefinierte**  >  **Einstellungsansicht"** aus, und deaktivieren Sie die Kontrollkästchen für die Dienste, die Sie aus der Ansicht des Dienststatus-Dashboards herausfiltern möchten. Stellen Sie sicher, dass das Kontrollkästchen für jeden Dienst aktiviert ist, den Sie überwachen möchten.

Um sich für E-Mail-Benachrichtigungen über neue Vorfälle zu registrieren, die sich auf Ihren Mandanten und Statusänderungen für einen aktiven Vorfall auswirken, wählen Sie **"Einstellungs-E-Mail"**  >  aus, klicken Sie auf **"Dienstbenachrichtigungen per E-Mail senden"** und geben Sie dann Folgendes an:

- Bis zu zwei E-Mail-Adressen.
- Ob Sie Benachrichtigungen für Vorfälle oder Empfehlungen wünschen
- Die Dienste, für die Sie eine Benachrichtigung wünschen

> [!NOTE]
> Jeder Administrator kann seine Einstellungen festlegen, und das oben genannte Limit von zwei E-Mail-Adressen ist pro Administratorkonto.

> [!TIP]
> Sie können auch die [Microsoft 365 Admin-App](https://go.microsoft.com/fwlink/p/?linkid=627216) auf Ihrem mobilen Gerät verwenden, um den Dienststatus anzuzeigen. Dies ist eine hervorragende Möglichkeit, um mit Pushbenachrichtigungen auf dem laufenden zu bleiben.

### <a name="view-details-of-posted-service-health"></a>Anzeigen von Details des veröffentlichten Dienststatus

Wenn Sie in der Ansicht **Alle Dienste** den Dienststatus auswählen, wird eine Zusammenfassungsansicht der Empfehlungen oder Vorfälle angezeigt.

[![Screenshot der Dienstempfehlung ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

Die Empfehlungs- oder Vorfallzusammenfassung enthält folgende Informationen:

- **Titel**: Eine Zusammenfassung des Problems.
- **Dienst**: Der Name des betroffenen Diensts.
- **ID**: Ein numerischer Bezeichner für das Problem.
- **Status**: Wie sich dieses Problem auf den Dienst auswirkt.
- **Startzeit**: Der Zeitpunkt, zu dem das Problem begann.
- **Letzte Aktualisierung**: Der Zeitpunkt der letzten Aktualisierung der Nachricht zum Dienststatus. Wir veröffentlichen häufig Nachrichten, um Sie über die Fortschritte beim Anwenden einer Lösung zu informieren.

Wählen Sie das Problem aus, um die Detailseite mit weiteren Informationen zum Problem anzuzeigen, einschließlich des [Verlaufs](#history) aller Nachrichten, die wir während unserer Arbeit an einer Lösung veröffentlicht haben.

![Screenshot mit Details zum Problem](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Übersetzen von Dienststatusdetails

Da Erläuterungen zum Dienststatus in Echtzeit veröffentlicht werden, sind sie nicht automatisch in Ihre Sprache übersetzt, und die Details eines Dienstereignisses sind nur in Englisch angegeben. Zum Übersetzen der Erläuterung führen Sie die folgenden Schritte aus: 

1. Wechseln Sie zu [Translator](https://www.bing.com/translator/).

2. Wählen Sie auf der Seite **Dienststatus** einen Vorfall oder eine Empfehlung aus. Kopieren Sie unter **Details anzeigen** den Text zum Problem.

3. Fügen Sie den Text in Translator ein, und klicken Sie auf **Übersetzen**.

### <a name="definitions"></a>Definitionen

Die meiste Zeit werden Dienste als fehlerfrei und ohne weitere Informationen angezeigt. Wenn bei einem Dienst ein Problem vorliegt, wird das Problem entweder als eine Empfehlung oder als ein Vorfall angegeben, und der aktuelle Status wird angezeigt.

> [!TIP]
> Geplante Wartungsereignisse werden im Dienststatus nicht angezeigt. Sie können geplante Wartungsereignisse verfolgen, indem Sie sich mit dem **Nachrichtencenter** auf dem neuesten Stand halten. Filtern Sie nach Nachrichten, für dieeine geplante Änderung als Kategorie angegeben ist, um herauszufinden, wann die Änderung stattfinden soll, welche Auswirkungen sie hat und wie Sie Vorbereitungen dafür treffen können. Weitere Informationen finden Sie [im Nachrichtencenter in Microsoft 365.](https://support.office.com/article/38fb3333-bfcc-4340-a37b-deda509c2093)

### <a name="incidents-and-advisories"></a>Vorfälle und Empfehlungen

| Symbol | Beschreibung |
|:-----|:-----|
|![Infosymbol für Empfehlung](../media/a7f5fd21-c760-4948-9bc1-50f7c8070e28.png)|Wenn für einen Dienst eine Empfehlung angezeigt wird, wissen wir von einem Problem, das sich auf einige Benutzer auswirkt, doch ist der Dienst weiterhin verfügbar. Bei einer Empfehlung gibt es häufig eine Umgehung für das Problem und das Problem tritt ggf. nur zeitweilig auf oder ist in Hinsicht auf Umfang und Auswirkungen auf Benutzer eingeschränkt.  <br/> |
|![Ausrufezeichensymbol für Vorfall](../media/a636db57-6083-44dc-bbd5-556850804f17.png)|Wenn für einen Dienst ein aktiver Vorfall angezeigt wird, handelt es sich ein kritisches Problem und der Dienst oder eine wichtige Funktion des Diensts ist nicht verfügbar. Beispielsweise können Benutzer keine E-Mails senden und empfangen oder sich nicht anmelden. Vorfälle haben erkennbare Auswirkungen für die Benutzer. Tritt ein Vorfall ein, stellen wir Updates zur Untersuchung, Abhilfemaßnahmen und Lösungsbestätigungen im Dashboard zur Dienstintegrität bereit.  <br/> |

### <a name="status-definitions"></a>Statusdefinitionen

| Status | Definition |
|:-----|:-----|
|**Wird untersucht** | Uns ist ein potenzielles Problem bekannt, und wir sammeln weitere Informationen dazu, was vor sich geht und welche Auswirkungen es hat. |
|**Dienstbeeinträchtigung** | Wir haben bestätigt, dass ein Problem vorliegt, das eine Auswirkung auf die Verwendung eines Diensts oder Features haben kann. Dieser Status wird möglicherweise angezeigt, wenn ein Dienst langsamer als gewöhnlich ausgeführt wird, zeitweilige Unterbrechungen auftreten oder ein Feature nicht funktioniert. |
|**Dienstunterbrechung** | Dieser Status wird angezeigt, wenn wir feststellen, dass sich ein Problem auf den Zugriff der Benutzer auf den Dienst auswirkt. In diesem Fall ist das Problem schwerwiegend und kann konsistent reproduziert werden. |
|**Dienst wird wiederhergestellt** | Die Ursache des Problems wurde erkannt, wir wissen, welche Behebungsmaßnahme zu ergreifen ist, und sind dabei, den Dienst wieder in einen fehlerfreien Zustand zu versetzen. |
|**Erweiterte Wiederherstellung** | Dieser Status gibt an, dass eine Behebungsmaßnahme durchgeführt wird, um den Dienst für die Mehrzahl der Benutzer wiederherzustellen, es dauert jedoch einige Zeit, bis alle betroffenen Systeme erreicht sind. Dieser Status wird möglicherweise auch angezeigt, wenn wir eine temporäre Korrektur vorgenommen haben, um die Auswirkungen zu verringern, während wir an der Bereitstellung einer dauerhaften Lösung arbeiten. |
|**Untersuchung angehalten** | Dieser Status wird angezeigt, wenn unsere detaillierte Untersuchung eines potenziellen Problems dazu führt, dass Kunden um Angabe zusätzlicher Informationen für eine weitere Untersuchung gebeten werden. Wenn Ihre Unterstützung erforderlich ist, informieren wir Sie, welche Daten oder Protokolle wir benötigen. |
|**Dienst wiederhergestellt** | Wir haben bestätigt, dass durch die Behebungsmaßnahme das zugrunde liegende Problem gelöst und der Dienst wieder in einen fehlerfreien Zustand versetzt wurde. Informationen zur Fehlerursache finden Sie unter den Problemdetails. |
|**Falsch positives Ergebnis** | Nach einer detaillierten Untersuchung haben wir bestätigt, dass der Dienst fehlerfrei ist und wie vorgesehen funktioniert. Es wurden keine Auswirkungen auf den Dienst oder die Ursache des Vorfalls festgestellt, der außerhalb des Diensts aufgetreten ist. |
|**Vorfallnachsorgebericht veröffentlicht** | Wir haben für ein bestimmtes Problem einen Beitrag veröffentlicht, der Informationen zu den Ursachen sowie nächste Schritte umfasst, um sicherzustellen, dass ein ähnliches Problem nicht wieder auftritt. |

### <a name="history"></a>Verlauf

Der Dienststatus zeigt den aktuellen Status sowie den Verlauf aller Empfehlungen und Vorfälle für Dienste, die Ihren Mandanten in den letzten 30 Tagen betroffen haben. Zum Anzeigen des früheren Status aller Dienste wählen Sie auf der Seite mit den Problemdetails die Option **Verlauf anzeigen** aus.

![Anzeigen des Links zum Statusverlauf](../media/service-health-view-history.png)

Es wird eine Liste aller Nachrichten zum Dienststatus angezeigt, die im ausgewählten Zeitraum veröffentlicht wurden (siehe unten).

![Anzeigen des Dienststatusverlaufs](../media/service-health-history.png)

Erweitern Sie eine beliebige Zeile, um weitere Details zum Problem anzuzeigen.

Weitere Informationen zu unserer Verpflichtung zur Betriebszeit finden Sie unter ["Transparente Vorgänge aus Microsoft 365."](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

## <a name="related-topics"></a>Verwandte Themen

[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[Nachrichtencentereinstellungen](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[Überprüfen Windows Veröffentlichungsintegrität im Admin Center](/windows/deployment/update/check-release-health)
