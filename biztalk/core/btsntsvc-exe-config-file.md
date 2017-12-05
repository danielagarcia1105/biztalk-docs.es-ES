---
title: Archivo BTSNTSvc.exe.config | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2bb89a7-4fff-4ccf-a0a7-20ca610f2ddf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7fae2fc49487597380e6c5d04a946b1078daeeb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="btsntsvcexeconfig-file"></a><span data-ttu-id="5eec6-102">BTSNTSvc.exe.config (archivo)</span><span class="sxs-lookup"><span data-stu-id="5eec6-102">BTSNTSvc.exe.config File</span></span>
<span data-ttu-id="5eec6-103">Las propiedades de deshidratación y sus valores predeterminados se pueden configurar en [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] o como XML en el archivo de configuración de BizTalk (BTSNTSvc.exe.config o BTSNTSvc64.exe.config).</span><span class="sxs-lookup"><span data-stu-id="5eec6-103">Dehydration properties and their default values are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="5eec6-104">Los valores del archivo de configuración de BizTalk se aplican antes.</span><span class="sxs-lookup"><span data-stu-id="5eec6-104">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="5eec6-105">A continuación, se aplica la configuración de [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5eec6-105">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="5eec6-106">Las propiedades de deshidratación se leen cuando se inician todas las instancias de host que contienen una orquestación.</span><span class="sxs-lookup"><span data-stu-id="5eec6-106">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
 <span data-ttu-id="5eec6-107">Este tema se centra en el archivo de configuración de BizTalk (BTSNTSvc.exe.config o BTSNTSvc64.exe.config).</span><span class="sxs-lookup"><span data-stu-id="5eec6-107">This topic focuses on the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="5eec6-108">Muchas propiedades de deshidratación no se enumeran.</span><span class="sxs-lookup"><span data-stu-id="5eec6-108">Many dehydration properties are not listed.</span></span> <span data-ttu-id="5eec6-109">Sin embargo, estas propiedades se aplican con sus valores predeterminados aunque no se especifiquen explícitamente en el archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5eec6-109">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="5eec6-110">Para cambiar los valores predeterminados, debe agregarlos de forma explícita al archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5eec6-110">To change the default values, you must explicitly add them to your configuration file.</span></span> <span data-ttu-id="5eec6-111">Para obtener información acerca de cómo cambiar el comportamiento de deshidratación predeterminado, consulte [cómo modificar configuración de la limitación de orquestación](../core/how-to-modify-orchestration-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5eec6-111">For information about how to change the default dehydration behavior, see [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span> <span data-ttu-id="5eec6-112">Para obtener información acerca de la limitación de memoria de orquestación, consulte [cómo modificar configuración de limitación de orquestación memoria](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5eec6-112">For information about orchestration memory throttling, see [How to Modify Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
 <span data-ttu-id="5eec6-113">A continuación figura el contenido del archivo BTSNTSvc.exe.config.</span><span class="sxs-lookup"><span data-stu-id="5eec6-113">Following is the contents of the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="5eec6-114">Este archivo siempre se encuentra en el mismo directorio que el archivo BTSNTSvc.exe, que normalmente es C:\Program Files\Microsoft BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="5eec6-114">This file is always located in the same directory as the BTSNTSvc.exe file, which is usually C:\Program Files\Microsoft BizTalk Server.</span></span>  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section name="xlangs" type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
       <xlangs>  
              <Configuration>  
                     <Dehydration MaxThreshold="1800" MinThreshold="1" ConstantThreshold="-1">  
                            <VirtualMemoryThrottlingCriteria OptimalUsage="900" MaximalUsage="1300" IsActive="true" />  
                            <PrivateMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="true" />  
                            <PhysicalMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="false" />  
                     </Dehydration>  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5eec6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5eec6-115">See Also</span></span>  
 [<span data-ttu-id="5eec6-116">Uso del panel de configuración para ajustar el rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="5eec6-116">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)