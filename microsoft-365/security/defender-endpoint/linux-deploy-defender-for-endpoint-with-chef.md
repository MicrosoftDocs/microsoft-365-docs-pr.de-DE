---
title: Bereitstellen von Defender for Endpoint unter Linux mit Chef
description: Erfahren Sie, wie Sie Defender for Endpoint unter Linux mit Chef bereitstellen
keywords: microsoft, defender, atp, linux, scans, antivirus, microsoft defender for endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 362222e4737b1a8dd6b8a0a284bf3bfb1903c288
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861446"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="516e4-104">Bereitstellen von Defender for Endpoint unter Linux mit Chef</span><span class="sxs-lookup"><span data-stu-id="516e4-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="516e4-105">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="516e4-105">Before you begin:</span></span>

- <span data-ttu-id="516e4-106">Installieren Sie entpacken, wenn es noch nicht installiert ist.</span><span class="sxs-lookup"><span data-stu-id="516e4-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="516e4-107">Die Chef-Komponenten sind bereits installiert, und es ist ein Chefrepository vorhanden (chef generate repo), um das Rezeptbuch zu speichern, das für die Bereitstellung in Defender for Endpoint auf von Chef verwalteten <reponame> Linux-Servern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="516e4-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="516e4-108">Sie können ein neues Rezeptbuch in Ihrem vorhandenen Repository erstellen, indem Sie den folgenden Befehl im Ordner "Rezeptbücher" ausführen, der sich im Chefrepository befindet:</span><span class="sxs-lookup"><span data-stu-id="516e4-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="516e4-109">Mit diesem Befehl wird eine neue Ordnerstruktur für das neue Rezeptbuch mdatp erstellt.</span><span class="sxs-lookup"><span data-stu-id="516e4-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="516e4-110">Sie können auch ein vorhandenes Rezeptbuch verwenden, wenn Sie bereits über ein Rezept verfügen, zu dem Sie die MDE-Bereitstellung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="516e4-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="516e4-111">Erstellen Sie nach dem Erstellen des Kochbuchs einen Ordner mit Dateien innerhalb des Gerade erstellten Kochbuchordners:</span><span class="sxs-lookup"><span data-stu-id="516e4-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="516e4-112">Übertragen Sie die Zip-Datei für das Linux Server-Onboarding, die aus dem Microsoft Defender Security Center-Portal heruntergeladen werden kann, in diesen neuen Dateiordner.</span><span class="sxs-lookup"><span data-stu-id="516e4-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="516e4-113">Navigieren Sie auf der Chef Workstation zum Ordner mdatp/recipes.</span><span class="sxs-lookup"><span data-stu-id="516e4-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="516e4-114">Dieser Ordner wird erstellt, wenn das Rezeptbuch generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="516e4-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="516e4-115">Verwenden Sie ihren bevorzugten Texteditor (z. B. vi oder nano), um die folgenden Anweisungen am Ende der Datei "default.rb" hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="516e4-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="516e4-116">include_recipe '::onboard_mdatp'</span><span class="sxs-lookup"><span data-stu-id="516e4-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="516e4-117">include_recipe '::install_mdatp'</span><span class="sxs-lookup"><span data-stu-id="516e4-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="516e4-118">Speichern und schließen Sie dann die Datei default.rb.</span><span class="sxs-lookup"><span data-stu-id="516e4-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="516e4-119">Erstellen Sie als Nächstes eine neue Rezeptdatei namens install_mdatp.rb im Ordner "Rezept", und fügen Sie der Datei diesen Text hinzu:</span><span class="sxs-lookup"><span data-stu-id="516e4-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

<span data-ttu-id="516e4-120">Sie müssen version number, distribution und repo name so ändern, dass sie der Version entsprechen, in der Sie bereitstellen, und dem Kanal, den Sie bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="516e4-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="516e4-121">Als Nächstes sollten Sie eine onboard_mdatp.rb-Datei im Ordner mdatp/recipies erstellen.</span><span class="sxs-lookup"><span data-stu-id="516e4-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="516e4-122">Fügen Sie der Datei den folgenden Text hinzu:</span><span class="sxs-lookup"><span data-stu-id="516e4-122">Add the following text to that file:</span></span>

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

<span data-ttu-id="516e4-123">Achten Sie darauf, den Pfadnamen auf den Speicherort der Onboardingdatei zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="516e4-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="516e4-124">Führen Sie einfach aus, um die Bereitstellung auf der Chef-Arbeitsstation zu ``sudo chef-client -z -o mdatp`` testen.</span><span class="sxs-lookup"><span data-stu-id="516e4-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="516e4-125">Nach der Bereitstellung sollten Sie das Erstellen und Bereitstellen einer Konfigurationsdatei auf den Servern basierend auf Den Einstellungen für Microsoft Defender ATP für Linux festlegen –  [Windows-Sicherheitseinstellungen | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span><span class="sxs-lookup"><span data-stu-id="516e4-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender ATP for Linux - Windows security | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span></span>  
<span data-ttu-id="516e4-126">Nachdem Sie die Konfigurationsdatei erstellt und getestet haben, können Sie sie in den Ordner cookbook/mdatp/files platzieren, in dem Sie auch das Onboardingpaket platziert haben.</span><span class="sxs-lookup"><span data-stu-id="516e4-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="516e4-127">Anschließend können Sie eine datei settings_mdatp.rb im Ordner mdatp/recipies erstellen und diesen Text hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="516e4-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

<span data-ttu-id="516e4-128">Wenn Sie diesen Schritt als Teil des Rezepts hinzufügen möchten, fügen Sie einfach include_recipe ":: settings_mdatp" zur Datei default.rb im Rezeptordner hinzu.</span><span class="sxs-lookup"><span data-stu-id="516e4-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="516e4-129">Sie können auch crontab verwenden, um automatische Updates zu planen Planen eines Updates von [Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span><span class="sxs-lookup"><span data-stu-id="516e4-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="516e4-130">Deinstallieren des MDATP-Kochbuchs:</span><span class="sxs-lookup"><span data-stu-id="516e4-130">Uninstall MDATP cookbook:</span></span>

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

