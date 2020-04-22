<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Erforderlich: Sicherheits- und Information Protection-Stufen sind für Ihre Organisation definiert

Sie haben die Planung und Definition der Sicherheitsstufen abgeschlossen, die Ihre Organisation benötigt. Diese Stufen definieren ein Mindestmaß an Sicherheit sowie zusätzliche Sicherheitsstufen für zunehmend vertrauliche Informationen und die erforderliche Datensicherheit.

Sie verwenden mindestens drei Sicherheitsstufen:

- Baseline
- Vertraulich
- Streng geregelt

Gegebenenfalls hilft Ihnen [Schritt 1](../infoprotect-define-sec-infoprotect-levels.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step3"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>Erforderlich: Erhöhte Sicherheit für Microsoft 365 ist konfiguriert

Sie haben die folgenden Einstellungen für [höhere Sicherheit von Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) konfiguriert:

- Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Security Center
- Zusätzliche mandantenweite Exchange Online-Einstellungen
- Mandantenweite Freigaberichtlinien im SharePoint Admin Center
- Azure Active Directory-Einstellungen (Azure AD)

Sie haben zudem [Office 365 Advanced Threat Protection (ATP) für SharePoint, OneDrive und Microsoft Teams aktiviert](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Gegebenenfalls hilft Ihnen [Schritt 3](../infoprotect-configure-increased-security-office-365.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step2"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>Optional: Klassifikation ist in der gesamten Umgebung konfiguriert

Sie haben mit Ihrer Rechts- und Complianceabteilung eine entsprechende Klassifikation und ein Bezeichnungsschema für Data Governance- und Sicherheitsrichtlinien in Ihrer Organisation erarbeitet. 

Diese Richtlinien entsprechen der Konfiguration und Bereitstellung von:

- Typen vertraulicher Daten
- Aufbewahrungsbezeichnungen
- Vertraulichkeitsbezeichnungen
- Azure Information Protection-Bezeichnungen

Gegebenenfalls hilft Ihnen [Schritt 2](../infoprotect-configure-classification.md), diese Anforderung zu erfüllen. 


<a name="crit-infoprotect-step4"></a>
### <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Optional: Windows Information Protection wird in Ihrer Umgebung eingesetzt.

Für Ihre angemeldeten Windows 10 Enterprise-Geräte wird eine Intune-Richtlinie bereitgestellt und angewendet, die definiert:

- Welche Apps geschützt werden sollen.
- Der Schutzgrad.
- Wo der Schutz gilt.

Gegebenenfalls hilft Ihnen [Schritt 4](../infoprotect-deploy-windows-information-protection.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-data-loss-prevention-dlp-is-deployed"></a>Optional: Verhinderung von Datenverlust (DLP) wird bereitgestellt

Sie haben die DLP-Richtlinien analysiert, getestet und dann eingeführt, mit Standorten und Regeln, Bedingungen und Maßnahmen, die Ihre Organisation benötigt, um Kunden und andere Arten von privaten Daten zu schützen und branchenspezifische und regionale Vorschriften und Anforderungen einzuhalten.

Ihre Datenkompatibilität- und Ihr Sicherheits-Personal nutzt das Security & Compliance Dashboard zur Überwachung von DLP-Vorfällen.

Gegebenenfalls hilft Ihnen [Schritt 5](../infoprotect-data-loss-prevention.md), diese Anforderung zu erfüllen. 

<a name="crit-infoprotect-step6"></a>
### <a name="optional-email-encryption-is-configured"></a>Optional: E-Mail-Verschlüsselung ist konfiguriert

Sie haben die folgende E-Mail-Verschlüsselung nach Bedarf für Ihre Organisation konfiguriert:

|||
|:-------|:-----|
| **Verschlüsselungsmethode** | **Für gesendete E-Mails** |
| [Office 365-Nachrichtenverschlüsselung (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | Außerhalb Ihres Unternehmens mit Verschlüsselung |
| [Verwaltung von Informationsrechten (Information Rights Management, IRM)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | Verschlüsselung und Berechtigungen |
| [S/MIME (Secure/Multipurpose Internet Mail Extensions)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | Verschlüsselung und digitale Signaturen unter Verwendung der Kryptografie mit öffentlichen Schlüsseln |
|||

Gegebenenfalls hilft Ihnen [Schritt 6](../infoprotect-email-encryption.md), diese Anforderung zu erfüllen.

<a name="crit-infoprotect-step7"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>Optional: Konfigurieren von Privileged Access Management in Office 365

Sie haben die Informationen im Thema [Konfigurieren von Privileged Access Management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) verwendet, um privilegierten Zugriff zu aktivieren und eine oder mehrere Richtlinien für privilegierten Zugriff in Ihrer Organisation zu erstellen. Sie haben diese Richtlinien konfiguriert, und Just-in-Time-Zugriff ist für Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen aktiviert.

Gegebenenfalls hilft Ihnen [Schritt 7](../infoprotect-configure-privileged-access-management.md), diese Anforderung zu erfüllen. 
