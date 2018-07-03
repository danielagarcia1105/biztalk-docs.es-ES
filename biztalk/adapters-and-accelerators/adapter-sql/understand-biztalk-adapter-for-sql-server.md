---
title: Comprender el adaptador de BizTalk para SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 302a7f20-ffa2-49f1-a4c4-dd713adc23e1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea21a06ad5d87e94118aaa45e2f6f541627aae9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996940"
---
# <a name="understand-biztalk-adapter-for-sql-server"></a>Comprender el adaptador de BizTalk para SQL Server
El [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] permite el acceso mediante programación orientada a servicios que lo que permite interactuar con un sistema externo. Los adaptadores proporcionan las siguientes ventajas a los clientes:  
  
- **Experiencia en tiempo de diseño coherente**. Los adaptadores proporcionan una experiencia en tiempo de diseño comunes y fácil de usar para explorar, buscar y recuperar los metadatos de artefactos de LOB.  
  
- **Variar las opciones de programación**. Los adaptadores proporcionan una elección del modelo de programación incluido el modelo de canal de Windows Communication Foundation (WCF), WCF del servicio servicios Web de model, ADO.NET, o modelos admitidos de BizTalk.  
  
- **Uniforme de experiencia en LOB**. Los adaptadores de estandarizan sobre el uso de WCF y la [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]y por lo tanto, proporcionar una experiencia uniforme de obtener acceso a cualquier sistema LOB.  
  
  Como se mencionó, los adaptadores se crean sobre el SDK de adaptador LOB de WCF. El SDK de adaptador LOB de WCF proporciona una base común para la creación de adaptadores de integración que puede consumir una gran variedad de aplicaciones de cliente como el servidor BizTalk Server y Microsoft Office. El SDK de adaptador LOB de WCF se alinea a la estrategia de adaptador con la estrategia de Microsoft Services mediante la exposición de los adaptadores de integración como canales de Windows Communication Foundation (WCF). Para obtener más información sobre el SDK de adaptador LOB de WCF, vea [documentación del SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/microsoft-wcf-line-of-business-adapter-sdk-documentation.md).
  
  Para llevar a cabo operaciones en una base de datos de SQL Server, los clientes del adaptador deben tener acceso a las tablas relevantes, procedimientos, vistas, funciones escalares y funciones con valores de tabla. Las tablas de base de datos son la unidad básica de almacenamiento en la base de datos de SQL Server. Las aplicaciones externas pueden seleccionar, insertar, eliminar y actualizar los datos de una tabla mediante el uso de instrucciones SQL. Las aplicaciones también pueden tener acceso a datos en las tablas mediante el uso de procedimientos, vistas, funciones escalares y funciones con valores de tabla. Con [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)], los clientes del adaptador pueden examinar los artefactos, como tablas, procedimientos, vistas y otros elementos de este tipo en una base de datos de SQL Server. Los clientes del adaptador pueden seleccionar los artefactos que se requieren para su solución y recuperar metadatos para aquellos artefactos. Esto permite a los usuarios obtener acceso a ejecutar las operaciones en los artefactos en la base de datos de SQL Server.  
  
  En esta sección se enumera las características de la [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Información general sobre el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)  
  
-   [Características clave en el adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/key-features-in-biztalk-adapter-for-sql-server.md) 
  
-   [Limitaciones del adaptador de BizTalk para SQL Server](../../adapters-and-accelerators/adapter-sql/limitations-of-biztalk-adapter-for-sql-server.md)  
  
## <a name="see-also"></a>Vea también  
[Empezar a trabajar con el adaptador de BizTalk para SQL](../../adapters-and-accelerators/adapter-sql/get-started-with-the-biztalk-adapter-for-sql.md)