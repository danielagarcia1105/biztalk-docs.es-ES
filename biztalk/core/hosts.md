---
title: Hosts | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host instances, servers
- hosts, isolated
- host instances, relationships
- hosts, in-process hosts
- servers, hosts
- hosts, host instances
- hosts, relationships
- In-Process BizTalk Host groups
- hosts, about hosts
- hosts, untrusted
- host instances, hosts
- hosts, servers
- hosts
- servers, host instances
- Isolated Host Users group
- hosts, trusted
ms.assetid: d96537e0-e679-407a-8870-34a663acfed9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790c839685e71dd1a88b637e5ca7811d62809cc0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980021"
---
# <a name="hosts"></a>Hosts
El objeto de host de BizTalk representa un conjunto lógico que puede contener (o no) procesos en tiempo de ejecución y en el que se pueden implementar servicios, canalizaciones y otros artefactos. Además, representa un conjunto de instancias de hosts que puede estar vacío y en el que se ejecutan físicamente los elementos implementados.  
  
 Una vez creado un host (contenedor lógico), puede agregar servidores físicos BizTalk (instancias de host) al host. Los servidores BizTalk no se pueden agregar más de una vez en el mismo host. No obstante, una instancia de host se puede agregar a varios hosts.  
  
 Los elementos, como controladores de adaptador, ubicaciones de recepción (incluidas las canalizaciones) y orquestaciones, incluidos en BizTalk hosts pueden realizar las siguientes funciones:  
  
- **Recibir**. Estos elementos realizan el procesamiento inicial de los mensajes después de haberlos recogido en una ubicación de recepción. Cuando un host contiene un elemento de recepción, como una canalización o una ubicación de recepción, actúa como un límite de seguridad y la descodificación y descifrado de mensajes tiene lugar en una canalización del host.  
  
- **Enviar**. Estos elementos realizan el procesamiento final de los mensajes antes de enviarlos al puerto de envío. Cuando un host contiene un elemento de envío, como un puerto de envío o una canalización, el host actúa como un límite de seguridad, y la firma y cifrado de mensajes tiene lugar en una canalización del host.  
  
- **Procesamiento**. Estos elementos procesan los mensajes en función de las instrucciones de una orquestación.  
  
  Un host de BizTalk puede contener elementos que reciben, envían y procesan mensajes. Se recomienda crear diferentes hosts para cada función con el fin de crear límites de seguridad y facilitar la administración. En concreto, se recomienda utilizar hosts diferentes para operaciones de procesamiento y recepción o envío, así como separar los elementos que son de confianza de los que no lo son.  
  
  La siguiente ilustración muestra la relación entre servidores, hosts e instancias de host.  
  
  ![Hosts, instancias de host y las relaciones de servidor](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
  Relación entre hosts, instancias de host y servidores  
  
  Para obtener más información acerca de las instancias de Host, consulte [instancias de Host](../core/host-instances.md).  
  
  Según la configuración física y el tipo de adaptador que se aloje, hay dos tipos de hosts: hosts y hosts aislados en el proceso.  
  
## <a name="in-process-hosts"></a>Hosts de tipo en curso  
 Los hosts de tipo En curso representan instancias de servicio que un administrador crea, elimina y controla por completo a través del Instrumental de administración de Windows (WMI) y la Consola de administración de BizTalk.  
  
 Los hosts de tipo En curso cuentan con las siguientes características:  
  
- Las orquestaciones pueden darse de alta en los hosts de tipo En curso.  
  
- Los hosts de tipo En curso pueden alojar controladores de envío.  
  
- Un host de tipo En curso puede alojar cualquiera de los controladores de recepción excepto SOAP y HTTP:  
  
  -   FILE  
  
  -   FTP  
  
  -   MQSeries  
  
  -   MSMQ  
  
  -   POP3  
  
  -   SQL  
  
  -   Windows SharePoint Services  
  
- El primer host en proceso se crea en un [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] implementación es el **host predeterminado** y no puede eliminarlo. El Adaptador de BizTalk para Message Queue Server utiliza el host predeterminado para la configuración del controlador estático. La agregación automática de adaptadores crea puertos de envío y recepción en el host predeterminado.  
  
## <a name="isolated-hosts"></a>Hosts aislados  
 Los hosts aislados representan instancias de servicio que un programador de soluciones crea, elimina y controla mediante programación. Los administradores usan el WMI y la Consola de administración de BizTalk para configurar estos hosts (por ejemplo, para configurar la cuenta de servicio de host y la autenticación de confianza).  
  
 Los hosts aislados se encargan principalmente de alojar adaptadores que deban ejecutarse fuera del proceso en tiempo de ejecución habitual de BizTalk Server. Por ejemplo, los hosts aislados se emplean para alojar adaptadores para procesos externos como, por ejemplo, extensiones ISAPI y ASP.NET.  
  
 Los hosts aislados cuentan con las siguientes características:  
  
-   Las orquestaciones no pueden darse de alta en un host aislado.  
  
-   Los hosts aislados no pueden alojar controladores de envío.  
  
-   Los hosts aislados solo pueden alojar controladores de recepción que estén asociados con adaptadores de HTTP/S y SOAP (los adaptadores de tipo aislado).  
  
-   Los hosts aislados no pueden alojar el seguimiento.  
  
-   Un host aislado no puede ser el host predeterminado.  
  
-   El estado de un host aislado siempre es **estado no disponible**. BizTalk Server no tiene acceso a la información de estado de los procesos externos.  
  
> [!NOTE]
>  Las instancias de hosts pueden compartir la misma cuenta de servicio siempre que compartan también la misma configuración de seguridad (autenticación de confianza).  
  
## <a name="trusted-and-untrusted-hosts"></a>Hosts de confianza y de no confianza  
 BizTalk Server permite que un host identificado como con autenticación de confianza indique que el remitente de un mensaje que dicho host está agregando a la cola de la base de datos de cuadro de mensajes es una entidad distinta del host de confianza mismo. Los fines principales de la autenticación de confianza son permitir que las canalizaciones se resuelvan en un Id. de producto (PID) y pasen éste a servicios de consumo para su uso en la autorización y la resolución de entidades salientes, y permitir la transmisión del Id. de seguridad de Windows del remitente (SSID) a los servicios de consumo para su uso en la autorización de acciones de orquestación.  
  
## <a name="see-also"></a>Vea también  
 [Instancias de host](../core/host-instances.md)   
 [Administrar hosts de BizTalk e instancias de host](../core/managing-biztalk-hosts-and-host-instances.md)  
 [Entidades](../core/entities.md)