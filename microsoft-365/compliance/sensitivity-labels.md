---
title: Übersicht über Vertraulichkeitsbezeichnungen
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 12/13/2019
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
description: Mit Vertraulichkeitsbezeichnungen können Sie Ihre vertraulichen Inhalte klassifizieren und schützen, ohne dass die Produktivität Ihrer Mitarbeiter und deren Fähigkeit zur Zusammenarbeit behindert wird. Mithilfe von Vertraulichkeitsbezeichnungen können Sie Schutzeinstellungen wie Verschlüsselung oder Wasserzeichen für bezeichnete Inhalte erzwingen.
ms.openlocfilehash: f411cf5ac91581526c54f718ee83d0beaaaa2d73
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802838"
---
# <a name="overview-of-sensitivity-labels"></a>Übersicht über Vertraulichkeitsbezeichnungen

Im Rahmen ihrer Arbeit müssen Personen in Ihrer Organisation mit anderen Personen innerhalb und außerhalb der Organisation zusammenarbeiten. Dies bedeutet, dass Inhalte nicht mehr durch eine Firewall geschützt sind – sie werden zwischen verschiedenen Geräten, Apps und Diensten hin und her bewegt. Dies soll auf sichere und geschützte Weise geschehen, die den geschäftlichen Anforderungen und Compliancerichtlinien Ihrer Organisation entspricht.

Mithilfe von Vertraulichkeitsbezeichnungen können Sie Ihre vertraulichen Inhalte klassifizieren und schützen, ohne dass die Produktivität Ihrer Mitarbeiter und deren Fähigkeit zur Zusammenarbeit behindert wird.

![Vertraulichkeitsbezeichnung auf dem Excel-Menüband und in der Statusleiste](media/Sensitivity-label-in-Excel.png)

Vertraulichkeitsbezeichnungen werden nur für Mandanten in der globalen (öffentlichen) Cloud unterstützt. Vertraulichkeitsbezeichnungen werden nicht für Mandanten in anderen Clouds (z. B. [nationalen Clouds](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)) unterstützt.

Um Vertraulichkeitsbezeichnungen anwenden zu können müssen die Benutzer mit ihrem Geschäfts-, Schul- oder Unikonto bei Office angemeldet sein.

Sie können Vertraulichkeitsbezeichnungen zu Folgendem verwenden:
  
- **Erzwingen von Schutzeinstellungen wie Verschlüsselung oder Wasserzeichen für bezeichnete Inhalte.** Z. B. können die Benutzer eine Vertraulichkeitsbezeichnung auf ein Dokument oder eine E-Mail anwenden, und durch diese Bezeichnung kann der Inhalt verschlüsselt und ein Vertraulichkeitswasserzeichen angewendet werden.

- **Schützen von Inhalten in Office-Apps auf verschiedenen Plattformen und Geräten.** Eine Liste der unterstützten Apps finden Sie unter [Vertraulichkeitsbezeichnungen in Office-Apps](sensitivity-labels-office-apps.md).

- **Verhindern, dass vertrauliche Inhalte Ihre Organisation auf Geräten unter Windows verlassen**, mithilfe von Microsoft Intune Endpoint Protection. Nachdem eine Vertraulichkeitsbezeichnung auf Inhalte auf einem Windows-Gerät angewendet wurde, kann Endpoint Protection verhindern, dass diese Inhalte in eine Drittanbieter-App, z. B. Twitter oder Gmail, oder auf Wechselmedien, z. B. ein USB-Laufwerk, kopiert werden.

- **Schützen Sie Inhalte in Drittanbieter-Apps und -Diensten** mithilfe von Microsoft Cloud App Security. Mit Cloud App Security (CAS) können Sie Inhalte in Drittanbieter-Apps und -Diensten wie z. B. SalesForce, Box oder DropBox erkennen, klassifizieren, beschriften und schützen, auch wenn die Drittanbieter-App oder der Dienst Vertraulichkeitsbezeichnungen nicht liest oder unterstützt.

- **Erweitern von Vertraulichkeitsbezeichnungen auf Drittanbieter-Apps und -Dienste.** Mit dem Microsoft Information Protection SDK können Drittanbieter-Apps auf [diesen Plattformen](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk) Vertraulichkeitsbezeichnungen lesen und Schutzeinstellungen anwenden.

- **Klassifizieren von Inhalten ohne Verwendung von Schutzeinstellungen.** Sie können auch einfach eine Klassifizierung für Inhalte (z. B. einen Aufkleber) zuweisen, die erhalten bleibt und mit wandert, wenn die Inhalte verwendet und freigegeben werden. Sie können diese Klassifizierung verwenden, um Nutzungsberichte zu generieren und Aktivitätsdaten für Ihre vertraulichen Inhalte anzuzeigen. Anhand dieser Informationen können Sie jederzeit auswählen, dass später Schutzeinstellungen angewendet werden.

In all diesen Fällen können Vertraulichkeitsbezeichnungen in Office 365 Ihnen dabei helfen, die richtigen Maßnahmen für die entsprechenden Inhalte zu treffen. Mit Vertraulichkeitsbezeichnungen können Sie Daten organisationsweit klassifizieren und Schutzeinstellungen basierend auf dieser Klassifizierung durchsetzen.
  
Sie erstellen Vertraulichkeitsbezeichnungen im Microsoft 365 Compliance Center, Microsoft 365 Security Center oder Office 365 Security & Compliance Center unter **Klassifizierung** > **Vertraulichkeitsbezeichnungen**. Diese Vertraulichkeitsbezeichnungen können von Azure Information Protection, Office-Apps und Office 365-Diensten verwendet werden.

Azure Information Protection-Kunden können Ihre Azure Information Protection-Bezeichnungen in den anderen Admin Centern verwenden, damit Ihre Bezeichnungen mit dem Azure-Portal synchronisiert werden, falls Sie eine zusätzliche oder erweiterte Konfiguration ausgewählt haben. **Azure Information Protection-Bezeichnungen und Office 365-Vertraulichkeitsbezeichnungen sind miteinander vollständig kompatibel.** Dies bedeutet z. B., wenn Sie Inhalte mit Azure Information Protection gekennzeichnet haben, müssen Sie Ihre Inhalte nicht klassifizieren oder neu bezeichnen.

## <a name="what-a-sensitivity-label-is"></a>Bedeutung von Vertraulichkeitsbezeichnungen

Wenn Sie einem Dokument oder einer E-Mail eine Vertraulichkeitsbezeichnung zuweisen, hat diese ähnliche Eigenschaften wie ein Tag:

- **Anpassbar.** Sie können Kategorien für unterschiedliche Stufen vertraulicher Inhalte in Ihrer Organisation erstellen, z. B. Privat, Öffentlich, Allgemein, Vertraulich und Streng vertraulich.

- **Klartext.** Da die Beschriftung aus Klartext besteht, ist sie für Drittanbieter-Apps und -Dienste verfügbar, um Schutzmaßnahmen auf mit Bezeichnungen versehene Inhalte anzuwenden.

- **Beständig.** Nachdem eine Vertraulichkeitsbezeichnung auf Inhalte angewendet wurde, bleibt diese in den Metadaten der E-Mail oder des Dokuments erhalten. Dies bedeutet, dass die Bezeichnung einschließlich der Schutzeinstellungen mit dem Inhalt bewegt wird und zur Grundlage für die Anwendung und Durchsetzung von Richtlinien wird.

In den Office-Apps wird eine Vertraulichkeitsbezeichnung einfach als Tag für eine E-Mail oder ein Dokument angezeigt.

Jedem Inhaltselement kann eine Vertraulichkeitsbezeichnung zugewiesen werden. Auf ein Element kann sowohl eine einzelne Vertraulichkeitsbezeichnung als auch eine einzelne [Aufbewahrungsbezeichnung](labels.md) angewendet werden.

![Auf eine E-Mail angewendete Vertraulichkeitsbezeichnung](media/Sensitivity-label-on-email.png)

## <a name="what-sensitivity-labels-can-do"></a>Wirkung von Vertraulichkeitsbezeichnungen

Zusätzlich zu E-Mails und Dokumenten stehen Vertraulichkeitsbezeichnungen in mehreren öffentlichen Vorschauversionen zur Verfügung. Weitere Informationen dazu, welche Möglichkeiten Vertraulichkeitsbezeichnungen für Dateien, Teams, Gruppen und Websites bieten, finden Sie in den folgenden Artikeln:

- [Aktivieren von Vertraulichkeitsbezeichnungen für Office-Dateien in SharePoint und OneDrive (öffentliche Vorschau)](sensitivity-labels-sharepoint-onedrive-files.md)

- [Verwenden von Vertraulichkeitsbezeichnungen für Microsoft Teams, Office 365-Gruppen und SharePoint-Websites (öffentliche Vorschau)](sensitivity-labels-teams-groups-sites.md)

Nachdem eine Vertraulichkeitsbezeichnung auf eine E-Mail oder ein Dokument angewendet wurde, werden die Schutzeinstellungen für diese Bezeichnung auf den Inhalt erzwungen. Mit einer Vertraulichkeitsbezeichnung können Sie folgende Aktionen auslösen:

- **Verschlüsseln** Sie nur E-Mails oder E-Mails und Dokumente. Sie können auswählen, welche Benutzer oder Gruppen über Berechtigungen zum Ausführen welcher Aktionen verfügen, und wie lange diese Berechtigungen gültig sind. Sie können z. B. festlegen, dass Benutzer in einer bestimmten Domäne außerhalb Ihrer Organisation nach der Festlegung der Bezeichnung für den Inhalt nur sieben Tage lang berechtigt sind, den Inhalt zu überprüfen. Alternativ können Sie, statt Berechtigungen selbst zuzuweisen, Ihren Benutzern das Zuweisen von Berechtigungen für den Inhalt erlauben, wenn sie die Bezeichnung anwenden. Weitere Informationen finden Sie unter [Einschränken des Zugriffs auf Inhalte mithilfe der Verschlüsselung in Vertraulichkeitsbezeichnungen](encryption-sensitivity-labels.md).

- **Markieren Sie die Inhalte** durch Hinzufügen von benutzerdefinierten Wasserzeichen, Kopf- oder Fußzeilen zu E-Mails oder Dokumenten, denen die Bezeichnung zugewiesen wurde. Wasserzeichen werden nur auf Dokumente und nicht auf E-Mails angewendet und sind auf 255 Zeichen beschränkt. Kopf- und Fußzeilen sind darüber hinaus auf 1024 Zeichen beschränkt (mit Ausnahme von Excel, wo sie auf 255 oder weniger Zeichen beschränkt sind, abhängig davon, ob das Dokument andere Kopf- oder Fußzeilen enthält, sowie von anderen Faktoren).

    ![Auf Dokument angewendetes Wasserzeichen und Kopfzeile](media/Sensitivity-label-watermark-header.png)

- **Verhindern Sie Datenverlust** durch Aktivieren des Endpunktschutzes in Intune. Wenn vertrauliche Inhalte heruntergeladen werden, können Sie den Verlust von Daten von Windows-Geräten verhindern. So können beispielsweise mit Bezeichnungen versehene Inhalte nicht in Dropbox, Gmail oder auf ein USB-Laufwerk kopiert werden. Bevor Ihre Vertraulichkeitsbezeichnungen Windows Information Protection (WIP) nutzen können, müssen Sie zuerst eine App-Schutzrichtlinie im Azure-Portal erstellen. Weitere Informationen hierzu finden Sie unter [Wie Windows Information Protection Dateien mit einer Vertraulichkeitsbezeichnung schützt](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553).

- **Automatisches Anwenden der Bezeichnung auf Inhalte anwenden, die vertrauliche Informationen enthalten. ** Sie können festlegen, für welchen Typ vertraulicher Informationen die Bezeichnung angewendet werden soll. Die Bezeichnung kann entweder automatisch angewendet werden oder Benutzer werden aufgefordert, die empfohlene Bezeichnung anzuwenden. Wenn Sie eine Bezeichnung empfehlen, wird in der Aufforderung der entsprechende Text angezeigt. Weitere Informationen finden Sie unter [Automatisches Anwenden einer Vertraulichkeitsbezeichnung auf Inhalte](apply-sensitivity-label-automatically.md).

    ![Auffordern zum Zuweisen einer erforderlichen Bezeichnung](media/Sensitivity-label-Prompt-for-required-label.png)

Alle diese Optionen sind verfügbar, wenn Sie eine Vertraulichkeitsbezeichnung erstellen.

![Optionen beim Erstellen einer Vertraulichkeitsbezeichnung](media/Sensitivity-label-create-options.png)

### <a name="label-priority-order-matters"></a>Priorität der Bezeichnungen (Reihenfolge wesentlich)

Wenn Sie Ihre Vertraulichkeitsbezeichnungen erstellen, werden sie in einer Liste auf der Registerkarte **Vertraulichkeit** auf der Seite **Bezeichnungen** angezeigt. In dieser Liste ist die Reihenfolge der Beschriftungen wichtig, da diese ihre Priorität widerspiegelt. Die restriktivste Vertraulichkeitsbezeichnung, z. B. Streng vertraulich, soll **am Ende** der Liste angezeigt werden, die am wenigsten restriktivste Vertraulichkeitsbezeichnung, z. B. Öffentlich, soll **am Anfang** der Liste angezeigt werden.

Sie können eine einzelne Vertraulichkeitsbezeichnung nur auf ein Dokument oder eine E-Mail anwenden. Wenn Sie festlegen, dass Benutzer eine Begründung für die Änderung der Bezeichnung zu einer niedrigeren Klassifizierung angeben müssen, werden in der Reihung dieser Liste die niedrigeren Klassifizierungen angegeben.

![Option zum Erstellen einer Unterbezeichnung](media/Sensitivity-label-sublabel-options.png)

### <a name="sublabels-grouping-labels"></a>Unterbezeichnungen (Gruppierungsbezeichnungen)

Mit Unterbezeichnungen können Sie ein oder mehrere Bezeichnungen unter einer übergeordneten Bezeichnung gruppieren, die ein Benutzer in einer Office-App sieht. Unter "Vertraulich" kann Ihr Unternehmen beispielsweise mehrere verschiedene Bezeichnungen für bestimmte Arten dieser Klassifizierung verwenden. In diesem Beispiel ist die übergeordnete Bezeichnung "Vertraulich" einfach eine Textbezeichnung ohne Schutzeinstellungen, und da sie Unterbezeichnungen enthält, kann sie nicht auf Inhalt angewendet werden. Stattdessen müssen Benutzer "Vertraulich" auswählen, um die Unterbezeichnungen anzuzeigen, und können dann eine Unterbezeichnung auswählen, die auf Inhalt angewendet wird.

Unterbezeichnungen sind einfach eine Möglichkeit, Benutzern Bezeichnungen in logischen Gruppen zu bereitzustellen. Unterbezeichnungen erben keine Einstellungen von ihrer übergeordneten Bezeichnung. Unterbezeichnungen können auf Inhalte angewendet werden, übergeordnete Bezeichnungen hingegen nicht.

Übergeordnete Bezeichnungen sollten nicht als Standardbezeichnungen ausgewählt (siehe nächster Abschnitt) oder so konfiguriert werden, dass sie automatisch angewendet oder empfohlen werden, da eine übergeordnete Bezeichnung nicht auf Inhalte in Office-Apps angewendet wird, die den Azure Information Protection-Client mit einheitlichen Bezeichnungen verwenden.

![Gruppierte Unterbezeichnungen im Menüband](media/Sensitivity-label-grouped-labels.png)

### <a name="editing-or-deleting-a-sensitivity-label"></a>Bearbeiten oder Löschen einer Vertraulichkeitsbezeichnung

Beim Löschen einer Vertraulichkeitsbezeichnung wird diese nicht vom Inhalt entfernt und es werden alle Schutzeinstellungen weiterhin für den Inhalt erzwungen.

Wenn Sie eine Vertraulichkeitsbezeichnung bearbeiten, wird die Version der Bezeichnung, die auf Inhalte angewendet wurde, für diese Inhalte erzwungen.

## <a name="what-label-policies-can-do"></a>Wirkung von Bezeichnungsrichtlinien

Nachdem Sie die Vertraulichkeitsbezeichnungen erstellt haben, müssen Sie sie veröffentlichen, um sie für Personen in Ihrer Organisation zur Anwendung auf Inhalte bereitzustellen. Im Gegensatz zu Aufbewahrungsbezeichnungen, die für Speicherorte, z. B. alle Exchange-Postfächer, veröffentlicht werden, werden Vertraulichkeitsbezeichnungen für Benutzer oder Gruppen veröffentlicht. Vertraulichkeitsbezeichnungen werden dann in Office-Apps für diese Benutzer und Gruppen angezeigt.

Mit einer Bezeichnungsrichtlinie können Sie Folgendes bewirken:

- **Auswählen, welchen Benutzern und Gruppen die Bezeichnungen angezeigt werden.** Bezeichnungen können für E-Mail-aktivierte Sicherheitsgruppen, Verteilergruppen, Office 365-Gruppen oder dynamische Verteilergruppen veröffentlicht werden.

- **Anwenden einer Standardbezeichnung** auf alle neuen Dokumente und E-Mails, die von den in der Bezeichnungsrichtlinie enthaltenen Benutzern und Gruppen erstellt werden. Durch diese Standardbezeichnung kann eine Basisstufe an Schutzeinstellungen festgelegt werden, die auf alle Ihre Inhalte angewendet werden soll.

- **Begründung für das Ändern einer Bezeichnung anfordern** Sie können festlegen, dass wenn Inhalte als vertraulich gekennzeichnet sind und ein Benutzer diese Bezeichnung entfernen oder durch eine niedrigere Klassifizierung (z. B. durch eine Bezeichnung als "öffentlich") ersetzen möchte, er eine Begründung für diese Aktion angeben muss. Aktuell wird die Begründung nicht zur [Analyse der Bezeichnungen](label-analytics.md) an den Administrator gesendet. Allerdings sendet der [Azure Information Protection-Client für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) diese Informationen an [Azure Information Protection-Analysen](https://docs.microsoft.com/azure/information-protection/reports-aip).

    ![Eingabeaufforderung, in der Benutzer eine Begründung eingeben](media/Sensitivity-label-justification-required.png)

- **Anfordern, dass Benutzer eine Bezeichnung auf E-Mails und Dokumente anwenden. ** Wenn Sie möchten, dass alle Inhalte des Benutzers mit Bezeichnungen versehen werden, können Sie festlegen, dass eine Bezeichnung auf alle gespeicherten Dokumente und gesendeten E-Mails angewendet werden muss. Die Bezeichnung kann durch den Benutzer manuell, automatisch als Ergebnis einer Bedingung oder standardmäßig zugewiesen werden (die beschriebene standardmäßige Bezeichnungsoption). Im Folgenden wird eine Eingabeaufforderung in Outlook angezeigt, wenn ein Benutzer eine Bezeichnung zuweisen muss.

    > [!NOTE]
    > Für die obligatorische Kennzeichnung ist ein Azure Information Protection-Abonnement erforderlich. Um diese Funktion zu verwenden, müssen Sie entweder den [Azure Information Protection-Client](https://www.microsoft.com/download/details.aspx?id=53018) oder den höheren [Azure Information Protection-Client für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) herunterladen und installieren. Darüber hinaus wird der Client nur unter Windows ausgeführt, sodass die Funktion derzeit nicht unter Mac, iOS und Android unterstützt wird.

    ![Eingabeaufforderung in Outlook, in der der Benutzer zum Anwenden der erforderlichen Bezeichnung aufgefordert wird](media/sensitivity-labels-mandatory-prompt-aipv2-outlook.PNG)

- **Link zu einer benutzerdefinierten Hilfeseite bereitstellen** Wenn Ihre Benutzer nicht genau wissen, was Vertraulichkeitsbezeichnungen bedeuten oder wie sie verwendet werden sollten, können Sie eine URL zu weiteren Informationen angeben, die unten im Menü der **Vertraulichkeitsbezeichnungen** in den Office-Apps angezeigt wird.

    ![Links zu weiteren Informationen auf der Schaltfläche „Vertraulichkeit“ im Menüband](media/Sensitivity-label-learn-more.png)

Nachdem Sie eine Bezeichnungsrichtlinie erstellt und Benutzern und Gruppen Vertraulichkeitsbezeichnungen zugewiesen haben, werden die Bezeichnungen diesen Personen innerhalb einer Stunde oder weniger in den Office-Apps angezeigt.

### <a name="label-policy-priority-order-matters"></a>Priorität der Bezeichnungsrichtlinien (Reihenfolge wesentlich)

Sie können Benutzern die Vertraulichkeitsbezeichnungen zur Verfügung stellen, indem Sie sie in einer Richtlinie zur Vertraulichkeitsbezeichnung veröffentlichen, die in einer Liste auf der Registerkarte **Vertraulichkeitsrichtlinien** auf der Seite **Bezeichnungsrichtlinien** angezeigt wird. Wie bei den Vertraulichkeitsbezeichnungen (siehe [Priorität der Bezeichnungen (Reihenfolge wesentlich)](#label-priority-order-matters)) ist auch die Reihenfolge der Richtlinien zur Vertraulichkeitskennzeichnung wichtig, da sie deren Priorität widerspiegelt. Die Bezeichnungsrichtlinie mit der niedrigsten Priorität wird **am Anfang** und jene mit der höchsten Priorität **am Ende** angezeigt.

Eine Bezeichnungsrichtlinie besteht aus:

- Einer Gruppe von Beschriftungen.
- Dem Bereich der Bezeichnungsrichtlinie, d. h. die Benutzer und Gruppen, die in der Richtlinie enthalten sind.
- Die Einstellungen der oben beschriebenen Bezeichnungsrichtlinie (Standardbezeichnung, Ausrichtung, obligatorische Bezeichnung und Hilfe-Link).

Sie können einen Benutzer in mehrere Bezeichnungsrichtlinien einschließen, und der Benutzer sieht alle Vertraulichkeitsbezeichnungen aus diesen Richtlinien. Ein Benutzer sieht jedoch nur die Richtlinieneinstellungen der Bezeichnungsrichtlinie mit der höchsten Priorität.

Wenn ein Benutzer oder eine Gruppe in Ihrer Organisation keine Option in der von Ihnen beabsichtigten Bezeichnungsrichtlinie sieht, z.B. eine Standard- oder obligatorische Bezeichnung, überprüfen Sie die Reihenfolge der Vertraulichkeits-Bezeichnungsrichtlinien. Wenn Sie die Bezeichnungsrichtlinien neu anordnen möchten, wählen Sie eine Vertraulichkeits-Bezeichnungsrichtlinie aus > wählen Sie die drei Punkte auf der rechten Seite aus > bewegen Sie sie nach **unten** oder **oben**.

![Option „Verschieben“ auf der Seite für Vertraulichkeits Bezeichnungsrichtlinien](media/sensitivity-label-policy-priority.png)

Prioritäten wirken sich zwar auf Vertraulichkeitsbezeichnungsrichtlinien aus, **nicht** jedoch auf Aufbewahrungsbezeichnungsrichtlinien. Wie in [Grundsätze der Aufbewahrung oder was Vorrang hat](labels.md#the-principles-of-retention-or-what-takes-precedence) erklärt, können Inhalte mehreren Aufbewahrungsrichtlinien unterliegen.

## <a name="how-to-get-started-with-sensitivity-labels"></a>Erste Schritte mit Vertraulichkeitsbezeichnungen

Die ersten Schritte mit Vertraulichkeitsbezeichnungen sind einfach:

1. **Definieren Sie die Bezeichnungen.** Zuerst sollten Sie Ihre Taxonomie für die Definition unterschiedlicher Grade an vertraulichen Inhalten definieren. Verwenden Sie allgemeine Namen oder Ausdrücke, die für die Benutzer sinnvoll sind. Sie können z. B. mit Beschriftungen wie Privat, Öffentlich, Allgemein, Vertraulich und Streng vertraulich beginnen. Mit Unterbezeichnungen können Sie ähnliche Bezeichnungen nach Kategorien gruppieren. Zusätzlich müssen Sie beim Erstellen einer Bezeichnung eine QuickInfo angeben, die in den Office-Apps angezeigt wird, wenn ein Benutzer die Maus über eine Bezeichnung im Menüband bewegt.

1. **Definieren Sie, was die einzelnen Bezeichnungen bewirken.** Konfigurieren Sie dann die Schutzeinstellungen, die den Bezeichnungen zugeordnet werden sollen. Auf Inhalt mit niedriger Vertraulichkeit (Bezeichnung „Allgemein“) wird beispielsweise nur eine Kopf- oder Fußzeile angewendet, während auf vertraulicheren Inhalt (Bezeichnung „Vertraulich“) ein Wasserzeichen, Verschlüsselung und WIP angewendet werden, um dafür zu sorgen, dass nur privilegierte Benutzer darauf zugreifen können.

1. **Definieren Sie, wer die Bezeichnungen erhält.** Nachdem Sie die Bezeichnungen Ihrer Organisation definiert haben, veröffentlichen Sie sie in einer Bezeichnungsrichtlinie, die steuert, welche Benutzer und Gruppen diese Bezeichnungen anzeigen können. Eine einzelne Bezeichnung ist wieder verwendbar – Sie definieren sie einmal und können sie dann in mehreren, unterschiedlichen Benutzern zugewiesenen Bezeichnungsrichtlinien verwenden. Doch damit eine Bezeichnung Inhalten zugewiesen werden kann, müssen Sie die Bezeichnung zuerst veröffentlichen, sodass sie in Office-Apps und anderen Diensten verfügbar ist. Für den Anfang können Sie Ihre Vertraulichkeitsbezeichnungen testen, indem Sie sie nur einigen wenigen Personen zuweisen.

Im Folgenden werden die grundlegenden Schritte des Administrators, des Benutzers und der Office-App bei der Erstellung von Vertraulichkeitsbezeichnungen beschrieben.

![Diagramm mit Workflow für Vertraulichkeitsbezeichnungen](media/Sensitivity-label-flow.png)

## <a name="where-sensitivity-labels-can-appear"></a>Anzeige von Vertraulichkeitsbezeichnungen

Vertraulichkeitsbezeichnungen werden in der Benutzeroberfläche von Office-Apps angezeigt. Informationen zur aktuellen Verfügbarkeit für bestimmte Apps und Plattformen finden Sie unter **Wo ist das Feature heute verfügbar?[.

### <a name="office-apps-on-windows"></a>Office-Apps unter Windows

In Office-Apps auf Geräten unter Windows werden Vertraulichkeitsbezeichnungen auf der Schaltfläche **Vertraulichkeit** auf der Registerkarte **Start** im Menüband angezeigt. Die angewendete Bezeichnung wird auch in der Statusleiste am unteren Rand des Fensters angezeigt.

![Schaltfläche „Vertraulichkeit“ im Menüband von Excel unter Windows](media/Sensitivity-label-Sensitivity-button.png)

### <a name="office-apps-on-the-web"></a>Office-Apps im Web

Informationen zu Vertraulichkeitsbezeichnungen für Office-Apps im Web finden Sie unter [Anwenden von Vertraulichkeitsbezeichnungen auf Dokumente und E-Mails in Office – Web](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

### <a name="office-apps-on-mac"></a>Office-Apps unter Mac

In Office-Apps auf Mac-Geräten werden Vertraulichkeitsbezeichnungen auf der Schaltfläche **Vertraulichkeit** auf der Registerkarte **Start** im Menüband angezeigt. Die angewendete Bezeichnung wird auch in der Statusleiste am unteren Rand des Fensters angezeigt.

![Schaltfläche „Vertraulichkeit“ im Menüband von Office für Mac](media/Sensitivity-label-on-Mac.png)

### <a name="office-apps-on-ios"></a>Office-Apps unter iOS

In Office-Apps auf iOS-Geräten werden Vertraulichkeitsbezeichnungen auf der Schaltfläche **Vertraulichkeit** auf der Registerkarte **Start** im Menüband angezeigt. Die angewendete Bezeichnung wird auch in der Statusleiste am unteren Rand des Fensters angezeigt.

![Schaltfläche „Vertraulichkeit“ im Menüband von Office für iOS](media/Sensitivity-label-on-iOS.png)

### <a name="office-apps-on-android"></a>Office-Apps unter Android

In Office-Apps auf Android-Geräten werden Vertraulichkeitsbezeichnungen auf der Schaltfläche **Vertraulichkeit** auf der Registerkarte **Start** im Menüband angezeigt. Die angewendete Bezeichnung wird auch in der Statusleiste am unteren Rand des Fensters angezeigt.

![Schaltfläche „Vertraulichkeit“ im Menüband von Office für Android](media/Sensitivity-label-on-Android.png)

### <a name="more-information-on-sensitivity-labels-in-office-apps"></a>Weitere Informationen zu Vertraulichkeitsbezeichnungen in Office-Apps

- [Anwenden von Vertraulichkeits-Beschriftungen auf Ihre Dokumente und E-Mails in Office](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
- [Bekannte Probleme beim Anwenden von Vertraulichkeits-Beschriftungen auf Ihren Office-Dateien](https://support.office.com/article/known-issues-when-you-apply-sensitivity-labels-to-your-office-files-b169d687-2bbd-4e21-a440-7da1b2743edc)
- [Vertraulichkeitsbezeichnungen in Office-Apps](sensitivity-labels-office-apps.md)

## <a name="how-sensitivity-labels-work-with-existing-azure-information-protection-labels"></a>Funktionsweise von Vertraulichkeitsbezeichnungen zusammen mit vorhandenen Azure Information Protection-Bezeichnungen

Azure Information Protection-Benutzer können Inhalte unter Windows derzeit mit dem Azure Information Protection-Client für einheitliche Bezeichnungen klassifizieren und mit Bezeichnungen versehen. Vorhandene Azure Information Protection-Bezeichnungen arbeiten nahtlos mit neuen Vertraulichkeitsbezeichnungen zusammen. Das heißt, Sie können:

- Ihre vorhandenen Azure Information Protection-Bezeichnungen für Dokumente und E-Mails beibehalten.
- Ihre vorhandene Azure Information Protection-Bezeichnungskonfiguration beibehalten.

Wenn Sie Azure Information Protection-Bezeichnungen verwenden, wird empfohlen, dass Sie vorerst keine neuen Bezeichnungen in anderen Admin Centern erstellen, bis Sie die Migration abgeschlossen haben. Das [Azure Information Protection-Migrationsthema](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) enthält wichtige Informationen und einige bestimmte Vorsichtsmaßnahmen. Wenn Sie noch nicht bereit zum Migrieren Ihrer Produktionsmandanten zu Vertraulichkeitbezeichnungen sind, gibt es keinen Grund zur Beunruhigung: Derzeit können Ihre Kunden den Azure Information Protection-Client weiterhin verwenden, und Administratoren können weiterhin das Azure-Portal zur Verwaltung verwenden.

## <a name="sensitivity-labels-and-the-azure-information-protection-client"></a>Vertraulichkeitsbezeichnungen und der Azure Information Protection-Client

Wenn Sie den Azure Information Protection-Client in Office für Windows installiert haben, werden Vertraulichkeitsbezeichnungen von Office 365 automatisch deaktiviert.
Informationen dazu, wie Sie dieses Problem beheben können, finden Sie unter [Der in Office integrierte Bezeichnungsclient](sensitivity-labels-office-apps.md#about-the-office-built-in-labeling-client).

## <a name="protect-content-on-windows-devices-by-using-endpoint-protection-in-microsoft-intune"></a>Schützen von Inhalten auf Windows-Geräten mithilfe von Microsoft Intune Endpoint Protection

Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie Windows mitteilen, dass Dateien mit dieser Bezeichnung vertraulich sind und bei Speicherung auf Windows-Geräten vor Datenverlust geschützt werden müssen. Durch diese Option kann sichergestellt werden, dass Inhalte mit dieser Bezeichnung nur an sanktionierte Speicherorte freigegeben oder kopiert werden können, auch wenn sie an einem Endpunkt gespeichert sind. Im Prinzip wird Windows durch Aktivieren dieser Option für eine Vertraulichkeitsbezeichnung mitgeteilt, dass es sich um besonders wichtige Daten handelt, was weitere Verwendungsbeschränkungen garantiert.

Wenn Sie diese Option aktivieren, kann Windows Vertraulichkeitsbezeichnungen in Dokumenten lesen, verstehen, und behandeln sowie Windows Informationen Protection (WIP) automatisch auf Inhalte anwenden, unabhängig davon, wie sie auf ein verwaltetes Windows-Gerät gelangen. Dies trägt zum Schutz von mit Bezeichnungen versehenen Dateien vor unbeabsichtigtem Zugriff, mit oder ohne Verschlüsselung bei.

Windows kann z. B. erkennen, dass einem Word-Dokument auf dem Computer eines Benutzers die Bezeichnung „Vertraulich“ zugewiesen wurde, und WIP kann eine App-Schutzrichtlinie anwenden, um das Kopieren oder Freigeben der Daten von diesem Gerät an einen beliebigen Ort außerhalb des Netzwerks (z. B. ein persönliches OneDrive, persönliche E-Mail-Konten, soziale Medien oder USB-Laufwerke) zu verhindern.

Wenn ein Benutzer versucht, mit Bezeichnungen versehene Inhalte in ein persönliches Gmail-Konto hochzuladen, wird die folgende Meldung angezeigt.

![Nachricht, dass mit Bezeichnungen versehener Inhalt nicht in Gmail kopiert werden kann](media/Sensitivity-label-WIP-Gmail.png)

Und wenn ein Benutzer versucht, mit Bezeichnungen versehene Inhalte auf einem USB-Laufwerk zu speichern, wird die folgende Meldung angezeigt.

![Nachricht, dass mit Bezeichnungen versehener Inhalt nicht auf ein USB-Laufwerk kopiert werden kann](media/Sensitivity-label-WIP-USB-drive.png)

### <a name="important-prerequisites-for-using-wip"></a>Wichtige Voraussetzungen für die Nutzung von WIP

Bevor die Vertraulichkeitsbezeichnungen WIP verwenden können, müssen Sie zuerst die hier beschriebenen Voraussetzungen erfüllen: [Wie Windows Information Protection Dateien mit einer Vertraulichkeitsbezeichnung schützt](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/how-wip-works-with-labels?branch=vsts17546553). In diesem Thema werden die folgenden Voraussetzungen beschrieben:

- Stellen Sie sicher, dass Windows 10, Version 1809 oder höher, ausgeführt wird.
- [Einrichten von Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), das Inhalte für einer Bezeichnung scannt und den entsprechenden WIP-Schutz anwendet. ATP führt einige Aktionen unabhängig von WIP aus, wie beispielsweise die Meldung von Anomalien.
- Erstellen Sie eine WIP-Richtlinie (Windows Informationen Protection), die auf Endpunktgeräte angewendet wird:

  - [Erstellen einer WIP-Richtlinie (Windows Information Protection) mit MDM mithilfe des Azure-Portals für Microsoft Intune](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-intune-azure)
  - [Erstellen und Bereitstellen einer WIP-Richtlinie (Windows Information Protection) mit System Center Configuration Manager](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/create-wip-policy-using-sccm)

## <a name="protect-content-in-third-party-apps-and-services-by-using-microsoft-cloud-app-security"></a>Schützen von Inhalten in Drittanbieter-Apps und -Diensten mithilfe von Microsoft Cloud App Security

Schützen von Inhalten in Drittanbieter-Apps und -Diensten mithilfe von Cloud App Security (CAS) Mit CAS können Sie Inhalte in Drittanbieter-Diensten und -Apps wie z. B. SalesForce, Box oder Dropbox erkennen, klassifizieren, mit Bezeichnungen versehen und schützen. Z. B. wird eine Vertraulichkeitsbezeichnung möglicherweise von Dropbox nicht verstanden, aber CAS kann mit Bezeichnungen versehene Inhalte auch an diesem Speicherort schützen.

Weitere Informationen finden Sie unter [Automatisches Anwenden von Azure Information Protection-Klassifizierungsbezeichnungen](https://docs.microsoft.com/cloud-app-security/use-case-information-protection).

### <a name="important-prerequisites-for-using-cas"></a>Wichtige Voraussetzungen für die Nutzung von CAS

Damit Ihre Vertraulichkeitsbezeichnungen CAS verwenden können, müssen Sie zuerst die hier beschriebenen Voraussetzungen erfüllen: [Automatisches Anwenden von Azure Information Protection-Klassifizierungsbezeichnungen](https://docs.microsoft.com/cloud-app-security/use-case-information-protection). In diesem Thema werden die folgenden Voraussetzungen beschrieben:

- [Aktivieren Sie Cloud App Security und Azure Information Protection](https://docs.microsoft.com/cloud-app-security/azip-integration) für Ihren Mandanten.
- [Verbinden Sie die App](https://docs.microsoft.com/cloud-app-security/enable-instant-visibility-protection-and-governance-actions-for-your-apps) mit Cloud App Security.

## <a name="extend-sensitivity-labels-to-third-party-apps-and-services-by-using-the-microsoft-information-protection-sdk"></a>Erweitern von Vertraulichkeitsbezeichnungen auf Drittanbieter-Apps und -Dienste mithilfe des Microsoft Information Protection SDK

Da eine Vertraulichkeitsbezeichnung als Klartext in den Metadaten des Dokuments gespeichert wird, können Drittanbieter-Apps und -Dienste die Identifizierung und den Schutz von Inhalten mit einer solchen Bezeichnung unterstützen. Die Unterstützung in anderen Apps und Diensten wird ständig erweitert.

Mit dem [Microsoft Information Protection SDK](https://docs.microsoft.com/information-protection/develop/) können Apps und Dienste von Drittanbietern Vertraulichkeitsbezeichnungen lesen und anwenden sowie Schutz auf Dokumente anwenden. Das SDK unterstützt Apps auf [diesen Plattformen](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk).

Mithilfe des SDK können Sie Inhalte in einer Weise klassifizieren und schützen, die mit anderen Microsoft Information Protection-Apps und -Diensten wie Office-Apps, Office 365-Diensten, dem Azure Information Protection-Scanner, Microsoft Cloud App Security und anderen Partnerlösungen funktioniert. Hier finden Sie z. B. Informationen über die [Unterstützung für Vertraulichkeitsbezeichnungen in Adobe Acrobat](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Starting-October-use-Adobe-Acrobat-Reader-for-PDFs-protected-by/ba-p/262738).

Weitere Informationen zum Microsoft Information Protection SDK finden Sie in der [Ankündigung im Tech Community-Blog](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Microsoft-Information-Protection-SDK-Now-Generally-Available/ba-p/263144). Sie finden auch Informationen zu [Partnerlösungen, die in Microsoft Information Protection integriert sind](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/Microsoft-Information-Protection-showcases-integrated-partner/ba-p/262657).

## <a name="permissions-required-to-create-sensitivity-labels"></a>Für das Erstellen von Vertraulichkeitsbezeichnungen erforderliche Berechtigungen

Mitglieder Ihres Complianceteams, die Vertraulichkeitsbezeichnungen erstellen, benötigen Berechtigungen für das Microsoft 365 Compliance Center, das Microsoft 365 Security Center oder das Office 365 Security & Compliance Center. Standardmäßig hat Ihr Mandantenadministrator Zugriff auf diese Admin Center und kann Compliance Officer und anderen Personen Zugriff gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu erteilen. Zu diesem Zweck wird Folgendes empfohlen: Gehen Sie zur Seite **Berechtigungen** des jeweiligen Admin Centers und fügen Sie dann der Rollengruppe **Complianceadministrator** oder **Sicherheitsadministrator** Mitglieder hinzu.

Weitere Informationen finden Sie unter [Freigeben des Benutzerzugriffs auf das Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Diese Berechtigungen sind nur erforderlich, um Bezeichnungen und eine Bezeichnungsrichtlinie zu erstellen und anzuwenden. Für die Durchsetzung von Richtlinien ist kein Zugriff auf Inhalte erforderlich.
