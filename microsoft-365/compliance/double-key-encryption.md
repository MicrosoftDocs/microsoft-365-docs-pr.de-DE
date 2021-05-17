---
title: Double Key Encryption (DKE)
description: MIT DKE können Sie hochsensible Daten schützen und gleichzeitig die volle Kontrolle über Ihren Schlüssel beibehalten.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 746f1345b47694f4a4122edc5d89cc924441ea81
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408176"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Doppelschlüsselverschlüsselung für Microsoft 365

> *Gilt für: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), Azure [Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Anweisungen für: [Azure Information Protection unified labeling client for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *Dienstbeschreibung für: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Die Doppelschlüsselverschlüsselung (Double Key Encryption, DKE) verwendet zwei Schlüssel zusammen, um auf geschützte Inhalte zu zugreifen. Microsoft speichert einen Schlüssel in Microsoft Azure, und Sie halten den anderen Schlüssel. Sie behalten die volle Kontrolle über einen Ihrer Schlüssel mithilfe des Double Key Encryption-Diensts. Sie wenden den Schutz mithilfe des Azure Information Protection Unified Labeling-Clients auf Ihre hochsensiblen Inhalte an.

Die Doppelschlüsselverschlüsselung unterstützt sowohl Cloud- als auch lokale Bereitstellungen. Diese Bereitstellungen tragen dazu bei, sicherzustellen, dass verschlüsselte Daten undurchsichtig bleiben, unabhängig davon, wo Sie die geschützten Daten speichern.

Weitere Informationen zu den standardmäßigen, cloudbasierten Mandantenstammschlüsseln finden Sie unter [Planning and implementing your Azure Information Protection tenant key](/azure/information-protection/plan-implement-tenant-key).

## <a name="when-your-organization-should-adopt-dke"></a>Wann Ihre Organisation DKE übernehmen soll

Die Doppelschlüsselverschlüsselung ist für Ihre vertraulichen Daten vorgesehen, die den strengsten Schutzanforderungen unterliegen. DKE ist nicht für alle Daten vorgesehen. Im Allgemeinen verwenden Sie die Doppelschlüsselverschlüsselung, um nur einen kleinen Teil Ihrer Gesamtdaten zu schützen. Sie sollten vor der Bereitstellung die richtigen Daten ermitteln, die mit dieser Lösung zu decken sind. In einigen Fällen müssen Sie möglicherweise Ihren Bereich einen und andere Lösungen für die meisten Ihrer Daten verwenden, z. B. Microsoft Information Protection mit von Microsoft verwalteten Schlüsseln oder BYOK. Diese Lösungen sind ausreichend für Dokumente, die keinen erweiterten Schutz- und behördlichen Anforderungen unterliegen. Darüber hinaus ermöglichen ihnen diese Lösungen die Verwendung der leistungsstärksten Office 365 Dienste; Dienste, die Sie nicht mit DKE-verschlüsselten Inhalten verwenden können. Beispiel:

- Transportregeln, einschließlich Anti-Malware und Spam, die sichtbarkeit in der Anlage erfordern
- Microsoft Delve
- eDiscovery
- Inhaltssuche und Indizierung
- Office Web apps including coauthoring functionality

Externe Anwendungen oder Dienste, die nicht über das MIP SDK in DKE integriert sind, können keine Aktionen für die verschlüsselten Daten ausführen.

Das Microsoft Information Protection SDK 1.7+ unterstützt die Doppelschlüsselverschlüsselung. Anwendungen, die in unser SDK integriert sind, können mit ausreichenden Berechtigungen und Integrationen über diese Daten verfügen.

Es wird empfohlen, dass Organisationen Microsoft Information Protection-Funktionen (Klassifizierung und Bezeichnung) verwenden, um die meisten ihrer vertraulichen Daten zu schützen und dkE nur für ihre unternehmenskritischen Daten zu verwenden. Die Doppelschlüsselverschlüsselung ist für vertrauliche Daten in stark regulierten Branchen wie Finanzdienstleistungen und Gesundheitswesen relevant.

Wenn Ihre Organisationen eine der folgenden Anforderungen erfüllen, können Sie DKE verwenden, um Ihre Inhalte zu sichern:

- Sie möchten sicherstellen, *dass nur Sie* geschützte Inhalte unter allen Umständen entschlüsseln können.
- Sie möchten nicht, dass Microsoft allein zugriff auf geschützte Daten hat.
- Sie haben gesetzliche Anforderungen, um Schlüssel innerhalb einer geografischen Grenze zu halten. Alle Schlüssel, die Sie für die Datenverschlüsselung und -entschlüsselung speichern, werden in Ihrem Rechenzentrum verwaltet.

## <a name="system-and-licensing-requirements-for-dke"></a>System- und Lizenzierungsanforderungen für DKE

**Double Key Encryption for Microsoft 365** ist mit Microsoft 365 E5. Wenn Sie nicht über eine Microsoft 365 E5 verfügen, können Sie sich für eine Testversion [registrieren.](https://aka.ms/M365E5ComplianceTrial) Weitere Informationen zu diesen Lizenzen finden Sie [unter Microsoft 365 Lizenzierungsleitfade für & Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

**Azure Information Protection**. DKE arbeitet mit Vertraulichkeitsbezeichnungen und erfordert Azure Information Protection.

DKE-Vertraulichkeitsbezeichnungen werden Endbenutzern über das Vertraulichkeitsband in Office Desktop-Apps zur Verfügung stellen. Installieren Sie diese Voraussetzungen auf jedem Clientcomputer, auf dem Sie geschützte Dokumente schützen und nutzen möchten.

**Microsoft Office Apps for Enterprise** Version 2009 oder höher (Desktopversionen von Word, PowerPoint und Excel) auf Windows.

**Azure Information Protection Unified Labeling Client** Version 2.7.93.0 oder höher. Laden Sie den Unified Labeling-Client aus dem Microsoft Download Center herunter, und [installieren Sie den Client.](https://www.microsoft.com/download/details.aspx?id=53018)

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Unterstützte Umgebungen zum Speichern und Anzeigen von DKE-geschützten Inhalten

**Unterstützte Anwendungen**. [Microsoft 365 Apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.

**Online-Inhaltsunterstützung**. Sie können Dokumente und Dateien, die mit der Double Key Encryption geschützt sind, online in Microsoft SharePoint und OneDrive for Business. Sie müssen Dokumente und Dateien mit DKE durch unterstützte Anwendungen beschriften und schützen, bevor Sie an diese Speicherorte hochladen. Sie können verschlüsselte Inhalte per E-Mail freigeben, verschlüsselte Dokumente und Dateien können jedoch nicht online angezeigt werden. Stattdessen müssen Sie geschützte Inhalte mithilfe der unterstützten Desktopanwendungen und Clients auf Dem lokalen Computer anzeigen.

## <a name="overview-of-deploying-dke"></a>Übersicht über die Bereitstellung von DKE

Sie führen die folgenden allgemeinen Schritte zum Einrichten von DKE aus. Nachdem Sie diese Schritte abgeschlossen haben, können Ihre Endbenutzer Ihre hochsensiblen Daten mit der Double Key Encryption schützen.

1. Stellen Sie den DKE-Dienst wie in diesem Artikel beschrieben zur Verfügung.

2. Erstellen Sie eine Bezeichnung mit Double Key Encryption. Navigieren Sie zu Informationsschutz unter [Microsoft 365 Compliance Center,](https://compliance.microsoft.com) und erstellen Sie eine neue Bezeichnung mit Double Key Encryption. Weitere [Informationen finden Sie unter Einschränken des Zugriffs auf Inhalte mithilfe von Vertraulichkeitsbezeichnungen zum Anwenden der Verschlüsselung.](./encryption-sensitivity-labels.md)

3. Verwenden Sie Doppelschlüsselverschlüsselungsbezeichnungen. Schützen Sie Daten, indem Sie im Menüband Vertraulichkeit in der Datei "Double Key Encrypted" Microsoft Office.

Es gibt verschiedene Möglichkeiten, wie Sie einige der Schritte zum Bereitstellen der Double Key Encryption ausführen können. Dieser Artikel enthält ausführliche Anweisungen, damit weniger erfahrene Administratoren den Dienst erfolgreich bereitstellen können. Wenn Sie es sich bequem machen, können Sie ihre eigenen Methoden verwenden.

## <a name="deploy-dke"></a>Bereitstellen von DKE

In diesem Artikel und dem Bereitstellungsvideo wird Azure als Bereitstellungsziel für den DKE-Dienst verwendet. Wenn Sie an einem anderen Speicherort bereitstellen, müssen Sie eigene Werte bereitstellen.

Sehen Sie [sich das Bereitstellungsvideo](https://youtu.be/vDWfHN_kygg) zur Double Key Encryption an, um eine schrittweise Übersicht über die Konzepte in diesem Artikel zu erhalten. Das Video dauert ca. 18 Minuten.

Führen Sie die folgenden allgemeinen Schritte aus, um die Doppelschlüsselverschlüsselung für Ihre Organisation zu einrichten.

1. [Installieren von Softwarevoraussetzungen für den DKE-Dienst](#install-software-prerequisites-for-the-dke-service)
1. [Klonen des Double Key Encryption GitHub Repository](#clone-the-dke-github-repository)
1. [Ändern von Anwendungseinstellungen](#modify-application-settings)
1. [Generieren von Testschlüsseln](#generate-test-keys)
1. [Erstellen des Projekts](#build-the-project)
1. [Bereitstellen des DKE-Diensts und Veröffentlichen des Schlüsselspeichers](#deploy-the-dke-service-and-publish-the-key-store)
1. [Überprüfen Ihrer Bereitstellung](#validate-your-deployment)
1. [Registrieren des Schlüsselspeichers](#register-your-key-store)
1. [Erstellen von Vertraulichkeitsbezeichnungen mithilfe von DKE](#create-sensitivity-labels-using-dke)
1. [Aktivieren von DKE in Ihrem Client](#enable-dke-in-your-client)
1. [Migrieren geschützter Dateien von HYOK-Bezeichnungen zu DKE-Bezeichnungen](#migrate-protected-files-from-hyok-labels-to-dke-labels)

Wenn Sie fertig sind, können Sie Dokumente und Dateien mithilfe von DKE verschlüsseln. Weitere Informationen finden Sie [unter Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).

### <a name="install-software-prerequisites-for-the-dke-service"></a>Installieren von Softwarevoraussetzungen für den DKE-Dienst

Installieren Sie diese Voraussetzungen auf dem Computer, auf dem Sie den DKE-Dienst installieren möchten.

**.NET Core 3.1 SDK**. Laden Sie das SDK von [Download .NET Core 3.1 herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core/3.1)

**Visual Studio Code**. Laden Visual Studio Code von [https://code.visualstudio.com/](https://code.visualstudio.com) herunter. Führen Sie nach der Installation Visual Studio Code aus, und wählen **Sie Ansichtserweiterungen** \> **aus.** Installieren Sie diese Erweiterungen.

- C# für Visual Studio Code

- NuGet Paket-Manager

**Git-Ressourcen**. Laden Sie eine der folgenden Optionen herunter, und installieren Sie sie.

- [Git](https://git-scm.com/downloads)

- [GitHub Desktop](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** Sie müssen [OpenSSL installiert haben,](https://slproweb.com/products/Win32OpenSSL.html) um [Testschlüssel zu generieren,](#generate-test-keys) nachdem Sie DKE bereitgestellt haben. Stellen Sie sicher, dass Sie den Pfad für Umgebungsvariablen korrekt aufrufen. Weitere Informationen finden Sie unter "Hinzufügen des Installationsverzeichnisses zu [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) PATH".

### <a name="clone-the-dke-github-repository"></a>Klonen des DKE GitHub Repositorys

Microsoft stellt die DKE-Quelldateien in einem GitHub zur Verfügung. Sie klonen das Repository, um das Projekt lokal für die Verwendung In Ihrer Organisation zu erstellen. Das DKE-GitHub-Repository befindet sich unter [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

Die folgenden Anweisungen sind für unerfahrene Git- oder Visual Studio Code vorgesehen:

1. Wechseln Sie in Ihrem Browser zu: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

2. Wählen Sie rechts neben dem Bildschirm Code **aus.** Ihre Version der Benutzeroberfläche zeigt möglicherweise eine **Klon- oder Downloadschaltfläche** an. Wählen Sie dann in der angezeigten Dropdownliste das Kopiersymbol aus, um die URL in die Zwischenablage zu kopieren.

    Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Klonen Sie das Double Key Encryption Service Repository aus GitHub](../media/dke-clone.png)

3. Wählen Visual Studio Code **Befehlspalette** \> **anzeigen aus,** und wählen **Sie Git: Klonen aus.** Um zu der Option in der Liste zu wechseln, beginnen Sie mit der Eingabe, um die Einträge zu filtern, und wählen Sie sie dann aus der `git: clone` Dropdownliste aus. Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Visual Studio Code GIT:Clone-Option](../media/dke-vscode-clone.png)

4. Fügen Sie in das Textfeld die URL ein, die Sie aus Git kopiert haben, und wählen Sie **Klonen aus GitHub**.

5. Navigieren Sie **im angezeigten** Dialogfeld Ordner auswählen zu einem Speicherort, und wählen Sie diesen aus, um das Repository zu speichern. Wählen Sie an der Eingabeaufforderung **Öffnen aus.**

    Das Repository wird in Visual Studio Code geöffnet und zeigt die aktuelle Git-Verzweigung unten links an. Die Verzweigung sollte z. B. main **sein.** Beispiel:

   ![Screenshot des DKE-Repositorys in Visual Studio Code der Hauptverzweigung](../media/dke-vscode-main-branch.jpg)

6. Wenn Sie nicht in der Hauptverzweigung sind, müssen Sie sie auswählen. Wählen Visual Studio Code Zweig aus, und wählen Sie **haupt** aus der Liste der angezeigten Verzweigungen aus.

   > [!IMPORTANT]
   > Durch Auswählen der Hauptverzweigung wird sichergestellt, dass Sie über die richtigen Dateien zum Erstellen des Projekts verfügen. Wenn Sie nicht die richtige Verzweigung auswählen, wird die Bereitstellung fehlschlagen.

Ihr DKE-Quellrepository ist nun lokal eingerichtet. Ändern Sie [als Nächstes die Anwendungseinstellungen](#modify-application-settings) für Ihre Organisation.

### <a name="modify-application-settings"></a>Ändern von Anwendungseinstellungen

Zum Bereitstellen des DKE-Diensts müssen Sie die folgenden Anwendungseinstellungen ändern:

- [Einstellungen für den Schlüsselzugriff](#key-access-settings)
- [Mandanten- und Schlüsseleinstellungen](#tenant-and-key-settings)

Sie ändern anwendungseinstellungen in der appsettings.json-Datei. Diese Datei befindet sich im DoubleKeyEncryptionService-Repository, das Sie lokal unter DoubleKeyEncryptionService\src\customer-key-store geklont haben. In Visual Studio Code können Sie z. B. zu der Datei navigieren, wie in der folgenden Abbildung dargestellt.

![Suchen des appsettings.jsfür DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Einstellungen für den Schlüsselzugriff

Wählen Sie aus, ob die E-Mail- oder Rollenautorisierung verwendet werden soll. DKE unterstützt immer nur eine dieser Authentifizierungsmethoden.

- **E-Mail-Autorisierung**. Ermöglicht Ihrer Organisation, den Zugriff auf Schlüssel nur basierend auf E-Mail-Adressen zu autorisieren.

- **Rollenautorisierung**. Ermöglicht Ihrer Organisation, den Zugriff auf Schlüssel basierend auf Active Directory-Gruppen zu autorisieren, und erfordert, dass der Webdienst LDAP abfragen kann.

**So legen Sie schlüsselzugriffseinstellungen für DKE mithilfe der E-Mail-Autorisierung**

1. Öffnen Sieappsettings.js **on-Datei,** und suchen Sie die `AuthorizedEmailAddress` Einstellung.

2. Fügen Sie die E-Mail-Adresse oder -Adressen hinzu, die Sie autorisieren möchten. Trennen Sie mehrere E-Mail-Adressen durch doppelte Anführungszeichen und Kommas. Beispiel:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Suchen Sie die `LDAPPath` Einstellung, und entfernen Sie den Text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` zwischen den doppelten Anführungszeichen. Lassen Sie die doppelten Anführungszeichen an Ort und Stelle. Wenn Sie fertig sind, sollte die Einstellung wie dies aussehen.

   ```json
   "LDAPPath": ""
   ```

4. Suchen Sie die `AuthorizedRoles` Einstellung, und löschen Sie die gesamte Zeile.

Diese Abbildung zeigt die **appsettings.jsfür** die E-Mail-Autorisierung ordnungsgemäß formatierte Datei.

   ![The appsettings.json file showing email authorization method](../media/dke-email-accesssetting.png)

**So legen Sie schlüsselzugriffseinstellungen für DKE mithilfe der Rollenautorisierung**

1. Öffnen Sieappsettings.js **on-Datei,** und suchen Sie die `AuthorizedRoles` Einstellung.

2. Fügen Sie die Active Directory-Gruppennamen hinzu, die Sie autorisieren möchten. Trennen Sie mehrere Gruppennamen durch doppelte Anführungszeichen und Kommas. Beispiel:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Suchen Sie die `LDAPPath` Einstellung, und fügen Sie die Active Directory-Domäne hinzu. Beispiel:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Suchen Sie die `AuthorizedEmailAddress` Einstellung, und löschen Sie die gesamte Zeile.

Diese Abbildung zeigt die **appsettings.js,** die für die Rollenautorisierung ordnungsgemäß formatiert ist.

   ![appsettings.jsder Datei mit der Rollenautorisierungsmethode](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Mandanten- und Schlüsseleinstellungen

DkE-Mandanten- und -Schlüsseleinstellungen befinden sich in der **appsettings.json-Datei.**

**So konfigurieren Sie Mandanten- und Schlüsseleinstellungen für DKE**

1. Öffnen Sie **appsettings.json-Datei.**

2. Suchen Sie die `ValidIssuers` Einstellung, und ersetzen `<tenantid>` Sie sie durch Ihre Mandanten-ID. Sie können Ihre Mandanten-ID finden, indem Sie zum Azure-Portal gehen und die [Mandanteneigenschaften anzeigen.](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) Beispiel:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```
> [!NOTE]
> Wenn Sie den externen B2B-Zugriff auf Ihren Schlüsselspeicher aktivieren möchten, müssen Sie diese externen Mandanten auch in die Liste der gültigen Aussteller aufgenommen haben.

Suchen Sie die `JwtAudience` . Ersetzen `<yourhostname>` Sie durch den Hostnamen des Computers, auf dem der DKE-Dienst ausgeführt wird. Beispiel:

  > [!IMPORTANT]
  > Der Wert für `JwtAudience` muss genau mit dem Namen Ihres Hosts *übereinstimmen.* Sie können **localhost:5001 beim** Debuggen verwenden. Wenn Sie mit dem Debuggen fertig sind, müssen Sie diesen Wert jedoch auf den Hostnamen des Servers aktualisieren.

- `TestKeys:Name`. Geben Sie einen Namen für Ihren Schlüssel ein. Beispiel: `TestKey1`
- `TestKeys:Id`. Erstellen Sie eine GUID, und geben Sie sie als Wert `TestKeys:ID` ein. Beispiel: `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Sie können eine Website wie [den Online-GUID-Generator verwenden,](https://guidgenerator.com/) um eine GUID nach dem Zufallsprinzip zu generieren.

Diese Abbildung zeigt das richtige Format für Mandanten- und **Schlüsseleinstellungen** inappsettings.jsunter . `LDAPPath` ist für die Rollenautorisierung konfiguriert.

![Zeigt die richtigen Mandanten- und Schlüsseleinstellungen für DKE in der appsettings.jsein.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Generieren von Testschlüsseln

Nachdem Sie die Anwendungseinstellungen definiert haben, können Sie öffentliche und private Testschlüssel generieren.

So generieren Sie Schlüssel:

1. Führen Sie Windows Startmenü die OpenSSL-Eingabeaufforderung aus.

2. Wechseln Sie zu dem Ordner, in dem Sie die Testschlüssel speichern möchten. Die Dateien, die Sie durch Ausführen der Schritte in dieser Aufgabe erstellen, werden im gleichen Ordner gespeichert.

3. Generieren Sie den neuen Testschlüssel.

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. Generieren Sie den privaten Schlüssel.

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. Generieren Sie den öffentlichen Schlüssel.

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. Öffnen Sie in einem Texteditor **pubkeyonly.pem**. Kopieren Sie alle Inhalte in der **Datei pubkeyonly.pem,** mit Ausnahme der ersten und letzten Zeilen, in den Abschnittappsettings.js`PublicPem` **on-Datei.**

7. Öffnen Sie in einem Texteditor **privkeynopass.pem**. Kopieren Sie alle Inhalte in der **Datei "privkeynopass.pem"** mit Ausnahme der ersten und letzten Zeilen in den Abschnittappsettings.js`PrivatePem` **On-Datei.**

8. Entfernen Sie alle Leerzeichen und Newlines in den `PublicPem` Abschnitten `PrivatePem` und.

    > [!IMPORTANT]
    > Wenn Sie diesen Inhalt kopieren, löschen Sie keine der PEM-Daten.

9. Navigieren Visual Studio Code sie zur **Datei Startup.cs.** Diese Datei befindet sich im DoubleKeyEncryptionService-Repository, das Sie lokal unter DoubleKeyEncryptionService\src\customer-key-store\ geklont haben.

10. Suchen Sie die folgenden Zeilen:

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. Ersetzen Sie diese Zeilen durch den folgenden Text:

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    Die Endergebnisse sollten wie folgt aussehen.

    ![datei startup.cs für die öffentliche Vorschau](../media/dke-startupcs-usetestkeys.png)

Jetzt können Sie Ihr [DKE-Projekt erstellen.](#build-the-project)

### <a name="build-the-project"></a>Erstellen des Projekts

Verwenden Sie die folgenden Anweisungen, um das DKE-Projekt lokal zu erstellen:

1. Wählen Visual Studio Code im DKE-Dienstrepository  Befehlspalette anzeigen aus, und geben Sie \>  dann **build an** der Eingabeaufforderung ein.

2. Wählen Sie in der Liste **Aufgaben: Buildaufgabe ausführen aus.**

   Wenn keine Buildaufgaben gefunden wurden, wählen Sie **Buildaufgabe konfigurieren aus,** und erstellen Sie eine für .NET Core wie folgt.

   ![Konfigurieren fehlender Buildaufgabe für .NET](../media/dke-configurebuildtask.png)

   1. Wählen **Sie Erstellen tasks.jsaus Vorlage aus.**

      ![Erstellen tasks.jseiner Datei aus der Vorlage für DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. Wählen Sie in der Liste der Vorlagentypen **.NET Core aus.**

      ![Auswählen der richtigen Vorlage für DKE](../media/dke-tasksjsontemplate.png)

   3. Suchen Sie im Abschnitt Build den Pfad zur **Datei customerkeystore.csproj.** Wenn sie nicht da ist, fügen Sie die folgende Zeile hinzu:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. Führen Sie den Build erneut aus.

3. Stellen Sie sicher, dass im Ausgabefenster keine roten Fehler angezeigt werden.

   Wenn rote Fehler auftreten, überprüfen Sie die Konsolenausgabe. Stellen Sie sicher, dass Sie alle vorherigen Schritte ordnungsgemäß ausgeführt haben und die richtigen Buildversionen vorhanden sind.

4. Wählen **Sie** \> **Debuggen starten aus,** um den Prozess zu debuggen. Wenn Sie aufgefordert werden, eine Umgebung auszuwählen, wählen Sie **.NET core aus.**

   Der .NET-Kerndebugger wird in der Regel in `https://localhost:5001` gestartet. Gehen Sie zum Anzeigen des Testschlüssels zu, und fügen Sie einen Schrägstrich (/) und den `https://localhost:5001` Namen Des Schlüssels an. Beispiel:

   ```https
   https://localhost:5001/TestKey1
   ```

   Der Schlüssel sollte im JSON-Format angezeigt werden.

Das Setup ist nun abgeschlossen. Stellen Sie vor der Veröffentlichung des Keystores in appsettings.jsfür die JwtAudience-Einstellung sicher, dass der Wert für hostname genau mit dem Hostnamen des App-Diensts entspricht. Möglicherweise haben Sie es in localhost geändert, um den Build zu beheben.

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>Bereitstellen des DKE-Diensts und Veröffentlichen des Schlüsselspeichers

Stellen Sie den Dienst für Produktionsbereitstellungen entweder in einer Cloud eines Drittanbieters oder in einem lokalen [System zur Verfügung.](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)

Möglicherweise bevorzugen Sie andere Methoden, um Ihre Schlüssel zu bereitstellen. Wählen Sie die Methode aus, die für Ihre Organisation am besten funktioniert.

Für Pilotbereitstellungen können Sie in Azure bereitstellen und sofort los damit beginnen.

**So erstellen Sie eine Azure Web App-Instanz zum Hosten Ihrer DKE-Bereitstellung**

Um den Schlüsselspeicher zu veröffentlichen, erstellen Sie eine Azure App Service-Instanz zum Hosten Ihrer DKE-Bereitstellung. Als Nächstes veröffentlichen Sie Ihre generierten Schlüssel in Azure.

1. Melden Sie sich in Ihrem Browser beim [Microsoft Azure-Portal an,](https://ms.portal.azure.com)und wechseln Sie zu **App Services**  >  **Add**.

2. Wählen Sie Ihr Abonnement und Ihre Ressourcengruppe aus, und definieren Sie Ihre Instanzdetails.

   - Geben Sie den Hostnamen des Computers ein, auf dem Sie den DKE-Dienst installieren möchten. Stellen Sie sicher, dass der Name mit dem namen identisch ist, der für die JwtAudience-Einstellung in der Datei [**"appsettings.json" definiert**](#tenant-and-key-settings) ist. Der Wert, den Sie für den Namen bereitstellen, ist auch WebAppInstanceName.

   - Wählen **Sie für Veröffentlichen**, Code auswählen und für **Laufzeitstapel**  **.NET Core 3.1** aus.

   Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Hinzufügen ihres App-Diensts](../media/dke-azure-add-app-service.png)

3. Wählen Sie unten auf der Seite **Überprüfen + erstellen** aus, und wählen Sie dann Hinzufügen **aus.**

4. Gehen Sie wie folgt vor, um die generierten Schlüssel zu veröffentlichen:

   - [Veröffentlichen über ZipDeployUI](#publish-via-zipdeployui)
   - [Veröffentlichen über FTP](#publish-via-ftp)
   - [Veröffentlichen über Visual Studio 2019 oder höher](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>Veröffentlichen über ZipDeployUI

1. Wechseln Sie zu `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

   Beispiel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. Wechseln Sie in der Codebasis für den Schlüsselspeicher zum Ordner **customer-key-store\src\customer-key-store,** und vergewissern Sie sich, dass dieser Ordner die **Datei customerkeystore.csproj** enthält.

3. Ausführen: **dotnet publish**

   Im Ausgabefenster wird das Verzeichnis angezeigt, in dem die Veröffentlichung bereitgestellt wurde.

   Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. Senden Sie alle Dateien im Veröffentlichungsverzeichnis an .zip Datei. Stellen Sie beim .zip der Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der .zip befinden.

5. Ziehen Und ablegen Sie die .zip, die Sie erstellen, auf die oben geöffnete ZipDeployUI-Website. Beispiel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE wird bereitgestellt, und Sie können zu den von Ihnen erstellten Testschlüsseln navigieren. Fahren Sie mit [Validate your deployment below](#validate-your-deployment) fort.

#### <a name="publish-via-ftp"></a>Veröffentlichen über FTP

1. Verbinden app Service, den Sie oben erstellt [haben.](#deploy-the-dke-service-and-publish-the-key-store)

   Wechseln Sie in Ihrem Browser zu: **Azure portal**  >  **App Service** Deployment  >  **Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**.

2. Kopieren Sie die angezeigten Verbindungszeichenfolgen in eine lokale Datei. Sie verwenden diese Zeichenfolgen, um eine Verbindung mit dem Web-App-Dienst herzustellen und Dateien über FTP hochzuladen.

   Beispiel:

   ![Kopieren von Verbindungszeichenfolgen aus dem FTP-Dashboard](../media/dke-ftp-dashboard.png)

3. Wechseln Sie in der Codebasis für den Schlüsselspeicher zum **Verzeichnis customer-key-store\src\customer-key-store**.

4. Stellen Sie sicher, dass dieses Verzeichnis die **Datei customerkeystore.csproj** enthält.

5. Ausführen: **dotnet publish**

   Die Ausgabe enthält das Verzeichnis, in dem die Veröffentlichung bereitgestellt wurde.

   Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. Senden Sie alle Dateien im Veröffentlichungsverzeichnis an eine ZIP-Datei. Stellen Sie beim .zip der Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der .zip befinden.

7. Verwenden Sie von Ihrem FTP-Client die Verbindungsinformationen, die Sie kopiert haben, um eine Verbindung mit Ihrem App-Dienst herzustellen. Hochladen die .zip, die Sie im vorherigen Schritt erstellt haben, in das Stammverzeichnis Ihrer Web App.

DKE wird bereitgestellt, und Sie können zu den von Ihnen erstellten Testschlüsseln navigieren. Überprüfen Sie als Nächstes [Die Bereitstellung überprüfen.](#validate-your-deployment)

### <a name="validate-your-deployment"></a>Überprüfen Ihrer Bereitstellung

Überprüfen Sie nach der Bereitstellung von DKE mit einer der oben beschriebenen Methoden die Bereitstellung und die Einstellungen für den Schlüsselspeicher.

Ausführen:

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

Beispiel:

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

Stellen Sie sicher, dass in der Ausgabe keine Fehler angezeigt werden. Wenn Sie bereit sind, registrieren [Sie Ihren Schlüsselspeicher](#register-your-key-store).

Bei dem Schlüsselnamen wird die Zwischen- und Kleinschreibung beachtet. Geben Sie den Schlüsselnamen so ein, wie er in der Datei appsettings.jsangezeigt wird.

## <a name="register-your-key-store"></a>Registrieren des Schlüsselspeichers

Mit den folgenden Schritten können Sie Ihren DKE-Dienst registrieren. Die Registrierung Ihres DKE-Diensts ist der letzte Schritt bei der Bereitstellung von DKE, bevor Sie mit dem Erstellen von Bezeichnungen beginnen können.

So registrieren Sie den DKE-Dienst:

1. Öffnen Sie in Ihrem Browser [das Microsoft Azure Portal,](https://ms.portal.azure.com/)und wechseln Sie zu **All Services** \> **Identity** \> **App Registrations**.

2. Wählen **Sie Neue Registrierung** aus, und geben Sie einen aussagekräftigen Namen ein.

3. Wählen Sie einen Kontotyp aus den angezeigten Optionen aus.

   Wenn Sie Microsoft Azure einer nicht benutzerdefinierten Domäne wie **z.** B. onmicrosoft.com verwenden, wählen Sie nur Konten in diesem Organisationsverzeichnis **aus (nur Microsoft – Einzelner Mandant).**

   Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Neue App-Registrierung](../media/dke-app-registration.png)

4. Wählen Sie unten auf der Seite **Registrieren** aus, um die neue App-Registrierung zu erstellen.

5. Wählen Sie in Ihrer neuen App-Registrierung im linken Bereich unter **Verwalten** die Option **Authentifizierung aus.**

6. Wählen **Sie Plattform hinzufügen aus.**

7. Wählen Sie **im Popup** Plattformen konfigurieren die Option **Web aus.**

8. Geben **Sie unter Umleitungs-URIs** den URI Ihres Verschlüsselungsdiensts mit doppelschlüsseln ein. Geben Sie die APP-Dienst-URL ein, einschließlich Hostname und Domäne.

   Beispiel: https://mydkeservicetest.com

   - Die eingegebene URL muss mit dem Hostnamen übereinstimmen, in dem Ihr DKE-Dienst bereitgestellt wird.
   - Wenn Sie lokal mit Visual Studio testen, verwenden Sie **https://localhost:5001** .
   - In allen Fällen muss das Schema https **sein.**

   Stellen Sie sicher, dass der Hostname ihrem App Service-Hostnamen genau entspricht. Möglicherweise haben Sie es in eine `localhost` Problembehandlung für den Build geändert. In **appsettings.json** ist dieser Wert der Hostname, den Sie für festgelegt `JwtAudience` haben.

9. Aktivieren **Sie unter Implizite** Gewährung das Kontrollkästchen **ID-Token.**

10. Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.

11. Wählen Sie im linken Bereich **Api** verfügbar machen aus, und wählen Sie dann neben Anwendungs-ID-URI festlegen **aus.**

12. Wählen Sie **auf der Seite API verfügbar** machen im Bereich Bereiche, die von diesem **API-Bereich** definiert sind, Die Option Bereich hinzufügen **aus.** Im neuen Bereich:

    1. Definieren Sie den Bereichsnamen **als user_impersonation**.

    2. Wählen Sie die Administratoren und Benutzer aus, die zustimmen können.

    3. Definieren Sie alle verbleibenden erforderlichen Werte.

    4. Klicken Sie auf **Bereich hinzufügen**.

    5. Wählen **Sie oben** Speichern aus, um Ihre Änderungen zu speichern.

13. Wählen Sie auf **der Seite API verfügbar** machen im Bereich Autorisierte **Clientanwendungen** die Option **Clientanwendung hinzufügen aus.**

    In der neuen Clientanwendung:

    1. Definieren Sie die Client-ID als `d3590ed6-52b3-4102-aeff-aad2292ab01c` . Dieser Wert ist die Microsoft Office-Client-ID und ermöglicht Office, ein Zugriffstoken für Ihren Schlüsselspeicher abzurufen.

    2. Wählen **Sie unter** Autorisierte Bereiche den **user_impersonation** aus.

    3. Wählen Sie **Anwendung hinzufügen** aus.

    4. Wählen **Sie oben** Speichern aus, um Ihre Änderungen zu speichern.

    5. Wiederholen Sie diese Schritte, definieren Sie jedoch dieses Mal die Client-ID als `c00e9d32-3c8d-4a7d-832b-029040e7db99` . Dieser Wert ist die Azure Information Protection-Client-ID für einheitliche Bezeichnungen. 

Ihr DKE-Dienst ist jetzt registriert. Fahren Sie [fort, indem Sie Bezeichnungen mit DKE erstellen.](#create-sensitivity-labels-using-dke)

## <a name="create-sensitivity-labels-using-dke"></a>Erstellen von Vertraulichkeitsbezeichnungen mithilfe von DKE

Erstellen Sie Microsoft 365 Compliance Center eine neue Vertraulichkeitsbezeichnung, und wenden Sie die Verschlüsselung wie andernfalls an. Wählen **Sie Doppelschlüsselverschlüsselung verwenden aus,** und geben Sie die Endpunkt-URL für Ihren Schlüssel ein.

Beispiel:

> [!div class="mx-imgBorder"]
> ![Wählen Sie Doppelschlüsselverschlüsselung verwenden im Microsoft 365 Compliance Center aus.](../media/dke-use-dke.png)

Alle hinzugefügten DKE-Bezeichnungen werden für Benutzer in den neuesten Versionen von Microsoft 365 Apps for Enterprise.

> [!NOTE]
> Es kann bis zu 24 Stunden dauern, bis die Clients mit den neuen Bezeichnungen aktualisiert werden.

### <a name="enable-dke-in-your-client"></a>Aktivieren von DKE in Ihrem Client

Wenn Sie ein Office sind, ist DKE für Sie aktiviert. Aktivieren Sie andernfalls DKE für Ihren Client, indem Sie die folgenden Registrierungsschlüssel hinzufügen:

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>Migrieren geschützter Dateien von HYOK-Bezeichnungen zu DKE-Bezeichnungen

Wenn Sie möchten, können Sie nach abschluss der Einrichtung von DKE Inhalte, die Sie mithilfe von HYOK-Bezeichnungen geschützt haben, zu DKE-Bezeichnungen migrieren. Zum Migrieren verwenden Sie den AIP-Scanner. Informationen zu den ersten Schritte mit dem Scanner finden Sie unter [Was ist der einheitliche Bezeichnungsscanner](/azure/information-protection/deploy-aip-scanner)für Azure Information Protection? .

Wenn Sie keine Inhalte migrieren, bleiben Ihre HYOK-geschützten Inhalte davon unberührt.
