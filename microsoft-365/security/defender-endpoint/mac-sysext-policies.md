---
title: Neue Konfigurationsprofile für macOS Catalina und neuere Versionen von macOS
description: In diesem Thema werden die Änderungen beschrieben, die vorgenommen werden müssen, um von den Systemerweiterungen zu profitieren, die als Ersatz für Kernelerweiterungen unter macOS Catalina und neueren Versionen von macOS verwendet werden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, kernel, system, extensions, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: 28a332cec68521741bdda62aeecd25440552344a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932739"
---
# <a name="new-configuration-profiles-for-macos-catalina-and-newer-versions-of-macos"></a>Neue Konfigurationsprofile für macOS Catalina und neuere Versionen von macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

In Übereinstimmung mit der macOS-Weiterentwicklung bereiten wir ein Microsoft Defender for Endpoint auf macOS-Update vor, das Systemerweiterungen anstelle von Kernelerweiterungen nutzt. Dieses Update gilt nur für macOS Catalina (10.15.4) und neuere Versionen von macOS.

Wenn Sie Microsoft Defender for Endpoint auf macOS in einer verwalteten Umgebung (über JAMF, Intune oder eine andere MDM-Lösung) bereitgestellt haben, müssen Sie neue Konfigurationsprofile bereitstellen. Wenn diese Schritte nicht ausgeführt werden, erhalten Benutzer Genehmigungsaufforderungen zum Ausführen dieser neuen Komponenten.

## <a name="jamf"></a>JAMF

### <a name="system-extensions-policy"></a>Systemerweiterungsrichtlinie

Um die Systemerweiterungen zu genehmigen, erstellen Sie die folgende Nutzlast:

1. Wählen **Sie in > Konfigurationsprofile** Optionen > **Systemerweiterungen aus.**
2. Wählen **Sie in der** Dropdownliste **Systemerweiterungstypen** zulässige Systemerweiterungen aus.
3. Verwenden **Sie UBF8T346G9** für die Team-ID.
4. Fügen Sie der Liste zulässige Systemerweiterungen die folgenden **Bündelbezeichner** hinzu:

    - **com.microsoft.wdav.epsext**
    - **com.microsoft.wdav.netext**

    ![Screenshot genehmigter Systemerweiterungen](images/mac-approved-system-extensions.png)

### <a name="privacy-preferences-policy-control"></a>Richtliniensteuerelement für Datenschutzeinstellungen

Fügen Sie die folgende JAMF-Nutzlast hinzu, um der Microsoft Defender for Endpoint Endpoint Security Extension vollständigen Festplattenzugriff zu gewähren. Diese Richtlinie ist eine Voraussetzung für die Ausführung der Erweiterung auf Ihrem Gerät.

1. Wählen **Sie Optionen**  >  **Datenschutzeinstellungen Richtliniensteuerelement aus.**
2. Verwenden `com.microsoft.wdav.epsext` Sie als **Bezeichner** und `Bundle ID` als **Bundle-Typ**.
3. Festlegen der Codeanforderung auf `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
4. Legen **Sie App oder Dienst auf** **SystemPolicyAllFiles und** Zugriff auf Zulassen **.**

    ![Richtliniensteuerelement für Datenschutzeinstellungen](images/mac-system-extension-privacy.png)

### <a name="network-extension-policy"></a>Netzwerkerweiterungsrichtlinie

Im Rahmen der Funktionen für die Erkennung und Reaktion von Endpunkten prüft Microsoft Defender for Endpoint auf macOS den Socketdatenverkehr und meldet diese Informationen Microsoft Defender Security Center Portal. Mit der folgenden Richtlinie kann die Netzwerkerweiterung diese Funktionalität ausführen.

>[!NOTE]
>JAMF bietet keine integrierte Unterstützung für Inhaltsfilterrichtlinien, die eine Voraussetzung für die Aktivierung der Netzwerkerweiterungen sind, die Microsoft Defender for Endpoint auf macOS auf dem Gerät installiert. Darüber hinaus ändert JAMF manchmal den Inhalt der bereitgestellten Richtlinien.
>Daher bieten die folgenden Schritte eine Problemumgehung, bei der das Konfigurationsprofil signiert werden muss.

1. Speichern Sie den folgenden Inhalt auf Ihrem Gerät `com.microsoft.network-extension.mobileconfig` mithilfe eines Text-Editors:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1">
        <dict>
            <key>PayloadUUID</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadType</key>
            <string>Configuration</string>
            <key>PayloadOrganization</key>
            <string>Microsoft Corporation</string>
            <key>PayloadIdentifier</key>
            <string>DA2CC794-488B-4AFF-89F7-6686A7E7B8AB</string>
            <key>PayloadDisplayName</key>
            <string>Microsoft Defender ATP Network Extension</string>
            <key>PayloadDescription</key>
            <string/>
            <key>PayloadVersion</key>
            <integer>1</integer>
            <key>PayloadEnabled</key>
            <true/>
            <key>PayloadRemovalDisallowed</key>
            <true/>
            <key>PayloadScope</key>
            <string>System</string>
            <key>PayloadContent</key>
            <array>
                <dict>
                    <key>PayloadUUID</key>
                    <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                    <key>PayloadType</key>
                    <string>com.apple.webcontent-filter</string>
                    <key>PayloadOrganization</key>
                    <string>Microsoft Corporation</string>
                    <key>PayloadIdentifier</key>
                    <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                    <key>PayloadDisplayName</key>
                    <string>Approved Network Extension</string>
                    <key>PayloadDescription</key>
                    <string/>
                    <key>PayloadVersion</key>
                    <integer>1</integer>
                    <key>PayloadEnabled</key>
                    <true/>
                    <key>FilterType</key>
                    <string>Plugin</string>
                    <key>UserDefinedName</key>
                    <string>Microsoft Defender ATP Network Extension</string>
                    <key>PluginBundleID</key>
                    <string>com.microsoft.wdav</string>
                    <key>FilterSockets</key>
                    <true/>
                    <key>FilterDataProviderBundleIdentifier</key>
                    <string>com.microsoft.wdav.netext</string>
                    <key>FilterDataProviderDesignatedRequirement</key>
                    <string>identifier "com.microsoft.wdav.netext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                </dict>
            </array>
        </dict>
    </plist>
    ```

2. Stellen Sie sicher, dass die obige Datei ordnungsgemäß kopiert wurde, indem Sie `plutil` das Hilfsprogramm im Terminal ausführen:

    ```bash
    $ plutil -lint <PathToFile>/com.microsoft.network-extension.mobileconfig
    ```

    Wenn die Datei z. B. in Dokumenten gespeichert wurde:

    ```bash
    $ plutil -lint ~/Documents/com.microsoft.network-extension.mobileconfig
    ```
    
    Stellen Sie sicher, dass der Befehl ausgegeben `OK` wird.
        
    ```bash
    <PathToFile>/com.microsoft.network-extension.mobileconfig: OK
    ```
    
3. Befolgen Sie die Anweisungen [auf dieser Seite,](https://www.jamf.com/jamf-nation/articles/649/creating-a-signing-certificate-using-jamf-pro-s-built-in-certificate-authority) um ein Signaturzertifikat mit der integrierten Zertifizierungsstelle von JAMF zu erstellen.

4. Nachdem das Zertifikat erstellt und auf Ihrem Gerät installiert wurde, führen Sie den folgenden Befehl aus dem Terminal aus, um die Datei zu signieren:

    ```bash
    $ security cms -S -N "<CertificateName>" -i <PathToFile>/com.microsoft.network-extension.mobileconfig -o <PathToSignedFile>/com.microsoft.network-extension.signed.mobileconfig
    ```
    
    Wenn der Zertifikatname beispielsweise **SigningCertificate** ist und die signierte Datei in Dokumenten gespeichert wird:
    
    ```bash
    $ security cms -S -N "SigningCertificate" -i ~/Documents/com.microsoft.network-extension.mobileconfig -o ~/Documents/com.microsoft.network-extension.signed.mobileconfig
    ```
    
5. Navigieren Sie im JAMF-Portal zu **Konfigurationsprofile,** und klicken Sie **auf Hochladen** Schaltfläche. Wählen `com.microsoft.network-extension.signed.mobileconfig` Sie aus, wenn Sie zur Datei aufgefordert werden.

## <a name="intune"></a>Intune

### <a name="system-extensions-policy"></a>Systemerweiterungsrichtlinie

So genehmigen Sie die Systemerweiterungen:

1. Öffnen Sie in Intune **Die**  >  **Gerätekonfiguration verwalten.** Wählen **Sie Profil** erstellen von  >    >  **Profilen verwalten aus.**
2. Wählen Sie einen Namen für das Profil aus. Ändern **Sie Platform=macOS** in **Profile type=Extensions**. Wählen Sie **Erstellen** aus.
3. Geben Sie `Basics` auf der Registerkarte diesem neuen Profil einen Namen.
4. Fügen Sie `Configuration settings` auf der Registerkarte die folgenden Einträge im Abschnitt `Allowed system extensions` hinzu:

    Bundle-ID         | Team-ID
    --------------------------|----------------
    com.microsoft.wdav.epsext | UBF8T346G9
    com.microsoft.wdav.netext | UBF8T346G9

    ![Screenshot der Systemkonfigurationsprofile](images/mac-system-extension-intune2.png)

5. Weisen Sie `Assignments` auf der Registerkarte dieses Profil allen Benutzern & Allen Geräten **zu.**
6. Überprüfen und erstellen Sie dieses Konfigurationsprofil.

### <a name="create-and-deploy-the-custom-configuration-profile"></a>Erstellen und Bereitstellen des benutzerdefinierten Konfigurationsprofils

Das folgende Konfigurationsprofil aktiviert die Netzwerkerweiterung und gewährt Volldatenträgerzugriff auf die Endpoint Security-Systemerweiterung. 

Speichern Sie den folgenden Inhalt in einer Datei **namenssysext.xml:**

```xml
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1">
    <dict>
        <key>PayloadUUID</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadType</key>
        <string>Configuration</string>
        <key>PayloadOrganization</key>
        <string>Microsoft Corporation</string>
        <key>PayloadIdentifier</key>
        <string>7E53AC50-B88D-4132-99B6-29F7974EAA3C</string>
        <key>PayloadDisplayName</key>
        <string>Microsoft Defender ATP System Extensions</string>
        <key>PayloadDescription</key>
        <string/>
        <key>PayloadVersion</key>
        <integer>1</integer>
        <key>PayloadEnabled</key>
        <true/>
        <key>PayloadRemovalDisallowed</key>
        <true/>
        <key>PayloadScope</key>
        <string>System</string>
        <key>PayloadContent</key>
        <array>
            <dict>
                <key>PayloadUUID</key>
                <string>2BA070D9-2233-4827-AFC1-1F44C8C8E527</string>
                <key>PayloadType</key>
                <string>com.apple.webcontent-filter</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>CEBF7A71-D9A1-48BD-8CCF-BD9D18EC155A</string>
                <key>PayloadDisplayName</key>
                <string>Approved Network Extension</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>FilterType</key>
                <string>Plugin</string>
                <key>UserDefinedName</key>
                <string>Microsoft Defender ATP Network Extension</string>
                <key>PluginBundleID</key>
                <string>com.microsoft.wdav</string>
                <key>FilterSockets</key>
                <true/>
                <key>FilterDataProviderBundleIdentifier</key>
                <string>com.microsoft.wdav.netext</string>
                <key>FilterDataProviderDesignatedRequirement</key>
                <string>identifier &quot;com.microsoft.wdav.netext&quot; and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
            </dict>
            <dict>
                <key>PayloadUUID</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadType</key>
                <string>com.apple.TCC.configuration-profile-policy</string>
                <key>PayloadOrganization</key>
                <string>Microsoft Corporation</string>
                <key>PayloadIdentifier</key>
                <string>56105E89-C7C8-4A95-AEE6-E11B8BEA0366</string>
                <key>PayloadDisplayName</key>
                <string>Privacy Preferences Policy Control</string>
                <key>PayloadDescription</key>
                <string/>
                <key>PayloadVersion</key>
                <integer>1</integer>
                <key>PayloadEnabled</key>
                <true/>
                <key>Services</key>
                <dict>
                    <key>SystemPolicyAllFiles</key>
                    <array>
                        <dict>
                            <key>Identifier</key>
                            <string>com.microsoft.wdav.epsext</string>
                            <key>CodeRequirement</key>
                            <string>identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9</string>
                            <key>IdentifierType</key>
                            <string>bundleID</string>
                            <key>StaticCode</key>
                            <integer>0</integer>
                            <key>Allowed</key>
                            <integer>1</integer>
                        </dict>
                    </array>
                </dict>
            </dict>
        </array>
    </dict>
</plist>
```

Stellen Sie sicher, dass die obige Datei ordnungsgemäß kopiert wurde. Führen Sie im Terminal den folgenden Befehl aus, und stellen Sie sicher, dass er ausgegeben `OK` wird:

```bash
$ plutil -lint sysext.xml
sysext.xml: OK
```

So stellen Sie dieses benutzerdefinierte Konfigurationsprofil zur Bereitstellung ein:

1.  Öffnen Sie in Intune **Die**  >  **Gerätekonfiguration verwalten.** Wählen **Sie Profil**  >  **erstellen**  >  **aus.**
2. Wählen Sie einen Namen für das Profil aus. Ändern **von Platform=macOS** und **Profile type=Custom**. Wählen Sie **Konfigurieren** aus.
3.  Öffnen Sie das Konfigurationsprofil, und laden **Siesysext.xml.** Diese Datei wurde im vorherigen Schritt erstellt.
4.  Klicken Sie auf **OK**.

    ![Screenshot der Systemerweiterung in Intune](images/mac-system-extension-intune.png)

5. Weisen Sie `Assignments` auf der Registerkarte dieses Profil allen Benutzern & Allen Geräten **zu.**
6. Überprüfen und erstellen Sie dieses Konfigurationsprofil.
