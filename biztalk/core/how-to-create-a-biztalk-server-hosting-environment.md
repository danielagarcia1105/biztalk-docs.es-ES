---
title: Cómo crear un entorno de hospedaje de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosting environments, creating
- managing [hosts], hosting environments
- hosts, environments
- managing [hosts], creating
- creating, hosting environment
ms.assetid: 6f335139-1121-45ff-88da-5c626b8fff97
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba3829a2fecb32a191b7351833e975bf3770547d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013384"
---
# <a name="how-to-create-a-biztalk-server-hosting-environment"></a>Cómo crear un entorno de host de BizTalk Server
Antes de crear el entorno de host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], considere las siguientes recomendaciones:  

- **Utilice hosts diferentes para las orquestaciones que no son de confianza y controladores de recepción**  

   Los elementos que se ejecutan en un host (por ejemplo, orquestaciones, canalizaciones, controladores de envío y recepción) se ejecutan con la misma identidad y tienen acceso a las colas de trabajo y de suspensión de ese host.  

   Si no se puede entregar un mensaje a una orquestación debido a errores de permisos, el mensaje se coloca en la cola de suspensión del host donde se está ejecutando el proceso de envío (una canalización de recepción u otra orquestación). Sin embargo, si la orquestación y el proceso de envío (por ejemplo, una canalización de recepción) se ejecutan en el mismo host, la orquestación puede tener aún acceso al mensaje en la cola de suspensión. Esto podría comprometer el sistema si una orquestación que no sea de confianza se ejecuta en un host de confianza.  

   Se recomienda ejecutar las orquestaciones que no sean de confianza en otro host, con una cuenta de servicio diferente que los hosts de confianza del grupo de BizTalk. Para obtener información acerca de cómo designar un host como de confianza, vea [cómo modificar las propiedades de Host](../core/how-to-modify-host-properties.md).  

- **Limitar el tamaño de base de datos y registro en las bases de datos de BizTalk Server**  

   Las bases de datos de cuadro de mensajes de BizTalk y la base de datos de seguimiento de BizTalk crecen con más rapidez que las demás bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Como parte de su programa de copia de seguridad y mantenimiento, debe actualizar estas bases de datos con frecuencia.  

   De forma predeterminada, las tablas de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no tienen límite de tamaño de registro. Como parte de su programa de copia de seguridad y mantenimiento, se recomienda que limite el tamaño de registro para evitar que los registros se hagan demasiado grandes y utilicen todo el espacio del disco. Para obtener información acerca de cómo administrar el tamaño de la base de datos de seguimiento, vea [archivar y purgar la base de datos de seguimiento de BizTalk](../core/archiving-and-purging-the-biztalk-tracking-database.md).  

- **Usar clústeres de SQL Server**  

   Para proporcionar alta disponibilidad de las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], se recomienda agrupar los servidores SQL Server donde se almacenan las bases de datos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto contribuirá a minimizar el tiempo de inactividad si una de las bases de datos o alguno de los servidores SQL da error. Para obtener más información acerca de los clústeres del servidor SQL Server, vea el tema sobre la arquitectura de clúster de conmutación por error en los Libros en pantalla de SQL Server.  

## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  

- Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

- En las instrucciones del siguiente procedimiento se presupone que tiene instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con la opción de instalación completa. Si no instaló [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] con la opción de instalación completa, es posible que algunos objetos de administración enumerados en el paso 1 falten en el sistema.  

### <a name="to-create-a-biztalk-server-hosting-environment"></a>Para crear un entorno de host de BizTalk Server  

1. Use la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para crear un nuevo grupo de BizTalk. Para obtener información acerca de cómo crear un nuevo [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] de grupo, vea [grupos de configuración mediante la configuración de BizTalk Server](http://msdn.microsoft.com/library/16beb7bb-091c-4056-8622-cc79c95186e9).  

    La configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] crea los siguientes objetos de administración:  


   |                   Objeto de administración                    |                                                                                                                                                                                                                                       Descripción                                                                                                                                                                                                                                       |
   |------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      **Administración de BizTalk** base de datos (BizTalkMgmtDb)       |                                                                                                                                                                    Esta base de datos es el almacén central de metainformación para todos los servidores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].                                                                                                                                                                     |
   |     **BizTalk MessageBox** (BizTalkMsgBoxDb) de la base de datos      |           Esta base de datos almacena los predicados de suscripción. Se trata de una plataforma de host donde se encuentran las colas y las tablas de estado de cada host de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. La base de datos de cuadro de mensajes también almacena los mensajes y sus propiedades. Para obtener información acerca de las bases de datos de cuadro de mensajes, incluido agregar bases de datos de cuadro de mensajes adicionales, consulte [administrar bases de datos de cuadro de mensajes](../core/managing-messagebox-databases.md).           |
   |                         **Server**                         | Éste es el equipo en el que está instalado y configurado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y donde se ejecutan las instancias de host. Las instancias de host se crean a partir de un host creado en un servidor. Para obtener más información sobre la creación de un host, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md). Para obtener información sobre la creación de instancias de host, consulte [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md). |
   |     **Importación principal de BAM** (BAMPrimaryImport) de la base de datos     |                                                                                                                                                                                                Ésta es la base de datos en la que la herramienta Supervisión de la actividad económica recoge los datos de seguimiento.                                                                                                                                                                                                 |
   |       **Motor de reglas** (BizTalkRuleEngineDb) de la base de datos       |                                                                                                                                                                                       Esta base de datos es un repositorio para directivas, reglas y vocabularios para referencias de datos de reglas de negocios.                                                                                                                                                                                        |
   |        **Seguimiento de BizTalk** (BizTalkDTADb) de la base de datos        |                                                                                                                                                       Esta base de datos almacena datos económicos y de supervisión de estado controlados mediante el motor de seguimiento de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].                                                                                                                                                       |
   |                  **Inicio de sesión único** (SSODB) de la base de datos                  |                                                                                                                                                                                                                      Esta base de datos almacena información de credenciales.                                                                                                                                                                                                                       |
   |   **Host in-process** con instancias de host correspondientes    |                                                                                                                                                                        El host de tipo En curso funciona en el espacio de procesos de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].                                                                                                                                                                        |
   |    **Host aislado** con instancias de host correspondientes     |                                                                                                                                                                       El host aislado funciona fuera de la instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].                                                                                                                                                                        |
   | HTTP/S, Message Queue Server de BizTalk, archivo, SMTP, SOAP y SQL |                                                                                                                                                                   El Asistente para configuración crea los adaptadores que forman parte de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].                                                                                                                                                                    |


2. Use la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o WMI para agregar componentes al entorno de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] según sea necesario. Para escalar la solución de forma horizontal, agregue bases de datos de cuadro de mensajes, hosts y servidores.  

3. Utilice la consola de administración de BizTalk o WMI para crear instancias de host en los servidores asignados. Este paso determina en qué servidores se ejecutará [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Conforme cambien las necesidades de su empresa, puede agregar o quitar servidores, y cambiar la asignación servidor a host.  

## <a name="see-also"></a>Vea también  
 [Administración de Hosts de BizTalk y las instancias de Host](../core/managing-biztalk-hosts-and-host-instances.md)   
 [Hosts](../core/hosts.md)   
 [Instancias de host](../core/host-instances.md)