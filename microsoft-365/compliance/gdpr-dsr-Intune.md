---
title: Intune-Datenbetreffsanforderungen für die DSGVO
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
author: dougeby
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
manager: angrobe
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: fa65d33795108a16759fa87d476bb5a4dc94a281
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285197"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>Intune-Datenbetreffsanforderungen für die DSGVO
Die europäische Datenschutz-Grundverordnung (DSGVO) gewährt Personen (die in den Bestimmungen als *betroffene Personen* bezeichnet werden) Berechtigungen zum Verwalten der personenbezogenen Daten, die von einem Arbeitgeber oder von einer anderen Art von Behörde oder Organisation (als *Datenverantwortlicher* oder nur *Verantwortlicher* bezeichnet) erfasst werden. Personenbezogene Daten sind im Rahmen der DSGVO sehr weitgefasst als Daten definiert, die sich auf eine identifizierte oder identifizierbare natürliche Person beziehen. Die DSGVO erteilt betroffenen Personen bestimmte Rechte für ihre personenbezogenen Daten; dazu gehören das Kopieren der personenbezogenen Daten, das Anfordern von Korrekturen, das Einschränken der Verarbeitung, das Löschen oder das Erhalten in einem elektronischen Format, damit sie zu einem anderen Datenverantwortlichen bewegt werden können. Eine formale Anforderung von einer betroffenen Person an einen Datenverantwortlichen im Hinblick auf eine bestimmte Aktion für deren persönliche Daten wird als *Antrag einer betroffenen Person* bezeichnet.

In diesem Leitfaden wird erläutert, wie Microsoft-Produkte, -Dienste und -Verwaltungstools verwendet werden können, um als Reaktion auf Anträge betroffener Personen unseren als Datenverantwortliche handelnden Kunden dabei zu helfen, personenbezogene Daten zu finden und auf diese zu reagieren. Dies umfasst das Suchen, den Zugriff und die Reaktion auf personenbezogene Daten, die in der Microsoft-Cloud gespeichert sind. Im Folgenden finden Sie eine kurze Übersicht den in diesem Leitfaden beschriebenen Prozesse:

1.  ***Ermittlung *** – verwenden Sie Such- und Ermittlungstools, um Kundendaten leichter zu finden, die möglicherweise Gegenstand eines Antrags einer betroffenen Person sind. Sobald potenziell geeignete Dokumente gefunden wurden, können Sie eine oder mehrere der Aktionen für Anträge betroffener Personen durchführen, die in den folgenden Schritten beschrieben sind, um auf den Antrag der betroffenen Person zu reagieren. Andernfalls können Sie bestimmen, dass der Antrag nicht den Unternehmensrichtlinien für die Reaktion auf Anträge betroffener Personen entspricht.

2.  ***Zugriff*** – rufen Sie personenbezogene Daten auf, die sich in der Microsoft-Cloud befinden, und erstellen Sie eine Kopie, die der betroffenen Person zur Verfügung gestellt werden kann, sofern dies beantragt wurde.

3.  ***Berichtigung*** – nehmen Sie gegebenenfalls Änderungen oder sonstige beantragte Aktionen an den personenbezogenen Daten vor.

4.  ***Beschränkung*** – schränken Sie die Verarbeitung personenbezogener Daten entweder durch Zurückziehen von Lizenzen für verschiedenen Azure-Dienste oder durch Deaktivieren der gewünschten Dienste wo möglich ein. Des Weiteren können Sie Daten aus der Microsoft-Cloud entfernen und diese lokal oder an einem anderen Ort aufbewahren.

5.  ***Löschung*** – entfernen Sie personenbezogene Daten, die sich in der Microsoft-Cloud befinden, dauerhaft.

6.  ***Export*** – stellen Sie der betroffenen Person eine elektronische Kopie (in einem maschinenlesbaren Format) von personenbezogenen Daten zur Verfügung.

In jedem Abschnitt dieses Leitfadens werden technische Verfahren beschrieben, die ein als Datenverantwortlicher handelndes Unternehmen nutzen kann, um auf einen Antrag einer betroffenen Person bezüglich personenbezogener Daten in der Microsoft-Cloud zu reagieren.

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
#### <a name="terminology"></a>Terminologie

Nachfolgend finden Sie Definitionen von Begriffen, die für diesen Leitfaden relevant sind.

-   *Datenverantwortlicher* – eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die allein oder gemeinsam mit anderen die Zwecke und Mittel der Verarbeitung personenbezogener Daten bestimmt. Sofern die Zwecke und Mittel der Verarbeitung durch das Recht der Union oder der Mitgliedstaaten bestimmt werden, können der Datenverantwortliche bzw. die spezifischen Kriterien für dessen Benennung durch das Recht der Union oder des Mitgliedstaats angegeben werden.

-   *Personenbezogene Daten* und *betroffene Person* – alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person („betroffene Person“) beziehen; als identifizierbar wird eine natürliche Person angesehen, die direkt oder indirekt, insbesondere mittels Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind.

-   *Datenverarbeiter* – eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die personenbezogene Daten im Auftrag des Datenverantwortlichen verarbeitet.

-   *Kundendaten*– alle Daten, einschließlich aller Text-, Ton-, Video- oder Bilddateien und Software, die Microsoft durch oder im Auftrag eines Kunden durch die Verwendung des Enterprise-Dienstes bereitgestellt werden. Kundendaten umfassen sowohl (1) Informationen zur Identifikation von Endbenutzern (z. B. Benutzernamen und Kontaktinformationen in Azure Active Directory) als auch Kundeninhalte, die ein Kunde in einen bestimmten Dienst hochlädt oder in diesem erstellt (z. B. Kundeninhalte in einem Azure Storage-Konto, Kundeninhalte in einer Azure SQL-Datenbank oder das Image einer virtuellen Maschine eines Kunden in Azure Virtual Machines).

-   *Vom System generierte Protokolle* – von Microsoft generierte Protokolle und verbundene Daten, die Microsoft bei der Bereitstellung von Enterprise-Diensten für Benutzer unterstützen. Vom System generierte Protokolle enthalten in erster Linie pseudonymisierte Daten, z. B. eindeutige Bezeichner – in der Regel eine vom System generierte Zahl, die von sich aus eine Einzelperson nicht identifizieren kann, aber dazu verwendet wird, die Enterprise-Dienste für Benutzer bereitzustellen. Vom System generierte Protokolle enthalten möglicherweise auch Informationen zur Identifikation über Endbenutzer, wie z. B. einen Benutzernamen.  

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

#### <a name="how-to-use-this-guide"></a>Verwenden dieses Leitfadens

Dieser Leitfaden besteht aus zwei Teilen:

**Teil 1: Reaktion auf Anträge betroffener Personen bezüglich Kundendaten** – In Teil 1  dieses Leitfadens wird erläutert, wie Sie auf Daten in Anwendungen zugreifen und diese korrigieren, einschränken und exportieren können, in denen Sie Daten verfasst haben. Dieser Abschnitt enthält Informationen zum Ausführen von Anträgen von betroffenen Personen in Bezug auf Kundeninhalte und Informationen zur Identifikation von Endbenutzern.

**Teil 2: Reaktion auf Anträge betroffener Personen bezüglich vom System generierten Protokollen** – Wenn Sie die Microsoft Enterprise-Dienste verwenden, generiert Microsoft einige Informationen, die als vom System generierte Protokolle bekannt sind, um den Dienst bereitzustellen. In Teil 2 dieses Leitfadens wird erläutert, wie Sie auf solche Daten in Azure zugreifen können und wie Sie sie löschen und exportieren können.

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>







### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Grundlegendes zu Anträgen betroffener Personen für Azure Active Directory und Microsoft Intune

Bei der Betrachtung von Diensten für Enterprise-Kunden muss das Ausführen von Anträgen betroffener Personen immer im Kontext eines bestimmten Azure Active Directory(AAD)-Mandanten verstanden werden. Anträge betroffener Personen werden insbesondere innerhalb eines bestimmten AAD-Mandanten ausgeführt. Wenn ein Benutzer in mehreren Mandanten beteiligt ist, ist es wichtig, darauf hinzuweisen, dass ein bestimmter Antrag einer betroffenen Person *nur* im Kontext des bestimmten Mandanten ausgeführt wird, innerhalb dem die Anforderung empfangen wurde. Dies ist wichtig, da die Ausführung eines Antrags einer betroffenen Person von einem Enterprise-Kunden **keine** Auswirkungen auf die Daten eines angrenzenden Enterprise-Kunden hat.

Das gleiche gilt auch für den einem Enterprise-Kunden zur Verfügung gestellten Microsoft Intune-Dienst: die Ausführung eines Antrags einer betroffenen Person bezüglich eines Intune-Kontos *in Verbindung mit einem ADD-Mandanten* **betrifft nur** Daten innerhalb des Mandanten. Darüber hinaus ist es wichtig, Folgendes beim Umgang mit Intune-Konten in einem Mandanten zu verstehen:

-   Wenn ein Intune-Benutzer ein Azure-Abonnement erstellt, wird das Abonnement so behandelt, als wäre es ein AAD-Mandant. Aus diesem Grund sind Anträge betroffener Personen innerhalb des Mandanten eingeschränkt, wie oben beschrieben.

-   Wenn ein über ein Intune-Konto erstelltes Azure-Abonnement gelöscht wird, **hat dies keine Auswirkungen** auf das eigentliche Intune-Konto. In diesem Fall ist wie bereits oben erwähnt die Ausführung von Anträgen betroffener Personen innerhalb des Azure-Abonnements auf den Umfang des Mandanten selbst beschränkt.

Anträge betroffener Personen bezüglich eines Intune-Kontos selbst **außerhalb eines bestimmten Mandanten**, werden über das Dashboard für den Datenschutz von Heimanwendern ausgeführt. Weitere Informationen finden Sie im Windows-Leitfaden zu Anträgen betroffener Personen.

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>Teil 1: Leitfaden zu Anträgen betroffener Personen bezüglich Kundendaten

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a>Ausführen von Anträgen betroffener Personen bezüglich Kundendaten

Microsoft bietet die Möglichkeit, auf bestimmte Kundendaten über das Azure-Portal und auch direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste (auch bezeichnet als *Oberflächen im Produkt*) zugreifen und diese löschen und exportieren. Details zu solchen Erfahrungen im Produkt werden in der jeweiligen Referenzdokumentation der entsprechenden Dienste beschrieben.

>[!Important]  
>Dienste, die Anträge betroffener Personen im Produkt unterstützen, erfordern die direkte Verwendung der Anwendungsprogrammierschnittstelle (API) oder der Benutzeroberfläche (UI) des Services, die die entsprechenden CRUD-Vorgänge (Erstellen, Lesen, Aktualisieren und Löschen) beschreiben. Aus diesem Grund muss die Ausführung von Anträgen betroffener Personen in einem bestimmten Dienst zusätzlich zur Ausführung eines Antrags einer betroffenen Person im Azure-Portal erfolgen, damit eine vollständige Anforderung für eine bestimmte betroffene Person abgeschlossen werden kann. Weitere Details finden Sie in der Referenzdokumentation bestimmter Dienste.

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-1-discover"></a>Schritt 1: Ermittlung

Der erste Schritt beim Antworten auf einen Antrag einer betroffenen Person ist die Suche nach den betroffenen personenbezogenen Daten. In diesem ersten Schritt – Suchen und Überprüfen der betroffenen personenbezogenen Daten – können Sie bestimmen, ob ein Antrag einer betroffenen Person den Anforderungen Ihres Unternehmens zur Anerkennung oder zur Ablehnung eines Antrags einer betroffenen Person entspricht. Nach dem Suchen und Überprüfen der betroffenen personenbezogenen Daten können Sie beispielsweise bestimmen, dass die Anforderung nicht den Voraussetzungen Ihres Unternehmens entspricht, da dadurch Rechte und Freiheiten anderer beeinträchtigt werden könnten.

Nachdem Sie die Daten gefunden haben, können Sie eine bestimmte Aktion durchführen, um der Anforderung durch die betroffene Person gerecht zu werden. Details finden Sie unter:
- [Datenerfassung](https://docs.microsoft.com/intune/privacy-data-collect)
- [Datenspeicherung und -verarbeitung](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Anzeigen von personenbezogenen Daten](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Schritt 2: Zugriff
Nachdem Sie Kundendaten mit personenbezogenen Daten gefunden haben, die möglicherweise mit einem Antrag einer betroffenen Person zusammenhängen, liegt es an Ihnen und Ihrer Organisation, zu entscheiden, welche Daten Sie der betroffenen Person zur Verfügung stellen. Sie können ihr eine Kopie des tatsächlichen Dokuments, eine entsprechend geschwärzte Version oder einen Screenshot mit dem Bereich, den Sie als zur Freigabe geeignet eingestuft haben zur Verfügung stellen. Für jede der folgenden Antworten auf eine Zugriffsanforderung müssen Sie eine Kopie des Dokuments oder eines anderen Elements, das die entsprechenden Daten enthält, abrufen.

Wenn Sie der betroffenen Person eine Kopie zur Verfügung stellen, müssen Sie personenbezogene Daten zu anderen betroffenen Personen und sämtliche vertraulichen Informationen möglicherweise entfernen oder schwärzen.

<span id="_Using_Content_Search_1" class="anchor"></span>Im Folgenden wird erläutert, wie Sie eine Kopie der Daten als Reaktion auf einen Antrag einer betroffenen Person erhalten können.

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>Microsoft bietet sowohl ein Portal als auch Oberflächen im Produkt, mit denen der Mandantenadministrator des Enterprise-Kunden Zugriffsanträge betroffener Personen verwalten kann. Zugriffsanträge betroffener Personen ermöglichen den Zugriff auf die personenbezogenen Daten des Benutzers, einschließlich: (a) Informationen zur Identifikation eines Endbenutzers und (b) vom System generierten Protokollen.

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
#### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft Intune bietet die Möglichkeit zum [Ermittlung von Kundendaten](#step-1-discover) direkt über Benutzeroberflächen (UIs) oder bereits vorhandene Anwendungsprogrammierschnittstellen (APIs).

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-3-rectify"></a>Schritt 3: Berichtigung

Wenn eine betroffene Person Sie gebeten hat, personenbezogene Daten zu berichtigen, die in den Daten Ihres Unternehmens gespeichert werden, müssen Sie und Ihr Unternehmen feststellen, ob der Anforderung nachzukommen ist. Die Berichtigung der Daten kann Aktionen wie Bearbeiten, Schwärzen oder Entfernen von personenbezogenen Daten aus einem Dokument oder anderen Typ oder Element umfassen. 

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>


 Als Datenverantwortlicher bietet Microsoft nicht die Möglichkeit, die vom System generierten Protokolle zu korrigieren, da diese auf Fakten basierende Aktivitäten widerspiegeln und einen historischen Datensatz der Ereignisse innerhalb von Microsoft-Diensten bilden. Administratoren können keine geräte- oder appspezifischen Informationen im Zusammenhang mit Intune aktualisieren. Wenn ein Endbenutzer personenbezogene Daten (wie den Gerätenamen) korrigieren möchte, muss dies direkt auf dem Gerät erfolgen. Solche Änderungen werden beim nächsten Herstellen einer Verbindung mit Intune synchronisiert.

### <a name="step-4-restrict"></a>Schritt 4: Einschränkung

<span id="_Delete" class="anchor"></span>Betroffene Personen verlangen möglicherweise, dass Sie die Verarbeitung ihrer personenbezogenen Daten einschränken. Wir bieten sowohl das Azure-Portal als auch bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI). Diese Oberflächen bieten dem Mandantenadministrator des Enterprise-Kunden die Möglichkeit, solche Anträge betroffener Personen durch eine Kombination aus Export und Löschen von Daten zu verwalten. Details finden Sie unter [Verarbeitung von personenbezogenen Daten](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
### <a name="step-5-delete"></a>Schritt 5: Löschung

Das „Recht auf Löschung“ durch das Entfernen personenbezogener Daten aus den Kundendaten einer Organisation ist ein wichtiger Schutz in der DSGVO. Das Entfernen personenbezogener Daten umfasst das Entfernen aller personenbezogenen Daten und vom System generierten Protokolle, mit Ausnahme der Überwachungsprotokollinformationen. Details finden Sie unter [Löschen der personenbezogenen von Endbenutzern](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).


<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>Teil 2: Vom System generierte Protokolle
Überwachungsprotokolle bieten Mandantenadministratoren einen Datensatz von Aktivitäten, die eine Änderung in Microsoft Intune generieren. Überwachungsprotokolle stehen für zahlreiche Verwaltungsaktivitäten zur Verfügung und dienen in der Regel zum Erstellen, Aktualisieren (Bearbeiten), Löschen und Zuweisen von Aktionen. Remoteaufgaben, die Überwachungsereignisse generieren, können auch überprüft werden. Diese Überwachungsprotokolle enthalten möglicherweise personenbezogene Daten von Benutzern, deren Geräte bei Intune registriert sind. Administratoren können Überwachungsprotokolle nicht löschen. Details finden Sie unter [Überwachen von personenbezogenen Daten](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).


## <a name="notify-about-exporting-or-deleting-issues"></a>Benachrichtigung über Probleme beim Exportieren oder Löschen
Wenn beim Exportieren oder Löschen von Daten aus dem Azure-Portal Probleme auftreten, rufen Sie das Azure-Portalblatt **Hilfe + Support** auf, und übermitteln Sie unter **Abonnementverwaltung > Andere Sicherheits- und Complianceanforderung > Datenschutzblatt und DSGVO-Anforderungen** ein neues Ticket.

#### <a name="learn-more"></a>Weitere Informationen
[Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)