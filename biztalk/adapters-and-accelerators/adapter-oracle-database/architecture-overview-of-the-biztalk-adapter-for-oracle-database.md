---
title: Introducción a la arquitectura del adaptador de BizTalk para base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, and WCF
- architecture of the Oracle Database adapter
- ODAC
- Oracle Data Access Components
- endpoint
- adapter, architecture
- endpoint address
- ODP.NET
- Oracle Data Provider for .NET
- architecture
ms.assetid: cc59beb5-327a-4b00-a45c-82cc9d505167
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f5d4a23b9802c04af37716f8bef07735d8f80bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216596"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-database"></a>Introducción a la arquitectura del adaptador de BizTalk para base de datos de Oracle
Describe la arquitectura para la [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]. 

Una descripción de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] arquitectura le permitirá:  
  
-   Comprender la relación entre el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].  
  
-   Comprender los límites de seguridad, por lo que puede proteger mejor los datos de la solución.  
  
-   Comprender el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] propiedades de enlace.  
  
-   Solucionar problemas de instalación.  
  
Este tema describe la arquitectura de soluciones de extremo a extremo que usan el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] para operar en una base de datos de Oracle y también se describe la arquitectura interna de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
 
## <a name="adapter-architecture-overview"></a>Información general de arquitectura de adaptador
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Este enlace contiene un elemento de enlace de transporte personalizado único que permite la comunicación con una base de datos de Oracle. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] ajustada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] en tiempo de ejecución y se expone a las aplicaciones a través de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se comunica con la base de datos de Oracle a través del proveedor de datos de Oracle para .NET (ODP.NET) y el cliente de Oracle, que forman parte de los componentes de acceso de datos de Oracle (ODAC) para Windows.  
  
 En la siguiente ilustración muestra la arquitectura de-to-end de soluciones que se desarrollan usando la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].  
  
 ![Diagrama de arquitectura de adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/bts-oracledb-architecturec.gif "bts_OracleDB_Architecturec")  
  
## <a name="consuming-the-adapter"></a>Consumir el adaptador  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expone la base de datos de Oracle como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio a las aplicaciones cliente. Para realizar operaciones y obtener acceso a datos en la base de datos de Oracle, las aplicaciones de cliente intercambian mensajes SOAP con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] a través de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales. En la ilustración anterior muestra cuatro maneras en que la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] puede ser utilizado. Estas sobrecargas son:  
  
-   A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]modelo de solicitud de canal. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación de modelo del canal realiza operaciones en la base de datos de Oracle mediante el uso de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal para intercambiar SOAP mensajes directamente con el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información sobre cómo desarrollar soluciones para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] mediante el uso de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de canales, vea [aplicación de desarrollo de base de datos de Oracle mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).  
  
-   A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio llama a métodos en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente para realizar operaciones en la base de datos de Oracle. A [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente modela las operaciones expuestas por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] como métodos. NET. Puede usar el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] o el WCF ServiceModel Metadata Utility Tool (svcutil.exe) para crear un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] clase de cliente de los metadatos expuestos por la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Para obtener más información sobre la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio y la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [desarrollar aplicaciones de base de datos Oracle utilizando el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).  
  
-   A través de un BizTalk ubicación de recepción o puerto de envío que está configurado para usar el adaptador de Microsoft BizTalk WCF-Custom. El adaptador WCF-Custom habilita el uso de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] características de extensibilidad. Mediante el adaptador de WCF-Custom puede seleccionar y configurar el enlace de la base de datos de Oracle y el comportamiento de la ubicación de recepción o puerto de envío. Para obtener más información sobre cómo usar el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] soluciones, consulte [desarrollar las aplicaciones de BizTalk](../../core/develop-your-biztalk-applications.md).  
  
-   A través de un servicio Web hospedado en IIS. En este escenario, un proxy de servicio WCF generado mediante el adaptador se hospeda en IIS mediante el enlace de Http de WCF estándar. Esto expone el contrato de servicio como un servicio Web a los usuarios externos. IIS aloja automáticamente el adaptador en tiempo de ejecución, que, a su vez, se comunica con la base de datos de Oracle.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] y ODAC siempre se hospedan en proceso con la aplicación o servicio que utiliza el adaptador.  
  
## <a name="oracle-database-adapter-and-wcf"></a>WCF y el adaptador de base de datos de oracle  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]presenta un modelo de programación basado en el intercambio de mensajes SOAP a través de canales entre clientes y servicios. Estos mensajes se envían entre los extremos expuestos por un cliente y un servicio de comunicación. Un punto de conexión consta de:  
  
-   Un *dirección de extremo*, que especifica la ubicación a la que se reciben mensajes  
  
-   A *enlace*, que especifica los protocolos de comunicaciones utilizados para intercambiar mensajes  
  
-   A *contrato*, que especifica los tipos de operaciones y los datos expuestos por el punto de conexión.  
  
 Un enlace está compuesto de uno o más elementos de enlace que se apilan uno sobre otro para definir cómo se intercambian los mensajes con el punto de conexión. Como mínimo, un enlace debe especificar el transporte y codificación que se usan para intercambiar mensajes con el punto de conexión. Intercambio de mensajes entre los puntos de conexión se produce en una pila de canales que se compone de uno o más canales. Cada canal es una implementación concreta de uno de los elementos de enlace en el enlace configurado para el extremo. El [documentación de WCF](http://go.microsoft.com/fwlink/?LinkID=196850) incluye más detalles acerca de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]y el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de programación.  
  
 El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlace personalizado, el enlace de la base de datos de Oracle (**Microsoft.Adapters.OracleDB.OracleDBBinding**). De forma predeterminada, este enlace contiene un elemento de enlace de transporte personalizado único, el elemento de enlace del adaptador de base de datos de Oracle (**Microsoft.Adapters.OracleDB.OracleDBAdapter**), lo que permite las operaciones en una base de datos de Oracle.  
  
 **Microsoft.Adapters.OracleDB.OracleDBBinding** (el Oracle DB enlace) y **Microsoft.Adapters.OracleDB.OracleDBAdapter** (la Oracle DB adaptador de elemento de enlace) son las clases públicas y también se exponen para el sistema de configuración. Dado que el elemento de enlace de adaptador de base de datos de Oracle se exponen públicamente, puede crear su propio personalizado [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces capaces de ampliar la funcionalidad de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Por ejemplo, podría implementar un enlace personalizado para admitir el inicio de sesión único empresarial (SSO) en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio o canal. Los motivos para realizar esta acción podría consistir en operaciones de agregado de la base de datos en una sola operación multifunción o para realizar la transformación de esquema entre las operaciones que se implementa una aplicación personalizada y operaciones en la base de datos de Oracle.  
  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se crea en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y se ejecuta en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en tiempo de ejecución. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una infraestructura de marco de trabajo y herramientas de software que el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] usa para proporcionar un amplio conjunto de características para los usuarios y los clientes de adaptador.  

## <a name="oracle-database-adapter-and-wcf-lob-adapter-sdk"></a>Adaptador de base de datos de Oracle y el SDK del adaptador LOB de WCF
El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] implementa un conjunto de componentes principales que aprovechan la funcionalidad proporcionada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] y proporcionar conectividad a la base de datos de Oracle a través del proveedor de datos de Oracle para .NET (ODP.NET).  
  
 El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] actúa como la capa de software a través del cual el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se comunica con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. ODP.NET actúa como la capa a través del cual el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interfaces con la base de datos de Oracle. 
 
La siguiente ilustración muestra las relaciones entre los componentes internos de la [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]y ODP.NET.  
  
 ![Arquitectura interna del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/media/fa730561-9db7-40d1-bfcd-bc4eb119eea8.gif "fa730561-9db7-40d1-bfcd-bc4eb119eea8")  
 
   
## <a name="odpnet"></a>ODP.NET  
 El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] se conecta con la base de datos de Oracle a través de la ODP.NET y el cliente de Oracle. Ambos de estos componentes forman parte de componentes de acceso de datos de Oracle (ODAC).  
  
 ODP.NET implementa un proveedor de datos para la base de datos de Oracle que es coherente con la interfaz ADO.NET. El [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] utiliza las clases expuestas por ODP.NET para operar en la base de datos de Oracle.  
  
 El cliente de Oracle proporciona conectividad a la base de datos de Oracle. Establecer una conexión con una base de datos de Oracle proporcionando un URI de conexión para el [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]. Puede especificar el URI de conexión de dos maneras:  
  
-   **Usar tnsnames.ora**. En este enfoque, el URI proporcionado por el cliente del adaptador de conexión contiene solo el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión, como el nombre del servidor, el nombre del servicio, el número de puerto, etc. de la entrada de nombre de servicio de red en el archivo. Para utilizar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
-   **Sin usar tnsnames.ora**. En este enfoque, los clientes de adaptador especifican los parámetros de conexión directamente en el URI de conexión. Esto no requiere el nombre de servicio de red que esté presente en el archivo tnsnames.ora en el equipo cliente. Este enfoque no requiere incluso el archivo tnsnames.ora debe estar presente en el equipo cliente.  
  
 Para obtener más información sobre el URI de conexión, consulte [crear una conexión a la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md).
  
## <a name="next"></a>Siguiente
[Proteger las aplicaciones de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)