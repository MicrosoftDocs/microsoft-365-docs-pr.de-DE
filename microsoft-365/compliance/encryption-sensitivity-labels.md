---
title: Einschränken des Zugriffs auf Inhalte mithilfe der Verschlüsselung in Vertraulichkeitsbezeichnungen
ms.author: stephow
author: stephow-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie den Zugriff auf Inhalte beschränken, auf die die Bezeichnung angewendet wird. Vertraulichkeitsbezeichnungen können Verschlüsselung zum Schutz von Inhalten verwenden.
ms.openlocfilehash: a30f5d6168ea8118ef6b30ff26a429857affaa4a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081490"
---
# <a name="restrict-access-to-content-by-using-encryption-in-sensitivity-labels"></a>Einschränken des Zugriffs auf Inhalte mithilfe der Verschlüsselung in Vertraulichkeitsbezeichnungen

Wenn Sie eine Vertraulichkeitsbezeichnung erstellen, können Sie den Zugriff auf Inhalte beschränken, auf die die Bezeichnung angewendet wird. Mit den Verschlüsselungseinstellungen für eine Vertraulichkeitsbezeichnung können Sie beispielsweise Inhalte so schützen, dass:

- Nur Benutzer in Ihrer Organisation ein vertrauliches Dokument oder vertrauliche E-Mails öffnen können.
- Nur Benutzer in der Marketingabteilung das Ankündigungsdokument oder die Ankündigungs-E-Mail für die Werbeaktion bearbeiten und drucken können, während alle anderen Benutzer in der Organisation dieses Dokument oder diese E-Mail nur lesen können.
- Benutzer eine E-Mail nicht weiterleiten oder Informationen daraus kopieren können, die Neuigkeiten zur internen Neuorganisation enthalten.
- Die aktuelle Preisliste, die an Geschäftspartner gesendet wird, kann nach einem angegebenen Datum nicht geöffnet werden.

Wenn ein Dokument oder eine E-Mail verschlüsselt ist, wird Zugriff auf den Inhalt so eingeschränkt, dass:

- Er nur von Benutzern entschlüsselt werden kann, die durch die Verschlüsselungseinstellungen der Bezeichnung dazu autorisiert sind.
- Er immer verschlüsselt bleibt, unabhängig davon, wo er sich befindet (innerhalb oder außerhalb der Organisation), auch dann, wenn die Datei umbenannt wird.
- Er sowohl im Ruhezustand (z. B. in einem OneDrive-Konto) als auch während der Übertragung (z. B. eine gesendete E-Mail) verschlüsselt ist.

Als Administrator können Sie beim Erstellen einer Vertraulichkeitsbezeichnung eine der folgenden Optionen auswählen:

- **Berechtigungen sofort zuweisen**, um genau zu bestimmen, welche Benutzer welche Berechtigungen für Inhalte mit dieser Bezeichnung erhalten.
- **Benutzern die Zuweisung von Berechtigungen überlassen**, wenn sie die Bezeichnung auf Inhalte anwenden. Auf diese Weise ermöglichen Sie Personen in Ihrer Organisation eine gewisse Flexibilität, die sie möglicherweise benötigen, um untereinander zusammenarbeiten und ihre Aufgaben erfüllen zu können.

Die Verschlüsselungseinstellungen sind verfügbar, wenn Sie eine Vertraulichkeitzbezeichnung im Microsoft 365 Compliance Center, Microsoft 365 Security Center oder Office 365 Security & Compliance Center erstellen. Wählen Sie im linken Navigationsbereich **Klassifizierung** > **Vertraulichkeitsbezeichnung** > **Bezeichnung erstellen** aus.

## <a name="how-encryption-works"></a>Funktionsweise der Verschlüsselung

Die Verschlüsselung verwendet Azure Rights Management (Azure RMS). Azure RMS verwendet Verschlüsselungs-, Identitäts- und Autorisierungsrichtlinien. Weitere Informationen hierzu finden Sie unter [Was ist Azure Rights Management?](https://docs.microsoft.com/de-DE/azure/information-protection/what-is-azure-rms)

## <a name="how-to-turn-on-encryption-for-a-sensitivity-label"></a>Aktivieren der Verschlüsselung für eine Vertraulichkeitsbezeichnung

Setzen Sie zunächst **Verschlüsselung** auf **Ein**, und wählen Sie dann eine der folgenden Optionen aus:

- **Berechtigungen sofort zuweisen**, damit Sie genau bestimmen können, welche Benutzer welche Berechtigungen für Inhalte mit dieser Bezeichnung erhalten. Weitere Informationen hierzu finden Sie im nächsten Abschnitt [Berechtigungen sofort zuweisen](#assign-permissions-now).
- **Benutzern die Zuweisung von Berechtigungen überlassen**, wenn sie die Bezeichnung auf Inhalte anwenden. Auf diese Weise ermöglichen Sie Personen in Ihrer Organisation eine gewisse Flexibilität, die sie möglicherweise benötigen, um untereinander zusammenarbeiten und ihre Aufgaben erfüllen zu können. Weitere Informationen hierzu finden Sie weiter unten im Abschnitt [Benutzern die Zuweisung von Berechtigungen überlassen](#let-users-assign-permissions).

Liegt beispielsweise eine Vertraulichkeitsbezeichnung namens **Streng vertraulich** vor, die auf Ihre vertraulichsten Inhalte angewendet wird, können Sie jetzt festlegen, wer welche Art von Berechtigungen für diese Inhalte erhält.

Wenn Sie hingegen über eine Vertraulichkeitsbezeichnung namens **Geschäftsverträge** verfügen und der Workflow in Ihrer Organisation erfordert, dass Ihre Mitarbeiter mit anderen Personen auf Ad-hoc-Basis an diesen Inhalten zusammenarbeiten, können Sie zulassen, dass Ihre Benutzer jeweils entscheiden, wer eine Berechtigung erhält, wenn sie diese Bezeichnung zuweisen. Diese Flexibilität fördert die Produktivität Ihrer Benutzer und verringert die Anfragen an Ihre Administratoren, Vertraulichkeitsbezeichnungen für spezifische Szenarios zu erstellen oder zu aktualisieren.

![Option zum Hinzufügen von benutzer- oder administratordefinierten Berechtigungen](media/sensitivity-label-user-or-admin-defined-permissions.png)

## <a name="assign-permissions-now"></a>Berechtigungen sofort zuweisen

Steuern Sie über die folgenden Optionen, wer auf E-Mails oder Dokumente zugreifen kann, auf die eine bestimmte Bezeichnung angewendet wurde. Sie haben folgende Möglichkeiten:

1. **Verschlüsselung sowohl auf E-Mails als auch auf Dokumente oder nur auf E-Mails anwenden** Wenn Sie sich nur für E-Mails entscheiden, werden Nachrichten mit dieser Bezeichnung in Outlook verschlüsselt, aber Dokumente mit dieser Bezeichnung werden in anderen Apps wie Word oder PowerPoint nicht verschlüsselt. 
2. **Zulassen, dass Zugriff auf gekennzeichnete Inhalte abläuft**, entweder an einem bestimmten Datum oder nach einer bestimmten Anzahl von Tagen, nachdem die Bezeichnung angewendet wurde. Nach dieser Zeit können Benutzer das gekennzeichnete Element nicht mehr öffnen. Wenn Sie ein Datum angeben, gilt dieses ab Mitternacht an diesem Tag in Ihrer aktuellen Zeitzone. (Beachten Sie, dass einige E-Mail-Clients aufgrund ihrer Cachingmechanismen den Ablauf nicht durchsetzen können und E-Mails anzeigen, deren Ablaufdatum überschritten ist.)
3. **Offlinezugriff zulassen** entweder „niemals“, „immer“ oder für eine bestimmte Anzahl von Tagen, nachdem die Bezeichnung angewendet wurde. Wenn Sie den Offlinezugriff jedoch auf „nie“ oder eine Anzahl von Tagen einschränken, müssen Benutzer erneut authentifiziert werden, und ihr Zugriff wird protokolliert. Weitere Informationen finden Sie im nächsten Abschnitt zur Verwendungslizenz von Rights Management.

![Einstellungen für von Administratoren definierte Berechtigungen](media/sensitivity-encryption-settings-for-admin-defined-permissions.png)

### <a name="rights-management-use-license-for-offline-access"></a>Rights Management-Verwendungslizenz für den Offlinezugriff

Wenn ein Benutzer ein Dokument oder eine E-Mail, das bzw. die durch eine Vertraulichkeitsbezeichnung geschützt ist, offline öffnet, wird dem Benutzer eine Rights Management-Verwendungslizenz für diese Inhalte gewährt. Diese Verwendungslizenz ist ein Zertifikat, das die Nutzungsrechte des Benutzers für das Dokument oder die E-Mail sowie den Verschlüsselungsschlüssel enthält, der für die Verschlüsselung des Inhalts verwendet wurde. Die Verwendungslizenz enthält auch ein Ablaufdatum, wenn eines festgelegt wurde, und eine Angabe, wie lange die Verwendungslizenz gültig ist.

Wenn kein Ablaufdatum festgelegt wurde, beträgt die Standardeinstellung für die Gültigkeitsdauer der Verwendungslizenz für einen Mandanten 30 Tage. Für die Dauer der Verwendungslizenz muss der Benutzer nicht erneut authentifiziert oder für den Inhalt erneut autorisiert werden. Auf diese Weise kann der Benutzer das geschützte Dokument oder die geschützte E-Mail weiterhin ohne Internetverbindung öffnen. Wenn der Gültigkeitszeitraum für die Verwendungslizenz abläuft, muss der Benutzer beim nächsten Zugriff auf das geschützte Dokument oder die geschützte E-Mail erneut authentifiziert und erneut autorisiert werden.

Neben der erneuten Authentifizierung wird auch die Richtlinien- und die Benutzergruppenmitgliedschaft erneut bewertet. Dies bedeutet, dass bei Benutzern unterschiedliche Zugriffsergebnisse für dasselbe Dokument oder dieselbe E-Mail auftreten könnten, wenn es seit dem letzten Zugriff auf den Inhalt Änderungen in der Richtlinien- oder Gruppenmitgliedschaft gab.

Informationen zum Ändern der Standardeinstellung von 30 Tagen finden Sie unter [Rights Management-Verwendungslizenz](https://docs.microsoft.com/de-DE/azure/information-protection/configure-usage-rights#rights-management-use-license).

### <a name="assign-permissions-to-specific-users-or-groups"></a>Zuweisen von Berechtigungen für bestimmte Benutzer oder Gruppen

Sie können bestimmten Personen Berechtigungen erteilen, sodass nur sie mit dem gekennzeichneten Inhalt interagieren können.

Dies ist ein schneller und einfacher Prozess in zwei Schritten:

1. Zuerst fügen Sie Benutzer oder Gruppen hinzu, denen Berechtigungen für gekennzeichnete Inhalte erteilt werden.
2. Dann wählen Sie die Berechtigungen aus, die diese Benutzer für die gekennzeichneten Inhalte haben.

![Optionen zum Zuweisen von Berechtigungen zu Benutzern](media/Sensitivity-Assign-permissions-settings.png)

#### <a name="add-users-or-groups"></a>Hinzufügen von Benutzern und Gruppen

Wenn Sie Berechtigungen zuweisen, können Sie folgende Optionen auswählen:

- Jeder in Ihrem Unternehmen (alle Mandantenmitglieder). Diese Einstellung schließt Gastkonten aus.
- Bestimmte Benutzer oder E-Mail-aktivierte Sicherheitsgruppen, Verteilergruppen, Office 365-Gruppen oder dynamische Verteilergruppen. 
- Eine E-Mail-Adresse oder Domäne außerhalb Ihrer Organisation, z. B. gmail.com, outlook.com oder hotmail.com.

Wenn Sie alle Mandantenmitglieder auswählen oder das Verzeichnis durchsuchen, müssen die Benutzer oder Gruppe eine E-Mail-Adresse aufweisen.

Als bewährte Methode sollten Sie besser Gruppen anstelle von Benutzern verwenden. Dadurch wird die Konfiguration einfacher.

#### <a name="choose-permissions"></a>Berechtigungen auswählen

Wenn Sie die Berechtigungen für diese Benutzer oder Gruppen auswählen, können Sie folgende Optionen auswählen:

- Eine [vordefinierte Berechtigungsstufe](https://docs.microsoft.com/de-DE/azure/information-protection/configure-usage-rights#rights-included-in-permissions-levels) mit einer bereits festgelegten Gruppen von Rechten, z. B. Mitverfasser oder Überprüfer.
- Eine benutzerdefinierte Gruppe von Berechtigungen, aus der Sie beliebige Berechtigungen auswählen können.

Weitere Informationen zu den einzelnen Berechtigungen finden Sie unter [Nutzungsrechte und Beschreibungen](https://docs.microsoft.com/de-DE/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions).  

![Optionen zum Auswählen bereits festgelegter oder benutzerdefinierter Berechtigungen](media/Sensitivity-Choose-permissions-settings.png)

Beachten Sie, dass dieselbe Bezeichnung unterschiedlichen Benutzern unterschiedliche Berechtigungen erteilen kann. Eine einzelne Bezeichnung kann beispielsweise einige Benutzer als „Überprüfer“ und einen anderen Benutzer als „Mitverfasser“ zuweisen, wie nachfolgend dargestellt.

Weisen Sie hierfür Benutzern und Gruppen Berechtigungen zu, und speichern Sie die Einstellungen. Wiederholen Sie dann diese Schritte, und fügen Sie jedes Mal Benutzer hinzu, weisen diesen Berechtigungen zu, und speichern die Einstellungen. Sie können dies so oft wie erforderlich wiederholen, um unterschiedliche Berechtigungen für unterschiedliche Benutzer zu definieren.

![Unterschiedliche Benutzer mit unterschiedlichen Berechtigungen](media/Sensitivity-Multiple-users-permissions.png)

#### <a name="rights-management-issuer-user-applying-the-sensitivity-label-always-has-full-control"></a>Rights Management-Aussteller (Benutzer, der die Vertraulichkeitsbezeichnung anwendet) hat immer Vollzugriff

Die Verschlüsselung für eine Vertraulichkeitsbezeichnung verwendet Azure RMS. Wenn ein Benutzer eine Vertraulichkeitsbezeichnung anwendet, um ein Dokument oder eine E-Mail mithilfe von Azure RMS zu schützen, wird dieser Benutzer der Rights Management-Aussteller für diesen Inhalt.

Der Rights Management-Aussteller erhält immer Vollzugriff für das Dokument oder die E-Mail. Außerdem gilt:

- Wenn die Schutzeinstellungen ein Ablaufdatum umfassen, kann der Rights Management-Aussteller das Dokument oder die E-Mail nach diesem Datum immer noch öffnen und bearbeiten.
- Der Rights Management-Aussteller kann immer offline auf das Dokument oder die E-Mail zugreifen.
- Der Rights Management-Aussteller kann ein Dokument weiterhin öffnen, nachdem es gesperrt wurde.

Weitere Informationen finden Sie unter [Rights Management-Aussteller und Rights Management-Besitzer](https://docs.microsoft.com/de-DE/azure/information-protection/configure-usage-rights#rights-management-issuer-and-rights-management-owner).

## <a name="let-users-assign-permissions"></a>Benutzern die Zuweisung von Berechtigungen überlassen

Sie können mithilfe dieser Optionen Benutzern erlauben, Berechtigungen zuzuweisen, wenn sie eine Vertraulichkeitsbezeichnung manuell auf Inhalte anwenden:

- In Outlook kann ein Benutzer Einschränkungen durchsetzen, die der Option **Nicht weiterleiten** entsprechen. Diese Option wird in Outlook unter Windows systemintern unterstützt und erfordert keine Installation des Azure Information Protection-Clients für einheitliche Bezeichnungen.
- In Word, PowerPoint und Excel wird ein Benutzer aufgefordert, eine Berechtigungsstufe für bestimmte Benutzer, Gruppen oder Organisationen auszuwählen. Diese Option wird in diesen Office-Apps nicht systemintern unterstützt, Ihre Benutzer müssen deshalb den Azure Information Protection-Client für einheitliche Bezeichnungen installieren.

Durch diese Optionen wird festgelegt, in welchen Apps die Vertraulichkeitsbezeichnung angezeigt wird:

- Wenn für die Vertraulichkeitsbezeichnung nur die Option "Outlook" aktiviert ist, wird die Bezeichnung den Benutzern nur in Outlook angezeigt.
- Wenn für die Vertraulichkeitsbezeichnung nur die Optionen "Word", "PowerPoint" und "Excel" aktiviert sind, wird die Bezeichnung nur in diesen Apps angezeigt.
- Wenn für die Vertraulichkeitsbezeichnung beide Optionen aktiviert sind, wird die Bezeichnung den Benutzern in allen verfügbaren Apps angezeigt: Outlook, Word, PowerPoint und Excel.

Eine Vertraulichkeitsbezeichnung, bei der Benutzer Berechtigungen zuweisen können, kann nur manuell von Benutzern angewendet werden. Sie kann nicht automatisch angewendet oder als empfohlene Bezeichnung genutzt werden.

> [!NOTE]
> Das Zulassen der Zuweisung von Berechtigungen durch Benutzer erfordert ein Azure Information Protection-Abonnement. Wenn Sie dieses Feature in Word, PowerPoint und Excel verwenden möchten, müssen Sie den [Azure Information Protection-Client für einheitliche Bezeichnungen](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) herunterladen und installieren. Wir arbeiten an der systeminternen Unterstützung dieses Features in diesen Office-Apps, sodass Sie dafür nicht den Azure Information Protection-Client benötigen. Außerdem kann der Client nur unter Windows ausgeführt werden, sodass dieses Feature unter Mac, iOS, Android oder Office im Web noch nicht unterstützt wird.

![Verschlüsselungseinstellungen für benutzerdefinierte Berechtigungen](media/sensitivity-encryption-settings-for-user-defined-permissions.png)

### <a name="outlook-restrictions"></a>Einschränkungen in Outlook

Wenn ein Benutzer in Outlook eine Vertraulichkeitsbezeichnung anwendet, die ihm das Zuweisen von Berechtigungen für eine Nachricht gestattet, entsprechen die Einschränkungen der Option "Nicht weiterleiten". Der Benutzer sieht oben in der Nachricht den Namen und die Beschreibung der Bezeichnung, die den Inhalt als geschützt ausweist. Anders als in Word, PowerPoint und Excel (mehr dazu im [nächsten Abschnitt](#word-powerpoint-and-excel-permissions)) werden die Benutzer hier nicht aufgefordert, bestimmte Berechtigungen auszuwählen.

![Auf eine E-Mail angewendete Vertraulichkeitsbezeichnung in Outlook](media/sensitivity-label-outlook-protection-applied.png)

Wenn die Option "Nicht weiterleiten" auf eine E-Mail angewendet wird, wird diese E-Mail verschlüsselt und die Empfänger müssen authentifiziert werden. Die Empfänger können dann die Nachricht nicht weiterleiten, drucken oder kopieren. Wenn beispielsweise im Outlook-Client die Schaltfläche "Weiterleiten" nicht verfügbar ist, sind die Menüoptionen "Speichern unter" und "Drucken" ebenfalls nicht verfügbar, und Sie können in den Feldern "An", CC oder Bcc keine Empfänger hinzufügen oder ändern.

Für ungeschützte Office-Dokumente, die sich im Anhang der E-Mail befinden, werden automatisch die gleichen Beschränkungen übernommen. Die für diese Dokumente geltenden Nutzungsrechte sind "Inhalt bearbeiten", "Bearbeiten", "Speichern", "Anzeigen", "Öffnen", "Lesen" und "Makros zulassen". Wenn der Benutzer andere Nutzungsrechte für eine Anlage wünscht, oder wenn es sich bei der Anlage nicht um ein Office-Dokument handelt, das die Vererbung des Schutzes unterstützt, muss der Benutzer die Datei schützen, bevor er sie an die E-Mail anfügt.

### <a name="word-powerpoint-and-excel-permissions"></a>Berechtigungen in Word, PowerPoint und Excel

Wenn ein Benutzer in Word, PowerPoint oder Excel eine Vertraulichkeitsbezeichnung anwendet, die ihm das Zuweisen von Berechtigungen für ein Dokument gestattet, wird er aufgefordert, den Inhalt wie nachstehend beschrieben zu schützen.

Er hat folgende Möglichkeiten:

- Er kann eine Berechtigungsstufe auswählen, z. B. "Betrachter" (dadurch wird nur die Berechtigung "Nur anzeigen" zugewiesen) oder "Mitautor" (mit Berechtigungen zum "Anzeigen", "Bearbeiten", "Kopieren" und "Drucken").
- Er kann Benutzer, Gruppen oder Organisationen auswählen. Dies kann Personen innerhalb und außerhalb Ihrer Organisation umfassen.
- Er kann ein Ablaufdatum festlegen, nach dem die ausgewählten Benutzer nicht mehr auf die betreffenden Inhalte zugreifen können. Weitere Informationen finden Sie im vorstehenden Abschnitt [Rights Management-Verwendungslizenz für den Offlinezugriff](#rights-management-use-license-for-offline-access).

![Optionen für Benutzer für den Schutz durch benutzerdefinierte Berechtigungen](media/sensitivity-aip-custom-permissions-dialog.png)

## <a name="what-happens-to-existing-encryption-when-a-labels-applied"></a>Was mit einer vorhandenen Verschlüsselung geschieht, wenn eine Bezeichnung angewendet wird

Bevor eine Vertraulichkeitsbezeichnung auf Inhalte angewendet wird, ist es möglich, dass ein Benutzer die Inhalte durch Anwenden einer anderen Schutzeinstellung bereits verschlüsselt hat. Ein Benutzer kann beispielsweise Folgendes angewendet haben:

- Die Option **Nicht weiterleiten**.
- Benutzerdefinierten Schutz mithilfe des Azure Information Protection-Clients mit einheitlichen Bezeichnungen.
- Eine RMS-Vorlage (Rights Management Service), die die Inhalte verschlüsselt, aber keiner Bezeichnung zugewiesen ist.

In dieser Tabelle wird beschrieben, was mit einer vorhandenen Verschlüsselung geschieht, wenn eine Vertraulichkeitsbezeichnung auf diese Inhalte angewendet wird.
<br/>
<br/>

| |**Benutzer wendet eine Vertraulichkeitsbezeichnung bei deaktivierter Verschlüsselung an**|**Benutzer wendet eine Vertraulichkeitsbezeichnung bei aktivierter Verschlüsselung an**|**Benutzer wendet eine Bezeichnung mit „Schutz entfernen“ an**<sup>1</sup>|
|:-----|:-----|:-----|:-----|
|**Nicht weiterleiten**|E-Mail – Schutz wird entfernt.<br/>Dokument – Schutz wird beibehalten.|Bezeichnungsschutz wird angewendet.|**Nicht weiterleiten** wird entfernt.|
|**Benutzerdefinierter Schutz**<sup>1</sup>|Schutz wird beibehalten.|Bezeichnungsschutz wird angewendet.|Benutzerdefinierter Schutz wird entfernt.|
|**Azure RMS-Vorlage**|Schutz wird beibehalten.|Bezeichnungsschutz wird angewendet.|Benutzerdefinierter Schutz wird entfernt.|

<sup>1</sup>Dies wird nur im Azure Information Protection-Bezeichnungsclient unterstützt.

## <a name="storing-encrypted-content-in-onedrive-and-sharepoint"></a>Speichern von verschlüsselten Inhalten in OneDrive und SharePoint

Wenn Verschlüsselung auf Dateien in OneDrive und SharePoint angewendet wird, kann der Dienst den Inhalt dieser Dateien nicht verarbeiten. Dies bedeutet, das Features wie Gemeinsame Dokumenterstellung, eDiscovery, Suche, Delve und andere Features für die Zusammenarbeit nicht funktionieren. DLP-Richtlinien können nur für Metadaten (einschließlich Office 365-Bezeichnungen) angewendet werden, aber nicht für den Inhalt verschlüsselter Dateien (z. B. Kreditkartennummern in Dateien) verwendet werden.

Dies gilt nur für Inhalte, die in OneDrive und SharePoint gespeichert sind. In Exchange Online verwenden E-Mail-Flussregeln (auch als Transportregeln bezeichnet) das [Administratorkonto](https://docs.microsoft.com/de-DE/azure/information-protection/configure-super-users), damit sie verschlüsselte Inhalte überprüfen und DLP-Richtlinien erzwingen können.

## <a name="important-prerequisites"></a>Wichtige Voraussetzungen

Bevor Sie Verschlüsselung verwenden können, müssen Sie möglicherweise die folgenden Aufgaben ausführen.

### <a name="activating-azure-rights-management"></a>Aktivieren von Azure Rights Management

Um die Verschlüsselung in Vertraulichkeitbezeichnungen zu verwenden, muss in Ihrem Mandanten Azure Rights Management aktiviert werden. In neuen Mandanten ist dieser Dienst standardmäßig aktiviert, aber Sie müssen ihn möglicherweise manuell einschalten. Weitere Informationen finden Sie unter [Aktivieren von Azure Rights Management](https://docs.microsoft.com/de-DE/azure/information-protection/activate-service).

### <a name="configure-exchange-for-azure-information-protection"></a>Konfigurieren von Exchange für Azure Information Protection

Exchange muss nicht für Azure Information Protection konfiguriert werden, damit Benutzer Bezeichnungen in Outlook anwenden können, um E-Mails zu schützen. Bis Exchange aber für Azure Information Protection konfiguriert ist, können Sie nicht den vollen Funktionsumfang des Azure Information Protection-Schutzes in Exchange nutzen.
 
Benutzer können beispielsweise geschützte E-Mails nicht auf Mobiltelefonen oder mit Outlook im Web anzeigen, geschützte E-Mails können nicht für die Suche indexiert werden, und Sie können Exchange Online DLP nicht für den Rights Management-Schutz konfigurieren. 

Um sicherzustellen, dass Exchange diese zusätzlichen Szenarien unterstützt, lesen Sie die folgenden Informationen:

- Für Exchange Online lesen Sie die Anweisungen für [Exchange Online: Konfigurieren von IRM](https://docs.microsoft.com/de-DE/azure/information-protection/configure-office365#exchange-online-irm-configuration).
- For das lokale Exchange müssen Sie den [RMS-Connector bereitstellen und Ihre Exchange-Server konfigurieren](https://docs.microsoft.com/de-DE/azure/information-protection/deploy-rms-connector). 
