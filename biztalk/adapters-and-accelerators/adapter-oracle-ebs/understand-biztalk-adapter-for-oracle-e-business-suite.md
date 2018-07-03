---
title: Comprender el adaptador de BizTalk para Oracle E-Business Suite | Microsoft Docs
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
ms.openlocfilehash: ebf84eef3d5e1ec4730926dd34b6533e1a7491f8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980549"
---
# <a name="understand-biztalk-adapter-for-oracle-e-business-suite"></a>Comprender el adaptador de BizTalk para Oracle E-Business Suite
## <a name="biztalk-adapter-pack-features"></a>Características de BizTalk Adapter Pack
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios con el fin de interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
- **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño comunes y fácil de usar para explorar, buscar y recuperar los metadatos de artefactos de LOB.  
  
- **Variar las opciones de programación**. Los adaptadores proporcionan una opción de modelo de programación incluyen el modelo de canal de Windows Communication Foundation (WCF), WCF del servicio servicios Web de model, ADO.NET, o BizTalk Server admite los modelos.  
  
- **Uniforme de experiencia en LOB**. Los adaptadores de estandarizan sobre el uso de WCF y [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
  Como se mencionó, los adaptadores se crean sobre el SDK de adaptador LOB de WCF. El SDK de adaptador LOB de WCF proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones de cliente como el servidor BizTalk Server y Microsoft Office. El SDK de adaptador LOB de WCF se alinea a la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de los adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre el SDK de adaptador LOB de WCF, vea [documentación del SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).

## <a name="overview-of-the-oracle-ebs-adapter"></a>Información general sobre el adaptador de Oracle EBS
La [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] expone Oracle E-Business Suite como un servicio WCF. Los clientes del adaptador pueden realizar operaciones en Oracle E-Business Suite mediante el intercambio de mensajes SOAP con el adaptador. El adaptador consume el mensaje SOAP y realiza llamadas ODP.NET adecuadas para realizar la operación. El adaptador devuelve la respuesta de Oracle E-Business Suite al cliente en forma de mensajes SOAP.  
  
 La [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]muestra los metadatos de los artefactos de Oracle E-Business Suite (API de PL/SQL, tablas o vistas de interfaz, programas simultáneos y conjuntos de solicitud) y el subyacente Oracle database artefactos (como tablas, funciones y procedimientos) que describen la estructura de un mensaje SOAP en forma de lenguaje de descripción de servicios Web (WSDL). El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para permitir que los clientes del adaptador recuperar metadatos para las operaciones. El adaptador genera también los artefactos de programación que se pueden usar en la solución de programación. Para obtener más información acerca de [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
 El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] usa el proveedor de datos de Oracle para .NET (ODP.NET) 11.1.0.7 para comunicarse con Oracle E-Business Suite. ODP.NET 11.1.0.7 es uno de los componentes de Oracle Data Access Components (ODAC). Puede usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] para comunicarse con Oracle E-Business Suite en las siguientes maneras:  
  
- Mediante el desarrollo de aplicaciones de BizTalk. Para obtener más información, consulte [desarrollar aplicaciones de BizTalk Server](../../core/developing-biztalk-server-applications.md).  
  
- Mediante el uso de la [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] modelo de servicio. Para obtener más información, consulte [desarrollar Oracle base de datos de aplicaciones por utilizando el modelo de servicio WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).  
  
- Mediante el modelo de canal WCF. Para obtener más información, consulte [desarrollar aplicaciones de SQL mediante el modelo de canal WCF](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).  

## <a name="access-to-oracle-e-business-suite"></a>Acceso a Oracle E-Business Suite
 Para realizar operaciones en Oracle E-Business Suite, los clientes del adaptador deben tener acceso a los artefactos pertinentes en Oracle E-Business Suite. Las aplicaciones externas pueden agregar o quitar datos en tablas de la interfaz de Oracle E-Business Suite y las tablas de base de datos mediante instrucciones SQL. Las aplicaciones también pueden tener acceso a datos en las tablas de interfaz y las tablas de base de datos mediante el uso de vistas, funciones y procedimientos. Con [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)], los clientes del adaptador pueden examinar los artefactos de Oracle E-Business Suite, así como en la base de datos subyacente. En Oracle E-Business Suite, los clientes del adaptador pueden examinar tablas, vistas de interfaz, programas simultáneos y solicitar conjuntos mientras la base de datos de Oracle subyacente, los clientes del adaptador pueden examinar las tablas, vistas, procedimientos almacenados, funciones, las API de PL/SQL y los paquetes. Los clientes del adaptador pueden seleccionar los artefactos que se requieren para su solución y recuperar metadatos para aquellos artefactos. Esto permite a los usuarios obtener acceso a ejecutar las operaciones en los artefactos en Oracle E-Business Suite y la base de datos de Oracle subyacente.  
  
 En esta sección se enumera las características de la [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].  
  
## <a name="more-good-stuff"></a>Otros recursos útiles  
  
-    [Conectarse a Oracle E-Business Suite mediante el adaptador](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-the-adapter.md)

- [Examinar, buscar y obtener metadatos de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-oracle-e-business-suite-metadata.md)

- [Las operaciones que son compatibles con el adaptador de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/what-operations-are-supported-by-the-oracle-e-business-suite-adapter.md)

- [Controlar las transacciones con el adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/handle-transactions-with-the-oracle-database-adapter.md) 

- [Características para los clientes del adaptador de Oracle EBS](../../adapters-and-accelerators/adapter-oracle-ebs/features-for-oracle-ebs-adapter-clients.md) 

-   [Características clave en el adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/key-features-in-biztalk-adapter-for-oracle-e-business-suite.md)  
  
-   [Limitaciones del adaptador de BizTalk para Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/limitations-of-biztalk-adapter-for-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>Vea también  
[Introducción](../../adapters-and-accelerators/adapter-oracle-ebs/get-started-with-the-biztalk-adapter-for-oracle-e-business-suite.md)