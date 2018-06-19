---
title: Importar o exportar la configuración de BizTalk mediante BTSTask | Documentos de Microsoft
description: Usar comandos ImportSettings o ExportSettings BTSTask para mover la configuración de un entorno a otro en BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99aecaea767133fc5f3cb77d38dc174b09733674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255148"
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a><span data-ttu-id="24e31-103">Utilizar BTSTask para importar o exportar la configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="24e31-103">Use BTSTask to import or export BizTalk settings</span></span>

## <a name="overview"></a><span data-ttu-id="24e31-104">Información general</span><span class="sxs-lookup"><span data-stu-id="24e31-104">Overview</span></span>
<span data-ttu-id="24e31-105">Mediante la utilidad de línea de comandos BTSTask, se puede exportar la configuración de un entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] e importarla en otro entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], lo que reduce el tiempo general necesario para implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="24e31-105">Using the BTSTask command-line utility, you can export the settings from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment and import them to another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, thereby reducing the overall time-to-solution.</span></span> <span data-ttu-id="24e31-106">Esto es especialmente práctico en aquellas situaciones en las que los administradores intentan mejorar el rendimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en un entorno de ensayo y, una vez obtenidos los resultados deseados, pueden importar la configuración en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="24e31-106">This is especially useful in scenarios where the administrators try to tune [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance in a staging environment, and upon achieving the desired results, they can import the settings into a production environment.</span></span> 

<span data-ttu-id="24e31-107">En este tema se enumera los pasos para importar o exportar la configuración de BizTalk Server de un entorno a otro mediante **BTSTask.exe**.</span><span class="sxs-lookup"><span data-stu-id="24e31-107">This topic lists the steps to import or export the BizTalk Server settings from one environment to another using **BTSTask.exe**.</span></span>  


## <a name="import-biztalk-settings"></a><span data-ttu-id="24e31-108">Importar configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="24e31-108">Import BizTalk settings</span></span> 
> [!IMPORTANT]
>  <span data-ttu-id="24e31-109">Para importar la configuración de BizTalk desde un entorno concreto, debe haber exportado y guardado esa configuración a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="24e31-109">To import the BizTalk settings from a certain environment, you should have already exported and saved those settings in an XML file.</span></span> <span data-ttu-id="24e31-110">Para obtener más información acerca de cómo exportar la configuración, consulte [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) o **exportar la configuración de BizTalk usar BTSTask** (en este tema).</span><span class="sxs-lookup"><span data-stu-id="24e31-110">For more information about exporting the settings, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) or **Export BizTalk Settings Using BTSTask** (in this topic).</span></span>  
  
 <span data-ttu-id="24e31-111">Al importar el archivo XML, se puede replicar la configuración de BizTalk Server necesaria en el equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="24e31-111">By importing the XML file, you can replicate the required BizTalk Server settings on the target machine.</span></span> <span data-ttu-id="24e31-112">Mediante el **BTSTask.exe**, puede importar la configuración de grupo, Host e instancia de Host y asignar las propiedades de uno a otro.</span><span class="sxs-lookup"><span data-stu-id="24e31-112">Using the **BTSTask.exe**, you can import the Group, Host, and Host Instance settings and map the properties of one to another.</span></span> <span data-ttu-id="24e31-113">Las hipótesis necesarias para importar la configuración son:</span><span class="sxs-lookup"><span data-stu-id="24e31-113">Following are the necessary assumptions for importing the settings:</span></span>  
  
-   <span data-ttu-id="24e31-114">La configuración de BizTalk Server se puede importar a través de topologías similares.</span><span class="sxs-lookup"><span data-stu-id="24e31-114">You can import the BizTalk Server settings across similar topologies.</span></span>  
  
-   <span data-ttu-id="24e31-115">Debería poder asignar las instancias de host y el host de origen a sus equivalentes en el destino.</span><span class="sxs-lookup"><span data-stu-id="24e31-115">You should be able to map the source Host and Host Instances to the destination counterparts.</span></span>  
  
-   <span data-ttu-id="24e31-116">El entorno de destino tiene un hardware similar (si no idéntico) al entorno de origen.</span><span class="sxs-lookup"><span data-stu-id="24e31-116">The destination environment has hardware similar (if not identical) to the source environment.</span></span> <span data-ttu-id="24e31-117">Esto es esencial, ya que algunas de las configuraciones dependen del hardware subyacente.</span><span class="sxs-lookup"><span data-stu-id="24e31-117">This is essential as some of the settings depend on the underlying hardware.</span></span>  
  
### <a name="importsettings-command"></a><span data-ttu-id="24e31-118">Comando ImportSettings</span><span class="sxs-lookup"><span data-stu-id="24e31-118">ImportSettings command</span></span> 
 <span data-ttu-id="24e31-119">Puede usar el **ImportSettings** comandos de BTSTask para importar la configuración de BizTalk Server desde el entorno de origen al entorno de destino.</span><span class="sxs-lookup"><span data-stu-id="24e31-119">You can use the **ImportSettings** BTSTask command to import BizTalk Server settings from the source environment to destination environment.</span></span> <span data-ttu-id="24e31-120">Vea [comando ImportSettings](../core/importsettings-command.md) para obtener detalles específicos.</span><span class="sxs-lookup"><span data-stu-id="24e31-120">See [ImportSettings Command](../core/importsettings-command.md) for specific details.</span></span>  
  
 <span data-ttu-id="24e31-121">Puede definir la asignación de un host de origen a un host de destino o de una instancia de host de origen a una instancia de host de destino de este modo:</span><span class="sxs-lookup"><span data-stu-id="24e31-121">You can define the mapping from a source host to a destination host and/or a source host instance to a destination host instance as shown:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SettingsMap>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerApplication">  
  <DestinationHosts>BizTalkServerApplication</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerIsolatedHost">  
  <DestinationHosts>BizTalkServerIsolatedHost</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host1">  
  <DestinationHosts>Host2</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host2">  
  <DestinationHosts>Host1;Host3;Host4;Host5</DestinationHosts>   
  </SourceHost>  
  </HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostInstanceMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="BizTalkServerApplication:COMPUTER_NAME1">  
  <DestinationHostInstances>BizTalkServerApplication:COMPUTER_NAME2</DestinationHostInstances>   
  </SourceHostInstance>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="Host1:COMPUTER_NAME1">  
  <DestinationHostInstances>Host2:COMPUTER_NAME2;Host3:COMPUTER_NAME3;Host4:COMPUTER_NAME4;Host5:COMPUTER_NAME5</DestinationHostInstances>   
  </SourceHostInstance>  
  </HostInstanceMappings>  
  </SettingsMap>  
  
```  
  
 <span data-ttu-id="24e31-122">En un archivo de asignación, especifique una instancia de host como 'Hostname: MachineName'.</span><span class="sxs-lookup"><span data-stu-id="24e31-122">In a map file, enter a host instance as 'HostName:MachineName'.</span></span> <span data-ttu-id="24e31-123">Por ejemplo: "Host1:Server1" hace referencia a la instancia de host 'Host1' qué se está ejecutando (o presente) en el equipo 'Server1'.</span><span class="sxs-lookup"><span data-stu-id="24e31-123">For example: "Host1:Server1" means the instance of host 'Host1' which is running (or present) on machine 'Server1".</span></span>  
  
 <span data-ttu-id="24e31-124">Para especificar el origen de 1: n las asignaciones de destino, utilice una lista separada por punto y coma.</span><span class="sxs-lookup"><span data-stu-id="24e31-124">To enter 1:n source to destination mappings, use a semicolon-separated list.</span></span> <span data-ttu-id="24e31-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24e31-125">For example:</span></span>  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 <span data-ttu-id="24e31-126">Solo se pueden asignar los host-instancias para los que también se haya creado la asignación de host correspondiente.</span><span class="sxs-lookup"><span data-stu-id="24e31-126">Only those host-instances can be mapped for which the corresponding host mapping has also been created.</span></span> <span data-ttu-id="24e31-127">Si 'SourceHost1' se ha asignado a 'DestinationHost1' en las asignaciones de host, las instancias (si existen) de 'DestinationHost1' solo se pueden asignar a las instancias (si existen) de 'SourceHost1'.</span><span class="sxs-lookup"><span data-stu-id="24e31-127">If 'SourceHost1' has been mapped to 'DestinationHost1' in host mappings, the instances (if any) of 'DestinationHost1' can be mapped only to the instances (if any) of 'SourceHost1'.</span></span> <span data-ttu-id="24e31-128">La interfaz de usuario del Asistente para importar se encarga de esta restricción.</span><span class="sxs-lookup"><span data-stu-id="24e31-128">The UI Import Wizard takes care of this constraint.</span></span> <span data-ttu-id="24e31-129">Debe escribirlo explícitamente en el archivo de asignación.</span><span class="sxs-lookup"><span data-stu-id="24e31-129">You would need to explicitly write it in the map file.</span></span>  


## <a name="export-biztalk-settings"></a><span data-ttu-id="24e31-130">Exportar la configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="24e31-130">Export BizTalk settings</span></span>  

<span data-ttu-id="24e31-131">Hay un par de formas para exportar la configuración de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="24e31-131">There are a couple of ways to export the BizTalk settings:</span></span> 

1. <span data-ttu-id="24e31-132">Use la **ExportSettings** comandos de BTSTask para exportar la configuración de BizTalk Server al entorno de origen a un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="24e31-132">Use the **ExportSettings** BTSTask command to export the BizTalk Server settings of the source environment to an XML file.</span></span> <span data-ttu-id="24e31-133">Vea [comando ExportSettings](../core/exportsettings-command.md) para obtener más detalles.</span><span class="sxs-lookup"><span data-stu-id="24e31-133">See [ExportSettings Command](../core/exportsettings-command.md) for more details.</span></span>  

2.  <span data-ttu-id="24e31-134">Utilice el panel de configuración de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="24e31-134">Use the Settings Dashboard in BizTalk Server Administration.</span></span> <span data-ttu-id="24e31-135">Vea [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md) para conocer los pasos.</span><span class="sxs-lookup"><span data-stu-id="24e31-135">See [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md) for the steps.</span></span>

 
> [!TIP]
>  <span data-ttu-id="24e31-136">Para obtener información sobre cómo se aplica la configuración de BizTalk Server en un archivo XML para el entorno de destino, vea [importación o exportación panel de configuración de uso de configuración de BizTalk](how-to-import-biztalk-settings-using-settings-dashboard.md).</span><span class="sxs-lookup"><span data-stu-id="24e31-136">For information about how the BizTalk Server settings in an XML file are applied to the target environment, see [Import or export BizTalk Settings Using Settings Dashboard](how-to-import-biztalk-settings-using-settings-dashboard.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="24e31-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="24e31-137">See Also</span></span>  
 [<span data-ttu-id="24e31-138">Automatizar el servidor BizTalk Server ajuste del rendimiento</span><span class="sxs-lookup"><span data-stu-id="24e31-138">Automate BizTalk Server Performance Tuning</span></span>](../core/automating-biztalk-server-performance-tuning.md)