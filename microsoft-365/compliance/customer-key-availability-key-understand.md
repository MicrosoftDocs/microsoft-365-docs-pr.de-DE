---
title: Informationen zum Verfügbarkeits Schlüssel für Office 365 Kundenschlüssel
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Informationen zum Verfügbarkeits Schlüssel, der zum Wiederherstellen von verloren gegangenen Office 365 Kunden Schlüsseln verwendet wird.
ms.openlocfilehash: cb5284f46245db1d00506ab0e178244aac53a21f
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604172"
---
# <a name="learn-about-the-availability-key-for-office-365-customer-key"></a>Informationen zum Verfügbarkeits Schlüssel für Office 365 Kundenschlüssel

Der Verfügbarkeits Schlüssel ist ein Stammschlüssel, der automatisch generiert und bereitgestellt wird, wenn Sie eine Daten Verschlüsselungsrichtlinie erstellen. Office 365 speichert und schützt den Verfügbarkeits Schlüssel. Der Verfügbarkeits Schlüssel funktioniert wie die beiden Stammschlüssel, die Sie für die Dienst Verschlüsselung mit dem Kundenschlüssel angeben. Der Verfügbarkeits Schlüssel wickelt die Schlüssel um eine Ebene tiefer in die Schlüsselhierarchie ein. Im Gegensatz zu den Schlüsseln, die Sie in Azure Key Vault bereitstellen und verwalten, können Sie nicht direkt auf den Verfügbarkeits Schlüssel zugreifen. Office 365 automatisierte Dienste verwalten den Verfügbarkeits Schlüssel Programmgesteuertes. Diese Dienste initiieren automatisierte Vorgänge, die niemals direkten Zugriff auf den Verfügbarkeits Schlüsselbein halten.

Der Hauptzweck des Verfügbarkeits Schlüssels besteht darin, die Wiederherstellungsfunktion aus dem unerwarteten Verlust von Stamm Schlüsseln bereitzustellen, den Sie verwalten. Verlust kann ein Ergebnis von Misswirtschaft oder böswilligen Aktionen sein. Wenn Sie die Kontrolle über die Stammschlüssel verloren haben, wenden Sie sich an den Microsoft-Support, und Microsoft unterstützt Sie beim Wiederherstellungsprozess mithilfe des Verfügbarkeits Schlüssels. Sie verwenden den Verfügbarkeits Schlüssel, um zu einer neuen Daten Verschlüsselungsrichtlinie mit neuen von Ihnen bereitgestellten Stamm Schlüsseln zu migrieren.

Die Speicherung und Steuerung des Verfügbarkeits Schlüssels unterscheiden sich aus drei Gründen absichtlich von den Schlüsseln zu Azure Key Vault:

- Der Verfügbarkeits Schlüssel bietet eine Wiederherstellungs-, "Break-Glass"-Funktion, wenn die Steuerung über beide Azure Key Vault-Schlüssel verloren geht.
- Die Trennung von logischen Steuerelementen und sicheren Speicherorten bietet eine umfassende Verteidigung und schützt vor dem Verlust aller Schlüssel und ihrer Daten vor einem einzelnen Angriff oder Fehlerpunkt.
- Der Verfügbarkeits Schlüssel bietet eine hohe Verfügbarkeit, wenn Office 365 Dienste aufgrund von Transienten Fehlern keine in Azure Key Vault gehosteten Schlüssel erreichen können. Diese Regel gilt nur für Exchange Online-und Skype for Business Dienst Verschlüsselung. Für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien wird der Verfügbarkeits Schlüssel nie verwendet, es sei denn, Sie weisen Microsoft ausdrücklich an, den Wiederherstellungsprozess zu initiier

Durch die gemeinsame Nutzung der Verantwortung zum Schutz Ihrer Daten mithilfe einer Vielzahl von Schutzmaßnahmen und Prozessen für die Schlüsselverwaltung wird letztendlich das Risiko verringert, dass alle Schlüssel (und damit Ihre Daten) dauerhaft verloren gehen oder zerstört werden. Microsoft stellt Ihnen die alleinige Befugnis über die Deaktivierung oder Vernichtung des Verfügbarkeits Schlüssels zur Verfügung, wenn Sie den Dienst verlassen. Per Entwurf hat niemand bei Microsoft Zugriff auf den Verfügbarkeits Schlüssel: er ist nur über Office 365-Dienstcode zugänglich.

Weitere Informationen zum Sichern von Schlüsseln finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) .
  
## <a name="availability-key-uses"></a>Verwendung von Verfügbarkeits Schlüsseln

Der Verfügbarkeits Schlüssel bietet Wiederherstellungsfunktionen für Szenarien, in denen ein externer Übeltäter oder böswilliger Insider die Kontrolle über den schlüsseltresor stiehlt oder wenn versehentliches fehl Management zu einem Verlust von Stamm Schlüsseln führt. Diese Wiederherstellungsfunktion gilt für alle Office 365 Dienste, die mit dem Kundenschlüssel kompatibel sind. Einzelne Dienste verwenden den Verfügbarkeits Schlüssel unterschiedlich. Office 365 verwendet den Verfügbarkeits Schlüssel nur auf die unten beschriebenen Arten.

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online und Skype for Business verwendet

Zusätzlich zur Wiederherstellungsfunktion verwenden Exchange Online und Skype for Business den Verfügbarkeits Schlüssel, um die Datenverfügbarkeit während vorübergehender oder zeitweilig auftretender betriebsbedingter Probleme im Zusammenhang mit dem Dienst sicherzustellen, der auf Stammschlüssel zugreift. Wenn der Dienst aufgrund von vorübergehenden Fehlern keinen ihrer Kundenschlüssel in Azure Key Vault erreichen kann, verwendet der Dienst automatisch den Verfügbarkeits Schlüssel. Der Dienst geht nie direkt an den Verfügbarkeits Schlüssel.

Automatisierte Systeme in Exchange Online und Skype for Business können den Verfügbarkeits Schlüssel während vorübergehender Fehler verwenden, um automatisierte Back-End-Dienste wie Virenschutz, e-Discovery, Verhinderung von Datenverlust, Postfachverschiebungen und Datenindizierung zu unterstützen.

### <a name="sharepointonlineonedriveforbusinessandteamsfiles-uses"></a>SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien verwendet

Für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien wird der Verfügbarkeits Schlüssel nie außerhalb der Wiederherstellungsfunktion verwendet, und Kunden müssen Microsoft explizit anweisen, die Verwendung des Verfügbarkeits Schlüssels während eines Wiederherstellungsszenarios zu initiieren. Automatisierte Dienstvorgänge basieren ausschließlich auf Ihren Kunden Schlüsseln in Azure Key Vault. Ausführliche Informationen zur Funktionsweise der Schlüsselhierarchie für diese Dienste finden Sie unter [How SharePoint Online, OneDrive für Unternehmen und Teams-Dateien den Verfügbarkeits Schlüssel verwenden](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key).

## <a name="availability-key-security"></a>Sicherheit der verfügbaren Schlüssel

Microsoft teilt die Verantwortung für den Schutz von Daten mit Ihnen, indem Sie den Verfügbarkeits Schlüssel instanziieren und umfangreiche Maßnahmen zum Schutz dieser Lösung ergreifen. Microsoft stellt Kunden keine direkte Steuerung des Verfügbarkeits Schlüssels offen. Sie können beispielsweise nur die Schlüssel, die Sie in Azure Key Vault besitzen, Rollen (Drehen). Weitere Informationen finden Sie unter [Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Geheime Schlüsselspeicher für Verfügbarkeit

Microsoft schützt die Verfügbarkeits Schlüssel in Zugriffs kontrollierten internen geheimen Speicher wie dem kundenbezogenen Azure-schlüsseltresor. Wir implementieren Zugriffskontrollen, um zu verhindern, dass Microsoft-Administratoren direkt auf die darin enthaltenen Geheimnisse zugreifen. Geheime Speichervorgänge, einschließlich Schlüsselrotation und Löschung, erfolgen über automatisierte Befehle, die niemals direkten Zugriff auf den Verfügbarkeits Schlüsselbein halten. Geheime Speicherverwaltungsvorgänge sind auf bestimmte Ingenieure eingeschränkt und erfordern eine Eskalation der Rechte durch ein internes Tool, Lockbox. Die Berechtigungseskalation erfordert die Genehmigung des Vorgesetzten und die Begründung vor ihrer Erteilung. Lockbox stellt sicher, dass der Zugriff auf Zeit mit automatischer Zugriffssperre bei Zeitablauf oder beim Abmelden von Ingenieuren gebunden ist.

**Exchange Online-und Skype for Business-** Verfügbarkeits Schlüssel werden in einem geheimen Exchange Online geheimen Active Directory Speicher gespeichert. Verfügbarkeits Schlüssel werden sicher in mandantenspezifischen Containern innerhalb des Active Directory Domänencontrollers gespeichert. Dieser sichere Speicherort ist separat vom geheimen Speicher für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams-Dateien isoliert.

Verfüg barkeits Schlüssel für **SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien** werden in einem internen geheimen Speicher gespeichert, der vom Dienst Team verwaltet wird. Dieser gesicherte, geheime Speicherdienst verfügt über Front-End-Server mit Anwendungsendpunkten und einer SQL-Datenbank als Back-End. Verfügbarkeits Schlüssel werden in der SQL-Datenbank gespeichert und von Schlüsselspeicher-Verschlüsselungsschlüsseln umschlossen, die eine Kombination aus AES-256 und HMAC verwenden, um den Verfügbarkeits Schlüssel in Rest zu verschlüsseln. Die Verschlüsselungsschlüssel für geheimen Speicher werden in einer logisch isolierten Komponente derselben SQL-Datenbank gespeichert und weiter mit RSA-2048-Schlüsseln verschlüsselt, die in Zertifikaten enthalten sind, die von der Microsoft-Zertifizierungsstelle verwaltet werden. Diese Zertifikate werden in den geheimen Store-Front-End-Servern gespeichert, die Vorgänge für die Datenbank ausführen.

### <a name="defense-in-depth"></a>Tiefenverteidigung

Microsoft setzt eine umfassende Verteidigungsstrategie ein, um zu verhindern, dass böswillige Akteure die Vertraulichkeit, Integrität oder Verfügbarkeit von in der Microsoft-Cloud gespeicherten Kundendaten beeinträchtigen. Um den geheimen Speicher und den Verfügbarkeits Schlüssel im Rahmen der übergreifenden Sicherheitsstrategie zu schützen, werden bestimmte vorbeugende und Detektive Kontrollen implementiert.

Office 365 wurde entwickelt, um einen Missbrauch des Verfügbarkeits Schlüssels zu verhindern. Die Anwendungsschicht ist die einzige Methode, über die Schlüssel, einschließlich des Verfügbarkeits Schlüssels, zum Verschlüsseln und Entschlüsseln von Daten verwendet werden können. Nur Office 365-Dienstcode kann die Schlüsselhierarchie für Verschlüsselungs-und Entschlüsselungs Aktivitäten interpretieren und durchlaufen. Die logische Isolierung besteht zwischen den Speicherorten von Kunden Schlüsseln, Verfügbarkeits Schlüsseln, anderen hierarchischen Schlüsseln und Kundendaten. Durch diese Isolierung wird das Risiko von Daten Gefährdungen verringert, wenn ein oder mehrere Standorte gefährdet sind. Jede Ebene in der Hierarchie verfügt über integrierte Überwachungsfunktionen für die 24X7-Intrusionserkennung zum Schutz von gespeicherten Daten und Geheimnissen.

Zugriffssteuerungen werden implementiert, um nicht autorisierten Zugriff auf interne Systeme zu verhindern, einschließlich geheimer Schlüsselspeicher für Verfügbarkeit. Microsoft-Techniker haben keinen direkten Zugriff auf die geheimen Schlüsselspeicher für Verfügbarkeit. Weitere Details zu Zugriffssteuerungen finden Sie [unter administrative Access Controls in Office 365](https://docs.microsoft.com/Office365/securitycompliance/office-365-administrative-access-controls-overview).

Technische Steuerelemente verhindern, dass Microsoft-Mitarbeiter sich bei hoch privilegierten Dienstkonten anmelden, die andernfalls von Angreifern für die Identitätswechsel von Office 365 Diensten verwendet werden können. Beispielsweise verhindern diese Steuerelemente die interaktive Anmeldung.

Sicherheitsprotokollierung und Überwachungssteuerelemente sind eine weitere umfassende Schutzmaßnahme, die das Risiko für Microsoft-Dienste und Ihre Daten minimiert. Microsoft-Dienst Teams haben aktive Überwachungslösungen bereitgestellt, mit denen Warnungen und Überwachungsprotokolle generiert werden. Alle Dienst Teams laden ihre Protokolle in ein zentrales Repository hoch, in dem die Protokolle aggregiert und verarbeitet werden. Interne Tools untersuchen automatisch Datensätze, um zu bestätigen, dass die Dienste in einem optimalen, widerstandsfähigen und sicheren Zustand funktionieren. Für eine weitere Überprüfung werden ungewöhnliche Aktivitäten gekennzeichnet.

Jedes Protokollereignis, das auf eine mögliche Verletzung der Microsoft-Sicherheitsrichtlinie hinweist, wird den Microsoft-Sicherheitsteams sofort zur Kenntnis gebracht. Office 365 Security hat Warnungen konfiguriert, um den versuchten Zugriff auf geheime Verfügbarkeits Schlüssel zu erkennen. Warnungen werden auch generiert, wenn Microsoft-Mitarbeiter interaktive Anmeldung bei Dienstkonten versuchen, die durch Zugriffskontrollen untersagt und geschützt ist. Office 365 Sicherheit erkennt und warnt auch bei Abweichungen des Office 365 Diensts von normalen Basis Vorgängen. Übeltäter, die versuchen, Office 365 Dienste zu missbrauchen, würden Warnungen auslösen, die die Vertreibung des Täters von der Microsoft-Cloud-Umgebung zur Folge haben.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Verwenden des Verfügbarkeits Schlüssels zum Wiederherstellen nach Schlüssel Verlusten

Wenn Sie die Kontrolle über Ihre Kundenschlüssel verlieren, bietet Ihnen der Verfügbarkeits Schlüssel die Möglichkeit, Ihre Daten wiederherzustellen und erneut zu verschlüsseln.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Wiederherstellungsverfahren für Exchange Online und Skype for Business

Wenn Sie die Kontrolle über Ihre Kundenschlüssel verlieren, haben Sie mit dem Verfügbarkeits Schlüssel die Möglichkeit, Ihre Daten wiederherzustellen und die betroffenen Office 365 Ressourcen wieder online zu schalten. Der Verfügbarkeits Schlüssel schützt Ihre Daten weiterhin während der Wiederherstellung. Um eine vollständige Wiederherstellung nach Schlüssel Verlusten durchführen zu können, müssen Sie eine neue DEP erstellen und Ressourcen mit Auswirkungen auf die neue Richtlinie migrieren.

Wenn Sie Ihre Daten mit neuen Kunden Schlüsseln verschlüsseln möchten, erstellen Sie neue Schlüssel in Azure Key Vault, erstellen Sie eine neue DEP mithilfe der neuen Kundenschlüssel, und weisen Sie die neue DEP dann den Postfächern zu, die derzeit mit der vorherigen DEP verschlüsselt sind, für die die Schlüssel verloren gegangen sind oder kompromittiert wurden.

Dieser erneute Verschlüsselungsvorgang kann bis zu 72 Stunden dauern. Dies ist die Standarddauer, wenn Sie eine Datenausführungsverhinderung ändern.
  
### <a name="recovery-procedure-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Wiederherstellungsverfahren für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien

Für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien wird der Verfügbarkeits Schlüssel nie außerhalb der Wiederherstellungsfunktion verwendet. Sie müssen Microsoft explizit anweisen, die Verwendung des Verfügbarkeits Schlüssels während eines Wiederherstellungsszenarios zu initiieren. Um den Wiederherstellungsvorgang zu initiieren, wenden Sie sich an Microsoft, um den Verfügbarkeits Schlüssel zu aktivieren. Sobald die Option aktiviert ist, wird der Verfügbarkeits Schlüssel automatisch zum Entschlüsseln Ihrer Daten verwendet, sodass Sie die Daten mit einer neu erstellten DEP verschlüsseln können, die neuen Kunden Schlüsseln zugeordnet ist.  

Dieser Vorgang ist proportional zur Anzahl der Websites in Ihrer Organisation. Nachdem Sie Microsoft aufgerufen haben, den Verfügbarkeits Schlüssel zu verwenden, sollten Sie innerhalb von etwa vier Stunden vollständig online sein.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Verwenden des Verfügbarkeits Schlüssels für Exchange Online und Skype for Business

Wenn Sie eine DEP mit dem Kundenschlüssel erstellen, generiert Office 365 einen Daten Verschlüsselungsrichtlinien Schlüssel (DEP-Schlüssel), der dieser DEP zugeordnet ist. Der Dienst verschlüsselt den DEP-Schlüssel dreimal: einmal mit jedem Kundenschlüssel und einmal mit dem Verfügbarkeits Schlüssel. Nur die verschlüsselten Versionen des DEP-Schlüssels werden gespeichert, und ein DEP-Schlüssel kann nur mit den Kunden Schlüsseln oder dem Verfügbarkeits Schlüssel entschlüsselt werden. Der DEP-Schlüssel wird dann zum Verschlüsseln von Post Fach Schlüsseln verwendet, die einzelne Postfächer verschlüsseln.
  
Office 365 folgt diesem Prozess zum Entschlüsseln und Bereitstellen von Daten, wenn Kunden den Dienst verwenden:
  
1. Entschlüsseln Sie den DEP-Schlüssel mit dem Kundenschlüssel.

2. Verwenden Sie den entschlüsselten DEP-Schlüssel, um einen postfachschlüssel zu entschlüsseln.

3. Verwenden Sie den Schlüssel für entschlüsselte Postfächer, um das Postfach selbst zu entschlüsseln, sodass Sie auf die Daten innerhalb des Postfachs zugreifen können.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Verwenden der Verfügbarkeits Taste für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien

Die SharePoint Online und OneDrive für Unternehmen Architektur und Implementierung für den Schlüssel und die Verfügbarkeit von Kunden unterscheiden sich von Exchange Online und Skype for Business.
  
Wenn eine Organisation zu von Kunden verwalteten Schlüsseln wechselt, erstellt Office 365 einen mandantenspezifischen zwischen Schlüssel (tik). Office 365 verschlüsselt die tik zweimal, einmal mit jedem Kundenschlüssel, und speichert die beiden verschlüsselten Versionen des tik. Nur die verschlüsselten Versionen der tik werden gespeichert, und ein tik kann nur mit den Kunden Schlüsseln entschlüsselt werden. Das tik wird dann zum Verschlüsseln von Website Schlüsseln verwendet, die dann zum Verschlüsseln von BLOB-Schlüsseln verwendet werden (auch als Dateisegment Schlüssel bezeichnet). Je nach Dateigröße kann der Dienst eine Datei in mehrere Datei Blöcke mit jeweils einem eindeutigen Schlüssel aufteilen. Die BLOBs (Datei Blöcke) selbst werden mit den BLOB-Schlüsseln verschlüsselt und im Microsoft Azure BLOB-Speicherdienst gespeichert.
  
Office 365 folgt diesem Prozess zum Entschlüsseln und Bereitstellen von Kundendateien, wenn Kunden den Dienst verwenden:

1. Entschlüsseln Sie die tik mit dem Kundenschlüssel.

2. Verwenden Sie den entschlüsselten tik, um einen Standort Schlüssel zu entschlüsseln.

3. Verwenden Sie den entschlüsselten Standort Schlüssel, um einen BLOB-Schlüssel zu entschlüsseln.

4. Verwenden Sie den entschlüsselten BLOB-Schlüssel, um das BLOB zu entschlüsseln.

Office 365 entschlüsselt ein tik, indem zwei Entschlüsselungs Anforderungen an Azure Key Vault mit einem leichten Offset ausgegeben werden. Der erste, der fertig ist, liefert das Ergebnis und bricht die andere Anforderung ab.
  
Wenn Sie den Zugriff auf Ihre Kundenschlüssel verlieren, verschlüsselt Office 365 auch die tik mit einem Verfügbarkeits Schlüssel und speichert diese zusammen mit den TIKs, die mit jedem Kundenschlüssel verschlüsselt sind. Die mit dem Verfügbarkeits Schlüssel verschlüsselte tik wird nur verwendet, wenn der Kunde Microsoft anruft, um den Wiederherstellungspfad einzutragen, wenn er böswillig oder versehentlich den Zugriff auf die Schlüssel verloren hat.
  
Aus Gründen der Verfügbarkeit und Skalierung werden entschlüsselte TIKs in einem zeitbegrenzten Arbeitsspeichercache zwischengespeichert. Zwei Stunden, bevor ein tik-Cache auf Ablauf festgelegt wird, versucht Office 365, die einzelnen tik zu entschlüsseln. Das Entschlüsseln des TIKs verlängert die Lebensdauer des Caches. Wenn die tik-Entschlüsselung für eine erhebliche Zeitspanne fehlschlägt, generiert Office 365 eine Warnung, die das Engineering vor dem Cache Ablauf benachrichtigt. Nur wenn der Kunde Microsoft anruft, Office 365 den Wiederherstellungsvorgang zu initiieren, bei dem die tik mit dem verfügbaren Verfügbarkeits Schlüssel entschlüsselt wird, der im geheimen Speicher von Microsoft gespeichert ist, und der den Mandanten erneut mit dem entschlüsselten tik und einer neuen Gruppe von vom Kunden bereitgestellte Azure Key-Tresorschlüssel.
  
Ab heute ist der Kundenschlüssel an der Verschlüsselungs-und Entschlüsselungs Kette von SharePoint Online Dateidaten beteiligt, die im Azure-BLOB-Speicher gespeichert sind, aber nicht SharePoint Online Listenelementen oder Metadaten, die in der SQL-Datenbank gespeichert sind. Office 365 verwendet nicht den verfügbaren Schlüssel für Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien außer dem oben beschriebenen Fall, der vom Kunden initiiert wurde. Der menschliche Zugriff auf Kundendaten wird durch die Kunden-Lockbox geschützt.

## <a name="availability-key-triggers"></a>Trigger für Verfügbarkeits Schlüssel

Office 365 löst den Verfügbarkeits Schlüssel nur unter bestimmten Umständen aus. Diese Umstände unterscheiden sich je nach Dienst.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Trigger für Exchange Online und Skype for Business
  
1. Office 365 liest die DEP, der das Postfach zugewiesen ist, um den Speicherort der beiden Kundenschlüssel in Azure Key Vault zu ermitteln.

2. Office 365 wählt nach dem Zufallsprinzip einen der beiden Kundenschlüssel aus der DEP aus und sendet eine Anforderung an Azure Key Vault, um den DEP-Schlüssel mit dem Kundenschlüssel zu entpacken.

3. Wenn die Anforderung zum Aufräumen des DEP-Schlüssels mit dem Kundenschlüssel fehlschlägt, sendet Office 365 eine zweite Anforderung an Azure Key Vault, wobei Sie dieses Mal angewiesen wird, den alternativen Kundenschlüssel (zweiter) zu verwenden.

4. Wenn die zweite Anforderung zum Aufziehen des DEP-Schlüssels mit dem Kundenschlüssel fehlschlägt, untersucht Office 365 die Ergebnisse beider Anforderungen.

    - Wenn die Prüfung festgestellt hat, dass die Anforderungen einen Systemfehler zurückgeben konnten:

       - Office 365 löst den Verfügbarkeits Schlüssel zum Entschlüsseln des DEP-Schlüssels aus.

       - Office 365 verwendet dann den DEP-Schlüssel, um den postfachschlüssel zu entschlüsseln und die Benutzeranforderung abzuschließen. 

       - In diesem Fall kann Azure Key Vault aufgrund eines vorübergehenden Fehlers entweder nicht reagieren oder nicht erreichbar sein.

    - Wenn die Prüfung festgestellt hat, dass die Anforderungen die Rückgabe des Zugriffs verweigert haben:

       - Dies bedeutet, dass absichtliche, unbeabsichtigte oder böswillige Aktionen ausgeführt wurden, um die Kundenschlüssel nicht verfügbar zu machen (beispielsweise während des Daten Löschvorgangs im Rahmen des Ausscheidens des Diensts).

       - In diesem Fall wird der Verfügbarkeits Schlüssel nur für Systemaktionen und nicht für Benutzeraktionen verwendet, die Benutzeranforderung schlägt fehl, und der Benutzer erhält eine Fehlermeldung.

>[!IMPORTANT]
>Office 365 Dienstcode hat immer ein gültiges Anmeldetoken für die Argumentation über Kundendaten, um Mehrwertdienste für die Cloud bereitzustellen. Daher kann es, bis der Verfügbarkeits Schlüssel gelöscht wurde, als Fallback für Aktionen verwendet werden, die von oder intern in Exchange Online und Skype for Business wie Such Indexerstellung oder Verschieben von Postfächern initiiert wurden. Dies gilt sowohl für vorübergehende Fehler als auch für Zugriff verweigerte Anforderungen an Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Trigger für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien

Für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien wird der Verfügbarkeits Schlüssel nie außerhalb der Wiederherstellungsfunktion verwendet, und Kunden müssen Microsoft explizit anweisen, die Verwendung des Verfügbarkeits Schlüssels während eines Wiederherstellungsszenarios zu initiieren.

## <a name="audit-logs-and-the-availability-key"></a>Überwachungsprotokolle und der Verfügbarkeits Schlüssel

Automatisierte Systeme in Office 365 verarbeiten alle Daten, die durch das System fließen, um Cloud-Dienste bereitzustellen, beispielsweise Virenschutz, e-Discovery, Verhinderung von Datenverlust und Datenindizierung. Office 365 generiert keine Kundensicht baren Protokolle für diese Aktivität. Darüber hinaus greifen Microsoft-Mitarbeiter nicht im Rahmen dieser normalen Systemvorgänge auf Ihre Daten zu.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online-und Skype for Business-verfüg barkeits Schlüsselprotokollierung

Wenn Exchange Online und Skype for Business auf den Verfügbarkeits Schlüssel zugreift, um den Dienst bereitzustellen, veröffentlicht Office 365 Kunden sichtbare Protokolle, auf die über das Security and Compliance Center zugegriffen werden kann. Ein Überwachungsprotokolleintrag für den Vorgang des Verfügbarkeits Schlüssels wird jedes Mal generiert, wenn der Dienst den Verfügbarkeits Schlüssel verwendet. Ein neuer Datensatztyp namens "Customer Key Service Encryption" mit Aktivitätstyp "Fallback auf Verfügbarkeits Taste" ermöglicht Administratoren das Filtern von [Unified Audit Log](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) -Suchergebnissen, um die Verfügbarkeits Schlüsseldaten Sätze anzuzeigen.

Protokolldatensätze umfassen Attribute wie Datum, Uhrzeit, Aktivität, Organisations-ID und Daten Verschlüsselungsrichtlinien-ID. Der Datensatz ist im Rahmen Office 365 einheitlichen Überwachungsprotokollen verfügbar und kann über die Registerkarte Suche im Office 365 Security and Compliance Center-Überwachungsprotokoll abgerufen werden.

![Überwachungsprotokoll Suche nach Verfügbarkeits Schlüsselereignissen](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online-und Skype for Business-Verfügbarkeits Schlüsseleinträge verwenden das [allgemeine Schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) der Office 365-Verwaltungsaktivität mit hinzugefügten benutzerdefinierten Parametern: Richtlinien-ID, Versions-ID des Bereichs Schlüssels und Anforderungs-ID.

![Benutzerdefinierte Parameter für den Verfügbarkeits Schlüssel](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Datei Verfügbarkeits Schlüsselprotokollierung

Die Protokollierung der Verfügbarkeits Schlüssel ist für diese Dienste noch nicht verfügbar. Bei SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien wird der Verfügbarkeits Schlüssel nur von Microsoft, wenn Sie von Ihnen angewiesen werden, zu Wiederherstellungszwecken aktiviert. Daher kennen Sie bereits jedes Ereignis, in dem der Verfügbarkeits Schlüssel für diese Dienste verwendet wird.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Verfügbarkeits Schlüssel in der Kundenschlüssel Hierarchie
  
Office 365 verwendet den Verfügbarkeits Schlüssel, um die Schlüssel Ebene tiefer in die Hierarchie für die Verschlüsselung von Kundenschlüssel Diensten einzuschließen. Zwischen Diensten gibt es unterschiedliche wichtige Hierarchien. Wichtige Algorithmen unterscheiden sich auch zwischen Verfügbarkeits Schlüsseln und anderen Schlüsseln in der Hierarchie jedes zutreffenden Diensts. Die von den verschiedenen Diensten verwendeten Algorithmen für die Verfügbarkeit Schlüssel sind wie folgt:

- Die Exchange Online-und Skype for Business-Verfügbarkeits Schlüssel verwenden AES-256.

- Die verfüg barkeits Schlüssel für Dateien SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwenden RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Verschlüsselungs Chiffren, die zum Verschlüsseln von Schlüsseln für Exchange Online und Skype for Business verwendet werden

![Verschlüsselungs Chiffren für Exchange Online Kundenschlüssel](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Verschlüsselungs Chiffren, die zum Verschlüsseln von Schlüsseln für SharePoint Online und OneDrive für Unternehmen verwendet werden

![Verschlüsselungs Chiffren für SharePoint Online Kundenschlüssel](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Dienst Verschlüsselung mit Kundenschlüssel für Office 365](customer-key-overview.md)

- [Einrichten des Kunden Schlüssels für Office 365](customer-key-set-up.md)

- [Verwalten des Kunden Schlüssels für Office 365](customer-key-manage.md)

- [Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels](customer-key-availability-key-roll.md)
