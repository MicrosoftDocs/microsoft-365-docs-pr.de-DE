---
title: Isolierung und Zugriffskontrolle in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: 'Zusammenfassung: eine Erläuterung der Isolierung und Zugriffssteuerung in den verschiedenen Anwendungen von Microsoft 365.'
ms.openlocfilehash: 40a1f1d93fe34333366e456cc006ab2d1c700a83
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690614"
---
# <a name="isolation-and-access-control-in-microsoft-365"></a>Isolierung und Zugriffskontrolle in Microsoft 365

Azure Active Directory (Azure AD) und Microsoft 365 verwenden ein hoch komplexes Datenmodell, das Dutzende von Diensten, Hunderte von Entitäten, Tausende von Beziehungen und Zehntausende von Attributen umfasst. Auf einer hohen Ebene sind Azure AD und die Dienst Verzeichnisse die Container von Mandanten und Empfängern, die mithilfe von statusbasierten Replikationsprotokollen synchron gehalten werden. Zusätzlich zu den Verzeichnisinformationen, die in Azure AD aufbewahrt werden, verfügen alle Dienst Arbeitslasten über eine eigene Verzeichnisdienst-Infrastruktur.
 
![Microsoft 365 Mandantendaten Synchronisierung](../media/office-365-isolation-tenant-data-sync.png)

In diesem Modell gibt es keine einzelne Quelle für Verzeichnisdaten. Bestimmte Systeme besitzen einzelne Daten, aber kein einzelnes System besitzt alle Daten. Microsoft 365-Dienste kooperieren mit Azure AD in diesem Datenmodell. Azure AD ist das "System der Wahrheit" für freigegebene Daten, bei dem es sich typischerweise um kleine und statische Daten handelt, die von jedem Dienst verwendet werden. Das Verbundmodell, das in Microsoft 365 und Azure AD verwendet wird, stellt die freigegebene Ansicht der Daten bereit.

Microsoft 365 verwendet sowohl physischen Speicher als auch Azure-Cloud-Speicher. Exchange Online (einschließlich Exchange Online Schutz) und Skype for Business ihren eigenen Speicher für Kundendaten verwenden. SharePoint Online verwendet sowohl SQL Server Speicher als auch Azure-Speicher, daher ist die zusätzliche Isolierung von Kundendaten auf Speicherebene erforderlich.

## <a name="exchange-online"></a>Exchange Online

Exchange Online speichert Kundendaten in Postfächern. Postfächer werden in ESE-Datenbanken (Extensible Storage Engine) als Postfachdatenbanken gehostet. Dies umfasst Benutzerpostfächer, verknüpfte Postfächer, freigegebene Postfächer und Postfächer für Öffentliche Ordner. Zu den Benutzerpostfächern gehören gespeicherte Skype for Business Inhalte wie Unterhaltungs Verläufe.

Der Inhalt des Benutzerpostfachs umfasst Folgendes:

- E-Mails und e-Mail-Anhänge
- Kalender-und Frei/Gebucht-Informationen
- Kontakte
- Aufgaben
- Anmerkungen
- Gruppen
- Rückschluss Daten

Jede Postfachdatenbank in Exchange Online enthält Postfächer von mehreren Mandanten. Ein Autorisierungscode sichert jedes Postfach, auch innerhalb eines Mandanten. Standardmäßig hat nur der zugewiesene Benutzer Zugriff auf ein Postfach. Die Zugriffssteuerungsliste (Access Control List, ACL), die ein Postfach sichert, enthält eine Identität, die von Azure AD auf Mandantenebene authentifiziert wurde. Die Postfächer für jeden Mandanten sind auf Identitäten beschränkt, die für den Authentifizierungsanbieter des Mandanten authentifiziert wurden, der nur Benutzer von diesem Mandanten enthält. Inhalte in Mandant a können von Benutzern in Mandant B nicht in irgendeiner Weise abgerufen werden, es sei denn, Sie werden von Mandanten a ausdrücklich genehmigt.

## <a name="skype-for-business"></a>Skype for Business

Skype for Business speichert Daten an verschiedenen Stellen:

- Benutzer-und Kontoinformationen, einschließlich Verbindungs Endpunkten, Mandanten-IDs, Wähleinstellungen, Roamingeinstellungen, Anwesenheitsstatus, Kontaktlisten usw., werden auf den Skype for Business Active Directory Servern und in verschiedenen Skype for Business Datenbankservern gespeichert. Kontaktlisten werden im Exchange Online Postfach des Benutzers gespeichert, wenn der Benutzer für beide Produkte aktiviert ist, oder auf Skype for Business Servern, wenn der Benutzer dies nicht tut. Skype for Business Datenbankserver sind nicht partitioniert pro Mandanten, aber die mehrinstanzenfähige Isolierung von Daten wird über die rollenbasierte Zugriffssteuerung (Role-Based Access Control, RBAC) erzwungen.
- Besprechungsinhalte und hochgeladene Daten werden auf DFS-Freigaben (Distributed File System) gespeichert. Dieser Inhalt kann auch in Exchange Online archiviert werden, wenn dieser aktiviert ist. Die DFS-Freigaben werden nicht pro Mandant partitioniert. der Inhalt ist mit ACLs gesichert, und Mehrmandantenfähigkeit wird über RBAC erzwungen.
- Anruf Detaildatensätze, bei denen es sich um den Aktivitätsverlauf handelt, wie Anrufverlauf, Chatsitzungen, Anwendungsfreigabe, Chatverlauf usw., können auch in Exchange Online gespeichert werden, aber die meisten Anruf Detaildatensätze werden temporär auf KDS-Servern (Call Detail Record) gespeichert. Inhalt wird nicht pro Mandant partitioniert, aber Mehrmandantenfähigkeit wird über RBAC erzwungen.

## <a name="sharepoint-online"></a>SharePoint Online

SharePoint Online verfügt über mehrere unabhängige Mechanismen zur Datenisolierung. Sie speichert Objekte als abstrahierten Code in Anwendungsdatenbanken. Wenn ein Benutzer beispielsweise eine Datei in SharePoint Online hochlädt, wird die Datei zerlegt, in Anwendungscode übersetzt und in mehreren Tabellen über mehrere Datenbanken gespeichert.

Wenn ein Benutzer direkten Zugriff auf den Speicher erhält, der die Daten enthält, kann der Inhalt nicht für einen Menschen oder ein anderes System als SharePoint Online interpretiert werden. Diese Mechanismen umfassen Sicherheitszugriffssteuerung und Eigenschaften. Alle SharePoint Online Ressourcen werden durch den Autorisierungscode und die RBAC-Richtlinie gesichert, einschließlich innerhalb eines Mandanten. Die Zugriffssteuerungsliste (Access Control List, ACL), die eine Ressource sichert, enthält eine auf Mandantenebene authentifizierte Identität. SharePoint Online Daten für einen Mandanten sind auf vom Authentifizierungsanbieter für den Mandanten authentifizierte Identitäten limitiert.

Zusätzlich zu den ACLs wird eine Eigenschaft auf Mandantenebene, die den Authentifizierungsanbieter angibt (die mandantenspezifische Azure AD), einmal geschrieben und kann nicht mehr geändert werden, nachdem Sie festgelegt wurde. Nachdem die Mandanten Eigenschaft des Authentifizierungsanbieters für einen Mandanten festgelegt wurde, kann Sie nicht mithilfe aller für einen Mandanten verfügbar gemachten APIs geändert werden.

Für jeden Mandanten wird eine eindeutige *Abonnement* -Nr verwendet. Alle Kunden Standorte befinden sich im Besitz eines Mandanten und weisen dem Mandanten eine eindeutige *Abonnement* -Nummer zu. Die *Subscription* -Eigenschaft für eine Website wird einmal geschrieben und ist dauerhaft. Nachdem eine Website einem Mandanten zugewiesen wurde, kann Sie nicht zu einem anderen Mandanten verschoben werden. Die *Abonnement* -Nr ist der Schlüssel, der zum Erstellen des Sicherheitsbereichs für den Authentifizierungsanbieter verwendet wird und an den Mandanten gebunden ist.

SharePoint Online verwendet SQL Server und Azure-Speicher für die Speicherung von Inhaltsmetadaten. Der Partitionsschlüssel für den Inhaltsspeicher lautet *Site* -Nr in SQL. Bei der Ausführung einer SQL-Abfrage verwendet SharePoint Online eine *Website* -Überprüfung, die als Teil einer *Abonnement* -Bestätigung auf Mandantenebene überprüft wurde.

SharePoint Online speichert verschlüsselte Dateiinhalte in Microsoft Azure BLOBs. Jede SharePoint Online Farm verfügt über ein eigenes Microsoft Azure Konto, und alle in Azure gespeicherten BLOBs werden einzeln mit einem Schlüssel verschlüsselt, der im SQL-Inhaltsspeicher gespeichert ist. Der Verschlüsselungsschlüssel, der in Code von der Autorisierungs Schicht geschützt wird und nicht direkt für den Endbenutzer verfügbar gemacht wird. SharePoint Online verfügt über eine Echtzeitüberwachung, um zu erkennen, wann eine HTTP-Anforderung Daten für mehr als einen Mandanten liest oder schreibt. Die Anforderungs-ID- *Abonnement* -ID wird anhand der *Abonnement* -ID der aufgerufenen Ressource nachverfolgt. Anforderungen für den Zugriff auf Ressourcen von mehr als einem Mandanten sollten niemals durch Endbenutzer geschehen. Dienstanforderungen in einer Umgebung mit mehreren Mandanten sind die einzige Ausnahme. Der Suchcrawler zieht beispielsweise Inhaltsänderungen für eine gesamte Datenbank gleichzeitig durch. Dies umfasst normalerweise das Abfragen von Websites von mehr als einem Mandanten in einer einzelnen Dienstanforderung, was aus Effizienzgründen geschieht.

## <a name="teams"></a>Teams

Ihre Teams-Daten werden je nach Inhaltstyp unterschiedlich gespeichert. 

Eine ausführliche Erläuterung finden Sie unter [Ignite Breakout Session on Microsoft Teams Architecture](https://channel9.msdn.com/Events/Ignite/Microsoft-Ignite-Orlando-2017/BRK3071) .

### <a name="core-teams-customer-data"></a>Kern Teams Kundendaten

Wenn Ihr Mandant in Australien, Kanada, der Europäischen Union, Frankreich, Deutschland, Indien, Japan, Südafrika, Südkorea, der Schweiz (einschließlich Liechtenstein), den Vereinigten Arabischen Emiraten, dem Vereinigten Königreich oder den Vereinigten Staaten bereitgestellt wird, speichert Microsoft die folgenden Kundendaten in Ruhe nur an diesem Speicherort:

- Teams Chats, Team-und Kanal Unterhaltungen, Bilder, Voicemail-Nachrichten und Kontakte.
- SharePoint Online-Websiteinhalt und die auf der Website gespeicherten Dateien.
- Dateien, die in OneDrive für Arbeit oder Schule hochgeladen wurden.

#### <a name="chat-channel-messages-team-structure"></a>Chat, Kanal Nachrichten, Teamstruktur

Jedes Team in Teams wird von einer Microsoft 365-Gruppe und Ihrer SharePoint-Website und Ihrem Exchange-Postfach unterstützt. Private Chats (einschließlich Gruppenchats), Nachrichten, die im Rahmen einer Unterhaltung in einem Kanal gesendet werden, und die Struktur von Teams und Kanälen werden in einem in Azure ausgeführten Chatdienst gespeichert. Die Daten werden auch in einem verborgenen Ordner in den Benutzer-und Gruppen Postfächern gespeichert, um Funktionen zum Schutz von Informationen zu aktivieren.

#### <a name="voicemail-and-contacts"></a>Voicemail und Kontakte

Voicemails werden in Exchange gespeichert. Kontakte werden im Exchange-basierten Cloud-Datenspeicher gespeichert. Exchange und der Exchange-basierte Cloud Store bieten bereits Daten in jedem der weltweiten Rechenzentren GEOSS. Für alle Teams werden Voicemail und Kontakte in-Country für Australien, Kanada, Frankreich, Deutschland, Indien, Japan, die Vereinigten Arabischen Emirate, das Vereinigte Königreich, Südafrika, Südkorea, die Schweiz (einschließlich Liechtenstein) und die Vereinigten Staaten gespeichert. Für alle anderen Länder werden Dateien basierend auf der Mandanten Affinität im Standort USA, Europa oder im asiatisch-pazifischen Raum gespeichert.

#### <a name="images-and-media"></a>Bilder und Medien

In Chats verwendete Medien (mit Ausnahme von Giphy-GIFs, bei denen es sich nicht um einen Verweis Link zur ursprünglichen Giphy-Dienst-URL handelt, Giphy ist ein nicht von Microsoft stammender Dienst), wird in einem Azure-basierten Mediendienst gespeichert, der an denselben Stellen wie der Chatdienst bereitgestellt wird.

#### <a name="files"></a>Dateien

Dateien (einschließlich OneNote und wiki), die jemand in einem Kanal freigibt, werden auf der SharePoint-Website des Teams gespeichert. In einem privaten Chat oder einem Chat während einer Besprechung oder eines Anrufs freigegebene Dateien werden hochgeladen und im OneDrive for Work-oder School-Konto des Benutzers gespeichert, der die Datei freigibt. Exchange, SharePoint und OneDrive bieten bereits Daten in jedem der weltweiten Rechenzentren in GEOS. Für vorhandene Kunden sind also alle Dateien, OneNote-Notizbücher, wiki-Inhalte von Microsoft Teams und Postfächer, die Teil der Teams-Erfahrung sind, bereits basierend auf Ihrer Mandanten Affinität am Speicherort gespeichert. Dateien werden in-Country für Australien, Kanada, Frankreich, Deutschland, Indien, Japan, die Vereinigten Arabischen Emirate, das Vereinigte Königreich, Südafrika, Südkorea und die Schweiz (einschließlich Liechtenstein) gespeichert. Für alle anderen Länder werden Dateien basierend auf der Mandanten Affinität im Standort USA, Europa oder im asiatisch-pazifischen Raum gespeichert.
