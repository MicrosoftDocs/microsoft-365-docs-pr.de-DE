---
title: Verschlüsselung für Skype, OneDrive, SharePoint und Exchange
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
description: In diesem Artikel finden Sie eine Beschreibung der Office 365 Verschlüsselung für Skype, OneDrive, SharePoint und Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9e250f3fe63875f2f1d65f2765e114f212e72f35
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44031395"
---
# <a name="encryption-for-skype-for-business-onedrive-for-business-sharepoint-online-and-exchange-online"></a>Verschlüsselung in Skype for Business, OneDrive for Business, SharePoint Online und Exchange Online

Microsoft 365 ist eine hochsichere Umgebung mit umfangreichem Schutz in mehreren Schichten: Sicherheit von physischen Rechenzentren, Netzwerksicherheit, Zugriffssicherheit, Anwendungssicherheit und Datensicherheit.

## <a name="skype-for-business"></a>Skype for Business

Skype for Business Kundendaten können in Ruhe in Form von Dateien oder Präsentationen gespeichert werden, die von Besprechungsteilnehmern hochgeladen werden. Der Webkonferenzserver verschlüsselt Kundendaten mithilfe von AES mit einem 256-Bit-Schlüssel. Die verschlüsselten Kundendaten werden in einer Dateifreigabe gespeichert. Jeder Teil der Kundendaten wird mit einem anderen zufällig generierten 256-Bit-Schlüssel verschlüsselt. Wenn ein Teil der Kundendaten in einer Konferenz freigegeben wird, weist der Webkonferenzserver die Konferenz Clients an, die verschlüsselten Kundendaten über HTTPS herunterzuladen. Der entsprechende Schlüssel wird an Clients gesendet, damit die Kundendaten entschlüsselt werden können. Der Webkonferenzserver authentifiziert auch Konferenz Clients, bevor er den Clients den Zugriff auf Konferenz Kundendaten ermöglicht. Wenn Sie an einer Webkonferenz teilnehmen, richtet jeder Konferenz Client zunächst ein SIP-Dialogfeld mit der Konferenz Fokus Komponente ein, die in dem Front-End-Server über TLS läuft. Der Konferenz Fokus übergibt dem Konferenz Client ein vom Webkonferenzserver generiertes Authentifizierungscookie. Der Konferenz Client stellt dann eine Verbindung mit dem Webkonferenzserver her, der das Authentifizierungscookie darstellt, um vom Server authentifiziert zu werden.

## <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online und OneDrive for Business

Alle Kundendateien in SharePoint Online werden durch eindeutige, dateispezifische Schlüssel geschützt, die immer exklusiv für einen einzelnen Mandanten sind. Die Schlüssel werden entweder vom SharePoint Online Dienst erstellt und verwaltet oder wenn der Kundenschlüssel von Kunden verwendet, erstellt und verwaltet wird. Wenn eine Datei hochgeladen wird, wird die Verschlüsselung von SharePoint Online im Kontext der Upload-Anforderung ausgeführt, bevor Sie an Azure Storage gesendet wird. Wenn eine Datei heruntergeladen wird, ruft SharePoint Online die verschlüsselten Kundendaten aus dem Azure-Speicher basierend auf der eindeutigen Dokument-ID ab und entschlüsselt die Kundendaten vor dem Senden an den Benutzer. Azure Storage hat keine Möglichkeit, die Kundendaten zu entschlüsseln oder sogar zu identifizieren oder zu verstehen. Alle Verschlüsselung und Entschlüsselung erfolgen in denselben Systemen, die die Mandanten Isolierung erzwingen, die Azure Active Directory und SharePoint Online sind.

Mehrere Arbeitslasten in Microsoft 365 speichern Daten in SharePoint Online, einschließlich Microsoft Teams, in dem alle Dateien in SharePoint Online gespeichert werden, und OneDrive für Unternehmen, die SharePoint Online für den Speicher verwendet. Alle in SharePoint Online gespeicherten Kundendaten werden verschlüsselt (mit einem oder mehreren AES 256-Bit-Schlüsseln) und wie folgt über das Rechenzentrum verteilt. (In jedem Schritt dieses Verschlüsselungsprozesses wird FIPS 140-2 Level 2 validiert. Weitere Informationen zur FIPS 140-2-Konformität finden Sie unter [FIPS 140-2 Compliance](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105)).)

- Jede Datei wird je nach Dateigröße in einen oder mehrere Chunks aufgeteilt. Jeder Chunk wird mit seinem eigenen eindeutigen AES 256-Bit-Schlüssel verschlüsselt.
- Wenn eine Datei aktualisiert wird, wird das Update auf die gleiche Weise behandelt: die Änderung wird in einen oder mehrere Chunks aufgeteilt, und jedes Segment wird mit einem separaten eindeutigen Schlüssel verschlüsselt.
- Diese Chunks – Dateien, Dateien und Update-Deltas – werden als BLOBs im Azure-Speicher gespeichert, die nach dem Zufallsprinzip über mehrere Azure-Speicherkonten verteilt werden.
- Die Gruppe von Verschlüsselungsschlüsseln für diese Segmente von Kundendaten ist selbst verschlüsselt.

    - Die zum Verschlüsseln der Blobs verwendeten Schlüssel werden in der SharePoint Online Inhaltsdatenbank gespeichert.
    - Die Inhaltsdatenbank ist durch Datenbankzugriffs Steuerelemente und Verschlüsselung im Rest geschützt. Die Verschlüsselung erfolgt mithilfe der [transparenten Datenverschlüsselung](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-tde) (DSA) in [Azure SQL-Datenbank](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview). (Azure SQL-Datenbank ist ein allgemeiner relationaler Datenbankdienst in Microsoft Azure, der Strukturen wie relationale Daten, JSON, Spatial und XML unterstützt.) Diese Geheimnisse befinden sich auf Dienstebene für SharePoint Online, nicht auf Mandantenebene. Diese Geheimnisse (manchmal auch als Hauptschlüssel bezeichnet) werden in einem separaten sicheren Repository gespeichert, das als Schlüsselspeicher bezeichnet wird. DSA bietet Sicherheit im Ruhezustand sowohl für die aktive Datenbank als auch für die Datenbanksicherungen und Transaktionsprotokolle.
    - Wenn Kunden den optionalen Schlüssel bereitstellen, wird der Kundenschlüssel in Azure Key Vault gespeichert, und der Dienst verwendet den Schlüssel zum Verschlüsseln eines Mandanten Schlüssels, der zum Verschlüsseln eines Standort Schlüssels verwendet wird, der dann zum Verschlüsseln der Tasten auf Dateiebene verwendet wird. Im Wesentlichen wird eine neue Schlüsselhierarchie eingeführt, wenn der Kunde einen Schlüssel bereitstellt.
- Die Karte, die zum erneuten zusammensetzen der Datei verwendet wird, wird zusammen mit den verschlüsselten Schlüsseln in der Inhaltsdatenbank gespeichert, getrennt vom Hauptschlüssel, der für die Entschlüsselung erforderlich ist.
- Jedes Azure-Speicherkonto verfügt über eigene eindeutige Anmeldeinformationen pro Zugriffstyp (lesen, schreiben, aufzählen und löschen). Jeder Satz von Anmeldeinformationen wird im sicheren Schlüsselspeicher aufbewahrt und regelmäßig aktualisiert. Wie oben beschrieben gibt es drei verschiedene Informationsspeichertypen mit jeweils einer eigenen Funktion:
    - Kundendaten werden als verschlüsselte BLOBs im Azure-Speicher gespeichert. Der Schlüssel zu jedem Segment von Kundendaten wird verschlüsselt und separat in der Inhaltsdatenbank gespeichert. Die Kundendaten selbst haben keine Anhaltspunkte dafür, wie Sie entschlüsselt werden können.
    - Die Inhaltsdatenbank ist eine SQL Server-Datenbank. Sie verfügt über die erforderliche Zuordnung zum Auffinden und erneuten zusammensetzen der in Azure Storage gespeicherten Kundendaten-BLOBs sowie der zum Verschlüsseln dieser BLOBs erforderlichen Schlüssel. Allerdings ist die Gruppe von Schlüsseln selbst verschlüsselt (wie oben erläutert) und in einem separaten Schlüsselspeicher gehalten.
    - Der Schlüsselspeicher ist physisch von der Inhaltsdatenbank und dem Azure-Speicher getrennt. Es werden die Anmeldeinformationen für jeden Azure-Speichercontainer und der Hauptschlüssel für den Satz von verschlüsselten Schlüsseln in der Inhaltsdatenbank gespeichert.

Jeder dieser drei Speicherkomponenten – der Azure-BLOB-Speicher, die Inhaltsdatenbank und der Schlüsselspeicher – ist physisch getrennt. Die Informationen in einer der Komponenten sind allein unbrauchbar. Ohne Zugriff auf alle drei ist es nicht möglich, die Schlüssel für die Chunks abzurufen, die Schlüssel zu entschlüsseln, um Sie nutzbar zu machen, die Schlüssel mit ihren entsprechenden Chunks zu verbinden, jeden Chunk zu entschlüsseln oder ein Dokument aus seinen konstituierenden Chunks neu zu erstellen.

BitLocker-Zertifikate, die die physischen Datenträger auf Computern im Rechenzentrum schützen, werden in einem sicheren Repository (SharePoint Online geheimen Speicher) gespeichert, das durch den Farm Schlüssel geschützt ist.

Die DSA-Tasten, die die pro-BLOB-Schlüssel schützen, werden an zwei Orten gespeichert:

- Das sichere Repository, das die BitLocker-Zertifikate beherbergt und durch den Farm Schlüssel geschützt ist; und
- In einem sicheren Repository, das von Azure SQL-Datenbank verwaltet wird.

Die Anmeldeinformationen, die für den Zugriff auf die Azure-Speichercontainer verwendet werden, werden auch im geheimen Speicher SharePoint Online aufbewahrt und bei Bedarf an jede SharePoint Online Farm delegiert. Diese Anmeldeinformationen sind Azure Storage SAS-Signaturen mit separaten Anmeldeinformationen, die zum Lesen oder Schreiben von Daten verwendet werden, und mit Richtlinie, die so angewendet wird, dass Sie automatisch alle 60 Tage ablaufen. Unterschiedliche Anmeldeinformationen werden verwendet, um Daten zu lesen oder zu schreiben (nicht beides), und SharePoint Online Farmen werden keine Berechtigungen zum Aufzählen erteilt.

> [!NOTE]
> Für Office 365 Kunden der US-Regierung werden Daten-BLOBs in Azure U.S. Government Storage gespeichert. Darüber hinaus ist der Zugriff auf SharePoint Online Schlüssel in Office 365 US-Regierung auf Office 365 Mitarbeiter, die speziell gezeigt wurden, limitiert. Azure US Government Operations Mitarbeiter haben keinen Zugriff auf den SharePoint Online Schlüsselspeicher, der zum Verschlüsseln von Daten-BLOBs verwendet wird.

Weitere Informationen zur Datenverschlüsselung in SharePoint Online und OneDrive für Unternehmen finden Sie unter [Datenverschlüsselung in OneDrive für Unternehmen und SharePoint Online](https://technet.microsoft.com/library/dn905447.aspx).

### <a name="list-items-in-sharepoint-online"></a>Auflisten von Elementen in SharePoint Online

Listenelemente sind kleinere Segmente von Kundendaten, die Ad-hoc erstellt werden oder die dynamischer innerhalb einer Website Leben können, wie Zeilen in einer vom Benutzer erstellten Liste, einzelne Beiträge in einem SharePoint Online-Blog oder Einträge in einer SharePoint Online Wiki-Seite. Listenelemente werden in der Inhaltsdatenbank (Azure SQL-Datenbank) gespeichert und mit DSA geschützt.

## <a name="encryption-of-data-in-transit"></a>Verschlüsselung von Daten während der Übertragung

In OneDrive for Business und SharePoint Online gibt es zwei Szenarien, in denen Daten in Rechenzentren ein- und ausgehen.

- Die **Client Kommunikation mit der Server Kommunikation mit** SharePoint Online und OneDrive für Unternehmen über das Internet verwendet TLS-Verbindungen.
- **Datenverlagerung zwischen Rechenzentren** – der Hauptgrund für das Verschieben von Daten zwischen Rechenzentren ist die geografische Replikation zur Aktivierung der Notfallwiederherstellung. Beispielsweise werden SQL Server-Transaktionsprotokolle und BLOB-Speicher-Deltas entlang dieser Pipe übertragen. Während diese Daten bereits über ein privates Netzwerk übertragen werden, werden sie zusätzlich durch branchenbeste Verschlüsselung geschützt.

## <a name="exchange-online"></a>Exchange Online

Exchange Online verwendet BitLocker für alle Postfachdaten, und die BitLocker-Konfiguration wird in [BitLocker for Encryption](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)beschrieben. Durch die Verschlüsselung auf Dienstebene werden alle Postfachdaten auf Postfachebene verschlüsselt. 

Zusätzlich zur Dienst Verschlüsselung unterstützt Microsoft 365 den Kundenschlüssel, der auf der Dienst Verschlüsselung basiert. Kundenschlüssel ist eine von Microsoft verwaltete Schlüssel Option für Exchange Online Dienst Verschlüsselung, die auch in der Roadmap von Microsoft zur Verfügung steht. Diese Verschlüsselungsmethode bietet erhöhten Schutz, der von BitLocker nicht gewährt wird, da Sie die Trennung von Serveradministratoren und kryptografischen Schlüsseln ermöglicht, die für die Entschlüsselung von Daten erforderlich sind, und da die Verschlüsselung direkt auf die Daten angewendet wird (im Gegensatz zu BitLocker, das die Verschlüsselung auf dem logischen Datenträgervolume verwendet), bleiben alle von einem Exchange-Server kopierten Kundendaten verschlüsselt

Der Bereich für die Exchange Online Dienst Verschlüsselung sind Kundendaten, die im Rest in Exchange Online gespeichert werden. (Skype for Business speichert fast alle vom benutzergenerierten Inhalte im Exchange Online Postfach des Benutzers und erbt daher das Dienst Verschlüsselungsfeature von Exchange Online.)
