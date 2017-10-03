---
title: Admin (carpeta de ejemplos de BizTalk Server) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SDK examples
- examples, administering
- administering, examples
ms.assetid: 178d0ee2-d437-4945-a35d-1a8be524aff1
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d50da9489338ff9b3bf00dd829d7001b12d1b93c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="admin-biztalk-server-samples-folder"></a>Admin (carpeta de ejemplos de BizTalk Server)
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] incluye varios ejemplos de administración en su kit de desarrollo de software (SDK). En esta sección se proporciona información detallada acerca de la funcionalidad que se muestra en cada ejemplo de administración, de las instrucciones para la generación y ejecución del ejemplo y de los resultados que se pueden esperar.  
  
> [!WARNING]
>  Las secuencias de comandos de implementación se deben quitar después de la implementación si no son necesarias. La lista de control de acceso (ACL) debe proteger y supervisar detalladamente las secuencias de comandos de administración y otras secuencias de comandos que deben permanecer.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Administración-ExplorerOM (carpeta de ejemplos de BizTalk Server)](../core/admin-explorerom-biztalk-server-samples-folder.md).  
  
    -   [ApplicationManager (ejemplo de BizTalk Server)](../core/applicationmanager-biztalk-server-sample.md). Muestra cómo iniciar o detener una aplicación de BizTalk.  
  
    -   [BrowsingArtifacts (ejemplo de BizTalk Server)](../core/browsingartifacts-biztalk-server-sample.md). Muestra cómo enumerar los artefactos y los atributos de BizTalk.  
  
    -   [CBR (ejemplo de BizTalk Server)](../core/cbr-biztalk-server-sample.md). Muestra cómo agregar y configurar nuevos puertos de envío para el enrutamiento basado en contenido de los mensajes de BizTalk.  
  
    -   [DeleteParty (ejemplo de BizTalk Server)](../core/deleteparty-biztalk-server-sample.md). Muestra cómo eliminar una entidad especificada.  
  
    -   [OrchestrationBinding (ejemplo de BizTalk Server)](../core/orchestrationbinding-biztalk-server-sample.md). Muestra cómo administrar y configurar las orquestaciones.  
  
    -   [PartnerManagement (ejemplo de BizTalk Server)](../core/partnermanagement-biztalk-server-sample.md). Muestra cómo crear y eliminar entidades. También muestra cómo dar de alta y de baja entidades con roles.  
  
    -   [ReceiveLocations (ejemplo de BizTalk Server)](../core/receivelocations-biztalk-server-sample.md). Muestra cómo crear y administrar ubicaciones de recepción para puertos de recepción.  
  
    -   [ReceivePorts (ejemplo de BizTalk Server)](../core/receiveports-biztalk-server-sample.md). Muestra cómo crear, enumerar y eliminar puertos de recepción.  
  
    -   [SendPortGroups (ejemplo de BizTalk Server)](../core/sendportgroups-biztalk-server-sample.md). Muestra cómo enumerar y administrar grupos de puertos de envío.  
  
    -   [PuertosEnvío (ejemplo de BizTalk Server)](../core/sendports-biztalk-server-sample.md). Muestra cómo enumerar y administrar puertos de envío.  
  
    -   [UnenlistParties (ejemplo de BizTalk Server)](../core/unenlistparties-biztalk-server-sample.md). Muestra cómo dar de baja todas las entidades asociadas a un ensamblado de BizTalk implementado.  
  
    -   [Sysprep un disco duro virtual (ejemplo de BizTalk Server) con el servidor BizTalk Server](../core/sysprep-a-biztalk-server-vhd-biztalk-server-sample.md). Muestra cómo crea una instantánea de una máquina virtual con Sysprep [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] instalado para una implementación rápida en otras máquinas virtuales.  
  
-   [Administración-OperationsOM (carpeta de ejemplos de BizTalk Server)](../core/admin-operationsom-biztalk-server-samples-folder.md)  
  
    -   [OperationsSamples (ejemplo de BizTalk Server)](../core/operationssamples-biztalk-server-sample.md)  
  
-   [WMI de administración (carpeta de ejemplos de BizTalk Server)](../core/admin-wmi-biztalk-server-samples-folder.md)  
  
    -   [Habilitar (ejemplo de BizTalk Server) de la ubicación de recepción](../core/enable-receive-location-biztalk-server-sample.md). Muestra cómo habilitar una ubicación de recepción y establecer la dirección URL de transporte de entrada para esa ubicación de recepción.  
  
    -   [Dar de alta una orquestación (ejemplo de BizTalk Server)](../core/enlist-orchestration-biztalk-server-sample.md). Muestra cómo dar de alta una orquestación de BizTalk Server en un host.  
  
    -   [Enumerar (ejemplo de BizTalk Server) de ubicaciones de recepción](../core/enumerate-receive-locations-biztalk-server-sample.md) ejemplo. Muestra cómo recuperar detalles sobre una o varias ubicaciones de recepción.  
  
    -   [Quitar (ejemplo de BizTalk Server) del puerto de recepción](../core/remove-receive-port-biztalk-server-sample.md). Muestra cómo quitar uno o varios puertos de recepción.  
  
    -   [Quitar puerto de envío (ejemplo de BizTalk Server)](../core/remove-send-port-biztalk-server-sample.md). Muestra cómo dar de baja y quitar uno o varios puertos de envío.  
  
    -   [Establecer la propiedad de controlador de envío (ejemplo de BizTalk Server)](../core/set-send-handler-property-biztalk-server-sample.md). Muestra cómo establecer la información de configuración de XML para un controlador de envío del Protocolo simple de transferencia de correo (SMTP).  
  
    -   [Iniciar puerto de envío (ejemplo de BizTalk Server)](../core/start-send-port-biztalk-server-sample.md). Muestra cómo iniciar un puerto de envío y establecer la dirección de transporte principal al usar el adaptador de archivo.  
  
    -   [Detener la orquestación (ejemplo de BizTalk Server)](../core/stop-orchestration-biztalk-server-sample.md). Muestra cómo detener una orquestación de BizTalk Server y, de forma opcional, darla de baja.