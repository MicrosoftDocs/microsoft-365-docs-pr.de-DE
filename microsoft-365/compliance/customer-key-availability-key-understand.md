---
title: Erfahren Sie mehr über den Verfügbarkeitsschlüssel für Kundenschlüssel
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
description: Erfahren Sie mehr über den Verfügbarkeitsschlüssel, der zum Wiederherstellen verlorener Kundenschlüssel verwendet wird.
ms.openlocfilehash: bbad6ace0880c142a497bcac3469c579f13c7881
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907741"
---
# <a name="learn-about-the-availability-key-for-customer-key"></a>Erfahren Sie mehr über den Verfügbarkeitsschlüssel für Kundenschlüssel

Der Verfügbarkeitsschlüssel ist ein Stammschlüssel, der beim Erstellen einer Datenverschlüsselungsrichtlinie automatisch generiert und bereitgestellt wird. Microsoft 365 speichert und schützt den Verfügbarkeitsschlüssel. Der Verfügbarkeitsschlüssel gleicht den beiden Stammschlüsseln, die Sie für die Dienstverschlüsselung mit Dem Kundenschlüssel liefern. Der Verfügbarkeitsschlüssel umschließt die Schlüssel um eine Ebene tiefer in der Schlüsselhierarchie. Im Gegensatz zu den Schlüsseln, die Sie in Azure Key Vault bereitstellen und verwalten, können Sie nicht direkt auf den Verfügbarkeitsschlüssel zugreifen. Automatisierte Microsoft 365-Dienste verwalten den Verfügbarkeitsschlüssel programmgesteuert. Diese Dienste initiieren automatisierte Vorgänge, die niemals direkten Zugriff auf den Verfügbarkeitsschlüssel beinhalten.

Der Hauptzweck des Verfügbarkeitsschlüssels besteht in der Bereitstellung von Wiederherstellungsfunktionen nach dem unerwarteten Verlust von Stammschlüsseln, die Sie verwalten. Der Verlust kann ein Ergebnis von Missmanagement oder böswilliger Aktion sein. Wenn Sie die Kontrolle über Ihre Stammschlüssel verlieren, wenden Sie sich an den Microsoft-Support, und Microsoft unterstützt Sie bei der Wiederherstellung mithilfe des Verfügbarkeitsschlüssels. Sie verwenden den Verfügbarkeitsschlüssel, um zu einer neuen Datenverschlüsselungsrichtlinie mit neuen Stammschlüsseln zu migrieren, die Sie bereitstellen.

Speicher und Steuerung des Verfügbarkeitsschlüssels unterscheiden sich aus drei Gründen absichtlich von Azure Key Vault-Schlüsseln:

- Der Verfügbarkeitsschlüssel bietet eine "Break-Glass"-Wiederherstellungsfunktion, wenn die Kontrolle über beide Azure Key Vault-Schlüssel verloren geht.
- Die Trennung von logischen Steuerelementen und sicheren Speicherorten bietet eine eingehende Verteidigung und schützt vor dem Verlust aller Schlüssel und Ihrer Daten vor einem einzelnen Angriff oder Einem Fehlerpunkt.
- Der Verfügbarkeitsschlüssel bietet eine Hochverfügbarkeitsfunktion, wenn Microsoft 365-Dienste in Azure Key Vault gehostete Schlüssel aufgrund vorübergehender Fehler nicht erreichen können. Diese Regel gilt nur für die Exchange Online- und Skype for Business-Dienstverschlüsselung. SharePoint Online-, OneDrive for Business- und #A0 verwenden nie den Verfügbarkeitsschlüssel, es sei denn, Sie weisen Microsoft explizit an, den Wiederherstellungsprozess zu initiieren.

Die Freigabe der Verantwortung für den Schutz Ihrer Daten mithilfe einer Vielzahl von Schutz- und Prozessen für die Schlüsselverwaltung reduziert letztendlich das Risiko, dass alle Schlüssel (und damit Ihre Daten) dauerhaft verloren gehen oder zerstört werden. Microsoft stellt Ihnen die alleinige Autorität für die Deaktivierung oder Vernichtung des Verfügbarkeitsschlüssels zur Verfügung, wenn Sie den Dienst verlassen. Kein Microsoft-Mitarbeiter hat Zugriff auf den Verfügbarkeitsschlüssel: Er kann nur über einen Microsoft 365-Dienstcode aufgerufen werden.

Weitere Informationen [zum Sichern von Schlüsseln](https://www.microsoft.com/trustcenter/Privacy/govt-requests-for-data) finden Sie im Microsoft Trust Center.
  
## <a name="availability-key-uses"></a>Verwendung des Verfügbarkeitsschlüssels

Der Verfügbarkeitsschlüssel bietet Wiederherstellungsfunktionen für Szenarien, in denen ein externer Böswilliger oder böswilliger Insider die Kontrolle über Ihren Schlüsseltresor stiehlt oder wenn versehentliche Missmanagement zum Verlust von Stammschlüsseln führt. Diese Wiederherstellungsfunktion gilt für alle Microsoft 365-Dienste, die mit dem Kundenschlüssel kompatibel sind. Einzelne Dienste verwenden den Verfügbarkeitsschlüssel unterschiedlich. Microsoft 365 verwendet den Verfügbarkeitsschlüssel nur auf die unten beschriebene Weise.

### <a name="exchange-online-and-skype-for-business-uses"></a>Exchange Online und Skype for Business verwendet

Zusätzlich zur Wiederherstellungsfunktion verwenden Exchange Online und Skype for Business den Verfügbarkeitsschlüssel, um die Datenverfügbarkeit bei vorübergehenden oder zeitweiligen Betriebsproblemen im Zusammenhang mit dem Zugriff auf die Stammschlüssel des Diensts sicherzustellen. Wenn der Dienst einen Ihrer Kundenschlüssel in Azure Key Vault aufgrund vorübergehender Fehler nicht erreichen kann, verwendet der Dienst automatisch den Verfügbarkeitsschlüssel. Der Dienst geht NIE direkt zum Verfügbarkeitsschlüssel.

Automatisierte Systeme in Exchange Online und Skype for Business können den Verfügbarkeitsschlüssel bei vorübergehenden Fehlern verwenden, um automatisierte Back-End-Dienste wie Virenschutz, E-Discovery, Verhinderung von Datenverlust, Postfachbewegungen und Datenindizierung zu unterstützen.

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-uses"></a>SharePoint Online-, OneDrive for Business- und #A0 werden verwendet

Für SharePoint Online-, OneDrive for Business- und #A0 wird der Verfügbarkeitsschlüssel nie außerhalb der Wiederherstellungsfunktion verwendet, und Kunden müssen Microsoft explizit anweisen, die Verwendung des Verfügbarkeitsschlüssels während eines Wiederherstellungsszenarios zu initiieren. Automatisierte Dienstvorgänge beruhen ausschließlich auf Ihren Kundenschlüsseln in Azure Key Vault. Ausführliche Informationen zur Funktionsweise der Schlüsselhierarchie für diese Dienste finden Sie unter [How SharePoint Online, OneDrive for Business, and Teams files use the availability key](#how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key).

## <a name="availability-key-security"></a>Sicherheit des Verfügbarkeitsschlüssels

Microsoft teilt sich die Verantwortung des Datenschutzes mit Ihnen, indem der Verfügbarkeitsschlüssel instanziiert und umfangreiche Maßnahmen zum Schutz ergriffen wird. Microsoft macht keine direkte Kontrolle über den Verfügbarkeitsschlüssel für Kunden verfügbar. Sie können z. B. nur die Schlüssel rollen (drehen), die Sie in Azure Key Vault besitzen. Weitere Informationen finden Sie unter [Roll or rotate a customer key or an availability key](customer-key-availability-key-roll.md).

### <a name="availability-key-secret-stores"></a>Schlüsselspeicher für die Verfügbarkeit

Microsoft schützt Verfügbarkeitsschlüssel in zugriffsgesteuerten internen geheimen Speichern wie dem kundenorientierten Azure Key Vault. Wir implementieren Zugriffssteuerelemente, um zu verhindern, dass Microsoft-Administratoren direkt auf die darin enthaltenen Geheimgeheimnisse zugreifen. Geheime Speichervorgänge, einschließlich Drehung und Löschung von Schlüsseln, erfolgen über automatisierte Befehle, die niemals direkten Zugriff auf den Verfügbarkeitsschlüssel beinhalten. Geheime Speicherverwaltungsvorgänge sind auf bestimmte Techniker beschränkt und erfordern eine Rechteeskalation über ein internes Tool, Lockbox. Die Berechtigungseskalation erfordert die Genehmigung und Begründung des Managers, bevor sie erteilt wird. Lockbox stellt sicher, dass der Zugriff mit dem automatischen Zugriffssperrstatus nach Ablauf der Zeit oder der Techniker-Abmeldezeit verbunden ist.

**Verfügbarkeitsschlüssel für Exchange Online** und Skype for Business werden in einem geheimen Exchange Online Active Directory-Speicher gespeichert. Verfügbarkeitsschlüssel werden sicher in mandantenspezifischen Containern innerhalb des Active Directory-Domänencontrollers gespeichert. Dieser sichere Speicherort ist getrennt und vom geheimen Speicher für SharePoint Online-, OneDrive for Business- und #A0 isoliert.

**Verfügbarkeitsschlüssel für SharePoint Online-, OneDrive for Business-** und #A0 werden in einem internen geheimen Speicher gespeichert, der vom Dienstteam verwaltet wird. Dieser gesicherte geheime Speicherdienst verfügt über Front-End-Server mit Anwendungsendpunkten und SQL Datenbank als Back-End. Verfügbarkeitsschlüssel werden in der SQL-Datenbank gespeichert und von Geheimspeicherverschlüsselungsschlüsseln umschlossen (verschlüsselt), die eine Kombination aus AES-256 und HMAC zum Verschlüsseln des verfügbarkeitsschlüssels im Ruhespeicher verwenden. Die Verschlüsselungsschlüssel für den geheimen Speicher werden in einer logisch isolierten Komponente derselben SQL-Datenbank gespeichert und mit RSA-2048-Schlüsseln weiter verschlüsselt, die in Von der Zertifizierungsstelle verwalteten Zertifikaten enthalten sind. Diese Zertifikate werden auf den Front-End-Servern des geheimen Speichers gespeichert, die Vorgänge für die Datenbank ausführen.

### <a name="defense-in-depth"></a>Ausführliche Verteidigung

Microsoft verwendet eine tief gehende Strategie zur Verteidigung, um zu verhindern, dass sich böswillige Akteure auf die Vertraulichkeit, Integrität oder Verfügbarkeit von Kundendaten auswirken, die in der Microsoft Cloud gespeichert sind. Spezifische präventive und detektive Kontrollen werden implementiert, um den geheimen Speicher und den Verfügbarkeitsschlüssel im Rahmen der übergeordneten Sicherheitsstrategie zu schützen.

Microsoft 365 wurde entwickelt, um den Missbrauch des Verfügbarkeitsschlüssels zu verhindern. Die Anwendungsebene ist die einzige Methode, mit der Schlüssel, einschließlich des Verfügbarkeitsschlüssels, zum Verschlüsseln und Entschlüsseln von Daten verwendet werden können. Nur Microsoft 365-Dienstcode kann die Schlüsselhierarchie für Verschlüsselungs- und Entschlüsselungsaktivitäten interpretieren und durchlaufen. Die logische Isolation besteht zwischen den Speicherorten von Kundenschlüsseln, Verfügbarkeitsschlüsseln, anderen hierarchischen Schlüsseln und Kundendaten. Diese Isolation verringert das Risiko der Datenexposition, wenn ein oder mehrere Standorte gefährdet sind. Jede Ebene in der Hierarchie verfügt über integrierte 24 x 7-Angriffserkennungsfunktionen, um gespeicherte Daten und geheime Daten zu schützen.

Zugriffssteuerelemente werden implementiert, um nicht autorisierten Zugriff auf interne Systeme zu verhindern, einschließlich geheimer Verfügbarkeitsschlüsselspeicher. Microsoft-Techniker haben keinen direkten Zugriff auf die geheimen Verfügbarkeitsschlüsselspeicher. Weitere Informationen zu Zugriffssteuerelementen erhalten Sie unter [Administrative Access Controls in Microsoft 365](/Office365/securitycompliance/office-365-administrative-access-controls-overview).

Technische Kontrollen verhindern, dass sich Microsoft-Mitarbeiter bei Dienstkonten mit hohen Berechtigungen anmelden, die andernfalls von Angreifern zum Identitätswechsel von Microsoft-Diensten verwendet werden. Diese Steuerelemente verhindern beispielsweise die interaktive Anmeldung.

Sicherheitsprotokollierungs- und Überwachungssteuerelemente sind ein weiterer, tief gehender Schutz, der implementiert wurde, um das Risiko für Microsoft-Dienste und Ihre Daten zu mindern. Microsoft-Dienstteams haben aktive Überwachungslösungen bereitgestellt, die Warnungen und Überwachungsprotokolle generieren. Alle Dienstteams laden ihre Protokolle in ein zentrales Repository hoch, in dem die Protokolle aggregiert und verarbeitet werden. Interne Tools untersuchen Datensätze automatisch, um zu bestätigen, dass Dienste in einem optimalen, ausfallsicheren und sicheren Zustand funktionieren. Ungewöhnliche Aktivitäten werden zur weiteren Überprüfung gekennzeichnet.

Jedes Protokollereignis, das einen potenziellen Verstoß gegen die Microsoft-Sicherheitsrichtlinie angibt, wird den Microsoft-Sicherheitsteams sofort zur Anzeige gebracht. Microsoft 365 Security hat Warnungen konfiguriert, um versuchten Zugriff auf geheime Verfügbarkeitsspeicher zu erkennen. Warnungen werden auch generiert, wenn Microsoft-Mitarbeiter versuchen, sich interaktiv bei Dienstkonten zu anmelden, was durch Zugriffssteuerungen verboten und geschützt ist. Microsoft 365 Security erkennt und warnt auch bei Abweichungen des Microsoft 365-Diensts von normalen Basisbetriebsvorgängen. Wenn Angreifer versuchen, Microsoft 365-Dienste zu missbrauchen, würden Warnungen ausgelöst, die zu einer Räumung des Angreifers aus der Microsoft-Cloudumgebung führt.

## <a name="use-the-availability-key-to-recover-from-key-loss"></a>Verwenden des Verfügbarkeitsschlüssels zum Wiederherstellen von Schlüsselverlusten

Wenn Sie die Kontrolle über Ihre Kundenschlüssel verlieren, können Sie ihre Daten mit dem Verfügbarkeitsschlüssel wiederherstellen und erneut verschlüsseln.

### <a name="recovery-procedure-for-exchange-online-and-skype-for-business"></a>Wiederherstellungsverfahren für Exchange Online und Skype for Business

Wenn Sie die Kontrolle über Ihre Kundenschlüssel verlieren, können Sie mit dem Verfügbarkeitsschlüssel Ihre Daten wiederherstellen und Ihre auswirkungen auf Microsoft 365-Ressourcen wieder online stellen. Der Verfügbarkeitsschlüssel schützt Ihre Daten während der Wiederherstellung weiterhin. Auf einer hohen Ebene müssen Sie eine neue DEP erstellen und die ressourcenverhedderten Ressourcen in die neue Richtlinie verschieben, um den Schlüsselverlust vollständig wiederhergestellt zu können.

Um Ihre Daten mit neuen Kundenschlüsseln zu verschlüsseln, erstellen Sie neue Schlüssel in Azure Key Vault, erstellen Sie eine neue DEP mit den neuen Kundenschlüsseln, und weisen Sie die neue DEP dann den Postfächern zu, die derzeit mit der vorherigen DEP verschlüsselt sind, für die die Schlüssel verloren gegangen oder gefährdet wurden.

Dieser Erneute Verschlüsselungsprozess kann bis zu 72 Stunden dauern. Dies ist die Standarddauer, wenn Sie eine DEP ändern.
  
### <a name="recovery-procedure-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Wiederherstellungsverfahren für SharePoint Online-, OneDrive for Business- und #A0

Für SharePoint Online-, OneDrive for Business- und #A0 wird der Verfügbarkeitsschlüssel nie außerhalb der Wiederherstellungsfunktion verwendet. Sie müssen Microsoft explizit anweisen, die Verwendung des Verfügbarkeitsschlüssels während eines Wiederherstellungsszenarios zu initiieren. Um den Wiederherstellungsprozess zu initiieren, wenden Sie sich an Microsoft, um den Verfügbarkeitsschlüssel zu aktivieren. Nach der Aktivierung wird der Verfügbarkeitsschlüssel automatisch verwendet, um Ihre Daten zu entschlüsseln, sodass Sie die Daten mit einer neu erstellten DEP verschlüsseln können, die neuen Kundenschlüsseln zugeordnet ist.  

Dieser Vorgang ist proportional zur Anzahl der Websites in Ihrer Organisation. Sobald Sie Microsoft anrufen, um den Verfügbarkeitsschlüssel zu verwenden, sollten Sie innerhalb von etwa vier Stunden vollständig online sein.

## <a name="how-exchange-online-and-skype-for-business-use-the-availability-key"></a>Verwenden des Verfügbarkeitsschlüssels von Exchange Online und Skype for Business

Wenn Sie eine DEP mit Dem Kundenschlüssel erstellen, generiert Microsoft 365 einen Datenverschlüsselungsrichtlinienschlüssel (DEP Key), der dieser DEP zugeordnet ist. Der Dienst verschlüsselt den DEP-Schlüssel dreimal: einmal mit jedem Kundenschlüssel und einmal mit dem Verfügbarkeitsschlüssel. Nur die verschlüsselten Versionen des DEP-Schlüssels werden gespeichert, und ein DEP-Schlüssel kann nur mit den Kundenschlüsseln oder dem Verfügbarkeitsschlüssel entschlüsselt werden. Der DEP-Schlüssel wird dann zum Verschlüsseln von Postfachschlüsseln verwendet, die einzelne Postfächer verschlüsseln.
  
Microsoft 365 folgt diesem Prozess zum Entschlüsseln und Bereitstellen von Daten, wenn Kunden den Dienst verwenden:
  
1. Entschlüsseln Sie den DEP-Schlüssel mithilfe des Kundenschlüssels.

2. Verwenden Sie den entschlüsselten DEP-Schlüssel, um einen Postfachschlüssel zu entschlüsseln.

3. Verwenden Sie den entschlüsselten Postfachschlüssel, um das Postfach selbst zu entschlüsseln, sodass Sie auf die Daten innerhalb des Postfachs zugreifen können.

## <a name="how-sharepoint-online-onedrive-for-business-and-teams-files-use-the-availability-key"></a>Verwenden des Verfügbarkeitsschlüssels für SharePoint Online-, OneDrive for Business- und #A0

Die Architektur und Implementierung von SharePoint Online und OneDrive for Business für Kundenschlüssel und Verfügbarkeitsschlüssel unterscheiden sich von Exchange Online und Skype for Business.
  
Wenn eine Organisation zu vom Kunden verwalteten Schlüsseln wechselt, erstellt Microsoft 365 einen organisationsspezifischen Zwischenschlüssel (TIK). Microsoft 365 verschlüsselt die TIK zweimal, einmal mit jedem Kundenschlüssel, und speichert die beiden verschlüsselten Versionen der TIK. Nur die verschlüsselten Versionen der TIK werden gespeichert, und eine TIK kann nur mit den Kundenschlüsseln entschlüsselt werden. Die TIK wird dann zum Verschlüsseln von Websiteschlüsseln verwendet, die dann zum Verschlüsseln von Blobschlüsseln (auch Als Dateiblöckeschlüssel bezeichnet) verwendet werden. Je nach Dateigröße kann der Dienst eine Datei mit einem eindeutigen Schlüssel in mehrere Dateiblöcke aufteilen. Die Blobs (Dateiblöcke) selbst werden mit den Blobschlüsseln verschlüsselt und im Microsoft Azure Blob Storage Service gespeichert.
  
Microsoft 365 folgt diesem Prozess zum Entschlüsseln und Bereitstellen von Kundendateien, wenn Kunden den Dienst verwenden:

1. Entschlüsseln Sie die TIK mithilfe des Kundenschlüssels.

2. Verwenden Sie die entschlüsselte TIK, um einen Websiteschlüssel zu entschlüsseln.

3. Verwenden Sie den entschlüsselten Websiteschlüssel, um einen Blobschlüssel zu entschlüsseln.

4. Verwenden Sie den entschlüsselten Blobschlüssel, um das Blob zu entschlüsseln.

Microsoft 365 entschlüsselt eine TIK, indem zwei Entschlüsselungsanforderungen an Azure Key Vault mit einem geringfügigen Offset gesendet werden. Der erste, der fertig gestellt wird, gibt das Ergebnis an, und die andere Anforderung wird abgebrochen.
  
Falls Sie den Zugriff auf Ihre Kundenschlüssel verlieren, verschlüsselt Microsoft 365 auch die TIK mit einem Verfügbarkeitsschlüssel und speichert diesen zusammen mit den mit jedem Kundenschlüssel verschlüsselten TIKs. Die mit dem Verfügbarkeitsschlüssel verschlüsselte TIK wird nur verwendet, wenn der Kunde Microsoft aufruft, um den Wiederherstellungspfad einlisten zu lassen, wenn er versehentlich oder böswilligen Zugriff auf seine Schlüssel verloren hat.
  
Aus Gründen der Verfügbarkeit und Skalierung werden entschlüsselte TIKs in einem zeitlich begrenzten Arbeitsspeichercache zwischengespeichert. Zwei Stunden, bevor ein TIK-Cache auf Ablauf festgelegt ist, versucht Microsoft 365, jede TIK zu entschlüsseln. Durch die Entschlüsselung der TIKs wird die Lebensdauer des Caches verlängert. Wenn die TIK-Entschlüsselung für einen erheblichen Zeitraum fehlschlägt, generiert Microsoft 365 eine Warnung zur Benachrichtigung des Engineerings vor dem Cacheablauf. Nur wenn der Kunde Microsoft anruft, initiiert Microsoft 365 den Wiederherstellungsvorgang, bei dem die TIK mit dem im geheimen Speicher von Microsoft gespeicherten Verfügbarkeitsschlüssel entschlüsselt und der Mandant erneut mithilfe der entschlüsselten TIK und einer neuen Gruppe von vom Kunden bereitgestellten Azure Key Vault-Schlüsseln onboardiert wird.
  
Ab heute ist Customer Key an der Verschlüsselungs- und Entschlüsselungskette von SharePoint Online-Dateidaten beteiligt, die im Azure Blob Store gespeichert sind, aber nicht an SharePoint Online-Listenelementen oder Metadaten, die in der SQL gespeichert sind. Microsoft 365 verwendet nicht den Verfügbarkeitsschlüssel für Exchange Online-, Skype for Business-, SharePoint Online-, OneDrive for Business- und #A0 mit dem oben beschriebenen Fall, der vom Kunden initiiert wurde. Der Menschliche Zugriff auf Kundendaten wird durch Customer Lockbox geschützt.

## <a name="availability-key-triggers"></a>Auslöser des Verfügbarkeitsschlüssels

Microsoft 365 löst den Verfügbarkeitsschlüssel nur unter bestimmten Umständen aus. Diese Umstände unterscheiden sich je nach Dienst.

### <a name="triggers-for-exchange-online-and-skype-for-business"></a>Trigger für Exchange Online und Skype for Business
  
1. Microsoft 365 liest die DEP, der das Postfach zugewiesen ist, um den Speicherort der beiden Kundenschlüssel in Azure Key Vault zu bestimmen.

2. Microsoft 365 wählt zufällig einen der beiden Kundenschlüssel aus der DEP aus und sendet eine Anforderung an Azure Key Vault, den DEP-Schlüssel mithilfe des Kundenschlüssels zu entpacken.

3. Wenn bei der Anforderung, den DEP-Schlüssel mithilfe des Kundenschlüssels zu entpacken, ein Fehler auftritt, sendet Microsoft 365 eine zweite Anforderung an Azure Key Vault, die ihn anweisen soll, den alternativen (zweiten) Kundenschlüssel zu verwenden.

4. Wenn bei der zweiten Anforderung zum Auspacken des DEP-Schlüssels mithilfe des Kundenschlüssels ein Fehler auftritt, untersucht Microsoft 365 die Ergebnisse beider Anforderungen.

    - Wenn die Prüfung feststellt, dass die Anforderungen einen Systemfehler zurückgegeben haben:

       - Microsoft 365 löst den Verfügbarkeitsschlüssel aus, um den DEP-Schlüssel zu entschlüsseln.

       - Microsoft 365 verwendet dann den DEP-Schlüssel, um den Postfachschlüssel zu entschlüsseln und die Benutzeranforderung zu vervollständigen. 

       - In diesem Fall kann Azure Key Vault aufgrund eines vorübergehenden FEHLERs nicht reagieren oder nicht erreichbar sein.

    - Wenn die Prüfung feststellt, dass die Anforderungen keinen ZUGRIFF VERWEIGERT zurückgeben konnten:

       - Dies bedeutet, dass absichtliche, unbeabsichtigte oder böswillige Maßnahmen ergriffen wurden, um die Kundenschlüssel nicht verfügbar zu machen (z. B. während des Datenbereinigungsprozesses als Teil des Verlassens des Diensts).

       - In diesem Fall wird der Verfügbarkeitsschlüssel nur für Systemaktionen und nicht für Benutzeraktionen verwendet, die Benutzeranforderung schlägt fehl, und der Benutzer erhält eine Fehlermeldung.

>[!IMPORTANT]
>Microsoft 365-Dienstcode verfügt immer über ein gültiges Anmeldetoken zur Begründung von Kundendaten, um Mehrwert für Clouddienste zu bieten. Daher kann er bis zum Löschen des Verfügbarkeitsschlüssels als Ausweichfunktion für Aktionen verwendet werden, die von Exchange Online und Skype for Business initiiert oder in diese initiiert wurden, z. B. das Erstellen von Suchindex oder das Verschieben von Postfächern. Dies gilt sowohl für vorübergehende FEHLER als auch für ACCESS-DENIED-Anforderungen an Azure Key Vault.

### <a name="triggers-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Trigger für SharePoint Online-, OneDrive for Business- und #A0

Für SharePoint Online-, OneDrive for Business- und #A0 wird der Verfügbarkeitsschlüssel nie außerhalb der Wiederherstellungsfunktion verwendet, und Kunden müssen Microsoft explizit anweisen, die Verwendung des Verfügbarkeitsschlüssels während eines Wiederherstellungsszenarios zu initiieren.

## <a name="audit-logs-and-the-availability-key"></a>Überwachungsprotokolle und verfügbarkeitsschlüssel

Automatisierte Systeme in Microsoft 365 verarbeiten alle Daten, während sie durch das System fließen, um Clouddienste, z. B. Virenschutz, E-Discovery, Verhinderung von Datenverlust und Datenindizierung, zur Verfügung zu stellen. Microsoft 365 generiert keine kunden sichtbaren Protokolle für diese Aktivität. Darüber hinaus greifen Mitarbeiter von Microsoft im Rahmen dieser normalen Systemvorgänge nicht auf Ihre Daten zu.

### <a name="exchange-online-and-skype-for-business-availability-key-logging"></a>Exchange Online- und Skype for Business-Verfügbarkeitsschlüsselprotokollierung

Wenn Exchange Online und Skype for Business auf den Verfügbarkeitsschlüssel für die Bereitstellung von Dienst zugreifen, veröffentlicht Microsoft 365 kunden sichtbare Protokolle, auf die über das Security and Compliance Center zugegriffen werden kann. Jedes Mal, wenn der Dienst den Verfügbarkeitsschlüssel verwendet, wird ein Überwachungsprotokolldatensatz für den Verfügbarkeitsschlüsselvorgang generiert. Ein neuer Datensatztyp namens "Customer Key Service Encryption" mit dem Aktivitätstyp "Fallback to Availability Key" ermöglicht Administratoren das Filtern der Suchergebnisse des [einheitlichen Überwachungsprotokolls](./search-the-audit-log-in-security-and-compliance.md) zum Anzeigen von Verfügbarkeitsschlüsseleinträgen.

Protokolldatensätze enthalten Attribute wie Datum, Uhrzeit, Aktivität, Organisations-ID und Datenverschlüsselungsrichtlinien-ID. Der Datensatz ist als Teil der einheitlichen Überwachungsprotokolle verfügbar und kann über die Registerkarte Security & Compliance Center Audit Log Search zugegriffen werden.

![Überwachungsprotokollsuche für Verfügbarkeitsschlüsselereignisse](../media/customerkeyauditlogsearchavailabilitykeyloggingimage.png)

Exchange Online- und Skype for Business-Verfügbarkeitsschlüsseleinträge verwenden [](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) das allgemeine Schema der Office 365-Verwaltungsaktivität mit hinzugefügten benutzerdefinierten Parametern: Richtlinien-ID, Bereichsschlüsselversions-ID und Anforderungs-ID.

![Benutzerdefinierte Parameter für Verfügbarkeitsschlüssel](../media/customerkeyauditlogsearchavailabilitykeyloggingcustomparam.png)

### <a name="sharepoint-online-onedrive-for-business-and-teams-files-availability-key-logging"></a>SharePoint Online- und OneDrive for Business- und #A0

Die Protokollierung von Verfügbarkeitsschlüsseln ist für diese Dienste noch nicht verfügbar. Für SharePoint Online-, OneDrive for Business- und #A0 wird der Verfügbarkeitsschlüssel nur von Microsoft aktiviert, wenn Sie dies angewiesen haben, um wiederherstellungszwecke zu dienen. Als Ergebnis kennen Sie bereits jedes Ereignis, in dem der Verfügbarkeitsschlüssel für diese Dienste verwendet wird.

## <a name="availability-key-in-the-customer-key-hierarchy"></a>Verfügbarkeitsschlüssel in der Hierarchie des Kundenschlüssels
  
Microsoft 365 verwendet den Verfügbarkeitsschlüssel, um die Schlüsselebene tiefer in der Schlüsselhierarchie zu umschließen, die für die Verschlüsselung des Customer Key Service eingerichtet wurde. Zwischen diensten sind unterschiedliche Schlüsselhierarchien vorhanden. Schlüsselalgorithmen unterscheiden sich auch zwischen Verfügbarkeitsschlüsseln und anderen Schlüsseln in der Hierarchie der einzelnen anwendbaren Dienste. Die von den verschiedenen Diensten verwendeten Verfügbarkeitsschlüsselalgorithmen sind wie folgt:

- Die Verfügbarkeitsschlüssel für Exchange Online und Skype for Business verwenden AES-256.

- Die Verfügbarkeitsschlüssel für SharePoint Online-, OneDrive for Business- und #A0 verwenden RSA-2048.

### <a name="encryption-ciphers-used-to-encrypt-keys-for-exchange-online-and-skype-for-business"></a>Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln für Exchange Online und Skype for Business

![Verschlüsselungschiffren für Exchange Online Customer Key](../media/customerkeyencryptionhierarchiesexchangeskype.png)

### <a name="encryption-ciphers-used-to-encrypt-keys-for-sharepoint-online-and-onedrive-for-business"></a>Verschlüsselungschiffren zum Verschlüsseln von Schlüsseln für SharePoint Online und OneDrive for Business

![Verschlüsselungschiffren für SharePoint Online Customer Key](../media/customerkeyencryptionhierarchiessharepointonedriveteamsfiles.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Einrichten des Kundenschlüssels](customer-key-set-up.md)

- [Verwalten des Kundenschlüssels](customer-key-manage.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)