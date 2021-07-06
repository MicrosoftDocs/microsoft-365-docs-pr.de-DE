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
ms.openlocfilehash: 95ab260b4950d261eed1288b8fdf1f59883ff15f
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300405"
---
# <a name="how-to-check-microsoft-365-service-health"></a>Überprüfen des Microsoft 365-Dienststatus

[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/O365-Admin-AdminCenterChanging.png)](/office365/admin/microsoft-365-admin-center-preview?preserve-view=true&view=o365-worldwide)

Sie können den Status Ihrer Microsoft-Dienste, einschließlich Office im Web, Yammer, Microsoft Dynamics CRM und Clouddienste für die Verwaltung mobiler Geräte, auf der Seite **"Dienstintegrität"** im [Microsoft 365 Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2024339)anzeigen. Wenn bei einem Clouddienst Probleme auftreten, können Sie den Dienststatus überprüfen, um festzustellen, ob es sich um ein bekanntes Problem handelt, für das bereits an einer Lösung gearbeitet wird, bevor Sie den Support anrufen oder Zeit für die Problembehandlung aufwenden.

Wenn Sie sich nicht beim Admin Center anmelden können, können Sie die [Dienststatusseite](https://status.office365.com) verwenden, um nach bekannten Problemen zu suchen, die Sie daran hindern, sich bei Ihrem Mandanten anzumelden.  Registrieren Sie sich auch, um uns bei [@MSFT365status](https://twitter.com/MSFT365Status) auf Twitter zu folgen, um Informationen zu bestimmten Ereignissen zu erhalten.

## <a name="how-to-check-service-health"></a>Überprüfen des Dienststatus

1. Wechseln Sie zum Microsoft 365 Admin Center unter [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) , und melden Sie sich mit einem Administratorkonto an.

    > [!NOTE]
    > Personen, denen die Administratorrolle "Globaler Administrator" oder "Dienstsupport" zugewiesen ist, können den Dienststatus anzeigen. Damit Exchange-, SharePoint- und Skype for Business-Administratoren den Dienststatus anzeigen können, muss ihnen auch die Rolle des Dienstadministrators zugewiesen sein. Weitere Informationen zu Rollen, die den Dienststatus anzeigen können, finden Sie unter [Informationen zu Administratorrollen](../admin/add-users/about-admin-roles.md?preserve-view=true&view=o365-worldwide#commonly-used-microsoft-365-admin-center-roles).

2. Zum Anzeigen des Dienststatus wechseln Sie im Admin Center zu **Status** > **Dienststatus**, oder wählen Sie auf dem **Startdashboard** die Karte **Dienststatus** aus. Die Dashboardkarte gibt an, ob ein Problem mit einem aktiven Dienst vorliegt, und stellt einen Link zur Seite mit Details zum **Dienststatus** bereit.

3. Der Status der einzelnen Clouddienste wird auf der Seite **Dienstatus** in einem Tabellenformat angezeigt.

   ![Ansicht der aktuellen Probleme unter "Dienststatus"](../media/service-health-all-services.png)

Auf der Registerkarte **"Alle Dienste"** (Standardansicht) werden alle Dienste, deren aktueller Integritätsstatus sowie alle aktiven Vorfälle oder Empfehlungen angezeigt. Ein Symbol und ein Status in der Spalte **"Integrität"** geben den Status der einzelnen Dienste an.

Wenn ein aktiver Vorfall oder eine Empfehlung für einen Dienst vorhanden ist, werden diese direkt unter dem Dienstnamen in einer geschachtelten Tabelle aufgeführt. Sie können die geschachtelte Tabelle reduzieren, um die Vorfälle oder Empfehlungen in dieser Ansicht auszublenden, indem Sie links neben dem Dienstnamen auf das Chevronsymbol klicken.   

Um Ihre Ansicht so zu filtern, dass nur alle aktiven Vorfälle angezeigt werden, wählen Sie oben auf der Seite die Registerkarte **"Vorfälle"** aus. Wenn Sie die Registerkarte **"Empfehlungen"** auswählen, werden nur alle aktiven bereitgestellten Empfehlungen angezeigt.

Auf der Registerkarte **"Verlauf"** werden alle Vorfälle und Empfehlungen angezeigt, die innerhalb der letzten sieben oder 30 Tage behoben wurden.

Wenn ein Problem mit einem Microsoft 365 Dienst auftritt und er nicht auf der Seite **"Dienstintegrität"** aufgeführt wird, teilen Sie uns dies mit, indem Sie **"Problem melden"** auswählen und das Kurzformular ausfüllen. Wir sehen uns verwandte Daten und Berichte aus anderen Organisationen an, um zu sehen, wie weit das Problem verbreitet ist und ob es von unserem Dienst stammt. Wenn dies der Fall ist, fügen wir sie als neuen Vorfall oder eine Empfehlung auf der Seite **"Dienststatus"** hinzu, auf der Sie die Lösung nachverfolgen können. Auf der Seite **"Gemeldete Probleme"** werden alle Probleme angezeigt, die Ihr Mandant in diesem Formular gemeldet hat, sowie den Status.

Um Ihre Ansicht anzupassen, welche Dienste im Dashboard angezeigt werden, wählen Sie die Ansicht  >  **"Einstellungen" aus,** und deaktivieren Sie die Kontrollkästchen für die Dienste, die Sie aus der Ansicht des Dienststatus-Dashboards herausfiltern möchten. Stellen Sie sicher, dass das Kontrollkästchen für jeden Dienst aktiviert ist, den Sie überwachen möchten.

Um sich für E-Mail-Benachrichtigungen über neue Vorfälle zu registrieren, die sich auf Ihren Mandanten auswirken, und Statusänderungen für einen aktiven Vorfall, wählen Sie   >  **"Einstellungs-E-Mail"** aus, klicken Sie auf **"Dienstbenachrichtigungen per E-Mail senden"** und geben Sie dann Folgendes an:

- Bis zu zwei E-Mail-Adressen.
- Ob Sie Benachrichtigungen für Vorfälle oder Empfehlungen wünschen
- Die Dienste, für die Sie eine Benachrichtigung wünschen

Sie können auch E-Mail-Benachrichtigungen für einzelne Ereignisse anstelle jedes Ereignisses für einen Dienst abonnieren. Wählen Sie dazu das aktive Problem aus, für das Sie E-Mail-Benachrichtigungsupdates erhalten möchten, wählen Sie **"Benachrichtigungen für dieses Problem verwalten"** aus, und geben Sie dann Folgendes an: 
- Bis zu zwei E-Mail-Adressen.

> [!NOTE]
> Jeder Administrator kann seine Einstellungen festlegen, und das oben genannte Limit von zwei E-Mail-Adressen ist pro Administratorkonto.

> [!TIP]
> Sie können auch die [Microsoft 365 Admin-App](https://go.microsoft.com/fwlink/p/?linkid=627216) auf Ihrem mobilen Gerät verwenden, um den Dienststatus anzuzeigen. Dies ist eine hervorragende Möglichkeit, um mit Pushbenachrichtigungen auf dem laufenden zu bleiben.

### <a name="view-details-of-posted-service-health"></a>Anzeigen von Details des veröffentlichten Dienststatus

Wählen Sie in der Ansicht **"Alle Dienste"** den Problemtitel aus, um die Problemdetailseite anzuzeigen, auf der weitere Informationen zu dem Problem angezeigt werden, einschließlich eines Feeds aller Nachrichten, die während der Arbeit an einer Lösung veröffentlicht wurden. 

[![Screenshot der Dienstempfehlung ](../media/service-health-advisory.png)](../media/service-health-advisory.png#lightbox)

Die Empfehlungs- oder Vorfallzusammenfassung enthält folgende Informationen:

- **Titel**: Eine Zusammenfassung des Problems.
- **ID**: Ein numerischer Bezeichner für das Problem.
- **Dienst**: Der Name des betroffenen Diensts.
- **Letzte Aktualisierung**: Der Zeitpunkt der letzten Aktualisierung der Nachricht zum Dienststatus.
- **Geschätzte Startzeit** – Die geschätzte Zeit, zu der das Problem gestartet wurde.
- **Status**: Wie sich dieses Problem auf den Dienst auswirkt.
- **Auswirkungen auf** benutzer – Eine kurze Beschreibung der Auswirkungen, die dieses Problem auf den Endbenutzer hat.
- **Alle Updates** – Wir veröffentlichen häufig Nachrichten, um Sie über den Fortschritt beim Anwenden einer Lösung zu informieren.

![Screenshot mit Details zum Problem](../media/service-health-advisory-detail.png)

### <a name="translate-service-health-details"></a>Übersetzen von Dienststatusdetails

Wir verwenden maschinelle Übersetzung, um Nachrichten automatisch in Ihrer bevorzugten Sprache anzuzeigen. Lesen Sie [die Sprachübersetzung für Nachrichtencenterbeiträge,](/microsoft-365/admin/manage/language-translation-for-message-center-posts) um weitere Informationen zum Festlegen Ihrer Sprache zu finden.

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

### <a name="message-post-types"></a>Nachrichtenbeitragstypen

| Typ | Definition |
|:-----|:-----|
|**Schnellaktualisierung** | Kurze und häufige inkrementelle Updates für Vorfälle mit großen Auswirkungen, die für alle Kunden verfügbar sind. |
|**Weitere Details** | Diese zusätzlichen Beiträge bieten umfassendere technische und Lösungsdetails, um einen tieferen Einblick in die Behandlung von Vorfällen zu bieten. Dies ist für Mandanten verfügbar, die die gleichen Anforderungen für [Exchange Online Überwachung](/microsoft-365/enterprise/microsoft-365-exchange-monitoring?view=o365-worldwide#requirements)erfüllen. |

### <a name="history"></a>Verlauf

Mit der Dienstintegrität können Sie Ihren aktuellen Integritätsstatus anzeigen und den Verlauf aller Dienstratgeber und Vorfälle anzeigen, die Ihren Mandanten in den letzten 30 Tagen betroffen haben. Wählen Sie die **Verlaufsansicht** aus, um die frühere Integrität aller Dienste anzuzeigen.

Weitere Informationen zu unserer Verpflichtung zur Betriebszeit finden Sie unter ["Transparente Vorgänge aus Microsoft 365."](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

## <a name="related-topics"></a>Verwandte Themen

[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](https://support.office.com/article/0d6dfb17-8582-4172-a9a9-aed798150263)

[Nachrichtencentereinstellungen](../admin/manage/message-center.md?preserve-view=true&view=o365-worldwide#preferences)

[Überprüfen Windows Veröffentlichungsintegrität im Admin Center](/windows/deployment/update/check-release-health)
