---
title: Introducción a la arquitectura del adaptador de BizTalk para Oracle E-Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f840ff23-4d68-4bd3-b115-aa87bc4c99f2
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc82d65b477cf1ac9ea7f7451c3521cc5a00a72c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007645"
---
# <a name="architecture-overview-of-the-biztalk-adapter-for-oracle-e-business-suite"></a>Introducción a la arquitectura del adaptador de BizTalk para Oracle E-Business Suite
El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado. Este enlace contiene un elemento de enlace de transporte personalizado único que permite la comunicación con un Oracle E-Business Suite. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] ajustada por el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] en tiempo de ejecución y se expone a aplicaciones a través de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] arquitectura de canal. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se comunica con Oracle E-Business Suite a través del proveedor de datos de Oracle para .NET (ODP.NET) y el cliente de Oracle, que forman parte de Oracle Data Access Components (ODAC) de Windows.  
  
 En la siguiente ilustración muestra la arquitectura de to-end de soluciones desarrolladas con la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
 ![Diagrama de arquitectura de adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-ebs/media/967bc4a5-852b-479e-8ef0-941773f5991f.gif "967bc4a5-852b-479e-8ef0-941773f5991f")  
  
## <a name="consuming-the-adapter"></a>Consumo del adaptador  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] expone Oracle E-Business Suite como un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] servicio a las aplicaciones cliente. Para realizar operaciones y obtener acceso a datos en Oracle E-Business Suite, las aplicaciones de cliente intercambian mensajes SOAP con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a través de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canales. La ilustración anterior muestra cuatro maneras en que la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] puede consumir. Estas sobrecargas son:   
  
- A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canal aplicación del modelo. Un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación de modelo del canal realiza operaciones en Oracle E-Business Suite mediante el uso de la [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal para intercambiar SOAP mensajes directamente con el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
- A través de un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio. Un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] aplicación del modelo de servicio llama a métodos en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente para realizar operaciones en Oracle E-Business Suite. Un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] cliente modela las operaciones expuestas por la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] como métodos. NET. Puede usar el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] o el WCF ServiceModel Metadata Utility Tool (svcutil.exe) para crear un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] clase de cliente desde los metadatos expuestos por el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].  
  
- A través de un BizTalk ubicación de recepción o puerto de envío que está configurado para usar el adaptador de Microsoft BizTalk WCF-Custom. El adaptador WCF-Custom habilita el uso de [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] las características de extensibilidad. Mediante el adaptador de WCF-Custom puede seleccionar y configurar el enlace de Oracle EBS y el comportamiento de la ubicación de recepción o puerto de envío. Para obtener más información sobre cómo usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] soluciones, consulte [aplicaciones de desarrollo de BizTalk con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/develop-biztalk-applications-using-the-oracle-e-business-suite-adapter.md).  
  
- A través de un servicio Web hospedado en IIS. En este escenario, un proxy de servicio WCF generado mediante el adaptador se hospeda en IIS mediante el enlace basicHttpBinding de WCF. Esto expone el contrato de servicio como un servicio Web a los usuarios externos. IIS hospeda automáticamente el adaptador en tiempo de ejecución, que, a su vez, se comunica con Oracle E-Business Suite.  
  
  El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] y ODAC siempre se hospedan en proceso con la aplicación o servicio que utiliza el adaptador.  
  
## <a name="oracle-ebs-adapter-and-wcf"></a>Adaptador de Oracle EBS y WCF  
 [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] presenta un modelo de programación basado en el intercambio de mensajes SOAP a través de canales entre clientes y servicios. Estos mensajes se envían entre los extremos expuestos por un cliente y servicio de comunicación. Un punto de conexión consta de:  
  
- Un *dirección de extremo*, que especifica la ubicación en la que se reciben los mensajes  
  
- Un *enlace*, que especifica los protocolos de comunicación que se usa para intercambiar mensajes  
  
- Un *contrato*, que especifica los tipos de operaciones y los datos expuestos por el punto de conexión.  
  
  Un enlace está compuesto de uno o varios elementos de enlace que se apilen para definir cómo se intercambian los mensajes con el punto de conexión. Como mínimo, un enlace debe especificar el transporte y codificación que se usan para intercambiar mensajes con el punto de conexión. Intercambio de mensajes entre los puntos de conexión se realiza a través de una pila de canales que se compone de uno o más canales. Cada canal es una implementación concreta de uno de los elementos de enlace en el enlace configurado para el extremo. El [documentación de WCF](http://go.microsoft.com/fwlink/?LinkID=196850) incluye más detalles sobre [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]y el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de programación.  
  
  El [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlace personalizado, el enlace de Oracle E-Business Suite (**Microsoft.Adapters.OracleEBS.OracleEBSBinding**). De forma predeterminada, este enlace contiene un elemento de enlace de transporte personalizado único, el elemento de enlace de Oracle E-Business Suite adaptador (**Microsoft.Adapters.OracleEBS.OracleEBSAdapter**), que habilita las operaciones en Oracle E-Business Suite.  
  
  **Microsoft.Adapters.OracleEBS.OracleEBSBinding** (la Oracle E-Business Suite enlace) y **Microsoft.Adapters.OracleEBS.OracleEBSAdapter** (la Oracle E-Business Suite adaptador de elemento de enlace) son públicos clases y se exponen también en el sistema de configuración. Dado que el elemento de enlace de adaptador de Oracle E-Business Suite se expone públicamente, puede crear su propio custom [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] enlaces capaces de ampliar la funcionalidad de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Por ejemplo, podría implementar un enlace personalizado para admitir el inicio de sesión único empresarial (SSO) en un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio o canal. Las razones para hacer esto sería a las operaciones de base de datos agregados en una sola operación multifunción o para realizar la transformación de esquema entre las operaciones que se implementa mediante una aplicación personalizada y en Oracle E-Business Suite.  

## <a name="oracle-ebs-adapter-and-the-wcf-lob-sdk"></a>Adaptador de Oracle EBS y el SDK de LOB de WCF
 
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se basa en la parte superior de la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y se ejecuta en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en tiempo de ejecución. 


El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] proporciona una infraestructura de marco y herramientas de software que el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa para proporcionar un amplio conjunto de características a los usuarios y los clientes del adaptador.  También sirve como la capa de software a través del cual el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] interactúa con el [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]. ODP.NET actúa como la capa a través del cual el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] interfaces con la base de datos de Oracle. 

La siguiente ilustración muestra las relaciones entre los componentes internos de la [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]y ODP.NET:  
  
 ![Oracle E&#45;arquitectura interna del adaptador Business](../../adapters-and-accelerators/adapter-oracle-ebs/media/bts-oracleebs-architecture-internalc.gif "bts_OracleEBS_Architecture_Internalc")  
  
## <a name="odpnet"></a>ODP.NET  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] se conecta con Oracle E-Business Suite a través de la ODP.NET y el cliente de Oracle. Ambos componentes forman parte de Oracle Data Access Components (ODAC).  
  
 ODP.NET implementa un proveedor de datos para Oracle E-Business Suite que sea coherente con la interfaz ADO.NET. El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza las clases expuestas por ODP.NET para operar en Oracle E-Business Suite.  
  
 El cliente Oracle proporciona conectividad con Oracle E-Business Suite. Establecer una conexión a un Oracle E-Business Suite, ya que proporciona un URI de conexión para el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]. Puede especificar el URI de conexión de dos maneras:  
  
- **Uso de tnsnames.ora**. En este enfoque, el URI proporcionado por el cliente del adaptador de conexión contiene únicamente el nombre de servicio de red especificado en el archivo tnsnames.ora. El adaptador extrae los parámetros de conexión, como el nombre del servidor, el nombre del servicio, el número de puerto, etc. de la entrada del nombre de servicio de red en el archivo. Para usar este enfoque, el equipo que ejecuta al cliente de Oracle debe configurarse para incluir el nombre de servicio de red para la base de datos de Oracle en el archivo tnsnames.ora.  
  
- **Sin usar tnsnames.ora**. En este enfoque, los clientes del adaptador especifican los parámetros de conexión directamente en el URI de conexión. Esto no requiere el nombre de servicio de red esté presente en el archivo tnsnames.ora en el equipo cliente. Incluso este enfoque no requiere el archivo tnsnames.ora esté presente en el equipo cliente.  
  
  Para obtener más información sobre el URI de conexión, consulte [crear una conexión a Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).  
  
## <a name="next"></a>Siguiente
[Proteger las aplicaciones de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/secure-your-oracle-ebs-applications.md)