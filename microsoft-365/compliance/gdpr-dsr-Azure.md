---
title: Azure-Datenbetreffsanforderungen für die DSGVO
description: ''
keywords: Microsoft 365, Microsoft 365 Education, Microsoft 365-Dokumentation, DSGVO
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: 8066b7a69b8f6a8ec2a75eea4a8816f4c3b3ef93
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868228"
---
# <a name="azure-data-subject-requests-for-the-gdpr"></a>Azure-Datenbetreffsanforderungen für die DSGVO

## <a name="introduction-to-data-subject-requests-dsrs"></a>Einführung in Datenbetreffsanforderungen (DSRs)

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
### <a name="terminology"></a>Terminologie

Nachfolgend finden Sie Definitionen von Begriffen, die für diesen Leitfaden relevant sind.

-   *Datenverantwortlicher* – eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die allein oder gemeinsam mit anderen die Zwecke und Mittel der Verarbeitung personenbezogener Daten bestimmt. Sofern die Zwecke und Mittel der Verarbeitung durch das Recht der Union oder der Mitgliedstaaten bestimmt werden, können der Datenverantwortliche bzw. die spezifischen Kriterien für dessen Benennung durch das Recht der Union oder des Mitgliedstaats angegeben werden.

-   *Personenbezogene Daten* und *betroffene Person* – alle Informationen, die sich auf eine identifizierte oder identifizierbare natürliche Person („betroffene Person“) beziehen; als identifizierbar wird eine natürliche Person angesehen, die direkt oder indirekt, insbesondere mittels Zuordnung zu einer Kennung wie einem Namen, zu einer Kennnummer, zu Standortdaten, zu einer Online-Kennung oder zu einem oder mehreren besonderen Merkmalen identifiziert werden kann, die Ausdruck der physischen, physiologischen, genetischen, psychischen, wirtschaftlichen, kulturellen oder sozialen Identität dieser natürlichen Person sind.

-   *Datenverarbeiter* – eine natürliche oder juristische Person, öffentliche Behörde, Agentur oder andere Stelle, die personenbezogene Daten im Auftrag des Datenverantwortlichen verarbeitet.

-   *Kundendaten*– alle Daten, einschließlich aller Text-, Ton-, Video- oder Bilddateien und Software, die Microsoft durch oder im Auftrag eines Kunden durch die Verwendung des Enterprise-Dienstes bereitgestellt werden. Kundendaten umfassen sowohl (1) Informationen zur Identifikation von Endbenutzern (z. B. Benutzernamen und Kontaktinformationen in Azure Active Directory) als auch Kundeninhalte, die ein Kunde in einen bestimmten Dienst hochlädt oder in diesem erstellt (z. B. Kundeninhalte in einem Azure Storage-Konto, Kundeninhalte in einer Azure SQL-Datenbank oder das Image einer virtuellen Maschine eines Kunden in Azure Virtual Machines).

-   *Vom System generierte Protokolle* – von Microsoft generierte Protokolle und verbundene Daten, die Microsoft bei der Bereitstellung von Enterprise-Diensten für Benutzer unterstützen. Vom System generierte Protokolle enthalten in erster Linie pseudonymisierte Daten, z. B. eindeutige Bezeichner – in der Regel eine vom System generierte Zahl, die von sich aus eine Einzelperson nicht identifizieren kann, aber dazu verwendet wird, die Enterprise-Dienste für Benutzer bereitzustellen. Vom System generierte Protokolle enthalten möglicherweise auch Informationen zur Identifikation über Endbenutzer, wie z. B. einen Benutzernamen.

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

### <a name="how-to-use-this-guide"></a>Verwenden dieses Leitfadens

Dieser Leitfaden besteht aus zwei Teilen:

**Teil 1: Reaktion auf Anträge betroffener Personen bezüglich Kundendaten** – In Teil 1  dieses Leitfadens wird erläutert, wie Sie auf Daten in Anwendungen zugreifen und diese korrigieren, einschränken und exportieren können, in denen Sie Daten verfasst haben. Dieser Abschnitt enthält Informationen zum Ausführen von Anträgen von betroffenen Personen in Bezug auf Kundeninhalte und Informationen zur Identifikation von Endbenutzern.

**Teil 2: Reaktion auf Anträge betroffener Personen bezüglich vom System generierten Protokollen** – Wenn Sie die Microsoft Enterprise-Dienste verwenden, generiert Microsoft einige Informationen, die als vom System generierte Protokolle bekannt sind, um den Dienst bereitzustellen. In Teil 2 dieses Leitfadens wird erläutert, wie Sie auf solche Daten in Azure zugreifen können und wie Sie sie löschen und exportieren können.

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>

### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-service-accounts"></a>Grundlegendes zu Anträgen betroffener Personen für Azure Active Directory- und Microsoft-Dienstkonten

Bei der Betrachtung von Diensten für Enterprise-Kunden muss das Ausführen von Anträgen betroffener Personen immer im Kontext eines bestimmten Azure Active Directory(AAD)-Mandanten verstanden werden. Anträge betroffener Personen werden insbesondere innerhalb eines bestimmten AAD-Mandanten ausgeführt. Wenn ein Benutzer in mehreren Mandanten beteiligt ist, ist es wichtig, darauf hinzuweisen, dass ein bestimmter Antrag einer betroffenen Person *nur* im Kontext des bestimmten Mandanten ausgeführt wird, innerhalb dem die Anforderung empfangen wurde. Dies ist wichtig, da die Ausführung eines Antrags einer betroffenen Person von einem Enterprise-Kunden **keine** Auswirkungen auf die Daten eines angrenzenden Enterprise-Kunden hat.

Das gleiche gilt auch für Microsoft-Dienstkonten (Microsoft Service Accounts, MSA) im Kontext der einem Enterprise-Kunden zur Verfügung gestellten Dienste: die Ausführung eines Antrags einer betroffenen Person bezüglich eines MSA-Kontos *in Verbindung mit einem ADD-Mandanten* **betrifft nur** Daten innerhalb des Mandanten. Darüber hinaus ist es wichtig, Folgendes beim Umgang mit MSA-Konten in einem Mandanten zu verstehen:

-   Wenn ein MSA-Benutzer ein Azure-Abonnement erstellt, wird das Abonnement so behandelt, als wäre es ein AAD-Mandant. Aus diesem Grund sind Anträge betroffener Personen innerhalb des Mandanten eingeschränkt, wie oben beschrieben.

-   Wenn ein über ein MSA-Konto erstelltes Azure-Abonnement gelöscht wird, **hat dies keine Auswirkungen** auf das eigentliche MSA-Konto. In diesem Fall ist wie bereits oben erwähnt die Ausführung von Anträgen betroffener Personen innerhalb des Azure-Abonnements auf den Umfang des Mandanten selbst beschränkt.

Anträge betroffener Personen bezüglich eines MSA-Kontos selbst **außerhalb eines bestimmten Mandanten**, werden über das Dashboard für den Datenschutz von Heimanwendern ausgeführt. Weitere Informationen finden Sie im Windows-Leitfaden zu Anträgen betroffener Personen.

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>Teil 1: Leitfaden zu Anträgen betroffener Personen bezüglich Kundendaten

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

## <a name="executing-dsrs-against-customer-data"></a>Ausführen von Anträgen betroffener Personen bezüglich Kundendaten

Microsoft bietet die Möglichkeit, auf bestimmte Kundendaten über das Azure-Portal und auch direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste (auch bezeichnet als *Oberflächen im Produkt*) zugreifen und diese löschen und exportieren. Details zu solchen Erfahrungen im Produkt werden in der jeweiligen Referenzdokumentation der entsprechenden Dienste beschrieben.

>[Wichtig]  
> Dienste, die Anträge betroffener Personen im Produkt unterstützen, erfordern die direkte Verwendung der Anwendungsprogrammierschnittstelle (API) oder der Benutzeroberfläche (UI) des Services, die die entsprechenden CRUD-Vorgänge (Erstellen, Lesen, Aktualisieren und Löschen) beschreiben. Aus diesem Grund muss die Ausführung von Anträgen betroffener Personen in einem bestimmten Dienst zusätzlich zur Ausführung eines Antrags einer betroffenen Person im Azure-Portal erfolgen, damit eine vollständige Anforderung für eine bestimmte betroffene Person abgeschlossen werden kann. Weitere Details finden Sie in der Referenzdokumentation bestimmter Dienste.

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-1-discover"></a>Schritt 1: Ermittlung

Der erste Schritt beim Antworten auf einen Antrag einer betroffenen Person ist die Suche nach den betroffenen personenbezogenen Daten. In diesem ersten Schritt – Suchen und Überprüfen der betroffenen personenbezogenen Daten – können Sie bestimmen, ob ein Antrag einer betroffenen Person den Anforderungen Ihres Unternehmens zur Anerkennung oder zur Ablehnung eines Antrags einer betroffenen Person entspricht. Nach dem Suchen und Überprüfen der betroffenen personenbezogenen Daten können Sie beispielsweise bestimmen, dass die Anforderung nicht den Voraussetzungen Ihres Unternehmens entspricht, da dadurch Rechte und Freiheiten anderer beeinträchtigt werden könnten.

Nachdem Sie die Daten gefunden haben, können Sie eine bestimmte Aktion durchführen, um der Anforderung durch die betroffene Person gerecht zu werden.

<span id="_Toc511384807" class="anchor"><span id="_Toc511163878" class="anchor"><span id="_Toc511136235" class="anchor"><span id="_Toc511125168" class="anchor"><span id="_Toc511120755" class="anchor"><span id="_Toc511122662" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

[Azure Active Directory](https://azure.microsoft.com/services/active-directory/) ist ein cloudbasierter Verzeichnis- und Identitätsverwaltungsdienst für mehrere Mandanten von Microsoft. Sie können nach Information zur Identifikation von Endbenutzer, wie Benutzerprofil- und Benutzerarbeitsinformationen von Kunden und Mitarbeitern, die personenbezogene Daten enthalten, in Ihrer [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)(AAD)-Umgebung unter Verwendung des [ Azure-Portals](https://portal.azure.com/) suchen.

Dies ist besonders hilfreich, wenn Sie nach personenbezogenen Daten für einen bestimmten Benutzer suchen oder diese ändern möchten. Sie können auch Benutzerprofil- und Arbeitsinformationen hinzufügen oder ändern. Sie müssen sich bei einem Konto anmelden, das ein globaler Administrator für das Verzeichnis ist.

#### <a name="how-do-i-locate-or-view-user-profile-and-work-information"></a>Wie kann ich nach Benutzerprofilen und Arbeitsinformationen suchen oder diese anzeigen?

1. Melden Sie sich im [Azure-Portal](https://portal.azure.com/) mit einem Konto an, das ein globaler Administrator für das Verzeichnis ist.

1. Wählen Sie **Alle Dienste** aus, geben Sie **Benutzer und Gruppen** in das Textfeld ein und drücken Sie dann die **Eingabetaste**.

     ![Alle Dienste auswählen](media/azure-dsr_image3.png)

3. Wählen Sie auf dem Blatt **Benutzer und Gruppen** **Benutzer** aus.

     ![Benutzer auswählen](media/azure-dsr_image9.png)

4.  Wählen Sie auf dem Blatt **Benutzer und Gruppen** einen Benutzer aus der Liste aus und wählen Sie dann auf dem Blatt für den ausgewählten Benutzer **Profil** aus, um Benutzerprofilinformationen anzuzeigen, die möglicherweise personenbezogene Daten enthalten.

    ![Profil auswählen](media/azure-dsr_image5.png)

5. Wenn Sie Benutzerprofilinformationen hinzufügen oder ändern möchten, können Sie dies tun und dann in der Befehlsleiste **Speichern** auswählen.

<!-- steps 6 and 7 not in original 
6. On the blade for the selected user, select **Work Info** to view user work information that may contain personal data.

     ![Select work info](media/azure-dsr_image11.png)

7. If you need to add or change user work information, you can do so, and then, in the command bar, select **Save.**

end of text to isolate -->

<span id="_Toc511384808" class="anchor"><span id="_Toc511163879" class="anchor"><span id="_Toc511136236" class="anchor"><span id="_Toc511125169" class="anchor"><span id="_Toc511120756" class="anchor"><span id="_Toc511122663" class="anchor"></span></span></span></span></span></span>

### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

<span id="_Access" class="anchor"><span id="_Toc508792512" class="anchor"><span id="_Ref511119401" class="anchor"><span id="_Toc511122664" class="anchor"><span id="_Toc511120757" class="anchor"><span id="_Toc511125170" class="anchor"><span id="_Toc511136237" class="anchor"><span id="_Toc511163880" class="anchor"><span id="_Toc511384809" class="anchor"><span id="_Hlk503968195" class="anchor"></span></span></span></span></span></span></span></span></span></span>
## <a name="step-2-access"></a>Schritt 2: Zugriff

Nachdem Sie Kundendaten mit personenbezogenen Daten gefunden haben, die möglicherweise mit einem Antrag einer betroffenen Person zusammenhängen, liegt es an Ihnen und Ihrer Organisation, zu entscheiden, welche Daten Sie der betroffenen Person zur Verfügung stellen. Sie können ihr eine Kopie des tatsächlichen Dokuments, eine entsprechend geschwärzte Version oder einen Screenshot mit dem Bereich, den Sie als zur Freigabe geeignet eingestuft haben zur Verfügung stellen. Für jede der folgenden Antworten auf eine Zugriffsanforderung müssen Sie eine Kopie des Dokuments oder eines anderen Elements, das die entsprechenden Daten enthält, abrufen.

Wenn Sie der betroffenen Person eine Kopie zur Verfügung stellen, müssen Sie personenbezogene Daten zu anderen betroffenen Personen und sämtliche vertraulichen Informationen möglicherweise entfernen oder schwärzen.

<span id="_Using_Content_Search_1" class="anchor"></span>Im Folgenden wird erläutert, wie Sie eine Kopie der Daten als Reaktion auf einen Antrag einer betroffenen Person erhalten können.

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>Microsoft bietet sowohl ein Portal als auch Oberflächen im Produkt, mit denen der Mandantenadministrator des Enterprise-Kunden Zugriffsanträge betroffener Personen verwalten kann. Zugriffsanträge betroffener Personen ermöglichen den Zugriff auf die personenbezogenen Daten des Benutzers, einschließlich: (a) Informationen zur Identifikation eines Endbenutzers und (b) vom System generierten Protokollen.

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-3-rectify"></a>Schritt 3: Berichtigung

Wenn eine betroffene Person Sie gebeten hat, personenbezogene Daten zu berichtigen, die in den Daten Ihres Unternehmens gespeichert werden, müssen Sie und Ihr Unternehmen feststellen, ob der Anforderung nachzukommen ist. Die Berichtigung der Daten kann Aktionen wie Bearbeiten, Schwärzen oder Entfernen von personenbezogenen Daten aus einem Dokument oder anderen Typ oder Element umfassen. Nachfolgend finden Sie die zweckmäßigste Möglichkeit hierzu für Microsoft-Support- und FastTrack-Daten.

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

Enterprise-Kunden haben die Möglichkeit, Berichtigungsanträge betroffener Personen zu verwalten, einschließlich eingeschränkter Bearbeitungsfunktionen entsprechend der Natur eines bestimmten Microsoft-Dienstes. Als Datenverantwortlicher bietet Microsoft nicht die Möglichkeit, die vom System generierten Protokolle zu korrigieren, da diese auf Fakten basierende Aktivitäten widerspiegeln und einen historischen Datensatz der Ereignisse innerhalb von Microsoft-Diensten bilden. Im Hinblick auf Azure Active Directory gibt es eingeschränkte Bearbeitungsfunktionen, um Informationen zur Identifikation eines Endbenutzers wie unten beschrieben zu korrigieren.

#### <a name="azure-active-directory-rectifycorrect-inaccurate-or-incomplete-personal-data"></a>Azure Active Directory: Berichtigen/Korrigieren ungenauer oder unvollständiger personenbezogener Daten

Sie können Informationen zur Identifikation von Endbenutzer, wie Benutzerprofil- und Benutzerarbeitsinformationen von Kunden und Mitarbeitern, die personenbezogene Daten, z. B. den Namen des Benutzers, den Arbeitstitel, die Adresse oder die Telefonnummer, in Ihrer [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)(AAD)-Umgebung unter Verwendung des [Azure-Portals](https://portal.azure.com/) korrigieren, aktualisieren oder löschen. Sie müssen sich mit einem Konto anmelden, das ein globaler Administrator für das Verzeichnis ist.

##### <a name="how-do-i-correct-or-update-user-profile-and-work-information-in-azure-active-directory"></a>Wie kann ich Benutzerprofil- und Arbeitsinformationen in Azure Active Directory korrigieren oder aktualisieren?

1.  Melden Sie sich im [Azure-Portal](https://portal.azure.com/) mit einem Konto an, das ein globaler Administrator für das Verzeichnis ist.

2.  Wählen Sie **Alle Dienste** aus, geben Sie **Benutzer und Gruppen** in das Textfeld ein und drücken Sie dann die **Eingabetaste**.

    ![Alle Dienste auswählen](media/azure-dsr_image3.png)

3.  Wählen Sie auf dem Blatt **Benutzer und Gruppen** **Benutzer** aus.
         
    ![Benutzer auswählen](media/azure-dsr_image9.png)

4.  Wählen Sie auf dem Blatt **Benutzer und Gruppen** einen Benutzer aus der Liste aus und wählen Sie dann auf dem Blatt für den ausgewählten Benutzer **Profil** aus, um Benutzerprofilinformationen anzuzeigen, die korrigiert oder aktualisiert werden müssen.

    ![Profil auswählen](media/azure-dsr_image5.png)

5.  Korrigieren oder aktualisieren Sie die Daten und wählen Sie dann in der Befehlsleiste **Speichern** aus.

6.  Wählen Sie auf dem Blatt für den ausgewählten Benutzer **Arbeitsinformationen** aus, um Benutzerarbeitsinformationen anzuzeigen, die korrigiert oder aktualisiert werden müssen.

    ![Arbeitsinformationen auswählen](media/azure-dsr_image4.png)

7.  Korrigieren oder aktualisieren Sie Benutzerarbeitsinformationen und wählen Sie dann in der Befehlsleiste **Speichern** aus.

<span id="_Toc511384814" class="anchor"><span id="_Toc511163885" class="anchor"><span id="_Toc511136242" class="anchor"><span id="_Toc511125175" class="anchor"><span id="_Toc511120762" class="anchor"><span id="_Toc511122669" class="anchor"></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

<span id="_Gain_access_to" class="anchor"><span id="_Toc508792521" class="anchor"><span id="_Toc511122670" class="anchor"><span id="_Toc511120763" class="anchor"><span id="_Toc511125176" class="anchor"><span id="_Toc511136243" class="anchor"><span id="_Toc511163886" class="anchor"><span id="_Toc511384815" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-4-restrict"></a>Schritt 4: Einschränkung

<span id="_Delete" class="anchor"></span>Betroffene Personen verlangen möglicherweise, dass Sie die Verarbeitung ihrer personenbezogenen Daten einschränken. Wir bieten sowohl das Azure-Portal als auch bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI). Diese Oberflächen bieten dem Mandantenadministrator des Enterprise-Kunden die Möglichkeit, solche Anträge betroffener Personen durch eine Kombination aus Export und Löschen von Daten zu verwalten. Ein Kunde kann (1) eine elektronische Kopie der personenbezogenen Daten des Benutzers exportieren, einschließlich (a) Konto/Konten, (b) vom System generierten Protokollen und (c) verbundenen Protokollen, gefolgt von einer (2) Löschung des Kontos und verbundener Daten, die innerhalb von Microsoft-Systemen gespeichert werden.

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
## <a name="step-5-delete"></a>Schritt 5: Löschung

Das „Recht auf Löschung“ durch das Entfernen personenbezogener Daten aus den Kundendaten eines Unternehmens ist ein wichtiger Schutz in der DSGVO. Das Entfernen personenbezogener Daten umfasst das Entfernen aller personenbezogenen Daten und vom System generierten Protokolle, mit Ausnahme der Überwachungsprotokollinformationen. Wenn ein Benutzer **vorläufig gelöscht** wird (siehe unten), wird das Konto für 30 Tage deaktiviert. Wenn während dieses 30-tägigen Zeitraums keine weitere Aktion durchgeführt wird, wird der Benutzer **dauerhaft gelöscht** (siehe unten). Bei einer **dauerhaft Löschung** wird das Konto des Benutzers, personenbezogene Daten und vom System generierte Protokolle werden innerhalb weiterer 30 Tage ausgelöscht. Wenn ein Mandantenadministrator sofort eine **dauerhafte Löschung** veranlasst, werden das Konto des Benutzers, personenbezogene Daten und vom System generierte Protokolle innerhalb von 30 Tagen nach der Veranlassung ausgelöscht.

>[Wichtig] Sie müssen ein Mandantenadministrator sein, um einen Benutzer von einem Mandanten löschen zu können.

<span id="_Toc511384817" class="anchor"><span id="_Toc511163888" class="anchor"><span id="_Toc511136245" class="anchor"><span id="_Toc511125178" class="anchor"><span id="_Toc511120765" class="anchor"><span id="_Toc511122672" class="anchor"><span id="_Ref511119801" class="anchor"></span></span></span></span></span></span></span>

### <a name="delete-a-user-and-associated-data-through-the-azure-portal"></a>Löschen eines Benutzers und der verbundenen Daten über das Azure-Portal

Nachdem Sie eine Anforderung zur Löschung erhalten haben, können Sie das Azure-Portal sowohl zum Löschen eines Benutzer und der verbundenen personenbezogenen Daten als auch zum Löschen von vom System generierten Protokollen verwenden.

Durch das Löschen diese Daten löschen Sie ebenfalls den Benutzer aus dem Mandanten. Benutzer werden zunächst vorläufig gelöscht, was bedeutet, dass das Konto von einem Mandantenadministrator innerhalb von 30 Tagen, während es zum vorläufigen Löschen gekennzeichnet ist, wiederhergestellt werden kann. Nach 30 Tagen wird das Konto automatisch und dauerhaft zu aus dem Mandanten gelöscht. Vor diesen 30 Tagen können Sie manuell einen vorläufig gelöschten Benutzer im Papierkorb löschen.

Im Folgenden finden Sie Schritte auf einer hohen Ebene zum Löschen von Benutzern aus Ihrem Mandanten.

1.  Rufen Sie das Azure-Portal auf und suchen Sie nach dem Benutzer.

2.  Löschen Sie den Benutzer. Wenn Sie den Benutzer das erste Mal löschen, wird das Konto des Benutzers in den Papierkorb gesendet. **An diesem Punkt ist der Benutzer vorläufig gelöscht, d. h. das Konto ist deaktiviert, aber nicht aus Azure Active Directory gelöscht.**

3.  Rufen Sie die Liste der kürzlich gelöschten Benutzer auf und löschen Sie den Benutzer dauerhaft. **An diesem Punkt ist der Benutzer dauerhaft gelöscht (auch bekannt als endgültig gelöscht), d. h. das Konto wurde aus Azure Active Directory ausgelöscht.**

##### <a name="to-delete-a-user-from-an-azure-tenant"></a>So löschen Sie einen Benutzer aus einem Azure-Mandanten

1.  Öffnen Sie das Azure-Portal, wählen Sie das Blatt **Azure Active Directory** aus und wählen Sie dann **Benutzer** aus.

    Das Blatt **Benutzer – alle Benutzer** wird angezeigt.

    ![Benutzer suchen](media/azure-dsr_image8.png)

2.  Aktivieren Sie das Kontrollkästchen neben dem Benutzer, den Sie löschen möchten, wählen Sie **Benutzer löschen** aus und wählen Sie dann **Ja** in dem Feld aus, in dem Sie gefragt werden, ob Sie den Benutzer löschen möchten.

    ![Benutzerverwaltung](media/azure-dsr_image9.png)

3.  Wählen Sie im Dropdown-Feld **Anzeigen** die Option **Kürzlich gelöschte Benutzer** aus.

    ![Benutzerprofil anzeigen](media/azure-dsr_image10.png)

4.  Wählen Sie denselben Benutzer erneut aus, wählen Sie **Dauerhaft löschen** aus und wählen Sie dann **Ja** im dem Feld aus, in dem Sie gefragt werden, ob Sie sicher sind.

>[Wichtig]  
>Beachten Sie, dass Sie den Benutzer und alle verbundenen Daten und vom System generierte Protokolle dauerhaft und unwiderruflich löschen, indem Sie auf **Ja** klicken. Wenn Sie dies versehentlich tun, müssen Sie den Benutzer manuell wieder zum Mandanten hinzufügen. Die verbundenen Daten und die vom System generierten Protokolle werden nicht wiederhergestellt.

   ![Benutzerarbeitsinformationen anzeigen](media/azure-dsr_image11.png)

<span id="_Export" class="anchor"><span id="_Step_6:_Export" class="anchor"><span id="_Toc511116629" class="anchor"><span id="_Toc511122673" class="anchor"><span id="_Toc511120766" class="anchor"><span id="_Toc511125179" class="anchor"><span id="_Toc511136246" class="anchor"><span id="_Toc511163889" class="anchor"><span id="_Toc508792534" class="anchor"></span></span></span></span></span></span></span></span></span>

### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

<span id="_Toc511384819" class="anchor"><span id="_Toc511163890" class="anchor"><span id="_Toc511136247" class="anchor"><span id="_Toc511125180" class="anchor"><span id="_Toc511120767" class="anchor"><span id="_Toc511122674" class="anchor"></span></span></span></span></span></span>
## <a name="step-6-export"></a>Schritt 6: Export

<span id="_Power_BI_2" class="anchor"></span>Durch das „Recht auf Datenübertragbarkeit“ kann eine betroffene Person eine Kopie ihrer personenbezogenen Daten in einem elektronischen Format (d. h. strukturierten, gängigen, maschinenlesbaren und kompatiblen Format“) anfordern, die an einen anderen Datenverantwortlichen übertragen werden kann. Azure unterstützt dies dadurch, dass Ihr Unternehmen die Daten im ursprünglichen JSON-Format zum angegebenen Azure Storage-Container exportieren kann.

>[Wichtig] Sie müssen ein Mandantenadministrator sein, um Benutzerdaten aus dem Mandanten exportieren zu können.

<span id="_Toc511384820" class="anchor"><span id="_Toc511163891" class="anchor"><span id="_Toc511136248" class="anchor"><span id="_Toc511125181" class="anchor"><span id="_Toc511120768" class="anchor"><span id="_Toc511122675" class="anchor"><span id="_Ref511119875" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

Im Hinblick auf Kundendaten bietet Microsoft sowohl ein Portal als auch Oberflächen im Produkt, mit denen der Mandantenadministrator des Enterprise-Kunden Exportanforderungen für Informationen zur Identifikation eines Endbenutzers verwalten kann.

<span id="_Toc511384821" class="anchor"><span id="_Toc511163892" class="anchor"></span></span>
### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>Teil 2: Vom System generierte Protokolle


Microsoft bietet Ihnen auch die Möglichkeit, auf bestimmte vom System generierte Protokolle in Verbindung mit der Verwendung von Azure eines Benutzers zuzugreifen und diese zu löschen und zu exportieren.

>[!Important]
> Die Möglichkeit, vom System generierte Protokolle einzuschränken oder zu berichtigen, wird nicht unterstützt. Vom System generierte Protokolle stellen auf Fakten basierende Aktionen dar, die innerhalb der Microsoft-Cloud und der Diagnosedaten durchgeführt werden. Änderungen an solchen Daten würden den historischen Datensatz von Aktionen beeinträchtigen und die Betrugs- und Sicherheitsrisiken erhöhen.

<span id="_Toc511384823" class="anchor"><span id="_Toc511163894" class="anchor"><span id="_Toc511136252" class="anchor"><span id="_Toc511125185" class="anchor"><span id="_Toc511120772" class="anchor"><span id="_Toc511122679" class="anchor"></span></span></span></span></span></span>
## <a name="executing-dsrs-against-system-generated-logs"></a>Ausführen von Anträgen betroffener Personen bezüglich vom System generierter Protokolle

Microsoft bietet die Möglichkeit, auf bestimmte vom System generierte Protokolle über das Azure-Portal und auch direkt über programmgesteuerte Schnittstellen oder Benutzeroberflächen für bestimmte Dienste zuzugreifen und diese zu löschen und zu exportieren. Details werden in der jeweiligen Referenzdokumentation der entsprechenden Dienste beschrieben.

>[!Important]  
> Dienste, die Anträge betroffener Personen im Produkt unterstützen, erfordern die direkte Verwendung der Anwendungsprogrammierschnittstelle (API) oder der Benutzeroberfläche (UI) des Services. Aus diesem Grund **muss die Ausführung eines Antrags im Produkt in einem bestimmten Dienst zusätzlich zur Ausführung eines Antrags einer betroffenen Person im Azure-Portal erfolgen, damit eine vollständige Anforderung für eine bestimmte betroffene Person abgeschlossen werden kann. Weitere Details finden Sie in der Referenzdokumentation bestimmter Dienste.**

<span id="_Toc511384824" class="anchor"><span id="_Toc511163895" class="anchor"><span id="_Toc511136253" class="anchor"><span id="_Toc511125186" class="anchor"><span id="_Toc511120773" class="anchor"><span id="_Toc511122680" class="anchor"><span id="_Ref511119063" class="anchor"><span id="_Toc508792552" class="anchor"><span id="_Toc509825622" class="anchor"></span></span></span></span></span></span></span></span></span>
## <a name="step-1-access"></a>Schritt 1: Zugriff 

Der Mandantenadministrator ist die einzige Person in Ihrem Unternehmen, die auf vom System generierte Protokolle in Verbindung mit der Verwendung von Azure eines bestimmten Benutzers zugreifen kann. Die Daten, die für eine Zugriffsanforderung abgerufen werden, werden in einem maschinenlesbaren Format und in Dateien bereitgestellt, durch die die Benutzer wissen, mit welchen Diensten die Daten verbunden sind. Wie bereits oben erwähnt, enthalten die abgerufenen Daten keine Daten, die die Sicherheit des Dienstes gefährden könnten.

<span id="_Toc511384825" class="anchor"><span id="_Toc511163896" class="anchor"><span id="_Toc511136254" class="anchor"><span id="_Toc511125187" class="anchor"><span id="_Toc511120774" class="anchor"><span id="_Toc511122681" class="anchor"><span id="_Toc511119129" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft bietet sowohl ein Portal als auch Oberflächen im Produkt, mit denen der Mandantenadministrator des Enterprise-Kunden Zugriffsanträge verwalten kann. Zugriffsanträge ermöglichen den Zugriff auf die personenbezogenen Daten des Benutzers, einschließlich: (a) Informationen zur Identifikation eines Endbenutzers und (b) vom System generierten Protokollen. Der Prozess entspricht dem im Abschnitt „Azure Active Directory“ beschriebenen Prozess in Teil 1, Schritt 2: Zugriff.

<span id="_Toc511384826" class="anchor"><span id="_Toc511163897" class="anchor"><span id="_Toc511136255" class="anchor"><span id="_Toc511125188" class="anchor"><span id="_Toc511120775" class="anchor"><span id="_Toc511122682" class="anchor"><span id="_Toc511119130" class="anchor"></span></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

<span id="_Toc511384827" class="anchor"><span id="_Toc511163898" class="anchor"><span id="_Toc511136256" class="anchor"><span id="_Toc511125189" class="anchor"><span id="_Toc511120776" class="anchor"><span id="_Toc511122683" class="anchor"><span id="_Toc508792553" class="anchor"><span id="_Toc509825623" class="anchor"></span></span></span></span></span></span></span></span>
## <a name="step-2-delete"></a>Schritt 2: Löschen

Der Mandantenadministrator ist die einzige Person in Ihrem Unternehmen, die einen Antrag einer betroffenen Person zur Löschung für einen bestimmten Benutzer innerhalb eines Azure-Mandanten ausführen kann.

<span id="_Toc511384828" class="anchor"><span id="_Toc511163899" class="anchor"><span id="_Toc511136257" class="anchor"><span id="_Toc511125190" class="anchor"><span id="_Toc511120777" class="anchor"><span id="_Toc511122684" class="anchor"><span id="_Toc511119563" class="anchor"></span></span></span></span></span></span></span>
### <a name="azure-active-directory"></a>Azure Active Directory

Microsoft bietet sowohl ein Portal als auch Oberflächen im Produkt, mit denen der Mandantenadministrator des Enterprise-Kunden Anträge betroffener Personen zum Löschen verwalten kann. Anträge betroffener Personen zum Löschen befolgen dieselben Schritte, wie im Abschnitt „Löschen eines Benutzers und der verbundenen Daten über das Azure-Portal“ in Teil 1, Schritt 5: Löschen beschrieben.

<span id="_Toc511384829" class="anchor"><span id="_Toc511163900" class="anchor"><span id="_Toc511136258" class="anchor"><span id="_Toc511125191" class="anchor"><span id="_Toc511120778" class="anchor"><span id="_Toc511122685" class="anchor"><span id="_Toc511119564" class="anchor"></span></span></span></span></span></span></span>
### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

<span id="_Toc511384830" class="anchor"><span id="_Toc511163901" class="anchor"><span id="_Toc511136259" class="anchor"><span id="_Toc511125192" class="anchor"><span id="_Toc511120779" class="anchor"><span id="_Toc511122686" class="anchor"><span id="_Toc508792554" class="anchor"><span id="_Toc509825624" class="anchor"></span></span></span></span></span></span></span></span>

## <a name="step-3-export"></a>Schritt 3: Export

Der Mandantenadministrator ist die einzige Person in Ihrem Unternehmen, die auf vom System generierte Protokolle in Verbindung mit der Verwendung von Azure eines bestimmten Benutzers zugreifen kann. Die Daten, die für eine Exportanforderung abgerufen werden, werden in einem maschinenlesbaren Format und in Dateien bereitgestellt, durch die die Benutzer wissen, mit welchen Diensten die Daten verbunden sind. Wie bereits oben erwähnt, enthalten die abgerufenen Daten keine Daten, die die Sicherheit oder die Stabilität des Dienstes gefährden könnten.

<span id="_Toc511384831" class="anchor"><span id="_Toc511163902" class="anchor"></span></span>
### <a name="export-system-generated-logs-using-the-azure-portal"></a>Exportieren von vom System generierten Protokollen mit dem Azure-Portal

Nachdem Sie eine Exportanforderung für eine betroffene Person erhalten haben, können Sie vom System generierte Protokolle, die mit diesem Benutzer verbunden sind, mit dem Azure-Portal exportieren.

Im Folgenden finden Sie Schritte auf einer hohen Ebene zum Exportieren von Daten aus Ihrem Mandanten.

1.  Rufen Sie das Azure-Portal auf und erstellen Sie eine Exportanforderung im Auftrag des Benutzers.

2.  Exportieren Sie die Daten und die senden Sie Datei an den Benutzer.

##### <a name="to-export-a-users-info-from-an-azure-tenant"></a>So exportieren Sie Informationen eines Benutzers aus einem Azure-Mandanten

1.  Öffnen Sie das Azure-Portal, wählen Sie **Alle Dienste** aus, geben Sie *Richtlinie* in den Filter ein und wählen Sie dann **Richtlinie** aus.

     ![Alle Dienste filtern ](media/azure-dsr_image12.png)

2.  Wählen Sie im Blatt **Richtlinie** die Option **Datenschutz** und dann die Option **Benutzeranforderungen verwalten** aus und wählen Sie dann **Exportanforderung hinzufügen** aus.

    ![Exportanforderung hinzufügen ](media/azure-dsr_image13.png)

3.  Schließen Sie die **Anforderung zum Exportieren von Daten** ab:

    ![Neue Anforderung zum Exportieren von Daten](media/azure-dsr_image14.png)

-   **Benutzer** – geben Sie die E-Mail-Adresse des Azure Active Directory-Benutzers ein, der den Export angefordert hat.

-   **Abonnement** – wählen Sie das Konto aus, das Sie verwenden, um den Ressourceneinsatz festzuhalten und um die Dienste in Rechnung zu stellen. Dies ist auch der Ort für Ihr Azure Storage-Konto.

-   **Speicherkonto** – wählen Sie den Speicherort Ihres Azure Storage (Blob) aus. Weitere Informationen finden Sie im Artikel [Einführung in Microsoft Azure Storage – Blob-Speicher](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage).

-   **Container** – erstellen Sie eine neuen (oder wählen Sie einen bestehenden) Container als Speicherort die exportieren vertraulichen Daten des Benutzers.

4.  Wählen Sie **Erstellen** aus.

Die Exportanforderung wechselt in den Status **Ausstehend**. Sie können den Berichtstatus auf dem Blatt **Datenschutz – Übersicht** anzeigen.
>
>[Wichtig]  
>Da personenbezogene Daten aus mehreren Systemen stammen können, ist es möglich, dass der Exportvorgang bis zum Abschluss zu einen Monat dauern kann.

<span id="_Toc511384832" class="anchor"><span id="_Toc511163903" class="anchor"></span></span>

### <a name="service-specific-interfaces"></a>Dienstspezifische Schnittstellen

Microsoft bietet die Möglichkeit zur Ermittlung von Kundendaten direkt über bereits vorhandene Anwendungsprogrammierschnittstellen (APIs) oder Benutzeroberflächen (UI) für bestimmte Dienste. Details werden in der jeweiligen Referenzdokumentation zu entsprechenden CRUD-Vorgängen (Erstellen, Lesen, Aktualisieren, Löschen) beschrieben.

## <a name="notify-about-exporting-or-deleting-issues"></a>Benachrichtigung über Probleme beim Exportieren oder Löschen
Wenn beim Exportieren oder Löschen von Daten aus dem Azure-Portal Probleme auftreten, rufen Sie das Azure-Portalblatt **Hilfe + Support** auf, und übermitteln Sie unter **Abonnementverwaltung > Andere Sicherheits- und Complianceanforderung > Datenschutzblatt und DSGVO-Anforderungen** ein neues Ticket.

#### <a name="learn-more"></a>Weitere Informationen
[Microsoft Trust Center](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)