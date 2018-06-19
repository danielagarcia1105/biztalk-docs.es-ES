---
title: Introducción a la arquitectura del adaptador de BizTalk para SQL Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d31eb73f-b73e-4cd3-8b62-207b806175ee
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 841f07bfb8c027ab2bfc1b98e23b225af42b449c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225252"
---
# <a name="architecture-overview-of-biztalk-adapter-for-sql-server"></a>Introducción a la arquitectura del adaptador de BizTalk para SQL Server
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Este enlace contiene un elemento de enlace de transporte personalizado único que permite la comunicación con una base de datos de SQL Server. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] ajustada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] tiempo de ejecución y se expone a las aplicaciones a través de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal. El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se comunica con la base de datos de SQL Server a través de ADO.NET.  


 En la siguiente ilustración muestra la arquitectura de-to-end de soluciones que se desarrollan usando la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/05e2a88c-a3cc-42a7-9c06-cfdb7c071e70.gif "05e2a88c-a3cc-42a7-9c06-cfdb7c071e70")  

  
## <a name="consuming-the-adapter"></a>Consumir el adaptador  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expone la base de datos de SQL Server como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio a las aplicaciones cliente. Para realizar operaciones y obtener acceso a datos en la base de datos de SQL Server, las aplicaciones de cliente intercambian mensajes SOAP con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] a través de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales. La ilustración anterior muestra cuatro maneras en que la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] puede ser utilizado.  
  
-   **A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de solicitud de canal**. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación de modelo del canal realiza operaciones en la base de datos de SQL Server mediante el uso de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal para intercambiar SOAP mensajes directamente con el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Vea [aplicaciones desarrollar SQL mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).
  
-   **A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio**. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio llama a métodos en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente para realizar operaciones en la base de datos de SQL Server. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente modela las operaciones expuestas por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] como métodos. NET. Puede usar el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] o el WCF ServiceModel Metadata Utility Tool (svcutil.exe) para crear un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] clase de cliente de los metadatos expuestos por la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  Vea [aplicaciones desarrollar SQL utilizando el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md).
  
-   **A través de BizTalk, ubicación de recepción o puerto de envío que está configurado para usar el adaptador de Microsoft BizTalk WCF-Custom**. El adaptador WCF-Custom habilita el uso de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] características de extensibilidad. Mediante el adaptador de WCF-Custom puede seleccionar y configurar el enlace de la base de datos de SQL y el comportamiento de la ubicación de recepción o puerto de envío. Para obtener más información sobre cómo usar el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] soluciones, consulte [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md). 
  
-   **A través de un servicio Web hospedado en IIS**. En este escenario, un proxy de servicio WCF generado mediante el adaptador se hospeda en IIS mediante el enlace de Http de WCF estándar. Esto expone el contrato de servicio como un servicio Web a los usuarios externos. IIS aloja automáticamente el adaptador en tiempo de ejecución, que, a su vez, se comunica con la base de datos de SQL Server.  
  
## <a name="the-sql-adapter-and-wcf"></a>El adaptador de SQL y WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]presenta un modelo de programación basado en el intercambio de mensajes SOAP a través de canales entre clientes y servicios. Estos mensajes se envían entre los extremos expuestos por un cliente y un servicio de comunicación. Un punto de conexión consta de:  
  
-   Un *dirección de extremo*, que especifica la ubicación a la que se reciben los mensajes.  
  
-   A *enlace*, que especifica los protocolos de comunicaciones utilizados para intercambiar mensajes.  
  
-   A *contrato*, que especifica los tipos de operaciones y los datos expuestos por el punto de conexión.  
  
 Un enlace está compuesto de uno o más elementos de enlace que se apilan uno sobre otro para definir cómo se intercambian los mensajes con el punto de conexión. Como mínimo, un enlace debe especificar el transporte y codificación que se usan para intercambiar mensajes con el punto de conexión. Intercambio de mensajes entre los puntos de conexión se produce en una pila de canales que se compone de uno o más canales. Cada canal es una implementación concreta de uno de los elementos de enlace en el enlace configurado para el extremo. 

El [documentación de WCF](http://go.microsoft.com/fwlink/?LinkID=196850) incluye más detalles acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]y el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de programación.  
  
 El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] expone un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlace personalizado, el enlace de la base de datos de SQL (**Microsoft.Adapters.SQLDB.SQLDBBinding**). De forma predeterminada, este enlace contiene un elemento de enlace de transporte personalizado único, el elemento de enlace del adaptador de base de datos de SQL (**Microsoft.Adapters.SQLDB.SQLDBAdapter**), lo que permite las operaciones en una base de datos de SQL Server.  
  
 **Microsoft.Adapters.SQLDB.SQLDBBinding** (el SQL DB enlace) y **Microsoft.Adapters.SQLDB.SQLDBAdapter** (la SQL DB adaptador de elemento de enlace) son las clases públicas y también se exponen al sistema de configuración. Dado que el elemento de enlace de adaptador de base de datos de SQL se exponen públicamente, puede crear su propio personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces capaces de ampliar la funcionalidad de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Por ejemplo, podría implementar un enlace personalizado para admitir el inicio de sesión único empresarial (SSO) en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio o canal. Los motivos para realizar esta acción podría consistir en operaciones de agregado de la base de datos en una sola operación multifunción o para realizar la transformación de esquema entre las operaciones que se implementa una aplicación personalizada y operaciones en la base de datos de SQL Server.  
  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y se ejecuta en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] tiempo de ejecución. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una infraestructura de marco de trabajo y herramientas de software que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] usa para proporcionar un amplio conjunto de características para los usuarios y los clientes de adaptador.  

## <a name="sql-adapter-and-the-wcf-lob-adapter-sdk"></a>Adaptador de SQL y el SDK de adaptador LOB de WCF
El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] implementa un conjunto de componentes principales que aprovechan la funcionalidad proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y proporcionar conectividad a la base de datos de SQL Server a través de ADO.NET.  
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] actúa como la capa de software a través del cual el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se comunica con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]; ADO.NET actúa como la capa a través del cual el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] interfaces con la base de datos de SQL Server. La siguiente ilustración muestra las relaciones entre los componentes internos de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] y entre estos componentes y ADO.NET.  
  
 ![](../../adapters-and-accelerators/adapter-sql/media/0b15e33b-7f59-4228-bb50-0455f7ed3d85.gif "0b15e33b-7f59-4228-bb50-0455f7ed3d85")  
 
   
## <a name="adonet"></a>ADO.NET  
 El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] se conecta con la base de datos de SQL Server a través de ADO.NET. ADO.NET proporciona acceso coherente a orígenes de datos como SQL Server y facilita la recuperación, control y modificación de los datos de los orígenes de datos. Obtenga más información sobre [ADO.NET](https://msdn.microsoft.com/library/e80y5yhx.aspx).
  
 El cliente SQL proporciona conectividad a la base de datos de SQL Server. Establecer una conexión con una base de datos de SQL Server al proporcionar un URI de conexión para el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]. Este URI de conexión contiene el nombre del equipo donde está instalado el servidor SQL Server y el nombre de la base de datos. Para obtener más información sobre el URI de conexión, consulte [crear una conexión a SQL Server](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md).  
  
## <a name="see-also"></a>Vea también  

 [Comprender el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)