---
title: Informationen zu Vertraulichkeitsbezeichnungen
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Verwenden Sie Vertraulichkeitsbezeichnungen aus dem Microsoft Information Protection Framework, um die Daten Ihrer Organisation zu klassifizieren und zu schützen, ohne die Produktivität und Zusammenarbeit der Benutzer zu behindern.
ms.openlocfilehash: 26b916f2a6aa86131da6f0bf9250291bad85dd74
ms.sourcegitcommit: 57afde60f81499f58a9dce13649361c62f2b5a01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "44590926"
---
# <a name="learn-about-sensitivity-labels"></a>Informationen zu Vertraulichkeitsbezeichnungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit & Compliance](https://aka.ms/ComplianceSD).*

Im Rahmen ihrer Arbeit müssen Personen in Ihrer Organisation mit anderen Personen innerhalb und außerhalb der Organisation zusammenarbeiten. Dies bedeutet, dass Inhalte nicht mehr durch eine Firewall geschützt sind – sie können zwischen verschiedenen Geräten, Apps und Diensten hin- und herbewegt werden. Dies soll auf sichere und geschützte Weise geschehen, die den geschäftlichen Anforderungen und Compliancerichtlinien Ihrer Organisation entspricht.

Mit Vertraulichkeitsbezeichnungen aus dem Microsoft Information Protection-Framework, können Sie die Daten Ihrer Organisation klassifizieren und schützen und gleichzeitig sicherstellen, dass Produktivität und Zusammenarbeit der Benutzer nicht beeinträchtigt werden.

Hier ein Beispiel zur Anzeige verfügbarer Vertraulichkeitsbezeichnungen aus der Registerkarte **Start** im Menüband von Excel. In diesem Beispiel wird die angewendete Bezeichnung in der Statusleiste angezeigt:

![Vertraulichkeitsbezeichnung auf dem Excel-Menüband und in der Statusleiste](../media/Sensitivity-label-in-Excel.png)

Vertraulichkeitsbezeichnungen werden ausschließlich für Mandanten in der globalen (öffentlichen) Cloud unterstützt. Vertraulichkeitsbezeichnungen werden derzeit nicht für Mandanten in anderen Clouds (z. B. [nationalen Clouds](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)) unterstützt.

> [!NOTE]
> Vertraulichkeitsbezeichnungen sind in US Government Community (GCC)-Organisationen noch nicht verfügbar.

Um Vertraulichkeitsbezeichnungen anwenden zu können müssen die Benutzer mit ihrem Geschäfts-, Schul- oder Unikonto bei Office angemeldet sein.

Sie können Vertraulichkeitsbezeichnungen zu Folgendem verwenden:
  
- **Erzwingen von Schutzeinstellungen wie Verschlüsselung oder Wasserzeichen für bezeichnete Inhalte.** Z. B. können die Benutzer eine Vertraulichkeitsbezeichnung auf ein Dokument oder eine E-Mail anwenden, und durch diese Bezeichnung kann der Inhalt verschlüsselt und ein Vertraulichkeitswasserzeichen angewendet werden.

- **Schützen von Inhalten in Office-Apps auf verschiedenen Plattformen und Geräten.** Eine Liste der unterstützten Apps finden Sie unter [Verwenden von Vertraulichkeitsbezeichnungen in Office-Apps](sensitivity-labels-office-apps.md).

- **Schützen von Inhalten in Drittanbieter-Apps und -Diensten** mithilfe von Microsoft Cloud App Security. Mit Cloud App Security (CAS) können Sie Inhalte in Drittanbieter-Apps und -Diensten wie z. B. SalesForce, Box oder DropBox erkennen, klassifizieren, beschriften und schützen, auch wenn die Drittanbieter-App oder der Dienst Vertraulichkeitsbezeichnungen nicht liest oder unterstützt.

- **Erweitern von Vertraulichkeitsbezeichnungen auf Drittanbieter-Apps und -Dienste**. Mit dem Microsoft Information Protection SDK können Drittanbieter-Apps Vertraulichkeitsbezeichnungen lesen und Schutzeinstellungen anwenden.

- **Klassifizieren von Inhalten ohne Verwendung von Schutzeinstellungen.** Sie können auch einfach eine Klassifizierung für Inhalte (z. B. einen Aufkleber) zuweisen, die erhalten bleibt und mit wandert, wenn die Inhalte verwendet und freigegeben werden. Sie können diese Klassifizierung verwenden, um Nutzungsberichte zu generieren und Aktivitätsdaten für Ihre vertraulichen Inhalte anzuzeigen. Anhand dieser Informationen können Sie jederzeit auswählen, dass später Schutzeinstellungen angewendet werden.

In allen diesen Fällen können Ihnen Vertraulichkeitsbezeichnungen in Microsoft 365 dabei helfen, die richtigen Aktionen an den richtigen Inhalten auszuführen. Mit Vertraulichkeitsbezeichnungen können Sie Daten organisationsweit klassifizieren und Schutzeinstellungen auf der Grundlage dieser Klassifizierung erzwingen.

## <a name="what-a-sensitivity-label-is"></a>Bedeutung von Vertraulichkeitsbezeichnungen

Wenn Sie einem Dokument oder einer E-Mail eine Vertraulichkeitsbezeichnung zuweisen, gleicht dies einem auf den Inhalt angebrachten Stempel wie z. B.:

- **Anpassbar.** Sie können Kategorien für unterschiedliche Stufen vertraulicher Inhalte in Ihrer Organisation erstellen, z. B. Privat, Öffentlich, Allgemein, Vertraulich und Streng vertraulich.

- **Klartext.** Da die Bezeichnung in den Metadaten des Inhalts als Klartext gespeichert ist, können Apps und Dienste von Drittanbietern ihn lesen und dann bei Bedarf ihre eigenen Schutzaktionen anwenden.

- **Persistent.** Nachdem eine Vertraulichkeitsbezeichnung auf einen Inhalt angewendet wurde, wird diese Bezeichnung in den Metadaten der entsprechenden E-Mail oder des betreffenden Dokuments gespeichert. Dies bedeutet, dass die Bezeichnung mit dem Inhalt, einschließlich der Schutzeinstellungen, hin- und herbewegt werden, und diese Daten werden zur Basis für das Anwenden und Erzwingen von Richtlinien.

In Office-Apps wird eine Vertraulichkeitsbezeichnung Benutzern wie ein Tag für eine E-Mail oder ein Dokument angezeigt.

Jedem Inhaltselement kann eine Vertraulichkeitsbezeichnung zugewiesen werden. Auf ein Element kann sowohl eine einzelne Vertraulichkeitsbezeichnung als auch eine einzelne [Aufbewahrungsbezeichnung](labels.md) angewendet werden.

> [!div class="mx-imgBorder"]
> ![Auf eine E-Mail angewendete Vertraulichkeitsbezeichnung](../media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>Wirkung von Vertraulichkeitsbezeichnungen

> [!NOTE]
> Zusätzlich zur Anwendung von Vertraulichkeitsbezeichnungen auf E-Mails und Dokumente, die aktuell in der Vorschau angezeigt werden, können Sie auch [Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und Microsoft Office SharePoint Online-Websites](sensitivity-labels-teams-groups-sites.md) verwenden.

Nachdem eine Vertraulichkeitsbezeichnung auf eine E-Mail oder ein Dokument angewendet wurde, werden alle konfigurierten Schutzeinstellungen für diese Bezeichnung auf den Inhalt erzwungen. Mit einer Vertraulichkeitsbezeichnung können Sie folgende Aktionen auslösen:

- **Verschlüsseln** Sie nur E-Mails oder E-Mails und Dokumente. Sie können auswählen, welche Benutzer oder Gruppen über Berechtigungen zum Ausführen welcher Aktionen verfügen, und wie lange diese Berechtigungen gültig sind. Sie können z. B. festlegen, dass Benutzer in einer bestimmten Gruppe in einer anderen Organisation nach der Festlegung der Bezeichnung für den Inhalt nur sieben Tage lang berechtigt sind, den Inhalt zu überprüfen. Alternativ können Sie, statt Berechtigungen durch einen Administrator zu definieren, Ihren Benutzern das Zuweisen von Berechtigungen für den Inhalt erlauben, wenn sie die Bezeichnung anwenden. 
    
    Weitere Informationen zu den Einstellungen für die **Verschlüsselungs** beim Erstellen oder Bearbeiten einer Vertraulichkeitsbezeichnung finden Sie unter [Einschränken des Zugriffs auf Inhalte mithilfe der Verschlüsselung in Vertraulichkeitsbezeichnungen](encryption-sensitivity-labels.md).

- **Markieren Sie die Inhalte** beim Verwenden von Office Apps durch Hinzufügen von Wasserzeichen, Kopf- oder Fußzeilen zu E-Mails oder Dokumenten, denen die Bezeichnung zugewiesen wurde. Wasserzeichen können nur auf Dokumente, nicht aber auf E-Mails angewendet werden. Beispielkopfzeile und Wasserzeichen:
    
    ![Auf Dokument angewendetes Wasserzeichen und Kopfzeile](../media/Sensitivity-label-watermark-header.png)
    
    Müssen Sie überprüfen, wann Inhaltsmarkierungen angebracht werden? Siehe [Wenn Office-Apps Markierungen und Verschlüsselungen auf Inhalte anwenden](sensitivity-labels-office-apps.md#when-office-apps-apply-content-marking-and-encryption).
    
    Zeichenfolgenlängen: Wasserzeichen sind auf 255 Zeichen beschränkt. Kopf-und Fußzeilen sind (mit Ausnahme von Excel) auf 1024 Zeichen beschränkt. Bei Excel liegt der Höchstwert bei 255 Zeichen für Kopf-und Fußzeilen, aber in dieser Beschränkung sind nicht sichtbare Zeichen, wie z. B. Formatierungscodes, enthalten. Wenn dieser Wert erreicht ist, wird die eingegebene Zeichenfolge in Excel nicht angezeigt.


- **Schützen von Inhalten in Containern, z. B. Websites und Gruppen**, wenn Sie sich für die Vorschauversion anmelden, um [Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites (Public Preview) zu verwenden](sensitivity-labels-teams-groups-sites.md).
    
    Konfigurationsoptionen für **Website- und Gruppeneinstellungen** werden erst angezeigt, wenn Sie sich für die Vorschauversion anmelden. Beachten Sie, dass diese Bezeichnungskonfiguration nicht dazu führt, dass Dokumente automatisch mit Bezeichnungen versehen werden. Stattdessen werden die Inhalte geschützt, indem die Bezeichnungseinstellungen den Zugriff auf den Container, in dem Dokumente gespeichert sind, steuern. Diese Einstellungen legen die Datenschutzebene fest, bestimmen, ob ein Microsoft 365-Gruppenbesitzer Gäste zur Gruppe hinzufügen kann, und steuern die Zugriffsebene für ein nicht verwaltetes Gerät.

- **Automatisches Anwenden der Bezeichnung in Office-Apps oder Empfehlen einer Bezeichnung.** Sie können auswählen, welche Arten von vertraulichen Informationen mit Bezeichnungen versehen werden sollen, und die Bezeichnung entweder automatisch anwenden oder die Benutzer auffordern, die von Ihnen empfohlene Bezeichnung anzuwenden. Wenn Sie eine Bezeichnung empfehlen, zeigt die Eingabeaufforderung einen von Ihnen ausgewählten Text an. Zum Beispiel:
    
    ![Auffordern zum Zuweisen einer erforderlichen Bezeichnung](../media/Sensitivity-label-Prompt-for-required-label.png)
    
    Weitere Informationen zu den Einstellungen für die **automatische Anwendung von Bezeichnungen für Office-Apps** beim Erstellen oder Bearbeiten einer Vertraulichkeitsbezeichnung finden Sie unter [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md).

### <a name="label-priority-order-matters"></a>Priorität der Bezeichnungen (Reihenfolge wesentlich)

Wenn Sie Ihre Vertraulichkeitsbezeichnungen in Ihrem Admin Center erstellen, werden sie in einer Liste auf der Registerkarte **Vertraulichkeit** auf der Seite **Bezeichnungen** angezeigt. In dieser Liste ist die Reihenfolge der Beschriftungen wichtig, da diese ihre Priorität widerspiegelt. Die restriktivste Vertraulichkeitsbezeichnung, z. B. Streng vertraulich, soll **am Ende** der Liste angezeigt werden, die am wenigsten restriktivste Vertraulichkeitsbezeichnung, z. B. Öffentlich, soll **am Anfang** der Liste angezeigt werden.

Sie können nur eine Vertraulichkeitsbezeichnung auf ein einzelnes Dokument oder eine E-Mail anwenden. Wenn Sie eine Option festlegen, die bestimmt, dass Benutzer eine Begründung für die Änderung der Bezeichnung zu einer niedrigeren Klassifizierung angeben müssen, werden in der Reihung dieser Liste die niedrigeren Klassifizierungen angegeben. Diese Option gilt jedoch nicht für Unterbezeichnungen.

Die Reihenfolge der Unterbezeichnungen wird allerdings mit [automatischen Bezeichnungen](apply-sensitivity-label-automatically.md) verwendet. Wenn Sie Bezeichnungen so konfigurieren, dass Sie automatisch oder als Empfehlung angewendet werden, können daraus mehrere Übereinstimmungen für mehrere Bezeichnungen resultieren. Anhand der Bezeichnungsreihenfolge wird die Bezeichnung ermittelt, die angewendet oder empfohlen werden soll: Die letzte vertrauliche Bezeichnung wird ausgewählt, und dann, falls zutreffend, die letzte Unterbezeichnung.

![Option zum Erstellen einer Unterbezeichnung](../media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>Unterbezeichnungen (Gruppierungsbezeichnungen)

Mit Unterbezeichnungen können Sie ein oder mehrere Bezeichnungen unter einer übergeordneten Bezeichnung gruppieren, die ein Benutzer in einer Office-App sieht. Unter "Vertraulich" kann Ihr Unternehmen beispielsweise mehrere verschiedene Bezeichnungen für bestimmte Arten dieser Klassifizierung verwenden. In diesem Beispiel ist die übergeordnete Bezeichnung "Vertraulich" einfach eine Textbezeichnung ohne Schutzeinstellungen, und da sie Unterbezeichnungen enthält, kann sie nicht auf Inhalt angewendet werden. Stattdessen müssen Benutzer "Vertraulich" auswählen, um die Unterbezeichnungen anzuzeigen, und können dann eine Unterbezeichnung auswählen, die auf Inhalt angewendet wird.

Unterbezeichnungen sind einfach eine Möglichkeit, Benutzern Bezeichnungen in logischen Gruppen zu bereitzustellen. Unterbezeichnungen erben keine Einstellungen von ihrer übergeordneten Bezeichnung. Wenn Sie eine Unterbezeichnung für einen Benutzer veröffentlichen, kann dieser Benutzer diese Unterbezeichnung auf den Inhalt anwenden, aber er kann nicht nur die übergeordnete Bezeichnung anwenden.

Wählen Sie keine übergeordnete Bezeichnung als Standardbezeichnung aus, und konfigurieren Sie keine übergeordnete Bezeichnung so, dass Sie automatisch angewendet (oder empfohlen) wird. Wenn Sie dies tun, wird die übergeordnete Bezeichnung nämlich nicht auf den Inhalt angewendet.

Beispiel für die Anzeige von Unterbeschriftungen für Benutzer:

![Gruppierte Unterbezeichnungen im Menüband](../media/Sensitivity-label-grouped-labels2.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>Bearbeiten oder Löschen einer Vertraulichkeitsbezeichnung

Wenn Sie eine Vertraulichkeitsbezeichnung aus Ihrem Admin Center löschen, wird die Bezeichnung nicht automatisch vom Inhalt entfernt und alle Schutzeinstellungen für den Inhalt werden weiterhin erzwungen.

Wenn Sie eine Vertraulichkeitsbezeichnung bearbeiten, wird die Version der Bezeichnung, die auf Inhalte angewendet wurde, für diese Inhalte erzwungen.

## <a name="what-label-policies-can-do"></a>Wirkung von Bezeichnungsrichtlinien

Nachdem Sie Ihre Vertraulichkeitsbezeichnungen erstellt haben, müssen Sie diese veröffentlichen, um Sie für Personen und Dienste in Ihrer Organisation zur Verfügung zu stellen. Die Vertraulichkeitsbezeichnungen können dann auf Dokumente und E-Mails angewendet werden. Im Gegensatz zu Aufbewahrungsbezeichnungen, die an Speicherorten wie allen Exchange-Postfächern veröffentlicht werden, werden Vertraulichkeitsbezeichnungen für Benutzer oder Gruppen veröffentlicht. Die Vertraulichkeitsbezeichnungen werden dann in Office Apps für diese Benutzer und Gruppen angezeigt.

Mit einer Bezeichnungsrichtlinie können Sie Folgendes bewirken:

- **Entscheiden, welchen Benutzern und Gruppen die Bezeichnungen angezeigt werden.** Die Bezeichnungen können für jeden spezifischen Benutzer oder jede E-Mail-fähige Sicherheits-, Verteiler- oder Microsoft 365-Gruppe (die eine [dynamische Mitgliedschaft](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) in Azure AD haben kann) veröffentlicht werden.

- **Eine Standardbezeichnung** auf alle neuen Dokumente und E-Mails anwenden, die von den in der Bezeichnungsrichtlinie enthaltenen Benutzern und Gruppen erstellt wurden. Diese Option gilt auch für Container, wenn [Vertraulichkeitsbezeichnungen für Microsoft Teams, Microsoft 365-Gruppen und SharePoint-Websites aktiviert sind](sensitivity-labels-teams-groups-sites.md). Ein Benutzer kann die Standardbezeichnung immer ändern, wenn sie für sein Dokument oder seine E-Mail nicht die richtige Bezeichnung ist. 
    
    Sie haben die Möglichkeit, eine als Basisniveau Standardbezeichnung von Schutzeinstellungen festzulegen, die auf alle Ihre Inhalte angewendet werden sollen. Ohne Benutzerschulungen und andere Steuerelemente kann diese Einstellung aber auch zu ungenauen Bezeichnungen führen. Normalerweise empfiehlt es sich nicht, eine Bezeichnung auszuwählen, die Verschlüsselung als Standardbezeichnung für Dokumente anwendet. So müssen z.B. viele Organisationen Dokumente an externe Benutzer freigeben, die möglicherweise nicht über [Apps verfügen, welche die Verschlüsselung unterstützen](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications), oder die möglicherweise kein [Konto verwenden, das autorisiert werden kann](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#supported-scenarios-for-opening-protected-documents).

- **Begründung für das Ändern einer Bezeichnung anfordern.** Sie können festlegen, dass ein Benutzer, der versucht, eine Bezeichnung zu entfernen oder durch eine Bezeichnung mit einer niedrigeren Ordnungszahl zu ersetzen, eine Begründung für diese Aktion angeben muss. Beispiel: Ein Benutzer öffnet ein Dokument mit der Bezeichnung "Vertraulich" (Ordnungszahl 3) und ersetzt diese Bezeichnung durch die Bezeichnung "Öffentlich" (Ordnungszahl 1). Aktuell wird die Begründung nicht zur [Analyse der Bezeichnungen](label-analytics.md) an den Administrator gesendet. Allerdings sendet der [Azure Information Protection-Client für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) diese Informationen an [Azure Information Protection-Analysen](https://docs.microsoft.com/azure/information-protection/reports-aip).

    ![Eingabeaufforderung, in der Benutzer eine Begründung eingeben](../media/Sensitivity-label-justification-required.png)

- **Von Benutzern fordern, dass sie eine Bezeichnung auf ihre E-Mails und Dokumente anwenden**. Dies wird auch obligatorische Bezeichnung genannt: Sie können festlegen, dass eine Bezeichnung angewendet werden muss, bevor Benutzer Dokumente speichern und E-Mails senden können. Die Bezeichnung kann vom Benutzer manuell, und zwar automatisch als Ergebnis einer von Ihnen konfigurierten Bedingung, oder standardmäßig zugewiesen werden (die oben beschriebene Standardbezeichnung). Eine Beispielaufforderung, die in Outlook angezeigt wird, wenn ein Benutzer eine Bezeichnung zuweisen muss:

    ![Eingabeaufforderung in Outlook, durch die der Benutzer zum Anwenden der erforderlichen Bezeichnung aufgefordert wird](../media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)
    
    > [!NOTE]
    > Die obligatorische Kennzeichnung setzt zurzeit den [Azure Information Protection Unified Labeling Client](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) voraus. Dieser Assistent kann nur unter Windows ausgeführt werden, sodass die Funktion derzeit nicht unter Mac, iOS und Android unterstützt wird.
    
    Erwägen Sie die Verwendung dieser Option, um dafür zu sorgen, dass Bezeichnungen in höherem Maß verwendet werden. Ohne Benutzerschulungen kann diese Einstellung jedoch zu ungenauen Bezeichnungen führen. Außerdem kann die obligatorische Kennzeichnung, sofern Sie keine Standardbezeichnung festlegen, dazu führen, dass Ihre Benutzer mit den häufig auftretenden Eingabeaufforderungen frustriert sind. 

- **Link zu einer benutzerdefinierten Hilfeseite bereitstellen** Wenn Ihre Benutzer nicht genau wissen, was Vertraulichkeitsbezeichnungen sind oder wie sie verwendet werden sollten, können Sie eine URL zu weiteren Informationen angeben, die unten im Menü der **Vertraulichkeitsbezeichnungen** in den Office-Apps angezeigt wird:

    ![Links zu weiteren Informationen auf der Schaltfläche „Vertraulichkeit“ im Menüband](../media/Sensitivity-label-learn-more.png)

Nachdem Sie eine Bezeichnungsrichtlinie erstellt haben, die Benutzern und Gruppen Vertraulichkeitsbezeichnungen zuweist, kann es bis zu 24 Stunden dauern, bis die Bezeichnungen in den Office-Anwendungen der Benutzer angezeigt werden.

Es gibt keine Beschränkung für die Anzahl der Vertraulichkeitsbezeichnungen, die Sie erstellen und veröffentlichen können, mit einer Ausnahme: Wenn bei der die Bezeichnung Verschlüsselung angewendet wird, gibt es maximal 500 Bezeichnungen, die Sie erstellen können. Allerdings gilt als bewährte Methode, um den Verwaltungsaufwand für die Administratoren und die Komplexität für die Benutzer zu verringern, die Anzahl der Bezeichnungen möglichst gering zu halten. Praxisnahe Bereitstellungen haben sich als weit weniger effektiv erwiesen, wenn Benutzer mehr als fünf Hauptbezeichnungen oder mehr als fünf Unterbezeichnungen pro Hauptbezeichnung zuordnen.

### <a name="label-policy-priority-order-matters"></a>Priorität der Bezeichnungsrichtlinien (Reihenfolge wesentlich)

Sie können Benutzern die Vertraulichkeitsbezeichnungen zur Verfügung stellen, indem Sie sie in einer Richtlinie zur Vertraulichkeitsbezeichnung veröffentlichen, die in einer Liste auf der Registerkarte **Vertraulichkeitsrichtlinien** auf der Seite **Bezeichnungsrichtlinien** angezeigt wird. Wie bei den Vertraulichkeitsbezeichnungen (siehe [Priorität der Bezeichnungen (Reihenfolge wesentlich)](#label-priority-order-matters)) ist auch die Reihenfolge der Richtlinien zur Vertraulichkeitskennzeichnung wichtig, da sie deren Priorität widerspiegelt. Die Bezeichnungsrichtlinie mit der niedrigsten Priorität wird **am Anfang** und jene mit der höchsten Priorität **am Ende** angezeigt.

Eine Bezeichnungsrichtlinie besteht aus:

- Einer Gruppe von Beschriftungen.
- Dem Bereich der Bezeichnungsrichtlinie, d. h. die Benutzer und Gruppen, die in der Richtlinie enthalten sind.
- Die Einstellungen der oben beschriebenen Bezeichnungsrichtlinie (Standardbezeichnung, Ausrichtung, obligatorische Bezeichnung und Hilfe-Link).

Sie können einen Benutzer in mehrere Bezeichnungsrichtlinien einschließen, und der Benutzer sieht sämtliche Vertraulichkeitsbezeichnungen aus diesen Richtlinien. Ein Benutzer sieht jedoch nur die Richtlinieneinstellungen der Bezeichnungsrichtlinie mit der höchsten Priorität.

Wenn Ihnen die für einen Benutzer oder eine Gruppe erwartete Bezeichnungs oder Bezeichnungsrichtlinieneinstellung nicht angezeigt wird und Sie 24 Stunden gewartet haben, überprüfen Sie die Reihenfolge der Vertraulichkeitsbezeichnungsrichtlinien. Wenn Sie die Bezeichnungsrichtlinien neu anordnen möchten, wählen Sie eine Vertraulichkeits-Bezeichnungsrichtlinie aus > wählen Sie die drei Punkte auf der rechten Seite aus > bewegen Sie sie nach **unten** oder **oben**.

![Option „Verschieben“ auf der Seite für Vertraulichkeits Bezeichnungsrichtlinien](../media/sensitivity-label-policy-priority.png)

Wenn Sie zusätzlich zu Vertraulichkeits- auch Aufbewahrungsbezeichnungen verwenden, ist es wichtig, dass Vorrang für Vertraulichkeits-, nicht jedoch für [Aufbewahrungsbezeichnungsrichtlinien](labels.md#the-principles-of-retention-or-what-takes-precedence) von Bedeutung ist.

## <a name="sensitivity-labels-and-azure-information-protection"></a>Vertraulichkeitsbezeichnungen und Azure Information Protection

Wenn Sie Bezeichnungen mit Azure Information Protection bereitgestellt haben, machen Sie sich mit den folgenden Abschnitten vertraut, bevor Sie mit der Verwendung von Vertraulichkeitsbezeichnungen beginnen.

### <a name="azure-information-protection-labels"></a>Azure Information Protection-Bezeichnungen

> [!NOTE]
> Die Unterstützung der Verwaltung von Azure Information Protection-Bezeichnungen im Azure-Portal wird ab dem**31. März 2021**eingestellt. Weitere Informationen finden Sie in der offiziellen [Benachrichtigung über die Einstellung](https://techcommunity.microsoft.com/t5/azure-information-protection/announcing-timelines-for-sunsetting-label-management-in-the/ba-p/1226179).

Wenn Sie Azure Information Protection-Bezeichnungen verwenden, weil Ihr Mandant noch nicht auf der [vereinheitlichten Bezeichnungs-Plattform](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)ist, empfehlen wir, dass Sie das Erstellen von Vertraulichkeitsbezeichnungen vermeiden, bis Sie die einheitlichen Bezeichnungen aktiviert haben. In diesem Szenario sind die Bezeichnungen, die Sie im Azure-Portal sehen, Azure Information Protection-Bezeichnungen anstelle von Vertraulichkeitsbezeichnungen. Diese Bezeichnungen können vom Azure Information Protection-Client (Classic) auf Windows-Computern verwendet werden, aber nicht von Geräten, auf denen macOS, iOS oder Android ausgeführt wird. Um dieses Problem zu beheben, [überführen Sie diese Bezeichnungen](/azure/information-protection/configure-policy-migrate-labels) in Vertraulichkeitsbezeichnungen. 

Die Metadaten beider Bezeichnungstypen sind kompatibel, sodass Sie Dokumente und E-Mails nach Abschluss der Migration nicht erneut kennzeichnen müssen.

### <a name="azure-information-protection-clients"></a>Azure Information Protection-Clients

Wenn Sie Vertraulichkeitsbezeichnungen in Microsoft 365 Apps for Enterprise-Apps auf Windows-Computern verwenden, können Sie auswählen, ob ein Azure Information Protection-Client oder die in Office integrierte Bezeichnung verwendet werden soll.

Die integrierte Bezeichnung wird in diesen Apps standardmäßig deaktiviert, wenn der Azure Information Protection-Client installiert ist. Weitere Informationen, einschließlich der Möglichkeit, dieses Standardverhalten zu ändern, finden Sie unter [Integrierter Bezeichnungs-Client und der Azure Information Protection-Client](sensitivity-labels-office-apps.md#office-built-in-labeling-client-and-the-azure-information-protection-client).

Auch wenn Sie integrierte Bezeichnungen in Office-Apps verwenden, können Sie außerdem den Azure Information Protection-Client mit einheitlichen Bezeichnungen mit Vertraulichkeitsbezeichnungen für Folgendes verwenden:

- Suchen und Erkennen sensibler Informationen, die lokal gespeichert sind, und (optional) Bezeichnen dieser Inhalte

- Rechtsklickoptionen im Datei-Explorer, mit denen Benutzer Bezeichnungen auf alle Dateitypen anwenden können

- Viewer zum Anzeigen von verschlüsselten Dateien für Text, Bilder oder PDF-Dokumente

- PowerShell-Modul zum Auffinden vertraulicher Informationen in lokalen Dateien sowie Anwenden oder Entfernen von Bezeichnungen und Verschlüsselung für diese Dateien

Wenn Sie noch nicht mit Azure Information Protection vertraut sind, oder wenn Sie ein vorhandener Azure Information Protection-Kunde sind und gerade Ihre Bezeichnungen migriert haben, finden Sie weitere Informationen unter [Auswählen des Bezeichnungsclients, der für Windows-Computer verwendet werden soll](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) in Dokumentation zu Azure Information Protection.

## <a name="sensitivity-labels-and-microsoft-cloud-app-security"></a>Vertraulichkeitsbezeichnungen und Microsoft Cloud App Security

Mit Cloud App Security (CAS) können Sie Inhalte in Drittanbieter-Diensten und -Apps wie z. B. SalesForce, Box oder Dropbox erkennen, klassifizieren, mit Bezeichnungen versehen und schützen. 

Cloud App Security arbeitet sowohl mit Azure Information Protection-Bezeichnungen als auch mit Vertraulichkeitsbezeichnungen zusammen:

- Wenn die Bezeichnungs-Admin Center über ein oder mehrere Vertraulichkeitsbezeichnungen verfügen, die mindestens für einen Benutzer [veröffentlicht](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) wurden: Es werden Vertraulichkeitsbezeichnungen verwendet.

- Wenn die Bezeichnungs-Admin Center über keine veröffentlichten Vertraulichkeitsbezeichnungen verfügen: Es werden Azure Information Protection-Bezeichnungen verwendet.

Eine Anleitung, wie Sie Cloud App Security mit diesen Bezeichnungen verwenden können, finden Sie unter [Azure Information Protection-Integration](https://docs.microsoft.com/cloud-app-security/azip-integration).

## <a name="sensitivity-labels-and-the-microsoft-information-protection-sdk"></a>Vertraulichkeitsbezeichnungen und der Microsoft Information Protection SDK

Da eine Vertraulichkeitsbezeichnung in den Metadaten eines Dokuments als Klartext gespeichert wird, können Apps und Dienste von Drittanbietern diese Bezeichnungsmetadaten lesen und in diese schreiben, um die Bereitstellung Ihrer Bezeichnungen zu ergänzen. Darüber hinaus können Softwareentwickler das [Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk) verwenden, um die Bezeichnungs- und Verschlüsselungsfunktionen auf mehreren Plattformen vollständig zu unterstützen. Weitere Informationen hierzu finden Sie in der [Ankündigung der allgemeinen Verfügbarkeit im Blog der Tech-Community](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). 

Außerdem erfahren Sie mehr über [Partnerlösungen, die in Microsoft Information Protection integriert sind](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).

## <a name="deployment-guidance"></a>Bereitstellungsleitfaden

Siehe [Erste Schritte mit Vertraulichkeitsbezeichnungen](get-started-with-sensitivity-labels.md).

