---
title: Cómo se acumula el estado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c37644cd-7d3c-4e93-ad56-101043cfa685
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25dd7a2aea4d01a2fd84fe294f793cda833d1322
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297668"
---
# <a name="how-health-rolls-up"></a>Resúmenes de estados
El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack clasifica la implementación de BizTalk Server, las aplicaciones y sus artefactos constituyentes dentro de una estructura de capas donde el estado de una capa puede depender del estado del nivel inferior.  
  
-   Implementación de BizTalk  
  
-   Aplicación de BizTalk  
  
## <a name="health-roll-up-for-biztalk-deployment"></a>Resumen de estado para la implementación de BizTalk  
 El diagrama siguiente muestra cómo los Estados de mantenimiento de implementación de BizTalk Server se acumula en este módulo de administración.  
  
 ![Modelo de implementación](../technical-guides/media/biztalk2010mp-deploymentmodel.gif "BizTalk2010MP DeploymentModel")  
  
 La tabla siguiente describen los componentes que se muestran en el diagrama de flujo de trabajo de implementación de BizTalk Server.  
  
|Nombre|Description|Mantenimiento|  
|----------|-----------------|------------|  
|Grupo de implementación de BizTalk|Un grupo que contiene varios servidores de tiempo de ejecución con componentes como motor de reglas en tiempo de ejecución.|El estado de este grupo depende de la disponibilidad de<br /><br /> : Rol BAM<br />: Implementación del Host de BizTalk<br />: Función de tiempo de ejecución de BizTalk<br />-Motor regla|  
|Rol BAM|Un servidor en el que BAM está instalado el componente.|El estado de esto depende de la función de tiempo de ejecución BAM y el Portal de BAM.|  
|Implementación del Host de BizTalk|Una entidad lógica que define los límites para los diferentes artefactos de la aplicación para que se ejecute o parámetros de tiempo de ejecución. Varias instancias de este (instancias de host) se ejecutan como servicios NT en servidores diferentes en tiempo de ejecución.|El estado de este grupo depende de la disponibilidad de distintas instancias de este host.|  
|Función de tiempo de ejecución de BizTalk|Un servidor donde está instalado el tiempo de ejecución de BizTalk.|El estado de este grupo depende de la disponibilidad de<br /><br /> : Servicio SSO<br />: Base de datos de administración<br />: Base de datos de cuadro de mensajes<br />: Base de datos SSO<br />-Base de datos de seguimiento|  
|Rol de motor de reglas|Un servidor que tiene instalado el motor de reglas.|El estado de este grupo depende de la disponibilidad del servicio de motor de reglas y la base de datos de motor de reglas<br /><br /> : Servicio motor de reglas<br />: Base de datos de motor de reglas|  
|Función de tiempo de ejecución BAM|Un servidor en que BAM está instalado el componente de tiempo de ejecución.|El estado de esto depende de la disponibilidad de<br /><br /> : Base de datos de importación principal de BAM<br />: Base de datos de archivo BAM<br />: Análisis de BAM<br />: Las alertas de BAM|  
|Portal de BAM|Un servidor Web que tiene la aplicación de portal de BAM instalada y configurada.|El estado de esto depende de la disponibilidad de aplicación de portal de BAM.|  
|Instancia de host|Un servicio de Windows NT configurado para ejecutarse en tiempo de ejecución de BizTalk server.|El estado de esto es depende del estado del servicio de Windows NT.|  
|Servicio SSO|Un servicio de Windows NT para SSO.|El estado de esto es depende del estado del servicio SSO.|  
|Base de datos de administración|Un servidor de SQL que contiene una o varias bases de datos de BizTalk.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Base de datos de cuadro de mensaje|Un servidor de SQL que contiene una o más bases de datos de BizTalk MessageBox.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Servicio motor de reglas|Un servicio de motor de reglas que se utiliza para procesar las reglas de BizTalk.|El estado de esto depende de la disponibilidad del servicio de motor de reglas.|  
|Base de datos de motor de reglas|Un servidor de SQL que contiene una o más bases de datos de motor de reglas de BizTalk.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Base de datos de importación principal de BAM|Un servidor de SQL que contiene las bases de datos BAM.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Base de datos de archivo de BAM|Una base de datos de SQL Server que contiene los datos archivados.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Análisis de BAM|Contiene los datos de análisis BAM en línea y sin conexión.|El estado de esto es depende de la disponibilidad de los datos de análisis BAM.|  
|Alertas de BAM|Un servicio de notificación de SQL.|El estado de esto es depende del estado del servicio de notificación.|  
|Servicio de alertas de BAM|Un servicio de notificación de SQL.|El estado de esto es depende del estado del servicio de notificación.|  
|Base de datos de análisis de BAM|Una base de datos de SQL Server que contiene los datos de análisis BAM en línea y sin conexión.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Base de datos de esquema de estrella de SAE|Contiene la tabla provisional y las tablas de dimensiones y medidas.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Base de datos de seguimiento|Una base de datos de SQL Server que almacena los datos de seguimiento de motor de seguimiento de BizTalk Server de supervisión de estado.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
|Base de datos de SSO|SQL Server que hospeda la base de datos SSO.|El estado de esto es depende de la disponibilidad de la disponibilidad de la base de datos de SQL Server.|  
  
## <a name="health-roll-up-for-biztalk-application"></a>Resumen de estado para la aplicación de BizTalk  
 El diagrama siguiente muestra cómo los Estados de mantenimiento de la aplicación de BizTalk y sus artefactos constituyentes se acumula en este módulo de administración.  
  
 ![Modelo de aplicación](../technical-guides/media/biztalkserver2010mp-applicationmodel.gif "BizTalkServer2010MP ApplicationModel")  
  
 La tabla siguiente describen los componentes que se muestran en el diagrama de flujo de trabajo de aplicaciones de BizTalk.  
  
|Nombre|Description|Mantenimiento|  
|----------|-----------------|------------|  
|Grupo de BizTalk|Un grupo que contiene los artefactos de la aplicación. Todos estos artefactos se almacenan en una base de datos centralizada que se denomina base de datos de configuración. Estos artefactos se pueden detectar desde cualquiera de los equipos en tiempo de ejecución.|El estado de este grupo depende de la disponibilidad de Host de BizTalk y aplicaciones de BizTalk.|  
|Host|Una entidad lógica que define los límites para los diferentes artefactos de la aplicación para que se ejecute o parámetros de tiempo de ejecución. Varias instancias de este (instancias de host) se ejecutan como servicios NT en servidores diferentes en tiempo de ejecución.|El estado de este grupo depende de la disponibilidad de otra instancia de este host.|  
|Aplicación|Un grupo de artefactos de la aplicación de BizTalk, como orquestaciones, esquemas, asignaciones y canalizaciones. Componentes de mensajería como puertos de envío, ubicaciones de recepción y puertos de recepción. Instancias de estos artefactos se ejecutan en la instancia de host cuando el servidor BizTalk Server recibe un mensaje adecuado.|El estado de esto depende de la<br /><br /> : Estado configuración de puerto de recepción<br />-En tiempo de ejecución estado del puerto de recepción<br />: Estado configuración de puerto de envío<br />-Estado de orquestación<br />-En tiempo de ejecución estado de orquestación|  
|Puerto de recepción|Un artefacto de BizTalk que se ejecuta en una instancia de host. Esto se ejecuta cuando el servidor BizTalk Server recibe un mensaje. Recepción puerto contiene uno o más la ubicación de recepción.|El estado de esto depende del estado de configuración y estado en tiempo de ejecución de puerto de recepción.|  
|Ubicación de recepción|Un artefacto de BizTalk que recibe el mensaje desde un sistema externo. Utiliza un adaptador con su punto de conexión asociado para recibir un mensaje.|El estado de esto depende del estado de configuración y estado en tiempo de ejecución de la ubicación de recepción.|  
|Puerto de envío|Envía el mensaje procesado a un sistema externo.|El estado de esto depende del estado de configuración y estado en tiempo de ejecución de puerto de envío.|  
|Orquestación|Recibe un mensaje desde el puerto de recepción y procesa el mensaje. Orquestación es similar al flujo de trabajo.|El estado de este depende del estado de configuración en tiempo de ejecución y de estado de orquestación.|  
|Grupo de puertos de envío|Un grupo lógico de puertos de envío que recibe el mensaje de cuadro de mensaje de BizTalk y lo envía a sistemas externos.|El estado de este grupo depende del estado de los puertos de envío en este grupo.|