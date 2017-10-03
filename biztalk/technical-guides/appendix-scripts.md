---
title: "Apéndice: Scripts | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6394321-13c9-4b1d-b529-eba3d53b33c4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12df00876f6b2da9ebb98631016bd42947b4a40a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="appendix-scripts"></a>Apéndice: secuencias de comandos
Las secuencias de comandos siguientes se incluyen en este módulo de administración.  
  
|Script|Finalidad|  
|------------|-------------|  
|Microsoft.BizTalk.Server.2013.ArtifactsDiscovery.vbs|Este script detecta los artefactos de la aplicación en función de $Config parámetro$ (opción). Las opciones incluyen<br /><br /> -Todos los puertos de envío, grupos de puertos de envío en una aplicación, sus relaciones de hospedaje a una aplicación y las relaciones de grupo de puertos contiene el puerto de envío de envío.<br />-Todas las orquestaciones en una aplicación, sus relaciones de hospedaje para la aplicación.<br />-Todos los puertos de recepción, ubicaciones de recepción en una aplicación, su relación de hospedaje ' a una aplicación y ' puerto de recepción contiene ubicación de recepción ' relaciones.|  
|Microsoft.BizTalk.Server.2013.ApplicationDiscovery.vbs|Este script detecta lo siguiente:<br /><br /> -Todas las aplicaciones en un grupo y las relaciones "grupo de aplicaciones de hosts".<br />-Todos los hosts en un grupo y las relaciones de "host de hosts de grupo".|  
|Microsoft.BizTalk.Server.2013.BAMAnalysisDiscovery.vbs|Este script detecta el análisis de BAM y alertas de componentes en un equipo donde se descubre el componente de tiempo de ejecución BAM.|  
|Microsoft.BizTalk.Server.2013.BAMPortalDiscovery.vbs|Este script detecta el portal de BAM configurado en un equipo con IIS. También detecta la función BAM y la contención de portal de BAM en ella.|  
|Microsoft.BizTalk.Server.2013.BAMRuntimeDiscovery.vbs|Este script detecta el componente de tiempo de ejecución BAM en un equipo que se pasa como parámetro $Config/ComputerName$. Si no se pasa el nombre del equipo detecta BAM en un equipo en tiempo de ejecución con el Id. de servidor más bajo en la base de datos de administración. También detecta la función BAM y la contención de BAM en tiempo de ejecución en él.|  
|Microsoft.BizTalk.Server.2013.BizTalkApplicationServiceDiscovery.vbs|Este script detecta todos los servicios de aplicaciones de BizTalk en un equipo junto con sus relaciones de hospedaje con la función en tiempo de ejecución.|  
|Microsoft.BizTalk.Server.2013.BizTalkGroupDiscovery.vbs|Este script detecta el grupo de BizTalk en un equipo que se pasa como parámetro $Config/ComputerName$. Si no se pasa el nombre del equipo, a continuación, detecta grupo en un equipo en tiempo de ejecución con el Id. de servidor más bajo en la base de datos de administración.|  
|Microsoft.BizTalk.Server.2013.BizTalkRoleDiscovery.vbs|Este script detecta los roles de servidor de BizTalk en un equipo especificado en función de parámetro. $Config$ (opción). Entre las opciones posibles se encuentran las siguientes:<br /><br /> -Rol en tiempo de ejecución de BizTalk, implementación de grupo de BizTalk y la contención de tiempo de ejecución en la implementación del grupo.<br />-El motor de reglas de BizTalk rol, la implementación del grupo de BizTalk y contención del motor de reglas de implementación de grupo. Rol BAM siempre se detecta con cualquiera de las opciones y la contención en la implementación de grupo.|  
|BizTalkAnalysisDatabaseMonitor.vbs|Esta secuencia de comandos genera datos de supervisión de disponibilidad de base de datos de análisis SQL basándose en la conectividad. Los Estados de monitor pueden ser correcto o error.|  
|BizTalkArtifactConfigurationMonitor.vbs|Esta secuencia de comandos genera datos de supervisión de configuración de artefacto de aplicación de BizTalk. Cada artefacto se encontrarán en uno de los tres correcta supervisión de Estados, advertencia y error.|  
|BizTalkArtifactSuspendedInstancesMonitor.vbs|Esta secuencia de comandos genera datos de supervisión de estado del artefacto en tiempo de ejecución de BizTalk aplicación según el número de instancias suspendidas por artefacto. Cada artefacto se encontrarán en uno de los tres correcta supervisión de Estados, advertencia y error.|  
|BizTalkBAMPortalMonitor.vbs|Esta secuencia de comandos genera datos de supervisión de disponibilidad de portal de BAM. Los Estados de monitor pueden ser correcto o error.|  
|BizTalkHostConfigurationMonitor.vbs|Esta secuencia de comandos genera datos de supervisión de host de BizTalk en función de la disponibilidad de todas sus instancias de host (BTSNTSvc.exe). El monitor de estados puede ser cualquier correcto (ejecutando > = límite de éxito), advertencia (ejecutando > = límite de advertencia y en ejecución < límite correcto) o error.|  
|BizTalkDatabaseMonitor.vbs|Esta secuencia de comandos genera datos de supervisión de disponibilidad de una base de datos SQL basándose en la conectividad. Los Estados de monitor pueden ser correcto o error.|  
|BizTalkMultipleDatabaseMonitor.vbs|Esta secuencia de comandos genera datos de supervisión de disponibilidad de un grupo de bases de datos SQL como una sola entidad basándose en la conectividad. Estados del monitor pueden ser cualquier error (base de datos principal no está disponible), correcto (todas las bases de datos disponibles) o advertencia (algunas no principales bases de datos no está disponible).|  
|BizTalkHostProbeAction.vbs|Esta secuencia de comandos genera datos de diagnóstico para el host de BizTalk en función de la disponibilidad de todas sus instancias de host (BTSNTSvc.exe). Correspondientes a Estados de advertencia y error muestra la instancia de host que no se están ejecutando.|  
|Microsoft.BizTalk.Server.2013.HostAction.vbs|Este script se utiliza para iniciar o detener un Host de BizTalk.|  
|Microsoft.BizTalk.Server.2013.OrchestrationAction.vbs|Este script se utiliza para iniciar o detener una orquestación (artefacto de aplicación de BizTalk).|  
|Microsoft.BizTalk.Server.2013.EnableReceiveLocation.vbs|Esta secuencia de comandos utiliza para habilitar o deshabilitar una ubicación de recepción (artefacto de aplicación de BizTalk).|  
|Microsoft.BizTalk.Server.2013.SendPortAction.vbs|Este script se utiliza para iniciar o detener un puerto de envío (artefacto de aplicación de BizTalk).|  
|Microsoft.BizTalk.Server.2013.SendPortGroupAction.vbs|Este script se utiliza para iniciar o detener un grupo de puertos de envío (artefacto de aplicación de BizTalk).|