---
title: Comprender el adaptador de BizTalk para Oracle E-Business Suite | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 77a3f0a8-fc64-42cd-bb7c-0a6f527622e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 342ffbd77434a470e3afdd10ae1c708c8734e85c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964594"
---
# <a name="understand-biztalk-adapter-for-oracle-e-business-suite"></a>Comprender el adaptador de BizTalk para Oracle E-Business Suite
## <a name="biztalk-adapter-pack-features"></a>Características de BizTalk Adapter Pack
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
-   **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño común y fácil de usar para la exploración, búsqueda y recuperación de metadatos de artefactos de LOB.  
  
-   **Opciones de programación de variados**. Los adaptadores proporcionan servicios Web ADO.NET, modelo de servicio de una opción de modelo de programación incluido el modelo de canal de Windows Communication Foundation (WCF), WCF o BizTalk Server admite los modelos.  
  
-   **Uniformes experiencia a través de LOB**. Los adaptadores estandarización sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
 Como se mencionó, los adaptadores se generan en la parte superior de la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]. Este SDK proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones cliente como el servidor BizTalk Server y Microsoft Office. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] Alinee la estrategia de adaptador con la estrategia de servicios de Microsoft mediante la exposición de adaptadores de integración como canales WCF. Para obtener más información sobre la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], consulte el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación. El [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] documentación está instalada junto con la [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], normalmente en \< *unidad de instalación*\>: \Program archivos\\[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]\Documents.  

## <a name="overview-of-the-oracle-ebs-adapter"></a>Información general sobre el adaptador de Oracle EBS
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone Oracle E-Business Suite como un servicio WCF. Los clientes de adaptador pueden realizar operaciones en Oracle E-Business Suite mediante el intercambio de mensajes SOAP con el adaptador. El adaptador consume el mensaje SOAP y realiza llamadas ODP.NET adecuadas para realizar la operación. El adaptador devuelve la respuesta de Oracle E-Business Suite al cliente en forma de mensajes SOAP.  
  
 La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]muestra los metadatos de los artefactos de Oracle E-Business Suite (API de PL/SQL, las tablas o vistas de interfaz, programas simultáneos y conjuntos de solicitudes) y el subyacente Oracle base de datos artefactos (por ejemplo, tablas, funciones y procedimientos) que describen la estructura de un mensaje SOAP con el formato de lenguaje de descripción de servicios Web (WSDL). El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] utiliza la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes de adaptador recuperar metadatos para las operaciones. El adaptador también genera artefactos de programación que se pueden usar en la solución de programación. Para obtener más información acerca de [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa el proveedor de datos de Oracle para .NET (ODP.NET) 11.1.0.7 para comunicarse con Oracle E-Business Suite. ODP.NET 11.1.0.7 es uno de los componentes de componentes de acceso de datos de Oracle (ODAC). Puede usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para comunicarse con Oracle E-Business Suite de las maneras siguientes:  
  
-   Al desarrollar aplicaciones de BizTalk. Para obtener más información, consulte [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).  
  
-   Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio. Para obtener más información, consulte [desarrollar Oracle base de datos de aplicaciones usando el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).  
  
-   Mediante el modelo de canal WCF. Para obtener más información, consulte [desarrollar aplicaciones de SQL mediante el modelo de canal de WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).  

## <a name="access-to-oracle-e-business-suite"></a>Acceso a Oracle E-Business Suite
 Para realizar operaciones en Oracle E-Business Suite, los clientes de adaptador deben tener acceso a los artefactos correspondientes en Oracle E-Business Suite. Las aplicaciones externas pueden agregar o quitar datos en tablas de la interfaz de Oracle E-Business Suite y las tablas de base de datos mediante instrucciones SQL. Las aplicaciones también pueden tener acceso a datos en las tablas de interfaz y las tablas de base de datos mediante el uso de vistas, funciones y procedimientos. Con [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], los clientes de adaptador pueden examinar los artefactos de Oracle E-Business Suite, así como en la base de datos subyacente. En Oracle E-Business Suite, los clientes de adaptador pueden examinar tablas de interfaz, vistas de interfaz, programas simultáneos y solicitar conjuntos mientras la base de datos de Oracle subyacente, los clientes de adaptador pueden examinar las tablas, vistas, procedimientos almacenados, funciones, las API de PL/SQL y paquetes. Los clientes de adaptador pueden seleccionar los artefactos que necesitan para su solución y recuperan metadatos para los artefactos. Esto permite a los usuarios tener acceso a y ejecutar las operaciones en los artefactos en Oracle E-Business Suite y la base de datos de Oracle subyacente.  
  
 En esta sección se enumera las características de la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].  
  
## <a name="more-good-stuff"></a>Otros recursos útiles  
  
-    [Conectarse a Oracle E-Business Suite mediante el adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-the-adapter.md)

- [Buscar, búsqueda y obtener los metadatos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-oracle-e-business-suite-metadata.md)

- [Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)

- [Controlar las transacciones con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md) 

- [Características para los clientes del adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/features-for-oracle-ebs-adapter-clients.md) 

-   [Características clave en el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/key-features-in-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [Limitaciones del adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/limitations-of-biztalk-adapter-for-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>Vea también  
[Introducción](../../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)