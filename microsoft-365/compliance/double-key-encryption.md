---
title: Double Key Encryption (DKE)
description: MIT DKE können Sie streng vertrauliche Daten schützen und gleichzeitig die vollständige Kontrolle über Ihren Schlüssel behalten.
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
ms.openlocfilehash: b9696f26dd8f68ba291eab50e11a4cb6dd55ab7a
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226911"
---
# <a name="double-key-encryption-for-microsoft-365"></a>Doppelschlüsselverschlüsselung für Microsoft 365

> *Gilt für: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance,](https://www.microsoft.com/microsoft-365/business/compliance-management) [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*
>
> *Anweisungen für: [Azure Information Protection-Client für einheitliche Bezeichnungen für Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*
>
> *Dienstbeschreibung für: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Die Doppelschlüsselverschlüsselung (Double Key Encryption, DKE) verwendet zwei Schlüssel zusammen, um auf geschützte Inhalte zuzugreifen. Microsoft speichert einen Schlüssel in Microsoft Azure, und Sie halten den anderen Schlüssel. Sie behalten die vollständige Kontrolle über einen Ihrer Schlüssel mithilfe des Double Key Encryption-Diensts. Sie wenden den Schutz mithilfe des Azure Information Protection-Clients für einheitliche Bezeichnungen auf Ihre streng vertraulichen Inhalte an.

Double Key Encryption unterstützt sowohl Cloudbereitstellungen als auch lokale Bereitstellungen. Diese Bereitstellungen tragen dazu bei, sicherzustellen, dass verschlüsselte Daten überall dort, wo Sie die geschützten Daten speichern, undurchsichtig bleiben.

Weitere Informationen zu den standardmäßigen, cloudbasierten Mandantenstammschlüsseln finden Sie unter [Planen und Implementieren Ihres Azure Information Protection-Mandantenschlüssels.](/azure/information-protection/plan-implement-tenant-key)

## <a name="when-your-organization-should-adopt-dke"></a>Wann Ihre Organisation DKE einführen soll

Die Verschlüsselung mit Doppelschlüssel ist für Ihre vertraulichsten Daten vorgesehen, die den strengsten Schutzanforderungen unterliegen. DKE ist nicht für alle Daten vorgesehen. Im Allgemeinen verwenden Sie die Doppelschlüsselverschlüsselung, um nur einen kleinen Teil Ihrer Gesamtdaten zu schützen. Sie sollten die richtigen Daten, die mit dieser Lösung behandelt werden sollen, vor der Bereitstellung mit der gebotenen Sorgfalt ermitteln. In einigen Fällen müssen Sie möglicherweise Ihren Umfang eingrenzen und andere Lösungen für die meisten Daten verwenden, z. B. Microsoft Information Protection mit von Microsoft verwalteten Schlüsseln oder BYOK. Diese Lösungen sind für Dokumente ausreichend, die keinen erweiterten Schutzmaßnahmen und behördlichen Anforderungen unterliegen. Darüber hinaus können Sie mit diesen Lösungen die leistungsstärksten Office 365 Dienste verwenden. Dienste, die Sie nicht mit verschlüsselten DKE-Inhalten verwenden können. Beispiel:

- Transportregeln, einschließlich Antischadsoftware und Spam, die Sichtbarkeit in der Anlage erfordern
- Microsoft Delve
- eDiscovery
- Inhaltssuche und -indizierung
- Office Web-Apps, einschließlich Funktionen für die gemeinsame Dokumenterstellung

Alle externen Anwendungen oder Dienste, die nicht über das MIP SDK in DKE integriert sind, können keine Aktionen für die verschlüsselten Daten ausführen.

Das Microsoft Information Protection SDK 1.7+ unterstützt die Doppelschlüsselverschlüsselung. Anwendungen, die in unser SDK integriert sind, können über diese Daten mit ausreichenden Berechtigungen und Integrationen verfügen.

Wir empfehlen Organisationen, die Microsoft Information Protection-Funktionen (Klassifizierung und Bezeichnung) zu verwenden, um die meisten ihrer vertraulichen Daten zu schützen, und dke nur für ihre unternehmenskritischen Daten zu verwenden. Die Doppelschlüsselverschlüsselung ist für vertrauliche Daten in stark regulierten Branchen wie Finanzdienstleistungen und Gesundheitswesen relevant.

Wenn Ihre Organisationen eine der folgenden Anforderungen haben, können Sie DKE verwenden, um Ihre Inhalte zu schützen:

- Sie möchten sicherstellen, dass *nur Sie* geschützte Inhalte unter allen Umständen entschlüsseln können.
- Sie möchten nicht, dass Microsoft allein Zugriff auf geschützte Daten hat.
- Sie haben gesetzliche Vorschriften, um Schlüssel innerhalb einer geografischen Grenze zu halten. Alle Schlüssel, die Sie für die Datenverschlüsselung und -entschlüsselung aufbewahren, werden in Ihrem Rechenzentrum verwaltet.

## <a name="system-and-licensing-requirements-for-dke"></a>System- und Lizenzierungsanforderungen für DKE

**Die Doppelschlüsselverschlüsselung für Microsoft 365** ist mit Microsoft 365 E5 verbunden. Wenn Sie nicht über eine Microsoft 365 E5 Lizenz verfügen, können Sie sich für eine [Testversion](https://aka.ms/M365E5ComplianceTrial)registrieren. Weitere Informationen zu diesen Lizenzen finden Sie [unter Microsoft 365 Lizenzierungsleitfaden für sicherheitsbezogene & Compliance.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

**Azure Information Protection**. DKE arbeitet mit Vertraulichkeitsbezeichnungen und erfordert Azure Information Protection.

DKE-Vertraulichkeitsbezeichnungen werden Endbenutzern über das Vertraulichkeitsmenüband in Office Desktop-Apps zur Verfügung gestellt. Installieren Sie diese erforderlichen Komponenten auf jedem Clientcomputer, auf dem Sie geschützte Dokumente schützen und nutzen möchten.

**Microsoft Office Apps for Enterprise** Version 2009 oder höher (Desktopversionen von Word, PowerPoint und Excel) auf Windows.

**Azure Information Protection Unified Labeling Client** Version 2.7.93.0 oder höher. Laden Sie den Unified Labeling-Client aus dem [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=53018)herunter, und installieren Sie es.

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a>Unterstützte Umgebungen zum Speichern und Anzeigen von DKE-geschützten Inhalten

**Unterstützte Anwendungen.** [Microsoft 365 Apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) Clients auf Windows, einschließlich Word, Excel und PowerPoint.

**Unterstützung von Onlineinhalten.** Sie können Dokumente und Dateien, die mit der Doppelschlüsselverschlüsselung geschützt sind, online sowohl in Microsoft SharePoint als auch in OneDrive for Business speichern. Sie müssen Dokumente und Dateien mit DKE von unterstützten Anwendungen bezeichnen und schützen, bevor Sie an diese Speicherorte hochladen. Sie können verschlüsselte Inhalte per E-Mail freigeben, aber keine verschlüsselten Dokumente und Dateien online anzeigen. Stattdessen müssen Sie geschützte Inhalte mithilfe der unterstützten Desktopanwendungen und Clients auf Ihrem lokalen Computer anzeigen.

## <a name="overview-of-deploying-dke"></a>Übersicht über die Bereitstellung von DKE

Sie führen diese allgemeinen Schritte zum Einrichten von DKE aus. Nachdem Sie diese Schritte abgeschlossen haben, können Ihre Endbenutzer Ihre streng vertraulichen Daten mit der Double Key Encryption schützen.

1. Stellen Sie den DKE-Dienst wie in diesem Artikel beschrieben bereit.

2. Erstellen Sie eine Bezeichnung mit Doppelschlüsselverschlüsselung. Navigieren Sie unter dem [Microsoft 365 Compliance Center](https://compliance.microsoft.com) zum Informationsschutz, und erstellen Sie eine neue Bezeichnung mit Doppelschlüsselverschlüsselung. Weitere Informationen finden Sie unter [Einschränken des Zugriffs auf Inhalte mithilfe von Vertraulichkeitsbezeichnungen, um Verschlüsselung anzuwenden.](./encryption-sensitivity-labels.md)

3. Verwenden Sie Double Key Encryption-Bezeichnungen. Schützen Sie Daten, indem Sie im Menüband Vertraulichkeit in Microsoft Office die Bezeichnung Verschlüsselter Doppelschlüssel auswählen.

Es gibt verschiedene Möglichkeiten, einige der Schritte zum Bereitstellen der Double Key Encryption auszuführen. Dieser Artikel enthält ausführliche Anweisungen, damit weniger erfahrene Administratoren den Dienst erfolgreich bereitstellen können. Wenn Sie damit vertraut sind, können Sie ihre eigenen Methoden verwenden.

## <a name="deploy-dke"></a>Bereitstellen von DKE

In diesem Artikel und dem Bereitstellungsvideo wird Azure als Bereitstellungsziel für den DKE-Dienst verwendet. Wenn Sie die Bereitstellung an einem anderen Speicherort durchführen, müssen Sie Ihre eigenen Werte angeben.

Sehen Sie sich das Video zur Bereitstellung der [Doppelschlüsselverschlüsselung](https://youtu.be/vDWfHN_kygg) an, um eine schrittweise Übersicht über die Konzepte in diesem Artikel zu sehen. Der Abschluss des Videos dauert ca. 18 Minuten.

Sie führen die folgenden allgemeinen Schritte aus, um die Doppelschlüsselverschlüsselung für Ihre Organisation einzurichten.

1. [Installieren der erforderlichen Software für den DKE-Dienst](#install-software-prerequisites-for-the-dke-service)
1. [Klonen Des Double Key Encryption GitHub Repositorys](#clone-the-dke-github-repository)
1. [Ändern von Anwendungseinstellungen](#modify-application-settings)
1. [Generieren von Testschlüsseln](#generate-test-keys)
1. [Erstellen des Projekts](#build-the-project)
1. [Bereitstellen des DKE-Diensts und Veröffentlichen des Schlüsselspeichers](#deploy-the-dke-service-and-publish-the-key-store)
1. [Überprüfen Ihrer Bereitstellung](#validate-your-deployment)
1. [Registrieren Ihres Schlüsselspeichers](#register-your-key-store)
1. [Erstellen von Vertraulichkeitsbezeichnungen mit dke](#create-sensitivity-labels-using-dke)
1. [Aktivieren von DKE in Ihrem Client](#enable-dke-in-your-client)
1. [Migrieren geschützter Dateien von HYOK-Bezeichnungen zu DKE-Bezeichnungen](#migrate-protected-files-from-hyok-labels-to-dke-labels)

Wenn Sie fertig sind, können Sie Dokumente und Dateien mithilfe von DKE verschlüsseln. Weitere Informationen finden Sie unter [Anwenden von Vertraulichkeitsbezeichnungen auf Ihre Dateien und E-Mails in Office.](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

### <a name="install-software-prerequisites-for-the-dke-service"></a>Installieren der erforderlichen Software für den DKE-Dienst

Installieren Sie diese erforderlichen Komponenten auf dem Computer, auf dem Sie den DKE-Dienst installieren möchten.

**.NET Core 3.1 SDK**. Laden Sie das SDK von [.NET Core 3.1 herunter,](https://dotnet.microsoft.com/download/dotnet-core/3.1)und installieren Sie es.

**Visual Studio Code**. Laden Sie Visual Studio Code von [https://code.visualstudio.com/](https://code.visualstudio.com) herunter. Führen Sie nach der Installation Visual Studio Code aus, und wählen Sie Erweiterungen **anzeigen** \> **aus.** Installieren Sie diese Erweiterungen.

- C# für Visual Studio Code

- NuGet Paket-Manager

**Git-Ressourcen**. Laden Sie eine der folgenden Komponenten herunter, und installieren Sie sie.

- [Git](https://git-scm.com/downloads)

- [GitHub Desktop](https://desktop.github.com/)

- [GitHub Enterprise](https://github.com/enterprise)

**OpenSSL** Sie müssen [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installiert haben, um Nach der Bereitstellung von DKE Testschlüssel zu [generieren.](#generate-test-keys) Stellen Sie sicher, dass Sie sie korrekt aus dem Pfad der Umgebungsvariablen aufrufen. Ausführliche Informationen finden Sie beispielsweise unter "Hinzufügen des Installationsverzeichnisses zu [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) PATH".

### <a name="clone-the-dke-github-repository"></a>Klonen des DKE-GitHub-Repositorys

Microsoft stellt die DKE-Quelldateien in einem GitHub Repository bereit. Sie klonen das Repository, um das Projekt lokal für die Verwendung in Ihrer Organisation zu erstellen. Das DKE-GitHub-Repository befindet sich unter [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

Die folgenden Anweisungen sind für unerfahrene Git- oder Visual Studio Code-Benutzer vorgesehen:

1. Wechseln Sie in Ihrem Browser zu: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .

2. Wählen Sie rechts neben dem Bildschirm **Code** aus. Ihre Version der Benutzeroberfläche zeigt möglicherweise eine **Schaltfläche zum Klonen oder Herunterladen** an. Wählen Sie dann in der angezeigten Dropdownliste das Kopiersymbol aus, um die URL in Die Zwischenablage zu kopieren.

    Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Klonen des Double Key Encryption-Dienst-Repositorys aus GitHub](../media/dke-clone.png)

3. Wählen Sie in Visual Studio Code  \> **Befehlspalette** anzeigen und dann **Git: Klonen** aus. Um zur Option in der Liste zu springen, beginnen Sie mit `git: clone` der Eingabe, um die Einträge zu filtern, und wählen Sie sie dann aus der Dropdownliste aus. Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Visual Studio Code GIT:Clone-Option](../media/dke-vscode-clone.png)

4. Fügen Sie in das Textfeld die URL ein, die Sie von Git kopiert haben, und wählen Sie **"Klonen" aus GitHub aus.**

5. Navigieren Sie im daraufhin angezeigten Dialogfeld **"Ordner auswählen"** zu einem Speicherort, an dem das Repository gespeichert werden soll, und wählen Sie diesen aus. Wählen Sie an der Eingabeaufforderung **"Öffnen"** aus.

    Das Repository wird in Visual Studio Code geöffnet und zeigt die aktuelle Git-Verzweigung unten links an. Die Verzweigung sollte z. B. **die Hauptverzweigung** sein. Beispiel:

   ![Screenshot des DKE-Repositorys in Visual Studio Code anzeigen des Hauptzweigs](../media/dke-vscode-main-branch.jpg)

6. Wenn Sie nicht in der Hauptverzweigung sind, müssen Sie sie auswählen. Wählen Sie in Visual Studio Code die Verzweigung aus, und wählen Sie **"Haupt"** aus der Liste der angezeigten Verzweigungen aus.

   > [!IMPORTANT]
   > Durch Auswählen der Hauptverzweigung wird sichergestellt, dass Sie über die richtigen Dateien zum Erstellen des Projekts verfügen. Wenn Sie nicht die richtige Verzweigung auswählen, schlägt ihre Bereitstellung fehl.

Ihr DKE-Quell-Repository ist jetzt lokal eingerichtet. Ändern Sie als Nächstes [die Anwendungseinstellungen](#modify-application-settings) für Ihre Organisation.

### <a name="modify-application-settings"></a>Ändern von Anwendungseinstellungen

Um den DKE-Dienst bereitzustellen, müssen Sie die folgenden Arten von Anwendungseinstellungen ändern:

- [Schlüsselzugriffseinstellungen](#key-access-settings)
- [Mandanten- und Schlüsseleinstellungen](#tenant-and-key-settings)

Sie ändern anwendungseinstellungen in der appsettings.json-Datei. Diese Datei befindet sich im DoubleKeyEncryptionService-Repository, das Sie lokal unter DoubleKeyEncryptionService\src\customer-key-store geklont haben. In Visual Studio Code können Sie beispielsweise zu der Datei navigieren, wie in der folgenden Abbildung dargestellt.

![Suchen der datei "appsettings.json" für DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a>Schlüsselzugriffseinstellungen

Wählen Sie aus, ob E-Mail- oder Rollenautorisierung verwendet werden soll. DKE unterstützt jeweils nur eine dieser Authentifizierungsmethoden.

- **E-Mail-Autorisierung**. Ermöglicht Ihrer Organisation, den Zugriff auf Schlüssel nur basierend auf E-Mail-Adressen zu autorisieren.

- **Rollenautorisierung**. Ermöglicht Ihrer Organisation, den Zugriff auf Schlüssel basierend auf Active Directory-Gruppen zu autorisieren, und erfordert, dass der Webdienst LDAP abfragen kann.

##### <a name="to-set-key-access-settings-for-dke-using-email-authorization"></a>So legen Sie schlüsselbasierte Zugriffseinstellungen für DKE mithilfe der E-Mail-Autorisierung fest

1. Öffnen **Sie** dieappsettings.json-Datei, und suchen Sie die `AuthorizedEmailAddress` Einstellung.

2. Fügen Sie die E-Mail-Adresse oder -Adressen hinzu, die Sie autorisieren möchten. Trennen Sie mehrere E-Mail-Adressen durch doppelte Anführungszeichen und Kommas. Beispiel:

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. Suchen Sie die `LDAPPath` Einstellung, und entfernen Sie den Text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` zwischen den doppelten Anführungszeichen. Lassen Sie die doppelten Anführungszeichen erhalten. Wenn Sie fertig sind, sollte die Einstellung wie folgt aussehen.

   ```json
   "LDAPPath": ""
   ```

4. Suchen Sie die `AuthorizedRoles` Einstellung, und löschen Sie die gesamte Zeile.

Diese Abbildung zeigt die **appsettings.js-On-Datei,** die für die E-Mail-Autorisierung richtig formatiert ist.

   ![Die appsettings.jsin der Datei mit der E-Mail-Autorisierungsmethode](../media/dke-email-accesssetting.png)

##### <a name="to-set-key-access-settings-for-dke-using-role-authorization"></a>So legen Sie schlüsselbasierte Zugriffseinstellungen für DKE mithilfe der Rollenautorisierung fest

1. Öffnen **Sie** dieappsettings.json-Datei, und suchen Sie die `AuthorizedRoles` Einstellung.

2. Fügen Sie die Active Directory-Gruppennamen hinzu, die Sie autorisieren möchten. Trennen Sie mehrere Gruppennamen durch doppelte Anführungszeichen und Kommas. Beispiel:

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. Suchen Sie die `LDAPPath` Einstellung, und fügen Sie die Active Directory-Domäne hinzu. Beispiel:

   ```json
   "LDAPPath": "contoso.com"
   ```

4. Suchen Sie die `AuthorizedEmailAddress` Einstellung, und löschen Sie die gesamte Zeile.

Diese Abbildung zeigt die **appsettings.js-On-Datei,** die für die Rollenautorisierung richtig formatiert ist.

   ![appsettings.jszur Datei mit Rollenautorisierungsmethode](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a>Mandanten- und Schlüsseleinstellungen

DkE-Mandanten- und Schlüsseleinstellungen befinden sich in der **appsettings.json-Datei.**

##### <a name="to-configure-tenant-and-key-settings-for-dke"></a>So konfigurieren Sie Mandanten- und Schlüsseleinstellungen für DKE

1. Öffnen Sie die **appsettings.json-Datei.**

2. Suchen Sie die `ValidIssuers` Einstellung, und ersetzen `<tenantid>` Sie sie durch Ihre Mandanten-ID. Sie können Ihre Mandanten-ID suchen, indem Sie zum Azure-Portal wechseln und die [Mandanteneigenschaften](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)anzeigen. Beispiel:

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

> [!NOTE]
> Wenn Sie den externen B2B-Zugriff auf Ihren Schlüsselspeicher aktivieren möchten, müssen Sie diese externen Mandanten auch als Teil der Liste der gültigen Aussteller einschließen.

Suchen Sie die `JwtAudience` . Ersetzen Sie `<yourhostname>` ihn durch den Hostnamen des Computers, auf dem der DKE-Dienst ausgeführt wird. Beispiel:

  > [!IMPORTANT]
  > Der Wert für `JwtAudience` muss *genau* mit dem Namen Ihres Hosts übereinstimmen. Sie können **localhost:5001** beim Debuggen verwenden. Wenn Sie das Debuggen abgeschlossen haben, stellen Sie jedoch sicher, dass Sie diesen Wert auf den Hostnamen des Servers aktualisieren.

- `TestKeys:Name`. Geben Sie einen Namen für Ihren Schlüssel ein. Beispiel: `TestKey1`
- `TestKeys:Id`. Erstellen Sie eine GUID, und geben Sie sie als `TestKeys:ID` Wert ein. Beispiel: `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`. Sie können eine Website wie [den Online-GUID-Generator](https://guidgenerator.com/) verwenden, um nach dem Zufallsprinzip eine GUID zu generieren.

Diese Abbildung zeigt das richtige Format für Mandanten- und Schlüsseleinstellungen in **appsettings.json**. `LDAPPath` ist für die Rollenautorisierung konfiguriert.

![Zeigt die richtigen Mandanten- und Schlüsseleinstellungen für DKE in der appsettings.json-Datei an.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a>Generieren von Testschlüsseln

Nachdem Sie die Anwendungseinstellungen definiert haben, können Sie öffentliche und private Testschlüssel generieren.

So generieren Sie Schlüssel:

1. Führen Sie im Windows Startmenü die OpenSSL-Eingabeaufforderung aus.

2. Wechseln Sie zu dem Ordner, in dem Sie die Testschlüssel speichern möchten. Die Dateien, die Sie durch Ausführen der Schritte in dieser Aufgabe erstellen, werden im selben Ordner gespeichert.

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

6. Öffnen Sie in einem Text-Editor **pubkeyonly.pem**. Kopieren Sie den gesamten Inhalt der Datei **"pubkeyonly.pem"** mit Ausnahme der ersten und letzten Zeilen in den `PublicPem` Abschnitt der **on-Dateiappsettings.js.**

7. Öffnen Sie in einem Text-Editor **privkeynopass.pem**. Kopieren Sie den gesamten Inhalt der Datei **"privkeynopass.pem"** mit Ausnahme der ersten und letzten Zeilen in den `PrivatePem` Abschnitt der **on-Dateiappsettings.js.**

8. Entfernen Sie alle Leerzeichen und Newlines in den Abschnitten und den `PublicPem` `PrivatePem` Abschnitten.

    > [!IMPORTANT]
    > Wenn Sie diesen Inhalt kopieren, löschen Sie keine der PEM-Daten.

9. Navigieren Sie in Visual Studio Code zur Datei **"Startup.cs".** Diese Datei befindet sich im DoubleKeyEncryptionService-Repository, das Sie lokal unter DoubleKeyEncryptionService\src\customer-key-store\ geklont haben.

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

    Die Endergebnisse sollten etwa wie folgt aussehen.

    ![Datei "startup.cs" für die öffentliche Vorschau](../media/dke-startupcs-usetestkeys.png)

Jetzt können Sie [Ihr DKE-Projekt erstellen.](#build-the-project)

### <a name="build-the-project"></a>Erstellen des Projekts

Verwenden Sie die folgenden Anweisungen, um das DKE-Projekt lokal zu erstellen:

1. Wählen Sie in Visual Studio Code im DKE-Dienst-Repository die  \> **Befehlspalette** anzeigen aus, und geben Sie dann an der Eingabeaufforderung build ein. 

2. Wählen Sie in der Liste **Tasks: Ausführen** der Buildaufgabe aus.

   Wenn keine Buildaufgaben gefunden wurden, wählen Sie **"Buildtask konfigurieren"** aus, und erstellen Sie eine für .NET Core wie folgt.

   ![Konfigurieren fehlender Buildaufgabe für .NET](../media/dke-configurebuildtask.png)

   1. Wählen Sie **aus der Vorlage tasks.jserstellen aus.**

      ![Erstellen tasks.json-Datei aus einer Vorlage für DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. Wählen Sie in der Liste der Vorlagentypen **.NET Core** aus.

      ![Auswählen der richtigen Vorlage für DKE](../media/dke-tasksjsontemplate.png)

   3. Suchen Sie im Buildabschnitt den Pfad zur Datei **"customerkeystore.csproj".** Wenn sie nicht vorhanden ist, fügen Sie die folgende Zeile hinzu:

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. Führen Sie den Build erneut aus.

3. Stellen Sie sicher, dass im Ausgabefenster keine roten Fehler vorhanden sind.

   Wenn rote Fehler auftreten, überprüfen Sie die Konsolenausgabe. Stellen Sie sicher, dass Sie alle vorherigen Schritte ordnungsgemäß ausgeführt haben und die richtigen Buildversionen vorhanden sind.

4. Wählen  Sie \> **"Debuggen starten ausführen"** aus, um den Prozess zu debuggen. Wenn Sie aufgefordert werden, eine Umgebung auszuwählen, wählen Sie **.NET Core** aus.

   Der .NET Core-Debugger wird in der Regel mit `https://localhost:5001` gestartet. Um den Testschlüssel anzuzeigen, wechseln Sie zu `https://localhost:5001` und fügen Sie einen Schrägstrich (/) und den Namen des Schlüssels an. Beispiel:

   ```https
   https://localhost:5001/TestKey1
   ```

   Der Schlüssel sollte im JSON-Format angezeigt werden.

Das Setup ist jetzt abgeschlossen. Stellen Sie vor der Veröffentlichung des Keystores in appsettings.json für die JwtAudience-Einstellung sicher, dass der Wert für den Hostnamen exakt dem Hostnamen des App-Diensts entspricht. Möglicherweise haben Sie es in "localhost" geändert, um Probleme mit dem Build zu beheben.

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a>Bereitstellen des DKE-Diensts und Veröffentlichen des Schlüsselspeichers

Stellen Sie den Dienst für Produktionsbereitstellungen entweder in einer Drittanbietercloud bereit oder [veröffentlichen Sie diesen auf einem lokalen System.](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)

Möglicherweise bevorzugen Sie andere Methoden zum Bereitstellen ihrer Schlüssel. Wählen Sie die Methode aus, die für Ihre Organisation am besten geeignet ist.

Für Pilotbereitstellungen können Sie die Bereitstellung in Azure durchführen und sofort loslegen.

#### <a name="to-create-an-azure-web-app-instance-to-host-your-dke-deployment"></a>So erstellen Sie eine Azure Web App-Instanz zum Hosten Ihrer DKE-Bereitstellung

Um den Schlüsselspeicher zu veröffentlichen, erstellen Sie eine Azure App Service-Instanz zum Hosten Ihrer DKE-Bereitstellung. Als Nächstes veröffentlichen Sie Ihre generierten Schlüssel in Azure.

1. Melden Sie sich in Ihrem Browser beim [Microsoft Azure-Portal](https://ms.portal.azure.com)an, und wechseln Sie zu **"App Services**  >  **Hinzufügen".**

2. Wählen Sie Ihr Abonnement und Ihre Ressourcengruppe aus, und definieren Sie Ihre Instanzdetails.

   - Geben Sie den Hostnamen des Computers ein, auf dem Sie den DKE-Dienst installieren möchten. Stellen Sie sicher, dass es sich um denselben Namen handelt, der für die JwtAudience-Einstellung in der [**on-Dateiappsettings.js**](#tenant-and-key-settings) definiert ist. Der Wert, den Sie für den Namen angeben, ist auch der WebAppInstanceName.

   - Wählen Sie für **"Veröffentlichen",** **"Code"** und für den **Laufzeitstapel** **.NET Core 3.1** aus.

   Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Hinzufügen ihres App-Diensts](../media/dke-azure-add-app-service.png)

3. Wählen Sie unten auf der Seite **"Überprüfen + erstellen"** und dann **"Hinzufügen"** aus.

4. Führen Sie einen der folgenden Schritte aus, um die generierten Schlüssel zu veröffentlichen:

   - [Veröffentlichen über ZipDeployUI](#publish-via-zipdeployui)
   - [Veröffentlichen per FTP](#publish-via-ftp)
   - [Veröffentlichen über Visual Studio 2019 oder höher](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a>Veröffentlichen über ZipDeployUI

1. Wechseln Sie zu `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.

   Beispiel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

2. Wechseln Sie in der Codebasis für den Schlüsselspeicher zum Ordner **"customer-key-store\src\customer-key-store",** und stellen Sie sicher, dass dieser Ordner die Datei **"customerkeystore.csproj"** enthält.

3. Run: **dotnet publish**

   Im Ausgabefenster wird das Verzeichnis angezeigt, in dem die Veröffentlichung bereitgestellt wurde.

   Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

4. Senden Sie alle Dateien im Veröffentlichungsverzeichnis an eine .zip Datei. Stellen Sie beim Erstellen der .zip-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der .zip-Datei befinden.

5. Ziehen Sie die .zip Datei, die Sie erstellen, per Drag & Drop auf die ZipDeployUI-Website, die Sie oben geöffnet haben. Beispiel: https://dkeservice.scm.azurewebsites.net/ZipDeployUI

DKE wird bereitgestellt, und Sie können zu den testschlüsseln navigieren, die Sie erstellt haben. Fahren Sie mit [der folgenden Überprüfung der Bereitstellung](#validate-your-deployment) fort.

#### <a name="publish-via-ftp"></a>Veröffentlichen per FTP

1. Verbinden zum App-Dienst, den Sie [oben](#deploy-the-dke-service-and-publish-the-key-store)erstellt haben.

   Wechseln Sie in Ihrem Browser zu: **Azure Portal**  >  **App Service** Deployment  >  **Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**.

2. Kopieren Sie die angezeigten Verbindungszeichenfolgen in eine lokale Datei. Sie verwenden diese Zeichenfolgen, um eine Verbindung mit dem Web App Service herzustellen und Dateien per FTP hochzuladen.

   Beispiel:

   ![Kopieren von Verbindungszeichenfolgen aus dem FTP-Dashboard](../media/dke-ftp-dashboard.png)

3. Wechseln Sie in der Codebasis für den Schlüsselspeicher zum **Verzeichnis "customer-key-store\src\customer-key-store".**

4. Stellen Sie sicher, dass dieses Verzeichnis die Datei **"customerkeystore.csproj"** enthält.

5. Run: **dotnet publish**

   Die Ausgabe enthält das Verzeichnis, in dem die Veröffentlichung bereitgestellt wurde.

   Beispiel: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`

6. Senden Sie alle Dateien im Veröffentlichungsverzeichnis an eine ZIP-Datei. Stellen Sie beim Erstellen der .zip-Datei sicher, dass sich alle Dateien im Verzeichnis auf der Stammebene der .zip-Datei befinden.

7. Verwenden Sie von Ihrem FTP-Client die Verbindungsinformationen, die Sie kopiert haben, um eine Verbindung mit Ihrem App-Dienst herzustellen. Hochladen sie die .zip Datei, die Sie im vorherigen Schritt erstellt haben, in das Stammverzeichnis Ihrer Web App ein.

DKE wird bereitgestellt, und Sie können zu den Testschlüsseln navigieren, die Sie erstellt haben. Als Nächstes [überprüfen Sie Ihre Bereitstellung.](#validate-your-deployment)

### <a name="validate-your-deployment"></a>Überprüfen Ihrer Bereitstellung

Überprüfen Sie nach der Bereitstellung von DKE mithilfe einer der oben beschriebenen Methoden die Bereitstellungs- und Schlüsselspeichereinstellungen.

Ausführen:

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

Beispiel:

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

Stellen Sie sicher, dass in der Ausgabe keine Fehler angezeigt werden. Wenn Sie bereit sind, [registrieren Sie Ihren Schlüsselspeicher.](#register-your-key-store)

Beim Schlüsselnamen wird die Groß-/Kleinschreibung beachtet. Geben Sie den Schlüsselnamen so ein, wie er in der datei appsettings.jsangezeigt wird.

## <a name="register-your-key-store"></a>Registrieren Ihres Schlüsselspeichers

Mit den folgenden Schritten können Sie Ihren DKE-Dienst registrieren. Die Registrierung Ihres DKE-Diensts ist der letzte Schritt bei der Bereitstellung von DKE, bevor Sie mit dem Erstellen von Bezeichnungen beginnen können.

So registrieren Sie den DKE-Dienst:

1. Öffnen Sie in Ihrem Browser das [Microsoft Azure-Portal,](https://ms.portal.azure.com/)und wechseln Sie zu **"Alle Dienste** \> **Identitäts-App-Registrierungen".** \> 

2. Wählen Sie **"Neue Registrierung"** aus, und geben Sie einen aussagekräftigen Namen ein.

3. Wählen Sie aus den angezeigten Optionen einen Kontotyp aus.

   Wenn Sie Microsoft Azure mit einer nicht benutzerdefinierten Domäne verwenden, z. **B. onmicrosoft.com,** wählen Sie **nur Konten in diesem Organisationsverzeichnis aus (nur Microsoft – einzelner Mandant).**

   Beispiel:

   > [!div class="mx-imgBorder"]
   > ![Neue App-Registrierung](../media/dke-app-registration.png)

4. Wählen Sie unten auf der Seite **"Registrieren"** aus, um die neue App-Registrierung zu erstellen.

5. Wählen Sie in Ihrer neuen App-Registrierung im linken Bereich unter **Verwalten** die Option **"Authentifizierung"** aus.

6. Wählen Sie **"Plattform hinzufügen"** aus.

7. Wählen Sie im Popup **"Plattformen konfigurieren"** die Option **"Web"** aus.

8. Geben Sie unter **"Umleitungs-URIs"** den URI des Verschlüsselungsdiensts mit Doppelschlüssel ein. Geben Sie die APP-Dienst-URL ein, einschließlich Hostname und Domäne.

   Beispiel: https://mydkeservicetest.com

   - Die eingegebene URL muss mit dem Hostnamen übereinstimmen, unter dem Ihr DKE-Dienst bereitgestellt wird.
   - Wenn Sie lokal mit Visual Studio testen, verwenden Sie **https://localhost:5001** .
   - In allen Fällen muss das Schema **https** sein.

   Stellen Sie sicher, dass der Hostname exakt ihrem App Service-Hostnamen entspricht. Möglicherweise haben Sie es zur `localhost` Problembehandlung für den Build geändert. In **appsettings.json** ist dieser Wert der Hostname, den Sie für `JwtAudience` .

9. Aktivieren Sie unter **"Implizite Gewährung"** das **Kontrollkästchen "ID-Token".**

10. Wählen Sie **Speichern** aus, um Ihre Änderungen zu speichern.

11. Wählen Sie im linken Bereich **"API verfügbar machen"** und dann neben dem Anwendungs-ID-URI die Option **"Festlegen"** aus.

12. Wählen Sie auf der Seite **"API verfügbar machen"** in den **von diesem API-Bereich definierten Bereichen** einen Bereich **hinzufügen** aus. Im neuen Bereich:

    1. Definieren Sie den Bereichsnamen als **user_impersonation.**

    2. Wählen Sie die Administratoren und Benutzer aus, die zustimmen können.

    3. Definieren Sie alle verbleibenden erforderlichen Werte.

    4. Klicken Sie auf **Bereich hinzufügen**.

    5. Wählen Sie oben **"Speichern"** aus, um Ihre Änderungen zu speichern.

13. Wählen Sie auf der Seite **"API verfügbar machen"** im Bereich **"Autorisierte Clientanwendungen"** die Option **"Clientanwendung hinzufügen"** aus.

    In der neuen Clientanwendung:

    1. Definieren Sie die Client-ID als `d3590ed6-52b3-4102-aeff-aad2292ab01c` . Dieser Wert ist die Microsoft Office Client-ID und ermöglicht es Office, ein Zugriffstoken für Ihren Schlüsselspeicher abzurufen.

    2. Wählen Sie unter **"Autorisierte Bereiche"** den **user_impersonation** Bereich aus.

    3. Wählen Sie **Anwendung hinzufügen** aus.

    4. Wählen Sie oben **"Speichern"** aus, um Ihre Änderungen zu speichern.

    5. Wiederholen Sie diese Schritte, aber definieren Sie dieses Mal die Client-ID als `c00e9d32-3c8d-4a7d-832b-029040e7db99` . Dieser Wert ist die Azure Information Protection-Client-ID für einheitliche Bezeichnungen.

Ihr DKE-Dienst ist jetzt registriert. Fahren Sie fort, indem [Sie Bezeichnungen mit DKE erstellen.](#create-sensitivity-labels-using-dke)

## <a name="create-sensitivity-labels-using-dke"></a>Erstellen von Vertraulichkeitsbezeichnungen mit dke

Erstellen Sie im Microsoft 365 Compliance Center eine neue Vertraulichkeitsbezeichnung, und wenden Sie die Verschlüsselung wie sonst an. Wählen Sie **"Doppelschlüsselverschlüsselung verwenden"** aus, und geben Sie die Endpunkt-URL für Ihren Schlüssel ein.

Beispiel:

> [!div class="mx-imgBorder"]
> ![Wählen Sie "Double Key Encryption" in der Microsoft 365 Compliance Center](../media/dke-use-dke.png)

Alle DKE-Bezeichnungen, die Sie hinzufügen, werden für Benutzer in den neuesten Versionen von Microsoft 365 Apps for Enterprise angezeigt.

> [!NOTE]
> Es kann bis zu 24 Stunden dauern, bis die Clients mit den neuen Bezeichnungen aktualisiert wurden.

### <a name="enable-dke-in-your-client"></a>Aktivieren von DKE in Ihrem Client

Wenn Sie ein Office Insider sind, ist DKE für Sie aktiviert. Aktivieren Sie andernfalls DKE für Ihren Client, indem Sie die folgenden Registrierungsschlüssel hinzufügen:

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a>Migrieren geschützter Dateien von HYOK-Bezeichnungen zu DKE-Bezeichnungen

Wenn Sie möchten, können Sie nach Abschluss der Einrichtung von DKE inhalte, die Sie geschützt haben, mithilfe von HYOK-Bezeichnungen zu DKE-Bezeichnungen migrieren. Zum Migrieren verwenden Sie den AIP-Scanner. Informationen zu den ersten Schritten mit dem Scanner finden Sie unter ["Was ist der Azure Information Protection-Scanner für einheitliche Bezeichnungen?".](/azure/information-protection/deploy-aip-scanner)

Wenn Sie Keine Inhalte migrieren, bleiben Ihre HYOK-geschützten Inhalte davon unberührt.
